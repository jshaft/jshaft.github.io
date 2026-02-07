# HACK THE INFINITE CORRIDOR

### A Text Adventure in the Style of the Great Implementors

**Tagline:** *"You are standing in the basement of a famous university. It is pitch dark. You are likely to be expelled."*

---

## PREMISE

It is 3:47 AM, Fall 1987. You are a first-year student at the **Massachusetts Institute of Technocracy** (M.I.T. -- the other MIT). You have 72 hours before the Dean's review board decides whether to expel you for the "Incident With The Mainframe." Your only hope: retrieve the **Lost Thesis of Professor Tarnhelm**, legendary AI researcher who vanished in 1971, rumored to have solved the Halting Problem and hidden the proof somewhere on campus. If you present it at the review, even the Dean can't touch you.

Problem: the thesis is locked behind a series of absurd puzzles left by generations of hackers, buried in steam tunnels, rooftops, and labs that officially don't exist.

## WORLD MAP

```
                    [ROOF OF BLDG 54]
                          |
                    [RADIO TOWER] (locked grate)
                          |
    [GREEN BLDG       [INFINITE CORRIDOR]------[LOBBY 7]
     STAIRWELL]---/        |         \            |
         |           [BLDG 26 LAB]  [BLDG 10    [MASS AVE]
    [SUB-BASEMENT]        |         DOME]          |
         |           [AI LAB]         |        [MIKE'S PASTRY
    [STEAM TUNNELS]       |      [DOME HATCH]   TRUCK] (NPC)
         |           [TAPE VAULT]     |
    [CONVERGENCE]         |      [DOME INTERIOR]
         |           [SECRET OFFICE]
    [PNEUMATIC TUBE                |
     JUNCTION]              [TARNHELM'S LAB]
```

**16 rooms.** Feels compact but layered.

---

## ROOMS

### LOBBY 7 (start)
> You stand in the grand lobby of Building 7. Massive columns loom overhead like disapproving authority figures. The security desk is unmanned -- Frank must be on his 3 AM donut run. The INFINITE CORRIDOR stretches west. The front doors lead out to MASS AVE.

- Contains: `campus map` (partially accurate), `Frank's coffee` (cold, in styrofoam)
- Exit north: MASS AVE
- Exit west: INFINITE CORRIDOR
- Note: Frank returns after 30 turns. If you're carrying anything suspicious, he confiscates it and you lose a puzzle item. Clock pressure.

### INFINITE CORRIDOR
> A hallway so long it has its own weather patterns. Fluorescent lights buzz with the frequency of existential dread. Doors line both sides. Twice a year the sun aligns perfectly down its length -- but not tonight. Tonight there's just you, the hum, and the faint smell of solder.

