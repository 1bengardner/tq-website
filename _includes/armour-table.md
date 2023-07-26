|Armour|Str.|Defence|Reduction{::nomarkdown}<colgroup><col><col style="width: 32px;"><col style="width: 28%;"><col style="width: 28%;"></colgroup>{:/nomarkdown}|
|-|-|-|-|
{%- assign sorted-armour = site.data.armourdata | sort: "PRICE" -%}
{%- for armour in sorted-armour %}
  |{::nomarkdown}<span class="record-name">{{ armour.NAME }}</span>{:/nomarkdown}
  {%- if armour.NAME contains "Moon Armour" or armour.NAME contains "Ugly Disguise" -%}
    <br /><span class="bar-descriptor"><a href="#legend">Evade encounters</a></span>
  {%- elsif armour.NAME contains "Hopalong Boots" -%}
    <br /><span class="bar-descriptor"><a href="#legend">Strike first</a></span>
  {%- endif -%}
  <br />![{{ armour.NAME }}](/assets/img/armour/{{ armour.NAME | downcase }}.gif){% include price.md price=armour.PRICE -%}{% include dropped-by.md item-name=armour.NAME -%}
  |{{ armour.REQUIREMENT_VALUE }}|
  {%- assign fill = armour.DEFENCE | times: 100 | divided_by: 40 -%}{::nomarkdown}{% include bar.html fill=fill text=armour.DEFENCE %}{:/nomarkdown}|
  {%- assign test = armour.REDUCTION | round -%}
  {%- if test != 0 -%}
    {%- assign text = armour.REDUCTION | append: "% " | append: armour.ELEMENT -%}{::nomarkdown}{% include bar.html fill=armour.REDUCTION text=text element=armour.ELEMENT %}{:/nomarkdown}
  {%- endif -%}|
{%- endfor %}

<div id="legend"><hr /></div>

## Notes

**Evade encounters** prevents random encounters while travelling.

**Strike first** causes you to always take your turn first in battle.
