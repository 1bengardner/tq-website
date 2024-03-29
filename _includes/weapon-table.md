{%- capture requirement -%}
  {%- case include.type -%}
    {%- when "Warrior" -%}
      Strength
    {%- when "Archer" -%}
      Dexterity
    {%- when "Mage" -%}
      Wisdom
  {%- endcase -%}
{%- endcapture -%}
{%- assign weapons-categories = site.data.weapondata | group_by: "CATEGORY" -%}

|Weapon|{{ requirement | slice: 0, 3 }}.|Accuracy|Power|Crit Chance{::nomarkdown}<colgroup><col><col style="width: 32px;"><col style="width: 10%;"><col style="width: 20%;"><col style="width: 20%;"></colgroup>{:/nomarkdown}|
|-|-|-|-|-|-|
{%- for weapons-category in weapons-categories -%}
{%- assign sorted-weapons-category = weapons-category.items | sort: "PRICE" -%}
{%- for weapon in sorted-weapons-category -%}
  {%- capture accuracy -%}
    {%- if weapon.CATEGORY == "Sword" -%}
      90
    {%- elsif weapon.CATEGORY == "Bludgeon" -%}
      80
    {%- elsif weapon.CATEGORY == "Axe" -%}
      70
    {%- elsif weapon.CATEGORY == "Spear" -%}
      60
    {%- elsif weapon.CATEGORY == "Bow" -%}
      50
    {%- elsif weapon.CATEGORY == "Wand" -%}
      100
    {%- elsif weapon.CATEGORY == "Gun" -%}
      10
    {%- endif -%}
  {%- endcapture -%}

  {% unless requirement == weapon.REQUIREMENT_TYPE -%}
    {% continue %}
  {%- endunless %}
  |{::nomarkdown}<span id="{{ weapon.NAME | downcase | replace: ' ', '-' }}" class="record-name{% if weapon.ELEMENT != "Physical" %}{{ weapon.ELEMENT | downcase | prepend: " " }}{% endif %}">{{ weapon.NAME }}</span></span>{:/nomarkdown}{%- if include.type == "Warrior" -%}<br /><span class="small-text">{{ weapon.CATEGORY }}</span>{%- endif -%}<br />![{{ weapon.NAME }}](/assets/img/weapons/{{ weapon.NAME | downcase }}.gif){:class="pixel-art"}{% include price.md price=weapon.PRICE %}{% include dropped-by.md item-name=weapon.NAME -%}
  |{{ weapon.REQUIREMENT_VALUE }}|
  {%- capture text -%}{%- if accuracy.size < 3 -%}{{ accuracy | append: "%" }}{%- else -%}Always hits{%- endif -%}{%- endcapture -%}{::nomarkdown}{% include bar.html fill=accuracy text=text %}{:/nomarkdown}|
  {%- assign fill = weapon.POWER | times: 100 | divided_by: 105 -%}{::nomarkdown}{% include bar.html fill=fill text=weapon.POWER %}{:/nomarkdown}|
  {%- assign fill = weapon.C_RATE | times: 100 | divided_by: 25 -%}{%- assign text = weapon.C_RATE | append: "%" -%}{::nomarkdown}{% include bar.html fill=fill text=text %}{:/nomarkdown}|
{%- endfor %}
{%- endfor -%}