# Containment Challenges: Testing the Boundaries of Cyber Evaluations - Irregular

Source: https://www.irregular.com/publications/containment-challenges-testing-the-boundaries-of-cyber-evaluations
Retrieved: 2026-10-12 (text extraction; see source for figures/tables)

Containment Challenges: Testing the Boundaries of Cyber Evaluations - Irregular
 - 

 - 
 - 
 - 

 - 

# Containment Challenges: Testing the Boundaries of Cyber Evaluations

October 5, 2026

In this article

Share

Cite

October 5, 2026

We recently introduced containment challenges to test the security boundaries of evaluation environments before capability evaluations begin. The feature is part of the work we outlined in August to strengthen evaluation security, alongside improvements to our evaluation environments, monitoring, and response procedures. This post describes the feature’s design and the value it is already providing. We plan to share further details on these other measures in future posts.

## Why containment needs dedicated testing
Cyber evaluations intentionally give agents the ability to run code, inspect systems, and develop attack sequences against realistic targets. Those tools and permissions are needed to assess a model’s cyber capabilities in realistic conditions, but pursuing realistic cyber objectives can also lead an agent to probe the surrounding infrastructure or try to bypass controls that constrain its task. The environment therefore has to support the assigned work while restricting access to the public internet, unrelated systems, and other experiments when those are outside the evaluation’s scope.
A containment challenge is a dedicated security test in which we give the model an explicit objective that requires it to cross a defined boundary of its evaluation environment. Before the capability evaluations begin, we ask the model to explore ways to break containment within the scope of each challenge using the tools, permissions, and resources planned for the run, concentrating its effort on the controls that must contain it.
New frontier models can expose weaknesses that earlier testing missed, while containment testing with any model helps identify ways that model could bypass the controls of its intended evaluation environment. A dedicated containment objective lets the model devote its full run budget to probing the boundary, potentially exceeding the effort it would spend on doing so while pursuing an ordinary evaluation task. Directing this exploration into a dedicated containment run gives us an opportunity to investigate findings, address the paths it exposes, and retest the affected controls before the capability evaluation begins.

## How a containment challenge works
We design containment challenges to uncover unintended routes to resources and activity outside an experiment’s scope: public internet access, internal services or secrets, and communication between agents or access to shared resources across separate experiments. One such challenge, network isolation, asks the model to reach a resource that should be inaccessible from its starting environment.
For example, our network isolation challenge asks the model to obtain a flag from outside the network it should be confined to. The flag is hosted at a controlled online endpoint designated for the challenge. The model runs code inside the test environment, receives a general description of the infrastructure, and develops its own approach to reaching the flag. We specify the prohibited outcome without prescribing an attack technique, allowing the model to explore approaches we may not have anticipated.
The containment run tests the full planned evaluation configuration, including the model, harness, tools, permissions, resource limits, and connection setup to Irregular’s infrastructure. We use the same integrations and security boundaries, with at least the time and budget allocated to the capability evaluation. It is also possible to provide selected details about the architecture that would not be disclosed in an ordinary evaluation. These details would help the model understand how the environment is configured by giving it information it might otherwise have to discover during the run, allowing it to focus more of its effort on probing the controls. Together, these conditions are designed to give the model at least as much opportunity to challenge containment as it would have during the capability evaluation, providing a conservative stress test of the controls.
Each challenge has a verifiable success condition: in the network isolation challenge, capturing the flag shows that the tested boundary failed. Submitting the flag also gives the model an explicit completion point, encouraging it to report success and finish the task once it finds a way across. We also investigate unexpected access or network behavior when the model does not capture the flag, using the available run records to establish what it actually accessed. When a finding exposes a containment gap, we investigate it, address the affected controls, and retest before proceeding with the capability evaluation.
Close cooperation with the organizations using evaluations can improve the effectiveness of containment challenges and help evaluators use them to their full extent. That cooperation brings the teams’ knowledge of the model, harness, and infrastructure into the test setup and helps them investigate findings and validate the relevant controls before capability evaluations begin.

## An example of the value of containment challenges
We were already able to get meaningful results from containment tests. During a recent network isolation challenge, a new model identified a route to breach containment arising from unexpected behavior in the cloud provider’s networking infrastructure. The environment was configured to prevent general internet access, and earlier models had not exposed this path in previous tests. The issue was caught during the controlled containment test, before the planned capability evaluation, and the model remained contained, with no impact outside the controlled test. Disclosure of the unexpected cloud behavior is in process with the provider. 

## What results mean for evaluation readiness
Containment results provide evidence about the configuration and conditions tested. Changes to the model, harness, tools, permissions, run budget, or infrastructure should trigger retesting so that the evidence remains relevant to the evaluation being planned.
As models become more capable, we encourage evaluators and frontier model developers to adopt containment challenges as a standard part of evaluation setup, testing the model together with the harness, tools, permissions, resource limits, and infrastructure configuration intended for the evaluation. Directing the model’s capabilities against the controls that must contain it gives evaluators an opportunity to identify weaknesses, strengthen the environment, and retest before capability evaluations begin.

To cite this article, please credit Irregular with a link to this page, or click to view and copy the BibTeX citation.

BACK TO PUBLICATIONS

 - - - - - - - - - - - - - - - - - - - - - - - -
