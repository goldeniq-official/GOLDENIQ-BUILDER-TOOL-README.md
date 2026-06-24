# GOLDENIQ Builder Tool

> An official **GOLDENIQ** product — [https://www.goldeniq.xyz/](https://www.goldeniq.xyz/)
>
> **Version 0.2.7.** Server plugin: **Paper — Minecraft 1.21.11 and newer** (JDK 21).
> Companion client mod **Hermitkh** (same version 0.2.7): **Fabric — Minecraft 26.1.2 and newer** (JDK 25 to build).
> The plugin and the mod always ship at the **same version number**; pair matching versions.

**EN:** A Paper 1.21 plugin for **builder servers**. It gives fast, reliable **per-world** control over
the physics-like behaviors that get in the way of building (time, weather, physics, liquids, redstone,
mobs, fire, explosions, decay), plus quality-of-life protections (no damage, no hunger, keep inventory)
and a per-world **gamemode policy** that fixes the classic "left in Creative, rejoined in Survival" problem.

**ខ្មែរ:** កម្មវិធីបន្ថែម Minecraft (Paper 1.21) សម្រាប់ **builder server**។ វាផ្ដល់ការគ្រប់គ្រង **តាម world នីមួយៗ**
ដ៏លឿន និងអាចទុកចិត្តបាន លើយន្តការដែលរំខានដល់ការសាងសង់ (ម៉ោង, អាកាសធាតុ, physics, ទឹក, redstone, សត្វ,
ភ្លើង, ការផ្ទុះ, ការរលួយ) ព្រមទាំងមុខងារសម្រួល (មិនរបួស, មិនឃ្លាន, រក្សា items) និង **គោលការណ៍ gamemode
តាម world** ដែលដោះស្រាយបញ្ហាបុរាណ "ចាកចេញពេលនៅ Creative តែពេលចូលវិញបែរជា Survival"។

ប្រើបានតាមពាក្យបញ្ជា `/gq` ឬតាម **GUI ស្អាត** (មិនចាំបាច់ teleport ដើម្បីប្ដូរ world)។

**EN — beyond the per-world toggles, the plugin also ships a full builder toolbox:**

- 🌍 **World Manager** — create and manage worlds from a GUI, backed by Multiverse-Core (presets,
  an advanced wizard with a live preview, and one-click teleport). See _World Manager_ below.
- 🎯 **Builder Reach** — change your arm length so you can place/break blocks from farther away.
- 💡 **Light Levels** — grab a light block at any brightness (0-15) for lighting interiors.
- 🧰 **Operator Items** — get the blocks that normally need `/give` (command blocks, barriers…).
- 🪄 **Replace & Paint-Fill wands** — `/rp` swaps one block on click; `/pf` flood-fills a whole
  connected same-type mass. Routes through WorldEdit/FAWE when present (so `//undo` works). Coral and
  other waterloggable blocks are placed **dry** — no water comes along.
- 🆔 **Show Item ID** — toggle on and the held block's **legacy numeric ID** (the same one WorldEdit/FAWE
  use: stone = `1`, grass block = `2`) shows on your action bar, updating as you switch hotbar slots.
  No more hitting a block to read its ID. Blocks with no legacy ID fall back to the namespaced key.

**ខ្មែរ — បន្ថែមលើ toggle តាម world, plugin នេះក៏មាន "ប្រអប់ឧបករណ៍" ពេញលេញសម្រាប់អ្នកសាងសង់ផងដែរ៖**

- 🌍 **World Manager** — បង្កើត និងគ្រប់គ្រង world តាមរយៈ GUI ដោយពឹងលើ Multiverse-Core (មាន preset,
  wizard កម្រិតខ្ពស់ដែលបង្ហាញលទ្ធផលជាមុន, និង teleport តែមួយចុច)។ មើលផ្នែក _World Manager_ ខាងក្រោម។
- 🎯 **Builder Reach** — ប្ដូរប្រវែងដៃ ដើម្បីដាក់/កាច់ block ពីចម្ងាយឆ្ងាយជាងធម្មតា។
- 💡 **Light Levels** — យក light block តាមកម្រិតពន្លឺ (0-15) សម្រាប់បំភ្លឺខាងក្នុងសំណង់។
- 🧰 **Operator Items** — យក block ដែលធម្មតាត្រូវការ `/give` (command block, barrier ។ល។)។
- 🪄 **Replace & Paint-Fill wands** — `/rp` ប្ដូរ block មួយពេលចុច; `/pf` បំពេញ block ប្រភេទដូចគ្នាដែលជាប់គ្នាទាំងមូល។
  ឆ្លងកាត់ WorldEdit/FAWE ពេលមាន (ដូច្នេះ `//undo` ដំណើរការ)។ Coral និង block ដែលផ្ទុកទឹកបាន ត្រូវដាក់ **ស្ងួត** — គ្មានទឹកមកជាមួយ។
- 🆔 **Show Item ID** — បើក toggle នោះ **លេខ ID legacy** (ដូចគ្នានឹង WorldEdit/FAWE៖ stone = `1`, grass block = `2`)
  នៃ block ក្នុងដៃបង្ហាញលើ action bar ហើយ update ពេលប្ដូរ hotbar slot។ លែងចាំបាច់វាយ block ដើម្បីអាន ID ទៀតហើយ។
  block ដែលគ្មាន legacy ID ត្រឡប់ទៅ namespaced key វិញ។

---

## 📦 Installation / ការដំឡើង

**EN**

1. Build the jar (see _Build_ below) or use a release jar.
2. Drop `goldeniq-builder-tool-<version>.jar` into your server's `plugins/` folder.
3. Restart the server. Config files are generated under `plugins/GOLDENIQ-BUILDER-TOOL/`.

