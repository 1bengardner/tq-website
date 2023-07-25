|Item|Description|
|-|-|
{%- for item in site.data.miscellaneousdata -%}
  {%- capture consumable -%}
    {%- if item.NAME contains "Mushroom" or item.NAME contains "Psilocybin" or item.NAME contains "The good stuff" or item.NAME contains "Leaf" or item.NAME contains "Mint" -%}
      true
    {%- endif -%}
  {%- endcapture -%}
  {%- capture for-crafting -%}
    {%- if item.NAME contains "Horn" or item.NAME contains "Ore" or item.NAME contains "Bar" or item.NAME contains "Crystal" or item.NAME contains "Shard" or item.NAME contains "Fragment" -%}
      true
    {%- endif -%}
  {%- endcapture -%}
  {%- capture reward -%}
    {%- if item.PRICE != "?" and item.NAME != "Ominous Orb" and item.NAME contains "Orb" or item.NAME contains "Platinum Ball" or item.NAME contains "Gumball of Power" -%}
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
      {%- unless item.PRICE == "?" -%}
        {%- continue -%}
      {%- endunless -%}
    {%- when "Ring" -%}
      {%- unless item.NAME contains "Ring" -%}
        {%- continue -%}
      {%- endunless -%}
    {%- when "Reward" -%}
      {%- unless reward == "true" -%}
        {%- continue -%}
      {%- endunless -%}
    {%- when "Other Item" -%}
      {%- if consumable == "true" or item.PRICE == "?" or item.NAME contains "Ring" or for-crafting == "true" or reward == "true" -%}
        {%- continue -%}
      {%- endif -%}
  {%- endcase %}
  |{::nomarkdown}<span class="record-name">{{ item.NAME }}</span>{:/nomarkdown}<br />![{{ item.NAME }}](/assets/img/miscellaneous/{{ item.NAME | downcase }}.gif)<br />{% include price.md price=item.PRICE %}|{{ item.INFO | replace: "*", " " }}|
{%- endfor -%}