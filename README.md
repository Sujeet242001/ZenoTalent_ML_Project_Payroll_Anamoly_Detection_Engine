# ZenoTalent_ML_Project_Payroll_Anamoly_Detection_Engine

# Payroll Anomaly Detection Engine  
### ZENVY – AI Powered Payroll

## Introduction
Built an **unsupervised anomaly detection system** for an AI-powered payroll platform to identify suspicious payroll activities such as **salary manipulation** and **fake overtime claims**. The system operates **without labeled data**, supports **batch and real-time pipelines**, and adapts to **concept drift** in evolving payroll patterns.

---

## Project Summary

### Tasks Completed

#### 1. Data Understanding & Assumptions
- Assumed structured payroll records with employee, role, salary, and overtime details
- Designed features to capture deviations from historical and peer-based norms
- Ensured compatibility with both historical and streaming payroll data

---

#### 2. Feature Engineering
- Salary deviation features:
  - Employee salary vs role average
  - Employee salary vs department/agency average
- Overtime-related features:
  - Overtime hours vs standard working hours
  - Overtime pay vs base salary ratio
- Temporal features:
  - Salary change velocity
  - Overtime trend over rolling windows
- Encoded categorical variables for model compatibility

---

#### 3. Anomaly Detection (Unsupervised Learning)
- **Algorithm Used:** Isolation Forest  
- **Contamination Rate:** Configurable (default 1–5%)
- **Salary Anomalies:** Detects abnormal compensation patterns relative to peers
- **Overtime Anomalies:** Flags excessive or unusual overtime usage
- **Combined Model:** Uses all engineered features to generate a unified anomaly score

---

#### 4. Concept Drift Handling
- Monitors feature distribution changes over time
- Compares rolling mean and standard deviation against baseline
- Triggers retraining if:
  - Mean shift > 15%
  - Standard deviation shift > 25%
- Maintains model versioning for auditability

---

#### 5. Pipeline Implementation

**Batch Pipeline**
- Processes historical payroll data in scheduled runs
- Generates anomaly scores for all employees
- Outputs ranked list of top anomalies for review

**Real-Time Pipeline**
- Scores individual payroll transactions instantly
- Uses the latest deployed model
- Flags anomalies for immediate alerting

---

#### 6. Monitoring & Visualization
- Salary distribution comparisons (normal vs anomalous)
- Overtime hours vs pay scatter analysis
- Anomaly score distributions over time
- Drift monitoring dashboards for feature stability

---

## Algorithm Selection Rationale

**Isolation Forest** was selected because:
- Requires no labeled anomaly data
- Efficient and scalable for large payroll datasets
- Performs well in high-dimensional feature spaces
- Naturally isolates rare and abnormal payroll patterns
- Easy to retrain for concept drift adaptation

---

## Evaluation Strategy (No Labels)
- Percentage of anomalies detected based on contamination rate
- Manual inspection of highest-risk payroll records
- Comparison across:
  - Salary-only detection
  - Overtime-only detection
  - Combined feature detection
- Distribution and visualization-based validation

---

## Deployment Plan
- Daily batch anomaly detection for all payroll records
- Real-time API endpoint for new payroll transactions
- Weekly concept drift monitoring
- Automated retraining when drift thresholds are exceeded
- Human-in-the-loop review process for high-confidence anomalies

---

## Conclusion
Successfully implemented a **production-ready payroll anomaly detection engine** that satisfies all system requirements. The solution uses **unsupervised learning**, detects both **salary manipulation and fake overtime**, supports **real-time and batch processing**, and remains resilient to **concept drift**. The system enables proactive fraud detection without relying on labeled training data and can scale with organizational growth.

---

## License
Internal / Educational Use Only
