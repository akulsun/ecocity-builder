# 🌍 EcoCity Builder

> **Can you design the ultimate sustainable metropolis before time runs out?**

**EcoCity Builder** is a fast-paced, strategic 5×5 grid simulation game built purely in Vanilla HTML5, CSS3, and JavaScript. Players manage a starting budget of $1,000 to balance clean energy, residential zones, and nature reserves while keeping pollution low and citizen happiness high.

Featuring clean **Open Sans** typography, responsive layouts, and a **real-time Global Leaderboard powered by Supabase**, EcoCity Builder lets players compete worldwide for the top sustainability ranking.

---

## ✨ Features

- ⏱️ **Timer-on-First-Move:** The 3-minute countdown begins only when you place your first structure—plan your strategy before making your first move.
- 🔄 **Dynamic Undo / Refund:** Click any placed building to dismantle it and refund its budget back into your treasury on the fly.
- 🌿 **Eco-Diversity Scoring Engine:** Rewards balanced city designs (clean energy, housing, agriculture, wetlands, and parks) with up to **+90 Harmony Bonus points**.
- 🛑 **Early Stop Mechanic:** Lock in your metropolis and submit your score as soon as your layout is perfected without waiting for the timer.
- 🌐 **Global Cloud Leaderboard:** Live worldwide ranking powered by **Supabase (PostgreSQL)**, featuring instant score submission and real-time top-50 standings.
- 💾 **Offline & Local Fallback:** Zero external dependencies required to play! Automatically falls back to `localStorage` and the modern **File System Access API** (`leaderboard.json`) when offline.
- 📱 **Fully Responsive:** Optimized side-by-side dashboard for desktop and stacked controls for mobile screens.

---

## 🎮 How to Play

1. **Select a Building** from the palette:
   | Building | Emoji | Cost | Impact |
   | :--- | :---: | :---: | :--- |
   | **Solar Panel** | ☀️ | $80 | High sustainability, zero pollution |
   | **Wind Turbine** | 💨 | $105 | Very high sustainability, clean power |
   | **Forest** | 🌲 | $65 | Lowers pollution, boosts sustainability |
   | **Organic Farm** | 🌾 | $60 | Provides food & sustainability |
   | **Eco-House** | 🏠 | $70 | Houses citizens, boosts happiness |
   | **Water Reservoir** | 💧 | $65 | Essential resource, boosts happiness |
   | **Park / Grass** | 🌱 | $35 | Affordable green space, lowers pollution |
   | **Eco-Factory** | 🏭 | $110 | Generates income, but increases pollution |

2. **Place Buildings:** Click any empty tile on the 5×5 grid. Your timer starts automatically!
3. **Refund / Reposition:** Click any occupied tile to dismantle the structure and reclaim your budget.
4. **Earn Diversity Bonuses:**
   - 4 unique types: **+20 pts**
   - 5 unique types: **+35 pts**
   - 6 unique types: **+55 pts**
   - 7 unique types: **+75 pts**
   - All 8 types: **+90 pts**
5. **Finish & Submit:** Click **Stop** when your city is optimized (or let the timer expire), enter your name, and lock your spot on the Global Leaderboard!

---

## 🧰 Built With

- **HTML5 & Vanilla JavaScript (ES6+)**: Zero framework overhead, ultra-fast performance.
- **Vanilla CSS3**: Custom styles, responsive grid, and glassmorphic modal design.
- **Google Fonts**: [Open Sans](https://fonts.google.com/specimen/Open+Sans) typeface.
- **Supabase**: Real-time cloud storage and serverless PostgreSQL database.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
