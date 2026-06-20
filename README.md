# GOLDENIQ Builder Tool

**EN:** A Paper 1.21 plugin for **builder servers**. It gives fast, reliable **per-world** control over
the physics-like behaviors that get in the way of building (time, weather, physics, liquids, redstone,
mobs, fire, explosions, decay), plus quality-of-life protections (no damage, no hunger, keep inventory)
and a per-world **gamemode policy** that fixes the classic "left in Creative, rejoined in Survival" problem.

**ខ្មែរ:** កម្មវិធីបន្ថែម Minecraft (Paper 1.21) សម្រាប់ **builder server**។ វាផ្ដល់ការគ្រប់គ្រង **តាម world នីមួយៗ**
ដ៏លឿន និងអាចទុកចិត្តបាន លើយន្តការដែលរំខានដល់ការសាងសង់ (ម៉ោង, អាកាសធាតុ, physics, ទឹក, redstone, សត្វ,
ភ្លើង, ការផ្ទុះ, ការរលួយ) ព្រមទាំងមុខងារសម្រួល (មិនរបួស, មិនឃ្លាន, រក្សា items) និង **គោលការណ៍ gamemode
តាម world** ដែលដោះស្រាយបញ្ហាបុរាណ "ចាកចេញពេលនៅ Creative តែពេលចូលវិញបែរជា Survival"។

ប្រើបានតាមពាក្យបញ្ជា `/gq` ឬតាម **GUI ស្អាត** (មិនចាំបាច់ teleport ដើម្បីប្ដូរ world)។

---

## 📦 Installation / ការដំឡើង

**EN**
1. Build the jar (see *Build* below) or use a release jar.
2. Drop `goldeniq-builder-tool-<version>.jar` into your server's `plugins/` folder.
3. Restart the server. Config files are generated under `plugins/GOLDENIQ-BUILDER-TOOL/`.

**ខ្មែរ**
1. Build យក jar (មើលផ្នែក *Build* ខាងក្រោម) ឬប្រើ jar ដែលមានស្រាប់។
2. ដាក់ `goldeniq-builder-tool-<version>.jar` ចូលក្នុងថត `plugins/` របស់ server។
3. Restart server។ ឯកសារ config នឹងបង្កើតនៅ `plugins/GOLDENIQ-BUILDER-TOOL/`។

---

## 🔑 Permissions / សិទ្ធិ

| Node | Default | EN | ខ្មែរ |
|---|---|---|---|
| `goldeniq.builder.use` | op | Use the GUI and all per-world toggles | ប្រើ GUI និង toggle ទាំងអស់ |
| `goldeniq.builder.admin` | op | Gamemode policy, `/gq copy`, `/gq reload` | គោលការណ៍ gamemode, copy, reload |
| `goldeniq.builder.gamemode.bypass` | op | Ignore `FORCED + lock` gamemode | មិនជាប់ការ lock gamemode |

---

## ⌨️ Commands / បញ្ជា (detailed / លម្អិត)

> **EN:** With no `on/off` argument a toggle **flips** (toggle). Every command targets the **world you
> are standing in**. Run `/gq` with no arguments to open the GUI.
> **ខ្មែរ:** បើគ្មាន argument `on/off` ទេ វានឹង **ប្ដូរស្ថានភាព** (toggle)។ រាល់បញ្ជាសុទ្ធតែធ្វើការលើ **world ដែលអ្នកកំពុងឈរនៅ**។
> វាយ `/gq` ទទេ ដើម្បីបើក GUI។

### `/gq`
- **EN:** Opens the visual control panel (GUI) for your current world.
- **ខ្មែរ:** បើក GUI សម្រាប់ world បច្ចុប្បន្នរបស់អ្នក។

### `/gq time [on | off | <ticks>]`
- **EN:** Freezes the time of day. `on` (or no argument) locks the world at the **current** tick;
  a number like `6000` (noon) or `18000` (midnight) jumps to and holds that tick; names `noon`,
  `midnight`, `day`, `night` also work; `off` resumes the normal day/night cycle. Sleeping won't skip time.
