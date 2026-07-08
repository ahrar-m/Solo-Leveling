# Solo Leveling: "The System" Habit Tracker 🎮

Welcome, Player.

This repository contains the source code for a highly gamified, standalone habit and goal tracker inspired by the anime/manhwa *Solo Leveling*. It is designed to run entirely within your web browser without the need for servers, databases, or complex installations.

---

## 🚀 Features & Mechanics

### I. Immersive RPG Leveling & Progress
* **Stat Goals:** Define your core attributes (e.g., Strength, Intelligence, Endurance).
* **Daily Quests:** Assign specific, daily actionable tasks to those stats (e.g., "100 Pushups", "Read 10 pages").
* **Quest Proficiency (Leveling):** Every individual quest has its own XP bar. Completing a quest grants XP, and the required XP to level up scales dynamically as you achieve higher mastery.
* **Level-Up Notifications:** Reaching a new player level triggers a dramatic, screen-wide neon banner saying **[ LEVEL UP ]** alongside status card glows.
* **Visual Radar Graph:** Features an animated Spider/Radar graph (powered by Chart.js) that visually represents your daily and historical stat balance. Custom tooltips display exact completion percentages when tapped or hovered.

### II. Ranks & Daily Streaks
* **Weekly Ranking System:** Your consistency across a specific Stat determines its weekly rank (E-Rank up to S-Rank). Ranks are displayed directly on your dashboard. S-Rank and A-Rank badges pulse with interactive neon glows.
* **Streak & Combo Multipliers:** Maintaining perfect daily goal completion ignites an active **Streak Flame (🔥)** on your HUD. Staying on a streak awards scaling XP multipliers (up to 1.5x) to reward daily momentum.

### III. System Control & Customization
* **Configurable Rollover Hour:** Adjust your daily reset boundary (e.g., rolling over the day at 4:00 AM instead of midnight) in the Settings panel to fit late-night productivity schedules.
* **Custom Goal Targets:** Set custom daily requirements (e.g., "Complete any 2 of the 5 listed Strength quests to achieve 100% for the day").
* **Quest Journal Hashtags:** Add hashtags (like `#fitness` or `#coding`) to your quest notes and click them to filter and analyze your habit history.
* **Reordering:** Arrange your Dashboard exactly how you want it using simple arrangement buttons (▲/▼).

### IV. Mobile Usability & Accessibility
* **Optimized Mobile Checkboxes:** Custom checkboxes have enlarged, invisible touch targets (44x44px) to ensure comfortable, error-free taps on mobile devices.
* **Keyboard Navigation:** Fully focusable checkboxes and buttons with visible neon-blue indicators for keyboard users.

### V. Data Persistence & Automated Safety
* **Browser Persistence:** Data automatically saves to your browser's local storage.
* **Automated Safety Reminders:** A warning banner appears at the top of the interface if you have not manually exported a backup in the last 2 days.
* **Export/Import:** Easily save or load your progress via JSON files to switch devices or create backups.
* **Spreadsheet Logs:** Extract your historical logs into a CSV file for spreadsheet analysis.

---

## 🛠️ Installation & Usage

1. **Download:** Save the provided `Solo Leveling.html` file.
2. **Run:** Double-click the file to open it in any web browser on your phone, tablet, or computer.
3. **Setup:**
   * Go to the **Settings** tab.
   * Define your main "Stat Goals" (e.g., Fitness, Learning, Focus).
   * Create "Daily Quests" and assign them to those stats.
4. **Play:**
   * Check off your daily quests on the **Dashboard**.
   * Resisting "Negative Quests" (bad habits) preserves your consistency and awards XP, while failing them reduces your level points.
   * Watch your quest levels grow, your radar chart expand, and unlock higher ranks.

---

## ⚠️ Important Notes

* **Browser Cache:** Clearing your browser's history or site cache *will* erase local storage. **Always export your data as a JSON backup regularly.**
* **Wipe Data:** The Danger Zone in Settings contains a hard reset button. This action requires confirmation and is permanent.

---
*"The System is merely a tool. Your will determines your limits."*
