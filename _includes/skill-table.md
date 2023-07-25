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
  |{::nomarkdown}<span class="record-name{% if skill.ELEMENT != "Physical" %}{{ skill.ELEMENT | downcase | prepend: " " }}{% endif %}">{{ skill.NAME }}</span>
  {%- if include.type == "Warrior" and permitted-weapons != "Melee" -%}<br /><span class="bar-descriptor">{{ permitted-weapons }} only</span>{%- endif -%}
  {%- if relative-damage > 0 -%}
    {% include bar.html fill=relative-damage text=action-word %}
  {%- endif %}{:/nomarkdown}|
  {{- skill.EP_USED }}|
  {%- if skill.USER_EFFECTS != "{}" -%}
    {::nomarkdown}<ul><li>Attacker stat changes:<ul>{:/nomarkdown}
    {%- assign effects = skill.USER_EFFECTS | remove: "{" | remove: "}" | split: ", " -%}
    {%- include skill-table-stats.md effects=effects -%}
    {::nomarkdown}</ul></li></ul>{:/nomarkdown}
  {%- endif %}
  {%- if skill.TARGET_EFFECTS != "{}" -%}
    {::nomarkdown}<ul><li>Defender stat changes:<ul>{:/nomarkdown}
    {%- assign effects = skill.TARGET_EFFECTS | remove: "{" | remove: "}" | split: ", " -%}
    {%- include skill-table-stats.md effects=effects -%}
    {::nomarkdown}</ul></li></ul>{:/nomarkdown}
  {%- endif %}
  {%- if skill.CATEGORY == "Multi-Hit Damage" -%}
    {::nomarkdown}<ul><li>Hits {{ skill.MULTIPLIER }} times</li></ul>{:/nomarkdown}
  {%- elsif skill.CATEGORY == "Life Steal Damage" -%}
    {::nomarkdown}<ul><li>Heals for {{ skill.MULTIPLIER }}% of damage dealt</li></ul>{:/nomarkdown}
  {%- elsif skill.CATEGORY == "Accurate Damage" -%}
    {::nomarkdown}<ul><li>2x accuracy</li></ul>{:/nomarkdown}
  {%- elsif skill.CATEGORY == "Reduced Accuracy Damage" -%}
    {::nomarkdown}<ul><li>0.5x accuracy</li></ul>{:/nomarkdown}
  {%- elsif skill.CATEGORY == "Critical Damage" -%}
    {::nomarkdown}<ul><li>4x crit chance</li></ul>{:/nomarkdown}
  {%- elsif skill.CATEGORY == "No Defence Damage" -%}
    {::nomarkdown}<ul><li>Ignore enemy defence</li></ul>{:/nomarkdown}
  {%- endif %}
  {%- if skill.FLAG == "Recovering" -%}
    {::nomarkdown}<ul><li>Lose a turn after using skill</li></ul>{:/nomarkdown}
  {%- endif %}|
{%- endfor %}