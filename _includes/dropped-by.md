{%- assign sorted-enemies = site.data.enemydata | sort: "LEVEL" -%}
{%- capture droppers-string -%}
{%- for enemy in sorted-enemies -%}
  {%- if enemy.ITEMS == "{}" -%}
    {%- continue -%}
  {%- endif -%}
  {%- assign items = enemy.ITEMS | remove: "{" | remove: "}" | replace: "\'", "&apos;" | remove: "'" | replace: "&apos;", "'" | split: ", " -%}
  {%- for item-chance in items -%}
    {%- assign item = item-chance | split: ": " | first -%}
    {%- if item == include.item-name -%}
      {{ enemy.NAME }},
    {%- endif -%}
  {%- endfor -%}
{%- endfor -%}
{%- endcapture -%}
{%- assign droppers = droppers-string | split: "," | uniq -%}
{%- if droppers.size > 0 -%}
  <br />{::nomarkdown}<details><summary class="bar-descriptor">Dropped by</summary><ul>
  {%- for dropper in droppers -%}
    <li>{:/nomarkdown}[{{ dropper }}](enemies#{{ dropper | downcase | replace: " ", "-" }}){::nomarkdown}</li>
  {%- endfor -%}
  </details>{:/nomarkdown}
{%- endif -%}