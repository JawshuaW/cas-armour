<div align="center">

# 🛡️ CAS Armour for RedM

### Slot-Based Armour, Equipment, Durability, Stats, Sets, Crafting & NUI UI

![RedM](https://img.shields.io/badge/RedM-rdr3-red?style=for-the-badge)
![Framework](https://img.shields.io/badge/Framework-VORP%20%7C%20RSGCore-brown?style=for-the-badge)
![Database](https://img.shields.io/badge/Database-oxmysql-gold?style=for-the-badge)
![Status](https://img.shields.io/badge/Version-Custom%20Updated-darkgreen?style=for-the-badge)

</div>

---

## ⚠️ Credit / Ownership Notice

This is **not my original script**.

The original **CAS Armour** resource is credited to **CAS / UIforc**.  
This repository is my personally updated/customized version for RedM/VORP server use.

The goal of this version is to keep the original armour system intact while adding UI fixes, startup fixes, HUD quality-of-life commands, resolution improvements, and other adjustments for better live-server use.

> Original author credit should remain with **CAS / UIforc** if this edited version is shared or redistributed.

---

## 📌 About This Version

This updated version keeps the main CAS Armour system while improving how it works and displays in-game.

It includes fixes for:

- Armour menu startup/opening issues
- `/armor` command behavior
- **U key** menu opening
- NUI readiness after server restarts
- 1920x1080 / 2560x1440 layout scaling
- Floating equipment slot positioning
- Red connector line behavior
- Equipped armour HUD placement
- Player hide/show HUD commands
- In-menu help hint for armour HUD controls

Basically, the same armour system, but less likely to behave like it was assembled during a saloon brawl.


---

## 🖼️ Preview Images

These screenshots show the main updated parts of the CAS Armour interface. If GitHub ever refuses to display externally hosted images, the direct links are included under each preview because apparently even pictures need backup paperwork.

<table>
  <tr>
    <td align="center" width="50%">
      <h3>View All Sets Page</h3>
      <a href="https://files.catbox.moe/yky5v9.png">
        <img src="https://files.catbox.moe/yky5v9.png" alt="CAS Armour View All Sets page showing armour sets, bonuses, and equipped pieces" width="100%" />
      </a>
      <br />
      <sub>Shows every armour set, what each set does, the set bonuses, and which pieces are currently equipped.</sub>
      <br />
      <sub><a href="https://files.catbox.moe/yky5v9.png">Open full image</a></sub>
    </td>
    <td align="center" width="50%">
      <h3>Armour Equipment Menu</h3>
      <a href="https://files.catbox.moe/9aib1q.png">
        <img src="https://files.catbox.moe/9aib1q.png" alt="CAS Armour equipment menu with body connector lines and armour slots" width="100%" />
      </a>
      <br />
      <sub>Opens with <code>U</code> or <code>/armor</code>. Shows the player equipment layout, inventory, armour slots, and connector lines to the proper body parts.</sub>
      <br />
      <sub><a href="https://files.catbox.moe/9aib1q.png">Open full image</a></sub>
    </td>
  </tr>
</table>

<div align="center">

### Equipped Armour HUD

<a href="https://files.catbox.moe/fomwsa.png">
  <img src="https://files.catbox.moe/fomwsa.png" alt="CAS Armour equipped armour HUD in the bottom-right showing currently worn armour" width="850" />
</a>

<sub>Shows what the player is currently wearing and the armour condition/status. This updated version places the HUD in the <strong>bottom-right</strong> of the screen so it stays clear of the minimap.</sub>

<br />
<sub><a href="https://files.catbox.moe/fomwsa.png">Open full image</a></sub>

</div>

> Image links used:
> - View All Sets Page: https://files.catbox.moe/yky5v9.png
> - Armour Equipment Menu: https://files.catbox.moe/9aib1q.png
> - Equipped Armour HUD: https://files.catbox.moe/fomwsa.png


---

## ✨ Custom Updates Made

### ✅ Menu Opening / Startup Fixes

- Fixed issues where the armour system worked after restart, but `/armor` or **U** would not open the menu properly.
- Added safer NUI startup/readiness handling.
- Improved menu opening reliability after full server restarts.

### ✅ Resolution / UI Scaling Fixes

- Improved layout behavior for common player resolutions:
  - `1920x1080`
  - `2560x1440`
- Adjusted the main UI frame so slot placement and line positions scale more consistently.
- Improved equipment slot positioning and body connector line alignment.

### ✅ Armour HUD Updates

The equipped armour/status HUD was moved away from the minimap and placed in the **bottom-right** of the screen.

Players can now hide, show, or toggle the armour HUD if they do not want it visible.

### ✅ Help Hint Added

A small help message was added inside the armour menu so players know how to hide/show the HUD:

```txt
Armor HUD: /hidearmor or /hidearmour to hide • /showarmor or /showarmour to show
```

---

## 🎮 Player Commands

### Open Armour Menu

```txt
/armor
```

The armour menu can also be opened with the configured **U key**.

### Hide Armour HUD

```txt
/hidearmor
/hidearmour
```

### Show Armour HUD

```txt
/showarmor
/showarmour
```

### Toggle Armour HUD

```txt
/togglearmorhud
/togglearmourhud
```

The HUD visibility preference is saved client-side, so if a player hides it, it should stay hidden until they choose to show it again.

---

## 🧩 Requirements

| Requirement | Notes |
|---|---|
| `vorp_core` or `rsg-core` | Framework support |
| `vorp_inventory` or `rsg-inventory` | Inventory support |
| `oxmysql` | Database support |

---

## 📦 Installation

### 1. Import SQL

Import the included SQL files into your database:

```txt
sql/cas_armour_equipment.sql
sql/cas_armour_items.sql
```

### 2. Resource Folder Name

Keep the folder named exactly:

```txt
cas-armour
```

### 3. Add to `server.cfg`

Make sure dependencies are started before this resource:

```cfg
ensure oxmysql
ensure vorp_core
ensure vorp_inventory
ensure cas-armour
```

### 4. Restart

```cfg
restart cas-armour
```

Or restart the full server if needed.

---

## 🛡️ Main Features

### Equipment System

CAS Armour uses **10 equipment slots**:

| Slot | Description |
|---|---|
| `head` | Head armour |
| `chest` | Chest armour |
| `vest` | Vest layer |
| `pants` | Pants/leg armour |
| `boots` | Footwear armour |
| `gloves` | Hand armour |
| `belt` | Belt equipment |
| `amulet` | Amulet slot |
| `trinket1` | Trinket slot 1 |
| `trinket2` | Trinket slot 2 |

Supports:

- Drag-and-drop NUI interface
- Equip from inventory
- Unequip back to inventory
- Item condition/durability metadata
- Persistent saved equipment through `oxmysql`

---

## ⚔️ Damage Reduction

Armour can reduce multiple damage categories:

| Stat | Purpose |
|---|---|
| `armorBase` | General baseline protection |
| `bulletResist` | Bullet damage resistance |
| `meleeResist` | Melee damage resistance |
| `animalResist` | Animal damage resistance |
| `fallResist` | Fall damage resistance |
| `explosionResist` | Explosion damage resistance |
| `poisonResist` | Poison damage resistance |

Formula:

```txt
reduction% = (armorBase * ArmorBaseToReduction) + categoryResist
```

Reduction is capped by:

```txt
MaxDamageReductionPercent
```

---

## 🔧 Durability / Wear

- Armour condition decreases when taking damage.
- Broken armour pieces are removed from their equipped slot.
- Wear can spread across related nearby slots.
- Example: torso damage can also affect belt or amulet condition.

---

## 🧥 Set Bonuses

Armour sets can provide bonus stats when multiple pieces are equipped.

Set bonuses may activate at different tiers:

```txt
2 pieces
4 pieces
6 pieces
8 pieces
10 pieces
```

Full sets can also grant unique passive abilities.

| Set | Passive | Effect |
|---|---|---|
| Wolf | Wolf Detection Reduction | Extra NPC sense reduction |
| Bear | Bear Charge Resistance | Ragdoll immunity |
| Outlaw | Bullet Dodge Chance | Chance to negate bullet damage |
| Scholar | Enemy Detection Boost | Blips on hostile NPCs |
| Snake | Poison Aura | AoE damage to nearby NPCs |
| Night | Assassination Expertise | Bonus damage on unaware NPCs |
| Legend | Quickdraw Mastery | Intimidation and deadeye recovery bonuses |

---

## 🏃 Movement / Weight

Armour weight and stamina values can affect movement.

Formula:

```txt
mult = 1.0 - (staminaCost * StaminaCostToMovePenalty) - weightPenalty
```

---

## 🌡️ Environmental Effects

Armour can affect:

- Cold resistance
- Heat resistance
- Stamina drain
- Deadeye drain
- NPC stealth detection
- NPC intimidation/surrender chance

---

## 🔨 Crafting

The resource includes armour crafting support.

- Blacksmith crafting locations are configurable.
- Default examples may include:
  - Valentine
  - Annesburg
  - Rhodes
- Uses `vorp_menu` for crafting selection.
- Uses progress bar and animation during crafting.

---

## 🖥️ UI / NUI Improvements

This customized version includes several interface improvements:

- More reliable NUI startup handling
- Better UI scaling across common resolutions
- Floating armour slot layout improvements
- Connector line layer improvements
- Equipped armour HUD moved to bottom-right
- Hide/show HUD commands
- Small command help hint inside the menu

---

## ⚙️ Configuration

Main configuration is located in:

```txt
shared/config.lua
```

Important sections may include:

| Config Section | Purpose |
|---|---|
| `Config.Tuning` | Main armour/stat tuning |
| `Config.WeightPenalty` | Weight and movement penalty settings |
| `Config.ArmorPieces` | Armour item definitions |
| `Config.ArmorSets` | Set bonus definitions |
| Crafting locations | Blacksmith/crafting setup |
| Passive effects | Unique set/passive behavior |

---

## 🔁 NUI Callbacks

Common NUI callbacks include:

```txt
cas_armour:close
cas_armour:requestData
cas_armour:equip
cas_armour:unequip
cas_armour:craft
```

Example payloads:

```txt
cas_armour:equip
{ pieceId, itemName, itemId, targetSlot, metadata }

cas_armour:unequip
{ slot }

cas_armour:craft
{ pieceId }
```

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

This is an edited/customized version of **CAS Armour** for personal RedM server use.

Original script/resource credit remains with:

```txt
CAS / UIforc
```

My changes are focused on:

- Compatibility
- Usability
- UI placement
- Resolution handling
- Player HUD controls
- Server restart reliability
- Quality-of-life improvements

Please keep the original author credit intact if redistributing or publishing an edited copy. Nobody likes the guy who steals a horse, paints it black, and claims he bred it himself.

---

<div align="center">

**Updated for custom RedM/VORP server use.**  
**Original CAS Armour credit: CAS / UIforc**

</div>