- **ខ្មែរ:** បង្កកម៉ោង។ `on` (ឬគ្មាន argument) ចាក់សោម៉ោងបច្ចុប្បន្ន; លេខដូចជា `6000` (ថ្ងៃត្រង់) ឬ `18000` (កណ្ដាលអធ្រាត្រ)
  នឹងលោតទៅ និងរក្សាម៉ោងនោះ; ឈ្មោះ `noon`, `midnight`, `day`, `night` ក៏ប្រើបាន; `off` បន្តវដ្ដថ្ងៃ-យប់ធម្មតាឡើងវិញ។ ការគេងនឹងមិនរំលងម៉ោងទេ។

### `/gq weather [on | off]`
- **EN:** Blocks weather. When on, the sky stays clear — no rain, no thunder, and existing storms are cleared.
- **ខ្មែរ:** បិទអាកាសធាតុ។ ពេលបើក មេឃនៅតែស្រឡះ — គ្មានភ្លៀង គ្មានផ្គរ ហើយព្យុះដែលមានស្រាប់ត្រូវបានសម្អាត។

### `/gq physics [on | off]`
- **EN:** Freezes block physics. Sand, gravel and concrete powder float in mid-air; torches, flowers,
  rails and other attachments don't pop off when their support is removed.
- **ខ្មែរ:** បង្កក physics។ ខ្សាច់ ក្រួស និងម្សៅ concrete អណ្ដែតលើអាកាស; ចន្លុះ ផ្កា ផ្លូវរថភ្លើង ។ល។ មិនធ្លាក់ពេលដកគ្រឹះចេញ។

### `/gq liquid [on | off]`
- **EN:** Freezes liquids. Placed water and lava sources stay exactly where you put them and never flow.
- **ខ្មែរ:** បង្កកវត្ថុរាវ។ ប្រភពទឹក និង lava ដែលអ្នកដាក់ នៅនឹងកន្លែងដដែល មិនហូរទេ។

