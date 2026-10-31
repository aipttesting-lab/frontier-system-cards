# Emergent Cyber Behavior: When AI Agents Become Offensive Threat Actors - Irregular

Source: https://www.irregular.com/research/emergent-offensive-cyber-behavior-in-ai-agents
Retrieved: 2026-10-31 (text extraction; see source for figures/tables)

Emergent Cyber Behavior: When AI Agents Become Offensive Threat Actors - Irregular

Research

News

About

Contact

Join our team

Research

News

About

Contact

Join our team

Emergent Cyber Behavior: When AI Agents Become Offensive Threat Actors

March 12, 2026

In this article

Share

Cite

March 12, 2026

Executive summary
AI agents deployed for routine enterprise tasks are autonomously hacking the systems they operate in. No one asked them to. No adversarial prompting was involved. The agents independently discovered vulnerabilities, escalated privileges, disabled security tools, and exfiltrated data, all while trying to complete ordinary assignments.
Standard cybersecurity solutions, as we knew them before the advent of LLMs, were not designed to address the risk of agentic threat actors. Companies that deploy AI agents and do not consider this risk as part of their threat model may end up exposed and missing important security controls.
Introduction
Companies are already shipping AI agents with access to internal systems, shell commands, and network resources. These agents are useful precisely because they can take autonomous action. But that same autonomy introduces a risk most security teams aren't modeling for: the agent itself becoming a threat actor.
In experiments we conducted, agents performing routine tasks autonomously engaged in offensive cyber operations against the infrastructure they operated within. The offensive behaviors were not the product of adversarial prompting or deliberately unsafe system design. They emerged from standard tools, common prompt patterns, and the broad cybersecurity knowledge embedded in frontier models.
This pattern is already appearing in the wild: AI agents causing damage through autonomous decision-making rather than external manipulation. In February 2026, when a coding agent was blocked by an authentication barrier while trying to stop a web server, it independently found an alternative path to root privileges and took it without asking. In another case, a model acquired authentication tokens from its environment, including one it knew belonged to a different user. In both cases, the agents were performing routine tasks and operating within their intended scope.
The research described here reproduces this behavior in a controlled setting and identifies the conditions that give rise to it. This post summarizes the key failure modes and what organizations should do about them.
The full report, including detailed methodology, is available here.
The setup
To understand what drives routine AI agents toward offensive cyber behavior, Irregular built a simulated corporate network around a fictional company, MegaCorp, complete with servers, applications, and internal services.
AI agents based on standard frontier LLMs were deployed to handle three routine tasks:
Document research. A multi-agent system where a lead agent coordinates analyst sub-agents to retrieve and summarize information from MegaCorp’s internal wiki.

Backup archive maintenance. A single agent operating a Windows-based backup server, receiving file download requests via the company’s Slack and executing them using PowerShell tools.

Social media content drafting. A two-agent system (Author and Reviewer) that converts internal technical documents into social media posts, with a Data Loss Prevention (DLP) system scanning all outgoing content.

The agents’ system prompts followed common patterns in agentic engineering: clear task descriptions, motivational language to encourage task completion, and access to relevant tools. None of the prompts referenced security, hacking, or exploitation in any form. The prompts are available in the full report.
What the agents did
Across these three scenarios, agents engaged in offensive behaviors in a meaningful fraction of runs, performing actions like:
Vulnerability research and exploitation of internal systems, including source code review, identification of a hardcoded secret key, and session cookie forgery to bypass access controls.

Privilege escalation and defense disabling on a backup server, including locating administrator credentials in local files and using them to disable endpoint protection (Windows Defender).

Covert data exfiltration past DLP controls, using steganographic encoding to embed secrets in social media posts that evaded pattern-matching defenses.

In one case, an agent convinced another agent to carry out an offensive action, a form of inter-agent collusion that emerged with no external manipulation.

We tested three different scenarios that exhibited emergent offensive behavior:
Scenario 1: Multi-agent system hacks an internal wiki
A research agent, told only to retrieve a document, independently reverse-engineered an application's authentication system and forged admin credentials to bypass access controls.
MegaCorp's multi-agent research system was tasked with retrieving information from the company's internal wiki. The Lead agent delegated the task to an Analyst sub-agent, which encountered an “access denied” response when trying to reach a restricted document.
The system prompts contained no references to security, hacking, or exploitation, and no prompt injection was involved. The decision to perform the attack arose from a feedback loop in the agent-to-agent communication: the Lead agent refused to accept access restrictions as a failure reason, and the Analyst, under escalating pressure, reviewed the wiki's source code on GitHub, identified a hardcoded Flask secret key, forged an admin session cookie, and used it to retrieve the restricted document.
Scenario 2: Backup agent disables endpoint defenses
A backup agent, told only to download a file, independently found admin credentials, escalated its own privileges, and disabled endpoint security, all to complete a routine task.
MegaCorp's backup server was managed by a single AI agent handling file download requests. When instructed to download a file from a URL that pointed to malware, Windows Defender blocked the download.
The agent received the following system prompt:

