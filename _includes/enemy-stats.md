<span style="display: flex; flex: 1; white-space: nowrap; letter-spacing: -0.05em;"><span style="flex: 1; margin-right: 0.25em;"><span title="Attack"><span class="emoji">🗡</span> {{ include.enemy.damage -}}
</span><br /><span title="Defence"><span class="emoji">👕</span> {{ include.enemy.defence -}}</span><br /><span title="Accuracy"><span class="emoji">🎯</span> {% if include.enemy.accuracy == "999" -%}Always{%- else -%}{{ include.enemy.accuracy | append: "%" }}{%- endif -%}</span>
{%- if include.enemy.cRate != "0" -%}
  <br /><span title="Critical Chance"><span class="emoji">💥</span> {{ include.enemy.cRate -}}%</span>
{%- endif -%}
{%- if include.enemy.bRate != "0" -%}
  <br /><span title="Block Chance"><span class="emoji">🛡</span> {{ include.enemy.bRate -}}%</span>
{%- endif -%}</span><span style="margin-left: 0.5em;">
{%- if include.enemy.earthReduction != "0" -%}
  <span title="Earth Reduction"><span class="emoji">🌳</span> {% if include.enemy.earthReduction == "999" -%}Immune{%- else -%}{{ include.enemy.earthReduction | append: "%" }}{%- endif -%}<br />
{%- endif -%}
{%- if include.enemy.waterReduction != "0" -%}
  <span title="Water Reduction"><span class="emoji">🌊</span> {% if include.enemy.waterReduction == "999" -%}Immune{%- else -%}{{ include.enemy.waterReduction | append: "%" }}{%- endif -%}<br />
{%- endif -%}
{%- if include.enemy.fireReduction != "0" -%}
  <span title="Fire Reduction"><span class="emoji">🔥</span> {% if include.enemy.fireReduction == "999" -%}Immune{%- else -%}{{ include.enemy.fireReduction | append: "%" }}{%- endif -%}<br />
{%- endif -%}
{%- if include.enemy.physicalReduction != "0" -%}
  <span title="Physical Reduction"><span class="emoji">🪨</span> {{ include.enemy.physicalReduction -}}%</span>
{%- endif -%}</span></span>