> **Optional dependencies:** **Multiverse-Core** (for the World Manager) and **LuckPerms** (recommended
> for Build Protection exemptions). Both are _soft_ — the plugin runs fine without them; the matching
> feature simply tells you it needs them.

**ខ្មែរ**

1. Build យក jar (មើលផ្នែក _Build_ ខាងក្រោម) ឬប្រើ jar ដែលមានស្រាប់។
2. ដាក់ `goldeniq-builder-tool-<version>.jar` ចូលក្នុងថត `plugins/` របស់ server។
3. Restart server។ ឯកសារ config នឹងបង្កើតនៅ `plugins/GOLDENIQ-BUILDER-TOOL/`។

> **Dependency ជាជម្រើស៖** **Multiverse-Core** (សម្រាប់ World Manager) និង **LuckPerms** (ណែនាំសម្រាប់ការលើកលែង
> Build Protection)។ ទាំងពីរជា _soft_ — plugin ដំណើរការធម្មតាបើគ្មានវា; មុខងារពាក់ព័ន្ធគ្រាន់តែប្រាប់ថាត្រូវការវា។

---

## 🔑 Permissions / សិទ្ធិ

| Node                               | Default   | EN                                                                                                                                                                                   | ខ្មែរ                                                                               |
| ---------------------------------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------- |
| `goldeniq.builder.use`             | op        | Use the GUI and all per-world toggles; open Lights/Op-Items                                                                                                                          | ប្រើ GUI និង toggle ទាំងអស់; បើក Lights/Op-Items                                    |
| `goldeniq.builder.admin`           | op        | Gamemode policy, `/gq copy`, `/gq reload`                                                                                                                                            | គោលការណ៍ gamemode, copy, reload                                                     |
| `goldeniq.builder.gamemode.bypass` | op        | Ignore `FORCED + lock` gamemode                                                                                                                                                      | មិនជាប់ការ lock gamemode                                                            |
| `goldeniq.builder.reach`           | op        | Change your own builder reach (arm length)                                                                                                                                           | ប្ដូរ reach (ប្រវែងដៃ) របស់ខ្លួនឯង                                                  |
| `goldeniq.world.use`               | op        | Open the World Manager and teleport to worlds                                                                                                                                        | បើក World Manager និង teleport ទៅ world                                             |
| `goldeniq.world.admin`             | op        | Create, delete and edit worlds                                                                                                                                                       | បង្កើត, លុប និងកែ world                                                             |
| `goldeniq.guard.export`            | op        | May run build-export commands. **Negate in LuckPerms** to lock anyone out (even an op)                                                                                               | អនុញ្ញាតប្រើ command export build។ **Negate ក្នុង LuckPerms** ដើម្បីទប់ (សូម្បី op) |
| `goldeniq.guard.admin`             | op        | Open & manage Build Protection (toggles, exemptions)                                                                                                                                 | បើក និងគ្រប់គ្រង Build Protection                                                   |
| `goldeniq.guard.mod.bypass`        | op        | Exempt from client-mod detection/kick (channel/brand guard)                                                                                                                          | លើកលែងពីការ detect/kick mod                                                         |
| `goldeniq.guard.companion.bypass`  | **false** | Exempt from the **required-companion-mod** join gate. **OP is NOT auto-exempt** — grant explicitly (GUI Exemptions → _Companion-bypass_, or `/gq guard companionbypass <player> on`) | លើកលែងពី gate ទាមទារ mod Hermitkh។ **OP មិនលើកលែងស្វ័យប្រវត្តិ**                    |

> **EN:** The `goldeniq.guard.*` nodes are `default: op`, so an **operator works out of the box today**.
> The gate uses `hasPermission`, which fully honors LuckPerms — to lock build-export down later (so even
> an operator cannot export, or only a specific rank can), **negate or grant the node in LuckPerms**; a
> LuckPerms negation overrides the `op` default. A non-op builder without `goldeniq.guard.export` is
> always blocked, which is the everyday protection. The server console / panel is never gated.
> **ខ្មែរ:** node `goldeniq.guard.*` ជា `default: op` ដូច្នេះ **OP ដំណើរការភ្លាមៗឥឡូវនេះ**។ Gate ប្រើ
> `hasPermission` ដែលគោរព LuckPerms ពេញលេញ — ដើម្បីដាក់សោ export ពេលអនាគត (សូម្បី OP ក៏មិន export បាន ឬ
> តែ rank ជាក់លាក់ប៉ុណ្ណោះ) គ្រាន់តែ **negate ឬ grant node ក្នុង LuckPerms** (negation ឈ្នះ default:op)។
> អ្នកសាងសង់ដែលមិនមែន op ហើយគ្មាន `goldeniq.guard.export` តែងតែត្រូវបានទប់ — នេះជាការការពារប្រចាំថ្ងៃ។ Console/panel មិន gate ឡើយ។

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

- **EN:** No decay/growth. Leaves never decay, grass/vines/mushrooms don't spread, crops/blocks don't
  grow or form, and **living coral never dries out into dead coral** — so coral placed without water
  (e.g. by the `/rp` and `/pf` wands) stays alive. The world stays exactly as built.
- **ខ្មែរ:** គ្មានការរលួយ/ដុះ។ ស្លឹកមិនរលួយ, ស្មៅ/វល្លិ៍/ផ្សិតមិនរីក, ដំណាំ/block មិនដុះ, ហើយ **coral រស់មិនស្ងួតទៅជា coral ងាប់**
  — ដូច្នេះ coral ដែលដាក់ដោយគ្មានទឹក (ឧ. ដោយ wand `/rp` និង `/pf`) នៅរស់។ world នៅដដែលដូចសង់។

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

### `/gq id`

