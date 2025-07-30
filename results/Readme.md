# Evaluation Results

This folder contains evaluation artifacts from the UAVThreatBench benchmark, which assesses the ability of various Large Language Models (LLMs) to generate RED-compliant cybersecurity threats for UAV–OT scenarios.

## Overview

A subset of 100 randomly selected scenarios was used to evaluate 7 different LLMs. Each model was prompted using the same set of inputs (from `benchmark_100_random_scenarios.json`), and the generated threats were compared against expert-curated ground truth (`benchmark_100_random_scenarios_withThreats_groundtruth.json`) using a fuzzy matching algorithm.

## Files

###  Input and Ground Truth

- `benchmark_100_random_scenarios.json`:  
  Input scenarios used for querying the LLMs (without threats).

- `benchmark_100_random_scenarios_withThreats_groundtruth.json`:  
  Same scenarios, but with expert-defined threats (used as ground truth for evaluation).

###  Evaluation Output (per model)

- `gpt-3.5-turbo-16k_threats.json`
- `gpt-4.1-mini_threats.json`
- `gpt-4.1-nano_threats.json`
- `gpt-4.1_threats.json`
- `gpt-4o_threats.json`
- `llama-3.1-sauerkrautlm-70b-instruct_threats.json`
- `llama-3.3-70b-instruct_threats.json`

Each file contains the model-generated threats for the 100 scenarios. These outputs were benchmarked against the ground truth.

### 📝 Log and Metadata

- `evaluation_log.txt`:  
  Execution log for evaluation runs, including timing, environment metadata, and performance summary.

## Evaluation Procedure

Each model’s output was compared against the expert ground truth using a fuzzy token set ratio (threshold: 70). Metrics such as perfect match rate, RED Article compliance, and partial/no match rates were computed.

## Notes

- Full analysis and result figures are discussed in the main paper.
- This folder reflects only the evaluation subset (100/924 scenarios). The full dataset is available at the root level of the repository.