### `/gq redstone [on | off]`
- **EN:** Freezes redstone. Signals stay at their current value (levers/buttons won't drive anything) and
  pistons won't extend or retract — useful while wiring a build without triggering it.
- **ខ្មែរ:** បង្កក redstone។ សញ្ញានៅតម្លៃបច្ចុប្បន្ន (lever/button មិនដំណើរការអ្វីទេ) ហើយ piston មិនលូក/ដកវិញ — មានប្រយោជន៍ពេលតម្លើងសៀគ្វី។

### `/gq mobs [on | off]`
- **EN:** Mob control. Blocks **all** natural/automatic spawning (night spawns, spawners, breeding,
  raids…). Intentional spawns still work: **spawn eggs**, dispensed eggs, `/summon`, and plugin spawns.
- **ខ្មែរ:** គ្រប់គ្រងសត្វ។ បិទការកើតឯង **ទាំងអស់** (ពេលយប់, spawner, ការបង្កាត់, raid…)។ ការ spawn ដោយចេតនានៅដំណើរការ៖
  **spawn egg**, egg ពី dispenser, `/summon`, និងការ spawn ពី plugin។

### `/gq fire [on | off]`
- **EN:** Fire control. Blocks don't burn away and fire doesn't spread. You can still place fire on
  purpose with flint & steel (for decoration).
- **ខ្មែរ:** គ្រប់គ្រងភ្លើង។ block មិនឆេះបាត់ ហើយភ្លើងមិនរាលដាល។ អ្នកនៅតែដុតភ្លើងដោយចេតនាដោយ flint & steel បាន (សម្រាប់តុបតែង)។

### `/gq explosion [on | off]`
- **EN:** Explosion protection. Explosions (TNT, creepers, beds…) still show the visual/sound effect but
  **destroy no blocks**.
- **ខ្មែរ:** ការពារការផ្ទុះ។ ការផ្ទុះ (TNT, creeper, គ្រែ…) នៅបង្ហាញ effect និងសំឡេង ប៉ុន្តែ **មិនបំផ្លាញ block** ទេ។

### `/gq decay [on | off]`
- **EN:** No decay/growth. Leaves never decay, grass/vines/mushrooms don't spread, and crops/blocks
  don't grow or form — the world stays exactly as built.
- **ខ្មែរ:** គ្មានការរលួយ/ដុះ។ ស្លឹកមិនរលួយ, ស្មៅ/វល្លិ៍/ផ្សិតមិនរីក, ដំណាំ/block មិនដុះ — world នៅដដែលដូចសង់។

### `/gq nodamage [on | off]`
- **EN:** No damage. Players take no damage of any kind (fall, fire, mobs…), and your decorations
  (armor stands, item frames, paintings) are protected from being broken. Mobs stay damageable so you
  can still remove them.
- **ខ្មែរ:** គ្មានរបួស។ អ្នកលេងមិនរបួស (ធ្លាក់, ភ្លើង, សត្វ…) ហើយការតុបតែង (armor stand, item frame, គំនូរ) ត្រូវបានការពារ។
  សត្វនៅតែសម្លាប់បាន ដើម្បីអ្នកអាចលុបវាបាន។

### `/gq nohunger [on | off]`
- **EN:** No hunger. The hunger bar never drains; you can still eat to heal.
- **ខ្មែរ:** គ្មានភាពឃ្លាន។ របារឃ្លានមិនថយ; អ្នកនៅតែញ៉ាំដើម្បីព្យាបាលបាន។

### `/gq keepinv [on | off]`
- **EN:** Keep inventory. Sets the `keepInventory` gamerule for the world so you never lose your
  items/tools on death.
- **ខ្មែរ:** រក្សា inventory។ កំណត់ gamerule `keepInventory` សម្រាប់ world ដូច្នេះអ្នកមិនបាត់ items/ឧបករណ៍ពេលស្លាប់។

### `/gq clearmobs`
- **EN:** Removes all AI mobs in your world. **Keeps** armor stands, item frames, paintings, and any
  custom-named mob (so decorative entities survive).
- **ខ្មែរ:** លុបសត្វ AI ទាំងអស់ក្នុង world។ **រក្សា** armor stand, item frame, គំនូរ និងសត្វដែលមានឈ្មោះ (ដូច្នេះវត្ថុតុបតែងនៅគង់វង្ស)។

### `/gq nv`
- **EN:** Toggles permanent night vision for **yourself** — great for building in caves or interiors
  without placing light. (Session-scoped.)
- **ខ្មែរ:** បើក/បិទ night vision អចិន្ត្រៃយ៍សម្រាប់ **ខ្លួនអ្នក** — ល្អសម្រាប់សង់ក្នុងរូងភ្នំ ឬខាងក្នុង ដោយមិនចាំបាច់ដាក់ភ្លើង។

### `/gq status`
- **EN:** Prints a summary of the current world's active protections to chat.
- **ខ្មែរ:** បង្ហាញសេចក្ដីសង្ខេបនៃ protection ដែលកំពុងបើកក្នុង world បច្ចុប្បន្នទៅក្នុង chat។

### `/gq copy <fromWorld>` *(admin)*
- **EN:** Copies **all** settings from another world to your current world (fast setup for multiple
  builder worlds).
- **ខ្មែរ:** ចម្លង settings **ទាំងអស់** ពី world ផ្សេងមក world បច្ចុប្បន្ន (តម្លើងលឿនសម្រាប់ builder worlds ច្រើន)។

### `/gq gamemode remember` *(admin)*
- **EN:** Sets this world's policy to **REMEMBER**: each player's gamemode is saved per world and
  restored when they enter/join.
- **ខ្មែរ:** កំណត់គោលការណ៍ world ទៅ **REMEMBER**៖ gamemode របស់អ្នកលេងម្នាក់ៗត្រូវរក្សាតាម world ហើយ restore ពេលចូល។

### `/gq gamemode force <mode> [lock]` *(admin)*
- **EN:** Sets this world's policy to **FORCED**: pins a fixed gamemode (`survival`, `creative`,
  `adventure`, `spectator`) applied on entry/join. Add `lock` to block manual changes for players
  without the bypass permission.
- **ខ្មែរ:** កំណត់គោលការណ៍ world ទៅ **FORCED**៖ ចាក់សោ gamemode (`survival`, `creative`, `adventure`, `spectator`)
  អនុវត្តពេលចូល។ បន្ថែម `lock` ដើម្បីការពារការប្ដូរដោយដៃ សម្រាប់អ្នកលេងគ្មានសិទ្ធិ bypass។

