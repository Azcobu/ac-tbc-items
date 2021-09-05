# ac-tbc-items
Listing all prematurely available TBC/WotLK items



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
    
  2851, 22853, 22854, 22861, 22866, 32596, 32597, 32598, 32599, 32600, 32601, 32764, 32765, 32766, 32767, 32898, 32899, 32900, 32901, 33208, 35716, 35717, 40079, 40082, 40083, 40084, 40404, 44939, 45006, 45007, 45008, 45009, 46376, 46377, 46378, 46379, 47499
    
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
 
 

<hr>

  - item enhancement (subclass = 6): 
    -  TEMPORARY - only vanilla items at 60 are elemental sharpening stone 18262 and 2 rogue poisons, instant poison VI  and Deadly Poison V id 20844. There are 3 TBC items at 60, lowest id is fel sharpening stone id 23528.
    - PERMANENT: lots of ilvl 60 vanilla enhances, but none higher, and only 1 ilvl 60 TBC item, knothide armor kit 25650
    - summation: >= 61 plus knothide armor kit, fel sharpening stone, comfortable insoles, fel weightstone

<hr>

  - bandages (subclass = 7): 1 vanilla 60 item, crystal infused bandage, probably not obtainable. >= 64 catches all TBC.

<hr>

  - other (subclass = 8): highest vanilla is 58, lowest TBC is 60, so >= 60 works fine here.

<hr>

- containers (class = 1) - going to leave this group alone as TBC bags are sold in store. Nuking every Chromie-purchased bag on the server would not be a popular move.

- weapons (class = 2): a general query for all open world map = 530 mobs -> items as a catchall. However, this misses Kara + Q'D and is hugely expensive
    Vanilla weapons go up to ilvl 100, all with req. lvl 60.
   TBC items seems ot start around 23300, but old world stuff is still interspersed

All Kara items (115 weapons)
SELECT DISTINCT( it.entry), it.name, it.itemlevel, it.RequiredLevel
FROM `creature_template` ct
JOIN `creature_loot_template` clt ON ct.lootid = clt.entry
JOIN `reference_loot_template` rlt ON clt.Reference = rlt.Entry
JOIN `item_template` it ON it.entry = rlt.Item
WHERE ct.entry IN (7370, 12377, 12378, 12379, 12380) AND it.class = 2 AND it.entry > 25000

All Q'D weapons (108 weapons)
SELECT DISTINCT( it.entry), it.name, it.itemlevel, it.RequiredLevel
FROM `creature_template` ct
JOIN `creature_loot_template` clt ON ct.lootid = clt.entry
JOIN `reference_loot_template` rlt ON clt.Reference = rlt.Entry
JOIN `item_template` it ON it.entry = rlt.Item
WHERE ct.entry IN (24996, 24960, 25047, 24999, 25002, 24976, 24978, 24979, 25063, 25087, 
25548, 25073, 25060, 25001) AND it.class = 2 

- gems (class = 3): vanilla has 2 ilvl 55 and 3 ilvl 60 gems, all itemid <= 12800. Highest vanilla gem index seems to be souldarite, 19774.  The TBC gems start at 55 and all have item ids > 23000
So this query finds all TBC/Wrath gems:

SELECT it.entry, it.name, it.ItemLevel
FROM `item_template` it
WHERE it.class = 3 AND it.itemlevel >= 55 AND it.entry > 20000
  
- armour (class = 4)

Q'D Armour: - 243 items, all unuseable anyway.
SELECT DISTINCT( it.entry), it.name, it.itemlevel, it.RequiredLevel
FROM `creature_template` ct
JOIN `creature_loot_template` clt ON ct.lootid = clt.entry
JOIN `reference_loot_template` rlt ON clt.Reference = rlt.Entry
JOIN `item_template` it ON it.entry = rlt.Item
WHERE ct.entry IN (24996, 24960, 25047, 24999, 25002, 24976, 24978, 24979, 25063, 
25087, 25548, 25073, 25060, 25001)
AND it.class = 4 

Targeting Kara armour:
SELECT DISTINCT( it.entry), it.name, it.itemlevel, it.RequiredLevel
FROM `creature_template` ct
JOIN `creature_loot_template` clt ON ct.lootid = clt.entry
JOIN `reference_loot_template` rlt ON clt.Reference = rlt.Entry
JOIN `item_template` it ON it.entry = rlt.Item
WHERE ct.entry IN (7370, 12377, 12378, 12379, 12380) AND it.class = 4 AND it.entry >= 24637

