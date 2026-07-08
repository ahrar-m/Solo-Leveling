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



## Future Scope & Development Roadmap

### I. Visuals, UI, and User Experience
* **Mobile Optimization:** Expand touch targets, specifically for the custom checkboxes (`.quest-checkbox` and `.subquest-checkbox`). Increasing padding and utilizing a minimum touch target size of 44x44px will ensure comfortable thumb interaction on standard mobile displays like a OnePlus 8T.
* **Modal Restructuring:** Improve the visual hierarchy within `#systemModal` (especially the "Edit Quest" view) by grouping related settings into visual "cards," increasing vertical spacing, and slightly darkening input backgrounds to contrast with the main modal color.
* **Data Visualization Enhancements:** Implement custom tooltips in the Chart.js configuration to display exact completion percentages when hovering or tapping on data points, improving the legibility of dense radar charts.
* **"Juice" and Game Feel:** Introduce impactful CSS animations. Implement keyframe flashes on the XP bar during level-ups, subtle particle effects, or text color shifts (e.g., turning gold) when a stat reaches S-Rank to make progression feel visceral.
* **Accessibility (A11y) Integration:** Add `aria-label` attributes to all icon-based buttons (✎, ✗, ▲, ▼) for screen reader support, and ensure custom checkboxes are focusable via the `tab` key for keyboard navigation.

### II. Core Functionalities & RPG Mechanics
* **DOM Rendering Optimization:** Transition away from heavy `innerHTML` string concatenation for list rendering. Refactor to update specific DOM nodes or utilize `DocumentFragment` to prevent micro-stutters and loss of scroll position as the quest list scales.
* **Configurable System Reset Time:** Add a settings variable to offset the "Day" boundary (e.g., rolling over at 4:00 AM instead of 12:00 AM) to accommodate late-night productivity and ensure the system time string matches user sleep cycles.
* **Streak & Combo Mechanics:** Introduce a consecutive completion tracker. Hitting daily targets for multiple days in a row will ignite a visual "streak" flame and grant XP multipliers (e.g., 1.2x XP after 3 days), incentivizing daily momentum.
* **Advanced Filtering & Tagging:** Implement robust tagging (`#tags`) and query filtering in the Journal tab. Drawing inspiration from block-level referencing and linked knowledge management tools like Logseq, this will allow for deep-dive analysis of specific habits over time.
* **Loot & Reward Economy:** Introduce a "System Gold" currency awarded alongside XP. Establish a 'System Shop' tab where earned currency can be spent on custom, real-life rewards (e.g., '1 Hour of Action RPGs' = 500 Gold, 'Order new Bambu Lab filament' = 5000 Gold) to close the gameplay loop.
* **Automated Data Safety:** Implement a time-based check that triggers a non-intrusive reminder pop-up ("Export required. System data at risk.") if the user has not manually exported a JSON backup within a defined window (e.g., 7 days), mitigating the volatility of `localStorage`.
