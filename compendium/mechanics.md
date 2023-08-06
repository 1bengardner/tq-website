---
layout: compendium-page
title: "Mechanics"
permalink: "/compendium/mechanics"
---

<strong class="callout">
  🚧 This page is a work in progress.
</strong>

<div class="callout">
  <strong>Contents</strong>
  <ul class="horizontal">
    <li>
      <a href="#battle">Battle</a>
    </li>
    <li>
      <a href="#stats">Stats</a>
    </li>
    <li>
      <a href="#skills">Skills</a>
    </li>
    <li>
      <a href="#items">Items</a>
    </li>
    <li>
      <a href="#elements">Elements</a>
    </li>
  </ul>
</div>

---

## Battle

<span class="callout">
  🚧 This section isn't written yet.
</span>

---

## Stats

Stats can be separated into [vital stats](#vital-stats), [primary stats](#primary-stats) and [secondary stats](#secondary-stats).

- **Vital stats** are the most important to watch and may fluctuate frequently.
- **Primary stats** shape your overall development.
- **Secondary stats** affect your potency in battle.

### Vital Stats

You gain *XP* from defeating enemies. You gain more XP when the enemies you defeat are closer to your level or above it.

Each time you level up, you gain 20 *HP* and 20 *EP*, and your HP and EP are fully restored.

|Stat|Effect
|-|-|
|XP|Allows you to level up when you accumulate enough of it.
|HP|Keeps you alive.
|EP|Allows you to use skills.

### Primary Stats

Each time you level up, you gain 5 *Stat Points* to distribute among *Strength*, *Dexterity* and *Wisdom*.

Each of the three primary stats increases your damage dealt with one or more weapon types, and increases one or more secondary stats.

A stat needs to be high enough in order to wield a particular piece of [equipment](#equipment).

|Stat|Weapons Empowered|Secondary Bonuses|
|-|-|-|
|Strength|Mace, sword, axe, spear|Critical damage|
|Dexterity|Bow|Accuracy, critical chance, block chance|
|Wisdom|Wand|Elemental reduction|

### Secondary Stats

These stats are derived from your primary stats and the equipment you wield (and [passive items](#passive-bonuses) you hold).

|Stat|Effect|
|-|-|
|Accuracy|Determines chance to hit.|
|Critical Chance|Determines chance to land a critical hit.|
|Critical Damage|Determines critical hit damage compared to a regular attack.|
|Defence|Decreases damage taken by a *flat value*. Calculated before reductions.<br />{::nomarkdown}<details><summary class="bar-descriptor">Flat value?</summary>Every point of defence will reduce damage taken by one point.</details>{:/nomarkdown}|
|Reduction|Decreases damage taken by a *percentage*. Calculated after defence.|
|Block Chance|Determines chance to nullify an enemy attack against you.|

---

## Skills

You may keep up to *4* skills. To get another skill after four, you must relinquish one that you already have.

### Stat-altering Skills

Some skills alter user stats and/or opponent stats.

Stats will return to their original values after

- Battle
- Changing equipment in battle.

---

## Items

You may carry up to *9* items, unless you have the [Chasmic Rucksack](miscellaneous#chasmic-rucksack), which allows you to carry up to *16*.

### Equipment

In general, you can wield 1 weapon, 1 piece of armour and 1 shield at a time. However, if you wield a bow, you may not wield a shield under most circumstances.

You must meet the stat requirement of a piece of equipment in order to wield it.

#### Modified equipment

Sometimes an enemy will drop a piece of equipment with a modifier (prefix). This is a regular piece of equipment with an additional enhancement.

|Modifier Name|Stat Enhanced|Enhancement Amount|
|-|-|
|Exotic|Sell price|+100% to +300%|
|Big|Power|+2 to +4|
|Keen|Critical chance|+1% to +2%|
|Stony|Earth reduction|+2% to +4%|
|Icy|Water reduction|+2% to +4%|
|Fiery|Fire reduction|+2% to +4%|
|Sturdy|Defence|+2 to +4|
|Heavy|Block chance|+1% to +2%|
|Giant|Power|+4 to +8|
|Deadly|Critical chance|+2% to +4%|
|Gaian|Earth reduction|+4% to +8%|
|Glacial|Water reduction|+4% to +8%|
|Molten|Fire reduction|+4% to +8%|
|Robust|Defence|+4 to +8|
|Massive|Block chance|+2% to +4%|

### Passive Bonuses

Some [Miscellaneous Items](miscellaneous) present passive bonuses that benefit you as long as that item is in your inventory. They do not need to be equipped.

---

## Elements

### Reductions

<span class="callout">
  🚧 This section isn't written yet.
</span>

### Elemental Ailments

Elemental attacks that deal damage (except Poison Ivy) have a chance to inflict an ailment upon the target. Ailments are removed after battle.

Elementally-imbued weapons in general do not inflict ailments. However, *lightning weapons* are special: While wielding one, non-elemental attacks have a chance of inflicting paralysis.

|Skill Element|Ailment|Effect|
|-|-|-|
|Earth|30% chance to *ground*|Lose one turn.|
|Lightning|20% chance to *paralyze*|Lose turns until recovery. 50% chance of recovery each turn.|
|Poison|100% chance to *poison*|Take damage equal to approximately 2% of your max HP each turn.|
|Water|50% chance to *drown* when 50% or more damage is dealt|Die immediately.|
|Ice|15% chance to *freeze*|Lose turns until recovery. 25% chance of recovery each turn.|
|Fire|25% chance to *ignite*|Take damage equal to approximately 25% of damage dealt by the original igniting attack each turn until recovery. 25% chance of recovery each turn.|
|Petrification|100% chance to *petrify*|Lose turns until recovery. 25% chance of recovery each turn.|

#### Additional Notes

- If you ignite while frozen, you will no longer be frozen, and vice versa.
- If you are petrified while paralyzed and/or frozen, you will no longer be paralyzed and/or frozen.