- **EN:** Toggles **Show Item ID** for **yourself**. While on, the **legacy numeric ID** of the block in
  your main hand — the same one **WorldEdit / FastAsyncWorldEdit** use (stone = `1`, grass block = `2`,
  red wool = `35:14`) — is shown on your action bar and updates the instant you switch hotbar slots; an
  empty hand shows nothing. A block with no legacy ID (most 1.13+ blocks), or a server without WE/FAWE,
  falls back to the namespaced key (e.g. `minecraft:mangrove_roots`). Alias: `/gq itemid`.
  (Session-scoped; Bedrock players see it through Geyser.)
- **ខ្មែរ:** បើក/បិទ **Show Item ID** សម្រាប់ **ខ្លួនអ្នក**។ ពេលបើក **លេខ ID legacy** នៃ block ក្នុងដៃ — ដូចគ្នានឹង
  **WorldEdit / FastAsyncWorldEdit** (stone = `1`, grass block = `2`, red wool = `35:14`) — បង្ហាញលើ action bar
  ហើយ update ភ្លាមៗពេលប្ដូរ hotbar slot; ដៃទទេមិនបង្ហាញអ្វី។ block ដែលគ្មាន legacy ID (block 1.13+ ភាគច្រើន) ឬ server
  គ្មាន WE/FAWE ត្រឡប់ទៅ namespaced key វិញ (ឧ. `minecraft:mangrove_roots`)។ ឈ្មោះក្រៅ៖ `/gq itemid`។

### `/gq reach [<number> | reset]`

- **EN:** Changes **your** builder reach (arm length) so you can place and break blocks from farther
  away. With no argument it opens the reach menu; a number sets the distance (clamped to the configured
  max, default 64); `reset` returns to vanilla. Per-player and saved. Needs `goldeniq.builder.reach`.
- **ខ្មែរ:** ប្ដូរ reach (ប្រវែងដៃ) របស់ **អ្នក** ដើម្បីដាក់ និងកាច់ block ពីចម្ងាយឆ្ងាយជាងធម្មតា។ បើគ្មាន argument វាបើកម៉ឺនុយ reach;
  លេខកំណត់ចម្ងាយ (កំណត់ត្រឹមអតិបរមាក្នុង config, លំនាំដើម 64); `reset` ត្រឡប់ទៅធម្មតាវិញ។ កំណត់តាមអ្នកលេង និងរក្សាទុក។ ត្រូវការ `goldeniq.builder.reach`។

### `/gq status`

- **EN:** Prints a summary of the current world's active protections to chat.
- **ខ្មែរ:** បង្ហាញសេចក្ដីសង្ខេបនៃ protection ដែលកំពុងបើកក្នុង world បច្ចុប្បន្នទៅក្នុង chat។

### `/gq copy <fromWorld>` _(admin)_

- **EN:** Copies **all** settings from another world to your current world (fast setup for multiple
  builder worlds).
- **ខ្មែរ:** ចម្លង settings **ទាំងអស់** ពី world ផ្សេងមក world បច្ចុប្បន្ន (តម្លើងលឿនសម្រាប់ builder worlds ច្រើន)។

### `/gq gamemode remember` _(admin)_

- **EN:** Sets this world's policy to **REMEMBER**: each player's gamemode is saved per world and
  restored when they enter/join.
- **ខ្មែរ:** កំណត់គោលការណ៍ world ទៅ **REMEMBER**៖ gamemode របស់អ្នកលេងម្នាក់ៗត្រូវរក្សាតាម world ហើយ restore ពេលចូល។

### `/gq gamemode force <mode> [lock]` _(admin)_

- **EN:** Sets this world's policy to **FORCED**: pins a fixed gamemode (`survival`, `creative`,
  `adventure`, `spectator`) applied on entry/join. Add `lock` to block manual changes for players
  without the bypass permission.
- **ខ្មែរ:** កំណត់គោលការណ៍ world ទៅ **FORCED**៖ ចាក់សោ gamemode (`survival`, `creative`, `adventure`, `spectator`)
  អនុវត្តពេលចូល។ បន្ថែម `lock` ដើម្បីការពារការប្ដូរដោយដៃ សម្រាប់អ្នកលេងគ្មានសិទ្ធិ bypass។

### `/gq reload` _(admin)_

- **EN:** Reloads `config.yml` + `worlds.yml` and re-applies everything.
- **ខ្មែរ:** ផ្ទុក `config.yml` + `worlds.yml` ឡើងវិញ ហើយអនុវត្តគ្រប់យ៉ាងម្ដងទៀត។

### `/gq guard` _(guard.admin)_

- **EN:** With no argument, opens the **Build Protection** menu. `/gq guard export [on|off]` and
  `/gq guard mods [on|off]` toggle the two guards (no argument flips). `/gq guard exempt <player>
[on|off]` grants/revokes that player's `goldeniq.guard.export` (the export exemption), and
  `/gq guard modbypass <player> [on|off]` does the same for `goldeniq.guard.mod.bypass`. Exemption
  changes are written directly to **LuckPerms** (required for that sub-command); without LuckPerms,
  grant the node with your permission plugin instead. Needs `goldeniq.guard.admin`.
- **ខ្មែរ:** បើគ្មាន argument បើកម៉ឺនុយ **Build Protection**។ `/gq guard export [on|off]` និង
  `/gq guard mods [on|off]` ប្ដូរ guard ទាំងពីរ (គ្មាន argument = ប្ដូរស្ថានភាព)។ `/gq guard exempt <player>
[on|off]` ផ្ដល់/ដក `goldeniq.guard.export` (ការលើកលែង export) ឱ្យអ្នកលេងនោះ, ហើយ `/gq guard modbypass
<player> [on|off]` ធ្វើដូចគ្នាសម្រាប់ `goldeniq.guard.mod.bypass`។ ការផ្លាស់ប្ដូរការលើកលែងសរសេរទៅ **LuckPerms**
  ផ្ទាល់ (ត្រូវការ LuckPerms សម្រាប់ sub-command នេះ); បើគ្មាន LuckPerms ផ្ដល់ node តាម permission plugin ជំនួសវិញ។
  ត្រូវការ `goldeniq.guard.admin`។