- reagent (class = 5) - vanlla items go up to 60, but highest id is symbol of kings, 21177. TBC reagents are all 70+, and there;s only 3 anyway.

- projectiles (class = 6): vanilla projectiles go up to lvl 61. TBC projectiles start at ilvl 80 (wicked arrows/impact shot, lvl 55 req.) - however, as of 2.0, both these were sold in old world. Quick check shows they are already sold by 53 vendors across the old world.

- trade goods (class = 7)
  - parts (subclass = 1): >=60 looks good - lowest vanilla is 58, arcanite converter
  - explosives (subclass = 2): 1 level 60 vanilla bomb, 19831 arcane bomb. >= 60 is good otherwise though. Maybe just >= 61 and add the 1 TBC 60 item which is 23736 fel iron bomb
  - devices (subclass = 3): >= 61 + "battered steam tonk controller". There are devices (field repair bot 74a) that are ilvl 60 in classic. There are 2 TBC toys that are 60 as well (crashin' thrashin' robot and racer controller)
  - jewelcrafting (subclass = 4): >= 60 is fine - only 12 items affected, most of which are deprecated anyway.
  - cloth (subclass = 5) : ilvl >= 60, 11 items or 18 counting wrath items too
  - leather (subclass = 6): ths one is really mixed - lots of TBC leather at 60, but lots of vanilla raid leather there too. >=61 + the following - 29539 cobra scales, 25708 thick clefthoof leather, nether dragonscales, fel scales, wind scales, crystal infused leather, knothide leather scraps.)
  - metal and stone (subclass = 7) - CANNOT use >=60 as breakpoint, there are vanilla metal/stone drops that are ilvl 60 -  query needs to be >= 61 + felsteel bar, fel iron bar, fel iron ore
  - meat (subclass = 8): >= 60 seems to be fine with 1 exception, 21024 Chimaerok Tenderloin in Feralas is 60
  - herbs (subclass = 9): there are 2 ilvl 60 classic herbs, black lotus and bloodvine, and blood scythe (a tool) . >= 61 is fine + 22789 terocone, 22786 dreaming glory, 22785 felweed
  - elemental (subclass = 10): >= 60 is fne, nice clear divide for once
  - other (subclass = 11): lots of overlap. >=61 is fine, but needs to add soul essence, inscribed scrollcase, curious crate, Charged Draenethyst Crystal which are all 60
  - enchanting (subclass = 12): >= 60 is fine except for 1 overlap, 20725 nexus crystals
  - materials (subclass = 13): only 1, 23572 primal nether
  - armour enchant (subclass = 14): empty set, armour vellums
  - weapon enchantments (subclass = 15): ditto
 
- class 8 is obsolete

