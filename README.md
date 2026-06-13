## ⚠️ Project No Longer Maintained

This project is an activity of the past and is no longer being actively developed or maintained. 

# Solo Leveling: "The System" Habit Tracker 🎮

Welcome, Player.

This repository contains the source code for a highly gamified, standalone habit and goal tracker inspired by the anime/manhwa *Solo Leveling*. It is designed to run entirely within your web browser without the need for servers, databases, or complex installations.

## 🚀 Features

* **Standalone Operation:** The entire application (HTML, CSS, JS) is self-contained in a single `system.html` file. Just double-click and play.
* **RPG Mechanics:**
    * **Stat Goals:** Define your core attributes (e.g., Strength, Intelligence, Endurance).
    * **Daily Quests:** Assign specific, daily actionable tasks to those stats (e.g., "100 Pushups", "Read 10 pages").
    * **Quest Proficiency (Leveling):** Every individual quest has its own XP bar. Completing a quest grants 10 XP. The required XP to level up scales dynamically as you achieve higher mastery.
    * **Weekly Ranking System:** Your consistency across a specific Stat determines its weekly rank (E-Rank up to S-Rank). The calculation cycle resets every Sunday. S-Rank requires maintaining an A-Rank for two consecutive weeks.
* **Dynamic Visualizations:** Features an animated Spider/Radar graph (powered by Chart.js) that visually represents your daily and historical stat balance.
* **Advanced Control:**
    * **Custom Goal Targets:** You don't have to complete *everything*. Set custom daily requirements (e.g., "Complete any 2 of the 5 listed Strength quests to achieve 100% for the day").
    * **Temporal Awareness:** The System remembers when you created a Quest or Stat. New additions won't penalize your past completion records.
    * **Retroactive Tracking:** Option to instantly auto-complete new quests for all past logged days upon creation.
    * **Reordering:** Drag-and-drop style buttons (▲/▼) to arrange your Dashboard exactly how you want it.
* **Data Persistence & Management:**
    * Data automatically saves to your browser's local storage.
    * Export/Import your progress via JSON files to switch devices or create backups.
    * Extract your historical logs into a CSV file for your own spreadsheet analysis.
* **Responsive Design:** The custom dark-mode, neon-styled UI is mobile-friendly, adjusting cleanly to different screen sizes.

## 🛠️ Installation & Usage

1.  **Download:** Save the provided HTML code as `Solo Leveling.html`.
2.  **Run:** Double-click the `Solo Leveling.html` file to open it in any modern web browser (Chrome, Firefox, Safari, Edge).
3.  **Setup:**
    * Navigate to the **Settings** tab.
    * Define your overarching "Stat Categories" (e.g., Fitness, Coding, Language).
    * Create "Daily Quests" and assign them to those stats.
4.  **Play:**
    * Navigate to the **Dashboard**.
    * Check off your daily quests.
    * Watch your quest levels grow and your radar chart expand.

## ⚙️ How the Logic Works

* **Storage:** The state object `{ goals: [], quests: [], logs: {} }` is serialized and saved to `localStorage` under the key `systemDataV8`.
* **XP Calculation:** A quest's level is calculated on the fly by scanning the entire historical log (`state.logs`) for completions of that specific `questId`.
* **Rank Calculation:** The system determines the *previous* week's boundaries (Sunday to Saturday), checks completion percentages for those dates, and assigns your rank for the *current* week (E: 0-20%, D: 21-40%, C: 41-60%, B: 61-80%, A: 81-100%). S-Rank checks the week prior to that for a sustaining A-Rank.

## ⚠️ Important Notes

* **Browser Storage Limit:** Because this uses `localStorage`, if you clear your browser's cache/site data, your progress *will* be lost. **Always export your data as a JSON backup regularly.**
* **"Wipe Data" Button:** The Danger Zone in Settings contains a hard reset. This action requires confirmation and is permanent.

---
*"The System is merely a tool. Your will determines your limits."*
