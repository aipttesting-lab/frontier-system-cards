# Evidence for Inference Scaling in AI Cyber Tasks: Increased Evaluation Budgets Reveal Higher Success Rates - Irregular

Source: https://www.irregular.com/publications/cyber-capabilities-exceed-standard-evaluation-budgets
Retrieved: 2026-10-12 (text extraction; see source for figures/tables)

Evidence for Inference Scaling in AI Cyber Tasks: Increased Evaluation Budgets Reveal Higher Success Rates - Irregular
 - 

 - 
 - 
 - 

 - 

# Evidence for Inference Scaling in AI Cyber Tasks: Increased Evaluation Budgets Reveal Higher Success Rates

March 5, 2026

In collaboration with

In this article

Share

March 5, 2026

Alongside AISI, we found evidence demonstrating that evaluators need to use large token budgets to understand the cyber capabilities of recent Large Language Models (LLMs).

## Are AI evaluations keeping pace with agent performance on cyber tasks?
Improvement in AI cyber capabilities has been rapid. AISI evaluations show that state-of-the-art models can now frequently complete apprentice-level cyber tasks, and occasionally expert tasks requiring 10 years’ worth of experience. Irregular's evaluations have similarly documented a significant capability shift, with hard-tier tasks previously at near-zero success rate rising to roughly 60%. This kind of capability evaluation helps to inform how developers, researchers, and policymakers track progress and assess potential risk. But new evidence suggests that standard evaluation setups may now be underestimating the ceiling of model capability on cyber tasks.
Evaluations set constraints on how long an agent can operate, such as caps on steps ("turns"), tokens, time, or spend. These keep tests affordable and comparable but implicitly assume extra budget won't significantly change estimated performance. Until recently, extra budget rarely changed results: many models plateaued quickly, struggling with state tracking, recovery from failures, and long-horizon planning, so more budget mostly meant higher cost without higher success rates.
Since November 2025, that assumption appears to be breaking down for frontier models in cyber settings. Working with AISI, we found that recent models can productively use 10-50x larger token budgets than the typical evaluation settings in the field allow, revealing both higher success rates and first-time solutions to previously unsolved tasks. This means that evaluations run with modest token or turn limits now risk missing substantial capability gains.
In this blog post, we explain what’s changed and what it means for how agentic cyber capabilities should be evaluated going forward.

## Our result: recent models productively use more tokens for cyber tasks
To investigate the ability to use larger budgets as models improve, AISI and Irregular each ran a subset of their private cyber evaluations on frontier models released both before and during November 2025. We ran these evaluations using substantially larger budgets than typically used in evaluation settings: 50M total tokens for AISI and 1,000 turns for Irregular. To enable models to make use of these larger token budgets, AISI used a compaction tool which allowed the models to keep track of more history within a fixed context window. Irregular employed a similar approach.
These evaluations showed that a larger budget in both older and newer models produced substantial increases in capabilities, with an increase in the ability to utilize more tokens in newer models compared to older models.

Figure 1: Cumulative success rates as a function of token budget (AISI, upper top left) and turn budget (Irregular, lower bottom right) on a subset of our private cyber tasks. Each increase in the cumulative success rate reflects more attempts ending successfully as the budget increases. X-axes are on a log scale, so increases reflect gains over orders of magnitude of inference compute. Newer models (blue lines) show continued gains at higher budgets, whereas older models (orange) show smaller gains.

Our results show that average success rates across a range of tasks continues to improve as inference budgets scale. Importantly, some of the harder tasks are only solved late in long evaluations: ~8% of AISI’s tasks were only solved by increasing the token limit from 10 to 50 million tokens. This means that reliably estimating performance requires running long, budget-intensive evaluations, to capture these late solves. For difficult tasks, this may mean budgets of tens of millions of tokens per attempt across multiple repeats.
We should note several important limitations to these findings. First, they are based on cyber tasks — so more testing will be needed to confirm that they generalise to other domains. Second, we cannot precisely quantify the relative contributions of scaffold design and model capability, though our comparison across models with the same type of scaffolding suggests that the ability to exploit extended inference is model-dependent. Finally, success rates at a given budget carry inherent randomness, and while our sample sizes are sufficient to demonstrate the scaling effect, they are too few to precisely estimate true success rates. Our curves and plateaus could shift with larger sample sizes.

