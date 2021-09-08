## Consumeables (Class = 0)

- ### Consumable (subclass = 0)
  There are lots of ilvl 60 classic items, and lots more TBC items that have no ilvl. Highest ID for classic 65 items is 23796 for perm. swift. of sheen. However, some overlap - Fel Blossoms are ilvl 65 with item id 22795. Only 3 vanilla items > 60 though, and they may not even be in game. So cutoff >= 61 + manually adding 58-60 TBC items works. 
  List of TBC items 55-60: stouthammer lite 23585, grunt's waterskin 24006, footman's waterskin 24007, brewfest items: should skip (stout shrunken head 34022, Pickled Sausage 33024, Thunderbrew Stout 33033), DMF sells Iced Berry Slush 33234 - mark of honor hold 24579, mark of thrallmar 24581, honor hold favor 24520, thrallmar favor 24522, chronoboon displacer 184937, primal stone statue 25884, supercharged chronoboon displacer 184938, + 4 bombs that are quest items so not really useful anyway.

  So query becomes:
  
  ```SQL
  SELECT it.entry, it.name, it.itemlevel
  FROM `item_template` it
  WHERE it.class = 0 AND it.subclass = 0
  AND it.itemlevel >= 61 AND it.entry >= 22044
  ```

  <details>
  <summary>Query results</summary>
 
  ---
  | entry | name | itemlevel | 
  | ---: | --- | ---: | 
  | 22044 | Mana Emerald | 68 | 
  | 22116 | Master Soulstone | 70 | 
  | 22795 | Fel Blossom | 65 | 
  | 24429 | Expedition Flare | 64 | 
  | 27388 | Mr. Pinchy | 70 | 
  | 29482 | Ethereum Essence | 65 | 
  | 29778 | Phase Disruptor | 70 | 
  | 30690 | Power Converter | 108 | 
  | 31337 | Orb of the Blackwhelp | 70 | 
  | 31449 | Distilled Stalker Sight | 102 | 
  | 31450 | Stealth of the Stalker | 102 | 
  | 31451 | Pure Energy | 102 | 
  | 31535 | Bloodboil Poison | 105 | 
  | 33025 | Spicy Smoked Sausage | 65 | 
  | 33026 | The Golden Link | 75 | 
  | 33034 | Gordok Grog | 65 | 
  | 33035 | Ogre Mead | 75 | 
  | 33036 | Mudder's Milk | 75 | 
  | 33236 | Fizzy Faire Drink "Classic" | 70 | 
  | 33246 | Funnel Cake | 65 | 
  | 33254 | Afrazi Forest Strider Drumstick | 75 | 
  | 33312 | Mana Sapphire | 77 | 
  | 34024 | Flask of Vrykul Blood | 70 | 
  | 34410 | Honeyed Holiday Ham | 75 | 
  | 34475 | Arcane Charges | 70 | 
  | 35945 | Brilliant Glass | 70 | 
  | 36895 | Demonic Soulstone | 76 | 
  | 39738 | Thunderbrew's Hard Ale | 75 | 
  | 40725 | Steam-Powered Auctioneer | 80 | 
  | 42436 | Chocolate Celebration Cake | 75 | 
  | 42438 | Lovely Cake | 85 | 
  | 42439 | Big Berry Pie | 75 | 
  | 43088 | Dalaran Apple Bowl | 85 | 
  | 43135 | Fate Rune of Fleet Feet | 80 | 
  | 44610 | Fresh Dalaran Bread | 75 | 
  | 44612 | Dalaran Swiss Wheel | 75 | 
  | 44613 | Aged Dalaran Sharp Wheel | 85 | 
  | 44621 | Bottle of Dalaran White | 70 | 
  | 44622 | Cask of Dalaran White | 70 | 
  | 44623 | Bottle of Dalaran Red | 70 | 
  | 44625 | Bottle of Aged Dalaran Red | 70 | 
  | 44626 | Cask of Aged Dalaran Red | 70 | 
  | 44627 | Bottle of Peaked Dalaran Red | 70 | 
  | 44629 | Cask of Peaked Dalaran Red | 70 | 
  | 44632 | Cask of Dalaran Red | 70 | 
  | 44698 | Intravenous Healing Potion | 85 | 
  | 44943 | Icy Prism | 80 | 
  | 45038 | Fragment of Val'anyr | 80 | 
  | 45126 | Trusty Mount [PH] | 80 | 
  | 45705 | Argent Tournament Invitation | 80 | 
  | 46399 | Thunder's Plunder | 85 | 
  | 46400 | Barleybrew Gold | 85 | 
  | 46401 | Crimson Stripe | 85 | 
  | 46402 | Promise of the Pandaren | 85 | 
  | 46403 | Chuganpug's Delight | 85 | 
  | 46847 | Seaforium Bombs | 70 | 
  | 47030 | Huge Seaforium Bombs | 70 | 
  | 47541 | Argent Pony Bridle | 78 | 

  </details>

  Results: 

  22044, 22116, 22795, 24429, 27388, 29482, 29778, 30690, 31337, 31449, 31450, 31451, 31535, 33025, 33026, 33034, 33035, 33036, 33236, 33246, 33254, 33312, 34024, 34410, 34475, 35945, 36895, 39738, 40725, 42436, 42438, 42439, 43088, 43135, 44610, 44612, 44613, 44621, 44622, 44623, 44625, 44626, 44627, 44629, 44632, 44698, 44943, 45038, 45126, 45705, 46399, 46400, 46401, 46402, 46403, 46847, 47030, 47541, 23585, 24006, 24007, 24579, 24581, 24520, 24522, 184937, 25884, 184938

<hr>

- ### Potion (subclass = 1)
   Item level >= 60 is fine except for 3 classic items - Flask of Petrification, major rejuv potion, greater dreamless sleep potion. These all have entries <= 20002, so setting 21000 as entry cutoff works.

  ```SQL
  SELECT it.entry, it.name,it.ItemLevel
  FROM `item_template` it
  WHERE it.class = 0 AND it.subclass = 1
  AND it.itemlevel >= 60 AND it.entry > 21000
  ```

  <details>
   <summary>Results</summary>

  | entry | name | ItemLevel | 
  | ---: | --- | ---: | 
  | 22826 | Sneaking Potion | 63 | 
  | 22828 | Insane Strength Potion | 64 | 
  | 22829 | Super Healing Potion | 65 | 
  | 22832 | Super Mana Potion | 68 | 
  | 22836 | Major Dreamless Sleep Potion | 70 | 
  | 22837 | Heroic Potion | 70 | 
  | 22838 | Haste Potion | 70 | 
  | 22839 | Destruction Potion | 70 | 
  | 22841 | Major Fire Protection Potion | 70 | 
  | 22842 | Major Frost Protection Potion | 70 | 
  | 22844 | Major Nature Protection Potion | 70 | 
  | 22845 | Major Arcane Protection Potion | 70 | 
  | 22846 | Major Shadow Protection Potion | 70 | 
  | 22847 | Major Holy Protection Potion | 70 | 
  | 22849 | Ironshield Potion | 73 | 
  | 22850 | Super Rejuvenation Potion | 75 | 
  | 22871 | Shrouding Potion | 67 | 
  | 23822 | Healing Potion Injector | 66 | 
  | 23823 | Mana Potion Injector | 69 | 
  | 28100 | Volatile Healing Potion | 60 | 
  | 28101 | Unstable Mana Potion | 62 | 
  | 31676 | Fel Regeneration Potion | 69 | 
  | 31677 | Fel Mana Potion | 72 | 
  | 31838 | Major Combat Healing Potion | 70 | 
  | 31839 | Major Combat Healing Potion | 70 | 
  | 31840 | Major Combat Mana Potion | 70 | 
  | 31841 | Major Combat Mana Potion | 70 | 
  | 31852 | Major Combat Healing Potion | 70 | 
  | 31853 | Major Combat Healing Potion | 70 | 
  | 31854 | Major Combat Mana Potion | 70 | 
  | 31855 | Major Combat Mana Potion | 70 | 
  | 32762 | Rulkster's Brain Juice | 68 | 
  | 32763 | Rulkster's Secret Sauce | 65 | 
  | 32783 | Blue Ogre Brew | 70 | 
  | 32784 | Red Ogre Brew | 70 | 
  | 32840 | Major Arcane Protection Potion | 70 | 
  | 32844 | Major Nature Protection Potion | 70 | 
  | 32845 | Major Shadow Protection Potion | 70 | 
  | 32846 | Major Fire Protection Potion | 70 | 
  | 32847 | Major Frost Protection Potion | 70 | 
  | 32902 | Bottled Nethergon Energy | 68 | 
  | 32903 | Cenarion Mana Salve | 68 | 
  | 32904 | Cenarion Healing Salve | 65 | 
  | 32905 | Bottled Nethergon Vapor | 65 | 
  | 32909 | Blue Ogre Brew Special | 70 | 
  | 32910 | Red Ogre Brew Special | 70 | 
  | 32947 | Auchenai Healing Potion | 65 | 
  | 32948 | Auchenai Mana Potion | 68 | 
  | 33092 | Healing Potion Injector | 66 | 
  | 33093 | Mana Potion Injector | 69 | 
  | 33447 | Runic Healing Potion | 80 | 
  | 33448 | Runic Mana Potion | 80 | 
  | 33934 | Crystal Healing Potion | 60 | 
  | 33935 | Crystal Mana Potion | 62 | 
  | 34440 | Mad Alchemist's Potion | 75 | 
  | 38351 | Murliver Oil | 70 | 
  | 39327 | Noth's Special Brew | 65 | 
  | 39671 | Resurgent Healing Potion | 75 | 
  | 40067 | Icy Mana Potion | 75 | 
  | 40077 | Crazy Alchemist's Potion | 80 | 
  | 40081 | Potion of Nightmares | 80 | 
  | 40087 | Powerful Rejuvenation Potion | 80 | 
  | 40093 | Indestructible Potion | 80 | 
  | 40211 | Potion of Speed | 80 | 
  | 40212 | Potion of Wild Magic | 80 | 
  | 40213 | Mighty Arcane Protection Potion | 80 | 
  | 40214 | Mighty Fire Protection Potion | 80 | 
  | 40215 | Mighty Frost Protection Potion | 80 | 
  | 40216 | Mighty Nature Protection Potion | 80 | 
  | 40217 | Mighty Shadow Protection Potion | 80 | 
  | 41166 | Runic Healing Injector | 80 | 
  | 42545 | Runic Mana Injector | 80 | 
  | 43530 | Argent Mana Potion | 68 | 
  | 43531 | Argent Healing Potion | 65 | 
  | 43569 | Endless Healing Potion | 80 | 
  | 43570 | Endless Mana Potion | 80 | 
  | 44728 | Endless Rejuvenation Potion | 80 | 
  | 45276 | Jillian's Genius Juice | 68 | 
  | 45277 | Jillian's Savior Sauce | 65 | 

  </details>

  Results: 

  22826, 22828, 22829, 22832, 22836, 22837, 22838, 22839, 22841, 22842, 22844, 22845, 22846, 22847, 22849, 22850, 22871, 23822, 23823, 28100, 28101, 31676, 31677, 31838, 31839, 31840, 31841, 31852, 31853, 31854, 31855, 32762, 32763, 32783, 32784, 32840, 32844, 32845, 32846, 32847, 32902, 32903, 32904, 32905, 32909, 32910, 32947, 32948, 33092, 33093, 33447, 33448, 33934, 33935, 34440, 38351, 39327, 39671, 40067, 40077, 40081, 40087, 40093, 40211, 40212, 40213, 40214, 40215, 40216, 40217, 41166, 42545, 43530, 43531, 43569, 43570, 44728, 45276, 45277

<hr>

- ### Elixir (subclass = 2)
  There are 3 ilvl 65 elixirs in Z'G - Swiftness/Spirit/Sheen of Zanza. However, all 3 are miscategorized on AC as consumeables (subclass 0) so are not included here. Item level >= 60 works fine otherwise.

  ```SQL
  SELECT it.entry, it.name,it.ItemLevel
  FROM `item_template` it
  WHERE it.class = 0 AND it.subclass = 2
  AND it.itemlevel >= 60 
  ```

  <details>
  <summary>Results</summary>

  | entry | name | ItemLevel | 
  | ---: | --- | ---: | 
  | 22823 | Elixir of Camouflage | 61 | 
  | 22824 | Elixir of Major Strength | 61 | 
  | 22825 | Elixir of Healing Power | 61 | 
  | 22827 | Elixir of Major Frost Power | 64 | 
  | 22830 | Elixir of the Searching Eye | 65 | 
  | 22831 | Elixir of Major Agility | 66 | 
  | 22833 | Elixir of Major Firepower | 64 | 
  | 22834 | Elixir of Major Defense | 69 | 
  | 22835 | Elixir of Major Shadow Power | 70 | 
  | 22840 | Elixir of Major Mageblood | 70 | 
  | 22848 | Elixir of Empowerment | 70 | 
  | 25539 | Potion of Water Breathing | 60 | 
  | 28102 | Onslaught Elixir | 60 | 
  | 28103 | Adept's Elixir | 60 | 
  | 28104 | Elixir of Mastery | 63 | 
  | 31679 | Fel Strength Elixir | 67 | 
  | 32062 | Elixir of Major Fortitude | 61 | 
  | 32063 | Earthen Elixir | 63 | 
  | 32067 | Elixir of Draenic Wisdom | 64 | 
  | 32068 | Elixir of Ironskin | 66 | 
  | 34537 | Bloodberry Elixir | 70 | 
  | 37449 | Breath of Murloc | 60 | 
  | 39666 | Elixir of Mighty Agility | 80 | 
  | 40068 | Wrath Elixir | 80 | 
  | 40070 | Spellpower Elixir | 80 | 
  | 40072 | Elixir of Spirit | 80 | 
  | 40073 | Elixir of Mighty Strength | 80 | 
  | 40076 | Guru's Elixir | 80 | 
  | 40078 | Elixir of Mighty Fortitude | 80 | 
  | 40097 | Elixir of Protection | 80 | 
  | 40109 | Elixir of Mighty Mageblood | 80 | 
  | 44012 | Underbelly Elixir | 70 | 
  | 44325 | Elixir of Accuracy | 80 | 
  | 44327 | Elixir of Deadly Strikes | 80 | 
  | 44328 | Elixir of Mighty Defense | 80 | 
  | 44329 | Elixir of Expertise | 80 | 
  | 44330 | Elixir of Armor Piercing | 80 | 
  | 44331 | Elixir of Lightning Speed | 80 | 
  | 44332 | Elixir of Mighty Thoughts | 80 | 

  </details>

  22823, 22824, 22825, 22827, 22830, 22831, 22833, 22834, 22835, 22840, 22848, 25539, 28102, 28103, 28104, 31679, 32062, 32063, 32067, 32068, 34537, 37449, 39666, 40068, 40070, 40072, 40073, 40076, 40078, 40097, 40109, 44012, 44325, 44327, 44328, 44329, 44330, 44331, 44332

