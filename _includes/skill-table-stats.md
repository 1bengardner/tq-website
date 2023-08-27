{%- for effect in include.effects -%}
  {%- capture abbr -%}
    {{ effect | remove: "'" | split: ": " | first }}
  {%- endcapture -%}
  {%- capture name -%}
    {%- if abbr == "hp" -%} SPACER HP
    {%- elsif abbr == "maxHp" -%} SPACER max HP
    {%- elsif abbr == "ep" -%} SPACER EP
    {%- elsif abbr == "maxEp" -%} SPACER max EP
    {%- elsif abbr == "damage" -%} SPACER damage
    {%- elsif abbr == "cDamage" -%} % critical damage
    {%- elsif abbr == "accuracy" -%} % accuracy
    {%- elsif abbr == "cRate" -%} % critical chance
    {%- elsif abbr == "bRate" -%} % block chance
    {%- elsif abbr == "earthReduction" -%} % earth reduction
    {%- elsif abbr == "waterReduction" -%} % water reduction
    {%- elsif abbr == "fireReduction" -%} % fire reduction
    {%- elsif abbr == "physicalReduction" -%} % physical damage reduction
    {%- elsif abbr == "defence" -%} SPACER defence
    {%- endif -%}
  {%- endcapture -%}
  {%- capture value -%}
    {{ effect | split: ": " | last }}        
  {%- endcapture -%}
  {%- assign value = value | round -%}
  {::nomarkdown}<li>{% if value >= 0 %}+{% endif %}{{ value }}{{ name | remove: "SPACER" }}{%- if value < 0 and abbr == "accuracy" -%}<a href="#legend">*</a>{%- endif -%}</li>{:/nomarkdown}
{%- endfor -%}