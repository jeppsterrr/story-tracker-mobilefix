# 📖 Story Tracker — SillyTavern Extension

A SillyTavern extension that automatically tracks **time, date, location, weather, character positions, outfits, and recent events** in your roleplay. It uses the LLM to analyze the chat and maintain narrative consistency, reducing character amnesia between messages.

📺 [Video demo](https://youtu.be/Lx2nBumpsd0)

---

## ✨ Features

- **Scene Context Tracking** — Automatically extracts current time, date, and specific location from the narrative.
- **Day of Week** — Calculated automatically from the in-story date.
- **Temperature & Weather** — Tracks the current temperature (°C / °F) and weather conditions (clear, rainy, cloudy, snowing, stormy, foggy, etc.), with matching weather icons in the HUD.
- **City & Country / Realm (optional)** — When enabled, the LLM determines or invents a fitting city and country/realm based on the setting. For fantasy or sci-fi worlds it creates original names that match the story tone; for real-world settings it uses actual place names; for known fictional universes (Westeros, Middle-earth, etc.) it uses canonical names. A dedicated fallback prompt is fired if the main scene analysis leaves these fields empty.
- **Character Position Log** — Keeps track of every character present in the scene and their current action or posture.
- **Outfit & Held Items Integration** — When the [Inventory extension](#-compatibility) is installed, the user's currently equipped clothing and any items held by the AI character are appended to the character lines (e.g. *"sitting on the bed, wearing leather jacket, jeans, boots"*) and injected into the LLM prompt so outfits are never forgotten.
- **Recent Events Summary** — A concise LLM-generated summary of what just happened in the last few messages.
- **Context Injection** — Injects the current scene state (time, date, location, city/country, weather, character positions, outfit, held items) into the Author's Note before each generation, reducing AI amnesia.
- **HUD Widget** — A compact floating overlay that shows the current scene at a glance: time, date, day of week, location, optional city/country, weather with icon, and up to 3 character positions with their outfits.
- **Adjustable HUD** — Resize the HUD widget from 50% to 200% and place it in any of the four screen corners.
- **History Log** — Stores up to 20 past scene snapshots so you can review how the story evolved.
- **Translation Support** — Integrates with the SillyTavern Translate extension to display data in your target language while keeping original text intact for LLM prompts.
- **Character Tracker Sync** — Pushes time, date, and location data into the Character Tracker extension if it is active.
- **Auto-Update** — Triggers an LLM scene analysis automatically every N messages (configurable).

---

## 📦 Installation

1. In SillyTavern, open **Extensions → Install Extension**.
2. Paste the URL of this repository and click **Install**.

Or install manually:

```
SillyTavern/
└── public/
    └── extensions/
        └── story-tracker/
            ├── index.js
            ├── style.css
            └── manifest.json
```

Clone or copy the files into a folder named `story-tracker` inside `public/extensions/`, then reload SillyTavern.

---

## ⚙️ Settings

Open **Extensions → Story Tracker** in the SillyTavern sidebar to access settings.

| Setting | Description |
|---|---|
| **Enable Extension** | Master toggle for the entire extension. |
| **Show HUD Widget** | Show/hide the floating scene overlay. |
| **HUD Position** | Corner where the HUD appears (Bottom Right / Left, Top Right / Left). |
| **HUD Scale** | Resize the HUD widget (50–200%). |
| **Show Icon in Chat Panel** | Show/hide the 📖 button in the message input bar. |
| **Auto-update LLM Scene** | Automatically re-analyze the scene every N messages. |
| **Update Every N Messages** | How often the auto-update fires (1–20 messages). |
| **Inject Context into Prompt** | Inserts current scene info into the Author's Note before generation. |
| **Show City / Country** | When enabled, the LLM also infers or invents a city and country/realm for the current scene and displays them in the modal and HUD. |

---

## 🖥️ Interface

### Modal Window
Open by clicking the **📖 book icon** in the chat input bar or via the settings panel.

- **Current Scene tab** — Shows time, date, day of week, location, optional city/country, temperature, weather, character positions (with outfits and held items inlined), and a recent events summary.
- **History / Stats tab** — A log of past scene updates with message number, time, location, weather, and the event summary at each snapshot.
- **Update Now** button — Forces an immediate LLM scene analysis.
- **Translate** button — Toggles translation of displayed data (requires the Translate extension).

### HUD Widget
A small floating panel that shows time, date, day of week, location, optional city/country, weather with icon, and up to 3 character positions (with outfits/held items) at a glance. Click the header to collapse/expand it. Click the body to open the full modal.

---

## 🔗 Compatibility

| Extension | Integration |
|---|---|
| **Character Tracker** | Time, date, and location data are pushed automatically on each update. |
| **Inventory** | The user's equipped outfit and any items held by the AI character are shown inline in character entries and injected into the LLM prompt. Story Tracker re-renders instantly when Inventory equipment changes. |
| **Translate** | Location, city/country, weather, events, and character states can be displayed in your target language while the LLM continues to receive the original (untranslated) text. |

---

## 📋 Requirements

- SillyTavern (recent version with extension support)
- Any LLM backend connected to SillyTavern

---

## 📄 License

MIT — free to use, modify, and distribute.
