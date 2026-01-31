# Diagnosis & Upgrade Strategy

## 1. Diagnosis
**Why most habit trackers fail:**
Most trackers (including the current version of Neko-Quest) rely on *tracking* rather than *designing*. They assume the user already has the willpower and clarity to execute. They fail because they don't account for:
1.  **Vagueness:** "Study" is not a behavior; it's a wish.
2.  **All-or-Nothing Thinking:** Missing a day breaks the "streak", leading to abandonment.
3.  **Friction Blindness:** When we fail, we ignore *why*, ensuring we fail again next time.

**Current Site Gaps:**
*   **Vague "Quests":** The todo list allows generic inputs without context (When? Where?).
*   **Vanity Metrics:** "XP Channels" are manually updated, measuring how the user *feels* rather than what they *did*.
*   **Lack of Safety Net:** There is no distinction between a "great day" and a "bare minimum day".

## 2. High-Leverage Upgrades

### Upgrade A: Constraint-Aware Habit Definition (The "When & Why")
Instead of just "Add Quest", we force a structure:
*   **Anchor/Trigger:** "When [Context]..."
*   **Behavior:** "I will [Action]..."
*   **Reason:** "To become [Identity]."
*   *Why:* Habits rely on environmental cues, not just willpower.

### Upgrade B: The "Emergency Cord" (Non-Binary Success)
*   **Concept:** Every habit must have a "Bad Day" version.
*   **Example:** Main: "Run 5k". Emergency: "Put on running shoes and step outside."
*   **Implementation:** If a user hesitates or clicks "Struggle", offer the Emergency version. It keeps the habit alive without burning out the user.
*   *Why:* Consistency > Intensity.

### Upgrade C: Friction Logging
*   **Concept:** When a user skips a habit, require a reason (e.g., "Forgot", "No Time", "Too Hard").
*   **Implementation:** "Missed" isn't a dead end; it's a data point.
*   *Why:* This data powers the "Weekly Review" to adjust habits that are too hard.

### Upgrade D: Evidence-Based Identity (Replacing Manual XP)
*   **Concept:** "Fitness" Level shouldn't be manually edited. It should grow based on completed fitness habits.
*   **Implementation:** Link habits to domains. Completing "Run 5k" automatically adds XP to "Fitness".

## 3. The Non-Obvious Feature: "The Habit Bankruptcy" (or "Review Loop")
Most apps let stale habits pile up. We will implement a **Weekly Review** that explicitly asks users to *kill* habits that have high friction rates.
*   *Feature:* If a habit is missed >3 times in a week with "No Time" as the reason, the app suggests: "Archive this? It seems not important right now."

## 4. Implementation Plan
I will refactor `index.html` to version 2 of the state.
1.  **Schema Change:** `quests` -> `habits` (with triggers, emergency versions, history).
2.  **UI Update:**
    *   Replace simple checkbox with a "Action Menu" (Complete, Emergency, Missed).
    *   Replace manual XP bars with calculated stats.
3.  **New Modal:** For adding detailed habits.
