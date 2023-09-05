---
layout: compendium-page
title: "Game Guide"
permalink: "/compendium/guide"
---

<div class="callout">
  <strong>Contents</strong>
  <ul class="horizontal">
    <li>
      <a href="#stats">Stats</a>
    </li>
    <li>
      <a href="#items">Items</a>
    </li>
    <li>
      <a href="#skills">Skills</a>
    </li>
    <li>
      <a href="#elements">Elements</a>
    </li>
    <li>
      <a href="#battle">Battle</a>
    </li>
    <li>
      <a href="#allies">Allies</a>
    </li>
  </ul>
</div>

---

## Stats

Stats can be grouped into [vital stats](#vital-stats), [primary stats](#primary-stats) and [secondary stats](#secondary-stats).

- **Vital stats** are the most important to watch and may fluctuate frequently.
- **Primary stats** shape your overall development.
- **Secondary stats** affect your potency in battle.

### Vital Stats

You gain *XP* from defeating enemies. You gain more XP when the enemies you defeat are closer to your level or above it.

Each time you level up, your *HP* and *EP* are fully restored and their maximums increase by 20.

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

Each time you level up, you gain 5 *stat points* to distribute among *strength*, *dexterity* and *wisdom*.

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
|Accuracy|Determines chance to hit.{::nomarkdown}<details markdown=1><summary class="small-text"><em>What's the formula?</em></summary><p>{:/nomarkdown}Accuracy = `weapon's accuracy` + `dexterity` - 10{::nomarkdown}</p></details>{:/nomarkdown}|
|Base Damage|Determines how much damage will be done with a [regular attack](#attacking).{::nomarkdown}<details markdown=1><summary class="small-text"><em>What's the formula?</em></summary><p>{:/nomarkdown}Base damage = [`power`](#power) × [`primary stat`](#primary-stats) / 10{::nomarkdown}</p></details>{:/nomarkdown}|
|Average Damage|Determines how much damage will be done with a regular attack, accounting for accuracy, critical chance and critical damage.|
|Critical Chance|Determines chance to land a critical hit.{::nomarkdown}<details markdown=1><summary class="small-text"><em>What's the formula?</em></summary><p>{:/nomarkdown}Critical chance = `weapon's critical chance` × (1 + (`dexterity` - 10) / 100){::nomarkdown}</p></details>{:/nomarkdown}|
|Critical Damage|Determines critical hit damage compared to a regular attack.{::nomarkdown}<details markdown=1><summary class="small-text"><em>What's the formula?</em></summary><p>{:/nomarkdown}Critical damage = `weapon's critical damage` × (1 + (`strength` - 10) / 100){::nomarkdown}</p></details>{:/nomarkdown}|
|Defence|Decreases damage taken by a *flat value*. Calculated before reductions.{::nomarkdown}<details><summary class="small-text"><em>Flat value?</em></summary><p>Every point of defence will reduce damage taken by one point.</p></details>{:/nomarkdown}|
|Reduction|Decreases damage taken by a *percentage*. Calculated after defence.{::nomarkdown}<details markdown=1><summary class="small-text"><em>What's the formula?</em></summary><p>{:/nomarkdown}Reduction = `equipment's reduction` + 3 × √(`wisdom` - 10){::nomarkdown}</p></details>{:/nomarkdown}|
|Block Chance|Determines chance to nullify an enemy attack against you.{::nomarkdown}<details markdown=1><summary class="small-text"><em>What's the formula?</em></summary><p>{:/nomarkdown}Block chance = `shield's block chance` × (1 + (`dexterity` - 10) / 20){::nomarkdown}</p></details>{:/nomarkdown}|

---

## Items

Items serve a variety of purposes from boosting stats to providing access to new locations. Items can be grouped into [equipment](#equipment) and [miscellaneous items](#miscellaneous-items).

You may carry up to *9* items, unless you have the <span class="compendium-link">[Chasmic Rucksack](miscellaneous#chasmic-rucksack)</span>, which allows you to carry up to *16*.

### Equipment

In general, you can wield 1 <span class="compendium-link">[weapon](weapons)</span>, 1 piece of <span class="compendium-link">[armour](armour)</span> and 1 <span class="compendium-link">[shield](shields)</span> at a time. However, if you wield a <span class="compendium-link">[bow](weapons#bows)</span>, you may not wield a shield under most circumstances.

You must meet the stat requirement of a piece of equipment in order to wield it.

#### Power

In general, equipment stats directly affect your secondary stats.

There is a special case for *power*. It is a stat found only on weapons and it affects your damage.

<details markdown=1><summary><em>What's the damage formula?</em></summary>

- Base damage = `power` × [`primary stat`](#primary-stats) / 10

</details>

#### Wands

*Regular attacks* with <span class="compendium-link">[wands](weapons#wands)</span> are peculiar for three reasons:

- An enemy's physical reduction is not applied.
- Only ½ of an enemy's defence is applied.
- The average of an enemy's 3 elemental reductions is applied.
  - If an enemy is immune to an element, that component is treated as 100% reduction in this average.

#### Modified Equipment

Sometimes an enemy will drop a piece of equipment with a modifier (prefix). This is a regular piece of equipment with an additional enhancement.

|Modifier Name|Stat Enhanced|Enhancement Amount|
|-|-|-|
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

### Miscellaneous Items

<span class="compendium-link">[Miscellaneous items](miscellaneous)</span> cannot be equipped (except for the <span class="compendium-link">[Scintillous Ring](miscellaneous#scintillous-ring)</span>), but they are useful in other ways.

- <span class="compendium-link">[**Quest items**](miscellaneous#quest-items)</span> help you make progress by aiding you in getting past obstacles.
- <span class="compendium-link">[**Consumable items**](miscellaneous#consumables)</span> help you in battle. Some are consumed and activated with a regular attack.
- <span class="compendium-link">[**Materials**](miscellaneous#materials)</span> like gems and ore can be combined to craft equipment when given to the right NPC.

There are a few other miscellaneous items that you will find throughout the game that serve various purposes.

#### Passive Bonuses

Some miscellaneous items present passive bonuses that benefit you as long as that item is in your inventory. They do not need to be equipped.

---

## Skills

Most <span class="compendium-link">[skills](skills)</span> require a certain weapon type to be equipped in order to use them in [battle](#battle). Skills consume EP when used.

There are <span class="compendium-link">[three](skills#avalanche)</span> <span class="compendium-link">[special](skills#melting-touch)</span> <span class="compendium-link">[skills](skills#hailstorm)</span> that may be used outside of battle in very specific scenarios.

You may keep up to *4* skills. To get another skill after four, you must relinquish one that you already have.

### Elemental Skills

*Elemental skills* are skills which deal elemental damage.

They have the following properties when used:

- Defence applied is reduced by ½.
- [Elemental reductions](#elemental-reductions) are applied.
- There is a chance to inflict an [elemental ailment](#elemental-ailments).

### Stat-Altering Skills

Some skills alter user stats and/or opponent stats.

Stats will return to their original values after

- Battle, or
- Changing equipment in battle.

---

## Elements

### Reductions

Reductions can be grouped into [physical reduction](#physical-reduction) and [elemental reductions](#elemental-reductions).

#### Physical Reduction

Physical reduction applies to all *non-elemental attacks* except regular attacks with [wands](#wands).

Non-elemental attacks are attacks that are performed without an elementally-imbued weapon, using

- A regular attack, or
- A non-elemental skill.

#### Elemental Reductions

There are *3* different elemental reductions: earth, water and fire.

Elemental reductions apply to all *elemental attacks* as well as regular attacks with wands.

Elemental attacks are attacks that are performed using

- An elemental skill, or
- An elementally-imbued weapon.

The specific elemental reduction that is applied depends on the element of the attack.

|Attack Element|Reduction Element|
|-|-|
|Earth|Earth|
|Water|Water|
|Fire|Fire|
|Lightning|Earth|
|Poison|Earth|
|Ice|Water|
|Frostfire|½ Water, ½ Fire|

Unlike other [secondary bonuses](#secondary-stats), elemental reductions do not increase linearly with their corresponding primary stat.

<details markdown=1><summary>Wisdom–elemental reduction table</summary>

|Wisdom|Elemental Reduction|
|-|-|
|10|+0%|
|11|+3%|
|12|+4%|
|13|+5%|
|14|+6%|
|15|+6%|
|16|+7%|
|17|+7%|
|18|+8%|
|19|+9%|
|20|+9%|
|21|+9%|
|22|+10%|
|23|+10%|
|24|+11%|
|25|+11%|
|26|+12%|
|...|...|
|51|+19%|
|...|...|
|104|+29%|

</details>

### Elemental Ailments

[Elemental skills](#elemental-skills) have a chance to inflict an ailment upon the target. Ailments are removed after battle.

Elementally-imbued weapons generally do not inflict ailments. However, *lightning weapons* are special: while wielding one, non-elemental attacks have a chance of inflicting paralysis.

|Skill Element|Ailment|Effect|
|-|-|-|
|Earth|30% chance to be *grounded*|Lose one turn.|
|Lightning|20% chance to be *paralyzed*|Lose turns until recovery. 50% chance of recovery each turn.|
|Poison|100% chance to be *poisoned*|Take damage equal to approximately 2% of your max HP each turn.{::nomarkdown}<details markdown=1><summary class="small-text"><em>Special case for rare enemies</em></summary><p>{:/nomarkdown}<span id="poison-on-rare-enemies">Poisoned [*rare enemies*](#rare-enemies) have a 20% chance to be cured each turn and cannot take poison damage if their HP is below 10% of their max HP</span>{::nomarkdown}</p></details>{:/nomarkdown}|
|Water|50% chance to *drown* when you lose 50% max HP from the attack|Die immediately.|
|Ice|15% chance to *freeze*|Lose turns until recovery. 25% chance of recovery each turn.|
|Fire|25% chance to *ignite*|Take damage equal to approximately 25% of damage dealt by the last igniting attack each turn until recovery. 25% chance of recovery each turn.{::nomarkdown}<details markdown=1><summary class="small-text"><em>Ignition, Transmission, Backfire, Afterburn</em></summary><p>{:/nomarkdown}If you ignite the enemy while you are on fire, your attack is considered the last igniting attack and you will take 25% of its damage instead of the attack that ignited you. The inverse also applies.{::nomarkdown}</p></details>{:/nomarkdown}|
|Petrification|100% chance to be *petrified*|Lose turns until recovery. 25% chance of recovery each turn.|

#### Additional Notes

- If you ignite while frozen, you will no longer be frozen, and vice versa.
- If you are petrified while paralyzed and/or frozen, you will no longer be paralyzed and/or frozen.

---

## Battle

Battles may occur randomly while travelling, or as a result of events that happen.

In battle, combatants take turns using moves.

### Turn Order

In general, you or the enemy are randomly selected to take the first turn. However, if you are wielding a bow, you will always go first.

Turn order is maintained throughout the battle.

### Moves

There are *3* basic combat moves always available to you.

- <span id="attacking">**Attacking** ![Sword](/assets/img/icons/attack.gif)</span> strikes the enemy with your equipped weapon. Also referred to as a *regular attack*.
- **Defending** ![Shield](/assets/img/icons/defend.gif) increases your chance to block the next attack by a flat 25% and restores EP. If the next attack is successfully blocked, you gain an EP boost.
  <details markdown=1 style="margin-bottom: 0.5em;"><summary class="small-text"><em>How much EP?</em></summary>
  
  - EP restored = 5 + ∜`wisdom`<sup>3</sup>
  - EP boost = 1 + 9 × √`blocked damage`
  
  </details>
- **Running away** ![Running Man](/assets/img/icons/flee.gif) attempts to flee from battle. If your level is not higher than the enemy's, there is a chance that the enemy will catch up.
  <details markdown=1><summary class="small-text"><em>What's the chance to flee?</em></summary>
  
  - Chance to flee = 100% / (2 + `enemy level` - `your level`)
  
  |Level Difference|Chance to Flee|
  |-|-|
  |0|50%|
  |1|33%|
  |2|25%|
  |3|20%|
  |4|16%|
  |5|14%|
  |...|...|
  |10|8%|
  
  </details>

There are *2* special moves available in battle. These actions can also be performed outside of battle.

- **Changing equipment** ![Body Armour](/assets/img/icons/inventory.gif) allows you to use a turn to equip a different item from your inventory.
- **Drinking a potion** ![Potion](/assets/img/icons/potion.gif) restores HP. It requires you to have at least one vial of life fluid.
  <details markdown=1><summary class="small-text"><em>How much HP?</em></summary>
  
  - HP restored = 50 + 10 × √`your level` - 10
  
  </details>
  
In addition to the five moves mentioned, you may use any of your [skills](#skills) for which you meet the requirements.

### Enemy Peculiarities

- Certain enemies cannot be fled from. If you attempt to flee from an unfleeable enemy, you will see text "<span class="game-text">There's nowhere to run.</span>"
- Enemies that are "living" can be poisoned. These are enemies that bear blood and drop potions. Bloodless enemies are immune to poison.
- <span id="rare-enemies">An enemy with a border that is not brown is considered "rare." [Poison has a weaker effect on rare enemies.](#poison-on-rare-enemies)</span>

---

## Allies

You will encounter fighters who want to accompany you on your quest.

Allies will join you in battle, taking their turn immediately after you. They have a set of skills and equipment that remains with them throughout your journey.

An enemy may attack an ally. If an ally loses all their HP, they will be unable to fight until they rest at their house or an inn.

Allies gain the same amount of XP as you after each battle. When they level up, they will gain 20 max HP and allocate 5 stat points to one of their primary stats.

|Ally|Chosen Primary Stat|
|-|-|
|Dragan|Dexterity|
|Qendresa|Strength|
|Barrie|Wisdom|