- Connects to: LOBBY 7, BLDG 26 LAB, BLDG 10 DOME access, GREEN BLDG STAIRWELL
- Contains: `bulletin board` (has a torn flyer with half a combination), `vending machine`
- The vending machine accepts only tokens from 1971. (You'll find one later.)

### GREEN BUILDING STAIRWELL
> The tallest building on campus. The stairwell smells like concrete and regret. Stairs go up (to ROOF access, locked) and down (to SUB-BASEMENT). Someone has spray-painted "THE TRUTH IS DOWN" with an arrow pointing to the basement.

- Up: ROOF OF BLDG 54 (locked -- need `roof key`)
- Down: SUB-BASEMENT

### SUB-BASEMENT
> A forgotten maintenance level. Asbestos warnings paper the walls. Pipes hiss overhead. A heavy door leads to the STEAM TUNNELS. There's a workbench here with ancient tools. A flickering CRT monitor displays: `LOGIN:`

- Contains: `workbench` (has `wire cutters`, `electrical tape`), `CRT terminal`
- The terminal runs a PDP-11 login. Username/password puzzle (see PUZZLES).
- Through heavy door: STEAM TUNNELS

### STEAM TUNNELS
> Sweltering. Pipes thick as tree trunks run in every direction, hissing and clanking. The air tastes like rust and warm pennies. Painted arrows on the walls point in contradictory directions. This is where hackers have traveled for decades.

- Navigation puzzle: arrows are misleading. Correct path requires `campus map` + noticing that left-hand rule works.
- Contains: `1971 vending token` (in a crack in the wall), spray-painted hacker tags
- Leads to: SUB-BASEMENT (back), CONVERGENCE

### CONVERGENCE
> The steam tunnels open into a vaulted chamber where five massive pipes meet. The acoustics are extraordinary -- whispers carry. There's a rusted pneumatic tube terminal bolted to the wall, and a brass plaque that reads: "CONVERGENCE - EST. 1916 - WE WERE HERE FIRST"

- Contains: `pneumatic tube terminal` (needs a capsule + destination code), `brass plaque` (the date is a clue)
- Leads to: STEAM TUNNELS (back), PNEUMATIC TUBE JUNCTION (via the tube, if you solve it)

### PNEUMATIC TUBE JUNCTION
> You tumble out of a pneumatic tube into a room full of them -- dozens of brass tubes emerging from the walls and ceiling like a mechanical octopus. Labels are mostly faded. One reads "TARNHELM." A maintenance hatch leads back to the steam tunnels.

- The TARNHELM tube is jammed. Need to clear it (see PUZZLES).
- Contains: `tube capsule` (empty), faded routing labels
- Leads to: CONVERGENCE (back), TARNHELM'S LAB (via fixed tube)

### BLDG 26 LAB
> A hardware lab frozen in time. Oscilloscopes, wire-wrap boards, and the lingering ghost of a thousand soldering irons. A DEC PDP-10 sits in the corner, its disk platters still. A door in the back is labeled "AI LABORATORY - AUTHORIZED PERSONNEL ONLY" but the lock is broken.

- Contains: `PDP-10` (can be powered on -- see PUZZLES), `soldering iron`, `wire-wrap board`
- Leads to: INFINITE CORRIDOR (back), AI LAB

### AI LAB
> The legendary AI Lab. Whiteboards covered in LISP expressions line the walls. A poster of Marvin Minsky stares at you judgmentally. Filing cabinets overflow with papers. A heavy vault door in the back wall is labeled "TAPE ARCHIVE."

- Contains: `LISP manual` (has marginalia with clues), `filing cabinet` (contains `Tarnhelm personnel file`), Minsky poster
- The personnel file reveals Tarnhelm's office was in "Room NE43-XXX" (the secret office)
- Leads to: BLDG 26 LAB (back), TAPE VAULT (locked -- need to solve LISP puzzle on nearby terminal)

### TAPE VAULT
> Rows and rows of magnetic tape reels on industrial shelving. The temperature is carefully controlled. A card catalog system indexes the tapes. Most are labeled with project names: MACSYMA, CONNIVER, SHRDLU... One tape is labeled simply "T."

- Contains: `Tape T` (Tarnhelm's backup -- but it's encrypted), `card catalog`
- The card catalog reveals the decryption key is "in the place where all paths converge" (CONVERGENCE brass plaque date = key)
- Leads to: AI LAB (back)

### SECRET OFFICE (NE43-XXX)
> A tiny office, barely a closet. Tarnhelm's name is still on the door in faded vinyl letters. Inside: a desk, a chair, a blackboard with equations that seem to shimmer. A single drawer in the desk. The blackboard reads: "THE PROOF IS NOT HERE. THE PROOF IS EVERYWHERE. LOOK UP."

- Contains: `desk drawer` (locked -- combination is the other half from the bulletin board + a number from the Dome), `blackboard`
- Drawer contains: `roof key`, `handwritten note` ("To read my work, you'll need the wind and a clear signal. -T")
- Accessible from: AI LAB (hidden door behind filing cabinet -- revealed by personnel file)
- "Look up" = go to the ROOF

### BLDG 10 DOME (exterior)
> You stand on the outer ledge of the Great Dome. Cambridge sprawls below, glittering. The Charles River is a dark ribbon. Wind whips at your jacket. A hatch leads inside the dome. Someone has, impossibly, placed a full-size replica of a phone booth up here.

- Contains: `phone booth` (a classic hack! -- dial the right number and it rings the pneumatic tube junction, unjamming it), `dome hatch`
- The right number is on a sticker inside Frank's coffee cup (LOBBY 7)
- Leads to: INFINITE CORRIDOR (back down), DOME INTERIOR (via hatch)

### DOME INTERIOR
> Inside the Great Dome is cavernous, dark, and echoey. Catwalks crisscross the space. The oculus above lets in faint starlight. On one of the catwalks, someone has chalked a large number: **4217**.

- Contains: the number `4217` (half of the desk combination)
- Leads to: BLDG 10 DOME (back)

### ROOF OF BLDG 54
> The roof of the Green Building. Radio antennas bristle against the sky. The wind is fierce. An old radio transmitter sits in a weatherproof housing. From here you can see the whole campus -- and a blinking red light atop the radio tower.

- Contains: `radio transmitter` (needs power + antenna alignment)
- The transmitter can decode Tape T's contents when powered and aimed at the right frequency
- Leads to: GREEN BLDG STAIRWELL (back down), RADIO TOWER

### RADIO TOWER
> A narrow ladder leads up to a small platform with a massive antenna array. A connector port is open -- something should plug in here. The wind nearly tears you off the ladder.

- Plug in `wire-wrap board` (modified with `soldering iron` + `electrical tape`) to complete the antenna circuit
- This is the final step of the endgame sequence
- Leads to: ROOF OF BLDG 54 (back)

### MASS AVE
> Massachusetts Avenue at 4 AM. Empty except for a battered pastry truck idling at the curb. The driver leans out the window, looking bored and philosophical.

- Contains: `Mike's Pastry Truck` (NPC)
- Leads to: LOBBY 7 (back)

---

## KEY ITEMS

| Item | Found | Used For |
|------|-------|----------|
| `campus map` | Lobby 7 | Navigate steam tunnels |
| `Frank's coffee` (cup) | Lobby 7 | Phone number sticker inside cup |
| `wire cutters` | Sub-basement workbench | Cut zip-ties on pneumatic tube |
| `electrical tape` | Sub-basement workbench | Modify wire-wrap board |
| `1971 vending token` | Steam tunnels | Vending machine (gets `jolt cola`) |
| `jolt cola` | Vending machine | Give to Mike for `roof hint` / stay awake |
| `tube capsule` | Pneumatic tube junction | Send yourself to Tarnhelm's Lab |
| `LISP manual` | AI Lab | Hints for LISP puzzle |
| `Tarnhelm personnel file` | AI Lab filing cabinet | Reveals secret office location |
| `Tape T` | Tape vault | Contains the encrypted thesis |
| `roof key` | Secret office desk | Unlocks roof access |
| `handwritten note` | Secret office desk | Clue: "wind + clear signal" = roof + antenna |
| `soldering iron` | Bldg 26 Lab | Modify wire-wrap board |
| `wire-wrap board` | Bldg 26 Lab | Becomes antenna adapter (endgame) |
| `phone booth` | Dome exterior | Fixed object; dial to unjam tube |

---

## PUZZLES

### 1. The PDP-11 Login (Sub-Basement)
**Problem:** Terminal demands username and password.
**Solution:** Username: `TARNHELM`. Password: `HALTING` (hinted by premise + graffiti in tunnels that says "DOES THIS PROGRAM HALT? ASK TARNHELM").
**Reward:** Prints a partial map of the pneumatic tube routing codes, including the code for CONVERGENCE.

### 2. Steam Tunnel Navigation
**Problem:** Arrows on walls are contradictory and misleading.
**Solution:** Use `campus map` and follow left-hand rule. OR examine the arrows closely -- the ones painted in *red* (not yellow) are correct. Describe colors only if player examines closely.
**Reward:** Reach CONVERGENCE without looping.

### 3. The LISP Puzzle (AI Lab)
**Problem:** Terminal outside Tape Vault displays:
```
(defun open-door (x)
  (cond ((eq x '???) T)
        (t (print "ACCESS DENIED"))))
```
What replaces `???`?
**Solution:** `LAMBDA` -- hinted by marginalia in the LISP manual that says "the key to everything is the nameless function." Also accept `lambda`.
**Reward:** Vault door opens.

### 4. The Combination Lock (Secret Office Desk)
**Problem:** Desk drawer has a 8-digit combination lock.
**Solution:** First 4 digits from torn flyer on bulletin board: `1916` (same as Convergence plaque year). Last 4 from Dome interior: `4217`. Full combo: `19164217`.
**Reward:** `roof key` + `handwritten note`.

### 5. The Phone Booth (Dome)
**Problem:** Pneumatic tube to Tarnhelm's Lab is jammed.
**Solution:** Dial the number written on a sticker inside Frank's coffee cup (the number is `x7-3401`, campus extension format). This sends a test pulse through the pneumatic system and clears the jam.
**Reward:** Pneumatic tube to Tarnhelm's Lab now works.

### 6. The Antenna Assembly (Endgame)
**Problem:** Radio transmitter on roof needs a working antenna connection to decode Tape T.
**Solution:** Combine `wire-wrap board` + `soldering iron` + `electrical tape` (done at any workbench or in inventory if you have all three -- player types `MODIFY BOARD` or `SOLDER BOARD` or similar). Then plug modified board into antenna port on radio tower. Insert `Tape T` into transmitter. Tune to frequency hinted in Tarnhelm's note (frequency `1971` MHz, a callback).
**Reward:** THE THESIS DECODES. You win.

---

## NPC: MIKE (Mike's Pastry Truck)

A grizzled pastry truck operator who has seen *everything*. Has been parked outside MIT since 1969. Knows every hacker legend. Functions as a hint system.

**Dialogue triggers:**
- First meeting: *"You look like you're either about to do something brilliant or something stupid. With you kids it's usually both."*
- Give him `jolt cola`: *"Jolt! Haven't seen one of these since... heh. You know, there's a phone booth on the Dome. Don't ask me how it got there. But I hear if you call the right number, things... open up."*
- Ask about Tarnhelm: *"Tarnhelm? Wild man. Used to come out here at 4 AM, buy a cruller, and mutter about 'the function that names itself.' Disappeared one night. Left his whole office behind. They sealed it up in NE43-something."*
- Ask about steam tunnels: *"Left hand on the wall. Ignore the yellow arrows. Some joker from '83 painted those to mess with freshmen."*
- Ask about roof: *"You didn't hear this from me, but Building 54, top floor, there's a stairwell door. Been locked since the antenna incident. If you had the key, though..."*
- If you come back after winning: *"You actually did it, huh? Cruller's on the house."*

---

## GAME MECHANICS

### Turns & Time Pressure
- Frank returns to the security desk at **turn 30**. If carrying any item tagged `suspicious` (`wire cutters`, `soldering iron`, `Tape T`), he confiscates ONE item. Player can hide items first (stash behind column in Lobby 7).
- Dean's review is at **turn 150**. Soft limit -- game gives increasingly urgent reminders starting at turn 100.
- Not a hard death timer. If you exceed 150, you get a "bad ending" where you present yourself at the review empty-handed, but the Dean's secretary says "he's running late" giving you 30 more turns. Classic Infocom mercy.

### Inventory
- Max 7 items. Realistic-ish. You're a college kid with a backpack.
- `campus map` doesn't count (it's in your pocket).

