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
- 💾 **Offline & Local Fallback:** Zero external dependencies required to play! Automatically saves high scores to `localStorage` when offline or without internet access.
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

## 🚀 Getting Started

### Play Locally
No installations, Node.js, or build steps required:
1. Clone or download this repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/ecocity-builder.git
   ```
2. Double-click `index.html` to open it in any web browser!

---

## 🌐 Deploy to GitHub Pages (Free Hosting)

Deploy your own live version in under a minute:
1. Push your code to your GitHub repository.
2. In your repo, go to **Settings** &rarr; **Pages**.
3. Under **Build and deployment**, set the Source to **Deploy from a branch**.
4. Select the `main` branch and `/ (root)` folder, then click **Save**.
5. Your game is now live at: `https://<your-username>.github.io/<repo-name>/`!

---

## 🛠️ Setting Up Your Own Global Leaderboard (Supabase)

If you fork or clone this repo and want to connect your own Supabase database:

1. Create a free account at [supabase.com](https://supabase.com).
2. Create a new project.
3. Open the **SQL Editor** (`>_` icon on the left) and run:
   ```sql
   create table leaderboard (
     id uuid primary key default gen_random_uuid(),
     created_at timestamp with time zone default timezone('utc'::text, now()),
     name text not null,
     score integer not null,
     sustainability integer not null,
     happiness integer not null,
     pollution integer not null,
     budget integer not null,
     buildings jsonb,
     time_taken text
   );

   -- Enable Row Level Security (RLS)
   alter table leaderboard enable row level security;

   -- Allow anyone to read top scores
   create policy "Allow public read" on leaderboard for select using (true);

   -- Allow players to submit valid scores
   create policy "Allow public insert" on leaderboard for insert with check (
     score >= 0 and score <= 1000 and length(name) <= 25
   );
   ```
4. Copy your **Project URL** and `anon` `public` key from **Project Settings** &rarr; **API**.
5. In `index.html`, update the configuration block:
   ```javascript
   const SUPABASE_URL = 'https://YOUR_PROJECT_ID.supabase.co';
   const SUPABASE_ANON_KEY = 'YOUR_ANON_KEY';
   ```

---

## 🧰 Built With

- **HTML5 & Vanilla JavaScript (ES6+)**: Zero framework overhead, ultra-fast performance.
- **Vanilla CSS3**: Custom styles, responsive grid, and glassmorphic modal design.
- **Google Fonts**: [Open Sans](https://fonts.google.com/specimen/Open+Sans) typeface.
- **Supabase**: Real-time cloud storage and serverless PostgreSQL database.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
