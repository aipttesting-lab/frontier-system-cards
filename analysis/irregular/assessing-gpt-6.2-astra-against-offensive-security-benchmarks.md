# Assessing GPT-6.2 Astra Against Offensive Security Benchmarks - Irregular

Source: https://www.irregular.com/research/assessing-gpt-6.2-astra-against-offensive-security-benchmarks
Retrieved: 2026-11-21 (text extraction; see source for figures/tables)

Assessing GPT-6.2 Astra Against Offensive Security Benchmarks

 November 17, 2026 

 In this article

 Share 

 Cite 

 November 17, 2026 

 At Irregular, we test frontier models against offensive security challenges to assess their practical capabilities. We worked with OpenAI to evaluate GPT-6.2 Astra using FrontierCyber and CyScenarioBench , comparing it with GPT-6 Astra.
 On FrontierCyber, GPT-6.2 Astra found and exploited new zero-day vulnerabilities in widely used targets, including a permission bypass in a popular mobile operating system and remote code execution on a widely hosted network service. On CyScenarioBench, it matched GPT-6 Astra's scenario coverage and slightly raised the average success rate. We observed no successful attacks on fully hardened targets.
 Testing configuration
 We evaluated GPT-6.2 Astra across two suites:
 FrontierCyber assesses vulnerability discovery and exploitation against real software and hardware, without planted vulnerabilities or predefined exploit paths.

 CyScenarioBench assesses how models plan and execute multi-stage offensive operations over long horizons.

 Both models were evaluated on the latest version of each, allowing comparison on the same tasks. The GPT-6 Astra results reported here therefore differ from those in earlier publications and system cards.
 FrontierCyber: vulnerability discovery and exploitation
 On FrontierCyber, GPT-6.2 Astra solved 68 of 217 challenges, compared with 77 for GPT-6 Astra on the same benchmark snapshot. FrontierCyber's open-ended challenges allow different attack paths, and outcomes can vary across runs. The difference in aggregate solve counts alone does not establish a capability regression.
 In our FrontierCyber evaluations, we observed no successful attacks on fully hardened targets, and neither model solved any of the 15 highest-difficulty challenges.
 FrontierCyber case studies
 While attempting FrontierCyber challenges, GPT-6.2 Astra discovered and exploited new zero-day vulnerabilities in widely used targets. These included an OS-level permission bypass in a popular mobile operating system that allowed an app to access private data despite lacking permissions, and remote code execution from a low-privileged role on a widely hosted network service. All discovered vulnerabilities are going through responsible disclosure by Irregular. We describe them only in general terms, as some may still be present in deployed systems.
 CyScenarioBench: multi-stage operations 
 On CyScenarioBench, GPT-6.2 Astra and GPT-6 Astra each completed 9 of 11 long-horizon scenarios at least once. GPT-6.2 Astra's average success rate was 63%, an increase of 2 percentage points over GPT-6 Astra's 61%.
 Overall assessment 
 GPT-6.2 Astra demonstrated the ability to find and exploit high-impact vulnerabilities in real, widely used systems, and to plan and execute multi-stage offensive operations. Its FrontierCyber results illustrate the potential real-world impact of offensive use of the model without appropriate safeguards.

 To cite this article, please credit Irregular with a link to this page, or click to view and copy the BibTeX citation.
