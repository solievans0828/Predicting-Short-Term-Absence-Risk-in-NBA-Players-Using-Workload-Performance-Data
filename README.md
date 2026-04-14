# Predicting Short-Term Absence Risk in NBA Players

##  Project Overview
This project uses data science and machine learning techniques to predict short-term absence risk in NBA players based on workload, performance, and recovery-related variables.

In professional basketball, player availability is critical for team success. This project explores whether recent workload and performance patterns can be used to identify players who are at higher risk of missing their next game.

Rather than relying on confirmed injury data, this study uses a proxy outcome representing whether a player appears in their team’s next scheduled game.

---

##  Research Question
Can player workload, performance, and recovery metrics predict whether an NBA player will miss their next scheduled game?

---

##  Dataset

- **Source:** Kaggle  
- **Dataset:** NBA Player Stats – 2024–2025 Season  
- **Link:** https://www.kaggle.com/datasets/eduardopalmieri/nba-player-stats-season-2425  
- **Rows:** 16,512  
- **Columns:** 25  
- **Unit of Analysis:** Player-game level observations  

Each row represents one player’s performance in one NBA game.

---

##  Target Variable

**`missed_next_game`**
- `0` = Player appears in next scheduled game  
- `1` = Player does not appear in next scheduled game  

This serves as a **proxy for short-term absence risk**, which may include injury, rest, or other factors.

---

##  Feature Engineering

The following features were engineered to capture workload and recovery:

- Minutes played in last 3 and 5 games  
- Average minutes in last 3 games  
- Days since last game  
- Back-to-back game indicator  
- Games played in last 7 days  
- Rest category (low, medium, high)  

Additional performance variables include:
- Points, assists, rebounds  
- Steals, blocks, turnovers  
- Shooting efficiency  
- Game score  

---

##  Models Used

### 1. Logistic Regression
- Baseline model  
- Interpretable coefficients  
- Strong recall for absence prediction  

### 2. Random Forest
- Captures nonlinear relationships  
- Higher overall accuracy  
- Feature importance analysis  

---

##  Model Performance

### Logistic Regression
- Accuracy: 0.73  
- ROC-AUC: 0.79  
- Recall (absence class): 0.73  
- F1-score (absence class): 0.43  

### Random Forest
- Accuracy: 0.88  
- ROC-AUC: 0.78  
- Recall (absence class): 0.26  
- F1-score (absence class): 0.37  

### Key Insight
- Logistic regression performed better at identifying missed games (higher recall)  
- Random forest achieved higher overall accuracy but struggled with minority class detection  

---

##  Key Findings

- Higher workload and limited rest are associated with increased absence risk  
- Back-to-back games and short recovery periods contribute to missed games  
- Workload-based features provide meaningful predictive signal  
- Model performance is impacted by class imbalance and proxy labeling  

---

##  Limitations

- The target variable is a proxy, not confirmed injury data  
- Dataset includes only one NBA season  
- External factors (coaching decisions, rest strategies) are not captured  

---

## Future Work

- Incorporate multi-season data  
- Use confirmed injury datasets  
- Apply advanced models (e.g., gradient boosting)  
- Improve handling of class imbalance  

---

##  Tech Stack

- Python  
- Pandas, NumPy  
- Scikit-learn  
- Matplotlib / Seaborn (optional for EDA)