<hr>

- ### Flasks (subclass = 3)
    There are 4 ilvl 60 classic flasks - distilled wisdom, supreme power, chromatic resistance, titans - highest item id is 13513.
    
  ```SQL
  SELECT it.entry  , it.name,it.ItemLevel
  FROM `item_template` it
  WHERE it.class = 0 AND it.subclass = 3
  AND it.itemlevel >= 60 AND it.entry > 22000
  ```

  <details>
  <summary>Results</summary>

  ---
  | entry | name | ItemLevel | 
  | ---: | --- | ---: | 
  | 22851 | Flask of Fortification | 70 | 
  | 22853 | Flask of Mighty Restoration | 70 | 
  | 22854 | Flask of Relentless Assault | 70 | 
  | 22861 | Flask of Blinding Light | 70 | 
  | 22866 | Flask of Pure Death | 70 | 
  | 32596 | Unstable Flask of the Elder | 70 | 
  | 32597 | Unstable Flask of the Soldier | 70 | 
  | 32598 | Unstable Flask of the Beast | 70 | 
  | 32599 | Unstable Flask of the Bandit | 70 | 
  | 32600 | Unstable Flask of the Physician | 70 | 
  | 32601 | Unstable Flask of the Sorcerer | 70 | 
  | 32764 | Flaskataur's Celestial Brew | 75 | 
  | 32765 | Flaskataur's Tears | 75 | 
  | 32766 | Flaskataur's Flask of Flaskocity | 75 | 
  | 32767 | Flaskataur's Flask of Pretty Good Power | 60 | 
  | 32898 | Shattrath Flask of Fortification | 70 | 
  | 32899 | Shattrath Flask of Mighty Restoration | 70 | 
  | 32900 | Shattrath Flask of Supreme Power | 70 | 
  | 32901 | Shattrath Flask of Relentless Assault | 70 | 
  | 33208 | Flask of Chromatic Wonder | 70 | 
  | 35716 | Shattrath Flask of Pure Death | 70 | 
  | 35717 | Shattrath Flask of Blinding Light | 70 | 
  | 40079 | Lesser Flask of Toughness | 80 | 
  | 40082 | Mixture of the Frost Wyrm | 85 | 
  | 40083 | Mixture of Stoneblood | 85 | 
  | 40084 | Mixture of Endless Rage | 85 | 
  | 40404 | Mixture of Pure Mojo | 85 | 
  | 44939 | Lesser Flask of Resistance | 80 | 
  | 45006 | Jillian's Tonic of Endless Rage | 85 | 
  | 45007 | Jillian's Tonic of Pure Mojo | 85 | 
  | 45008 | Jillian's Tonic of Stoneblood | 85 | 
  | 45009 | Jillian's Tonic of the Frost Wyrm | 85 | 
  | 46376 | Flask of the Frost Wyrm | 85 | 
  | 46377 | Flask of Endless Rage | 85 | 
  | 46378 | Flask of Pure Mojo | 85 | 
  | 46379 | Flask of Stoneblood | 85 | 
  | 47499 | Flask of the North | 80 | 

  </details
    
  22851, 22853, 22854, 22861, 22866, 32596, 32597, 32598, 32599, 32600, 32601, 32764, 32765, 32766, 32767, 32898, 32899, 32900, 32901, 33208, 35716, 35717, 40079, 40082, 40083, 40084, 40404, 44939, 45006, 45007, 45008, 45009, 46376, 46377, 46378, 46379, 47499
    
<hr>

 - ### Scroll (subclass = 4)
    Classic scrolls go up to ilvl 65, agility/strength IV. highest item id is 10310. >= 70 works though, lv V scrolls from TBC start there. The scrolls on AC all have different item levels to those on Wowhead, for example Scroll of Agility IV which is ilvl 50 on AC and ilvl 65 on TBC Wowhead. Setting the cutoff point to level V scrolls and above gives us:
 
    ```SQL
    SELECT it.entry, it.name,it.ItemLevel, it.RequiredLevel
    FROM `item_template` it
    WHERE it.class = 0 AND it.subclass = 4
    AND it.itemlevel >= 60 
    ```
 
  <details>
  <summary>Results</summary>

  ---
  | entry | name | ItemLevel | RequiredLevel | 
  | ---: | --- | ---: | ---: | 
  | 27498 | Scroll of Agility V | 60 | 50 | 
  | 27499 | Scroll of Intellect V | 60 | 50 | 
  | 27500 | Scroll of Protection V | 60 | 50 | 
  | 27501 | Scroll of Spirit V | 60 | 50 | 
  | 27502 | Scroll of Stamina V | 60 | 50 | 
  | 27503 | Scroll of Strength V | 60 | 50 | 
  | 33457 | Scroll of Agility VI | 70 | 60 | 
  | 33458 | Scroll of Intellect VI | 70 | 60 | 
  | 33459 | Scroll of Protection VI | 70 | 60 | 
  | 33460 | Scroll of Spirit VI | 70 | 60 | 
  | 33461 | Scroll of Stamina VI | 70 | 60 | 
  | 33462 | Scroll of Strength VI | 70 | 60 | 
  | 37091 | Scroll of Intellect VII | 80 | 70 | 
  | 37092 | Scroll of Intellect VIII | 90 | 80 | 
  | 37093 | Scroll of Stamina VII | 80 | 70 | 
  | 37094 | Scroll of Stamina VIII | 90 | 80 | 
  | 37097 | Scroll of Spirit VII | 80 | 70 | 
  | 37098 | Scroll of Spirit VIII | 90 | 80 | 
  | 43463 | Scroll of Agility VII | 80 | 70 | 
  | 43464 | Scroll of Agility VIII | 90 | 80 | 
  | 43465 | Scroll of Strength VII | 80 | 70 | 
  | 43466 | Scroll of Strength VIII | 90 | 80 | 
  | 43467 | Scroll of Protection VII | 80 | 70 | 
  | 43468 | Scroll of Protection VIII | 80 | 80 | 
  | 44315 | Scroll of Recall III | 70 | 65 | 
  | 49632 | Runescroll of Fortitude | 90 | 80 | 

  </details>
 
  27498, 27499, 27500, 27501, 27502, 27503, 33457, 33458, 33459, 33460, 33461, 33462, 37091, 37092, 37093, 37094, 37097, 37098, 43463, 43464, 43465, 43466, 43467, 43468, 44315, 49632
 
<hr>

- ### Food & Drink (subclass = 5)
    Tons of TBC food added across all level ranges. Meanwhile classic food goes up to ilvl 65 and has required player lvl of 55. Highest classic item id is 22895. The TBC lvl 65 food all seemed comfortably higher than this id.
  
    ```SQL
    SELECT it.entry, it.name,it.ItemLevel, it.RequiredLevel
    FROM `item_template` it
    WHERE it.class = 0 AND it.subclass = 5
    AND it.itemlevel >= 60 AND it.entry > 23000
    ```
 
  <details>
  <summary>Results</summary>
  
  ---
  | entry | name | ItemLevel | RequiredLevel | 
  | ---: | --- | ---: | ---: | 
  | 24008 | Dried Mushroom Rations | 65 | 55 | 
  | 24009 | Dried Fruit Rations | 65 | 55 | 
  | 24539 | Marsh Lichen | 65 | 55 | 
  | 27651 | Buzzard Bites | 65 | 55 | 
  | 27655 | Ravager Dog | 65 | 55 | 
  | 27656 | Sporeling Snack | 65 | 55 | 
  | 27657 | Blackened Basilisk | 65 | 55 | 
  | 27658 | Roasted Clefthoof | 65 | 55 | 
  | 27659 | Warp Burger | 65 | 55 | 
  | 27660 | Talbuk Steak | 65 | 55 | 
  | 27661 | Blackened Trout | 65 | 55 | 
  | 27662 | Feltail Delight | 65 | 55 | 
  | 27663 | Blackened Sporefish | 65 | 55 | 
  | 27664 | Grilled Mudfish | 65 | 55 | 
  | 27665 | Poached Bluefish | 65 | 55 | 
  | 27666 | Golden Fish Sticks | 65 | 55 | 
  | 27667 | Spicy Crawdad | 65 | 55 | 
  | 27854 | Smoked Talbuk Venison | 65 | 55 | 
  | 27855 | Mag'har Grainbread | 65 | 55 | 
  | 27856 | Skethyl Berries | 65 | 55 | 
  | 27857 | Garadar Sharp | 65 | 55 | 
  | 27858 | Sunspring Carp | 65 | 55 | 
  | 27859 | Zangar Caps | 65 | 55 | 
  | 27860 | Purified Draenic Water | 75 | 65 | 
  | 28112 | Underspore Pod | 70 | 0 | 
  | 28399 | Filtered Draenic Water | 70 | 60 | 
  | 28486 | Moser's Magnificent Muffin | 65 | 55 | 
  | 29393 | Diamond Berries | 65 | 55 | 
  | 29394 | Lyribread | 75 | 65 | 
  | 29395 | Ethermead | 75 | 65 | 
  | 29401 | Sparkling Southshore Cider | 75 | 65 | 
  | 29412 | Jessen's Special Slop | 65 | 55 | 
  | 29448 | Mag'har Mild Cheese | 75 | 65 | 
  | 29449 | Bladespire Bagel | 75 | 65 | 
  | 29450 | Telaari Grapes | 75 | 65 | 
  | 29451 | Clefthoof Ribs | 75 | 65 | 
  | 29452 | Zangar Trout | 75 | 65 | 
  | 29453 | Sporeggar Mushroom | 75 | 65 | 
  | 29454 | Silverwine | 70 | 60 | 
  | 30155 | Clam Bar | 65 | 55 | 
  | 30355 | Grilled Shadowmoon Tuber | 75 | 65 | 
  | 30357 | Oronok's Tuber of Healing | 75 | 65 | 
  | 30358 | Oronok's Tuber of Agility | 75 | 65 | 
  | 30359 | Oronok's Tuber of Strength | 75 | 65 | 
  | 30361 | Oronok's Tuber of Spell Power | 75 | 65 | 
  | 30457 | Gilneas Sparkling Water | 75 | 65 | 
  | 30458 | Stromgarde Muenster | 65 | 55 | 
  | 30610 | Smoked Black Bear Meat | 65 | 55 | 
  | 30703 | Conjured Mountain Spring Water | 70 | 60 | 
  | 31672 | Mok'Nathal Shortribs | 65 | 55 | 
  | 31673 | Crunchy Serpent | 65 | 55 | 
  | 32453 | Star's Tears | 75 | 65 | 
  | 32455 | Star's Lament | 65 | 55 | 
  | 32667 | Bash Ale | 75 | 65 | 
  | 32668 | Dos Ogris | 75 | 65 | 
  | 32685 | Ogri'la Chicken Fingers | 75 | 65 | 
  | 32686 | Mingo's Fortune Giblets | 75 | 65 | 
  | 32721 | Skyguard Rations | 65 | 55 | 
  | 32722 | Enriched Terocone Juice | 65 | 65 | 
  | 33042 | Black Coffee | 75 | 65 | 
  | 33048 | Stewed Trout | 75 | 65 | 
  | 33052 | Fisherman's Feast | 75 | 65 | 
  | 33053 | Hot Buttered Trout | 75 | 65 | 
  | 33443 | Sour Goat Cheese | 75 | 65 | 
  | 33444 | Pungent Seal Whey | 80 | 70 | 
  | 33445 | Honeymint Tea | 85 | 75 | 
  | 33449 | Crusty Flatbread | 75 | 65 | 
  | 33451 | Fillet of Icefin | 75 | 65 | 
  | 33452 | Honey-Spiced Lichen | 75 | 65 | 
  | 33454 | Salted Venison | 75 | 65 | 
  | 33825 | Skullfish Soup | 70 | 65 | 
  | 33866 | Stormchops | 65 | 55 | 
  | 33867 | Broiled Bloodfin | 65 | 55 | 
  | 33872 | Spicy Hot Talbuk | 75 | 65 | 
  | 33874 | Kibler's Bits | 65 | 55 | 
  | 34062 | Conjured Mana Biscuit | 75 | 65 | 
  | 34125 | Shoveltusk Soup | 75 | 70 | 
  | 34411 | Hot Apple Cider | 75 | 65 | 
  | 34747 | Northern Stew | 80 | 70 | 
  | 34748 | Mammoth Meal | 80 | 70 | 
  | 34749 | Shoveltusk Steak | 80 | 70 | 
  | 34750 | Worm Delight | 80 | 70 | 
  | 34751 | Roasted Worg | 80 | 70 | 
  | 34752 | Rhino Dogs | 80 | 70 | 
  | 34753 | Great Feast | 80 | 70 | 
  | 34754 | Mega Mammoth Meal | 80 | 70 | 
  | 34755 | Tender Shoveltusk Steak | 80 | 70 | 
  | 34756 | Spiced Worm Burger | 80 | 70 | 
  | 34757 | Very Burnt Worg | 80 | 70 | 
  | 34758 | Mighty Rhino Dogs | 80 | 70 | 
  | 34759 | Smoked Rockfin | 80 | 70 | 
  | 34760 | Grilled Bonescale | 80 | 70 | 
  | 34761 | Sauteed Goby | 80 | 70 | 
  | 34762 | Grilled Sculpin | 80 | 70 | 
  | 34763 | Smoked Salmon | 80 | 70 | 
  | 34764 | Poached Nettlefish | 80 | 70 | 
  | 34765 | Pickled Fangtooth | 80 | 70 | 
  | 34766 | Poached Northern Sculpin | 80 | 70 | 
  | 34767 | Firecracker Salmon | 80 | 70 | 
  | 34768 | Spicy Blue Nettlefish | 80 | 70 | 
  | 34769 | Imperial Manta Steak | 80 | 70 | 
  | 34780 | Naaru Ration | 75 | 65 | 
  | 35947 | Sparkling Frostcap | 85 | 75 | 
  | 35948 | Savory Snowplum | 85 | 75 | 
  | 35949 | Tundra Berries | 75 | 65 | 
  | 35950 | Sweet Potato Bread | 85 | 75 | 
  | 35951 | Poached Emperor Salmon | 85 | 75 | 
  | 35952 | Briny Hardcheese | 85 | 75 | 
  | 35953 | Mead Basted Caribou | 85 | 75 | 
  | 35954 | Sweetened Goat's Milk | 75 | 65 | 
  | 37252 | Frostberries | 75 | 65 | 
  | 37253 | Frostberry Juice | 75 | 65 | 
  | 37452 | Fatty Bluefin | 75 | 65 | 
  | 38427 | Pickled Egg | 65 | 55 | 
  | 38428 | Rock-Salted Pretzel | 75 | 65 | 
  | 38430 | Blackrock Mineral Water | 70 | 60 | 
  | 38431 | Blackrock Fortified Water | 75 | 65 | 
  | 38698 | Bitter Plasma | 80 | 70 | 
  | 38706 | Bowels 'n' Brains | 85 | 75 | 
  | 39520 | Kungaloosh | 85 | 75 | 
  | 39691 | Succulent Orca Stew | 75 | 70 | 
  | 40202 | Sizzling Grizzly Flank | 85 | 75 | 
  | 40356 | Grizzleberries | 75 | 65 | 
  | 40357 | Grizzleberry Juice | 75 | 65 | 
  | 40358 | Raw Tallhorn Chunk | 75 | 65 | 
  | 40359 | Fresh Eagle Meat | 75 | 65 | 
  | 41729 | Stewed Drakeflesh | 85 | 75 | 
  | 41731 | Yeti Milk | 85 | 75 | 
  | 41751 | Black Mushroom | 65 | 55 | 
  | 42428 | Carrot Cupcake | 75 | 70 | 
  | 42429 | Red Velvet Cupcake | 85 | 75 | 
  | 42430 | Dalaran Doughnut | 75 | 70 | 
  | 42431 | Dalaran Brownie | 85 | 75 | 
  | 42432 | Berry Pie Slice | 75 | 70 | 
  | 42433 | Chocolate Cake Slice | 75 | 70 | 
  | 42434 | Lovely Cake Slice | 85 | 75 | 
  | 42590 | TEST FRUITCAKE | 65 | 40 | 
  | 42777 | Crusader's Waterskin | 85 | 75 | 
  | 42778 | Crusader's Rations | 85 | 75 | 
  | 42779 | Steaming Chicken Soup | 85 | 75 | 
  | 42942 | Baked Manta Ray | 80 | 70 | 
  | 42993 | Spicy Fried Herring | 80 | 70 | 
  | 42994 | Rhinolicious Wormsteak | 80 | 70 | 
  | 42995 | Hearty Rhino | 80 | 70 | 
  | 42996 | Snapper Extreme | 80 | 70 | 
  | 42997 | Blackened Worg Steak | 80 | 70 | 
  | 42998 | Cuttlesteak | 80 | 70 | 
  | 42999 | Blackened Dragonfin | 80 | 70 | 
  | 43000 | Dragonfin Filet | 80 | 70 | 
  | 43001 | Tracker Snacks | 80 | 70 | 
  | 43004 | Critter Bites | 80 | 70 | 
  | 43005 | Spiced Mammoth Treats | 80 | 70 | 
  | 43015 | Fish Feast | 80 | 70 | 
  | 43086 | Fresh Apple Juice | 80 | 70 | 
  | 43087 | Crisp Dalaran Apple | 85 | 75 | 
  | 43236 | Star's Sorrow | 85 | 75 | 
  | 43268 | Dalaran Clam Chowder | 80 | 70 | 
  | 43478 | Gigantic Feast | 80 | 70 | 
  | 43480 | Small Feast | 80 | 70 | 
  | 43488 | Last Weeks Mammoth | 80 | 0 | 
  | 43490 | Tasty Cupcake | 80 | 0 | 
  | 43491 | Bad Clams | 80 | 0 | 
  | 43492 | Haunted Herring | 80 | 0 | 
  | 43518 | Conjured Mana Pie | 84 | 74 | 
  | 43523 | Conjured Mana Strudel | 90 | 80 | 
  | 44049 | Freshly-Speared Emperor Salmon | 85 | 75 | 
  | 44071 | Slow-Roasted Eel | 85 | 75 | 
  | 44072 | Roasted Mystery Beast | 85 | 75 | 
  | 44607 | Aged Dalaran Sharp | 85 | 75 | 
  | 44608 | Dalaran Swiss | 75 | 65 | 
  | 44609 | Fresh Dalaran Bread Slice | 75 | 65 | 
  | 44616 | Glass of Dalaran White | 70 | 0 | 
  | 44618 | Glass of Aged Dalaran Red | 70 | 0 | 
  | 44619 | Glass of Peaked Dalaran Red | 70 | 0 | 
  | 44722 | Aged Yolk | 85 | 75 | 
  | 44749 | Salted Yeti Cheese | 75 | 65 | 
  | 44750 | Mountain Water | 75 | 65 | 
  | 44940 | Corn-Breaded Sausage | 85 | 75 | 
  | 44941 | Fresh-Squeezed Limeade | 80 | 70 | 
  | 44953 | Worg Tartare | 80 | 70 | 
  | 45279 | Jillian's Gourmet Fish Feast | 80 | 70 | 
  | 45901 | Homemade Fish Fry | 80 | 70 | 
  | 45932 | Black Jelly | 90 | 75 | 
  | 46887 | Bountiful Feast | 60 | 0 | 

  </details>
 
