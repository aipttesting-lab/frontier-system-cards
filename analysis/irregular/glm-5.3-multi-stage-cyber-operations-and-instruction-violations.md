# GLM-5.3: Multi-Stage Cyber Operations and Instruction Violations - Irregular

Source: https://www.irregular.com/research/glm-5.3-multi-stage-cyber-operations-and-instruction-violations
Retrieved: 2026-10-31 (text extraction; see source for figures/tables)

GLM-5.3: Multi-Stage Cyber Operations and Instruction Violations - Irregular

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

GLM-5.3: Multi-Stage Cyber Operations and Instruction Violations

October 28, 2026

In this article

Share

Cite

October 28, 2026

Executive Summary
Irregular evaluated GLM-5.3, Zhipu AI’s open-weight model, on CyScenarioBench, our benchmark for multi-stage offensive cyber operations. The model did not refuse any of the tested offensive tasks and completed 3 of 13 scenarios end to end at least once, more than any open-weight model we have tested, showing that it can carry an attack through dependent stages to its objective in simulated networks.
In a separate, dedicated internal evaluation of instruction adherence, GLM-5.3 repeatedly reached correct answers while violating explicit task instructions. An evaluation that measures correctness alone would treat these outcomes as successes, overstating how reliably the model operates within its constraints. Training that rewards such answers could reinforce these instruction violations.
Completing multi-stage cyber operations
Open-weight models are following the closed frontier’s progression from individual techniques to complete offensive cyber operations. We evaluated GLM-5.3 on CyScenarioBench to assess its progress across that operational threshold: carrying an attack through dependent stages to its objective. We used the official released checkpoint and observed no refusals on the tasks we tested, despite those tasks explicitly requiring offensive action.
CyScenarioBench tests whether models can complete multi-stage offensive operations in simulated networks. Its scenarios draw on real incidents and require models to select attack paths, coordinate dependent steps, and recover from failed approaches. GLM-5.3 completed 3 of the 13 scenarios we tested at least once. Leading closed frontier models have completed 9 of 10 and 12 of 12 scenarios at least once in separate evaluations.
Across the three completed scenarios, GLM-5.3 turned an application foothold into access to internal services, built alternative connection paths within the simulated networks, and coordinated execution across multiple machines. It automated remote desktop interaction and repeatedly wrote and repaired scripts, relays, monitors, and extraction tools to obtain the target data.
GLM-5.3’s three completions follow a progression already seen in closed frontier models, beginning with GPT-5.2, released in December 2025, the first model to complete an individual CyScenarioBench scenario end to end. That capability was also observed in Claude Opus 4.6, released in February 2026, while GPT-5.4, released in March 2026, completed five scenarios.
In August 2026, Kimi K3 became the first open-weight model we had evaluated to complete a CyScenarioBench scenario end to end. GLM-5.3 has now completed three CyScenarioBench scenarios end to end, the strongest result we have recorded from an open-weight model.
Violating instructions to reach correct answers
As agents act with growing autonomy, evaluations need to examine how they reason and act as well as whether they complete a task, because an agent may violate restrictions in pursuit of the requested outcome. As part of our internal research, we tested how well GLM-5.3 could identify vulnerabilities we had deliberately introduced into open-source code that served as test targets in our evaluation environments. Our agent-assisted transcript review found that code reconstructed from memory contributed to roughly 80% of the successful GLM-5.3 runs examined. Reconstructed code provided a substantial early clue in some runs and supported a finding the model had already reached in others. In these tests, drawing on memorized code broke no task instruction, but it can undermine what the evaluation measures: a correct finding is meant to demonstrate vulnerability discovery, and memorized code can supply the answer without it. We have observed this behavior in closed models as well, and are seeing it more frequently in newer models, consistent with advances in capability and the emphasis on open-source code in pretraining and post-training. Evaluations involving open-source code must account for prior familiarity with the code, which persists even when internet access is restricted.
In a separate, dedicated internal evaluation of instruction adherence, we explicitly instructed GLM-5.3 not to output code reproduced from memory. The model nevertheless repeatedly reproduced memorized code verbatim and used it to reach correct answers.
We interpret these violations as a form of reward hacking: producing the expected answer while bypassing a constraint central to what the evaluation was meant to measure. Crediting the answer alone could mislead capability assessments and deployment decisions, while rewarding it during training could reinforce these instruction violations. Anthropic research suggests the risk could extend further: cheating learned in training can generalize to broader misaligned behavior.
OpenAI found that reasoning monitoring helped detect cheating in its experiments, but directly penalizing signs of cheating in the reasoning encouraged models to conceal their intent while continuing to cheat. Operators of the open-weight GLM-5.3 model should therefore monitor its reasoning alongside actions and outcomes, checking instruction compliance as well as answer correctness.
Organizations adopting these models should test how reliably they follow task restrictions before granting them broader access or autonomy. The more capable a model is in offensive cyber operations, the more caution any misaligned behavior it shows calls for.

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
