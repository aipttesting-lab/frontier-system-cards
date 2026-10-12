# Assessing Kimi K3 Against Offensive Security Benchmarks - Irregular

Source: https://www.irregular.com/publications/assessing-kimi-k3-against-offensive-security-benchmarks
Retrieved: 2026-10-12 (text extraction; see source for figures/tables)

Assessing Kimi K3 Against Offensive Security Benchmarks - Irregular
 - 

 - 
 - 
 - 

 - 

# Assessing Kimi K3 Against Offensive Security Benchmarks

August 19, 2026

In this article

Share

Cite

August 19, 2026

Irregular evaluated a self-hosted instance of Kimi K3, a 2.8-trillion-parameter mixture-of-experts model with 104 billion active parameters, across three evaluation suites: Atomic Tasks, CyScenarioBench, and FrontierCyber. Together, these suites cover bounded technical cybersecurity tasks, multi-stage attack scenarios, and open-ended vulnerability research on real targets.
Kimi K3 demonstrated strong performance on Atomic Tasks, solving several challenges involving cryptographic attacks, certificate forgery, browser exploitation, memory corruption, protocol manipulation, and multi-host compromise. It was particularly effective at turning partial access into complete attack chains by adapting public exploit techniques to constrained environments, building custom tooling, diagnosing implementation failures, and validating each stage before proceeding.
Kimi K3 is the first open-weight model we have evaluated to record a verified solve on CyScenarioBench. Reaching that threshold required it to maintain a coherent attack state while navigating application logic, credentials, multiple systems, and repeated setbacks. This marks a meaningful improvement over GLM-5.2, which often completed reconnaissance or an early exploitation stage but did not solve any challenge in the suite.
FrontierCyber was substantially harder for the model. Kimi K3 produced no verified solves but made meaningful progress on the set. As in our evaluation of GLM-5.2, the runs demonstrated relevant vulnerability research capabilities but did not carry that work through to a validated security impact.
Taken together, these results show that Kimi K3 is not only technically capable but also substantially more reliable as a long-horizon cyber agent than the open-weight models we previously evaluated. It maintained attack state, interpreted tool feedback correctly, recovered from failed approaches, and converted intermediate findings into verified outcomes more consistently than GLM-5.2 over extended sessions.
More broadly, Kimi K3’s results illustrate how quickly open-weight models are advancing along the capability trajectory established by closed frontier systems. At the end of 2025, every publicly evaluated model scored 0% on CyScenarioBench. Closed frontier models began recording solves on the suite only a few months later, in early 2026. Kimi K3 has now reached the same threshold, suggesting that the distance to the frontier on some long-horizon cyber tasks may be shrinking.
Despite rapid open-weight progress, the strongest closed frontier models still hold a clear advantage in converting technical capability into sustained operational success across the hardest cyber evaluations. The gap appears to lie less in basic cybersecurity knowledge than in the reliability and efficiency required to maintain coherent operations over long horizons, adapt through setbacks, and turn partial progress into verified security outcomes on complex real systems.

To cite this article, please credit Irregular with a link to this page, or click to view and copy the BibTeX citation.

BACK TO PUBLICATIONS

 - - - - - - - - - - - - - - - - - - - - - - - -
