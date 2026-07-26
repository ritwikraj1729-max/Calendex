# 📅 Calendex — Calendar Streak Tracker

**Build habits, track progress, and celebrate milestones — one day at a time.**

Calendex is a premium, habit-tracking web application that helps you build and maintain daily routines. Create custom challenges, mark each day as complete, and watch your streaks grow. With a beautiful glassmorphism interface, full calendar views, and powerful tracking features, Calendex turns habit-building into a motivating visual experience.

---

## ✨ Features

### 🎯 Challenge Management
- **Create Unlimited Challenges** — name your challenge (e.g., "Read Books", "Workout", "Meditate").
- **Flexible Durations** — choose from 7, 14, 21, 30, 50, 75, 100 days, or set a custom duration.
- **Edit & Delete** — modify or remove challenges as your goals evolve.
- **Reset Progress** — start fresh without losing the challenge structure.

### 📅 Full Calendar View
- **Open Calendar Grids** — every challenge displays its complete calendar without scrolling.
- **Day-by-Day Tracking** — click any day to mark it complete or incomplete.
- **Visual Status** — completed days are highlighted with a checkmark and glow effect.
- **Today Indicator** — the current day is clearly marked with a golden accent.
- **Independent Marking** — no order restrictions — mark any day in any sequence.

### 🔥 Streak & Progress
- **Current Streak** — see your active streak at a glance.
- **Longest Streak** — track your personal best for each challenge.
- **Progress Percentage** — animated progress bar shows completion rate.
- **Real-time Updates** — all stats update instantly when you mark a day.

### 🏆 Achievements & Milestones
- **Unlock Badges** — earn achievements at 7, 15, 21, 30, 50, 75, and 100 days.
- **Milestone Celebrations** — confetti bursts and toast notifications for every milestone.
- **Dedicated Achievements Section** — view all earned and locked badges.

### 📝 Daily Notes
- **Add Notes** — capture achievements, mood, or reflections on any completed day.
- **Easy Access** — double-click or shift+click a completed day to open the note popup.
- **Persistent** — notes are saved automatically with your progress.

### 📊 Statistics Dashboard
- **Total Challenges** — see how many you've created.
- **Active Challenges** — track ongoing habits.
- **Completed Challenges** — celebrate your finished goals.
- **Best Streak** — your overall highest streak across all challenges.
- **Total Days Completed** — cumulative progress across all challenges.

### 🔍 Search & Filter
- **Search Challenges** — find any challenge by name.
- **Filter by Status** — view All, Active, or Completed challenges.

### 💾 Data Management
- **Auto-save** — everything is saved to `localStorage` automatically.
- **Export Data** — backup your progress as a JSON file.
- **Import Data** — restore your data or transfer between devices.

### 🎨 Theme & UI
- **Dark / Light Mode** — toggle with one click; preference is saved.
- **Glassmorphism Design** — premium, modern aesthetic with subtle transparency and blur.
- **Floating Particles** — animated background for a polished feel.
- **Fully Responsive** — works perfectly on desktop, tablet, and mobile.

### ♿ Accessibility
- Semantic HTML
- ARIA labels
- Keyboard navigation
- Visible focus indicators
- High color contrast

---

## 🚀 Getting Started

### Installation
1. Download the project files:
   - `index.html`
   - `style.css`
   - `script.js`
2. Place them in the same folder.
3. Open `index.html` in any modern web browser (Chrome, Firefox, Safari, Edge).

No server, build tools, or dependencies required — it runs entirely client-side.

### Quick Start Guide

1. **Create a Challenge**
   - Enter a name (e.g., "Read Books").
   - Select a duration or enter a custom number of days.
   - Click "Create Challenge".

2. **Mark Days Complete**
   - Click any day cell to toggle it complete/incomplete.
   - Completed days turn purple with a checkmark.
   - Double-click or shift+click a completed day to add a note.

3. **Track Your Progress**
   - Watch your current streak, longest streak, and progress bar update in real time.
   - Celebrate milestones with confetti and toast notifications.

4. **Manage Challenges**
   - Use the reset (↺) button to clear progress.
   - Use the delete (✕) button to remove a challenge entirely.

5. **Search & Filter**
   - Type in the search box to find specific challenges.
   - Use the filter buttons to show All, Active, or Completed.

