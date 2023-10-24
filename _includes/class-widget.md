<div class="class-widget">
  <h2 style="margin-top: 0; white-space: nowrap;"><img src="{{ include.icon-path }}" width="58px" alt="" style="margin-right: 0.25em;" />{{ include.class-name }}</h2>
  <div class="stats-grid">
    <label for="damage-bar-{{ include.class-name | downcase }}">Damage</label><meter class="damage-bar" id="damage-bar-{{ include.class-name | downcase }}" max="5" value="{{ include.damage }}">{{ include.damage }}</meter>
    <label for="resilience-bar-{{ include.class-name | downcase }}">Resilience</label><meter class="resilience-bar" id="resilience-bar-{{ include.class-name | downcase }}" max="5" value="{{ include.resilience }}">{{ include.resilience }}</meter>
    <label for="versatility-bar-{{ include.class-name | downcase }}">Versatility</label><meter class="versatility-bar" id="versatility-bar-{{ include.class-name | downcase }}" max="5" value="{{ include.versatility }}">{{ include.versatility }}</meter>
    <label for="difficulty-bar-{{ include.class-name | downcase }}">Difficulty</label><meter class="difficulty-bar" id="difficulty-bar-{{ include.class-name | downcase }}" max="5" value="{{ include.difficulty }}">{{ include.difficulty }}</meter>
  </div>
  <em>Requires {{ include.requirement }}</em>
</div>