# UAVThreatBench
Benchmark dataset and evaluation framework for RED-compliant cybersecurity threat identification in UAV–OT systems.

**UAVThreatBench** is a benchmark dataset designed to evaluate the ability of Large Language Models (LLMs) to identify cybersecurity threats in industrial UAV–OT (Operational Technology) environments. It supports structured assessment of semantic alignment with expert-defined threats and regulatory requirements from the EU Radio Equipment Directive (RED 2014/53/EU).

## Repository Contents

### 📂 Files

- **`plausible_uav_ot_cyber_scenarios_withoutThreats.json`**  
  This file includes the same 924 scenarios but **without** the `Expected Threats` field.  
  ➤ *Used as input to LLMs for generating threats.*

- **`plausible_uav_ot_cyber_scenarios_withThreats.json`**  
  This file contains 924 expert-curated UAV–OT cybersecurity scenarios with corresponding expected threats. Each threat is labeled with its relevant **RED Article** — (d) network integrity, (e) personal data/privacy, or (f) fraud/economic harm.  
  ➤ *Used as the ground truth for evaluating LLM-generated threats.*

## Use Case

UAVThreatBench enables structured comparison of LLM threat generation capabilities in critical infrastructure settings. Evaluation metrics may include:

- Perfect/Partial/No Match rates (fuzzy semantic matching)
- RED article alignment accuracy
- Scenario-level recall and precision
- Threat type coverage (Confidentiality, Integrity, Availability)

## Use Case (under publication)

This benchmark has been used to evaluate the cybersecurity threat generation performance of seven different Large Language Models (LLMs) on industrial UAV–OT scenarios.

A subset of **100 randomly selected scenarios** from the dataset was chosen as the evaluation set. The models were given input from the file `plausible_uav_ot_cyber_scenarios_withoutThreats.json` (i.e., scenarios without ground truth threats). Each LLM generated its own set of predicted threats for each scenario.

These outputs were then **automatically evaluated** by comparing them against the expert-defined ground truth in `plausible_uav_ot_cyber_scenarios_withThreats.json` using a fuzzy string matching algorithm (`token_set_ratio` with a threshold of 70). This allowed partial matches and semantic similarity to be quantitatively captured.

🔍 The results of this evaluation—covering threat match rates, RED article alignment, and scenario-level classification—are available in a **separate Git branch** of this repository.

## Citation

If you use this benchmark, please cite the corresponding paper:

Iyenghar, Padma. *UAVThreatBench: A UAV Cybersecurity Risk Assessment Dataset and Empirical Benchmarking of LLMs for Threat Identification.* **Drones**, 9(9), 657, 2025.  
[👉 Read the article on MDPI](https://www.mdpi.com/2504-446X/9/9/657)

```bibtex
@Article{drones9090657,
  author        = {Iyenghar, Padma},
  title         = {UAVThreatBench: A UAV Cybersecurity Risk Assessment Dataset and Empirical Benchmarking of LLMs for Threat Identification},
  journal       = {Drones},
  year          = {2025},
  volume        = {9},
  number        = {9},
  article-number= {657},
  issn          = {2504-446X},
  url           = {https://www.mdpi.com/2504-446X/9/9/657}
}

---

For questions or contributions, please contact [Padma Iyenghar](mailto:piyengha@uos.de).
