# Junior Hockey 2026-27 Predictions

Interactive web dashboard for junior hockey player performance predictions for the 2026-27 season.

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
- **12,137 player transitions** used to build regression models
- **41 full regression models** + **66 fallback models**

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
   git commit -m "Initial commit: predictions dashboard"
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
- `predictions_data.json` - 2,277 player predictions in JSON format
- `README.md` - This file

## 🔍 Understanding the Predictions

### How It Works

The predictor uses **regression models** trained on historical transitions between leagues:

1. **For high-sample transitions (n≥30):** Full linear regression on PPG, GP, and position
2. **For medium samples (5-29):** Smart regression that learns from actual data points
3. **For small samples (<5):** Historical median as fallback

### Example: Kyler Lauder

- **Current:** OMHA-U16, 2.16 PPG (69 pts in 32 GP)
- **Comparables:** Ethan Belchetz (2.47 OMHA → 0.68 OHL), Alex Mclean (2.33 OMHA → 0.38 OHL)
- **Prediction:** 0.44 PPG → **30.2 OHL points**

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

## 📈 Model Performance

| Position | Sample Size | R² Score |
|----------|------------|----------|
| Centers | 7,690+ | 0.67 |
| Wingers | 3,054+ | 0.69 |
| Defense | 5,772+ | 0.62 |

## 🔗 Links

- Dashboard: [Your GitHub Pages URL]
- Data: See `predictions_data.json` in repo

## 📧 Questions?

Check the methodology or data in the source Python scripts.

---

**Last Updated:** May 2026  
**Data Through:** 2025-26 season  
**2026-27 Predictions Ready**