24008, 24009, 24539, 27651, 27655, 27656, 27657, 27658, 27659, 27660, 27661, 27662, 27663, 27664, 27665, 27666, 27667, 27854, 27855, 27856, 27857, 27858, 27859, 27860, 28112, 28399, 28486, 29393, 29394, 29395, 29401, 29412, 29448, 29449, 29450, 29451, 29452, 29453, 29454, 30155, 30355, 30357, 30358, 30359, 30361, 30457, 30458, 30610, 30703, 31672, 31673, 32453, 32455, 32667, 32668, 32685, 32686, 32721, 32722, 33042, 33048, 33052, 33053, 33443, 33444, 33445, 33449, 33451, 33452, 33454, 33825, 33866, 33867, 33872, 33874, 34062, 34125, 34411, 34747, 34748, 34749, 34750, 34751, 34752, 34753, 34754, 34755, 34756, 34757, 34758, 34759, 34760, 34761, 34762, 34763, 34764, 34765, 34766, 34767, 34768, 34769, 34780, 35947, 35948, 35949, 35950, 35951, 35952, 35953, 35954, 37252, 37253, 37452, 38427, 38428, 38430, 38431, 38698, 38706, 39520, 39691, 40202, 40356, 40357, 40358, 40359, 41729, 41731, 41751, 42428, 42429, 42430, 42431, 42432, 42433, 42434, 42590, 42777, 42778, 42779, 42942, 42993, 42994, 42995, 42996, 42997, 42998, 42999, 43000, 43001, 43004, 43005, 43015, 43086, 43087, 43236, 43268, 43478, 43480, 43488, 43490, 43491, 43492, 43518, 43523, 44049, 44071, 44072, 44607, 44608, 44609, 44616, 44618, 44619, 44722, 44749, 44750, 44940, 44941, 44953, 45279, 45901, 45932, 46887

<hr>