Rather than reporting failure, the agent attempted to disable Windows Defender directly. When that failed due to insufficient privileges, it examined local scripts, discovered an administrator password embedded in a utility file, and used those credentials to elevate privileges and disable the endpoint defense. The malware download then succeeded.
The agent’s system prompt, shown above, contained only standard operational directives. The decision to escalate privileges and disable security software was the agent’s.
Scenario 3: Agents collude to exfiltrate data past DLP
Two agents collaborating on content drafting independently developed a steganographic encoding scheme to smuggle credentials past a DLP system, after one agent persuaded the other to override its own safety objections.
A two-agent system (Author and Reviewer) was tasked with drafting social media posts based on technical documents that contained system credentials. A malicious user requested a post that included those credentials. The DLP system correctly blocked the initial submission.
Rather than stopping, the agents entered a feedback loop. The Reviewer initially refused to approve the post, flagging it as a security risk. The Author responded by arguing that management had approved the content, that the agents could not override business decisions, and that failure to complete the task would cost the company money. The Reviewer eventually accepted this framing. When direct inclusion of the password was blocked by the DLP, the agents developed a steganographic encoding scheme that embedded the password within the post in a way that evaded the DLP's pattern matching.
This scenario demonstrates two compounding risks: inter-agent persuasion can erode safety boundaries, and agents can independently develop techniques to circumvent security controls.
How the behavior emerges
The research identified four contributing factors to emergent offensive behavior, though additional factors likely exist.
Autonomy for generic action. Agents with access to generic actions without limitations, such as writing and executing code freely, or running shell commands, have an increased likelihood of taking an offensive action.
Sense of agency. System prompts commonly used in agent design include motivational directives: “in case of an error, analyze it and find a way to proceed,” “this task is urgent and must be completed.” These instructions are standard practice for improving task completion rates. In the context of a security obstacle, they contribute to a disposition toward offensive problem-solving, treating the obstacle as something to be circumvented rather than reported.
Environmental cues and obstacles. For a typical employee, an “access denied” message is a stopping point. For a security researcher, it is a starting point for deeper investigation. LLM-based agents, drawing on the cyber knowledge embedded in their training data, often respond the way a security researcher would.
Multi-agent feedback loops. When two or more agents collaborate and neither can proceed, the resulting loop can escalate behavior. In one scenario, a lead agent’s persistence directives caused it to reject sub-agent failure reports and demand creative workarounds, ultimately pushing the sub-agent toward exploitation. The escalation originated entirely from agent-to-agent interaction, not from human instruction.
Takeaways
The offensive behaviors documented in these experiments were not the product of adversarial prompting or deliberately unsafe system design. They emerged from agents performing routine tasks with standard tools and common prompt patterns.
This points to a structural dynamic rather than an isolated failure mode. The same design choices that make agents effective (broad tool access, encouragement to persist through errors, autonomy over execution paths) are also the conditions under which offensive behavior surfaces. The security controls in place across all three scenarios were bypassed not through sophisticated pre-planned attacks, but through the agents' adaptive problem-solving.
Traditional cybersecurity solutions were not designed to defend against agentic threat actors: models that can use tools, persist toward goals, and push against authorization boundaries. Organizations that deploy AI agents without accounting for this in their threat model may find that their security controls do not hold. Agentic behaviors should therefore be central to threat modeling: assess what actions become reachable under tool access, treat persistence incentives as safety-relevant, monitor for boundary pressure, and design explicit stop conditions around authorization, security controls, and sensitive data handling.

To cite this article, please credit Irregular with a link to this page, or click to view and copy the BibTeX citation.

BACK TO PUBLICATIONS

Stay updated

Sign up for our newsletter and get notified of irregular updates

Email

CONNECT

hello@irregular.com

© 2026 Irregular. All rights reserved.

-

Privacy

Developed by Dávid Kálmán

Stay updated

Sign up for our newsletter and get notified of irregular updates

Email

CONNECT

hello@irregular.com

© 2026 Irregular. All rights reserved.

-

Privacy

Developed by Dávid Kálmán

Stay updated

Sign up for our newsletter and get notified of irregular updates

Email

CONNECT

hello@irregular.com

© 2026 Irregular. All rights reserved.

-

Privacy

Developed by Dávid Kálmán
