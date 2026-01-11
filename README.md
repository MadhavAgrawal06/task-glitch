# 🚀 Task Management Dashboard - SDE Assignment

This repository contains the completed **Round 1 - SDE Assignment** for **Erino**. The goal was to debug, stabilize, and deploy a React-based task management application.

## 🔗 Live Demo
**Hosted Link:** [https://madhavagrawal-taskglitch.vercel.app/]

---

## 🛠️ Bug Fixes Implemented

### 1. Bug 1: Double Fetch Issue 🔄
- **Description:** The API/data fetch simulation was running twice on page load due to redundant effects.
- **Fix:** Removed the secondary `useEffect` in `useTasks.ts` and ensured the primary loader uses a clean dependency array.
- **Outcome:** The app now fetches data exactly once on initialization.

### 2. Bug 2: Undo Snackbar State Management 🍎
- **Description:** Closing the snackbar did not reset the `lastDeletedTask` state, leading to "phantom" data recovery.
- **Fix:** Implemented `clearLastDeleted` and linked it to the Snackbar's `onClose` event in `App.tsx`.
- **Outcome:** Deleted tasks are only recoverable while the snackbar is visible.

### 3. Bug 3: Unstable Sorting (ROI Ties) 📊
- **Description:** Tasks with identical ROI and Priority reshuffled randomly on re-renders.
- **Fix:** Added a deterministic tie-breaker using alphabetical task titles in the `sortTasks` utility.
- **Outcome:** Sorting is now stable and consistent across all renders.

### 4. Bug 4: Double Dialog Opening 🪟
- **Description:** Clicking "Edit" or "Delete" would also trigger the parent row's "View Details" dialog.
- **Fix:** Applied `e.stopPropagation()` to all action button handlers in `TaskTable.tsx`.
- **Outcome:** Only the intended dialog opens for each specific action.

### 5. Bug 5: ROI Calculation & Validation 🧮
- **Description:** Calculations failed (showing "Infinity") when Time Taken was 0, with inconsistent decimal formatting.
- **Fix:** Updated `computeROI` to return 0 for zero-time inputs and enforced 2-decimal place formatting.
- **Outcome:** Dashboard metrics are accurate and display safely without breaking the UI.

---

## 🏗️ Technical Stack
- **Framework:** React with Vite
- **Language:** TypeScript
- **UI Library:** Material UI (MUI)
- **Deployment:** Vercel

---

**Submitted by:** Madhav Agrawal  
**Email:** agrawalmad00@gmail.com  
**LinkedIn:** [https://www.linkedin.com/in/madhav-agrawal-1704a0194/](https://www.linkedin.com/in/madhav-agrawal-1704a0194/)  

**Submission Date:** January 11, 2026