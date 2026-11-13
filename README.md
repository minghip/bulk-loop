# Bulk Loop

A weekly training planner for the iPhone. It runs as a Home Screen web app: no App Store, no account, no server. Your plan and ticks are stored on your phone only. Open source under the MIT licence.

The whole app is one file, `index.html`. The other files give it a name and an icon on the Home Screen.

## Set it up (once, free, no laptop needed)

You can do every step in Safari on an iPad or an iPhone.

**1. Create the repository**

1. Sign in at github.com, tap **+** (top right) → **New repository**.
2. Repository name: `bulk-loop`. Visibility: **Public**. Turn **Add README** on.
3. Tap **Create repository**.

**2. Upload the files**

1. In the new repository tap **Add file** → **Upload files**.
2. Tap **choose your files** → **Choose Files**, open the unzipped `bulk-loop-upload` folder and select all six files:
   `index.html`, `manifest.webmanifest`, `icon-180.png`, `icon-512.png`, `README.md`, `LICENSE`.
3. Tap **Commit changes**.

**3. Switch on GitHub Pages**

1. In the repository open **Settings** → **Pages**.
2. Under *Build and deployment*, set **Source** to **Deploy from a branch**.
3. Set **Branch** to `main` and the folder to `/ (root)`, then tap **Save**.
4. Wait a few minutes (it can take up to ten) and reload the page. The address of the app appears at the top:
   `https://YOUR-USERNAME.github.io/bulk-loop/`

**4. Put it on the iPhone**

1. Open that address in **Safari** on the iPhone.
2. Tap **Share** → **Add to Home Screen**. Leave **Open as Web App** on, then tap **Add**.
3. From now on start it from the Home Screen icon. The icon and a Safari tab keep separate data, so plan and tick in the icon version only.

**Updating later:** upload the new `index.html` the same way (Add file → Upload files → Commit changes), wait a few minutes, then close and reopen the app. Your data stays on the phone.

## How it works

### Week

- Each day is one box: tick box, date, first block, second block, planned time.
- **Tap a coloured block** to change it, mark it done, move it to another day, swap first and second, or remove it. Tap **Free** or **+** to add one.
- **Drag a coloured block** onto another day to move it there. Drop it on a block and the two swap. Drop it on its neighbour to swap first and second (for example lunch session and evening session).
- **Tick the box** when the day is done: the whole box turns green. Tap again to untick.
- Tap the date or the time to open the day.
- The time on the right is the total for the day; each block shows its own time.

### Blocks

| Block | What it is | Colour |
| --- | --- | --- |
| Lower A · Lower B | squat day · hinge day | blue · deep blue |
| Upper A · Upper B | horizontal · vertical push and pull | purple · deep purple |
| Core+ | glutes, back and core | gold |
| Core mini · Legs mini · Back mini | short sessions of about 20 to 25 minutes | pale gold · pale blue · pale purple |
| Kondi · Yoga · Martial arts · Run | classes and cardio (rounded pill shape) | red · teal · charcoal · pink |
| Rest | planned day off | grey |

A done day is green, today has an orange ring, an unfinished past day has an amber edge.

### Day

- **Week** at the top left goes back to the week.
- Tick sets as you do them. A rest countdown starts by itself.
- Orange boxes are timed holds: tap to start the timer. For exercises done per side it beeps when it is time to change sides. Beeps follow the phone's silent switch.
- **− / +** removes or adds a set. **Swap** switches to an alternative when a machine is taken. Drag the dots to reorder.
- **Shorten…** trims the session to the time you have. **Move unticked on** sends what is left to your next session.
- **Swap order** flips the first and second block.
- Tap an exercise name for start and finish diagrams, cues and back-safety notes.

### Cheat-day quest

Finish Lower A, Upper A, Lower B and Upper B in one Monday to Sunday week and you earn a cheat day. The four boxes fill in as you finish sessions; you can also tap a box to tick or untick it by hand. Tap **Use** to put a saved cheat day on a date.

### Plan check and "Suggest a fix…"

The app follows a loop, not fixed weekdays: Lower A → Upper A → Lower B → Upper B → Core+, then again from the start. The plan check appears only when something breaks a spacing rule or a session was missed:

- two lower-body sessions on the same day or on back-to-back days
- a hard class (Kondi, Martial arts) or Legs mini the day before Lower A or Lower B, or a hard class on that day
- a hard class placed before lifting on the same day
- five lifting days in a row
- a main session earlier this week that was not finished

**Suggest a fix…** shows a preview that puts the remaining main sessions on the days ahead in loop order, moves missed sessions forward, and keeps everything you have started, every class and every rest day. Nothing changes until you tap **Apply**, and **Undo** puts the old week back.

## Your data

- Everything is saved in the browser storage of the Home Screen app on your phone. Nothing is uploaded.
- **Settings (gear icon) → Copy backup** copies your data as text. Paste it into a note. **Restore** brings it back, also on a new phone.
- Removing the Home Screen icon can remove its data, so copy a backup first.

## Tested

The build in this folder was run in Chrome's engine set up as an iPhone 13 mini (375 × 812 points, touch input) from a local server at the same `/bulk-loop/` path GitHub Pages uses: 73 automated checks covering loading, taps, touch drags, timers, the quest, missed sessions, week boundaries and reloads. It has not been run in Safari itself, so please report anything odd on the phone.

## Changing the app

`index.html` contains the styles, the script and the exercise data in plain readable form. The exercise data and the stick-figure diagrams are generated by a small Python script that is kept separately (the `bulk-loop-source` archive): edit `source/generator/data.py` or the files in `source/app/`, then run `python3 source/generator/build.py`.

## Licence

MIT. See `LICENSE`.