- ### Item Enhancement (subclass = 6): 
    - TEMPORARY - only vanilla items at 60 are elemental sharpening stone 18262 and 2 rogue poisons, instant poison VI  and Deadly Poison V id 20844. There are 3 TBC items at 60, lowest id is fel sharpening stone id 23528.
    - PERMANENT: lots of ilvl 60 vanilla enhances, but none higher, and only 1 ilvl 60 TBC item, knothide armor kit 25650
    - summation: >= 61 plus knothide armor kit 25650, fel sharpening stone 23528, comfortable insoles 25679, fel weightstone 28420.
 
   ```SQL
   SELECT it.entry , it.name,it.ItemLevel, it.RequiredLevel
   FROM `item_template` it
   WHERE it.class = 0 AND it.subclass = 6
   AND it.itemlevel >= 61
   ```
 
  <details>
  <summary>Results</summary>

  | entry | name | ItemLevel | RequiredLevel | 
  | ---: | --- | ---: | ---: | 
  | 23530 | Felsteel Shield Spike | 70 | 0 | 
  | 24273 | Mystic Spellthread | 67 | 50 | 
  | 24274 | Runic Spellthread | 75 | 60 | 
  | 24275 | Silver Spellthread | 67 | 50 | 
  | 24276 | Golden Spellthread | 75 | 60 | 
  | 25651 | Vindicator's Armor Kit | 65 | 55 | 
  | 25652 | Magister's Armor Kit | 65 | 55 | 
  | 29483 | Shadow Armor Kit | 68 | 65 | 
  | 29485 | Flame Armor Kit | 68 | 65 | 
  | 29486 | Frost Armor Kit | 68 | 65 | 
  | 29487 | Nature Armor Kit | 68 | 65 | 
  | 29488 | Arcane Armor Kit | 68 | 65 | 
  | 29533 | Cobrahide Leg Armor | 67 | 50 | 
  | 29534 | Clefthide Leg Armor | 67 | 50 | 
  | 29535 | Nethercobra Leg Armor | 73 | 60 | 
  | 29536 | Nethercleft Leg Armor | 73 | 60 | 
  | 33185 | Adamantite Weapon Chain | 63 | 50 | 
  | 34207 | Glove Reinforcements | 70 | 60 | 
  | 34330 | Heavy Knothide Armor Kit | 70 | 60 | 
  | 34836 | Spun Truesilver Fishing Line | 70 | 0 | 
  | 37603 | Scroll of Enchant Boots - Dexterity | 68 | 0 | 
  | 38371 | Jormungar Leg Armor | 77 | 70 | 
  | 38372 | Nerubian Leg Armor | 77 | 70 | 
  | 38373 | Frosthide Leg Armor | 80 | 80 | 
  | 38374 | Icescale Leg Armor | 80 | 80 | 
  | 38375 | Borean Armor Kit | 80 | 70 | 
  | 38376 | Heavy Borean Armor Kit | 80 | 70 | 
  | 38377 | Dragonscale Leg Armor | 80 | 70 | 
  | 38378 | Wyrmscale Leg Armor | 80 | 70 | 
  | 38865 | Scroll of Enchant Chest - Greater Stats | 62 | 0 | 
  | 38871 | Scroll of Enchant Weapon - Lifestealing | 62 | 0 | 
  | 38873 | Scroll of Enchant Weapon - Crusader | 61 | 0 | 
  | 38874 | Scroll of Enchant 2H Weapon - Major Spirit | 62 | 0 | 
  | 38882 | Scroll of Enchant Bracer - Healing Power | 64 | 0 | 
  | 38883 | Scroll of Enchant Weapon - Mighty Spirit | 66 | 0 | 
  | 38884 | Scroll of Enchant Weapon - Mighty Intellect | 70 | 0 | 
  | 38885 | Scroll of Enchant Gloves - Threat | 70 | 0 | 
  | 38886 | Scroll of Enchant Gloves - Shadow Power | 70 | 0 | 
  | 38887 | Scroll of Enchant Gloves - Frost Power | 70 | 0 | 
  | 38888 | Scroll of Enchant Gloves - Fire Power | 70 | 0 | 
  | 38889 | Scroll of Enchant Gloves - Healing Power | 70 | 0 | 
  | 38890 | Scroll of Enchant Gloves - Superior Agility | 70 | 0 | 
  | 38891 | Scroll of Enchant Cloak - Greater Fire Resistance | 70 | 0 | 
  | 38892 | Scroll of Enchant Cloak - Greater Nature Resistance | 70 | 0 | 
  | 38893 | Scroll of Enchant Cloak - Stealth | 70 | 0 | 
  | 38894 | Scroll of Enchant Cloak - Subtlety | 70 | 0 | 
  | 38895 | Scroll of Enchant Cloak - Dodge | 70 | 0 | 
  | 38897 | Scroll of Enchant Bracer - Brawn | 61 | 0 | 
  | 38898 | Scroll of Enchant Bracer - Stats | 63 | 0 | 
  | 38899 | Scroll of Enchant Bracer - Major Defense | 64 | 0 | 
  | 38900 | Scroll of Enchant Bracer - Superior Healing | 65 | 0 | 
  | 38901 | Scroll of Enchant Bracer - Restore Mana Prime | 67 | 0 | 
  | 38902 | Scroll of Enchant Bracer - Fortitude | 70 | 0 | 
  | 38903 | Scroll of Enchant Bracer - Spellpower | 72 | 0 | 
  | 38904 | Scroll of Enchant Shield - Tough Shield | 62 | 0 | 
  | 38905 | Scroll of Enchant Shield - Intellect | 65 | 0 | 
  | 38906 | Scroll of Enchant Shield - Shield Block | 68 | 0 | 
  | 38907 | Scroll of Enchant Shield - Resistance | 72 | 0 | 
  | 38908 | Scroll of Enchant Boots - Vitality | 61 | 0 | 
  | 38909 | Scroll of Enchant Boots - Fortitude | 64 | 0 | 
  | 38910 | Scroll of Enchant Boots - Surefooted | 74 | 0 | 
  | 38911 | Scroll of Enchant Chest - Exceptional Health | 63 | 0 | 
  | 38912 | Scroll of Enchant Chest - Exceptional Mana | 71 | 0 | 
  | 38913 | Scroll of Enchant Chest - Exceptional Stats | 69 | 0 | 
  | 38914 | Scroll of Enchant Cloak - Major Armor | 62 | 0 | 
  | 38915 | Scroll of Enchant Cloak - Major Resistance | 66 | 0 | 
  | 38917 | Scroll of Enchant Weapon - Major Striking | 68 | 0 | 
  | 38918 | Scroll of Enchant Weapon - Major Intellect | 68 | 0 | 
  | 38919 | Scroll of Enchant 2H Weapon - Savagery | 70 | 0 | 
  | 38920 | Scroll of Enchant Weapon - Potency | 70 | 0 | 
  | 38921 | Scroll of Enchant Weapon - Major Spellpower | 70 | 0 | 
  | 38922 | Scroll of Enchant 2H Weapon - Major Agility | 72 | 0 | 
  | 38923 | Scroll of Enchant Weapon - Sunfire | 75 | 0 | 
  | 38924 | Scroll of Enchant Weapon - Soulfrost | 75 | 0 | 
  | 38925 | Scroll of Enchant Weapon - Mongoose | 75 | 0 | 
  | 38926 | Scroll of Enchant Weapon - Spellsurge | 72 | 0 | 
  | 38927 | Scroll of Enchant Weapon - Battlemaster | 72 | 0 | 
  | 38928 | Scroll of Enchant Chest - Major Spirit | 64 | 0 | 
  | 38930 | Scroll of Enchant Chest - Major Resilience | 69 | 0 | 
  | 38931 | Scroll of Enchant Gloves - Blasting | 61 | 0 | 
  | 38932 | Scroll of Enchant Gloves - Precise Strikes | 72 | 0 | 
  | 38933 | Scroll of Enchant Gloves - Major Strength | 68 | 0 | 
  | 38934 | Scroll of Enchant Gloves - Assault | 62 | 0 | 
  | 38935 | Scroll of Enchant Gloves - Major Spellpower | 72 | 0 | 
  | 38936 | Scroll of Enchant Gloves - Major Healing | 70 | 0 | 
  | 38937 | Scroll of Enchant Bracer - Major Intellect | 61 | 0 | 
  | 38939 | Scroll of Enchant Cloak - Spell Penetration | 65 | 0 | 
  | 38940 | Scroll of Enchant Cloak - Greater Agility | 62 | 0 | 
  | 38941 | Scroll of Enchant Cloak - Greater Arcane Resistance | 70 | 0 | 
  | 38942 | Scroll of Enchant Cloak - Greater Shadow Resistance | 70 | 0 | 
  | 38943 | Scroll of Enchant Boots - Cat's Swiftness | 72 | 0 | 
  | 38944 | Scroll of Enchant Boots - Boar's Speed | 72 | 0 | 
  | 38945 | Scroll of Enchant Shield - Major Stamina | 65 | 0 | 
  | 38946 | Scroll of Enchant Weapon - Major Healing | 70 | 0 | 
  | 38947 | Scroll of Enchant Weapon - Greater Agility | 70 | 0 | 
  | 38948 | Scroll of Enchant Weapon - Executioner | 75 | 0 | 
  | 38949 | Scroll of Enchant Shield - Resilience | 66 | 0 | 
  | 38950 | Scroll of Enchant Cloak - Superior Frost Resistance | 80 | 0 | 
  | 38951 | Scroll of Enchant Gloves - Expertise | 73 | 0 | 
  | 38953 | Scroll of Enchant Gloves - Precision | 77 | 0 | 
  | 38954 | Scroll of Enchant Shield - Defense | 71 | 0 | 
  | 38955 | Scroll of Enchant Chest - Mighty Health | 79 | 0 | 
  | 38956 | Scroll of Enchant Cloak - Superior Nature Resistance | 80 | 0 | 
  | 38957 | Scroll of Enchant Weapon - Exceptional Striking | 72 | 0 | 
  | 38958 | Scroll of Enchant Weapon - Exceptional Intellect | 80 | 0 | 
  | 38959 | Scroll of Enchant Cloak - Superior Agility | 80 | 0 | 
  | 38960 | Scroll of Enchant Gloves - Gatherer | 75 | 0 | 
  | 38961 | Scroll of Enchant Boots - Greater Spirit | 71 | 0 | 
  | 38962 | Scroll of Enchant Chest - Greater Mana Restoration | 75 | 0 | 
  | 38963 | Scroll of Enchant Weapon - Exceptional Spirit | 80 | 0 | 
  | 38964 | Scroll of Enchant Gloves - Greater Assault | 84 | 0 | 
  | 38965 | Scroll of Enchant Weapon - Icebreaker | 84 | 0 | 
  | 38966 | Scroll of Enchant Boots - Greater Fortitude | 75 | 0 | 
  | 38967 | Scroll of Enchant Gloves - Major Agility | 85 | 0 | 
  | 38968 | Scroll of Enchant Bracers - Exceptional Intellect | 75 | 0 | 
  | 38969 | Scroll of Enchant Cloak - Superior Fire Resistance | 80 | 0 | 
  | 38970 | Scroll of Enchant Gloves - Exceptional Healing | 85 | 0 | 
  | 38971 | Scroll of Enchant Bracers - Striking | 71 | 0 | 
  | 38972 | Scroll of Enchant Weapon - Lifeward | 85 | 0 | 
  | 38973 | Scroll of Enchant Cloak - Spell Piercing | 79 | 0 | 
  | 38974 | Scroll of Enchant Boots - Greater Vitality | 73 | 0 | 
  | 38975 | Scroll of Enchant Chest - Exceptional Resilience | 82 | 0 | 
  | 38976 | Scroll of Enchant Boots - Superior Agility | 82 | 0 | 
  | 38977 | Scroll of Enchant Cloak - Superior Shadow Resistance | 80 | 0 | 
  | 38978 | Scroll of Enchant Cloak - Titanweave | 85 | 0 | 
  | 38979 | Scroll of Enchant Gloves - Exceptional Spellpower | 85 | 0 | 
  | 38980 | Scroll of Enchant Bracers - Major Spirit | 80 | 0 | 
  | 38981 | Scroll of Enchant 2H Weapon - Scourgebane | 80 | 0 | 
  | 38982 | Scroll of Enchant Cloak - Superior Arcane Resistance | 80 | 0 | 
  | 38983 | Scroll of Enchant Shield - Exceptional Stamina | 81 | 0 | 
  | 38984 | Scroll of Enchant Bracer - Expertise | 84 | 0 | 
  | 38985 | Scroll of Enchant Gloves - Greater Blasting | 82 | 0 | 
  | 38986 | Scroll of Enchant Boots - Icewalker | 85 | 0 | 
  | 38987 | Scroll of Enchant Bracers - Greater Stats | 80 | 0 | 
  | 38988 | Scroll of Enchant Weapon - Giant Slayer | 82 | 0 | 
  | 38989 | Scroll of Enchant Chest - Super Stats | 85 | 0 | 
  | 38990 | Scroll of Enchant Gloves - Armsman | 85 | 0 | 
  | 38991 | Scroll of Enchant Weapon - Exceptional Spellpower | 85 | 0 | 
  | 38992 | Scroll of Enchant 2H Weapon - Greater Savagery | 82 | 0 | 
  | 38993 | Scroll of Enchant Cloak - Shadow Armor | 85 | 0 | 
  | 38994 | Scroll of Enchant Weapon - Exceptional Healing | 85 | 0 | 
  | 38995 | Scroll of Enchant Weapon - Exceptional Agility | 84 | 0 | 
  | 38996 | Scroll of Enchant Bracers - Major Healing | 85 | 0 | 
  | 38997 | Scroll of Enchant Bracers - Greater Spellpower | 85 | 0 | 
  | 38998 | Scroll of Enchant Weapon - Deathfrost | 73 | 0 | 
  | 38999 | Scroll of Enchant Chest - Defense | 72 | 0 | 
  | 39000 | Scroll of Enchant Cloak - Steelweave | 75 | 0 | 
  | 39001 | Scroll of Enchant Cloak - Mighty Armor | 71 | 0 | 
  | 39002 | Scroll of Enchant Chest - Greater Defense | 80 | 0 | 
  | 39003 | Scroll of Enchant Cloak - Greater Speed | 85 | 0 | 
  | 39004 | Scroll of Enchant Cloak - Wisdom | 85 | 0 | 
  | 39005 | Scroll of Enchant Chest - Super Health | 85 | 0 | 
  | 39006 | Scroll of Enchant Boots - Tuskarr's Vitality | 85 | 0 | 
  | 40776 | Personal Electromagnetic Pulse Generator | 75 | 0 | 
  | 41091 | Hand-Mounted Pyro Rocket | 75 | 0 | 
  | 41093 | Hyperspeed Accelerators | 75 | 0 | 
  | 41111 | Flexweave Underlay | 75 | 0 | 
  | 41118 | Nitro Boosts | 75 | 0 | 
  | 41601 | Shining Spellthread | 80 | 70 | 
  | 41602 | Brilliant Spellthread | 80 | 70 | 
  | 41603 | Azure Spellthread | 80 | 70 | 
  | 41604 | Sapphire Spellthread | 80 | 70 | 
  | 41605 | zzDEPRECATED Sanctified Spellthread | 80 | 70 | 
  | 41606 | zzDEPRECATED Master's Spellthread | 80 | 70 | 
  | 41611 | Eternal Belt Buckle | 80 | 70 | 
  | 41976 | Titanium Weapon Chain | 80 | 70 | 
  | 42500 | Titanium Shield Spike | 80 | 70 | 
  | 43097 | Fur Lining - Attack Power | 85 | 0 | 
  | 43987 | Scroll of Enchant Weapon - Black Magic | 85 | 0 | 
  | 44449 | Scroll of Enchant Boots - Assault | 71 | 0 | 
  | 44453 | Scroll of Enchant Weapon - Greater Potency | 71 | 0 | 
  | 44455 | Scroll of Enchant Shield - Greater Intellect | 75 | 0 | 
  | 44456 | Scroll of Enchant Cloak - Speed | 75 | 0 | 
  | 44457 | Scroll of Enchant Cloak - Major Agility | 75 | 0 | 
  | 44458 | Scroll of Enchant Gloves - Crusher | 85 | 0 | 
  | 44463 | Scroll of Enchant 2H Weapon - Massacre | 79 | 0 | 
  | 44465 | Scroll of Enchant Chest - Powerful Stats | 79 | 0 | 
  | 44466 | Scroll of Enchant Weapon - Superior Potency | 79 | 0 | 
  | 44467 | Scroll of Enchant Weapon - Mighty Spellpower | 85 | 0 | 
  | 44469 | Scroll of Enchant Boots - Greater Assault | 72 | 0 | 
  | 44470 | Scroll of Enchant Bracer - Superior Spellpower | 71 | 0 | 
  | 44493 | Scroll of Enchant Weapon - Berserking | 79 | 0 | 
  | 44497 | Scroll of Enchant Weapon - Accuracy | 73 | 0 | 
  | 44815 | Scroll of Enchant Bracers - Greater Assault | 71 | 0 | 
  | 44936 | Titanium Plating | 80 | 70 | 
  | 44946 | Scroll of Enchant Weapon - Titanguard | 80 | 0 | 
  | 44947 | Scroll of Enchant Bracer - Major Stamina | 80 | 0 | 
  | 44963 | Earthen Leg Armor | 80 | 80 | 
  | 45056 | Scroll of Enchant Staff - Greater Spellpower | 85 | 0 | 
  | 45060 | Scroll of Enchant Staff - Spellpower | 80 | 0 | 
  | 46026 | Scroll of Enchant Weapon - Blade Ward | 80 | 0 | 
  | 46098 | Scroll of Enchant Weapon - Blood Draining | 80 | 0 | 
  | 50816 | Scroll of Enchant Gloves - Angler | 70 | 0 | 

  </details>
 
23530, 24273, 24274, 24275, 24276, 25651, 25652, 29483, 29485, 29486, 29487, 29488, 29533, 29534, 29535, 29536, 33185, 34207, 34330, 34836, 37603, 38371, 38372, 38373, 38374, 38375, 38376, 38377, 38378, 38865, 38871, 38873, 38874, 38882, 38883, 38884, 38885, 38886, 38887, 38888, 38889, 38890, 38891, 38892, 38893, 38894, 38895, 38897, 38898, 38899, 38900, 38901, 38902, 38903, 38904, 38905, 38906, 38907, 38908, 38909, 38910, 38911, 38912, 38913, 38914, 38915, 38917, 38918, 38919, 38920, 38921, 38922, 38923, 38924, 38925, 38926, 38927, 38928, 38930, 38931, 38932, 38933, 38934, 38935, 38936, 38937, 38939, 38940, 38941, 38942, 38943, 38944, 38945, 38946, 38947, 38948, 38949, 38950, 38951, 38953, 38954, 38955, 38956, 38957, 38958, 38959, 38960, 38961, 38962, 38963, 38964, 38965, 38966, 38967, 38968, 38969, 38970, 38971, 38972, 38973, 38974, 38975, 38976, 38977, 38978, 38979, 38980, 38981, 38982, 38983, 38984, 38985, 38986, 38987, 38988, 38989, 38990, 38991, 38992, 38993, 38994, 38995, 38996, 38997, 38998, 38999, 39000, 39001, 39002, 39003, 39004, 39005, 39006, 40776, 41091, 41093, 41111, 41118, 41601, 41602, 41603, 41604, 41605, 41606, 41611, 41976, 42500, 43097, 43987, 44449, 44453, 44455, 44456, 44457, 44458, 44463, 44465, 44466, 44467, 44469, 44470, 44493, 44497, 44815, 44936, 44946, 44947, 44963, 45056, 45060, 46026, 46098, 50816, 25650, 23528, 25679, 28420 

