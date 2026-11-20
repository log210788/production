# Lesson 07 Plan — Bárbara G.: JavaScript, Angular & Programming Best Practices Mock Interview
- **Interactive Study Lab:** [lesson-07-js-angular-prep.html](./lesson-07-js-angular-prep.html) ([Live on GitHub Pages](https://log210788.github.io/production/lesson-07-js-angular-prep.html))
- **Goal:** Test Bárbara's **technical interview techniques** (clarifying first, thinking aloud, explaining trade-offs, handling unknowns) alongside **JavaScript**, **Angular basics**, and **Programming Best Practices** (inspired by Diego's two hiring pillars).

---

## Facilitator Rules (For Louie — No Angular Expertise Needed!)
1. **Use the 5-Second Rule:** After asking a question, stay silent and let her think.
2. **Play Dumb on Purpose:** When she uses a buzzword (*closure*, *onPush*, *immutability*), ask: *"Can you explain how that works in plain English?"*
3. **Grade Both WHAT & HOW:**
   - **Clarify first?** Did she ask questions before jumping into code?
   - **Think aloud?** Did she narrate her reasoning instead of sitting in silence?
   - **Trade-offs?** Did she compare Option A vs. Option B?
   - **Honesty?** If unsure, did she reason from first principles instead of bluffing?

---

## 00–05 min | Setup & 30-Second Best Practices Pitch
- Ask: *"What are your programming best practices?"* (Target: under 30 seconds, hitting readability, early returns, single responsibility, naming, DRY, error handling, immutability, testability).
- Follow up by picking 1–2 of the 8 principles from Tab 1 and asking her to give a quick example.

## 05–20 min | Part 1: JavaScript Drills (Tab 2)
1. **`var` + `setTimeout` Loop:**
   - **Answer Key:** Prints `3, 3, 3` (not `0, 1, 2`) because `var` is function-scoped and the loop finishes before the 100ms timers run. Fix: change `var` to `let`.
   - **Green Flags:** Explains scope + async timing clearly.
2. **`fetchUser(id)` with `async/await`:**
   - **Answer Key:** Needs `try/catch` **AND** `if (!res.ok) throw ...` (because `fetch()` does not reject on HTTP 404/500).
   - **Green Flags:** Asks what the function should return on failure.

## 20–35 min | Part 2: Angular Basics & Code Review (Tab 3)
1. **Search Bar + User List Design:**
   - **Technique Test:** Does she ask clarifying questions *before* designing (frontend vs. backend filtering, list size, shared state)?
   - **Answer Key:** Smart parent + SearchBar (`@Output`) + UserList (`@Input`), or a Service if shared. Bonus: debouncing API calls.
2. **Code Review (`UserFeedComponent` `.subscribe()`):**
   - **Answer Key:** Unclosed RxJS subscription in `ngOnInit` can cause a **memory leak**.
   - **Fixes:** `async` pipe in template, `takeUntilDestroyed()`, `toSignal()`, or `ngOnDestroy` with `takeUntil`.

## 35–45 min | Part 3: Debrief & Scorecard
- Ask her first: *"How do you feel that went? Where did you feel most confident vs. stuck?"*
- Score 1–5 on: **Clarifying**, **Thinking Aloud**, **Technical Accuracy**, **Composure**.
