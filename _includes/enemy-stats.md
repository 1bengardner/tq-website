<span style="display: flex; flex: 1;"><span style="flex: 1;"><span title="Attack"><span class="emoji">🗡</span> {{ include.enemy.damage -}}
</span><br /><span title="Defence"><span class="emoji">👕</span> {{ include.enemy.defence -}}</span>
{%- assign accuracy = include.enemy.accuracy | round -%}
<br /><span title="Accuracy"><span class="emoji">🎯</span> {% if accuracy < 999 -%}{{ include.enemy.accuracy | append: "%" }}{%- else -%}Always{%- endif -%}</span>
{%- if include.enemy.cRate != "0" -%}
  <br /><span title="Critical Chance"><span class="emoji">💥</span> {{ include.enemy.cRate -}}%</span>
{%- endif -%}
{%- if include.enemy.bRate != "0" -%}
  <br /><span title="Block Chance"><span class="emoji">🛡</span> {{ include.enemy.bRate -}}%</span>
{%- endif -%}</span><span>
{%- if include.enemy.earthReduction != "0" -%}
  <span title="Earth Reduction"><span class="emoji">🪨</span> {{ include.enemy.earthReduction -}}%</span><br />
{%- endif -%}
{%- if include.enemy.waterReduction != "0" -%}
  <span title="Water Reduction"><span class="emoji">💧</span> {{ include.enemy.waterReduction -}}%</span><br />
{%- endif -%}
{%- if include.enemy.fireReduction != "0" -%}
  <span title="Fire Reduction"><span class="emoji">🔥</span> {{ include.enemy.fireReduction -}}%</span><br />
{%- endif -%}
{%- if include.enemy.physicalReduction != "0" -%}
  <span title="Physical Reduction"><span class="emoji">🧱</span> {{ include.enemy.physicalReduction -}}%</span>
{%- endif -%}</span></span>