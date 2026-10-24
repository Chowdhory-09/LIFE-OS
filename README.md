# LifeOS — Personal Routine, Study Planner & Achievement App

LifeOS is an all-in-one personal productivity application designed for students, software engineers, and ambitious learners. It integrates routine planning, fixed time slot timetables, monthly roadmaps, Pomodoro focus sessions, task tracking, and gamified achievement rewards.

---

## 🌟 Key Features

### 1. Dashboard Overview
- **Dynamic Greetings & Live Clock**: Context-aware greetings with digital live clock and date.
- **KPI Metrics**: Real-time daily completion percentage ring, study & focus hours, current streak, and total XP / level progress.
- **Active / Next Task Countdown**: Real-time countdown to upcoming scheduled subjects or active tasks.
- **Interactive Daily Timetable**: Check off completed tasks (+XP), skip, or launch a Pomodoro focus timer directly on that task.
- **Monthly Roadmap Snapshot**: Quick glance at progress towards this month's high-level goals.

### 2. Daily Routine Builder
- **Fixed Time Slots**: Assign start and end times for University lectures, Competitive Programming, Web Development, IELTS prep, Exercise, Breaks, Sleep, or Custom categories.
- **Automatic Duration Calculation**: Visual duration calculation for every activity.
- **Conflict & Overlap Detection**: Instant visual alerts when tasks overlap, with a 1-click **Auto-Resolve Time** button.
- **Day Selector & Copy Schedule**: Seamlessly copy a Monday schedule to all weekdays, apply weekend templates, or duplicate items.
- **Flexible Ordering**: Reorder, duplicate, edit, or delete routine activities with instant updates.

### 3. Interactive Calendar & Deadlines
- Monthly grid with indicators for scheduled routine volume, task completion badges, and milestone deadlines.
- Day drawer showing agenda, times, duration, and associated roadmap milestones.

### 4. Task Management
- Filter by: **All**, **Pending**, **Completed**, **Overdue**, and **Skipped**.
- **1-Click Reschedule Overdue**: Move unfinished tasks from previous days to today with a single button.
- Quick add ad-hoc single tasks not tied to routine timetables.

### 5. Monthly Roadmap & Goal Planner
- High-level objectives (e.g., *Solve 60 CP Problems*, *Deploy Full-Stack SaaS*, *IELTS Band 8.0 Prep*).
- 4-week milestone checklists with due dates.
- Target metric counters with quick `+1` / `-1` steppers.
- Archive completed months and review past progress.
- Copy goals from the previous month to start a new month effortlessly.

### 6. Pomodoro Focus Timer & Ambient Sound Synthesizer
- Presets: **25 min Focus**, **5 min Short Break**, **15 min Long Break**, or custom durations (20m, 45m, 60m, 90m).
- Native Web Audio API ambient sound generator: **Rain 🌧️**, **40Hz Gamma Focus 🧠**, and **White Noise 💨** (100% offline, zero network dependencies).
- Awards XP on completion, tracks actual focused minutes, and triggers confetti celebrations.

### 7. Gamified Achievements & Rewards
- **XP & Level Progression**: 5 Rank tiers from *Novice Scholar* to *Grandmaster of Routine*.
- **Streak Tracker**: Multi-day streak tracker and personal best counter.
- **Badges**: Unlocked and in-progress badges (*First Step*, *Flawless Day*, *Consistency Spark*, *Deep Work Champion*, *Algorithm Knight*, etc.).
- **Personal Rewards Store**: Define custom rewards (*1 Hour Video Games*, *Specialty Boba*, *Movie Night*) and redeem earned XP guilt-free!

### 8. Analytics & Reports
- Daily completion rates chart (7-day or 30-day view).
- Subject-wise time distribution breakdown.
- Peak productivity windows analysis.
- One-click **Export CSV** and **Backup JSON**.

### 9. Notification Center & Reminders
- Lead-time reminder alerts (5m, 10m, 15m, 30m before scheduled tasks).
- In-app notification center with snooze (10m) and dismissal controls.
- Browser notification permission toggle with honest background limitation guidance.

### 10. Progressive Web App (PWA) & Offline Persistence
- Installable on Android, Windows, macOS, Linux, and iOS Safari.
- Offline-first persistence via LocalStorage / IndexedDB.
- Offline connectivity banner when disconnected.
- In-app install button and guided iOS *Add to Home Screen* modal.

### 11. Google Sign-In & Firebase Cross-Device Sync
- **Official Google Sign-In**: "Continue with Google" popup flow via Firebase Authentication.
- **Cross-Device Cloud Sync**: Synchronizes routines, tasks, monthly goals, focus logs, and XP progression across phones, tablets, and laptops.
- **First-Time Onboarding & Migration**: Guided onboarding allows new Google accounts to migrate existing local browser data or start fresh.
- **Returning User Resilience**: Automatically detects returning users, retrieves their Firestore profile and cloud history, and updates the local offline cache without data loss.
- **Strict Firestore Security Rules**: Enforces individual user data isolation under `/users/{userId}/*` collections.

---

## 🔒 Firebase Security & Architecture

Each user's private data is structured under:
```
/users/{userId}/profile/main
/users/{userId}/routines/{routineId}
/users/{userId}/tasks/{taskId}
/users/{userId}/monthlyGoals/{goalId}
/users/{userId}/focusSessions/{sessionId}
/users/{userId}/achievements/{badgeId}
/users/{userId}/settings/main
```

Security rules in `firestore.rules` verify that `request.auth.uid == userId` for all read, write, update, and delete actions, preventing any cross-user data access.

---

## 🛠️ Tech Stack

- **Framework**: React 19 with TypeScript
- **Styling**: Tailwind CSS v4 with dark mode support
- **Authentication**: Firebase Authentication (Google Auth Provider)
- **Database**: Cloud Firestore with deployed `firestore.rules`
- **Icons**: Lucide React
- **Animations & Celebrations**: Canvas Confetti
- **Audio**: Web Audio API Sound Synthesizer
- **PWA**: `vite-plugin-pwa` with custom manifest and service worker

