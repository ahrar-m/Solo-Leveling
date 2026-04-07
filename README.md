# Solo Leveling: "The System" Habit Tracker 🎮

Welcome, Player.

This repository contains the source code for a gamified, standalone habit and goal tracker inspired by the anime/manhwa *Solo Leveling*. It is designed to run entirely within your web browser without the need for servers, databases, or complex installations.

## 🚀 Features

* **Standalone Operation:** The entire application (HTML, CSS, JS) is self-contained in a single `system.html` file.
* **RPG Mechanics:**
    * **Stat Goals:** Define your core attributes (e.g., Strength, Intelligence, Endurance).
    * **Daily Quests:** Assign specific, daily actionable tasks to those stats (e.g., "100 Pushups", "Read 10 pages").
    * **Quest Proficiency (Leveling):** Every individual quest has its own XP bar. Completing a quest grants 10 XP. The required XP to level up scales dynamically.
    * **Weekly Ranking System:** Your consistency across a specific Stat determines its weekly rank (E-Rank up to S-Rank). The cycle resets every Sunday. S-Rank requires maintaining an A-Rank for two consecutive weeks.
* **Dynamic Visualizations:** Features an animated Spider/Radar graph (powered by Chart.js) that visually represents your daily and historical stat balance.
* **Temporal Logging:** You can change the "Log Date" to go back in time and tick off quests you completed on previous days.
* **Data Persistence:** Your data is automatically saved locally in your browser's `localStorage`.
* **Data Management:** Easily Export (Save) and Import (Load) your progress via JSON files to switch devices or create backups. You can also extract your logs into a CSV file.
* **Responsive Design:** The UI is mobile-friendly, adjusting cleanly to different screen sizes.

## 🛠️ Installation & Usage

1.  **Download:** Download or copy the code from `Solo Leveling.html`.
2.  **Run:** Simply double-click the `Solo Lrveling.html` file to open it in any modern web browser (Chrome, Firefox, Safari, Edge).
3.  **Setup:**
    * Navigate to the **Settings** tab.
    * Define your overarching "Stat Categories" (e.g., Fitness, Coding, Language).
    * Create "Daily Quests" and assign them to those stats.
4.  **Play:**
    * Navigate to the **Dashboard**.
    * Check off your daily quests.
    * Watch your quest levels grow and your radar chart expand.

## 📁 File Structure

The project strictly adheres to a single-file architecture:

* `Solo Leveling.html`: Contains all markup, inline CSS styling, and vanilla JavaScript logic.
    * *External Dependency:* Uses the Chart.js CDN (`https://cdn.jsdelivr.net/npm/chart.js`) for rendering the radar graph.

## ⚙️ How the Logic Works

* **Storage:** The state object `{ goals: [], quests: [], logs: {} }` is serialized and saved to `localStorage` under the key `systemDataV6`.
* **XP Calculation:** A quest's level is calculated on the fly by scanning the entire historical log (`state.logs`) for completions of that specific `questId`.
* **Rank Calculation:** The system determines the current week's boundaries (Sunday to Saturday), checks completion percentages for those dates, and assigns a rank (E: 0-20%, D: 21-40%, C: 41-60%, B: 61-80%, A: 81-100%). S-Rank checks the previous week's boundaries for a sustaining A-Rank.

## ⚠️ Important Notes

* **Browser Storage:** Because this uses `localStorage`, if you clear your browser's cache/site data, your progress *will* be lost. **Always export your data as a JSON backup regularly.**
* **"Wipe Data" Button:** The Danger Zone in Settings contains a hard reset. This is permanent.

---
*"The System is merely a tool. Your will determines your limits."*
