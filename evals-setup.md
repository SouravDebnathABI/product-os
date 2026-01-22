# Evals Setup
* Langfuse will be used to maintain prompts, curated datasets, experiments and tracing
* Developers/testers to annotate datasets to maintain a golden dataset
* Developers/testers to annotate current responses via running experiment to check real truth
* Evals metrics to mark responses as correct or incorrect with same method as developers/testers
* Check the confusion matrix to understand gap in scoring strategy
* Iterate with metrics to reach optimal level of precision and recall to validate a good scoring strategy
* Once validated, scoring shall be frozen and used to take decisions
* To prove old orchestration is better than new
	* first phase will be to simply check how many responses were generated in new vs old (quantitative assessment)
	* second phase will be to check quality of answers where responses were present
		* first approach - compare old vs new responses but this will require a new set of evals since traditional evals compare expected response with current response
		* second approach - compare old vs expected and new vs expected which retains the traditional approach but will take longer time


## Risks
* Langfuse RBAC is taking a long time to be implemented and needs enterprise license procurement - Mitigation - focus on dataset curation on GitHub and evals experiments conducted by Core Team members only
* Developers/testers may not have bandwidth to annotate datasets - Mitigation - prioritize critical datasets first eg. BG, POS, BrewGPT
* Datasets may not be representative enough to validate scoring strategy - Mitigation - ensure diverse datasets are included in curation by taking comments from multiple stakeholders in validation
* Scoring strategy may not reach optimal precision and recall - Mitigation - involve Core Team members with expertise in LLM evals to help iterate on metrics
* Old orchestration may not have enough responses to compare with new orchestration - Mitigation - focus on quantitative assessment of response counts and prioritize critical datasets for quality comparison

