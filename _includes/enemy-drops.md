{%- unless include.enemy.EUROS == "0" -%}
  ![Euros](/assets/img/icons/euro.gif) <span style="font-size: 1.2em; vertical-align: middle;">{{ include.enemy.EUROS -}}</span>
{%- endunless -%}
{%- unless include.enemy.ITEMS == "{}" -%}
  {%- unless include.enemy.EUROS == "0" -%}
    {::nomarkdown}<hr />{:/nomarkdown}
  {%- endunless -%}
  {%- assign items = include.enemy.ITEMS | remove: "{" | remove: "}" | replace: "\'", "&apos;" | remove: "'" | replace: "&apos;", "'" | split: ", " -%}
  {%- for item-chance in items -%}
    {%- assign drop = item-chance | split: ": " | first -%}
    {%- assign rate = item-chance | split: ": " | last -%}
    {%- for weapon in site.data.weapondata -%}
      {%- if weapon.NAME == drop -%}
        [![{{ drop }}](/assets/img/weapons/{{ drop | downcase }}.gif)](weapons#{{ drop | downcase | replace: " ", "-" }} "{{ drop }}: {{ rate }}%")
      {%- endif -%}
    {%- endfor -%}
    {%- for armour in site.data.armourdata -%}
      {%- if armour.NAME == drop -%}
        [![{{ drop }}](/assets/img/armour/{{ drop | downcase }}.gif)](armour#{{ drop | downcase | replace: " ", "-" }} "{{ drop }}: {{ rate }}%")
      {%- endif -%}
    {%- endfor -%}
    {%- for shield in site.data.shielddata -%}
      {%- if shield.NAME == drop -%}
        [![{{ drop }}](/assets/img/shields/{{ drop | downcase }}.gif)](shields#{{ drop | downcase | replace: " ", "-" }} "{{ drop }}: {{ rate }}%")
      {%- endif -%}
    {%- endfor -%}
    {%- for misc-item in site.data.miscellaneousdata -%}
      {%- if misc-item.NAME == drop -%}
        [![{{ drop }}](/assets/img/miscellaneous/{{ drop | downcase }}.gif)](miscellaneous#{{ drop | downcase | replace: " ", "-" }} "{{ drop }}: {{ rate }}%")
      {%- endif -%}
    {%- endfor -%}
  {%- endfor -%}
{%- else -%}
  {%- if include.enemy.EUROS == "0" -%}
    <span class="quiet-text">None</span>
  {%- endif -%}
{%- endunless %}