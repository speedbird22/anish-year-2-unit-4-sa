# 🏏 IPL Cricket Data Analysis – Decoding Match-Winning Factors

**Course:** The Art of Storytelling with Data  
**CRS Name:** Artificial Intelligence  
**Student Name:** YOUR FULL NAME  
**Candidate Registration Number:** YOUR REG NUMBER  
**School Name:** YOUR SCHOOL NAME  

---

# 📌 Project Overview

This project analyses the Indian Premier League (IPL) dataset to uncover match-winning factors, player performance trends, and team rivalry dynamics using Tableau.

The objective is to build an interactive Tableau dashboard and storyboard that delivers actionable insights for:

- IPL franchises
- Cricket coaches
- Broadcasters
- Sports analysts
- Fans

The analysis focuses on identifying what drives match outcomes through player statistics, team rivalries, toss decisions, and venue influence.

---

# 📊 Data Summary

## Dataset Used

Two CSV files:

- `matches.csv` – Match-level data
- `deliveries.csv` – Ball-by-ball data

## Data Preparation & Cleaning

- Created relationship:  
  `matches.id = deliveries.match_id`
- Removed unnecessary columns (e.g., umpire fields)
- Handled missing values in winner, player_of_match, and result_margin
- Verified aggregation between match-level and ball-level data
- Ensured correct joins and no duplicate expansion errors

## Calculated Fields Created

### 1. Strike Rate
```
(SUM([Batsman Runs]) / COUNT([Ball])) * 100
```

### 2. Bowler Wickets (Excluding Run-Outs)
```
IF [Dismissal Kind] != "run out" THEN [Is Wicket] END
```

### 3. Toss Win Match?
```
IF [Toss Winner] = [Winner] THEN 1 ELSE 0 END
```

### 4. Bat First Win?
```
IF [Toss Decision] = "bat" AND [Winner] = [Toss Winner] THEN 1
ELSE 0
END
```

These calculated fields improved analytical accuracy.

---

# 📈 Exploratory Data Analysis (EDA)

The analysis was structured into four major themes:

---

## 1️⃣ Top Batting Performers

Metrics analysed:
- Total Runs
- Strike Rate
- Boundary impact

Visualization:
- Horizontal bar chart (Top 10 batters)

Insights:
- High strike-rate players influence match momentum.
- Consistent run-scorers drive long-term team success.
- Impact players combine volume with acceleration.

---

## 2️⃣ Top Bowling Performers

Metrics analysed:
- Wickets taken (excluding run-outs)
- Economy rate

Visualization:
- Bar chart (Top 10 bowlers)

Insights:
- Leading wicket-takers strongly influence match outcomes.
- Some bowlers balance high wicket counts with strong economy control.

---

## 3️⃣ Team Rivalries – Head-to-Head Analysis

Metrics analysed:
- Match counts between teams
- Dominance patterns

Visualization:
- Heatmap (Team1 vs Team2)

Insights:
- Certain rivalries show consistent dominance.
- Some matchups are statistically one-sided.
- Rivalry intensity varies across seasons.

---

## 4️⃣ Match-Winning Factors

### Toss Impact

- Calculated % of matches won by toss winner.
- Toss advantage exists but is not always decisive.

### Venue Influence

- Analysed win percentages by venue.
- Some venues favor batting first.
- Others show stronger chasing trends.

Visualization:
- Percentage bar charts
- Venue comparison analysis

---

# 🎨 Dashboard Features

- Interactive filters:
  - Season
  - Team
  - Player
  - Venue
  - Toss Decision
- Dynamic tooltips
- Sorted top-performer views
- Heatmap rivalry visualization
- Percentage formatting for clarity

---

# 📖 Storyboard Structure

The Tableau Story follows this order:

1. Top Batting Performers  
2. Leading Wicket-Takers  
3. Team Rivalries  
4. Toss & Venue Impact  

Each story point includes contextual captions explaining the importance of the insight.

---

# 🔍 Key Insights

- High-impact batters combine scoring volume with strong strike rates.
- Wicket-taking bowlers significantly influence match outcomes.
- Some IPL rivalries demonstrate clear dominance patterns.
- Toss impact varies depending on venue.
- Venue conditions influence strategic decisions and win probability.

---

# 🖼 Screenshots

(Add screenshots here)

Example:
- Dashboard Overview
- Rivalry Heatmap
- Toss Impact Chart
- Venue Analysis

---

# 📁 Repository Structure

```
IADAI204-StudentID-StudentName/
│
├── Data/
│   ├── matches.csv
│   └── deliveries.csv
│
├── IPL_Dashboard.twbx
│
└── README.md
```

---

# 🏁 Conclusion

This project demonstrates how sports analytics can uncover strategic insights in cricket.

By integrating match-level and ball-level data, the dashboard highlights:

- Player performance impact
- Tactical decision influence
- Venue-based winning trends
- Rivalry dominance patterns

The interactive Tableau dashboard transforms raw IPL data into actionable insights for stakeholders.

---

# 🚀 Future Improvements

- Add season-wise performance trends
- Include powerplay vs death-over analysis
- Build predictive models for match outcomes
- Expand player segmentation analysis
