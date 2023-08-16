|Item|Description|
|-|-|
{%- for misc-item in site.data.miscellaneousitemdata -%}
  {%- capture consumable -%}
    {%- if misc-item.NAME contains "Mushroom" or misc-item.NAME contains "Psilocybin" or misc-item.NAME contains "The good stuff" or misc-item.NAME contains "Leaf" or misc-item.NAME contains "Mint" or misc-item.NAME contains "Pear" or misc-item.NAME contains "Boulderwort" or misc-item.NAME contains "Snowdrops" -%}
      true
    {%- endif -%}
  {%- endcapture -%}
  {%- capture for-crafting -%}
    {%- if misc-item.NAME contains "Horn" or misc-item.NAME contains "Ore" or misc-item.NAME contains "Bar" or misc-item.NAME contains "Crystal" or misc-item.NAME contains "Shard" or misc-item.NAME contains "Fragment" -%}
      true
    {%- endif -%}
  {%- endcapture -%}
  {%- capture quest-item -%}
    {%- if misc-item.NAME contains "Key" or misc-item.NAME contains "Letter" or misc-item.NAME contains "Parchment" or misc-item.NAME contains "Map" or misc-item.NAME contains "Blueprint" or misc-item.NAME == "Oracular Orb" -%}
      true
    {%- endif -%}
  {%- endcapture -%}
  {%- capture reward -%}
    {%- if quest-item != "true" and misc-item.NAME != "Ominous Orb" and misc-item.NAME contains "Orb" or misc-item.NAME contains "Platinum Ball" or misc-item.NAME contains "Gumball of Power" -%}
      true
    {%- endif -%}
  {%- endcapture -%}
  {%- case include.type -%}
    {%- when "Consumable" -%}
      {%- unless consumable == "true" -%}
        {%- continue -%}
      {%- endunless -%}
    {%- when "Materials" -%}
      {%- unless for-crafting == "true" -%}
        {%- continue -%}
      {%- endunless -%}
    {%- when "Quest Item" -%}
      {%- unless quest-item == "true" -%}
        {%- continue -%}
      {%- endunless -%}
    {%- when "Ring" -%}
      {%- unless misc-item.NAME contains "Ring" -%}
        {%- continue -%}
      {%- endunless -%}
    {%- when "Reward" -%}
      {%- unless reward == "true" -%}
        {%- continue -%}
      {%- endunless -%}
    {%- when "Other Item" -%}
      {%- if consumable == "true" or quest-item == "true" or misc-item.NAME contains "Ring" or for-crafting == "true" or reward == "true" -%}
        {%- continue -%}
      {%- endif -%}
  {%- endcase %}
  |{::nomarkdown}<span id="{{ misc-item.NAME | downcase | replace: ' ', '-' }}" class="record-name">{{ misc-item.NAME }}</span>{:/nomarkdown}<br />![{{ misc-item.NAME }}](/assets/img/miscellaneous/{{ misc-item.NAME | downcase }}.gif){% include price.md price=misc-item.PRICE %}{% include dropped-by.md item-name=misc-item.NAME -%}
  |{{ misc-item.INFO | replace: "*", " " }}|
{%- endfor -%}