Repositories in scope:
- DS-core
- DS-sense
- DS-model-serving
- Knowledge-base
- LLM-service
- Optimize\

High Level Architecture scrappy notes:
## Prediction 
* From BE: DS-sense --> 
* DS-core-inbound (run_all_tasks function) populate the nlu_info --> 
	* sense performs Intent Classification --> 
	* Kb (Stored) Training -->
* answer AI (cosine sim 0.85) if not Answer Net (DS Model Serving)
## Training: (saving the data)
* 1.Intent --> sense sample queries --> ES
* 2.Answer AI --> KB (parsing) -> Saved QnAs --> ES
* 3.starts from KB --> Answer Net --> Model Serving (parsing in KB, creating ES in Model Serving)
##  Unclassified intent architecture for LLM-service:

![alt text](new_pipeline.png)

