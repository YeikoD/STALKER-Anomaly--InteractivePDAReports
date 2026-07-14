### What is Interactive PDA Reports?

An immersion mod for **S.T.A.L.K.E.R. Anomaly** that makes your character and NPCs communicate via radio through the PDA network.

- **You report looting:** When looting a corpse, your character automatically sends a message to the PDA. The text changes depending on your relationship with the dead:
  - **Friendly** (relation ≥ 400): Mourning the loss of an ally.
  - **Neutral** (between -400 and 400): Generic death report.
  - **Enemy** (≤ -400, you didn't kill them): Reporting an enemy corpse.
  - **Victim** (≤ -400, you killed them): Taunting about the kill.

- **NPCs respond:** If stalkers from the same faction as the victim are alive on the map, one of them replies via PDA after a configurable random delay. The tone matches your report (if you taunted, they respond with threats).

- **External comment:** Additionally, an NPC from a different faction may comment on the event with its own delay. The second response waits for the first one to be sent.

- **Ego Factor:** Controls what percentage of bodies actually get reported. At 100% all bodies are reported; at 50% only 1 in 2.

- **Cooldown:** Optionally enables a timer between reports to prevent spam.

- **Reward:** After a configurable number of reported bodies, you receive money from Sidorovich via PDA after a few seconds. Optionally exclude bodies you killed yourself.

- **Persistence:** The body counter and pending rewards are saved on exit and restored on load, even across level changes.

- **Available in Spanish and English.** The mod automatically uses the game's language.

### Installation

Option A — **Mod Organizer 2**: Install the `.zip` or `.7z` via the "Install a new mod from an archive" button. Enable the checkbox.

Option B — **Manual**: Extract the `gamedata` folder into your S.T.A.L.K.E.R. Anomaly root directory.

> The mod does not overwrite any native game files.

### Configuration (MCM)

If you have MCM installed, "Interactive PDA Reports" appears in the options menu. Available sliders:

| Slider | Description | Default |
|---|---|---|
| **Ego Factor** | Chance of a body being reported. 100% = always, 0% = never. | 100% |
| **Cooldown** | Enable/disable and duration of the timer between reports. | Disabled, 60s |
| **Reward** | Enable/disable payment, amount per report, bodies per payout, exclude your own kills. | Enabled, 10 rub, 5 bodies |
| **Response Probability** | Chance of an NPC from the same faction replying. | 50% |
| **External Comment Probability** | Chance of an NPC from a different faction commenting. | 30% |
| **Response Time 1 (Min/Max)** | Delay range (in deciseconds) for the first response. 30 = 3 sec. | 30-60 |
| **Response Time 2 (Min/Max)** | Delay range (in deciseconds) for the external comment. | 40-80 |

Without MCM, the mod uses the default values automatically.

### Localization and Expansion (XML)

Text files are located in `gamedata/configs/text/spa/` for Spanish and `gamedata/configs/text/eng/` for English. Edit the `st_ipreports_*.xml` and `st_pj_*.xml` files with any text editor.

#### Player Report

Files: `st_pj_amistoso.xml`, `st_pj_neutral.xml`, `st_pj_enemigo.xml`, `st_ipreports_victima.xml`.

Three `%s` in order: **victim name**, **current zone**, **victim faction**.

```xml
<string id="st_pjnews_amistoso_1">
    <text>Damn... Found my brother %s out here in %s. He was a good %s, may the Zone keep him in her glory.</text>
</string>
```

#### NPC Response (first)

File: `st_pj_respuestas.xml`.

Uses `{player}`, `{zone}`, `{victim}` placeholders (in any order, unlimited use).

```xml
<string id="st_pjnews_respuesta_victima_1">
    <text>You think you're tough, {player}? We've got our eyes on you. Your luck won't last long in {zone}, mark my words.</text>
</string>
```

#### External Comment (second response)

File: `st_ipreports_segunda_respuesta.xml`.

Uses simple `%s` in order: **victim name**, **zone**, **victim faction**.

### Mod Files

```
gamedata/
├── scripts/
│   ├── ipreports_interactive.script   # Main logic
│   └── ipreports_mcm.script           # MCM configuration
└── configs/text/
    ├── spa/                           # Spanish
    │   ├── st_ipreports.xml
    │   ├── st_ipreports_mcm.xml
    │   ├── st_ipreports_victima.xml
    │   ├── st_ipreports_segunda_respuesta.xml
    │   ├── st_pj_amistoso.xml
    │   ├── st_pj_neutral.xml
    │   ├── st_pj_enemigo.xml
    │   └── st_pj_respuestas.xml
    └── eng/                           # English
        ├── st_ipreports.xml
        ├── st_ipreports_mcm.xml
        ├── st_ipreports_victima.xml
        ├── st_ipreports_segunda_respuesta.xml
        ├── st_pj_amistoso.xml
        ├── st_pj_neutral.xml
        ├── st_pj_enemigo.xml
        └── st_pj_respuestas.xml
```
## 💬 Feedback & Suggestions (Let's Connect!)
This mod is actively maintained, and I’m always looking for ways to make the Zone even more immersive. Got an idea for a new feature, some spicy dialogue, or want to report a bug? I’m all ears! 

Feel free to reach out, share your suggestions, or follow my dev journey:
* **X (Twitter):** [@_yeikotv](https://x.com/_yeikotv) — For quick updates, modding news, and random Zone thoughts.
* **Instagram:** [@_yeikodev](https://www.instagram.com/_yeikodev/) — Where I share behind-the-scenes of my game dev projects.

Drop a follow, send a DM, and let's make this mod even better together. Good hunting, stalker! 🍂