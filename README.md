<div align="center">

# 🛡️ CAS Armour for RedM

### Slot-based armour, equipment, durability, set bonuses, crafting, and custom UI updates for RedM.

![RedM](https://img.shields.io/badge/RedM-Compatible-8b0000?style=for-the-badge)
![Framework](https://img.shields.io/badge/VORP%20%2F%20RSGCore-Supported-b8860b?style=for-the-badge)
![Database](https://img.shields.io/badge/oxmysql-Required-2f4f4f?style=for-the-badge)
![Status](https://img.shields.io/badge/Custom%20Updated-Cinderwake%20Build-6b3f1d?style=for-the-badge)

</div>

---

## 📌 Credits & Ownership

This resource is **not an original script by me**.  
Original credit goes to **CAS / UIforc** for creating the base CAS Armour system.

This version is an updated/customized build with fixes, layout improvements, HUD options, resolution support work, and quality-of-life changes made for server use.

> Please respect the original author and any original licensing/usage rules that came with CAS Armour. This repo exists as a customized working version, not as a claim of original ownership.

---

## 🖼️ Preview Images

> These screenshots are displayed from local repo files so they show properly on GitHub.  
> Place the images in `docs/images/` using the exact filenames shown below. GitHub can be weird with outside image hosts, because apparently even screenshots need a notarized travel permit.

<table>
  <tr>
    <td align="center" width="50%">
      <h3>View All Sets Page</h3>
      <a href="docs/images/cas-armour-sets.png">
        <img src="docs/images/cas-armour-sets.png" alt="CAS Armour View All Sets page showing armour sets, bonuses, and equipped pieces" width="420">
      </a>
      <br>
      <sub>
        Shows every armour set, what each set does, the set bonuses, and which set pieces are currently equipped.
      </sub>
    </td>
    <td align="center" width="50%">
      <h3>Armour Equipment Menu</h3>
      <a href="docs/images/cas-armour-menu.png">
        <img src="docs/images/cas-armour-menu.png" alt="CAS Armour equipment menu with armour slots and body connector lines" width="420">
      </a>
      <br>
      <sub>
        Opens with <code>U</code> or <code>/armor</code>. Allows players to equip armour items and view connector lines to the proper body parts.
      </sub>
    </td>
  </tr>
  <tr>
    <td align="center" colspan="2">
      <h3>Bottom-Right Armour HUD</h3>
      <a href="docs/images/cas-armour-hud.png">
        <img src="docs/images/cas-armour-hud.png" alt="CAS Armour bottom-right HUD showing currently equipped armour" width="520">
      </a>
      <br>
      <sub>
        Displays currently equipped armour pieces and their condition in the bottom-right of the screen. Players can hide or show this HUD with commands.
      </sub>
    </td>
  </tr>
</table>

### Image File Names

Save your three screenshots into the repo like this:

```txt
cas-armour/
├─ README.md
└─ docs/
   └─ images/
      ├─ cas-armour-sets.png   # Image 1: View All Sets page
      ├─ cas-armour-menu.png   # Image 2: Main armour menu opened with U or /armor
      └─ cas-armour-hud.png    # Image 3: Bottom-right equipped armour HUD
```

Original hosted image links for reference:

```txt
Image 1 / Sets Page: https://files.catbox.moe/yky5v9.png
Image 2 / Armour Menu: https://files.catbox.moe/9aib1q.png
Image 3 / Armour HUD:  https://files.catbox.moe/fomwsa.png
```

---

## ✨ Custom Updates in This Build

### Menu & Startup Fixes

- Fixed armour menu startup timing after server restarts.
- Improved NUI ready/ping handling so the menu opens properly.
- `U` opens the armour menu.
- `/armor` opens the armour menu.

### Resolution & UI Improvements

- Improved layout scaling for common resolutions like **1920x1080** and **2560x1440**.
- Adjusted the armour slot layout so equipment icons and connector lines stay aligned more consistently.
- Added/updated a shared UI frame system for the floating slot positions and connector lines.

### Body Connector Lines

- Updated the armour slot connector-line system so lines better match the proper body parts.
- Connector lines now use the same coordinate layout as the armour slot UI.
- Helps prevent the lines from drifting badly across different resolutions.

### Armour HUD Improvements

- Moved the equipped armour HUD to the **bottom-right** of the screen.
- Keeps the HUD away from the minimap and other common UI elements.
- HUD shows currently equipped armour pieces and condition.

### HUD Hide / Show Commands

Players can control the armour HUD with these commands:

```txt
/hidearmor
/hidearmour
/showarmor
/showarmour
/togglearmorhud
/togglearmourhud
```

The hidden/shown HUD preference is saved client-side, so players do not have to keep hiding it every time.

### Help Prompt Added

A small help message was added inside the armour menu so players know they can hide or show the armour HUD:

```txt
Armor HUD: /hidearmor or /hidearmour to hide • /showarmor or /showarmour to show
```

---

## ✅ Requirements

- `vorp_core` or `rsg-core`
- `vorp_inventory` or `rsg-inventory`
- `oxmysql`

---

## 📦 Installation

1. Import the SQL files into your database:

```txt
sql/cas_armour_equipment.sql
sql/cas_armour_items.sql
```

2. Keep the resource folder name as:

```txt
cas-armour
```

3. Add the resource to your `server.cfg`:

```cfg
ensure oxmysql
ensure vorp_core
ensure vorp_inventory
ensure cas-armour
```

4. Restart the server or resource:

```cfg
restart cas-armour
```

---

## 🎮 Player Commands

| Command | Description |
|---|---|
| `/armor` | Opens the armour equipment menu |
| `/hidearmor` | Hides the equipped armour HUD |
| `/hidearmour` | Hides the equipped armour HUD, alternate spelling |
| `/showarmor` | Shows the equipped armour HUD |
| `/showarmour` | Shows the equipped armour HUD, alternate spelling |
| `/togglearmorhud` | Toggles the equipped armour HUD on/off |
| `/togglearmourhud` | Toggles the equipped armour HUD on/off, alternate spelling |

---

## 🧩 Core Features

### Equipment System

- **10 equipment slots**:
  - Head
  - Chest
  - Vest
  - Pants
  - Boots
  - Gloves
  - Belt
  - Amulet
  - Trinket 1
  - Trinket 2
- Drag-and-drop equipment interface.
- Equip items from inventory.
- Unequip items back to inventory.
- Metadata persistence using oxmysql.

### Damage Reduction

Armour can reduce several types of damage:

- Bullet damage
- Melee damage
- Animal damage
- Fall damage
- Explosion damage
- Poison damage

Formula:

```txt
reduction% = (armorBase * ArmorBaseToReduction) + categoryResist
```

Reduction is capped by:

```txt
MaxDamageReductionPercent
```

### Durability / Wear

- Armour condition decreases when taking damage.
- Wear is based on `WearPerDamage`.
- When an armour piece reaches `0` condition, it breaks and is removed.
- Damage can wear nearby slots depending on hit location.

### Set Bonuses

- Includes multiple armour sets with tiered bonuses.
- Set bonuses activate based on equipped piece count.
- 10-piece bonuses grant unique passive effects.

---

## 🧙 Set Passive Abilities

| Set | Passive | Effect |
|---|---|---|
| Wolf | Wolf Detection Reduction | Extra NPC sense reduction |
| Bear | Bear Charge Resistance | Ragdoll immunity |
| Outlaw | Bullet Dodge Chance | Chance to negate bullet damage |
| Scholar | Enemy Detection Boost | Blips on hostile NPCs |
| Snake | Poison Aura | AoE damage to nearby NPCs |
| Night | Assassination Expertise | Bonus damage on unaware NPCs |
| Legend | Quickdraw Mastery | Stronger intimidation and deadeye recovery |

---

## 🔨 Crafting

- Blacksmith NPCs at configurable locations.
- Uses menu-based set and piece selection.
- Supports progress bar and crafting animation.
- Crafting recipes and tuning are configurable.

---

## ⚙️ Configuration

Main configuration is handled in:

```txt
shared/config.lua
```

Important areas include:

```txt
Config.Tuning
Config.WeightPenalty
Config.ArmorPieces
Config.ArmorSets
```

---

## 🔁 NUI Callbacks

| Callback | Description |
|---|---|
| `cas_armour:close` | Close the UI |
| `cas_armour:requestData` | Request equipment/inventory data |
| `cas_armour:equip` | Equip an item |
| `cas_armour:unequip` | Unequip a slot |
| `cas_armour:craft` | Craft a piece |

---

## 📤 Exports

### Client

```lua
exports['cas-armour']:GetEquipment()
exports['cas-armour']:GetStats()
exports['cas-armour']:GetActivePassives()
```

### Server

```lua
exports['cas-armour']:GetEquipment(source)
```

---

## 📝 Notes

This is a customized version of CAS Armour with server-specific fixes and UI improvements.  
Original resource credit belongs to **CAS / UIforc**.

If you are using this repo, make sure you review the original author’s permissions and any license terms before redistribution.