- recipes (class = 9)
  - book (subclass = 0): highest vanilla book is ilvl 60, lots of them. highest index is 24102. TBC books go down to 50, but they are demon training books which were removed in 3.0.2 (see https://wowwiki-archive.fandom.com/wiki/Demon_Trainer_grimoires) Skipping those, next lowest in TBC is ilvl 60, a druid cower book whch is useless since it can be learned at the trainer anyway. Moving on, lots more 61-69 demon trainer books, all junk, before we get to lvl 70 and some worthwhile items. So really looks like itemlevel >= 70 is fine.
  - leatherworking (subclass = 1): vanilla LW recipes go up to ilvl 80/skill 300. TBC LW recipes start at 57/285 skill, but that's only 1 (pattern: winter boots 34262). There's 1 x ilvl 60/skill 300 (pattern: comfortable insoles 25726), and the rest are ilvl 65/skill 325. So a query for >= ilvl 65 and skill 325 + the other 2 should work.
  - tailoring patterns (subclass = 2): lowest TBC pattern is 62/300 skill (truefaith vestments ID 29120) which looks very much like a vanilla item added later. From there on all TBC recipes need 325+ skill. Vanilla recipes go up to lvl 80, all below id 23000 though and all needing skill = 300. So the query could just be skill >= 325.
  - engineering (subclass = 3): vanilla goes up to ilvl 65/300 skill. TBC eng recipes are all through old world lvl range, but new ones are all 61+ and 305+ skill. So just skill >= 305 works.
  - blacksmithing (subclass = 4): vanilla BS recipes go up to ilvl 80/300 skill. TBC recipes starts at ilvl 63/325 skill. So again, >= 325 skill works.
  - cooking (subclass = 5): vanilla recipes go up to ilvl 60/300 skill. (only 1 though, "Recipe: Dirge's Kickin' Chimaerok Chops" ID 21025.) TBC cooking recipes are all through the old world level range, but have some overlap at lvl 60, with 8 more 60/300 skill recipes. Lowest TBC ID is 27684. Easiest to just take >= 60/skill and >= 300 and ID >22000 - verified no TBC cooking recipes have a lower ID than this.
  - alchemy (subclass = 6): vanilla goes up to 60/300 skill, 5 recipes from scholo/UBRS/BRD, etc and 1 ilvl 70, Recipe: Alchemist's Stone 13517, a TBC item added in vanilla (sold in Shattrath). The exact same 5 recipes are then duplicated in TBC as rep items. Highest vanilla 60/300 recipe index is 20761. The 5 TBC recipes at 60 are all in the 31K range, and other TBC recipes are all 61/305 and up. Multiple other TBC 61+ recipes have a 22.9K index. So query is 

SELECT it.entry, it.name, it.ItemLevel, it.RequiredSkillRank
FROM `item_template` it
WHERE it.class = 9 AND it.subclass = 6
AND it.ItemLevel >= 60 AND it.entry > 21000 OR it.entry = 13517

  - first aid (subclass = 7): vanilla goes up to 60/300 with crystal-infused bandages, which aren't available in game. TBC starts at 60/300, so a simple >=600 and >=300 skill should be fine.
  - enchanting (subclass = 8): vanilla recipes go up to ilvl 70, skill 300. TBC recipes start at ilvl 61 but all have skill >= 305. So skill >= 305 is enough.
  - fishing (subclass = 9): no vanilla recipes in the 55+ range. 1 TBC recipe (ilvl 55/skill 275) sold in Zangarmarsh, ID = 27532.
  - jewelcrafting (subclass = 10): no vanilla JC designs for obvious reasons. TBC added recipes at all level ranges, going as high as 2 x ilvl 60/300 recipes in UBRS/BRD. Outlands JC recipes also start at 60/300 and share same index range as old world. Best approach is just take >= ilvl 60/skill 300 and substract the 2 old world 60s, Design: Black Diamond Crab 21955 and Design: Dark Iron Scorpid 21956. ItemID 21957 is breakpoint:

SELECT it.entry, it.name, it.ItemLevel, it.RequiredSkillRank
FROM `item_template` it
WHERE it.class = 9 AND it.subclass = 10
AND it.ItemLevel >= 60 AND it.RequiredSkillRank >= 300 AND it.entry >= 21957

- class 10 is obsolete

- quivers (class = 11): vanilla quivers go up to ilvl 75 (Ancient Sinew Wrapped Lamina 18714) and 2 x ilvl 60s. TBC quivers start at ilvl 70, but have indices in the 29K range. So item ID breakpint works:

SELECT it.entry, it.name, it.ItemLevel, it.RequiredSkillRank
FROM `item_template` it
WHERE it.class = 11
AND it.ItemLevel >= 70 AND it.entry > 20000

- quest items (class = 12): vanilla quest items go to ilvl 80 (Thunderfury precursor). TBC quest items start as low as 58. 

- key (class = 13): irrelevant, all at the end of quest chains.

- class 14 is obsolete.

- miscellaneous (class = 15): vanilla has 102 60+ items, and 4 63+, including 1 70 - lots of loot tokens and mounts. TBC items start at 60. Also, AC DB has lots of misalocated items that are in wrong categories here.
  - junk (subclass = 0): vanilla ends at 65, but the item in question isn't in AC DB. TBC starts at 60, index breakpoint seems to be 24242. 
  - reagent (subclass = 1): 5 x ilvl 60 vanilla reagents, highest index id is 21177. TBC reagents start at 70 (only 3 as they were mosrtly phased out anyway.)
  - pet (subclass = 2): leaving this class alone as they are sold in the CC store.
  - holiday (subclass = 3): skipping.
  - other (subclass = 4): vanilla goes to 60, with 1 70 (Adamantite Arrow Maker 20475)

- glyphs (class = 16): 