### `/gq help`

- **EN / ខ្មែរ:** Shows the command list / បង្ហាញបញ្ជីពាក្យបញ្ជា។

> Aliases / ឈ្មោះក្រៅ: `/builder`, `/goldeniq` = `/gq`. Tab-completion is supported at every position.

### `/world [create]` _(world.use / world.admin)_

- **EN:** Opens the **World Manager** (needs `goldeniq.world.use`). `/world create` jumps straight to
  the creation hub (needs `goldeniq.world.admin`). Aliases: `/worlds`, `/wm`. Requires Multiverse-Core.
  See _World Manager_ below.
- **ខ្មែរ:** បើក **World Manager** (ត្រូវការ `goldeniq.world.use`)។ `/world create` ចូលផ្ទាំងបង្កើតផ្ទាល់ (ត្រូវការ `goldeniq.world.admin`)។
  ឈ្មោះក្រៅ៖ `/worlds`, `/wm`។ ត្រូវការ Multiverse-Core។ មើលផ្នែក _World Manager_ ខាងក្រោម។

### `/light` _(alias `/lights`)_

- **EN:** Opens the **Light Levels** selector — click a level (0-15) to get a light block at that
  brightness. Perfect for lighting interiors invisibly. Needs `goldeniq.builder.use`.
- **ខ្មែរ:** បើកម៉ឺនុយ **Light Levels** — ចុចកម្រិតមួយ (0-15) ដើម្បីយក light block តាមកម្រិតពន្លឺនោះ។ ល្អសម្រាប់បំភ្លឺខាងក្នុង
  ដោយមើលមិនឃើញ light block។ ត្រូវការ `goldeniq.builder.use`។

### `/items` _(aliases `/opitems`, `/item`, `/opitem`)_

- **EN:** Opens the **Operator Items** menu — click to receive one of the blocks that normally need
  `/give` (command blocks, barriers, structure/jigsaw blocks, light, etc.). Needs `goldeniq.builder.use`.
- **ខ្មែរ:** បើកម៉ឺនុយ **Operator Items** — ចុចដើម្បីទទួល block ដែលធម្មតាត្រូវការ `/give` (command block, barrier,
  structure/jigsaw block, light ។ល។)។ ត្រូវការ `goldeniq.builder.use`។

### `/rp` _(alias `/replace`)_ &nbsp;·&nbsp; `/pf` _(alias `/paintfill`)_

- **EN:** Arm the block in your hand as a **replace wand**. Hold a block, run the command, then
  right-click (Bedrock: tap) a block to swap it — `/rp` replaces the **single** block you click, `/pf`
  flood-fills the **whole connected mass of the same type** (a 3D paint bucket). Drop the wand to disarm.
  **Creative-only**, and the held block is never consumed. When **WorldEdit / FastAsyncWorldEdit** is
  installed the edits route through it, so `//undo` / `//redo` work and large `/pf` fills run async.
  Coral and other waterloggable blocks are placed **dry** — the water never comes along (pair with
  `/gq decay` to keep living coral alive). `/pf`'s fill size is capped by `rp.flood-max-blocks` in config.
- **ខ្មែរ:** កំណត់ block ក្នុងដៃជា **wand ប្ដូរ block**។ កាន់ block, វាយ command, រួចចុចស្ដាំ (Bedrock: tap) លើ block
  ដើម្បីប្ដូរ — `/rp` ប្ដូរ block **តែមួយ** ដែលអ្នកចុច, `/pf` បំពេញ **block ប្រភេទដូចគ្នាដែលជាប់គ្នាទាំងមូល** (ដូច paint bucket 3D)។
  ទម្លាក់ wand ដើម្បីបិទ។ **Creative ប៉ុណ្ណោះ**, ហើយ block ក្នុងដៃមិនអស់ឡើយ។ ពេលមាន **WorldEdit / FastAsyncWorldEdit**
  ការកែឆ្លងកាត់វា ដូច្នេះ `//undo` / `//redo` ដំណើរការ ហើយ `/pf` ធំ run async។ Coral និង block ផ្ទុកទឹក ត្រូវដាក់ **ស្ងួត** —
  គ្មានទឹកមកជាមួយ (ផ្គូផ្គង `/gq decay` ដើម្បីឱ្យ coral រស់នៅរស់)។ ទំហំបំពេញ `/pf` កំណត់ត្រឹម `rp.flood-max-blocks` ក្នុង config។

---

## 🌍 World Manager / កម្មវិធីគ្រប់គ្រង World

**EN:** A GUI for creating and managing worlds without touching `/mv` commands or config files. It is
powered by **Multiverse-Core** (soft dependency) — if Multiverse is not installed, the World Manager
simply tells you it is required and everything else keeps working. Open it from `/world` or the
**World Manager** button on the `/gq` panel.

- **Create — Presets:** one click + a name gives you a ready-made world: _Flat Creative_, _Void_,
  _Normal Survival_, _Nether_, _The End_.
- **Create — Advanced wizard:** a single screen with a **live preview** at the top that updates as you
  change each option — environment (Normal/Nether/The End), world type (Normal/Flat/Large Biomes/
  Amplified), seed, generate-structures, difficulty, generator, alias, icon, gamemode, and a reserved
  _Private_ flag. Press **Create** (it only lights up once the name is valid).
- **Manage:** every world is a clickable icon; opening one gives a detail menu with a one-click
  **Teleport** to its spawn (it loads the world first if needed).
