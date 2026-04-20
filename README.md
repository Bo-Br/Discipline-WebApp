# Character Progression System (Local RPG Life Tracker)


## [test link](disciplinewebapp.netlify.app)


A local-first gamified productivity / RPG-style character system.  
You define a character, track progress through status bars, quests, grind tasks, and penalties.

No backend. No cloud. Everything runs locally in the browser.

---

## ⚠️ Important Note

- The app currently works in **dev mode (`npm run dev`)**
- **Build mode (`npm run build`) is broken or unstable**



## 🧠 Core Concept

You are not "tracking tasks".  
You are leveling up a character.

Everything you do affects:
- XP
- Level
- Status bars (attributes)
- Skills (formerly “Grimoire”)



## ✨ Features

### 👤 Character System
- Set character name
- View level, rank, XP
- Rank text updates dynamically (fix pending if still static)


### 📊 Status Bars (Core System)
- Create custom bars:
  - Name
  - Color
  - Max value (e.g. 0/1000 system, not percentages)
- Bars affect XP progression
- Each bar tracks:
  - Current value
  - Repeat count


### ⚔️ Progress Rules (IMPORTANT LOGIC)

- XP is **NOT manually addable anymore**
- XP only increases when a **status bar is completely filled**

When a bar is full:
- +20% of current level XP is awarded
- Bar resets to 0
- Repeat count increases by 1


### 📉 Penalty System
- Problems can reduce XP
- XP can go below current level threshold
- If XP drops below 0:
  - Level decreases
  - Minimum level is 0 (cannot go negative)

### 📌 Quest System

#### Main Quest
- Can only be created or deleted
- Cannot be completed manually
- Does NOT directly give XP

#### Side Quests
- Create / edit / delete
- Claim reward manually
- Choose affected status bar
- Configurable XP reward per quest

### Grind Tasks (Infinite Tasks)
- Repeatable tasks
- Create / delete
- Each completion grants XP or affects status bar
- Fully configurable reward system


### ⚠️ Problems System
- Create “negative events” (e.g. sleep badly)
- Each problem can:
  - Reduce XP
  - Be activated manually
- Used for dynamic penalties

### Skills (formerly “Grimoire”)
- Sidebar system
- Add custom skills
- Planned for progression expansion

### UI / Themes

Bento Grid layout system applied.

Available themes:
- Rose (currently most stable)
- Blue
- Red
- Yellow
- Green

⚠️ Known issue: only Rose theme fully renders correctly (others partially broken)


### ⚙️ Settings Menu

Includes:
- Reset system 
- System wipe 
- Export / Import (JSON-based local backup)


## 💾 Data Storage

- Fully local (json storage)
- No backend
- No cloud sync
- No external APIs

## 🧯 Known Issues

### Build System
- `npm run build` does not work reliably
- App only stable in dev mode

### XP System Bugs (partially fixed)
- Some XP calculations previously incorrect (e.g. +10 EXP → +1000 XP bug)
- XP sometimes not syncing with level properly

### UI Bugs
- Theme system incomplete (only Rose fully working)
- Sidebar skill system incomplete in some states

### Feature Bugs
- Main quest not awarding XP (by design, but confusing behavior)


## 🚧 Roadmap / Fix Priority

1. Fix `npm run build`
2. Stabilize XP calculation engine
3. Fix theme system (all colors working)
4. Repair reset / system wipe
5. Stabilize export/import
6. Finalize skill system sidebar
7. Clean quest logic consistency

## 🛠 Tech Stack 

- React / Vite 
- LocalStorage / IndexedDB
- Tailwind or custom CSS (Bento layout)
- json simple backend

## 📦 Setup

```bash
npm install
npm run dev
