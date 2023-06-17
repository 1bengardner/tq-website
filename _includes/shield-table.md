|Shield|Str.|Defence|Block Chance|Reduction|
|-|-|-|-|-|
{%- assign sorted-shields = site.data.shielddata | sort: "PRICE" -%}
{%- for shield in sorted-shields %}
  |{::nomarkdown}<span class="{{ shield.ELEMENT | downcase }}"><span class="record-name">{{ shield.NAME }}</span></span>{:/nomarkdown}<br />![{{ shield.NAME | downcase }}](/assets/img/shields/{{ shield.NAME }}.gif)|{{ shield.REQUIREMENT_VALUE }}|
  {%- assign fill = shield.DEFENCE | times: 100 | divided_by: 40 -%}{::nomarkdown}{% include bar.html fill=fill text=shield.DEFENCE %}{:/nomarkdown}|
  {%- assign fill = shield.B_RATE | times: 100 | divided_by: 11 -%}
  {%- assign text = shield.B_RATE | append: "%" -%}{::nomarkdown}{% include bar.html fill=fill text=text %}{:/nomarkdown}|
  {%- assign test = shield.REDUCTION | round -%}
  {%- if test > 0 -%}
    {%- assign text = shield.REDUCTION | append: "% " | append: shield.ELEMENT -%}{::nomarkdown}{% include bar.html fill=shield.REDUCTION text=text %}{:/nomarkdown}
  {%- endif -%}|
{%- endfor %}