# Six Bullets

Six Bullets is a daily planning tool inspired by the Ivy Lee method built around one constraint: six tasks at most. Each evening you plan tomorrow's board, lock it in, and work through it in order the next morning. Unfinished work carries over to the top of the next day instead of disappearing.

The app is a single HTML file with no build step, no accounts, and no reminders.

## Core loop

1. **Plan tomorrow in the evening.** Add up to six tasks on the Plan tab and reorder them.
2. **Lock in.** Locking commits the board. Any edit unlocks it until you lock it again. Fewer than six is fine; more is not.
3. **Work the board.** On the Today tab, the first unfinished task is the current priority. Claim its bounty to complete it. The card flips to show "Bounty Claimed," then moves on to the next task.
4. **Roll over.** At the day boundary (6:00 am by default), unfinished tasks move to the top of the next day, in their original order. They never push out a locked task.

## Features

### Today
- Shows the current priority, its priority badge ("Prime Target," "Second on the List," "Next in Line," or "Last Rodeo"), and the full board.
- Completing a task flips the current card to "Bounty Claimed" before the next task appears.
- Completed tasks stay in the list with a check mark and a struck-through label, with an Undo link.
- A Sort button reveals reorder arrows. Carried-over tasks stay above new ones and keep their order.
- When every task is done, a "Good work, partner" card appears with a "Set Tomorrow's Plan" button, and fireworks play once.

### Plan
- Add, reorder, and remove tasks for tomorrow. Removing a carried-over task drops it, with an Undo toast.
- Lock in tomorrow. The button is disabled until at least one task is planned.

### Settings
- **Day starts at:** Choose the hour your day begins, from 12:00 am to 9:00 am. Default is 6:00 am.
- **Export backup:** Saves all days, tasks, and drops to a JSON file dated with today's date.
- **Import backup:** Reads a backup file, shows a preview of its date range, and replaces everything on the device with it.
- **Clear all data:** Removes everything from the device. Requires typing `CLEAR`, and offers an export first.

### Onboarding
Four steps with a progress bar: a welcome, three rules, a first board (with Start today or Start tomorrow), and an optional add to home screen step. The start date is the day you choose on the first board.

## Rules

- **Limit:** Six tasks per board, never more.
- **Day boundary:** Days change at the start hour set in Settings, so late-night work counts toward the day it belongs to. The first day of a journey is not affected by the boundary.
- **Carryover:** Unfinished tasks move to the top of the next day, in order, and don't need to be planned again.
- **Overflow:** If carryovers would exceed six, the lowest carried-over tasks are dropped automatically and recorded as "Automatic."
- **No reminders:** The app never sends notifications. Planning is started by the user.

## Data and privacy

All data stays in the browser on the device where you use the app. Nothing is sent to a server. The app saves to the browser's local storage, so data is per browser and per device.

To move or keep your data, export a backup. Importing a backup replaces what is on the device. Clearing all data cannot be undone unless you have exported first.

## Design

The palette is warm, with Western accents:

- **Surfaces:** Parchment and paper tones, with a faint tiled pattern in the background.
- **Actions:** Leather brown buttons with light text, plus a deep brown sort control.
- **Priority:** Brass marks the current task and its border.
- **Informational notices:** Denim blue.
- **Completion:** Green check marks.
- **Errors:** Muted red, used only for destructive actions.

Cards use a flat, hard offset shadow, 4px corner radii, and torn-paper edges for the main lists.

## Known limitations

- **No offline support** beyond what the browser caches.
- **Single device.** Data does not sync between devices. Use export and import to move it.