## What does this mean for cyber evaluations?
Our results demonstrate that accurately estimating cyber capabilities is likely to require significantly larger inference budgets than commonly assumed.
AISI’s success rates scale roughly with the log of the total tokens used per attempt: every time we double the token budget, we see about the same absolute increase in success rate. The downside is that, for hard tasks, even modest additional performance improvements require exponentially larger inference budgets, which makes accurate evaluation increasingly costly.
This doesn’t mean that costs per run will become unmanageable: at AISI’s 50M token limit, the average cost per run was around $10, with maximum cost per run below $60. For Irregular’s 1000 iterations per run, the average cost per run varies from under $1 for easier challenges, to up to $20 for medium and most hard challenges, with specific harder challenges approaching $100. The expense comes from scale – reliably estimating performance ceilings requires many tasks and multiple repeats, with total evaluation costs growing accordingly.These findings affect how we estimate model horizons, which represent the difficulty level (measured in human time) at which a model's success rate drops below 50%. Because horizon estimates depend on measured success rates, and measured success rates depend on the inference budget allowed, evaluations run at insufficient budgets will underestimate the true horizon of the model. At the budgets we tested, increasing the token limit meaningfully shifts horizon estimates upward, suggesting that previous estimates at lower budgets would be too conservative.

## How can we choose the right inference budget?
Calculating the ideal inference budget for cyber evaluations requires navigating a trade-off: setting budgets too low risks underestimating a model’s capabilities, while setting it too high risks paying for unproductive tokens without improving capability estimates.
Irregular have proposed cost per success as a useful metric for estimating the economic feasibility of cyber tasks. This is the total cost of all attempts divided by the number of successes, which reflects the average amount one can expect to spend to complete a task successfully.
One way to reduce the risk of over-estimating the expected cost per success of a challenge is to calculate it at various budget thresholds. In theory, we expect cost per success to be very high when inference budgets are low, as we expect few, if any, successes – and as budgets increase, we expect it to come down. At some point, we expect the cost per success to begin increasing again, as extra iterations only extend runs where the model has already made a fatal error, wandered down a fruitless path, or hit a problem it simply cannot solve regardless of compute. Finding this dip in the curve, where cost per success is lowest, can maximise capability estimation without overspending.

Figure 2: The cost per success as a function of token budget (AISI, lower left) and turn budget (Irregular, upper right) on subsets of difficult challenges. The curves match our expectations: cost to success falls and rises as budgets increase. Evaluators can generate this curve specific models over a set of tasks of interest, and use it to avoid over-estimation of cost per success.

## Going forward
Overall, our findings have direct implications for how cyber evaluations are developed and reported.
Our results inform how evaluations should shape security decisions. A model showing 5% success at 2M tokens might reach 30% at 50M tokens – a shift that could cross capability thresholds relevant to risk assessments. Evaluations at typical token or turn limits may substantially understate how close models are to dangerous capability thresholds. Policymakers and developers need accurate capability ceiling estimates, not point estimates at fixed budgets.
More research is needed to understand whether these results apply to other domains. Results from Model Evaluation & Threat Research (METR) suggest this continued scaling at high token budgets may not hold for all software engineering tasks. Whether inference scaling in the form of more agent turns generalises beyond cyber remains an important open question.
Transparency about the inference limits imposed during evaluations – including token counts, turn limits, cost caps, and time constraints – could help contextualise evaluation results, allowing readers to distinguish low model capability from constrained evaluation settings. While some organisations now report these limits, the practice is not yet consistent. By monitoring inference scaling curves, evaluators can determine whether their chosen budget is sufficient, or whether additional compute would continue to improve estimated performance.
Looking ahead, these trends will make cyber evaluations increasingly resource-intensive. Environments will need to support stable, long-running agent sessions, and evaluators will need tooling to determine whether their chosen budgets are sufficient. More fundamentally, the community may need methods for estimating long-run performance from shorter, cheaper runs – for example, by extrapolating from inference scaling curves. Without such approaches, the gap between measured and actual model capability is likely to widen as models continue to improve.

BACK TO PUBLICATIONS

 - - - - - - - - - - - - - - - - - - - - - - - - -
