|Shield|Str.|Defence|Block Chance<br />{::nomarkdown}<span class="bar-descriptor">Max. 11%</span>{:/nomarkdown}|Reduction|
|-|-|-|-|-|
{%- assign sorted-shields = site.data.shielddata | sort: "PRICE" -%}
{%- for shield in sorted-shields %}
  |{::nomarkdown}<span class="record-name">{{ shield.NAME }}</span>{:/nomarkdown}<br />![{{ shield.NAME }}](/assets/img/shields/{{ shield.NAME | downcase }}.gif)<br />{% include price.md price=shield.PRICE %}|{{ shield.REQUIREMENT_VALUE }}|
  {%- assign fill = shield.DEFENCE | times: 100 | divided_by: 40 -%}{::nomarkdown}{% include bar.html fill=fill text=shield.DEFENCE %}{:/nomarkdown}|
  {%- assign fill = shield.B_RATE | times: 100 | divided_by: 11 -%}
  {%- assign text = shield.B_RATE | append: "%" -%}{::nomarkdown}{% include bar.html fill=fill text=text %}{:/nomarkdown}|
  {%- assign test = shield.REDUCTION | round -%}
  {%- if test > 0 -%}
    {%- assign text = shield.REDUCTION | append: "% " | append: shield.ELEMENT -%}{::nomarkdown}{% include bar.html fill=shield.REDUCTION text=text element=shield.ELEMENT %}{:/nomarkdown}
  {%- endif -%}|
{%- endfor %}