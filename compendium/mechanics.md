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

<details markdown=1><summary><em>How much XP do I need to level up?</em></summary>

|Level|XP Required|
|-|-|
|1|0|
|2|100|
|3|340|
|4|800|
|5|1,600|
|6|2,900|
|7|4,900|
|8|7,840|
|9|12,000|
|10|17,700|
|11|25,300|
|12|35,200|
|13|47,840|
|14|63,700|
|15|83,300|
|16|107,200|
|17|136,000|
|18|170,340|
|19|210,900|
|20|258,400|
|21|313,600|
|22|377,300|
|23|450,340|
|24|533,600|
|25|628,000|
|26|734,500|
|27|854,100|
|28|987,840|
|29|1,136,800|
|30|1,302,100|
|31|1,484,900|
|32|1,686,400|
|33|1,907,840|
|34|2,150,500|
|35|2,415,700|
|36|2,704,800|
|37|3,019,200|
|38|3,360,340|
|39|3,729,700|
|40|4,128,800|
|41|4,559,200|
|42|5,022,500|
|43|5,520,340|
|44|6,054,400|
|45|6,626,400|
|46|7,238,100|
|47|7,891,300|
|48|8,587,840|
|49|9,329,600|
|50|10,118,500|
|...|...|
|100|163,812,000|

</details>

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
|Earth|30% chance to be *grounded*|Lose one turn.|
|Lightning|20% chance to be *paralyzed*|Lose turns until recovery. 50% chance of recovery each turn.|
|Poison|100% chance to be *poisoned*|Take damage equal to approximately 2% of your max HP each turn.|
|Water|50% chance to *drown* when you lose 50% max HP from the attack|Die immediately.|
|Ice|15% chance to *freeze*|Lose turns until recovery. 25% chance of recovery each turn.|
|Fire|25% chance to *ignite*|Take damage equal to approximately 25% of damage dealt by the original igniting attack each turn until recovery. 25% chance of recovery each turn.|
|Petrification|100% chance to be *petrified*|Lose turns until recovery. 25% chance of recovery each turn.|

#### Additional Notes

- If you ignite while frozen, you will no longer be frozen, and vice versa.
- If you are petrified while paralyzed and/or frozen, you will no longer be paralyzed and/or frozen.