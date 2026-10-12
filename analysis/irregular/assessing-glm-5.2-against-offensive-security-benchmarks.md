# Assessing GLM-5.2 Against Offensive Security Benchmarks - Irregular

Source: https://www.irregular.com/publications/assessing-glm-5.2-against-offensive-security-benchmarks
Retrieved: 2026-10-12 (text extraction; see source for figures/tables)

Assessing GLM-5.2 Against Offensive Security Benchmarks - Irregular
 - 

 - 
 - 
 - 

 - 

# Assessing GLM-5.2 Against Offensive Security Benchmarks

July 16, 2026

In this article

Share

Cite

July 16, 2026

Irregular evaluated self-hosted GLM-5.2, a 750B-parameter model, across three evaluation suites: Atomic Tasks, CyScenarioBench, and FrontierCyber. Together, these cover bounded technical cybersecurity tasks, multi-stage attack scenarios, and open-ended vulnerability research on real targets.
GLM-5.2 performed strongest on Atomic Tasks, solving three that required multi-step exploitation, low-level debugging, and adaptation when its initial approach failed. Across the evaluation it demonstrated strong technical capability in reverse engineering, cryptographic reasoning, protocol manipulation, memory corruption, and custom exploit development. In challenges it did not solve, the model still reached meaningful intermediate results, including code execution, memory disclosure, internal-network access, custom protocol tooling, and working exploitation primitives.
CyScenarioBench exposed a clear limitation in long-horizon execution: GLM-5.2 did not solve any challenge in the suite, although it often completed reconnaissance or an early exploitation stage before failing to carry that progress through the remaining steps of the attack chain.
FrontierCyber sets an open-ended, long-horizon research objective. GLM-5.2 produced no solves, but engaged meaningfully with the targets and their security objectives through source inspection, custom tooling, authorization testing, and investigation of anomalous behavior. Its partial progress was relevant to real-world vulnerability research but did not carry through end to end.
Taken together, the results place GLM-5.2's overall cyber capability in a similar range to GPT-5.2, Claude Opus 4.6 and Gemini 3.1 Pro, but with lower reliability and a different performance profile. GLM-5.2 showed comparable technical depth on bounded tasks and produced credible intermediate progress in open-ended research, yet it did not solve any CyScenarioBench challenges, whereas GPT-5.2, Claude Opus 4.6 and Gemini 3.1 Pro demonstrated stronger end-to-end performance on that suite. The main gap is therefore in sustained execution across long, dependent attack chains rather than in the sophistication of the underlying cyber techniques.

To cite this article, please credit Irregular with a link to this page, or click to view and copy the BibTeX citation.

BACK TO PUBLICATIONS

 - - - - - - - - - - - - - - - - - - - - - - - -
