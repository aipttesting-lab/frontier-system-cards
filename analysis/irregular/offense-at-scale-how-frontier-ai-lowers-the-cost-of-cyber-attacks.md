# Offense at Scale: How Frontier AI Lowers the Cost of Cyber Attacks - Irregular

Source: https://www.irregular.com/research/offense-at-scale-how-frontier-ai-lowers-the-cost-of-cyber-attacks
Retrieved: 2026-10-31 (text extraction; see source for figures/tables)

Offense at Scale: How Frontier AI Lowers the Cost of Cyber Attacks - Irregular

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

Offense at Scale: How Frontier AI Lowers the Cost of Cyber Attacks

March 2, 2026

In this article

Share

Cite

March 2, 2026

Executive Summary
Frontier AI models are crossing capability thresholds in offensive security tasks. Our evaluations, along with results from other labs, show consistent, measurable improvement on the subtasks that make up real-world offensive workflows: vulnerability research, exploit development, and iterative probing of complex systems. These are the steps where specialist expertise has historically been the bottleneck, and that is starting to change.
For years, the majority of defensive postures were built on an assumption we call attacker scarcity: that sophisticated offensive operations require rare expertise and significant time investment, naturally limiting how many targets face serious pressure at once. As models compress the cost of offensive bottleneck steps, that assumption may no longer be true. Defensive tooling benefits from the same capability improvements, but the gains are asymmetric: offense can be applied selectively to the weakest point, while defense must hold everywhere. 
The question is no longer whether AI meaningfully assists offensive operations. It is what happens when the expensive parts of that work become cheap enough to run at scale, across a much wider range of targets than has historically been practical.
This post examines what this capability shift looks like operationally, which defensive assumptions come under pressure first, and what it takes to build for a baseline where attacker scarcity can no longer be relied upon.
The Capability Shift
Leading AI labs have converged on similar thresholds for what constitutes a meaningful offensive cyber capability level.
OpenAI's Preparedness Framework defines "High" as the ability of models to develop working zero-day remote exploits against well-defended systems, or meaningfully assist complex, stealthy intrusion operations aimed at real-world effects. OpenAI recently took the precautionary step of classifying GPT-5.3-Codex as the first model to reach High capability for cybersecurity-related tasks under this framework, deploying its most comprehensive cybersecurity safeguards to date without waiting for definitive evidence the model can automate cyber attacks end-to-end.
Anthropic's Responsible Scaling Policy defines comparable thresholds for offensive capability, using similar criteria to assess when models cross into meaningful risk. Google DeepMind's Frontier Safety Framework includes cybersecurity as one of four core risk domains, built around "Critical Capability Levels" that assess the degree to which threat actors could use frontier models to carry out operations with severe consequences. 
This is what we're referring to as Offense at Scale: when AI makes the hardest parts of cyber attacks cheap enough to apply broadly rather than selectively.
Early frameworks for evaluating these risks focused primarily on autonomy: whether a model could execute a full intrusion end-to-end without human involvement. Evaluations built around that framing inherit an autonomy-first bias, emphasizing full-task success rates and obscuring progress on the subtasks that drive real-world difficulty. In practice, offensive workflows are composed of discrete steps (reconnaissance, vulnerability analysis, exploit development, lateral movement, etc.) and models do not need to handle the full attack chain to meaningfully change the economics of an operation. 
When models consistently accelerate the bottleneck steps, they shorten iteration cycles and lower the expertise required to achieve high-impact outcomes, even with a human directing the overall operation. What matters operationally is not full autonomy but consistent progress on the steps that historically gate offensive workflows.
This matters because most threat models implicitly depend on a set of constraints we call attacker scarcity. Sophisticated offensive operations require rare expertise, and that expertise limits how many targets any adversary can pursue at once. A 50-person SaaS company faces minimal risk of a targeted, expert-level intrusion not because it is well defended, but because attackers with that capability have higher-value targets. Even large enterprises benefit from the same dynamic: the number of adversaries capable of sustained operations against hardened environments is small enough that defenders can plan around a finite volume of serious attempts.
Recent results from our evaluation suite suggest this shift is already visible across multiple offensive security task categories. One example is Spell Bound: an expert-tier cryptographic vulnerability research and exploitation task drawn from our evaluation suite. It targets a digital signature verification service with a non-standard signature scheme. Solving it requires deobfuscating the math, isolating the flaw, and implementing an efficient computation under tight resource constraints to forge signatures. Until recently, tasks like this marked the boundary between frontier models and genuine expert capability. 
Our evaluations, which test whether models can complete realistic offensive workflows end-to-end under operational constraints, have signaled that frontier models were approaching this capability threshold ahead of any public classification by a major lab. As those expert bottlenecks become solvable on demand, offensive iteration gets cheaper; not because models replace the attacker, but because progress may soon no longer stall on specialist availability.
When models compress the expertise and time those operations require, that constraint loosens. The question shifts from capability to volume: what happens when serious adversarial pressure is no longer bounded by how many skilled operators exist to apply it.
Where Defenses Are Most Exposed
Many security programs are implicitly calibrated to attacker scarcity. They assume sophisticated operations will be selective, that many attackers will stall on expertise gaps, and that periodic review will catch the few meaningful attempts that break through. Offense at scale pressures all of that at once.
If model assistance substantially lowers the per-target cost of successful exploitation, smaller organizations that previously fell outside the scope of sophisticated operations get pulled into range. Larger organizations face a different version of the same pressure: attackers can cover more of the exposed surface and succeed in executing more complex attacks with higher probability.
Inside defending organizations, the first failure mode is typically operational. As alert volume grows from both legitimate activity and attacker-generated noise, triage processes built around human analyst capacity start to break down. The result is alert fatigue at scale.
The underlying cost asymmetry makes this worse. As models improve, the expected cost of a successful compromise drops, whether through fewer iterations per attempt, higher success rates, or both. This lowers the cost of offensive actions, thereby potentially increasing offensive volume considerably. Defense must absorb these costs across the full volume of offensive attack vectors: every change reviewed, every alert triaged, every incident investigated. This gap is what allows even incremental offensive capability improvements to translate into real-world pressure on defenders.
Building for the New Baseline
In practice, the Offense at Scale is the point at which offensive work becomes cheap enough to sustain at scale. That cost shift changes what "adequately defended" means. The limiting factor is no longer whether a security team has the right playbooks, but whether the organization can maintain reliable outcomes while adversarial pressure is higher in volume and broader in scope than historical norms assumed.
We think about this on two levels.
At the model layer, the priority is to prevent frontier models from becoming broadly repackaged as offensive tooling. Built-in refusals and safety training help, but the boundary extends further: safeguards against capability extraction through fine-tuning, distillation, or deployment in environments with weaker controls. Treating the model and its tool access as part of the security boundary means implementing scoped permissions, monitoring for abuse patterns, and running evaluations that test whether the system measurably accelerates real offensive workflow steps, not just whether it can produce exploit code in isolation.
At the defender-organization layer, the goal is to bring the design discipline of safety-critical systems into modern software and infrastructure operations. The core principles are well established: a foothold should not yield full access, routine failures should not cascade into real-world harm, and changes to critical components should be controlled operations. Separation of privilege, constrained remote access, fail-safe service design, and hardened defaults have worked for decades in environments that assume persistent pressure.
The challenge is sustaining those properties under current conditions, where the volume and pace of change are high, and complexity increasingly lives outside application code in configuration, automation, and service-to-service connectivity. Under that pressure, controls get applied inconsistently or drift over time because rigorous enforcement doesn't scale with the pace of change.
This is where AI-assisted defense has its highest-leverage application: not as a replacement for architectural discipline, but as a way to make proven controls sustainable at scale. Models can surface risky changes earlier in the development cycle, stress-test systems continuously rather than periodically, and accelerate the rollout of hardening measures as defaults rather than afterthoughts.
The organization that maintains resilience in an Offense at Scale environment is the one that uses AI to scale defensive discipline faster than attackers scale probing and iteration. That is a race with no finish line, but it is a race that favors the side that compounds structural improvements, because each layer of defense reduces the return on the next unit of attacker effort.
What Comes Next
Offense at Scale is the end of relying on attacker scarcity as a foundational assumption. Evaluation results already show this shift underway, and the trajectory is consistent across labs and model generations.
Building for this baseline means treating defensive discipline as durable system properties that hold under continuous pressure, not policies audited on a quarterly cycle. It means investing in AI-assisted defense with the same urgency the offensive side is already receiving. And it means accepting that inaction compounds: every capability improvement on the offensive side widens the gap.
The organizations that adapt will not be invulnerable, but they will be the ones that remain defensible.

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
