<style>@import url('https://fonts.googleapis.com/css2?family=Noto+Color+Emoji&display=swap');</style>
<style>tbody > tr { vertical-align: top; }</style>

|Enemy|Stats|Drops{::nomarkdown}<colgroup><col><col style="width: 25%;"><col style="width: 360px;"></colgroup>{:/nomarkdown}|
|-|-|-|
{% assign sorted-enemies = site.data.enemydata | group_by: "LEVEL" | sort: "name" -%}
{%- for enemy-group in sorted-enemies -%}
  {% assign enemies-by-level = enemy-group.items | sort: "XP" -%}
  {% for enemy in enemies-by-level %}
    {%- if enemy.IDENTIFIER contains "Unfleeable" -%}
      {%- continue -%}
    {%- endif -%}
    {%- capture border-color -%}
      {%- if enemy.RARITY == "COMMON" -%}
        #d1c29d
      {%- endif -%}
      {%- if enemy.RARITY == "RARE" -%}
        #ffe790
      {%- endif -%}
      {%- if enemy.RARITY == "LEGENDARY" -%}
        #ffffc0
      {%- endif -%}
    {%- endcapture -%}
    |<span class="enemy-level" title="Level">{{ enemy.LEVEL }}</span><span id="{{ enemy.IDENTIFIER | downcase | replace: ' ', '-' }}" class="record-name">{{ enemy.NAME }}</span><br /><span title="HP"><span class="emoji">❤</span> {{ enemy.hp | thousands_separated }}</span>
    {%- if enemy.LIVING == "1" -%}
      <span title="Drops potions" class="emoji" style="font-size: 0.5em; vertical-align: super;"> 🩸</span>
    {%- endif -%}
    <br /><img class="enemy-image" style="border-color: {{ border-color }};" alt="{{ enemy.NAME }}" src="/assets/img/enemies/{{ enemy.IMAGE | downcase }}.gif" />|
    {%- include enemy-stats.md enemy=enemy -%}|
    {%- include enemy-drops.md enemy=enemy -%}|
  {% endfor %}
{%- endfor -%}