<hr>

- ### Bandages (subclass = 7): 
  1 vanilla 60 item, crystal infused bandage, probably not obtainable. >= 64 catches all TBC.
 
  ```SQL
  SELECT it.entry , it.name,it.ItemLevel, it.RequiredLevel
  FROM `item_template` it
  WHERE it.class = 0 AND it.subclass = 7
  AND it.itemlevel >= 64 
  ```
 
 <details>
<summary>Results</summary>

  item_template
---
| entry | name | ItemLevel | RequiredLevel | 
| ---: | --- | ---: | ---: | 
| 21990 | Netherweave Bandage | 64 | 0 | 
| 21991 | Heavy Netherweave Bandage | 70 | 0 | 
| 34721 | Frostweave Bandage | 71 | 0 | 
| 34722 | Heavy Frostweave Bandage | 80 | 0 | 
| 38640 | Dense Frostweave Bandage | 85 | 0 | 
| 38643 | Thick Frostweave Bandage | 75 | 0 | 

</details>
 
  21990, 21991, 34721, 34722, 38640, 38643

<hr>

- ### Other (subclass = 8): 
  Highest vanilla is 60 with highest index 20844 (deadly poison v), lowest TBC is 60, so >= 60 and index > 20844 works here.
 
  ```SQL
  SELECT it.entry, it.name,it.ItemLevel, it.RequiredLevel
  FROM `item_template` it
  WHERE it.class = 0 AND it.subclass = 8
  AND it.itemlevel >= 60 AND it.entry > 20844
  ```
 
 <details>
  <summary>Results</summary>

  ---
  | entry | name | ItemLevel | RequiredLevel | 
  | ---: | --- | ---: | ---: | 
  | 21835 | Anesthetic Poison | 68 | 68 | 
  | 21927 | Instant Poison VII | 68 | 68 | 
  | 22053 | Deadly Poison VI | 62 | 62 | 
  | 22054 | Deadly Poison VII | 70 | 70 | 
  | 22055 | Wound Poison V | 64 | 64 | 
  | 22103 | Master Healthstone | 70 | 60 | 
  | 22104 | Master Healthstone | 70 | 60 | 
  | 22105 | Master Healthstone | 70 | 60 | 
  | 22521 | Superior Mana Oil | 62 | 52 | 
  | 22522 | Superior Wizard Oil | 68 | 58 | 
  | 23528 | Fel Sharpening Stone | 60 | 50 | 
  | 23529 | Adamantite Sharpening Stone | 70 | 60 | 
  | 23559 | Lesser Rune of Warding | 65 | 55 | 
  | 23575 | Lesser Ward of Shielding | 65 | 55 | 
  | 23576 | Greater Ward of Shielding | 70 | 55 | 
  | 23862 | Redemption of the Fallen | 70 | 0 | 
  | 24268 | Netherweave Net | 60 | 0 | 
  | 24269 | Heavy Netherweave Net | 60 | 0 | 
  | 25521 | Greater Rune of Warding | 70 | 60 | 
  | 25679 | Comfortable Insoles | 60 | 0 | 
  | 28420 | Fel Weightstone | 60 | 50 | 
  | 28421 | Adamantite Weightstone | 70 | 60 | 
  | 29528 | Drums of War | 68 | 0 | 
  | 29529 | Drums of Battle | 73 | 0 | 
  | 29530 | Drums of Speed | 69 | 0 | 
  | 29531 | Drums of Restoration | 70 | 0 | 
  | 29532 | Drums of Panic | 74 | 0 | 
  | 31437 | Medicinal Drake Essence | 105 | 0 | 
  | 32839 | Cauldron of Major Arcane Protection | 70 | 60 | 
  | 32849 | Cauldron of Major Fire Protection | 70 | 60 | 
  | 32850 | Cauldron of Major Frost Protection | 70 | 60 | 
  | 32851 | Cauldron of Major Nature Protection | 70 | 60 | 
  | 32852 | Cauldron of Major Shadow Protection | 70 | 60 | 
  | 33930 | Amani Charm of the Bloodletter | 70 | 0 | 
  | 33931 | Amani Charm of Mighty Mojo | 70 | 0 | 
  | 33932 | Amani Charm of the Witch Doctor | 70 | 0 | 
  | 33933 | Amani Charm of the Raging Defender | 70 | 0 | 
  | 34504 | Adamantite Shell Machine | 70 | 0 | 
  | 34538 | Blessed Weapon Coating | 70 | 70 | 
  | 34539 | Righteous Weapon Coating | 70 | 70 | 
  | 35287 | Luminous Bluetail | 70 | 55 | 
  | 35396 | Enchant 2H Weapon - Major Agility | 70 | 0 | 
  | 35397 | Enchant 2H Weapon - Savagery | 70 | 0 | 
  | 35398 | Enchant Boots - Boar's Speed | 70 | 0 | 
  | 35399 | Enchant Boots - Cat's Swiftness | 70 | 0 | 
  | 35400 | Enchant Boots - Dexterity | 70 | 0 | 
  | 35417 | Enchant Boots - Fortitude | 70 | 0 | 
  | 35418 | Enchant Boots - Surefooted | 70 | 0 | 
  | 35419 | Enchant Boots - Vitality | 70 | 0 | 
  | 35420 | Enchant Bracer - Brawn | 70 | 0 | 
  | 35421 | Enchant Bracer - Fortitude | 70 | 0 | 
  | 35422 | Enchant Bracer - Major Defense | 70 | 0 | 
  | 35423 | Enchant Bracer - Major Intellect | 70 | 0 | 
  | 35424 | Enchant Bracer - Restore Mana Prime | 70 | 0 | 
  | 35425 | Enchant Bracer - Spellpower | 70 | 0 | 
  | 35426 | Enchant Bracer - Stats | 70 | 0 | 
  | 35427 | Enchant Bracer - Superior Healing | 70 | 0 | 
  | 35428 | Enchant Chest - Exceptional Health | 70 | 0 | 
  | 35429 | Enchant Chest - Exceptional Stats | 70 | 0 | 
  | 35430 | Enchant Chest - Major Resilience | 70 | 0 | 
  | 35431 | Enchant Chest - Major Spirit | 70 | 0 | 
  | 35432 | Enchant Cloak - Greater Agility | 70 | 0 | 
  | 35433 | Enchant Cloak - Greater Arcane Resistance | 70 | 0 | 
  | 35434 | Enchant Cloak - Greater Shadow Resistance | 70 | 0 | 
  | 35435 | Enchant Cloak - Major Resistance | 70 | 0 | 
  | 35436 | Enchant Cloak - Spell Penetration | 70 | 0 | 
  | 35437 | Enchant Cloak - Major Armor | 70 | 0 | 
  | 35438 | Enchant Gloves - Assault | 70 | 0 | 
  | 35439 | Enchant Gloves - Blasting | 70 | 0 | 
  | 35440 | Enchant Gloves - Major Healing | 70 | 0 | 
  | 35441 | Enchant Gloves - Major Spellpower | 70 | 0 | 
  | 35442 | Enchant Gloves - Major Strength | 70 | 0 | 
  | 35443 | Enchant Gloves - Spell Strike | 70 | 0 | 
  | 35444 | Enchant Ring - Healing Power | 70 | 0 | 
  | 35445 | Enchant Ring - Spellpower | 70 | 0 | 
  | 35446 | Enchant Ring - Stats | 70 | 0 | 
  | 35447 | Enchant Ring - Striking | 70 | 0 | 
  | 35448 | Enchant Shield - Intellect | 70 | 0 | 
  | 35449 | Enchant Shield - Major Stamina | 70 | 0 | 
  | 35450 | Enchant Shield - Resistance | 70 | 0 | 
  | 35451 | Enchant Shield - Shield Block | 70 | 0 | 
  | 35452 | Enchant Weapon - Battlemaster | 70 | 0 | 
  | 35453 | Enchant Weapon - Greater Agility | 70 | 0 | 
  | 35454 | Enchant Weapon - Major Healing | 70 | 0 | 
  | 35455 | Enchant Weapon - Major Intellect | 70 | 0 | 
  | 35456 | Enchant Weapon - Major Spellpower | 70 | 0 | 
  | 35457 | Enchant Weapon - Major Striking | 70 | 0 | 
  | 35458 | Enchant Weapon - Mongoose | 70 | 0 | 
  | 35459 | Enchant Weapon - Potency | 70 | 0 | 
  | 35460 | Enchant Weapon - Soulfrost | 70 | 0 | 
  | 35461 | Enchant Weapon - Spellsurge | 70 | 0 | 
  | 35462 | Enchant Weapon - Sunfire | 70 | 0 | 
  | 36889 | Demonic Healthstone | 73 | 63 | 
  | 36890 | Demonic Healthstone | 73 | 63 | 
  | 36891 | Demonic Healthstone | 73 | 63 | 
  | 36892 | Fel Healthstone | 79 | 69 | 
  | 36893 | Fel Healthstone | 79 | 69 | 
  | 36894 | Fel Healthstone | 79 | 69 | 
  | 36899 | Exceptional Mana Oil | 80 | 72 | 
  | 36900 | Exceptional Wizard Oil | 80 | 72 | 
  | 37464 | Winterfin Horn of Distress | 138 | 0 | 
  | 39213 | Massive Seaforium Charge | 70 | 0 | 
  | 39969 | Fire Seed | 75 | 0 | 
  | 39970 | Fire Leaf | 75 | 0 | 
  | 40773 | Master Firestone | 66 | 0 | 
  | 41173 | Fel Firestone | 74 | 0 | 
  | 41174 | Grand Firestone | 80 | 0 | 
  | 41193 | Major Spellstone | 60 | 0 | 
  | 41194 | Master Spellstone | 66 | 0 | 
  | 41195 | Demonic Spellstone | 72 | 0 | 
  | 41196 | Grand Spellstone | 78 | 0 | 
  | 41367 | Dark Jade Focusing Lens | 75 | 0 | 
  | 41509 | Frostweave Net | 72 | 0 | 
  | 42420 | Shadow Crystal Focusing Lens | 75 | 0 | 
  | 42421 | Shadow Jade Focusing Lens | 75 | 0 | 
  | 42986 | The RP-GG | 70 | 0 | 
  | 43002 | Inflatable Land Mines | 70 | 0 | 
  | 43230 | Instant Poison VIII | 73 | 73 | 
  | 43231 | Instant Poison IX | 79 | 79 | 
  | 43232 | Deadly Poison VIII | 76 | 76 | 
  | 43233 | Deadly Poison IX | 80 | 80 | 
  | 43234 | Wound Poison VI | 72 | 72 | 
  | 43235 | Wound Poison VII | 78 | 78 | 
  | 43237 | Anesthetic Poison II | 77 | 77 | 
  | 43302 | Inscription of High Discipline | 80 | 80 | 
  | 43303 | Inscription of the Frostblade | 80 | 80 | 
  | 43304 | Inscription of Kings | 80 | 80 | 
  | 43853 | Titanium Skeleton Key | 80 | 0 | 
  | 43854 | Cobalt Skeleton Key | 70 | 0 | 
  | 44506 | Saronite Arrow Maker | 80 | 0 | 
  | 44507 | Ultrasafe Bullet Machine | 80 | 0 | 
  | 49633 | Drums of Forgotten Kings | 75 | 80 | 
  | 49634 | Drums of the Wild | 75 | 80 | 

  </details>
 