### `/gq reload` *(admin)*
- **EN:** Reloads `config.yml` + `worlds.yml` and re-applies everything.
- **ខ្មែរ:** ផ្ទុក `config.yml` + `worlds.yml` ឡើងវិញ ហើយអនុវត្តគ្រប់យ៉ាងម្ដងទៀត។

### `/gq help`
- **EN / ខ្មែរ:** Shows the command list / បង្ហាញបញ្ជីពាក្យបញ្ជា។

> Aliases / ឈ្មោះក្រៅ: `/builder`, `/goldeniq` = `/gq`. Tab-completion is supported at every position.

---

## 🖥️ GUI Guide / មគ្គុទ្ទេសក៍ GUI

**EN**
- `/gq` opens a 6-row panel titled `GOLDENIQ - <world>`.
- Each toggle button **glows** when ON. **Left-click** to flip it — the change applies instantly and is saved.
- **Gamemode Policy** button: click to cycle REMEMBER → FORCED(SURVIVAL→CREATIVE→ADVENTURE→SPECTATOR).
- **Gamemode Lock** button (next to it): click to lock/unlock manual changes (used when FORCED).
- **Clear Mobs**, **Night Vision**, **Status** are action buttons.
- **<< Previous World** / **Next World >>** switch to the previous/next loaded world **without teleporting**. **Done** closes the menu.
- Items can't be taken out — every click is handled by the plugin.
- Everything works with **plain left-clicks** (no shift-click required), so it behaves the same for Bedrock players.

**ខ្មែរ**
- `/gq` បើកផ្ទាំង ៦ ជួរ ដែលមានចំណងជើង `GOLDENIQ - <world>`។
- ប៊ូតុង toggle នីមួយៗ **ភ្លឺ** ពេល ON។ **ចុចឆ្វេង** ដើម្បីប្ដូរ — ការផ្លាស់ប្ដូរអនុវត្តភ្លាមៗ និងត្រូវបានរក្សាទុក។
- ប៊ូតុង **Gamemode Policy**៖ ចុចដើម្បីប្ដូរវដ្ដ REMEMBER → FORCED(SURVIVAL→CREATIVE→ADVENTURE→SPECTATOR)។
- ប៊ូតុង **Gamemode Lock** (ក្បែរវា)៖ ចុចដើម្បី lock/unlock ការប្ដូរដោយដៃ (ប្រើពេល FORCED)។
- **Clear Mobs**, **Night Vision**, **Status** ជាប៊ូតុងសកម្មភាព។
- **<< Previous World** / **Next World >>** ប្ដូរទៅ world មុន/បន្ទាប់ **ដោយមិនចាំបាច់ teleport**។ **Done** បិទម៉ឺនុយ។
- មិនអាចយក items ចេញបានទេ — រាល់ការចុចត្រូវបានដោះស្រាយដោយ plugin។
- គ្រប់យ៉ាងដំណើរការដោយ **ចុចឆ្វេងធម្មតា** (មិនត្រូវការ shift-click) ដូច្នេះវាដូចគ្នាសម្រាប់អ្នកលេង Bedrock។

---

## 📱 Cross-play / Bedrock Edition

**EN:** The plugin is **Bedrock-friendly** (Geyser/Floodgate). The chest GUI is translated automatically
for Bedrock clients, all text is ASCII-only (no emoji or symbols that show as empty boxes on Bedrock),
and every GUI action uses a single left-click — no shift-click — so Bedrock builders get the same
experience as Java builders. Commands and tab-completion work for both editions.

**ខ្មែរ:** កម្មវិធីបន្ថែមនេះ **គាំទ្រអ្នកលេង Bedrock** (Geyser/Floodgate)។ GUI (chest) ត្រូវបានបកប្រែដោយស្វ័យប្រវត្តិសម្រាប់
Bedrock, អក្សរទាំងអស់ជា ASCII (គ្មាន emoji ឬសញ្ញាដែលបង្ហាញជាប្រអប់ទទេលើ Bedrock), ហើយរាល់សកម្មភាព GUI
ប្រើ​ការចុចឆ្វេងតែម្ដង — គ្មាន shift-click — ដូច្នេះអ្នកសាងសង់ Bedrock ទទួលបានបទពិសោធន៍ដូច Java។
ពាក្យបញ្ជា និង tab-completion ដំណើរការសម្រាប់ទាំងពីរ edition។

