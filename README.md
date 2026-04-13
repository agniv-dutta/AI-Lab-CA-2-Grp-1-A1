# Lab CA-2 — Prompt Engineering & LLM Behavior Analysis

![University Name](https://img.shields.io/badge/University-Your_University_Name-0f766e?style=for-the-badge)
![Subject](https://img.shields.io/badge/Subject-Artificial%20Intelligence%20(Sem%20VI)-1d4ed8?style=for-the-badge)
![Semester](https://img.shields.io/badge/Semester-VI-7c3aed?style=for-the-badge)

---

## 📚 Table of Contents

- [Project Overview](#-project-overview)
- [Team Members](#-team-members)
- [Objectives](#-objectives)
- [Tools and Models Used](#-tools-and-models-used)
- [Methodology](#-methodology)
- [Test Inputs](#-test-inputs)
- [Results Summary](#-results-summary)
- [Failures and Biases Identified](#-failures-and-biases-identified)
- [Key Findings and Reflection](#-key-findings-and-reflection)
- [Repository Structure](#-repository-structure)
- [How to Reproduce](#-how-to-reproduce)
- [References](#-references)

---

## 📘 Project Overview

This repository contains the submission for **Lab CA-2 — Prompt Engineering & LLM Behavior Analysis** conducted for the subject **Artificial Intelligence (Sem VI)**. The work evaluates how two large language models respond to different prompt engineering strategies in a **Resume / SOP Evaluator** domain.

The study compares **ChatGPT (GPT-4o)** and **DeepSeek** across **40 runs** in total, covering **4 prompt types × 5 test inputs × 2 models**. The goal was to observe differences in reasoning quality, consistency, bias, hallucination risk, and adherence to structured output expectations.

> Note: All LLM outputs are logged in the `/screenshots` and `/outputs` folders. Prompt templates and structured prompt variations are maintained separately in `/prompts`.

---

## 👥 Team Members

| Name | Class | Roll No. |
|---|---:|---:|
| Agniv Dutta | TY A1 | 16010123029 |
| Aditya Choudhuri | TY A1 | 16010123021 |

---

## 🎯 Objectives

- Evaluate how prompt design changes LLM behavior in a resume/SOP assessment task.
- Compare output quality between ChatGPT (GPT-4o) and DeepSeek.
- Measure the effect of zero-shot, few-shot, role-based, and chain-of-thought prompting.
- Identify hallucination, bias, over-generalisation, and contradiction-detection failures.
- Summarise which prompt strategy produced the most reliable evaluation output.

---

## 🛠️ Tools and Models Used

| Category | Details |
|---|---|
| Domain | Resume / SOP Evaluator |
| Models Compared | ChatGPT (GPT-4o), DeepSeek |
| Prompting Styles | Zero-shot, Few-shot, Role-based, Chain-of-Thought |
| Total Runs | 40 |
| Logging | `/screenshots`, `/outputs` |

---

## 🧪 Methodology

The same five test inputs were evaluated with four prompt strategies on both models. Each prompt type was designed to test a different level of structure and reasoning control.

### 1. Zero-shot Prompt

A direct evaluation prompt with no examples and no persona framing. This was used as the baseline to measure raw model behavior.

### 2. Few-shot Prompt

A prompt containing **2 examples** to guide expected tone, structure, and evaluation style. This tested whether demonstrations improved consistency and format adherence.

### 3. Role-based Prompt

A prompt that frames the model as a **Senior Technical Recruiter**. This was intended to encourage more professional, hiring-oriented feedback and better judgment.

### 4. Chain-of-Thought Prompt

A structured **8-step reasoning prompt** that asks the model to analyze the input in stages before producing the final evaluation. This was used to examine whether stepwise reasoning improved accuracy and reduced missed issues.

---

## 📝 Test Inputs

Five resumes were used to test robustness across clear, ambiguous, incomplete, and contradictory cases.

| Input | Description |
|---|---|
| 1. Strong Resume | Aanya Kapoor — well-structured profile with quantified achievements and clear presentation |
| 2. Weak Resume | Rohan Verma — vague objective and no measurable metrics |
| 3. Ambiguous Resume | Neha Joshi — career switcher from banking to data |
| 4. Incomplete Resume | Karan — missing contact details, education, and email |
| 5. Contradictory Resume | Priyanka Desai — claims to be a fresher but also shows 5 years of senior experience; certification dates predate graduation |

---

## 📊 Results Summary

The overall pattern was clear: **ChatGPT outperformed DeepSeek across all four prompt types**. The strongest performance came from **Role-based** and **Chain-of-Thought** prompting, while **Zero-shot** was the weakest for both models.

| Prompt Type | ChatGPT (GPT-4o) | DeepSeek | Summary of Output Quality |
|---|---:|---:|---|
| Zero-shot | 4.4/10 avg | 3.6/10 avg | Weakest prompt style; outputs were generic and less reliable |
| Few-shot | Higher than zero-shot | Improved notably in format adherence | Examples helped both models, especially DeepSeek’s structure |
| Role-based | 8.8/10 avg | Lower than ChatGPT | Best hiring-context alignment and professional tone |
| Chain-of-Thought | 8.8/10 avg | Lower than ChatGPT | Best reasoning depth; DeepSeek showed more hallucination risk on incomplete input |

Detailed per-run outputs and screenshots are preserved in `/outputs` and `/screenshots` for review and verification.

---

## ⚠️ Failures and Biases Identified

- **Hallucination:** DeepSeek fabricated a university name on the incomplete resume in the Chain-of-Thought run for Input 4.
- **Bias:** Both models unfairly penalised the career-switcher resume on the zero-shot prompt.
- **Over-generalisation:** Both models produced generic feedback when no structure or examples were provided.
- **Incorrect assumption:** Both models missed all contradictions in the zero-shot evaluation of Input 5.

---

## 🔍 Key Findings and Reflection

- ChatGPT delivered more consistent and higher-quality evaluations overall.
- Role-based and Chain-of-Thought prompts were the most effective for this task.
- Zero-shot prompting exposed the models’ weakest behavior, especially on ambiguous and contradictory cases.
- Few-shot prompting improved DeepSeek more noticeably in output format and structure than it improved ChatGPT.
- DeepSeek was more prone to hallucination when the input was incomplete.

From a prompt-engineering perspective, the results show that better framing, examples, and explicit reasoning steps can materially improve LLM reliability in evaluation tasks. The experiment also highlights that prompt design influences not only output quality but also fairness and factual discipline.

---

## 🗂️ Repository Structure

```text
.
├── prompts/
├── outputs/
├── screenshots/
├── report/
└── README.md
```

### Folder Purpose

- `prompts/` stores the prompt templates used for all four prompting strategies.
- `outputs/` stores the generated LLM responses and evaluation logs.
- `screenshots/` stores visual proof of runs and captured outputs.
- `report/` stores the final submission report and supporting documentation.
- `README.md` provides the project summary and reproduction instructions.

---

## ▶️ How to Reproduce

1. Open the `/prompts` folder and review the four prompt templates.
2. Use the same five test inputs listed above.
3. Run each input through both models: ChatGPT (GPT-4o) and DeepSeek.
4. Save the generated responses in `/outputs`.
5. Capture screenshots of the interactions and store them in `/screenshots`.
6. Compare the outputs using the same evaluation criteria across all 40 runs.
7. Summarise the findings in the report folder and update this README if the scoring rubric changes.

> Important: This README intentionally does not include any raw prompt text or full resume content. Those details belong in the `/prompts` folder and supporting analysis files.

---

## 📎 References

- OpenAI documentation for GPT-4o and prompt usage guidelines.
- DeepSeek model documentation and product notes.
- Standard prompt engineering references for zero-shot, few-shot, role-based, and chain-of-thought prompting.
- Course material for Artificial Intelligence (Sem VI).

---

**Submission Note:** This project focuses on behavioral comparison and prompt engineering analysis. All detailed artefacts, including outputs and screenshots, are stored in the repository folders referenced above.