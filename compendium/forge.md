---
layout: compendium-page
title: "The Forge"
permalink: "/compendium/forge"
---

<span style="float: right;">
  <img class="decorative-circle" {% include independently-sized-image-properties.html path="/assets/img/other/forge.gif" %} alt="Forge of Hephaestus" style="margin-left: 1em; margin-bottom: 1em;" />
</span>

## Overview

Once you have completed the game, you unlock the *Forge of Hephaestus*, located on the highest peak of *Mount Olympus*.

Each successive climb grants you one attempt to forge a piece of your equipment upon the anvil, along with [legend rewards](#legend-rewards) for every tenth ascent.

<span style="float: left;">
  <img {% include independently-sized-image-properties.html path="/assets/img/other/anvil.gif" %} alt="Anvil" style="margin-right: 1em; margin-top: 30px;" />
</span>

## Forging

Forging a piece of your equipment requires two pieces of equipment as fodder to heat the crucible.

### Success Formula

Forge success chance depends on the quality of the equipment *forged* and *sacrificed*.

Quality of equipment is measured in three ways:

1. **Value**, `x`: The sell price of the equipment.
1. **Upgrade count**, `y`: The number of times the item has been successfully upgraded at the forge.
1. **[Form](#forms) changes**, `z`: The number of times the item has changed form.

The quality of sacrifices and upgrade candidates are inversely related.

- As the quality of equipment-to-be-forged <sub>(*f*)</sub> increases, the success chance *decreases*.
- As the quality of sacrificed equipment <sub>(*s1*, *s2*)</sub> increases, the success chance *increases*.

#### The Complete Formula

= 100% × ½[√`x`<sub>*s1*</sub> × (1 + ½`y`<sub>*s1*</sub> × 1.2<sup>`z`<sub>*s1*</sub></sup>) +
√`x`<sub>*s2*</sub> × (1 + ½`y`<sub>*s2*</sub> × 1.2<sup>`z`<sub>*s2*</sub></sup>)] /
[√`x`<sub>*f*</sub> × (1 + `y`<sub>*f*</sub> / 10)]

#### Horns

Horns are special one-time-use items that can increase your success chance at the forge. The horn that provides the highest success chance will automatically be used when you attempt to upgrade your equipment.

### Success Chance Over 100%

If the success chance exceeds 100%, there is a chance that the forged equipment will be upgraded multiple times.

A 125% success chance means the forged equipment will be upgraded at least once, with a 25% chance to be upgraded twice. At 200%, the equipment is guaranteed to be upgraded twice; at 300%, thrice, and so on.

### Fiddling

If you hit the anvil multiple times before letting it cool, you can randomly alter the success chance (between -5% and +5%). You may hit the anvil as many times as you like, but when the result is worse, the anvil will cool quicker and you will have a shorter time to react.

## Forge Outcomes

If you fail to upgrade a forged piece of equipment, the sacrificed equipment will be lost and the forged equipment will remain unchanged.

If you successfully upgrade a piece of equipment at the forge, the sacrifices will be consumed and the forged equipment will be enhanced based on its kind.

|Kind of Equipment|Stat Enhanced|
|-|-|
|Weapon|Power|
|Armour|Defence|
|Shield|Defence|

### Modifiers

Sacrificed equipment with a <span class="compendium-link">[modifier prefix](guide#modified-equipment)</span> in its name will provide an additional enhancement based on prefix name, but only if it's the same kind of equipment as forged.

## Forms

Each successive upgrade on a piece of equipment will increase its upgrade count. Once this upgrade count passes a threshold, the equipment will change *form* and gain an increased stat enhancement with each upgrade.

|Upgrade Count|Form|Stats per Upgrade|
|-|-|-|
|0+|<span class="quiet-text">None</span>|+2|
|10+|Heroic|+4|
|20+|Blessed|+6|
|30+|Glorious|+8|
|40+|Legendary|+10|

## Legend Rewards

After each forge attempt, you will have completed an ascent of Mount Olympus. You will receive a reward for every ten ascensions.

|Ascensions|Reward|
|-|-|
|10|Legendary portrait border|
|20|<span class="compendium-link">[Ranine Orb](/compendium/miscellaneous#ranine-orb)</span>|
|30|<span class="compendium-link">[Bulbous Orb](/compendium/miscellaneous#bulbous-orb)</span>|
|40|<span class="compendium-link">[Fiery Orb](/compendium/miscellaneous#fiery-orb)</span>|
|50|<span class="compendium-link">[Platinum Ball](/compendium/miscellaneous#platinum-ball)</span>|
|60|<span class="compendium-link">[Wizardly Orb](/compendium/miscellaneous#wizardly-orb)</span>|
|70|<span class="compendium-link">[Knightly Orb](/compendium/miscellaneous#knightly-orb)</span>|
|80|<span class="compendium-link">[Feline Orb](/compendium/miscellaneous#feline-orb)</span>|
|90|<span class="compendium-link">[Gumball of Power](/compendium/miscellaneous#gumball-of-power)</span>|
|100|<span class="compendium-link">[Purple Horn](/compendium/miscellaneous#purple-horn)</span>|