### Death/Failure States
- **Fall off the Dome** if you `JUMP` or act recklessly on the exterior. (Respawn in Lobby 7, lose 10 turns to "climbing back inside with bruised dignity.")
- **Electrocution** if you plug in the unmodified wire-wrap board. (Respawn at roof, board is fried, must find replacement part in Bldg 26 Lab -- a spare board hidden behind the PDP-10.)
- **Caught by campus police** if you spend more than 8 turns on the Dome exterior. Lose 15 turns.
- No permanent deaths. This is comedy, not cruelty.

### Score
- 100 points total.
- 10 pts each for six puzzles = 60
- 5 pts for finding each of four secret areas (sub-basement, convergence, secret office, dome interior) = 20
- 10 pts for talking to Mike exhaustively = 10
- 10 pts for winning = 10
- Ranks: 0-20 "Freshman", 21-50 "Tooler", 51-80 "Hacker", 81-99 "Guru", 100 "Wizard of the Infinite Corridor"

---

## TONE NOTES

- **Examine everything.** Reward curiosity with flavor text. The oscilloscope should have a witty description. The Minsky poster should judge you.
- **Fourth wall:** Occasional. "You feel a strange compulsion to SAVE your progress, but this reality doesn't support that."
- **Hacker culture:** Celebrate cleverness, irreverence, the joy of figuring things out. No malice. The "hacking" is exploration, puzzle-solving, and wit.
- **Running gags:** The vending machine. Frank's coffee temperature. The number 1971.
- **Unwinnable states:** NONE. This is post-Zork design philosophy. Everything has a backup path or the item respawns. Be kind.
- **Easter eggs:**
  - `XYZZY` responds with "A hollow voice says 'Wrong game, kid.'"
  - `PLUGH` responds with "Gesundheit."
  - Typing `(cons 'hello 'world)` at any terminal outputs `(HELLO . WORLD)`.
  - Examining the Minsky poster: "His eyes seem to follow you. Not in a creepy way. More in a 'have you considered the frame problem' way."