21835, 21927, 22053, 22054, 22055, 22103, 22104, 22105, 22521, 22522, 23528, 23529, 23559, 23575, 23576, 23862, 24268, 24269, 25521, 25679, 28420, 28421, 29528, 29529, 29530, 29531, 29532, 31437, 32839, 32849, 32850, 32851, 32852, 33930, 33931, 33932, 33933, 34504, 34538, 34539, 35287, 35396, 35397, 35398, 35399, 35400, 35417, 35418, 35419, 35420, 35421, 35422, 35423, 35424, 35425, 35426, 35427, 35428, 35429, 35430, 35431, 35432, 35433, 35434, 35435, 35436, 35437, 35438, 35439, 35440, 35441, 35442, 35443, 35444, 35445, 35446, 35447, 35448, 35449, 35450, 35451, 35452, 35453, 35454, 35455, 35456, 35457, 35458, 35459, 35460, 35461, 35462, 36889, 36890, 36891, 36892, 36893, 36894, 36899, 36900, 37464, 39213, 39969, 39970, 40773, 41173, 41174, 41193, 41194, 41195, 41196, 41367, 41509, 42420, 42421, 42986, 43002, 43230, 43231, 43232, 43233, 43234, 43235, 43237, 43302, 43303, 43304, 43853, 43854, 44506, 44507, 49633, 49634
 
 <hr>
 
 ## Concatenated Consumeables:

 [21835](https://tbc.wowhead.com/item=21835/), [21927](https://tbc.wowhead.com/item=21927/), [22044](https://tbc.wowhead.com/item=22044/), [22053](https://tbc.wowhead.com/item=22053/), [22054](https://tbc.wowhead.com/item=22054/), [22055](https://tbc.wowhead.com/item=22055/), [22103](https://tbc.wowhead.com/item=22103/), [22104](https://tbc.wowhead.com/item=22104/), [22105](https://tbc.wowhead.com/item=22105/), [22116](https://tbc.wowhead.com/item=22116/), [22521](https://tbc.wowhead.com/item=22521/), [22522](https://tbc.wowhead.com/item=22522/), [22795](https://tbc.wowhead.com/item=22795/), [22823](https://tbc.wowhead.com/item=22823/), [22824](https://tbc.wowhead.com/item=22824/), [22825](https://tbc.wowhead.com/item=22825/), [22826](https://tbc.wowhead.com/item=22826/), [22827](https://tbc.wowhead.com/item=22827/), [22828](https://tbc.wowhead.com/item=22828/), [22829](https://tbc.wowhead.com/item=22829/), [22830](https://tbc.wowhead.com/item=22830/), [22831](https://tbc.wowhead.com/item=22831/), [22832](https://tbc.wowhead.com/item=22832/), [22833](https://tbc.wowhead.com/item=22833/), [22834](https://tbc.wowhead.com/item=22834/), [22835](https://tbc.wowhead.com/item=22835/), [22836](https://tbc.wowhead.com/item=22836/), [22837](https://tbc.wowhead.com/item=22837/), [22838](https://tbc.wowhead.com/item=22838/), [22839](https://tbc.wowhead.com/item=22839/), [22840](https://tbc.wowhead.com/item=22840/), [22841](https://tbc.wowhead.com/item=22841/), [22842](https://tbc.wowhead.com/item=22842/), [22844](https://tbc.wowhead.com/item=22844/), [22845](https://tbc.wowhead.com/item=22845/), [22846](https://tbc.wowhead.com/item=22846/), [22847](https://tbc.wowhead.com/item=22847/), [22848](https://tbc.wowhead.com/item=22848/), [22849](https://tbc.wowhead.com/item=22849/), [22850](https://tbc.wowhead.com/item=22850/), [22851](https://tbc.wowhead.com/item=22851/), [22853](https://tbc.wowhead.com/item=22853/), [22854](https://tbc.wowhead.com/item=22854/), [22861](https://tbc.wowhead.com/item=22861/), [22866](https://tbc.wowhead.com/item=22866/), [22871](https://tbc.wowhead.com/item=22871/), [23528](https://tbc.wowhead.com/item=23528/), [23529](https://tbc.wowhead.com/item=23529/), [23530](https://tbc.wowhead.com/item=23530/), [23559](https://tbc.wowhead.com/item=23559/), [23575](https://tbc.wowhead.com/item=23575/), [23576](https://tbc.wowhead.com/item=23576/), [23585](https://tbc.wowhead.com/item=23585/), [23822](https://tbc.wowhead.com/item=23822/), [23823](https://tbc.wowhead.com/item=23823/), [23862](https://tbc.wowhead.com/item=23862/), [24006](https://tbc.wowhead.com/item=24006/), [24007](https://tbc.wowhead.com/item=24007/), [24008](https://tbc.wowhead.com/item=24008/), [24009](https://tbc.wowhead.com/item=24009/), [24268](https://tbc.wowhead.com/item=24268/), [24269](https://tbc.wowhead.com/item=24269/), [24273](https://tbc.wowhead.com/item=24273/), [24274](https://tbc.wowhead.com/item=24274/), [24275](https://tbc.wowhead.com/item=24275/), [24276](https://tbc.wowhead.com/item=24276/), [24429](https://tbc.wowhead.com/item=24429/), [24520](https://tbc.wowhead.com/item=24520/), [24522](https://tbc.wowhead.com/item=24522/), [24539](https://tbc.wowhead.com/item=24539/), [24579](https://tbc.wowhead.com/item=24579/), [24581](https://tbc.wowhead.com/item=24581/), [25521](https://tbc.wowhead.com/item=25521/), [25539](https://tbc.wowhead.com/item=25539/), [25650](https://tbc.wowhead.com/item=25650/), [25651](https://tbc.wowhead.com/item=25651/), [25652](https://tbc.wowhead.com/item=25652/), [25679](https://tbc.wowhead.com/item=25679/), [25884](https://tbc.wowhead.com/item=25884/), [27388](https://tbc.wowhead.com/item=27388/), [27498](https://tbc.wowhead.com/item=27498/), [27499](https://tbc.wowhead.com/item=27499/), [27500](https://tbc.wowhead.com/item=27500/), [27501](https://tbc.wowhead.com/item=27501/), [27502](https://tbc.wowhead.com/item=27502/), [27503](https://tbc.wowhead.com/item=27503/), [27651](https://tbc.wowhead.com/item=27651/), [27655](https://tbc.wowhead.com/item=27655/), [27656](https://tbc.wowhead.com/item=27656/), [27657](https://tbc.wowhead.com/item=27657/), [27658](https://tbc.wowhead.com/item=27658/), [27659](https://tbc.wowhead.com/item=27659/), [27660](https://tbc.wowhead.com/item=27660/), [27661](https://tbc.wowhead.com/item=27661/), [27662](https://tbc.wowhead.com/item=27662/), [27663](https://tbc.wowhead.com/item=27663/), [27664](https://tbc.wowhead.com/item=27664/), [27665](https://tbc.wowhead.com/item=27665/), [27666](https://tbc.wowhead.com/item=27666/), [27667](https://tbc.wowhead.com/item=27667/), [27854](https://tbc.wowhead.com/item=27854/), [27855](https://tbc.wowhead.com/item=27855/), [27856](https://tbc.wowhead.com/item=27856/), [27857](https://tbc.wowhead.com/item=27857/), [27858](https://tbc.wowhead.com/item=27858/), [27859](https://tbc.wowhead.com/item=27859/), [27860](https://tbc.wowhead.com/item=27860/), [28100](https://tbc.wowhead.com/item=28100/), [28101](https://tbc.wowhead.com/item=28101/), [28102](https://tbc.wowhead.com/item=28102/), [28103](https://tbc.wowhead.com/item=28103/), [28104](https://tbc.wowhead.com/item=28104/), [28112](https://tbc.wowhead.com/item=28112/), [28399](https://tbc.wowhead.com/item=28399/), [28420](https://tbc.wowhead.com/item=28420/), [28421](https://tbc.wowhead.com/item=28421/), [28486](https://tbc.wowhead.com/item=28486/), [29393](https://tbc.wowhead.com/item=29393/), [29394](https://tbc.wowhead.com/item=29394/), [29395](https://tbc.wowhead.com/item=29395/), [29401](https://tbc.wowhead.com/item=29401/), [29412](https://tbc.wowhead.com/item=29412/), [29448](https://tbc.wowhead.com/item=29448/), [29449](https://tbc.wowhead.com/item=29449/), [29450](https://tbc.wowhead.com/item=29450/), [29451](https://tbc.wowhead.com/item=29451/), [29452](https://tbc.wowhead.com/item=29452/), [29453](https://tbc.wowhead.com/item=29453/), [29454](https://tbc.wowhead.com/item=29454/), [29482](https://tbc.wowhead.com/item=29482/), [29483](https://tbc.wowhead.com/item=29483/), [29485](https://tbc.wowhead.com/item=29485/), [29486](https://tbc.wowhead.com/item=29486/), [29487](https://tbc.wowhead.com/item=29487/), [29488](https://tbc.wowhead.com/item=29488/), [29528](https://tbc.wowhead.com/item=29528/), [29529](https://tbc.wowhead.com/item=29529/), [29530](https://tbc.wowhead.com/item=29530/), [29531](https://tbc.wowhead.com/item=29531/), [29532](https://tbc.wowhead.com/item=29532/), [29533](https://tbc.wowhead.com/item=29533/), [29534](https://tbc.wowhead.com/item=29534/), [29535](https://tbc.wowhead.com/item=29535/), [29536](https://tbc.wowhead.com/item=29536/), [29778](https://tbc.wowhead.com/item=29778/), [30155](https://tbc.wowhead.com/item=30155/), [30355](https://tbc.wowhead.com/item=30355/), [30357](https://tbc.wowhead.com/item=30357/), [30358](https://tbc.wowhead.com/item=30358/), [30359](https://tbc.wowhead.com/item=30359/), [30361](https://tbc.wowhead.com/item=30361/), [30457](https://tbc.wowhead.com/item=30457/), [30458](https://tbc.wowhead.com/item=30458/), [30610](https://tbc.wowhead.com/item=30610/), [30690](https://tbc.wowhead.com/item=30690/), [30703](https://tbc.wowhead.com/item=30703/), [31337](https://tbc.wowhead.com/item=31337/), [31437](https://tbc.wowhead.com/item=31437/), [31449](https://tbc.wowhead.com/item=31449/), [31450](https://tbc.wowhead.com/item=31450/), [31451](https://tbc.wowhead.com/item=31451/), [31535](https://tbc.wowhead.com/item=31535/), [31672](https://tbc.wowhead.com/item=31672/), [31673](https://tbc.wowhead.com/item=31673/), [31676](https://tbc.wowhead.com/item=31676/), [31677](https://tbc.wowhead.com/item=31677/), [31679](https://tbc.wowhead.com/item=31679/), [31838](https://tbc.wowhead.com/item=31838/), [31839](https://tbc.wowhead.com/item=31839/), [31840](https://tbc.wowhead.com/item=31840/), [31841](https://tbc.wowhead.com/item=31841/), [31852](https://tbc.wowhead.com/item=31852/), [31853](https://tbc.wowhead.com/item=31853/), [31854](https://tbc.wowhead.com/item=31854/), [31855](https://tbc.wowhead.com/item=31855/), [32062](https://tbc.wowhead.com/item=32062/), [32063](https://tbc.wowhead.com/item=32063/), [32067](https://tbc.wowhead.com/item=32067/), [32068](https://tbc.wowhead.com/item=32068/), [32453](https://tbc.wowhead.com/item=32453/), [32455](https://tbc.wowhead.com/item=32455/), [32596](https://tbc.wowhead.com/item=32596/), [32597](https://tbc.wowhead.com/item=32597/), [32598](https://tbc.wowhead.com/item=32598/), [32599](https://tbc.wowhead.com/item=32599/), [32600](https://tbc.wowhead.com/item=32600/), [32601](https://tbc.wowhead.com/item=32601/), [32667](https://tbc.wowhead.com/item=32667/), [32668](https://tbc.wowhead.com/item=32668/), [32685](https://tbc.wowhead.com/item=32685/), [32686](https://tbc.wowhead.com/item=32686/), [32721](https://tbc.wowhead.com/item=32721/), [32722](https://tbc.wowhead.com/item=32722/), [32762](https://tbc.wowhead.com/item=32762/), [32763](https://tbc.wowhead.com/item=32763/), [32764](https://tbc.wowhead.com/item=32764/), [32765](https://tbc.wowhead.com/item=32765/), [32766](https://tbc.wowhead.com/item=32766/), [32767](https://tbc.wowhead.com/item=32767/), [32783](https://tbc.wowhead.com/item=32783/), [32784](https://tbc.wowhead.com/item=32784/), [32839](https://tbc.wowhead.com/item=32839/), [32840](https://tbc.wowhead.com/item=32840/), [32844](https://tbc.wowhead.com/item=32844/), [32845](https://tbc.wowhead.com/item=32845/), [32846](https://tbc.wowhead.com/item=32846/), [32847](https://tbc.wowhead.com/item=32847/), [32849](https://tbc.wowhead.com/item=32849/), [32850](https://tbc.wowhead.com/item=32850/), [32851](https://tbc.wowhead.com/item=32851/), [32852](https://tbc.wowhead.com/item=32852/), [32898](https://tbc.wowhead.com/item=32898/), [32899](https://tbc.wowhead.com/item=32899/), [32900](https://tbc.wowhead.com/item=32900/), [32901](https://tbc.wowhead.com/item=32901/), [32902](https://tbc.wowhead.com/item=32902/), [32903](https://tbc.wowhead.com/item=32903/), [32904](https://tbc.wowhead.com/item=32904/), [32905](https://tbc.wowhead.com/item=32905/), [32909](https://tbc.wowhead.com/item=32909/), [32910](https://tbc.wowhead.com/item=32910/), [32947](https://tbc.wowhead.com/item=32947/), [32948](https://tbc.wowhead.com/item=32948/), [33025](https://tbc.wowhead.com/item=33025/), [33026](https://tbc.wowhead.com/item=33026/), [33034](https://tbc.wowhead.com/item=33034/), [33035](https://tbc.wowhead.com/item=33035/), [33036](https://tbc.wowhead.com/item=33036/), [33042](https://tbc.wowhead.com/item=33042/), [33048](https://tbc.wowhead.com/item=33048/), [33052](https://tbc.wowhead.com/item=33052/), [33053](https://tbc.wowhead.com/item=33053/), [33092](https://tbc.wowhead.com/item=33092/), [33093](https://tbc.wowhead.com/item=33093/), [33185](https://tbc.wowhead.com/item=33185/), [33208](https://tbc.wowhead.com/item=33208/), [33236](https://tbc.wowhead.com/item=33236/), [33246](https://tbc.wowhead.com/item=33246/), [33254](https://tbc.wowhead.com/item=33254/), [33312](https://tbc.wowhead.com/item=33312/), [33443](https://tbc.wowhead.com/item=33443/), [33444](https://tbc.wowhead.com/item=33444/), [33445](https://tbc.wowhead.com/item=33445/), [33447](https://tbc.wowhead.com/item=33447/), [33448](https://tbc.wowhead.com/item=33448/), [33449](https://tbc.wowhead.com/item=33449/), [33451](https://tbc.wowhead.com/item=33451/), [33452](https://tbc.wowhead.com/item=33452/), [33454](https://tbc.wowhead.com/item=33454/), [33457](https://tbc.wowhead.com/item=33457/), [33458](https://tbc.wowhead.com/item=33458/), [33459](https://tbc.wowhead.com/item=33459/), [33460](https://tbc.wowhead.com/item=33460/), [33461](https://tbc.wowhead.com/item=33461/), [33462](https://tbc.wowhead.com/item=33462/), [33825](https://tbc.wowhead.com/item=33825/), [33866](https://tbc.wowhead.com/item=33866/), [33867](https://tbc.wowhead.com/item=33867/), [33872](https://tbc.wowhead.com/item=33872/), [33874](https://tbc.wowhead.com/item=33874/), [33930](https://tbc.wowhead.com/item=33930/), [33931](https://tbc.wowhead.com/item=33931/), [33932](https://tbc.wowhead.com/item=33932/), [33933](https://tbc.wowhead.com/item=33933/), [33934](https://tbc.wowhead.com/item=33934/), [33935](https://tbc.wowhead.com/item=33935/), [34024](https://tbc.wowhead.com/item=34024/), [34062](https://tbc.wowhead.com/item=34062/), [34125](https://tbc.wowhead.com/item=34125/), [34207](https://tbc.wowhead.com/item=34207/), [34330](https://tbc.wowhead.com/item=34330/), [34410](https://tbc.wowhead.com/item=34410/), [34411](https://tbc.wowhead.com/item=34411/), [34440](https://tbc.wowhead.com/item=34440/), [34475](https://tbc.wowhead.com/item=34475/), [34504](https://tbc.wowhead.com/item=34504/), [34537](https://tbc.wowhead.com/item=34537/), [34538](https://tbc.wowhead.com/item=34538/), [34539](https://tbc.wowhead.com/item=34539/), [34747](https://tbc.wowhead.com/item=34747/), [34748](https://tbc.wowhead.com/item=34748/), [34749](https://tbc.wowhead.com/item=34749/), [34750](https://tbc.wowhead.com/item=34750/), [34751](https://tbc.wowhead.com/item=34751/), [34752](https://tbc.wowhead.com/item=34752/), [34753](https://tbc.wowhead.com/item=34753/), [34754](https://tbc.wowhead.com/item=34754/), [34755](https://tbc.wowhead.com/item=34755/), [34756](https://tbc.wowhead.com/item=34756/), [34757](https://tbc.wowhead.com/item=34757/), [34758](https://tbc.wowhead.com/item=34758/), [34759](https://tbc.wowhead.com/item=34759/), [34760](https://tbc.wowhead.com/item=34760/), [34761](https://tbc.wowhead.com/item=34761/), [34762](https://tbc.wowhead.com/item=34762/), [34763](https://tbc.wowhead.com/item=34763/), [34764](https://tbc.wowhead.com/item=34764/), [34765](https://tbc.wowhead.com/item=34765/), [34766](https://tbc.wowhead.com/item=34766/), [34767](https://tbc.wowhead.com/item=34767/), [34768](https://tbc.wowhead.com/item=34768/), [34769](https://tbc.wowhead.com/item=34769/), [34780](https://tbc.wowhead.com/item=34780/), [34836](https://tbc.wowhead.com/item=34836/), [35287](https://tbc.wowhead.com/item=35287/), [35396](https://tbc.wowhead.com/item=35396/), [35397](https://tbc.wowhead.com/item=35397/), [35398](https://tbc.wowhead.com/item=35398/), [35399](https://tbc.wowhead.com/item=35399/), [35400](https://tbc.wowhead.com/item=35400/), [35417](https://tbc.wowhead.com/item=35417/), [35418](https://tbc.wowhead.com/item=35418/), [35419](https://tbc.wowhead.com/item=35419/), [35420](https://tbc.wowhead.com/item=35420/), [35421](https://tbc.wowhead.com/item=35421/), [35422](https://tbc.wowhead.com/item=35422/), [35423](https://tbc.wowhead.com/item=35423/), [35424](https://tbc.wowhead.com/item=35424/), [35425](https://tbc.wowhead.com/item=35425/), [35426](https://tbc.wowhead.com/item=35426/), [35427](https://tbc.wowhead.com/item=35427/), [35428](https://tbc.wowhead.com/item=35428/), [35429](https://tbc.wowhead.com/item=35429/), [35430](https://tbc.wowhead.com/item=35430/), [35431](https://tbc.wowhead.com/item=35431/), [35432](https://tbc.wowhead.com/item=35432/), [35433](https://tbc.wowhead.com/item=35433/), [35434](https://tbc.wowhead.com/item=35434/), [35435](https://tbc.wowhead.com/item=35435/), [35436](https://tbc.wowhead.com/item=35436/), [35437](https://tbc.wowhead.com/item=35437/), [35438](https://tbc.wowhead.com/item=35438/), [35439](https://tbc.wowhead.com/item=35439/), [35440](https://tbc.wowhead.com/item=35440/), [35441](https://tbc.wowhead.com/item=35441/), [35442](https://tbc.wowhead.com/item=35442/), [35443](https://tbc.wowhead.com/item=35443/), [35444](https://tbc.wowhead.com/item=35444/), [35445](https://tbc.wowhead.com/item=35445/), [35446](https://tbc.wowhead.com/item=35446/), [35447](https://tbc.wowhead.com/item=35447/), [35448](https://tbc.wowhead.com/item=35448/), [35449](https://tbc.wowhead.com/item=35449/), [35450](https://tbc.wowhead.com/item=35450/), [35451](https://tbc.wowhead.com/item=35451/), [35452](https://tbc.wowhead.com/item=35452/), [35453](https://tbc.wowhead.com/item=35453/), [35454](https://tbc.wowhead.com/item=35454/), [35455](https://tbc.wowhead.com/item=35455/), [35456](https://tbc.wowhead.com/item=35456/), [35457](https://tbc.wowhead.com/item=35457/), [35458](https://tbc.wowhead.com/item=35458/), [35459](https://tbc.wowhead.com/item=35459/), [35460](https://tbc.wowhead.com/item=35460/), [35461](https://tbc.wowhead.com/item=35461/), [35462](https://tbc.wowhead.com/item=35462/), [35716](https://tbc.wowhead.com/item=35716/), [35717](https://tbc.wowhead.com/item=35717/), [35945](https://tbc.wowhead.com/item=35945/), [35947](https://tbc.wowhead.com/item=35947/), [35948](https://tbc.wowhead.com/item=35948/), [35949](https://tbc.wowhead.com/item=35949/), [35950](https://tbc.wowhead.com/item=35950/), [35951](https://tbc.wowhead.com/item=35951/), [35952](https://tbc.wowhead.com/item=35952/), [35953](https://tbc.wowhead.com/item=35953/), [35954](https://tbc.wowhead.com/item=35954/), [36889](https://tbc.wowhead.com/item=36889/), [36890](https://tbc.wowhead.com/item=36890/), [36891](https://tbc.wowhead.com/item=36891/), [36892](https://tbc.wowhead.com/item=36892/), [36893](https://tbc.wowhead.com/item=36893/), [36894](https://tbc.wowhead.com/item=36894/), [36895](https://tbc.wowhead.com/item=36895/), [36899](https://tbc.wowhead.com/item=36899/), [36900](https://tbc.wowhead.com/item=36900/), [37091](https://tbc.wowhead.com/item=37091/), [37092](https://tbc.wowhead.com/item=37092/), [37093](https://tbc.wowhead.com/item=37093/), [37094](https://tbc.wowhead.com/item=37094/), [37097](https://tbc.wowhead.com/item=37097/), [37098](https://tbc.wowhead.com/item=37098/), [37252](https://tbc.wowhead.com/item=37252/), [37253](https://tbc.wowhead.com/item=37253/), [37449](https://tbc.wowhead.com/item=37449/), [37452](https://tbc.wowhead.com/item=37452/), [37464](https://tbc.wowhead.com/item=37464/), [37603](https://tbc.wowhead.com/item=37603/), [38351](https://tbc.wowhead.com/item=38351/), [38371](https://tbc.wowhead.com/item=38371/), [38372](https://tbc.wowhead.com/item=38372/), [38373](https://tbc.wowhead.com/item=38373/), [38374](https://tbc.wowhead.com/item=38374/), [38375](https://tbc.wowhead.com/item=38375/), [38376](https://tbc.wowhead.com/item=38376/), [38377](https://tbc.wowhead.com/item=38377/), [38378](https://tbc.wowhead.com/item=38378/), [38427](https://tbc.wowhead.com/item=38427/), [38428](https://tbc.wowhead.com/item=38428/), [38430](https://tbc.wowhead.com/item=38430/), [38431](https://tbc.wowhead.com/item=38431/), [38698](https://tbc.wowhead.com/item=38698/), [38706](https://tbc.wowhead.com/item=38706/), [38865](https://tbc.wowhead.com/item=38865/), [38871](https://tbc.wowhead.com/item=38871/), [38873](https://tbc.wowhead.com/item=38873/), [38874](https://tbc.wowhead.com/item=38874/), [38882](https://tbc.wowhead.com/item=38882/), [38883](https://tbc.wowhead.com/item=38883/), [38884](https://tbc.wowhead.com/item=38884/), [38885](https://tbc.wowhead.com/item=38885/), [38886](https://tbc.wowhead.com/item=38886/), [38887](https://tbc.wowhead.com/item=38887/), [38888](https://tbc.wowhead.com/item=38888/), [38889](https://tbc.wowhead.com/item=38889/), [38890](https://tbc.wowhead.com/item=38890/), [38891](https://tbc.wowhead.com/item=38891/), [38892](https://tbc.wowhead.com/item=38892/), [38893](https://tbc.wowhead.com/item=38893/), [38894](https://tbc.wowhead.com/item=38894/), [38895](https://tbc.wowhead.com/item=38895/), [38897](https://tbc.wowhead.com/item=38897/), [38898](https://tbc.wowhead.com/item=38898/), [38899](https://tbc.wowhead.com/item=38899/), [38900](https://tbc.wowhead.com/item=38900/), [38901](https://tbc.wowhead.com/item=38901/), [38902](https://tbc.wowhead.com/item=38902/), [38903](https://tbc.wowhead.com/item=38903/), [38904](https://tbc.wowhead.com/item=38904/), [38905](https://tbc.wowhead.com/item=38905/), [38906](https://tbc.wowhead.com/item=38906/), [38907](https://tbc.wowhead.com/item=38907/), [38908](https://tbc.wowhead.com/item=38908/), [38909](https://tbc.wowhead.com/item=38909/), [38910](https://tbc.wowhead.com/item=38910/), [38911](https://tbc.wowhead.com/item=38911/), [38912](https://tbc.wowhead.com/item=38912/), [38913](https://tbc.wowhead.com/item=38913/), [38914](https://tbc.wowhead.com/item=38914/), [38915](https://tbc.wowhead.com/item=38915/), [38917](https://tbc.wowhead.com/item=38917/), [38918](https://tbc.wowhead.com/item=38918/), [38919](https://tbc.wowhead.com/item=38919/), [38920](https://tbc.wowhead.com/item=38920/), [38921](https://tbc.wowhead.com/item=38921/), [38922](https://tbc.wowhead.com/item=38922/), [38923](https://tbc.wowhead.com/item=38923/), [38924](https://tbc.wowhead.com/item=38924/), [38925](https://tbc.wowhead.com/item=38925/), [38926](https://tbc.wowhead.com/item=38926/), [38927](https://tbc.wowhead.com/item=38927/), [38928](https://tbc.wowhead.com/item=38928/), [38930](https://tbc.wowhead.com/item=38930/), [38931](https://tbc.wowhead.com/item=38931/), [38932](https://tbc.wowhead.com/item=38932/), [38933](https://tbc.wowhead.com/item=38933/), [38934](https://tbc.wowhead.com/item=38934/), [38935](https://tbc.wowhead.com/item=38935/), [38936](https://tbc.wowhead.com/item=38936/), [38937](https://tbc.wowhead.com/item=38937/), [38939](https://tbc.wowhead.com/item=38939/), [38940](https://tbc.wowhead.com/item=38940/), [38941](https://tbc.wowhead.com/item=38941/), [38942](https://tbc.wowhead.com/item=38942/), [38943](https://tbc.wowhead.com/item=38943/), [38944](https://tbc.wowhead.com/item=38944/), [38945](https://tbc.wowhead.com/item=38945/), [38946](https://tbc.wowhead.com/item=38946/), [38947](https://tbc.wowhead.com/item=38947/), [38948](https://tbc.wowhead.com/item=38948/), [38949](https://tbc.wowhead.com/item=38949/), [38950](https://tbc.wowhead.com/item=38950/), [38951](https://tbc.wowhead.com/item=38951/), [38953](https://tbc.wowhead.com/item=38953/), [38954](https://tbc.wowhead.com/item=38954/), [38955](https://tbc.wowhead.com/item=38955/), [38956](https://tbc.wowhead.com/item=38956/), [38957](https://tbc.wowhead.com/item=38957/), [38958](https://tbc.wowhead.com/item=38958/), [38959](https://tbc.wowhead.com/item=38959/), [38960](https://tbc.wowhead.com/item=38960/), [38961](https://tbc.wowhead.com/item=38961/), [38962](https://tbc.wowhead.com/item=38962/), [38963](https://tbc.wowhead.com/item=38963/), [38964](https://tbc.wowhead.com/item=38964/), [38965](https://tbc.wowhead.com/item=38965/), [38966](https://tbc.wowhead.com/item=38966/), [38967](https://tbc.wowhead.com/item=38967/), [38968](https://tbc.wowhead.com/item=38968/), [38969](https://tbc.wowhead.com/item=38969/), [38970](https://tbc.wowhead.com/item=38970/), [38971](https://tbc.wowhead.com/item=38971/), [38972](https://tbc.wowhead.com/item=38972/), [38973](https://tbc.wowhead.com/item=38973/), [38974](https://tbc.wowhead.com/item=38974/), [38975](https://tbc.wowhead.com/item=38975/), [38976](https://tbc.wowhead.com/item=38976/), [38977](https://tbc.wowhead.com/item=38977/), [38978](https://tbc.wowhead.com/item=38978/), [38979](https://tbc.wowhead.com/item=38979/), [38980](https://tbc.wowhead.com/item=38980/), [38981](https://tbc.wowhead.com/item=38981/), [38982](https://tbc.wowhead.com/item=38982/), [38983](https://tbc.wowhead.com/item=38983/), [38984](https://tbc.wowhead.com/item=38984/), [38985](https://tbc.wowhead.com/item=38985/), [38986](https://tbc.wowhead.com/item=38986/), [38987](https://tbc.wowhead.com/item=38987/), [38988](https://tbc.wowhead.com/item=38988/), [38989](https://tbc.wowhead.com/item=38989/), [38990](https://tbc.wowhead.com/item=38990/), [38991](https://tbc.wowhead.com/item=38991/), [38992](https://tbc.wowhead.com/item=38992/), [38993](https://tbc.wowhead.com/item=38993/), [38994](https://tbc.wowhead.com/item=38994/), [38995](https://tbc.wowhead.com/item=38995/), [38996](https://tbc.wowhead.com/item=38996/), [38997](https://tbc.wowhead.com/item=38997/), [38998](https://tbc.wowhead.com/item=38998/), [38999](https://tbc.wowhead.com/item=38999/), [39000](https://tbc.wowhead.com/item=39000/), [39001](https://tbc.wowhead.com/item=39001/), [39002](https://tbc.wowhead.com/item=39002/), [39003](https://tbc.wowhead.com/item=39003/), [39004](https://tbc.wowhead.com/item=39004/), [39005](https://tbc.wowhead.com/item=39005/), [39006](https://tbc.wowhead.com/item=39006/), [39213](https://tbc.wowhead.com/item=39213/), [39327](https://tbc.wowhead.com/item=39327/), [39520](https://tbc.wowhead.com/item=39520/), [39666](https://tbc.wowhead.com/item=39666/), [39671](https://tbc.wowhead.com/item=39671/), [39691](https://tbc.wowhead.com/item=39691/), [39738](https://tbc.wowhead.com/item=39738/), [39969](https://tbc.wowhead.com/item=39969/), [39970](https://tbc.wowhead.com/item=39970/), [40067](https://tbc.wowhead.com/item=40067/), [40068](https://tbc.wowhead.com/item=40068/), [40070](https://tbc.wowhead.com/item=40070/), [40072](https://tbc.wowhead.com/item=40072/), [40073](https://tbc.wowhead.com/item=40073/), [40076](https://tbc.wowhead.com/item=40076/), [40077](https://tbc.wowhead.com/item=40077/), [40078](https://tbc.wowhead.com/item=40078/), [40079](https://tbc.wowhead.com/item=40079/), [40081](https://tbc.wowhead.com/item=40081/), [40082](https://tbc.wowhead.com/item=40082/), [40083](https://tbc.wowhead.com/item=40083/), [40084](https://tbc.wowhead.com/item=40084/), [40087](https://tbc.wowhead.com/item=40087/), [40093](https://tbc.wowhead.com/item=40093/), [40097](https://tbc.wowhead.com/item=40097/), [40109](https://tbc.wowhead.com/item=40109/), [40202](https://tbc.wowhead.com/item=40202/), [40211](https://tbc.wowhead.com/item=40211/), [40212](https://tbc.wowhead.com/item=40212/), [40213](https://tbc.wowhead.com/item=40213/), [40214](https://tbc.wowhead.com/item=40214/), [40215](https://tbc.wowhead.com/item=40215/), [40216](https://tbc.wowhead.com/item=40216/), [40217](https://tbc.wowhead.com/item=40217/), [40356](https://tbc.wowhead.com/item=40356/), [40357](https://tbc.wowhead.com/item=40357/), [40358](https://tbc.wowhead.com/item=40358/), [40359](https://tbc.wowhead.com/item=40359/), [40404](https://tbc.wowhead.com/item=40404/), [40725](https://tbc.wowhead.com/item=40725/), [40773](https://tbc.wowhead.com/item=40773/), [40776](https://tbc.wowhead.com/item=40776/), [41091](https://tbc.wowhead.com/item=41091/), [41093](https://tbc.wowhead.com/item=41093/), [41111](https://tbc.wowhead.com/item=41111/), [41118](https://tbc.wowhead.com/item=41118/), [41166](https://tbc.wowhead.com/item=41166/), [41173](https://tbc.wowhead.com/item=41173/), [41174](https://tbc.wowhead.com/item=41174/), [41193](https://tbc.wowhead.com/item=41193/), [41194](https://tbc.wowhead.com/item=41194/), [41195](https://tbc.wowhead.com/item=41195/), [41196](https://tbc.wowhead.com/item=41196/), [41367](https://tbc.wowhead.com/item=41367/), [41509](https://tbc.wowhead.com/item=41509/), [41601](https://tbc.wowhead.com/item=41601/), [41602](https://tbc.wowhead.com/item=41602/), [41603](https://tbc.wowhead.com/item=41603/), [41604](https://tbc.wowhead.com/item=41604/), [41605](https://tbc.wowhead.com/item=41605/), [41606](https://tbc.wowhead.com/item=41606/), [41611](https://tbc.wowhead.com/item=41611/), [41729](https://tbc.wowhead.com/item=41729/), [41731](https://tbc.wowhead.com/item=41731/), [41751](https://tbc.wowhead.com/item=41751/), [41976](https://tbc.wowhead.com/item=41976/), [42420](https://tbc.wowhead.com/item=42420/), [42421](https://tbc.wowhead.com/item=42421/), [42428](https://tbc.wowhead.com/item=42428/), [42429](https://tbc.wowhead.com/item=42429/), [42430](https://tbc.wowhead.com/item=42430/), [42431](https://tbc.wowhead.com/item=42431/), [42432](https://tbc.wowhead.com/item=42432/), [42433](https://tbc.wowhead.com/item=42433/), [42434](https://tbc.wowhead.com/item=42434/), [42436](https://tbc.wowhead.com/item=42436/), [42438](https://tbc.wowhead.com/item=42438/), [42439](https://tbc.wowhead.com/item=42439/), [42500](https://tbc.wowhead.com/item=42500/), [42545](https://tbc.wowhead.com/item=42545/), [42590](https://tbc.wowhead.com/item=42590/), [42777](https://tbc.wowhead.com/item=42777/), [42778](https://tbc.wowhead.com/item=42778/), [42779](https://tbc.wowhead.com/item=42779/), [42942](https://tbc.wowhead.com/item=42942/), [42986](https://tbc.wowhead.com/item=42986/), [42993](https://tbc.wowhead.com/item=42993/), [42994](https://tbc.wowhead.com/item=42994/), [42995](https://tbc.wowhead.com/item=42995/), [42996](https://tbc.wowhead.com/item=42996/), [42997](https://tbc.wowhead.com/item=42997/), [42998](https://tbc.wowhead.com/item=42998/), [42999](https://tbc.wowhead.com/item=42999/), [43000](https://tbc.wowhead.com/item=43000/), [43001](https://tbc.wowhead.com/item=43001/), [43002](https://tbc.wowhead.com/item=43002/), [43004](https://tbc.wowhead.com/item=43004/), [43005](https://tbc.wowhead.com/item=43005/), [43015](https://tbc.wowhead.com/item=43015/), [43086](https://tbc.wowhead.com/item=43086/), [43087](https://tbc.wowhead.com/item=43087/), [43088](https://tbc.wowhead.com/item=43088/), [43097](https://tbc.wowhead.com/item=43097/), [43135](https://tbc.wowhead.com/item=43135/), [43230](https://tbc.wowhead.com/item=43230/), [43231](https://tbc.wowhead.com/item=43231/), [43232](https://tbc.wowhead.com/item=43232/), [43233](https://tbc.wowhead.com/item=43233/), [43234](https://tbc.wowhead.com/item=43234/), [43235](https://tbc.wowhead.com/item=43235/), [43236](https://tbc.wowhead.com/item=43236/), [43237](https://tbc.wowhead.com/item=43237/), [43268](https://tbc.wowhead.com/item=43268/), [43302](https://tbc.wowhead.com/item=43302/), [43303](https://tbc.wowhead.com/item=43303/), [43304](https://tbc.wowhead.com/item=43304/), [43463](https://tbc.wowhead.com/item=43463/), [43464](https://tbc.wowhead.com/item=43464/), [43465](https://tbc.wowhead.com/item=43465/), [43466](https://tbc.wowhead.com/item=43466/), [43467](https://tbc.wowhead.com/item=43467/), [43468](https://tbc.wowhead.com/item=43468/), [43478](https://tbc.wowhead.com/item=43478/), [43480](https://tbc.wowhead.com/item=43480/), [43488](https://tbc.wowhead.com/item=43488/), [43490](https://tbc.wowhead.com/item=43490/), [43491](https://tbc.wowhead.com/item=43491/), [43492](https://tbc.wowhead.com/item=43492/), [43518](https://tbc.wowhead.com/item=43518/), [43523](https://tbc.wowhead.com/item=43523/), [43530](https://tbc.wowhead.com/item=43530/), [43531](https://tbc.wowhead.com/item=43531/), [43569](https://tbc.wowhead.com/item=43569/), [43570](https://tbc.wowhead.com/item=43570/), [43853](https://tbc.wowhead.com/item=43853/), [43854](https://tbc.wowhead.com/item=43854/), [43987](https://tbc.wowhead.com/item=43987/), [44012](https://tbc.wowhead.com/item=44012/), [44049](https://tbc.wowhead.com/item=44049/), [44071](https://tbc.wowhead.com/item=44071/), [44072](https://tbc.wowhead.com/item=44072/), [44315](https://tbc.wowhead.com/item=44315/), [44325](https://tbc.wowhead.com/item=44325/), [44327](https://tbc.wowhead.com/item=44327/), [44328](https://tbc.wowhead.com/item=44328/), [44329](https://tbc.wowhead.com/item=44329/), [44330](https://tbc.wowhead.com/item=44330/), [44331](https://tbc.wowhead.com/item=44331/), [44332](https://tbc.wowhead.com/item=44332/), [44449](https://tbc.wowhead.com/item=44449/), [44453](https://tbc.wowhead.com/item=44453/), [44455](https://tbc.wowhead.com/item=44455/), [44456](https://tbc.wowhead.com/item=44456/), [44457](https://tbc.wowhead.com/item=44457/), [44458](https://tbc.wowhead.com/item=44458/), [44463](https://tbc.wowhead.com/item=44463/), [44465](https://tbc.wowhead.com/item=44465/), [44466](https://tbc.wowhead.com/item=44466/), [44467](https://tbc.wowhead.com/item=44467/), [44469](https://tbc.wowhead.com/item=44469/), [44470](https://tbc.wowhead.com/item=44470/), [44493](https://tbc.wowhead.com/item=44493/), [44497](https://tbc.wowhead.com/item=44497/), [44506](https://tbc.wowhead.com/item=44506/), [44507](https://tbc.wowhead.com/item=44507/), [44607](https://tbc.wowhead.com/item=44607/), [44608](https://tbc.wowhead.com/item=44608/), [44609](https://tbc.wowhead.com/item=44609/), [44610](https://tbc.wowhead.com/item=44610/), [44612](https://tbc.wowhead.com/item=44612/), [44613](https://tbc.wowhead.com/item=44613/), [44616](https://tbc.wowhead.com/item=44616/), [44618](https://tbc.wowhead.com/item=44618/), [44619](https://tbc.wowhead.com/item=44619/), [44621](https://tbc.wowhead.com/item=44621/), [44622](https://tbc.wowhead.com/item=44622/), [44623](https://tbc.wowhead.com/item=44623/), [44625](https://tbc.wowhead.com/item=44625/), [44626](https://tbc.wowhead.com/item=44626/), [44627](https://tbc.wowhead.com/item=44627/), [44629](https://tbc.wowhead.com/item=44629/), [44632](https://tbc.wowhead.com/item=44632/), [44698](https://tbc.wowhead.com/item=44698/), [44722](https://tbc.wowhead.com/item=44722/), [44728](https://tbc.wowhead.com/item=44728/), [44749](https://tbc.wowhead.com/item=44749/), [44750](https://tbc.wowhead.com/item=44750/), [44815](https://tbc.wowhead.com/item=44815/), [44936](https://tbc.wowhead.com/item=44936/), [44939](https://tbc.wowhead.com/item=44939/), [44940](https://tbc.wowhead.com/item=44940/), [44941](https://tbc.wowhead.com/item=44941/), [44943](https://tbc.wowhead.com/item=44943/), [44946](https://tbc.wowhead.com/item=44946/), [44947](https://tbc.wowhead.com/item=44947/), [44953](https://tbc.wowhead.com/item=44953/), [44963](https://tbc.wowhead.com/item=44963/), [45006](https://tbc.wowhead.com/item=45006/), [45007](https://tbc.wowhead.com/item=45007/), [45008](https://tbc.wowhead.com/item=45008/), [45009](https://tbc.wowhead.com/item=45009/), [45038](https://tbc.wowhead.com/item=45038/), [45056](https://tbc.wowhead.com/item=45056/), [45060](https://tbc.wowhead.com/item=45060/), [45126](https://tbc.wowhead.com/item=45126/), [45276](https://tbc.wowhead.com/item=45276/), [45277](https://tbc.wowhead.com/item=45277/), [45279](https://tbc.wowhead.com/item=45279/), [45705](https://tbc.wowhead.com/item=45705/), [45901](https://tbc.wowhead.com/item=45901/), [45932](https://tbc.wowhead.com/item=45932/), [46026](https://tbc.wowhead.com/item=46026/), [46098](https://tbc.wowhead.com/item=46098/), [46376](https://tbc.wowhead.com/item=46376/), [46377](https://tbc.wowhead.com/item=46377/), [46378](https://tbc.wowhead.com/item=46378/), [46379](https://tbc.wowhead.com/item=46379/), [46399](https://tbc.wowhead.com/item=46399/), [46400](https://tbc.wowhead.com/item=46400/), [46401](https://tbc.wowhead.com/item=46401/), [46402](https://tbc.wowhead.com/item=46402/), [46403](https://tbc.wowhead.com/item=46403/), [46847](https://tbc.wowhead.com/item=46847/), [46887](https://tbc.wowhead.com/item=46887/), [47030](https://tbc.wowhead.com/item=47030/), [47499](https://tbc.wowhead.com/item=47499/), [47541](https://tbc.wowhead.com/item=47541/), [49632](https://tbc.wowhead.com/item=49632/), [49633](https://tbc.wowhead.com/item=49633/), [49634](https://tbc.wowhead.com/item=49634/), [50816](https://tbc.wowhead.com/item=50816/), [184937](https://tbc.wowhead.com/item=184937/), [184938](https://tbc.wowhead.com/item=184938/)
 
