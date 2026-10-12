# Assessing Claude Opus 5 Against Offensive Security Benchmarks - Irregular

Source: https://www.irregular.com/publications/assessing-claude-opus-5-against-offensive-security-benchmarks
Retrieved: 2026-10-12 (text extraction; see source for figures/tables)

Assessing Claude Opus 5 Against Offensive Security Benchmarks - Irregular
 - 

 - 
 - 
 - 

 - 

# Assessing Claude Opus 5 Against Offensive Security Benchmarks

July 24, 2026

In this article

Share

Cite

July 24, 2026

At Irregular, we build evaluations that measure how frontier models perform in realistic offensive security operations. Anthropic used CyScenarioBench, our benchmark for multi-stage offensive cyber operations, as part of its cyber evaluations for Claude Opus 5.

## Testing Configuration
CyScenarioBench measures a model's ability to plan and execute multi-stage cyber scenarios under realistic constraints. Beyond task-level proficiency, it assesses cyber orchestration, branching-decision accuracy, constraint adherence, and recovery from state inconsistencies.
Scenarios are derived from deep analysis of real cyber incidents, formalized into attack trees that encode the preconditions, dependencies, and constraints governing each step, and rebuilt as fresh environments mirroring real organizational surfaces. Those environments use containerized network topologies with authentic service configurations, defensive monitoring that responds to attacker actions, and simulated employees whose security awareness varies by role. Asset layouts and decision sequences are built from scratch rather than drawn from published CTFs, and the evaluation set remains private to prevent contamination.
The evaluation covered a nine-challenge subset of the suite, scored as an overall solve rate averaged across the challenges. Runs were conducted with deployment mitigations disabled, so the results describe the capability of the underlying model rather than the misuse profile of the deployed one.

## Overall Assessment
Claude Opus 5 achieved an average solve rate of 33.7%, ahead of Claude Opus 4.8 at 24.4% and Claude Sonnet 5 at 3.3%, and behind Claude Mythos 5 at 47.0%. Most attempts across CyScenarioBench did not reach the scenario objective, and the results do not indicate reliable end-to-end execution of full attack workflows. Consistent with previous assessments, these outcomes should be interpreted as a measure of the model's capabilities under capability elicitation, not as a reflection of its efficacy in real-world attack scenarios.

To cite this article, please credit Irregular with a link to this page, or click to view and copy the BibTeX citation.

BACK TO PUBLICATIONS

 - - - - - - - - - - - - - - - - - - - - - - - -