---

## CRITICAL PATH (minimum solve)

1. Lobby 7: take `campus map`, take `Frank's coffee`, note sticker in cup
2. Infinite Corridor: read torn flyer (`1916`), go to Bldg 26 Lab
3. Bldg 26 Lab: take `soldering iron`, take `wire-wrap board`, enter AI Lab
4. AI Lab: read `LISP manual`, read `personnel file`, solve LISP puzzle (`LAMBDA`)
5. Tape Vault: take `Tape T`
6. AI Lab: find hidden door to Secret Office (from personnel file)
7. Dome Interior: note number `4217`
8. Secret Office: open desk with `19164217`, take `roof key` + `note`
9. Dome Exterior: use phone booth, dial `x7-3401` (from coffee cup)
10. Sub-basement: take `wire cutters`, take `electrical tape`
11. Steam Tunnels: navigate to Convergence
12. Convergence: take pneumatic tube to Junction
13. Junction: cut zip-ties with `wire cutters`, tube to Tarnhelm's Lab is clear
14. (Optional: visit Tarnhelm's Lab for flavor, but the thesis is on the tape)
15. Modify `wire-wrap board` with `soldering iron` + `electrical tape`
16. Green Bldg: unlock roof with `roof key`, go to Radio Tower
17. Plug modified board into antenna, insert `Tape T`, tune to `1971`
18. **WIN.** The thesis prints out. You are the Wizard of the Infinite Corridor.

---

*"Shall we play a game?" --WOPR, and also me, right now*
