# Junior Hockey 2026-27 Predictions (V2.0 - Revised)

Interactive web dashboard for junior hockey player performance predictions for the 2026-27 season.

## 🚀 V2.0 Improvements

This version includes 3 proven improvements that enhance prediction accuracy:

### **1. Age-Based Growth Trajectory**
- Players show predictable PPG growth by age in OHL
- Age 17→18: +0.22 PPG average bonus (81% of players improve)
- Age 18→19: +0.15 PPG average bonus
- Age 19→20: +0.12 PPG average bonus
- Age 20→21: +0.10 PPG average bonus
- Model now accounts for developmental growth expected at each age

### **2. Multi-Year Trajectory Detection**
- Analyzes 3+ year patterns to identify improving vs. declining players
- 71.6% of OHL players with 3+ years are on improving trajectories
- Only 4.6% are consistently declining
- Adds ±0.075 PPG bonus/penalty based on historical trajectory
- Helps catch breakout years and declining players the old model missed

### **3. Non-Linear Cross-League Transitions**
- Elite players transitioning to OHL drop less severely
- Low PPG U16 players (0.5 PPG): Drop to ~0.15 OHL PPG (70% drop)
- Elite U16 players (2.5 PPG): Drop to ~0.35-0.40 OHL PPG (less severe drop)
- Recognizes that elite scorers maintain proportionally more value

## 🏒 Features

- **Filter by multiple dimensions:**
  - Player name (search)
  - League (OHL, OJHL, GOJHL, NOJHL, U16 leagues)
  - Position (Center, Winger, Defense)
  - Age Group (U16-U20)
  - Current season PPG range

- **Sortable columns** - Click any column header to sort ascending/descending

- **Multi-league predictions** - Switch between OHL, OJHL, GOJHL, NOJHL predictions with one click

- **Color-coded visualization:**
  - League badges by color
  - Position indicators
  - Prediction quality indicators (green for high, yellow for mid, red for low)

## 📊 Data

Built from:
- **24,552 junior hockey records** (2010-2026)
- **12,012 AAA records** (2010-2026)
- **Deduplicated and cleaned** to remove duplicate entries
- **12,137 player transitions** analyzed for model building
- **38 full regression models** + **85 fallback models**

## 🎯 Model Performance

V2.0 captures real patterns in the data:
- **Age growth:** 81% of 17→18 year olds improve
- **Trajectories:** 71.6% of veterans on improving paths
- **Elite transitions:** Top scorers drop proportionally less

### Key Improvements:
| Feature | Impact |
|---------|--------|
| Age Growth | +0.10 to +0.22 PPG bonus by age |
| Trajectory | ±0.075 PPG bonus/penalty for improving/declining |
| Elite Players | 15-30% boost for high scorers in cross-league |

## 🚀 Quick Start

### Option 1: GitHub Pages (Recommended)

1. Create a new GitHub repository: `hockey-predictions`
2. Clone to your machine:
   ```bash
   git clone https://github.com/YOUR_USERNAME/hockey-predictions.git
   cd hockey-predictions
   ```

3. Copy the files:
   ```bash
   cp index.html .
   cp predictions_data.json .
   ```

4. Commit and push:
   ```bash
   git add .
   git commit -m "Add hockey predictions dashboard v2.0"
   git push origin main
   ```

5. Enable GitHub Pages:
   - Go to Settings → Pages
   - Set source to "Deploy from a branch" / "main" / "/ (root)"
   - Your site will be live at: `https://YOUR_USERNAME.github.io/hockey-predictions/`

### Option 2: Local Testing

Simply open `index.html` in your browser (make sure `predictions_data.json` is in the same directory)

## 📝 Files

- `index.html` - Main interactive dashboard (React-based, fully self-contained)
- `predictions_data.json` - 2,056 player predictions in JSON format
- `README.md` - This file

## 🔍 Understanding the Predictions

### How It Works (V2.0)

The predictor uses **enhanced regression models** trained on historical transitions:

1. **Base Regression** (on PPG, GP, position)
   - For high-sample transitions (n≥30): Full linear regression
   - For medium samples (5-29): Smart regression on key features

2. **Age Growth Adjustment** 
   - Adds expected growth bonus based on age progression
   - 17-year-olds get +0.22 PPG boost when predicting 18-year-old performance

3. **Trajectory Bonus**
   - Multi-year improving trend: +0.075 PPG
   - Consistent decline: -0.075 PPG
   - Stable: no adjustment

4. **Elite Player Adjustment**
   - High-scoring players transitioning leagues drop less
   - Captures that elite scorers maintain proportionally more value

### Example: Cole Beaudoin

- **Current:** OHL, 1.63 PPG
- **V1.0 Prediction:** 99.7 OHL points
- **V2.0 Prediction:** 111.6 OHL points
- **Why:** Improving trajectory (+0.075 bonus), elite scorer, continues developing

## 📦 Data Dictionary

| Column | Description |
|--------|-------------|
| Player | Player name |
| Team_2025_26 | Team in current season |
| League_2025_26 | Current league |
| Age_Group_2025_26 | Age group (u16-u20) |
| Position_Class | Position (C, W, D, F_Other) |
| GP_2025_26 | Games played in 2025-26 |
| TP_2025_26 | Total points in 2025-26 |
| PPG_2025_26 | Points per game in 2025-26 |
| PPG_[LEAGUE]_2026_27 | Predicted PPG for target league |
| PTS_[LEAGUE]_2026_27 | Predicted total points (68 OHL GP, 56 OJHL GP, 50 for others) |

## 🛠️ Technical Stack

- **Frontend:** React 18 (via CDN)
- **Data Format:** JSON
- **Styling:** CSS3 with responsive design
- **Hosting:** GitHub Pages (free, no build required)
- **Model:** Enhanced linear regression with 3 core improvements

## 📈 Backtest Results (2024-25 → 2025-26)

On OHL→OHL transitions (181 players):
- **R² Score:** 0.688
- **MAE (PPG):** 0.163
- **67% within ±0.15 PPG**
- **82% within ±0.20 PPG**

## 🔗 Links

- Dashboard: [Your GitHub Pages URL]
- Data: See `predictions_data.json` in repo

---

**Last Updated:** May 2026  
**Model Version:** V2.0 Revised  
**Data Through:** 2025-26 season  
**2026-27 Predictions Ready**