- **Names** type through chat (Bedrock-friendly). World gamemode is enforced by the plugin's own
  gamemode policy, so it never fights Multiverse.

> Permissions: opening + teleport need `goldeniq.world.use`; creating needs `goldeniq.world.admin`.

**ខ្មែរ:** ម៉ឺនុយ GUI សម្រាប់បង្កើត និងគ្រប់គ្រង world ដោយមិនចាំបាច់ប្រើពាក្យបញ្ជា `/mv` ឬកែ config ឡើយ។ វាដំណើរការ
ដោយពឹងលើ **Multiverse-Core** (soft dependency) — បើគ្មាន Multiverse ដំឡើង World Manager គ្រាន់តែប្រាប់ថា
ត្រូវការវា ហើយមុខងារផ្សេងទៀតនៅដំណើរការធម្មតា។ បើកវាពី `/world` ឬប៊ូតុង **World Manager** ក្នុងផ្ទាំង `/gq`។

- **បង្កើត — Presets៖** ចុចមួយ + វាយឈ្មោះ គឺបាន​ world ស្រេច៖ _Flat Creative_, _Void_, _Normal Survival_,
  _Nether_, _The End_។
- **បង្កើត — Advanced wizard៖** ផ្ទាំងតែមួយដែលមាន **preview បង្ហាញផ្ទាល់** នៅខាងលើ ដែលផ្លាស់ប្ដូរតាមពេលអ្នកកែ
  ជម្រើសនីមួយៗ — environment (Normal/Nether/The End), world type (Normal/Flat/Large Biomes/Amplified),
  seed, generate-structures, difficulty, generator, alias, icon, gamemode, និង flag _Private_ ដែលទុកសម្រាប់ពេលក្រោយ។
  ចុច **Create** (វាភ្លឺតែពេលឈ្មោះត្រឹមត្រូវ)។
- **គ្រប់គ្រង៖** world នីមួយៗជា icon ដែលចុចបាន; ពេលបើកវាមានម៉ឺនុយលម្អិត ព្រមទាំងប៊ូតុង **Teleport** តែមួយចុចទៅ
  spawn របស់វា (បើ world មិនទាន់ load វា load ជាមុនសិន)។
- **ឈ្មោះ** វាយតាម chat (ស្រួលសម្រាប់ Bedrock)។ gamemode របស់ world ត្រូវបានគ្រប់គ្រងដោយ gamemode policy
  របស់ plugin ខ្លួនឯង ដូច្នេះវាមិនច្បាំងជាមួយ Multiverse ឡើយ។

> សិទ្ធិ៖ ការបើក + teleport ត្រូវការ `goldeniq.world.use`; ការបង្កើតត្រូវការ `goldeniq.world.admin`។

---

## 🛡️ Build Protection / ការការពារសំណង់

**EN:** On a collaborative builder server a build is shared property. **Build Protection** stops a
builder from **exporting a build out of the server** without going through an admin. Open it from the
**Build Protection** button on the `/gq` panel (visible only to `goldeniq.guard.admin`). It has two
layers:

- **Export Guard (Tier 1 — fully closable):** intercepts WorldEdit / FastAsyncWorldEdit export
  commands _before_ they run and **cancels** them for anyone without `goldeniq.guard.export`. Blocked:
  `//schem save | share | download | load | list | delete | …`, the standalone `//download`,
  CraftScript (`/cs`, `/.s`, `.`), and `//anvil` / region-to-file — including every aliased form
  (`worldedit:`, `fawe:`, `//`, casing, extra spaces are all normalized). **Allowed:** all normal
  building commands (`//copy`, `//paste`, `//set`, `//brush`, …) and `//listchunks` — the sanctioned
  "ask an admin to export" tool (it exports nothing; the builder reports the region, the admin pulls
  the files from the panel).
