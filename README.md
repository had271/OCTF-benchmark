# Synthetic Dataset for Collaborative Team Formation

This repository provides a synthetic dataset designed for evaluating algorithms in **collaborative team formation**, task allocation, and optimization problems under varying task and skill complexities.  
The dataset was generated using **randomized sampling in Python** with:

- Controlled task complexity  
- Variable team sizes  
- Diverse skill assignments  

---

## Dataset Contents

The repository includes:

- An expert dataset describing skills and workload
- Multiple task datasets grouped by **number of required skills per task**  

All files are in **CSV format**.

---

## Experts Dataset

The **experts dataset** includes **100 experts**, each described by:

| Column | Description |
|--------|-------------|
| expert_ID | Unique identifier for each expert |
| skills | List of skills assigned to the expert |
| current_workload | Count of assigned tasks |

- Skills were sampled from a pool of **20 or 30 distinct skills** (depending on the version).  
- Each expert was assigned **2–7 skills**.  
- `current_workload` initialized to **0** and incremented during experiments.

---

## Task Datasets

Multiple task datasets were created to model different problem complexities.

###  Group 1: Initial Datasets (100 tasks each)

| Skills per Task | Filename |
|-----------------|----------|
| 3 skills | `tasks_3skills.csv` |
| 5 skills | `tasks_5skills.csv` |
| 7 skills | `tasks_7skills.csv` |
| 10 skills | `tasks_10skills.csv` |
| 15 skills | `tasks_15skills.csv` |

---

### Group 2: Expanded Datasets (200 tasks each)

| Skills per Task | Filename |
|-----------------|----------|
| 3 skills | `tasks_3_ext.csv` |
| 5 skills | `tasks_5_ext.csv` |
| 7 skills | `tasks_7_ext.csv` |
| 10 skills | `tasks_10_ext.csv` |
| 15 skills | `tasks_15_ext.csv` |
| 20 skills | `tasks_20_ext.csv` |

---

##  Task Structure

Each task record includes:

| Column | Description |
|--------|-------------|
| task_ID | Unique identifier |
| skill_requirements | List of required skills |
| num_experts | Number of experts needed |

The number of experts was computed using:
num_experts = max(2, min(round(n_skills/2),
round(n_skills * random.uniform(0.3, 0.6))))

---

##  Intended Use

This dataset is suitable for research on:

- Optimization and meta-heuristics  
- Hybrid algorithms (e.g., ABC-SA)  
- Task allocation and scheduling  
- Skill-matching models  
- Multi-objective optimization  

It has been used to evaluate:

- SA  
- ABC  
- ABC-SA  

