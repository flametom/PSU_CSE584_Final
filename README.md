
# CSE 584 Final Project

**Jeongwon Bae (945397461)**

---

## Overview

This project evaluates the metacognitive abilities of state-of-the-art Large Language Models (LLMs), including GPT-4o, Claude 3.5 Haiku, Llama 3.2, Qwen 2.5, and Gemma 2. Through the creation of a dataset of **faulty science questions**, the project assesses the models' ability to detect errors, admit and correct mistakes, and maintain consistent responses. The goal is to highlight areas where LLMs fall short in scientific reasoning, moving beyond surface-level pattern recognition.

---

## Objectives

1. **Dataset Creation**: Develop a diverse set of faulty science questions across various disciplines to evaluate LLMs' reasoning capabilities.
2. **Experimental Evaluation**: Design and conduct experiments to test the models on error detection, correction, and response consistency.

---

## Dataset: Faulty Science Questions

A total of 3,000 faulty questions were initially generated, comprising 500 questions in each of six disciplines: Mathematics, Physics, Biology, Chemistry, Earth Science, and Computer Science. Due to computational limitations, the experimental dataset was reduced to 600 questions, with 100 questions per discipline. The selection process used cosine similarity analysis to ensure diverse coverage and minimize redundancy.

---

## Research Questions

1. **Error Detection in Faulty Questions**: 
   - How effectively can LLMs detect logical inconsistencies, incorrect premises, or impossible conditions in faulty questions?
   - What types of errors are more likely to be detected or missed by different models?

2. **Error Admission and Correction After Feedback**: 
   - When provided with feedback pointing out an error, how do LLMs react?
   - Do they admit the error and provide corrected answers, or justify their initial responses without acknowledging the mistake?

3. **Consistency and Adaptation Over Repeated Interactions**: 
   - How consistent are LLMs when faulty questions are posed again?
   - Can LLMs recognize and correct initial mistakes without external feedback?

---

## Experimental Design

### Dataset Organization

The dataset includes the following columns:
- **Discipline**: Subject area (e.g., Math, Physics, Biology).
- **Question**: Faulty science question.
- **Reason it is faulty**: Explanation of the flaw or fallacy.
- **Tested LLM**: Name of the LLM tested.
- **LLM Response**: The model's answer and its observed error.

### Testing Procedure

1. **Experiment 1: Error Detection Ability**  
   - Present each faulty question to the LLM and analyze its response for explicit recognition of errors.  
   - Use pattern matching to identify key phrases such as "impossible," "contradiction," or "invalid."

2. **Experiment 2: Error Admission and Correction Ability**  
   - Provide feedback on the LLM's initial answer, pointing out the error, and ask for a revised response.  
   - Record whether the model admits the mistake and assesses the quality of the correction.

3. **Experiment 3: Context Maintenance Ability**  
   - Re-present the same faulty questions in repeated interactions to observe whether the model adjusts its responses without feedback.  
   - Simulate continuous dialogue by maintaining conversation history.

### Evaluation Metrics

- **Error Detection Rate (EDR)**: Percentage of questions where the LLM successfully identified an error.
- **Error Identification Accuracy (EIA)**: Semantic similarity between the model's error identification and the actual faulty reason.
- **Error Admission Rate (EAR)**: Percentage of instances where the LLM admitted its error upon receiving feedback.
- **Correction Accuracy (CA)**: Improvement in error identification accuracy after feedback.
- **Context Consistency Score (CCS)**: Degree to which the LLM's responses remained consistent across repeated interactions.

---

## Results

### Experiment 1: Error Detection Ability

| Model                  | EDR (%) | EIA (Avg.) |
|------------------------|---------|------------|
| GPT-4o                | 16.5    | 0.5286     |
| Claude 3.5 Haiku       | 8.33    | 0.5379     |
| Llama 3.2-3B-Instruct  | 6.67    | 0.5245     |
| Qwen 2.5-3B-Instruct   | 21.67   | 0.5149     |
| Gemma-2-2B-It          | 7.00    | 0.5164     |

### Experiment 2: Error Admission and Correction Ability

| Model                  | EAR (%) | CA (Avg.)  |
|------------------------|---------|------------|
| GPT-4o                | 33.93   | 0.1303     |
| Claude 3.5 Haiku       | 29.27   | 0.0987     |
| Llama 3.2-3B-Instruct  | 13.75   | 0.0337     |
| Qwen 2.5-3B-Instruct   | 30.21   | 0.1470     |
| Gemma-2-2B-It          | 40.04   | 0.0449     |

### Experiment 3: Context Maintenance Ability

| Model                  | CCS (Avg.) |
|------------------------|------------|
| GPT-4o                | 0.9339     |
| Claude 3.5 Haiku       | 0.9263     |
| Llama 3.2-3B-Instruct  | 0.9399     |
| Qwen 2.5-3B-Instruct   | 0.8977     |
| Gemma-2-2B-It          | 0.9456     |

---

## Repository Structure

- `CSE584_Final_DataSet_JeongwonBae.xlsx`: Dataset containing all faulty questions and GPT-4o response.
- `Experiment.ipynb`: Code for testing LLMs on faulty questions.
- `Result_Extracted.ipynb`: Detailed result extraction and analysis.
- `CSE584_Final_Project_JeongwonBae.pdf`: Final project report.
- `dataset`: raw data of 600 questions and LLMs responses with experiment metrics.
- `result`: raw data of the result extraction and analysis.

---

For further details, refer to the project report and associated documentation.
