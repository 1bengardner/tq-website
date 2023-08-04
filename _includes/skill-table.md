|Skill|EP|Effects|
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
  {%- capture relative-damage -%}
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
  {%- assign relative-damage = relative-damage | round -%}
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
  |{::nomarkdown}<span id="{{ skill.NAME | downcase | replace: ' ', '-' }}" class="record-name{% if skill.ELEMENT != "Physical" %}{{ skill.ELEMENT | downcase | prepend: " " }}{% endif %}">{{ skill.NAME }}</span>
  {%- if include.type == "Warrior" and permitted-weapons != "Melee" -%}<br /><span class="bar-descriptor">{{ permitted-weapons }} only</span>{%- endif -%}
  {%- if relative-damage > 0 -%}
    {% include bar.html fill=relative-damage text=action-word %}
  {%- endif %}{:/nomarkdown}|
  {{- skill.EP_USED }}|{::nomarkdown}<ul>{:/nomarkdown}
  {%- if skill.USER_EFFECTS != "{}" -%}
    {::nomarkdown}<li style="list-style-type: '☉'; border-left: 1px solid var(--solarized-mono1); border-radius: 0.3em; padding-left: 0.5em; margin-left: -0.5em;">User stat changes<ul style="list-style-type: none;">{:/nomarkdown}
    {%- assign effects = skill.USER_EFFECTS | remove: "{" | remove: "}" | split: ", " -%}
    {%- include skill-table-stats.md effects=effects -%}
    {::nomarkdown}</ul></li>{:/nomarkdown}
  {%- endif %}
  {%- if skill.TARGET_EFFECTS != "{}" -%}
    {::nomarkdown}<li style="list-style-type: '☍'; border-left: 1px solid var(--solarized-mono1); border-radius: 0.3em; padding-left: 0.5em; margin-left: -0.5em;">Opponent stat changes<ul style="list-style-type: none;">{:/nomarkdown}
    {%- assign effects = skill.TARGET_EFFECTS | remove: "{" | remove: "}" | split: ", " -%}
    {%- include skill-table-stats.md effects=effects -%}
    {::nomarkdown}</ul></li>{:/nomarkdown}
  {%- endif %}
  {%- if skill.USER_EFFECTS != "{}" or skill.TARGET_EFFECTS != "{}" -%}
    {%- if skill.FLAG != "None" or skill.CATEGORY != "Damage" and skill.CATEGORY != "Miscellaneous" -%}
      {::nomarkdown}</ul><ul style="margin-top: 0.5em;">{:/nomarkdown}
    {%- endif %}
  {%- endif %}
  {%- if skill.CATEGORY == "Multi-Hit Damage" -%}
    {::nomarkdown}<li>Hits {{ skill.MULTIPLIER }} times</li>{:/nomarkdown}
  {%- elsif skill.CATEGORY == "Life Steal Damage" -%}
    {::nomarkdown}<li>Heals for {{ skill.MULTIPLIER }}% of damage dealt</li>{:/nomarkdown}
  {%- elsif skill.CATEGORY == "Accurate Damage" -%}
    {::nomarkdown}<li>2x accuracy</li>{:/nomarkdown}
  {%- elsif skill.CATEGORY == "Reduced Accuracy Damage" -%}
    {::nomarkdown}<li>0.5x accuracy</li>{:/nomarkdown}
  {%- elsif skill.CATEGORY == "Critical Damage" -%}
    {::nomarkdown}<li>4x crit chance</li>{:/nomarkdown}
  {%- elsif skill.CATEGORY == "No Defence Damage" -%}
    {::nomarkdown}<li>Ignore enemy defence</li>{:/nomarkdown}
  {%- endif %}
  {%- if skill.FLAG == "Recovering" -%}
    {::nomarkdown}<li>Lose a turn after using skill</li>{:/nomarkdown}
  {%- elsif skill.FLAG != "None" -%}
    {::nomarkdown}<li>Temporary effects</li>{:/nomarkdown}
  {%- endif %}{::nomarkdown}</ul>{:/nomarkdown}|
{%- endfor %}