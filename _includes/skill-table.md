|Skill|EP|Special Notes|
|-|-|-|
{%- for skill in site.data.skilldata -%}
  {%- capture visible -%}
    {%- if include.type == "Warrior" -%}
      {%- unless skill.PERMITTED_WEAPONS contains "Bow" or skill.PERMITTED_WEAPONS contains "Wand" or skill.PERMITTED_WEAPONS contains "All" -%}
        true
      {%- endunless -%}
    {%- elsif include.type == "Archer" and skill.PERMITTED_WEAPONS contains "Bow" -%}
      true
    {%- elsif include.type == "Mage" and skill.PERMITTED_WEAPONS contains "Wand" -%}
      true
    {%- elsif include.type == "Miscellaneous" and skill.PERMITTED_WEAPONS contains "All" -%}
      true
    {%- endif -%}
  {%- endcapture -%}
  {%- capture damage -%}
    {%- if skill.CATEGORY == "Multi-Hit Damage" -%}
      {{ skill.MULTIPLIER | times: 100 | divided_by: 10 }}
    {%- elsif skill.CATEGORY contains "Heal" -%}
      {{ skill.MULTIPLIER | times: 100 | divided_by: 100 }}
    {%- elsif skill.CATEGORY == "Life Steal Damage" -%}
      {{ 100 | times: 100 | divided_by: 750 }}
    {%- else -%}
      {{ skill.MULTIPLIER | times: 100 | divided_by: 750 }}
    {%- endif %}
  {%- endcapture -%}
  {%- assign damage = damage | round -%}
  {%- capture action-word -%}
    {%- if skill.CATEGORY contains "Heal" -%}
      Healing
    {%- else -%}
      Damage
    {%- endif -%}
  {%- endcapture -%}
  {%- assign permitted-weapons = skill.PERMITTED_WEAPONS | remove: "'" | remove: "{" | remove: "}" | replace: ", ", " and " -%}
  
  {% unless visible == "true" -%}
    {% continue %}
  {%- endunless %}
  |{::nomarkdown}<span class="{{ skill.ELEMENT | downcase }}"><span class="record-name">{{ skill.NAME }}</span></span>
  {%- if include.type == "Warrior" and permitted-weapons != "Melee" -%}<br /><span class="bar-descriptor">{{ permitted-weapons }} only</span>{%- endif -%}
  {%- if damage > 0 -%}
    <div class="bar"><span class="bar-fill" style="width:{{ damage }}%;"></span></div><span class="bar-descriptor">{{ action-word }}</span>
  {%- endif %}{:/nomarkdown}|
  {{- skill.EP_USED }}|
  {%- if skill.CATEGORY == "Multi-Hit Damage" -%}
    - Hits {{ skill.MULTIPLIER }} times<br />
  {%- elsif skill.CATEGORY == "Life Steal Damage" -%}
    - Heals for {{ skill.MULTIPLIER }}% of damage dealt<br />
  {%- elsif skill.CATEGORY == "Accurate Damage" -%}
    - Accuracy is doubled while using this skill<br />
  {%- elsif skill.CATEGORY == "Reduced Accuracy Damage" -%}
    - Accuracy is halved while using this skill<br />
  {%- elsif skill.CATEGORY == "Critical Damage" -%}
    - Critical chance is quadrupled while using this skill<br />
  {%- elsif skill.CATEGORY == "No Defence Damage" -%}
    - Enemy defence is reduced by two thirds while using this skill<br />
  {%- endif %}
  {%- if skill.USER_EFFECTS != "{}" -%}
    - Alters user stats<br />
  {%- endif %}
  {%- if skill.TARGET_EFFECTS != "{}" -%}
    - Alters enemy stats<br />
  {%- endif %}
  {%- if skill.FLAG == "Recovering" -%}
    - Lose a turn after using skill<br />
  {%- endif %}|
{%- endfor %}