<style>@import url('https://fonts.googleapis.com/css2?family=Noto+Color+Emoji&display=swap');</style>
<style>tbody > tr { vertical-align: top; }</style>

|Enemy|Stats|Drops{::nomarkdown}<colgroup><col><col style="width: 25%;"><col style="width: 360px;"></colgroup>{:/nomarkdown}|
|-|-|-|
{% assign sorted-enemies = site.data.enemydata | sort: "LEVEL" -%}
{% for enemy in sorted-enemies %}
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
  {%- endcapture -%}|<span id="{{ enemy.IDENTIFIER | downcase | replace: ' ', '-' }}" class="record-name">{{ enemy.NAME }}</span><span style="float: right; border: ridge #7bb4b9 2px; width: 2em; line-height: 2em; text-align: center; font-size: 1.2em;" title="Level">{{ enemy.LEVEL }}</span><br /><span title="HP"><span class="emoji">❤</span> {{ enemy.hp }}</span>
  {%- if enemy.LIVING == "1" -%}
    <span title="Drops potions" class="emoji" style="font-size: 0.5em; vertical-align: super;"> 🩸</span>
  {%- endif -%}
  <br /><img style="display: block; margin: auto; border: 4px ridge {{ border-color }};" alt="{{ enemy.NAME }}" src="/assets/img/enemies/{{ enemy.IMAGE | downcase }}.gif" />|{% include enemy-stats.md enemy=enemy %}|{%- include enemy-drops.md enemy=enemy -%}|
{% endfor %}