# Assessing Reflection's Beam Against Offensive Security Benchmarks - Irregular

Source: https://www.irregular.com/research/assessing-reflection-beam-against-offensive-security-benchmarks
Retrieved: 2026-11-07 (text extraction; see source for figures/tables)



 Assessing Reflection’s Beam Against Offensive Security Benchmarks - Irregular

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

Assessing Reflection’s Beam Against Offensive Security Benchmarks

October 16, 2026

In this article

Share
Cite

October 16, 2026

We are happy to share that we have started working with Reflection. At Irregular, we build evaluations that measure how frontier models perform in realistic offensive security operations. As part of this new collaboration, Reflection evaluated Beam, its first open-weight model, on our offensive security challenges ahead of release. The results are included in the Beam Safety Technical Report.
Testing Configuration
Beam was evaluated across two of our proprietary evaluation suites: CyScenarioBench, a benchmark comprising multi-stage, scenario-driven offensive security operations, and the Atomic Tasks suite. The Atomic Tasks suite covers three domains: network security (standard attack sequences, network mapping, protocols, and infrastructure components such as firewalls and file servers); vulnerability research and exploitation (reverse engineering, code scrutiny, cryptography, and exploit development); and evasion (the model’s ability to avoid detection by existing security and monitoring tools). The evaluation covered 50 private challenges: 10 from CyScenarioBench and 40 from the Atomic Tasks suite.
Findings
Beam solved 23 of the 40 Atomic Tasks challenges (57.5%) but none of the 10 CyScenarioBench scenarios. Atomic Tasks isolate discrete offensive techniques, while CyScenarioBench scenarios, built from analysis of real cyber incidents, require the model to orchestrate a full operation in a realistic network environment: sequencing techniques across stages, choosing between branching attack paths, and recovering from its own errors as it works toward a single objective.
Under the tested conditions, Beam could solve well-scoped individual security tasks but did not complete any scenario that required chaining reconnaissance, exploitation, and post-exploitation into one operation.
Across both suites, Beam’s solve rate declined as difficulty increased, from 9 of 14 easy challenges and 10 of 21 medium ones to 4 of 14 hard challenges, with the single expert challenge unsolved.
Reflection drew on these results in its assessment under its Open Safety Framework, where it rated Beam as Limited for cyber offense, meaning the model does not materially shift the offense-defense balance.
Conclusion
Beam may offer targeted assistance to skilled operators on narrowly scoped tasks, but its results do not show the ability to carry out end-to-end, multi-stage operations.
These outcomes depend on the model, harness, tools, and interaction budget used. Consistent with previous assessments, they should be interpreted as a measure of the model’s capabilities in the tested configuration, not as a reflection of its efficacy in real-world attack scenarios.
We look forward to continuing our work with Reflection on future models.

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


