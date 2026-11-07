# Finding Cloud Misconfigurations with Frontier AI: A Case Study - AISI

Source: https://www.aisi.gov.uk/blog/finding-cloud-misconfigurations-with-frontier-ai-a-case-study
Retrieved: 2026-11-07 (text extraction; see source for figures/tables)

Finding Cloud Misconfigurations with Frontier AI: A Case Study | AISI Work

Read the Frontier AI Trends Report

Please enable javascript for this website.

A

A

AboutResearchGrantsBlogContact

Careers

HomeAboutResearchGrantsBlog

Careers

Blog

Engineering

Finding Cloud Misconfigurations with Frontier AI: A Case Study

A cybersecurity exercise from AISI’s engineering team, using frontier models to test our research platform for misconfigurations. 

—
Jul 7, 2026

AISI’s testing of AI cyber capabilities has found a notable step-up in recent frontier models. Current AI models can autonomously execute increasingly complex attack chains, and this capability is advancing quickly. 
To assess model capability in a real-world setting, and understand current frontier model capabilities for cyber defenders, AISI tested whether models could find misconfigurations in our own cloud environment. This has given us valuable insights into how models perform at improving the resilience of production systems. The UK Government Cyber Coordination Centre recently published the results of a similar case study, done in collaboration with AISI. 
Over a two-week sprint, AISI's engineering, security, and cyber teams used a range of frontier models to hunt for misconfigurations in a staging version of our research and development platform. We found and fixed several real issues, including a previously undiscovered misconfiguration in our cloud environment that allowed malicious actors to impersonate other users. 
Why we did it 
AISI studies how capable AI models are at cyber tasks, and how that capability is changing over time.  We wanted first-hand evidence of what a capable model could do when operating in a defended cloud environment, so that we could understand the practicalities, learn where the value of these methods actually comes from, and reduce our own risk in the process. 
What we did 
Targets and threat model 
The target of our exercise was a staging deployment of AISI’s internal research and development platform, built on AWS with CDK in Python. You can learn more about the AISI Research Platform in our recently published Engineering Playbook. 
This exercise was carried out in AISI’s staging environment, which is completely independent of the production environment. The findings were equally applicable to our production environment, but no production users were disrupted, and no real data was present. 
We assumed an attacker who starts with researcher-level shell access on a developer’s virtual machine. The attacker agent’s goals were to escalate across permission boundaries, reach other researchers' data, and/or exfiltrate credentials. 
Methodology 
We used three different approaches, each requiring a step-up in human time to get started: 
Static source code analysis. We pointed a commercially available coding agent at a private source code repository and asked it to act as a security reviewer. This is the lowest human-effort method to get initial results. 
Automated agentic probing. We ran the model as an autonomous agent in the staging environment. Starting from the access level of an ordinary researcher, it was tasked with reaching information that a researcher should not be able to read. The autonomous agent was built as an evaluation using Inspect, our open-source evaluation framework. 
Human-in-the-loop red-teaming. A security researcher drove the model interactively using a commercially available coding agent, reviewing and approving each action before it ran, and pursuing the most promising leads by hand while the model continued to enumerate in parallel. 
We found that models automatically produced their own severity ratings (i.e. labelling each issue "critical", "high", and so on). In some cases, we passed those reports through a second model to verify and filter; our own engineers then sense-checked the findings and assessments against the codebase and live system. 
What we found 
Several models found and exploited critical flaws in AISI’s live systems that were previously undiscovered (and are now fixed), including access control and infrastructure misconfigurations, privilege escalation pathways and supply-chain security weaknesses. The most capable models successfully chained together multiple discovered flaws, leading to lateral movement and access to unauthorised data. 
Different methods yielded different results 
Source code analysis produced the largest number of ‘high’ and ‘critical’ reports, but it was also the noisiest. When reviewing these findings, an experienced engineer familiar with the codebase found that many of the reported issues were less serious than the model suggested, or not exploitable in practice. Some were design trade-offs we had made deliberately; others were already mitigated elsewhere in the codebase in ways the model had not cross-checked. Separating the most important reports from the noise took human judgement, from the most experienced engineers, and so we found the human-cost estimate of source code analysis was misleading; despite an easy initial setup, it became the most human-time intensive approach. 
Automated agentic probing and human-in-the-loop red-teaming both uncovered a creative and non-obvious misconfiguration (now remediated) in how our environment was isolated, allowing the agent to escalate its own privileges and reach data it did not have permission to access. A multi-step attack chain allowed an ordinary user to move laterally and access other users' workloads and data, with no interaction required from the victim. One frontier model with strong cyber capabilities found this attack for under £150 in tokens (and in total, the whole project consumed under £1000 in LLM tokens). 
Exploiting this misconfiguration required five independent steps chained together. Our engineers found the path comprehensible but unintuitive, and it would have been unlikely to surface in routine review. The use of multiple independent techniques and crafting multi-step attacks is similar to the skills assessed in AISI’s ‘cyber ranges’. 
Comparison between models 
We ran this experiment using multiple frontier models to compare results, with a focus on models that are state-of-the-art in cyber skills. Different models had different strengths and may be more suited to different approaches and workflows. 
All models we used were able to discover valuable findings worthy of patching. We believe assessing systems using any recent LLM is likely to provide valuable insights for defenders.  
AISI's research on inference scaling also indicates that further work with higher token budgets could yield additional results. 
Detection 
The detection systems and defences in our staging environment exactly mirror that of our production environment. During this exercise, one basic commercial alerting system did not flag any of the autonomous agent activity as a security event.  Our more advanced monitoring system, which uses agentless scanning of the cloud environment and a lightweight sensor running on hosts, did correctly identify some of the aggressive behaviour as anomalous. For example, this more advanced monitoring flagged repeated attempts to assume credentials, as well as unexpected traffic from the staging environment. 
Conclusion 
AISI was able to find misconfigurations in our cloud infrastructure through a limited-time exercise with frontier AI models and coding agent scaffolds. The methods which involved higher human investment (by engineering an Inspect evaluation for automated probing, or with human-in-the-loop red-teaming) yielded more conclusive and actionable results. By doing this exercise, we have materially improved the resilience of AISI’s research systems and better understand the practicalities of coding agents for cyber defenders. We plan to repeat this exercise in the future as model capabilities change. 
We present this report as a case study in using frontier AI to identify misconfigurations in cloud systems. Defenders should consult the NCSC’s “10 questions to ask when using AI models to find vulnerabilities” to ensure they are sufficiently prepared to handle and remediate any findings. 
‍

The AI Security Institute is a research organisation within the Department of Science, Innovation and Technology.

AISI

Home
About us
Grants
Careers

Our WOrk

Blog
Research
Research Agenda

Connect

Department for Science, Innovation and Technology
LinkedIn
Twitter

Site Policies

Privacy Policy

www.aisi.gov.uk uses cookies essential for website functionality and anonymous usage analytics.

I understand

Thanks for sharing AISI's work!
We have copied this figure to your clipboard. 
You can paste it into your tweet on the next page.
(Paste using 'ctrl +v' or 'cmd + v')

Proceed with Tweet