6. **Export / Import**
   - Click "Export" to download your data as JSON.
   - Click "Import" to restore from a JSON file.

---

## 🧠 How It Works

### Streak Calculation
- **Current Streak**: Counts consecutive completed days from the most recent day backward. The streak breaks when an incomplete day is encountered.
- **Longest Streak**: The maximum number of consecutive completed days achieved during the challenge's lifetime.
- Both values are calculated dynamically and update whenever a day is toggled.

### Progress Calculation
- **Completion Percentage**: `(completed_days / total_days) * 100`
- **Progress Bar**: Animated fill that reflects the percentage.
- **Stats Bar**: Shows completed/total days, current streak, and best streak.

### Achievement System
- Achievements are unlocked when a challenge's **longest streak** or **current streak** reaches a milestone (7, 15, 21, 30, 50, 75, 100 days).
- Once unlocked, the badge appears in the achievements section with a gold border and glow effect.
- Achievements are global across all challenges — earning a streak in one challenge unlocks the corresponding badge.

### Data Persistence
- All data is serialized to JSON and stored in `localStorage` under the key `streak-tracker-data`.
- On page load, the data is deserialized and restored.
- The theme preference is stored separately as `streak-tracker-theme`.

### Import / Export
- **Export**: Converts the current state to a downloadable JSON file.
- **Import**: Reads a JSON file and replaces the current state after user confirmation.

---

## 🎨 Customization

### Changing Colors
- The accent color is controlled by the `--accent` CSS variable in the `:root` selector.
- To change the primary color, modify `--accent: #6C63FF;` to your preferred color.
- The theme system automatically adapts the UI to light and dark modes.

### Modifying Achievements
- The `ACHIEVEMENTS` array in `script.js` defines all badges:
  ```javascript
  const ACHIEVEMENTS = [
      { id: '7day', label: '7 Day Warrior', icon: '🥉', days: 7 },
      // Add or modify entries
  ];
  ```

### Adjusting Calendar Grid
- The `grid-template-columns: repeat(auto-fill, minmax(46px, 1fr))` in `.calendar-grid` controls the day cell size.
- Adjust the `minmax()` values to make cells larger or smaller.

### Customizing the Background
- The floating particle background is generated by the `ParticleBackground` class in `script.js`.
- To adjust particle count, modify the `count` calculation in `_init()`.

---

## 📁 File Structure

```
calendex/
├── index.html          # Main HTML structure
├── style.css           # All styles (themes, glassmorphism, responsive)
└── script.js           # Application logic (state, rendering, streaks, achievements)
```

---

## ⌨️ Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl + N` | Focus the challenge name input |
| `Esc` | Close modals (note popup, completion modal) |
| `Ctrl + Enter` | Save a note (in the note popup) |
| `Enter` / `Space` | Toggle a day cell (when focused) |

---

## 🔧 Extending the Project

### Adding More Features
- **Cloud Sync**: Integrate with Firebase, Supabase, or a simple REST API to save data across devices.
- **Sound Effects**: Add the Web Audio API for click, milestone, and completion sounds.
- **Social Sharing**: Share challenge progress as an image or link.
- **Weekly/Monthly Summaries**: Generate reports showing weekly or monthly progress.
- **Challenge Templates**: Pre-made challenge templates (e.g., "30-Day Yoga", "100-Day Coding").

### Modifying the Code
- The code is modular with clear function names (e.g., `createChallenge()`, `toggleDay()`, `renderChallenges()`).
- To add new challenge properties, update the challenge object in `createChallenge()` and the rendering logic.
- To support new milestone days, add them to the `milestoneDays` array in `checkMilestone()`.

---

## 🛠️ Technologies Used
- **HTML5** — Semantic markup, custom data attributes.
- **CSS3** — Custom properties (variables), Flexbox/Grid, animations, glassmorphism, responsive design.
- **Vanilla JavaScript (ES6)** — All logic, state management, DOM manipulation, and data persistence.

No external libraries or frameworks — lightweight, fast, and dependency-free.

---

## 📝 License

MIT License — feel free to use, modify, and distribute for personal or commercial projects.

---

## 🙌 Credits

Created as a pure frontend project. Inspired by modern habit-tracking and productivity apps.

---

*Build habits one day at a time with Calendex.* 📅🔥
