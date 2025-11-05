# Credit-G Scoring (CRISP-DM)

This project applies the **CRISP-DM methodology** to build a **credit scoring model** using the `credit-g` dataset (available on [OpenML](https://www.openml.org/d/31)).

---

## Objective

The main goal is to **predict the credit risk** (good or bad credit) of applicants based on socio-economic and financial features.

This project demonstrates:
- The **end-to-end data science process** from understanding to deployment.
- The application of **best practices in machine learning pipelines**.
- The use of **modern tools** for reproducibility and interpretability.

---

## Methodology: CRISP-DM Phases

### 1. Business Understanding

Define business objectives and success metrics:
- Goal: Identify reliable borrowers to reduce financial risk.
- Success Metric: Model achieving ≥ 80% accuracy or AUC > 0.75 on test data.

### 2. Data Understanding

### 3. Data Preparation

### 4. Modeling

### 5. Evaluation

### 6. Deployment

---

## Data

- **Source:** [OpenML – Credit-G dataset](https://www.openml.org/d/31)  
- **Loading example:**
  ```python
  from sklearn.datasets import fetch_openml
  data = fetch_openml("credit-g", version=1, as_frame=True)
  df = data.frame
  ```

---

## Roadmap
- [x] 1. Business Understanding
- [ ] 2. Data Understanding
- [ ] 3. Data Preparation
- [ ] 4. Modeling
- [ ] 5. Evaluation
- [ ] 6. Deployment

---

## Author
**Franck Ngaha**  
Developer • Data Science & AI Enthusiast  
[franck.o.ngaha@gmail.com](mailto:franck.o.ngaha@gmail.com)  
[GitHub Profile](https://github.com/fngaha)