---

## 🎮 Gamemode Policy / គោលការណ៍ Gamemode

| Policy | EN | ខ្មែរ |
|---|---|---|
| **REMEMBER** *(default)* | Each player's gamemode is remembered per world and restored on join/entry. Fixes "left Creative, rejoined Survival". | gamemode អ្នកលេងម្នាក់ៗ ត្រូវចងចាំតាម world ហើយ restore ពេលចូល។ ដោះស្រាយបញ្ហា Creative→Survival។ |
| **FORCED** | Pins a fixed gamemode for the world; optional `lock` blocks manual changes for non-bypass players. | ចាក់សោ gamemode សម្រាប់ world; `lock` ការពារការប្ដូរដោយដៃ។ |

**EN:** To win the last write against world managers like Multiverse, the policy is applied **1 tick
after** join/world-change.
**ខ្មែរ:** ដើម្បីយកឈ្នះ plugin គ្រប់គ្រង world ដូចជា Multiverse គោលការណ៍ត្រូវអនុវត្ត **១ tick ក្រោយ** ការ join/ប្ដូរ world។

---

## ⚙️ Configuration / ការកំណត់

**EN:** Global options and the default toggle template live in `config.yml`. Per-world state is saved in
`worlds.yml`. Per-player remembered gamemodes are in `playerdata/<uuid>.yml`.
**ខ្មែរ:** ជម្រើសសកល និង template លំនាំដើម នៅក្នុង `config.yml`។ ស្ថានភាពតាម world នៅ `worlds.yml`។
gamemode ដែលចងចាំតាមអ្នកលេង នៅ `playerdata/<uuid>.yml`។

```yaml
debug: false
message-prefix: "&6&lGOLDENIQ &8» &r"
notify-on-join: true        # show a world's protections to builders on join
defaults:                   # template for worlds without an explicit entry
  freeze-time: false
  block-weather: false
  freeze-physics: false
  freeze-liquids: false
  freeze-redstone: false
  mob-control: false
  fire-control: false
  explosion-protection: false
  no-decay: false
  no-damage: false
  no-hunger: false
  keep-inventory: false
  gamemode:
    policy: REMEMBER          # REMEMBER or FORCED
    forced: CREATIVE          # used only when policy is FORCED
    lock: false
```

---

## 🔨 Build / ការ Build

**EN:** Requires JDK 21. Paper API and the shade plugin are already configured.
**ខ្មែរ:** ត្រូវការ JDK 21។ Paper API និង shade plugin ត្រូវបានកំណត់រួចហើយ។

```bash
mvn clean package
```

**EN:** The jar lands in `target/goldeniq-builder-tool-<version>.jar`. JUnit 5 tests run during
`package`. (No `mvn` on PATH? Use IntelliJ's bundled Maven at
`<IntelliJ>/plugins/maven/lib/maven3/bin/mvn.cmd`.)
**ខ្មែរ:** jar នឹងចេញនៅ `target/goldeniq-builder-tool-<version>.jar`។ test JUnit 5 ដំណើរការពេល `package`។
(គ្មាន `mvn` ក្នុង PATH? ប្រើ Maven ដែលភ្ជាប់មកជាមួយ IntelliJ នៅ `<IntelliJ>/plugins/maven/lib/maven3/bin/mvn.cmd`។)

---

## 🗂️ Project layout / រចនាសម្ព័ន្ធគម្រោង

- `settings/` — config & persistence (`WorldSettings`, `WorldSettingsManager`, `GamemodePolicy`, `PlayerGamemodeStore`)
- `feature/` — one service/listener per feature (hot-path listeners do an O(1) cache lookup and return early)
- `command/` — `/gq` executor + tab completer (pure parsing helpers are unit-tested)
- `gui/` — the 54-slot control panel
- `util/` — `Messages`, `Items`

**EN:** Full design: [`docs/superpowers/specs/2026-06-21-goldeniq-builder-tool-design.md`](docs/superpowers/specs/2026-06-21-goldeniq-builder-tool-design.md).
Manual QA: [`docs/QA-CHECKLIST.md`](docs/QA-CHECKLIST.md).
**ខ្មែរ:** ឯកសារ design ពេញលេញ និង QA checklist នៅក្នុងថត `docs/`។