- **Mod Guard (Tier 2 — honest limit, READ THIS):** on join (and on live channel registration) it
  detects and **kicks** clients that _announce themselves_ via a plugin channel (e.g. Schematica)
  unless they hold `goldeniq.guard.mod.bypass`. **Critical truth:** modern **Litematica** and
  minimaps announce **nothing** and read the world the client already legitimately receives, so **no
  server-side plugin can detect or block them — not even with anti-cheat, and spoofing makes it
  worse.** This is the client-server architecture, not a missing feature. The one blunt lever is
  `brand-policy: KICK_NON_VANILLA`, a vanilla-only-client rule that kicks any non-`vanilla` client
  brand — it catches non-spoofing modded clients but also kicks innocent Fabric/Forge users and
  Geyser/Bedrock, and a spoofed brand bypasses it (off by default). The real, airtight protection is
  the **Tier-1 export lock above plus policy** (don't expose sensitive builds to untrusted builders).
- **Companion mod (Tier 3 — strongest lever, optional):** the **Hermitkh** Fabric client mod (see the
  `Hermitkh/` project) can be made **required to join**. With `guard.companion-mod.enabled`, every Java
  player must — **during the configuration phase, before they enter the world** — send a signed
  announcement of the build-copy / schematic mods they have installed. The server verifies it (an HMAC
  keyed by `HKDF(secret, uuid+timestamp, buildId)`, **bound to the joining player's UUID** and single-use
  within a freshness window) and **rejects before entry** if a banned mod (e.g. Litematica) is present or
  no valid announcement arrives — there is **no "joined then kicked" delay**. The handshake is
  **client-initiated**, which is what lets it work **through ViaVersion** (server 1.21.11 ↔ a newer
  client): the server→client direction does not survive that version gap, so the mod announces itself
  instead of answering a server challenge. Bedrock/Floodgate are exempt (they cannot run a Fabric mod).
  Forging a clean announcement needs the shared `secret`, set in `config.yml` **and** the mod's `SECRET`
  — so this catches the vast majority, but the mod runs on the player's machine, so a skilled attacker
  can extract the secret/patch it: it raises the bar enormously, it is **not 100%**. Harden it by setting
  a long private `secret`, pinning `allowed-builds`, and obfuscating the jar. Disabled by default
  (enabling it without distributing the mod rejects every Java player). `goldeniq.guard.companion.bypass`
  exempts (OP is **not** auto-exempt).

**The server console / web panel is never gated**, so a senior admin exports freely from the panel
with zero setup. The guard nodes are `default: op`, so operators work today; access is managed
per-player through permissions (LuckPerms recommended) — grant `goldeniq.guard.export` to a trusted
builder, or **negate** it to lock down even operators when you move roles to LuckPerms. A non-op
builder without the node is always blocked. Trusted players can be granted an exemption from the
**Manage Exemptions** GUI page (or `/gq guard exempt|modbypass <player>`). Blocked export attempts go
to `guard-audit.log`, and every guard disconnection (with name, UUID, brand, reason) to
`guard-kicks.log` — the guard **never bans**, it only kicks and logs. Online admins are alerted live.

**ខ្មែរ:** នៅលើ builder server ដែលធ្វើការរួមគ្នា សំណង់គឺជាកម្មសិទ្ធិរួម។ **Build Protection** ទប់ស្កាត់អ្នកសាងសង់ពីការ
**នាំសំណង់ចេញក្រៅ server** ដោយមិនឆ្លងកាត់ admin។ បើកវាពីប៊ូតុង **Build Protection** ក្នុងផ្ទាំង `/gq`
(មើលឃើញតែអ្នកមាន `goldeniq.guard.admin`)។ វាមាន ២ ស្រទាប់៖

- **Export Guard (ស្រទាប់ ១ — បិទបាន ១០០%)៖** ស្ទាក់ command export របស់ WorldEdit / FastAsyncWorldEdit
  _មុនពេលវាដំណើរការ_ ហើយ **បោះបង់** វាសម្រាប់អ្នកដែលគ្មាន `goldeniq.guard.export`។ ត្រូវបានបិទ៖
  `//schem save | share | download | load | list | delete | …`, `//download`, CraftScript (`/cs`, `/.s`, `.`),
  និង `//anvil` / region-to-file — រួមទាំងគ្រប់ទម្រង់ alias (`worldedit:`, `fawe:`, `//`, អក្សរធំ/តូច, ដកឃ្លាលើស ត្រូវបាន
  normalize ទាំងអស់)។ **អនុញ្ញាត៖** គ្រប់ command សាងសង់ធម្មតា (`//copy`, `//paste`, `//set`, `//brush`, …)
  និង `//listchunks` — ឧបករណ៍ "សុំ admin export" ស្របច្បាប់ (វាមិន export អ្វីទេ; អ្នកសាងសង់ប្រាប់ region ហើយ admin
  ទាញ file ពី panel)។
- **Mod Guard (ស្រទាប់ ២ — ដែនកំណត់ត្រង់ៗ សូមអាន)៖** ពេលចូល (និងពេល register channel) វា detect និង **kick**
  client ដែល _ប្រកាសខ្លួនឯង_ តាម plugin channel (ឧ. Schematica) លុះត្រាមាន `goldeniq.guard.mod.bypass`។
  **ការពិតសំខាន់៖** **Litematica** ទំនើប និង minimap **មិនប្រកាសអ្វីទាំងអស់** ហើយគ្រាន់តែអាន world ដែល client ទទួល
  ស្រាប់ — ដូច្នេះ **គ្មាន plugin ខាង server ណាអាច detect ឬ block វាបានទេ សូម្បីតែ anti-cheat ក៏អត់ ហើយ spoof ធ្វើឱ្យកាន់តែពិបាក**។
  នេះជាស្ថាបត្យកម្ម client-server មិនមែនមុខងារខ្វះទេ។ ឧបករណ៍ blunt តែមួយគឺ `brand-policy: KICK_NON_VANILLA`
  (ច្បាប់ vanilla-only) ដែល kick client brand មិនមែន `vanilla` — ចាប់បានអ្នកមិន spoof តែ kick អ្នកប្រើ Fabric/Forge
  ស្លូតត្រង់ និង Geyser/Bedrock ផង ហើយ spoof brand គេចបាន (default បិទ)។ ការការពារពិតប្រាកដគឺ **Tier-1 export lock
  ខាងលើ បូកនឹង policy** (កុំឱ្យ builder មិនទុកចិត្តឃើញ build សំខាន់)។
- **Companion mod (ស្រទាប់ ៣ — ឧបករណ៍ខ្លាំងបំផុត ជាជម្រើស)៖** mod **Hermitkh** (Fabric, មើលថត `Hermitkh/`)
  អាចកំណត់ឱ្យ **ទាមទារដើម្បីចូល**។ ពេលបើក `guard.companion-mod` អ្នកលេង Java គ្រប់រូបត្រូវ — **នៅ configuration
  phase មុនពេលចូលក្នុង world** — ផ្ញើបញ្ជី mod ចម្លងសំណង់/schematic ដែលខ្លួនមាន ដែលបានចុះហត្ថលេខា។ Server ផ្ទៀង
  ផ្ទាត់ (HMAC ដោយ `HKDF(secret, uuid+timestamp, buildId)`, **ចងភ្ជាប់ UUID អ្នកលេង**, ប្រើបានតែម្ដង) ហើយ
  **បដិសេធមុនចូល** បើមាន mod ហាមឃាត់ (ឧ. Litematica) ឬគ្មាន announcement ត្រឹមត្រូវ — **គ្មានការ "ចូលរួចទើបទាត់"**។
  Handshake ជា **client-initiated** ដែលជាមូលហេតុឱ្យវាដំណើរការ **ឆ្លង ViaVersion** (server 1.21.11 ↔ client ថ្មីជាង)៖
  ទិស server→client មិនឆ្លង Via ដូច្នេះ mod ប្រកាសខ្លួនឯងជំនួសវិញ។ Bedrock/Floodgate លើកលែង (រត់ Fabric mod មិនបាន)។
  ការក្លែងបន្លំត្រូវការ `secret` រួម (កំណត់ក្នុង `config.yml` **និង** `SECRET` ក្នុង mod) — ប៉ុន្តែ mod រត់លើម៉ាស៊ីនអ្នកលេង
  ដូច្នេះអ្នកជំនាញអាចស្រង់ secret/patch វាបាន៖ វាលើករបាំងខ្ពស់ខ្លាំង ប៉ុន្តែ **មិនមែន ១០០%**។ ពង្រឹងដោយកំណត់ `secret`
  វែងឯកជន, pin `allowed-builds`, និង obfuscate jar។ Default បិទ។ `goldeniq.guard.companion.bypass` លើកលែង (OP មិនលើកលែងស្វ័យប្រវត្តិ)។

**Console / web panel មិនត្រូវបាន gate ឡើយ** ដូច្នេះ admin ជាន់ខ្ពស់ export ដោយសេរីពី panel ដោយមិនចាំបាច់រៀបចំអ្វី។
guard nodes ជា `default: op` ដូច្នេះ OP ដំណើរការឥឡូវនេះ; គ្រប់គ្រងតាមអ្នកលេងតាមរយៈ permission (ណែនាំ LuckPerms) —
grant `goldeniq.guard.export` ឱ្យ builder ដែលទុកចិត្ត ឬ **negate** វា ដើម្បីដាក់សោសូម្បី OP ពេលអ្នកប្ដូរ role ទៅ LuckPerms។
អ្នកសាងសង់ដែលមិនមែន op ហើយគ្មាន node តែងតែត្រូវបានទប់។ ការប៉ុនប៉ងដែលត្រូវបានបិទ ត្រូវកត់ទុកក្នុង audit log និងជូនដំណឹងទៅ admin ដែល online។

---

## 🖥️ GUI Guide / មគ្គុទ្ទេសក៍ GUI

**EN**

- `/gq` opens a 6-row panel titled `GOLDENIQ - <world>`.
- Each toggle button **glows** when ON. **Left-click** to flip it — the change applies instantly and is saved.
- **Gamemode Policy** button: click to cycle REMEMBER → FORCED(SURVIVAL→CREATIVE→ADVENTURE→SPECTATOR).
- **Gamemode Lock** button (next to it): click to lock/unlock manual changes (used when FORCED).
- **Clear Mobs**, **Night Vision**, **Show Item ID**, **Status** are action buttons (the bottom row is an
  evenly-spaced quad: Night Vision · Show Item ID · Clear Mobs · Close).
- **Operator Items**, **Light Levels**, **Builder Reach** and **World Manager** open their own sub-menus
  (the same as `/items`, `/light`, `/gq reach` and `/world`).
- **Build Protection** opens the export/mod guard menu — shown only to `goldeniq.guard.admin` holders.
  Inside, **Manage Exemptions** lists online players; click one to grant/revoke their export (or
  mod-bypass) exemption — written to LuckPerms. The mode button switches which exemption you edit.
- **<< Previous World** / **Next World >>** switch to the previous/next loaded world **without teleporting**. **Done** closes the menu.
- Items can't be taken out — every click is handled by the plugin.
- Everything works with **plain left-clicks** (no shift-click required), so it behaves the same for Bedrock players.

**ខ្មែរ**

- `/gq` បើកផ្ទាំង ៦ ជួរ ដែលមានចំណងជើង `GOLDENIQ - <world>`។
- ប៊ូតុង toggle នីមួយៗ **ភ្លឺ** ពេល ON។ **ចុចឆ្វេង** ដើម្បីប្ដូរ — ការផ្លាស់ប្ដូរអនុវត្តភ្លាមៗ និងត្រូវបានរក្សាទុក។
- ប៊ូតុង **Gamemode Policy**៖ ចុចដើម្បីប្ដូរវដ្ដ REMEMBER → FORCED(SURVIVAL→CREATIVE→ADVENTURE→SPECTATOR)។
- ប៊ូតុង **Gamemode Lock** (ក្បែរវា)៖ ចុចដើម្បី lock/unlock ការប្ដូរដោយដៃ (ប្រើពេល FORCED)។
- **Clear Mobs**, **Night Vision**, **Show Item ID**, **Status** ជាប៊ូតុងសកម្មភាព (ជួរក្រោមជា quad ស្មើគ្នា៖
  Night Vision · Show Item ID · Clear Mobs · Close)។
- **Operator Items**, **Light Levels**, **Builder Reach** និង **World Manager** បើកម៉ឺនុយរងរៀងៗខ្លួន
  (ដូចគ្នានឹង `/items`, `/light`, `/gq reach` និង `/world`)។
- **Build Protection** បើកម៉ឺនុយ guard (export/mod) — បង្ហាញតែអ្នកមាន `goldeniq.guard.admin`។
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

| Policy                   | EN                                                                                                                   | ខ្មែរ                                                                                            |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **REMEMBER** _(default)_ | Each player's gamemode is remembered per world and restored on join/entry. Fixes "left Creative, rejoined Survival". | gamemode អ្នកលេងម្នាក់ៗ ត្រូវចងចាំតាម world ហើយ restore ពេលចូល។ ដោះស្រាយបញ្ហា Creative→Survival។ |
| **FORCED**               | Pins a fixed gamemode for the world; optional `lock` blocks manual changes for non-bypass players.                   | ចាក់សោ gamemode សម្រាប់ world; `lock` ការពារការប្ដូរដោយដៃ។                                       |

**EN:** To win the last write against world managers like Multiverse, the policy is applied **1 tick
after** join/world-change.
**ខ្មែរ:** ដើម្បីយកឈ្នះ plugin គ្រប់គ្រង world ដូចជា Multiverse គោលការណ៍ត្រូវអនុវត្ត **១ tick ក្រោយ** ការ join/ប្ដូរ world។

---

## ⚙️ Configuration / ការកំណត់

**EN:** Global options and the default toggle template live in `config.yml`. Per-world toggle state is
in `worlds.yml`; world icons/private flags in `managed-worlds.yml`; per-player reach in `reach.yml`;
remembered gamemodes in `playerdata/<uuid>.yml`; blocked export attempts in `guard-audit.log`; and
every guard disconnection (time, name, UUID, client brand, reason — **never a ban**) in
`guard-kicks.log`. `/gq reload` re-reads `config.yml` + `worlds.yml`.
**ខ្មែរ:** ជម្រើសសកល និង template លំនាំដើម នៅ `config.yml`។ ស្ថានភាព toggle តាម world នៅ `worlds.yml`;
icon/flag private របស់ world នៅ `managed-worlds.yml`; reach តាមអ្នកលេង នៅ `reach.yml`;
gamemode ដែលចងចាំ នៅ `playerdata/<uuid>.yml`; ការប៉ុនប៉ង export/mod ដែលបិទ នៅ `guard-audit.log`។
`/gq reload` ផ្ទុក `config.yml` + `worlds.yml` ឡើងវិញ។

```yaml
debug: false
message-prefix: "&6&lGOLDENIQ &8» &r"
notify-on-join: true # show a world's protections to builders on join
defaults: # template for worlds without an explicit entry
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
    policy: REMEMBER # REMEMBER or FORCED
    forced: CREATIVE # used only when policy is FORCED
    lock: false

reach: # Builder reach (arm length), per-player
  enabled: true # master switch for the whole feature
  max-value: 64 # admin cap (vanilla hard max 64); higher requests are clamped

rp: # /rp + /pf replace wands (Creative; route through WorldEdit/FAWE when present, so //undo works)
  flood-max-blocks: 100000 # cap on a single /pf fill (0 = unlimited; only safe with FAWE installed)

guard: # Build Protection (see section above)
  export:
    enabled: true
    op-bypass: false # extra escape hatch (op already passes via default:op anyway)
    deny-message: "&cExporting builds is locked. Ask an admin to export for you."
    log: true
    custom-blocklist: [] # extra normalized command roots to block
  mods:
    enabled: true
    check-delay-ticks: 40 # delay after join before checking plugin channels
    kick-message: "&cRemove the &e%mod% &cmod, then rejoin."
    brand-policy: OFF # OFF | WARN | KICK_NON_VANILLA (strict vanilla-only; blunt+spoofable)
    blocked-channels: ["schematica", "litematica"] # only catches mods that ANNOUNCE a channel
  companion-mod: # Tier 3 — require the Hermitkh mod (see Hermitkh/). Default OFF.
    enabled: false # enabling without distributing the mod rejects every Java player
    handshake-timeout-ticks: 100 # config-phase window to wait for the announcement (~5s) before reject
    min-protocol: 4 # live wire protocol is v4 (client-initiated, configuration phase)
    secret: "CHANGE-ME" # MUST match SECRET in the Hermitkh mod; set a long random private string
    allowed-builds: [] # e.g. ["hermitkh-0.2.5"] to accept only the exact official build
    banned-mods: ["litematica", "schematica"] # matched against the suspect mods the client reports
    banned-classes:
      [
        "fi.dy.masa.litematica.Litematica",
        "com.github.lunatrius.schematica.Schematica",
      ]
    no-mod-kick-message: "&c&lBuild-Protected Server\n&fThe &eHermitkh &fcompanion mod is required to join."
    banned-mod-kick-message: "&c&lBuild-Protected Server\n&fThe &e%mod% &fmod is not allowed here."
    download-url: ""
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

- `settings/` — config & persistence (`WorldSettings`, `WorldSettingsManager`, `GamemodePolicy`, `PlayerGamemodeStore`, `ReachStore`)
- `feature/` — one service/listener per feature (hot-path listeners do an O(1) cache lookup and return early); also reach control
- `world/` — World Manager: `MultiverseBridge` (the only class touching Multiverse-Core), `WorldSpec`, `WorldPreset`, `ManagedWorldStore` and the result records
- `guard/` — Build Protection: pure `CommandNormalizer` / `ExportPolicy` / `ChannelPolicy`, the `ExportCommandGuard` / `ModGuard` listeners, `GuardPermissions` (LuckPerms + Bukkit impls), `AuditLog`
- `command/` — `/gq` executor + tab completer, plus `/light`, `/items`, `/world`, `/rp`, `/pf` (pure parsing helpers are unit-tested)
- `gui/` — the 54-slot control panel and every sub-menu (light, op-items, reach, world manager, build protection) on the shared `Guis` layout
- `util/` — `Messages`, `Items`

**EN:** Full design: [`docs/superpowers/specs/2026-06-21-goldeniq-builder-tool-design.md`](docs/superpowers/specs/2026-06-21-goldeniq-builder-tool-design.md).
Manual QA: [`docs/QA-CHECKLIST.md`](docs/QA-CHECKLIST.md).
**ខ្មែរ:** ឯកសារ design ពេញលេញ និង QA checklist នៅក្នុងថត `docs/`។

---

<div align="center">

### GOLDENIQ

**Official website — [https://www.goldeniq.xyz/](https://www.goldeniq.xyz/)**

© 2025 – 2026 GOLDENIQ (@golden-iq). **All Rights Reserved.**

</div>
