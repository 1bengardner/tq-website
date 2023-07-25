|Armour|Str.|Defence|Reduction|Special Notes|
|-|-|-|-|-|
{%- assign sorted-armour = site.data.armourdata | sort: "PRICE" -%}
{%- for armour in sorted-armour %}
  |{::nomarkdown}<span class="record-name">{{ armour.NAME }}</span>{:/nomarkdown}<br />![{{ armour.NAME }}](/assets/img/armour/{{ armour.NAME | downcase }}.gif)|{{ armour.REQUIREMENT_VALUE }}|
  {%- assign fill = armour.DEFENCE | times: 100 | divided_by: 40 -%}{::nomarkdown}{% include bar.html fill=fill text=armour.DEFENCE %}{:/nomarkdown}|
  {%- assign test = armour.REDUCTION | round -%}
  {%- if test != 0 -%}
    {%- assign text = armour.REDUCTION | append: "% " | append: armour.ELEMENT -%}{::nomarkdown}{% include bar.html fill=armour.REDUCTION text=text element=armour.ELEMENT %}{:/nomarkdown}
  {%- endif -%}|
  {%- if armour.NAME contains "Moon Armour" or armour.NAME contains "Ugly Disguise" -%}
    {::nomarkdown}<ul><li>Evade encounters</li></ul>{:/nomarkdown}
  {%- elsif armour.NAME contains "Hopalong Boots" -%}
    {::nomarkdown}<ul><li>Strike first</li></ul>{:/nomarkdown}
  {%- endif -%}|
{%- endfor %}