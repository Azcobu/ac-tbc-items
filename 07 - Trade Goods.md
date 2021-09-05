## Trade goods (class = 7)
  - ### Parts (subclass = 1)
    Itemlevel >=60 looks good - lowest vanilla is 58, arcanite converter.

    ```SQL
    SELECT it.entry  , it.name,it.ItemLevel, it.RequiredLevel
    FROM `item_template` it
    WHERE it.class = 7 AND it.subclass = 1
    AND it.ItemLevel >= 60
    ```

    <details>
    <summary>Results</summary>
  
    ---
    | entry | name | ItemLevel | RequiredLevel | 
    | ---: | --- | ---: | ---: | 
    | 23781 | Elemental Blasting Powder | 60 | 0 | 
    | 23782 | Fel Iron Casing | 60 | 0 | 
    | 23783 | Handful of Fel Iron Bolts | 60 | 0 | 
    | 23784 | Adamantite Frame | 65 | 0 | 
    | 23785 | Hardened Adamantite Tube | 70 | 0 | 
    | 23786 | Khorium Power Core | 70 | 0 | 
    | 23787 | Felsteel Stabilizer | 70 | 0 | 
    | 32423 | Icy Blasting Primers | 68 | 0 | 
    | 34467 | Test Handful of Fel Iron Bolts | 60 | 0 | 
    | 39681 | Handful of Cobalt Bolts | 71 | 0 | 
    | 39682 | Overcharged Capacitor | 70 | 0 | 
    | 39683 | Froststeel Tube | 70 | 0 | 
    | 39684 | Hair Trigger | 71 | 0 | 
    | 39685 | Indestructible Frame | 80 | 0 | 
    | 39686 | Neo-Dynamic Gear Assembly | 70 | 0 | 
    | 39690 | Volatile Blasting Trigger | 72 | 0 | 
    | 40533 | Walnut Stock | 80 | 0 | 
    | 41125 | zzOLD | 71 | 0 | 
    | 43124 | Ethereal Ink | 60 | 0 | 
    | 43125 | Darkflame Ink | 60 | 0 | 
    | 43126 | Ink of the Sea | 70 | 0 | 
    | 43127 | Snowfall Ink | 70 | 0 | 
    | 43614 | Broken Wrath Elixir | 80 | 0 | 
    | 43620 | Broken Spellpower Elixir | 80 | 0 | 
    | 43621 | Broken Noggenfogger Elixir | 80 | 0 | 
    | 44499 | Salvaged Iron Golem Parts | 80 | 0 | 
    | 44500 | Elementium-plated Exhaust Pipe | 80 | 0 | 
    | 44501 | Goblin-machined Piston | 80 | 0 | 

    </details>
    
    23781, 23782, 23783, 23784, 23785, 23786, 23787, 32423, 34467, 39681, 39682, 39683, 39684, 39685, 39686, 39690, 40533, 41125, 43124, 43125, 43126, 43127, 43614, 43620, 43621, 44499, 44500, 44501
    
    <hr>

  - ### Explosives (subclass = 2)
    1 level 60 vanilla bomb, 19831 arcane bomb. >= 60 is good otherwise though. Maybe just >= 61 and add the 1 TBC 60 item, which is 23736 fel iron bomb.

    ```SQL
    SELECT it.entry, it.name,it.ItemLevel, it.RequiredLevel
    FROM `item_template` it
    WHERE it.class = 7 AND it.subclass = 2
    AND it.ItemLevel >= 61
    ```

    <details>
    <summary>Results</summary>
  
    | entry | name | ItemLevel | RequiredLevel | 
    | ---: | --- | ---: | ---: | 
    | 23737 | Adamantite Grenade | 65 | 0 | 
    | 23819 | Elemental Seaforium Charge | 70 | 0 | 
    | 23826 | The Bigger One | 65 | 0 | 
    | 23827 | Super Sapper Charge | 68 | 0 | 
    | 23841 | Gnomish Flame Turret | 70 | 0 | 
    | 32413 | Frost Grenade | 65 | 0 | 
    | 39687 | Saronite Grenade | 75 | 0 | 
    | 40536 | Explosive Decoy | 80 | 0 | 
    | 40771 | Cobalt Frag Bomb | 71 | 0 | 
    | 41119 | Saronite Bomb | 75 | 0 | 
    | 41147 | Barrel o' Fun | 80 | 0 | 
    | 42641 | Global Thermal Sapper Charge | 75 | 0 | 
    | 43038 | The Naked Bomb | 75 | 0 | 
    | 44598 | Shrapnel Grenade | 75 | 0 | 
    | 44951 | Box of Bombs | 75 | 0 | 

    </details>
    
    23737, 23819, 23826, 23827, 23841, 32413, 39687, 40536, 40771, 41119, 41147, 42641, 43038, 44598, 44951, 23736

    <hr>
    
  - ### Devices (subclass = 3)
    Item level >= 60 gets all TBC devices except a lvl 55 toy, "battered steam tonk controller" 31666. Vanilla does have ilvl 60 devices (field repair bot 74a) but their indices are all < 20K.

    ```SQL
    SELECT it.entry, it.name,it.ItemLevel, it.RequiredLevel
    FROM `item_template` it
    WHERE it.class = 7 AND it.subclass = 3
    AND it.ItemLevel >= 60 AND it.entry > 20000
    ```

    <details>
    <summary>Results</summary>
  
    ---
    | entry | name | ItemLevel | RequiredLevel | 
    | ---: | --- | ---: | ---: | 
    | 23764 | Adamantite Scope | 67 | 55 | 
    | 23765 | Khorium Scope | 72 | 55 | 
    | 23766 | Stabilized Eternium Scope | 75 | 60 | 
    | 23767 | Crashin' Thrashin' Robot | 60 | 0 | 
    | 23820 | Critter Enlarger | 65 | 0 | 
    | 23821 | Zapthrottle Mote Extractor | 61 | 0 | 
    | 23831 | Goblin Tonk Controller | 65 | 0 | 
    | 23832 | Gnomish Tonk Controller | 65 | 0 | 
    | 23840 | Remote Mail Terminal | 67 | 0 | 
    | 34113 | Field Repair Bot 110G | 70 | 0 | 
    | 37567 | Healing Injector Kit | 80 | 0 | 
    | 37710 | Crashin' Thrashin' Racer Controller | 60 | 0 | 
    | 40768 | MOLL-E | 80 | 0 | 
    | 40769 | Scrapbot Construction Kit | 80 | 0 | 
    | 40772 | Gnomish Army Knife | 71 | 0 | 
    | 41146 | Sun Scope | 75 | 70 | 
    | 41167 | Heartseeker Scope | 80 | 70 | 
    | 41178 | ZX-5103 Mechanical Suit | 85 | 80 | 
    | 42546 | Mana Injector Kit | 80 | 0 | 
    | 44739 | Diamond-cut Refractor Scope | 75 | 70 | 
    | 47828 | Goblin Beam Welder | 80 | 0 | 
    | 49040 | Jeeves | 200 | 0 | 
    | 54343 | Blue Crashin' Thrashin' Racer Controller | 60 | 0 | 
  
    </details>
    
    23764, 23765, 23766, 23767, 23820, 23821, 23831, 23832, 23840, 34113, 37567, 37710, 40768, 40769, 40772, 41146, 41167, 41178, 42546, 44739, 47828, 49040, 54343, 31666

    <hr>
    
  - ### Jewelcrafting (subclass = 4)
    Item level >= 60 is fine - only 12 items affected, most of which are deprecated anyway. You'll see Cut Emerald/Cut Azerothian Diamond in here, but they're old items that were never implemented.

    ```SQL
    SELECT it.entry, it.name,it.ItemLevel, it.RequiredLevel
    FROM `item_template` it
    WHERE it.class = 7 AND it.subclass = 4
    AND it.ItemLevel >= 60
    ```

    <details>
    <summary>Results</summary>
  
    ---
    | entry | name | ItemLevel | RequiredLevel | 
    | ---: | --- | ---: | ---: | 
    | 21785 | Cut Emerald | 60 | 0 | 
    | 21786 | Cut Azerothian Diamond | 60 | 0 | 
    | 23364 | zzDEPRECATEDHeart of the Sky | 60 | 0 | 
    | 23366 | zzDEPRECATEDPerfect Diamond | 60 | 0 | 
    | 24243 | Adamantite Powder | 70 | 0 | 
    | 27774 | zzOLDMighty Blood Garnet | 60 | 0 | 
    | 27811 | zzOLDMighty Blood Garnet | 60 | 0 | 
    | 28117 | zzOLDBold Ornate Ruby | 60 | 0 | 
    | 28122 | zzOLDEnscribed Ornate Topaz | 60 | 0 | 
    | 28388 | TCHILTON TEST RUBY | 60 | 0 | 
    | 28389 | TCHILTON TEST DAWNSTONE | 60 | 0 | 
    | 31079 | Mercurial Adamantite | 60 | 0 | 

    </details>
    
    21785, 21786, 23364, 23366, 24243, 27774, 27811, 28117, 28122, 28388, 28389, 31079

    <hr>
    
  - ### Cloth (subclass = 5)
    Easy division, ilvl >= 60 captures 11 TBC items or 18 counting Wrath items too.

    ```SQL
    SELECT it.entry, it.name,it.ItemLevel, it.RequiredLevel
    FROM `item_template` it
    WHERE it.class = 7 AND it.subclass = 5
    AND it.ItemLevel >= 60
    ```
    
    <details>
    <summary>Results</summary>

    ---
    | entry | name | ItemLevel | RequiredLevel | 
    | ---: | --- | ---: | ---: | 
    | 21840 | Bolt of Netherweave | 60 | 0 | 
    | 21842 | Bolt of Imbued Netherweave | 66 | 0 | 
    | 21844 | Bolt of Soulcloth | 70 | 0 | 
    | 21845 | Primal Mooncloth | 70 | 0 | 
    | 21877 | Netherweave Cloth | 60 | 0 | 
    | 21881 | Netherweb Spider Silk | 60 | 0 | 
    | 23854 | Shadoweave Cloth | 70 | 0 | 
    | 23855 | Spellfire Cloth | 70 | 0 | 
    | 24271 | Spellcloth | 70 | 0 | 
    | 24272 | Shadowcloth | 70 | 0 | 
    | 33470 | Frostweave Cloth | 70 | 0 | 
    | 38426 | Eternium Thread | 70 | 0 | 
    | 41510 | Bolt of Frostweave | 70 | 0 | 
    | 41511 | Bolt of Imbued Frostweave | 75 | 0 | 
    | 41593 | Ebonweave | 80 | 0 | 
    | 41594 | Moonshroud | 80 | 0 | 
    | 41595 | Spellweave | 80 | 0 | 
    | 42253 | Iceweb Spider Silk | 75 | 0 | 


    </details>
    
    21840, 21842, 21844, 21845, 21877, 21881, 23854, 23855, 24271, 24272, 33470, 38426, 41510, 41511, 41593, 41594, 41595, 42253

    <hr>
    
  - ### Leather (subclass = 6)
    This one is really mixed - lots of TBC leather at 60, but lots of vanilla raid leather there too. highest vanilla index is dreamscale 20381. So ilvl >= 60 and entry > 20400 works.
    
    ```SQL
    SELECT it.entry , it.name,it.ItemLevel, it.RequiredLevel
    FROM `item_template` it
    WHERE it.class = 7 AND it.subclass = 6
    AND it.ItemLevel >= 60 AND it.entry > 20400
    ```

    <details>
    <summary>Results</summary>

    ---
    | entry | name | ItemLevel | RequiredLevel | 
    | ---: | --- | ---: | ---: | 
    | 21887 | Knothide Leather | 60 | 0 | 
    | 23793 | Heavy Knothide Leather | 65 | 0 | 
    | 25649 | Knothide Leather Scraps | 60 | 0 | 
    | 25699 | Crystal Infused Leather | 60 | 0 | 
    | 25700 | Fel Scales | 60 | 0 | 
    | 25707 | Fel Hide | 70 | 0 | 
    | 25708 | Thick Clefthoof Leather | 60 | 0 | 
    | 29539 | Cobra Scales | 60 | 0 | 
    | 29547 | Wind Scales | 60 | 0 | 
    | 29548 | Nether Dragonscales | 60 | 0 | 
    | 33567 | Borean Leather Scraps | 70 | 0 | 
    | 33568 | Borean Leather | 70 | 0 | 
    | 38425 | Heavy Borean Leather | 80 | 0 | 
    | 38557 | Icy Dragonscale | 75 | 0 | 
    | 38558 | Nerubian Chitin | 70 | 0 | 
    | 38561 | Jormungar Scale | 75 | 0 | 
    | 44128 | Arctic Fur | 75 | 0 | 
    | 49334 | Scale of Onyxia 2.0 | 80 | 0 | 

    </details>
    
    21887, 23793, 25649, 25699, 25700, 25707, 25708, 29539, 29547, 29548, 33567, 33568, 38425, 38557, 38558, 38561, 44128, 49334, 

    <hr>
    
  - ### Metal and Stone (subclass = 7)
    Vanilla metal/stone go all the way up to ilvl 60 - sulfuron/elementium ingots, etc, but all are <20K index.

    ```SQL
    SELECT it.entry  , it.name,it.ItemLevel, it.RequiredLevel
    FROM `item_template` it
    WHERE it.class = 7 AND it.subclass = 7
    AND it.ItemLevel >= 60 AND it.entry > 20000

    ```

    <details>
    <summary>Results</summary>

    ---
    | entry | name | ItemLevel | RequiredLevel | 
    | ---: | --- | ---: | ---: | 
    | 23424 | Fel Iron Ore | 60 | 0 | 
    | 23425 | Adamantite Ore | 65 | 0 | 
    | 23426 | Khorium Ore | 70 | 0 | 
    | 23427 | Eternium Ore | 70 | 0 | 
    | 23445 | Fel Iron Bar | 60 | 0 | 
    | 23446 | Adamantite Bar | 65 | 0 | 
    | 23447 | Eternium Bar | 70 | 0 | 
    | 23448 | Felsteel Bar | 60 | 0 | 
    | 23449 | Khorium Bar | 70 | 0 | 
    | 23573 | Hardened Adamantite Bar | 65 | 0 | 
    | 35128 | Hardened Khorium | 70 | 0 | 
    | 36909 | Cobalt Ore | 72 | 0 | 
    | 36910 | Titanium Ore | 80 | 0 | 
    | 36912 | Saronite Ore | 75 | 0 | 
    | 36913 | Saronite Bar | 80 | 0 | 
    | 36914 | Azurite Bar | 75 | 0 | 
    | 36915 | Froststeel Bar | 80 | 0 | 
    | 36916 | Cobalt Bar | 72 | 0 | 
    | 37663 | Titansteel Bar | 80 | 0 | 
    | 37706 | Hardened Saronite Bar | 80 | 0 | 
    | 41163 | Titanium Bar | 80 | 0 | 

    </details>
    
    23424, 23425, 23426, 23427, 23445, 23446, 23447, 23448, 23449, 23573, 35128, 36909, 36910, 36912, 36913, 36914, 36915, 36916, 37663, 37706, 41163

    <hr>
    
  - ### Meat (subclass = 8)
    item level >= 60 seems to be fine with 1 exception, 21024 Chimaerok Tenderloin 21024 in Feralas is 60.

    ```SQL
    SELECT it.entry  , it.name,it.ItemLevel, it.RequiredLevel
    FROM `item_template` it
    WHERE it.class = 7 AND it.subclass = 8
    AND it.ItemLevel >= 60 AND it.entry > 24000
    ```

    <details>
    <summary>Results</summary>
  
    ---
    | entry | name | ItemLevel | RequiredLevel | 
    | ---: | --- | ---: | ---: | 
    | 24477 | Jaggal Clam Meat | 65 | 0 | 
    | 27422 | Barbed Gill Trout | 60 | 0 | 
    | 27425 | Spotted Feltail | 60 | 0 | 
    | 27429 | Zangarian Sporefish | 60 | 0 | 
    | 27435 | Figluster's Mudfish | 60 | 0 | 
    | 27437 | Icefin Bluefish | 60 | 0 | 
    | 27438 | Golden Darter | 60 | 0 | 
    | 27439 | Furious Crawdad | 60 | 0 | 
    | 27515 | Huge Spotted Feltail | 60 | 0 | 
    | 27516 | Enormous Barbed Gill Trout | 60 | 0 | 
    | 27671 | Buzzard Meat | 60 | 0 | 
    | 27674 | Ravager Flesh | 60 | 0 | 
    | 27676 | Strange Spores | 60 | 0 | 
    | 27677 | Chunk o' Basilisk | 60 | 0 | 
    | 27678 | Clefthoof Meat | 60 | 0 | 
    | 27681 | Warped Flesh | 60 | 0 | 
    | 27682 | Talbuk Venison | 60 | 0 | 
    | 31670 | Raptor Ribs | 60 | 0 | 
    | 31671 | Serpent Flesh | 60 | 0 | 
    | 33823 | Bloodfin Catfish | 65 | 0 | 
    | 33824 | Crescent-Tail Skullfish | 65 | 0 | 
    | 34735 | Northrend Meat 01 | 70 | 0 | 
    | 34736 | Chunk o' Mammoth | 70 | 0 | 
    | 34737 | Northrend Meat 03 | 70 | 0 | 
    | 34738 | Northrend Meat 04 | 70 | 0 | 
    | 34739 | Northrend Meat 05 | 70 | 0 | 
    | 34740 | Northrend Meat 06 | 70 | 0 | 
    | 34741 | Northrend Meat 07 | 70 | 0 | 
    | 34742 | Northrend Meat 08 | 70 | 0 | 
    | 34743 | Northrend Meat 09 | 70 | 0 | 
    | 34744 | Northrend Meat 10 | 70 | 0 | 
    | 34745 | Northrend Meat 11 | 70 | 0 | 
    | 34746 | Northrend Meat 12 | 70 | 0 | 
    | 35285 | Giant Sunfish | 70 | 55 | 
    | 35794 | Silvercoat Stag Meat | 75 | 65 | 
    | 36782 | Succulent Clam Meat | 75 | 0 | 
    | 38270 | Slab of Blubber | 75 | 0 | 
    | 38271 | Lean Flank | 75 | 0 | 
    | 38272 | Bloody Giblets | 75 | 0 | 
    | 38625 | Northern Icelip | 72 | 0 | 
    | 39526 | Coral Crusher | 72 | 0 | 
    | 39527 | Plated Darkfish | 72 | 0 | 
    | 41800 | Deep Sea Monsterbelly | 70 | 0 | 
    | 41801 | Moonglow Cuttlefish | 70 | 0 | 
    | 41802 | Imperial Manta Ray | 70 | 0 | 
    | 41803 | Rockfin Grouper | 70 | 0 | 
    | 41804 | Icemouth Waveskipper | 70 | 0 | 
    | 41805 | Borean Man O' War | 70 | 0 | 
    | 41806 | Musselback Sculpin | 70 | 0 | 
    | 41807 | Dragonfin Angelfish | 70 | 0 | 
    | 41808 | Bonescale Snapper | 70 | 0 | 
    | 41809 | Glacial Salmon | 70 | 0 | 
    | 41810 | Fangtooth Herring | 70 | 0 | 
    | 41811 | Meltwater Beardfish | 70 | 0 | 
    | 41812 | Barrelhead Goby | 70 | 0 | 
    | 41813 | Nettlefish | 70 | 0 | 
    | 41814 | Glassfin Minnow | 70 | 0 | 
    | 43009 | Shoveltusk Flank | 70 | 0 | 
    | 43010 | Worm Meat | 70 | 0 | 
    | 43011 | Worg Haunch | 70 | 0 | 
    | 43012 | Rhino Meat | 70 | 0 | 
    | 43013 | Chilled Meat | 70 | 0 | 
    | 43501 | Northern Egg | 70 | 0 | 
    | 43571 | Sewer Carp | 80 | 70 | 
    | 43572 | Magic Eater | 80 | 70 | 
    | 43646 | Fountain Goldfish | 75 | 65 | 
    | 43647 | Shimmering Minnow | 80 | 70 | 
    | 43652 | Slippery Eel | 80 | 70 | 

    </details>
    
    24477, 27422, 27425, 27429, 27435, 27437, 27438, 27439, 27515, 27516, 27671, 27674, 27676, 27677, 27678, 27681, 27682, 31670, 31671, 33823, 33824, 34735, 34736, 34737, 34738, 34739, 34740, 34741, 34742, 34743, 34744, 34745, 34746, 35285, 35794, 36782, 38270, 38271, 38272, 38625, 39526, 39527, 41800, 41801, 41802, 41803, 41804, 41805, 41806, 41807, 41808, 41809, 41810, 41811, 41812, 41813, 41814, 43009, 43010, 43011, 43012, 43013, 43501, 43571, 43572, 43646, 43647, 43652, 

    <hr>
    
  - ### Herbs (subclass = 9)
    There are 2 ilvl 60 classic herbs, Black Lotus and Bloodvine, and Blood Scythe (a tool rather than a herb for some reason), all below 20K index.

    ```SQL
    SELECT it.entry , it.name,it.ItemLevel, it.RequiredLevel
    FROM `item_template` it
    WHERE it.class = 7 AND it.subclass = 9
    AND it.ItemLevel >= 60 AND it.entry > 20000
    ```

    <details>
    <summary>Results</summary>

    ---
    | entry | name | ItemLevel | RequiredLevel | 
    | ---: | --- | ---: | ---: | 
    | 22785 | Felweed | 60 | 0 | 
    | 22786 | Dreaming Glory | 60 | 0 | 
    | 22787 | Ragveil | 65 | 0 | 
    | 22788 | Flame Cap | 67 | 55 | 
    | 22789 | Terocone | 60 | 0 | 
    | 22790 | Ancient Lichen | 68 | 0 | 
    | 22791 | Netherbloom | 70 | 0 | 
    | 22792 | Nightmare Vine | 70 | 0 | 
    | 22793 | Mana Thistle | 70 | 0 | 
    | 22794 | Fel Lotus | 70 | 0 | 
    | 22797 | Nightmare Seed | 70 | 60 | 
    | 36901 | Goldclover | 72 | 0 | 
    | 36902 | Constrictor Grass | 75 | 0 | 
    | 36903 | Adder's Tongue | 77 | 0 | 
    | 36904 | Tiger Lily | 72 | 0 | 
    | 36905 | Lichbloom | 80 | 0 | 
    | 36906 | Icethorn | 80 | 0 | 
    | 36907 | Talandra's Rose | 72 | 0 | 
    | 36908 | Frost Lotus | 80 | 0 | 
    | 37921 | Deadnettle | 72 | 0 | 

    </details>
    
    22785, 22786, 22787, 22788, 22789, 22790, 22791, 22792, 22793, 22794, 22797, 36901, 36902, 36903, 36904, 36905, 36906, 36907, 36908, 37921

    <hr>
    
  - ### Elemental (subclass = 10)
    Item level>= 60 is fne, nice clear divide for once.

    ```SQL
    SELECT it.entry , it.name,it.ItemLevel, it.RequiredLevel
    FROM `item_template` it
    WHERE it.class = 7 AND it.subclass = 10
    AND it.ItemLevel >= 60
    ```

    <details>
    <summary>Results</summary>
  
    ---
    | entry | name | ItemLevel | RequiredLevel | 
    | ---: | --- | ---: | ---: | 
    | 21884 | Primal Fire | 65 | 0 | 
    | 21885 | Primal Water | 65 | 0 | 
    | 21886 | Primal Life | 65 | 0 | 
    | 22451 | Primal Air | 65 | 0 | 
    | 22452 | Primal Earth | 65 | 0 | 
    | 22456 | Primal Shadow | 65 | 0 | 
    | 22457 | Primal Mana | 65 | 0 | 
    | 22572 | Mote of Air | 65 | 0 | 
    | 22573 | Mote of Earth | 65 | 0 | 
    | 22574 | Mote of Fire | 65 | 0 | 
    | 22575 | Mote of Life | 65 | 0 | 
    | 22576 | Mote of Mana | 65 | 0 | 
    | 22577 | Mote of Shadow | 65 | 0 | 
    | 22578 | Mote of Water | 65 | 0 | 
    | 23571 | Primal Might | 65 | 0 | 
    | 34055 | Greater Cosmic Essence | 75 | 0 | 
    | 35622 | Eternal Water | 75 | 0 | 
    | 35623 | Eternal Air | 75 | 0 | 
    | 35624 | Eternal Earth | 75 | 0 | 
    | 35625 | Eternal Life | 75 | 0 | 
    | 35626 | Eternal Mana [PH] | 75 | 0 | 
    | 35627 | Eternal Shadow | 75 | 0 | 
    | 36860 | Eternal Fire | 75 | 0 | 
    | 37700 | Crystallized Air | 75 | 0 | 
    | 37701 | Crystallized Earth | 75 | 0 | 
    | 37702 | Crystallized Fire | 75 | 0 | 
    | 37703 | Crystallized Shadow | 75 | 0 | 
    | 37704 | Crystallized Life | 75 | 0 | 
    | 37705 | Crystallized Water | 75 | 0 | 
    | 40248 | Eternal Might | 80 | 0 | 

    </details>
    
      21884, 21885, 21886, 22451, 22452, 22456, 22457, 22572, 22573, 22574, 22575, 22576, 22577, 22578, 23571, 34055, 35622, 35623, 35624, 35625, 35626, 35627, 36860, 37700, 37701, 37702, 37703, 37704, 37705, 40248

    <hr>
    
  - ### Other (subclass = 11)
    Lots of overlap at 60, even with indices. Vanilla goes up to ilvl 80 with Frozen Rune 22682. >=61 is otherwise fine, but needs to add soul essence 21882, inscribed scrollcase 27511, curious crate 27513, Charged Draenethyst Crystal 21879 which are all 60.
    
    Also note Alchemist's Stone 13503, which was added in vanilla as you can tell by the low index, but is a TBC item, taught in Shattrath and requiring 350 alchemy. Counting this as a TBC item accordingly.

    ```SQL
    SELECT it.entry , it.name,it.ItemLevel, it.RequiredLevel
    FROM `item_template` it
    WHERE it.class = 7 AND it.subclass = 11
    AND it.ItemLevel >= 61
    ```

    <details>
    <summary>Results</summary>

    ---
    | entry | name | ItemLevel | RequiredLevel | 
    | ---: | --- | ---: | ---: | 
    | 13503 | Alchemist's Stone | 90 | 0 | 
    | 24288 | Rune Thread | 70 | 0 | 
    | 24476 | Jaggal Clam | 65 | 0 | 
    | 32428 | Heart of Darkness | 65 | 0 | 
    | 34664 | Sunmote | 70 | 0 | 
    | 35748 | Guardian's Alchemist Stone | 125 | 0 | 
    | 35749 | Sorcerer's Alchemist Stone | 125 | 0 | 
    | 35750 | Redeemer's Alchemist Stone | 125 | 0 | 
    | 35751 | Assassin's Alchemist Stone | 125 | 0 | 
    | 36781 | Darkwater Clam | 75 | 0 | 
    | 39343 | Azure Pigment | 70 | 0 | 
    | 39502 | Resilient Parchment | 80 | 0 | 
    | 40195 | Pygmy Oil | 75 | 0 | 
    | 40199 | Pygmy Suckerfish | 75 | 0 | 
    | 40411 | Enchanted Vial | 75 | 0 | 
    | 42170 | Silver Brooch | 70 | 0 | 
    | 42171 | Emerald Brooch | 80 | 0 | 
    | 42953 | Strange Envelope | 80 | 70 | 
    | 43007 | Northern Spices | 80 | 0 | 
    | 43102 | Frozen Orb | 80 | 0 | 
    | 43108 | Ebon Pigment | 70 | 0 | 
    | 43109 | Icy Pigment | 80 | 0 | 
    | 43562 | Nightmare Berries | 70 | 0 | 
    | 43563 | Frozen Beetle Husk | 80 | 0 | 
    | 44317 | Greater Darkmoon Card | 70 | 0 | 
    | 44318 | Darkmoon Card of the North | 80 | 0 | 
    | 44322 | Mercurial Alchemist Stone | 200 | 75 | 
    | 44323 | Indestructible Alchemist's Stone | 200 | 75 | 
    | 44324 | Mighty Alchemist's Stone | 200 | 75 | 
    | 44475 | Reinforced Crate | 70 | 0 | 
    | 44700 | Brooding Darkwater Clam | 75 | 0 | 
    | 44958 | Ethereal Oil | 75 | 0 | 
    | 45087 | Runed Orb | 80 | 0 | 
    | 45909 | Giant Darkwater Clam | 80 | 0 | 
    | 47556 | Crusader Orb | 80 | 0 | 
    | 49908 | Primordial Saronite | 80 | 0 | 

    </details>
    
    Note: manually removed 22682, added 21882, 27511, 27513, 21879
    
    13503, 24288, 24476, 32428, 34664, 35748, 35749, 35750, 35751, 36781, 39343, 39502, 40195, 40199, 40411, 42170, 42171, 42953, 43007, 43102, 43108, 43109, 43562, 43563, 44317, 44318, 44322, 44323, 44324, 44475, 44700, 44958, 45087, 45909, 47556, 49908, 21882, 27511, 27513, 21879

    <hr>
    
  - ## Enchanting (subclass = 12)
    Item level >= 60 is fine except for 1 overlap, nexus crystals 20725.

    ```SQL
    SELECT it.entry  , it.name,it.ItemLevel, it.RequiredLevel
    FROM `item_template` it
    WHERE it.class = 7 AND it.subclass = 12
    AND it.ItemLevel >= 60 AND it.entry > 21000
    ```

    <details>
    <summary>Results</summary>
  
    ---
    | entry | name | ItemLevel | RequiredLevel | 
    | ---: | --- | ---: | ---: | 
    | 22445 | Arcane Dust | 60 | 0 | 
    | 22446 | Greater Planar Essence | 65 | 0 | 
    | 22447 | Lesser Planar Essence | 60 | 0 | 
    | 22448 | Small Prismatic Shard | 65 | 0 | 
    | 22449 | Large Prismatic Shard | 70 | 0 | 
    | 22450 | Void Crystal | 70 | 0 | 
    | 22461 | Runed Fel Iron Rod | 61 | 0 | 
    | 22462 | Runed Adamantite Rod | 61 | 0 | 
    | 22463 | Runed Eternium Rod | 61 | 0 | 
    | 25843 | Fel Iron Rod | 60 | 0 | 
    | 25844 | Adamantite Rod | 70 | 0 | 
    | 25845 | Eternium Rod | 75 | 0 | 
    | 34052 | Dream Shard | 80 | 0 | 
    | 34053 | Small Dream Shard | 80 | 0 | 
    | 34054 | Infinite Dust | 70 | 0 | 
    | 34056 | Lesser Cosmic Essence | 70 | 0 | 
    | 34057 | Abyss Crystal | 80 | 0 | 
    | 41741 | Cobalt Rod | 70 | 0 | 
    | 41745 | Titanium Rod | 70 | 0 | 
    | 44451 | Runed Cobalt Rod | 71 | 0 | 
    | 44452 | Runed Titanium Rod | 81 | 0 | 
    | 46849 | Titanium Powder | 80 | 0 | 
    | 49640 | Essence or Dust | 80 | 0 | 
  
    </details>
    
    22445, 22446, 22447, 22448, 22449, 22450, 22461, 22462, 22463, 25843, 25844, 25845, 34052, 34053, 34054, 34056, 34057, 41741, 41745, 44451, 44452, 46849, 49640

    <hr>
    
  - ### Materials (subclass = 13)
    Only 2 Primal Nether 23572 and Nether Vortex 30183.

    ```SQL
    SELECT it.entry  , it.name,it.ItemLevel, it.RequiredLevel
    FROM `item_template` it
    WHERE it.class = 7 AND it.subclass = 13
    ```
   
    <details>
    <summary>Results</summary>
  
    ---
    | entry | name | ItemLevel | RequiredLevel | 
    | ---: | --- | ---: | ---: | 
    | 23572 | Primal Nether | 65 | 0 | 
    | 30183 | Nether Vortex | 75 | 0 | 
    | 37103 | NPC Equip 37103 | 0 | 0 | 

    </details>
    
    23572, 30183

    <hr>
    
  - ### Armour Enchants (subclass = 14)
    Empty set, armour vellums which were deprecated and thus unobtainable in game.

  - ### Weapon Eenchants (subclass = 15)
    As above.

## Concatenated Trade Goods:

23781, 23782, 23783, 23784, 23785, 23786, 23787, 32423, 34467, 39681, 39682, 39683, 39684, 39685, 39686, 39690, 40533, 41125, 43124, 43125, 43126, 43127, 43614, 43620, 43621, 44499, 44500, 44501, 23737, 23819, 23826, 23827, 23841, 32413, 39687, 40536, 40771, 41119, 41147, 42641, 43038, 44598, 44951, 23736, 23764, 23765, 23766, 23767, 23820, 23821, 23831, 23832, 23840, 34113, 37567, 37710, 40768, 40769, 40772, 41146, 41167, 41178, 42546, 44739, 47828, 49040, 54343, 31666, 21785, 21786, 23364, 23366, 24243, 27774, 27811, 28117, 28122, 28388, 28389, 31079, 21840, 21842, 21844, 21845, 21877, 21881, 23854, 23855, 24271, 24272, 33470, 38426, 41510, 41511, 41593, 41594, 41595, 42253, 21887, 23793, 25649, 25699, 25700, 25707, 25708, 29539, 29547, 29548, 33567, 33568, 38425, 38557, 38558, 38561, 44128, 49334, 23424, 23425, 23426, 23427, 23445, 23446, 23447, 23448, 23449, 23573, 35128, 36909, 36910, 36912, 36913, 36914, 36915, 36916, 37663, 37706, 41163, 24477, 27422, 27425, 27429, 27435, 27437, 27438, 27439, 27515, 27516, 27671, 27674, 27676, 27677, 27678, 27681, 27682, 31670, 31671, 33823, 33824, 34735, 34736, 34737, 34738, 34739, 34740, 34741, 34742, 34743, 34744, 34745, 34746, 35285, 35794, 36782, 38270, 38271, 38272, 38625, 39526, 39527, 41800, 41801, 41802, 41803, 41804, 41805, 41806, 41807, 41808, 41809, 41810, 41811, 41812, 41813, 41814, 43009, 43010, 43011, 43012, 43013, 43501, 43571, 43572, 43646, 43647, 43652, 22785, 22786, 22787, 22788, 22789, 22790, 22791, 22792, 22793, 22794, 22797, 36901, 36902, 36903, 36904, 36905, 36906, 36907, 36908, 37921, 21884, 21885, 21886, 22451, 22452, 22456, 22457, 22572, 22573, 22574, 22575, 22576, 22577, 22578, 23571, 34055, 35622, 35623, 35624, 35625, 35626, 35627, 36860, 37700, 37701, 37702, 37703, 37704, 37705, 40248, 13503, 24288, 24476, 32428, 34664, 35748, 35749, 35750, 35751, 36781, 39343, 39502, 40195, 40199, 40411, 42170, 42171, 42953, 43007, 43102, 43108, 43109, 43562, 43563, 44317, 44318, 44322, 44323, 44324, 44475, 44700, 44958, 45087, 45909, 47556, 49908, 21882, 27511, 27513, 21879, 22445, 22446, 22447, 22448, 22449, 22450, 22461, 22462, 22463, 25843, 25844, 25845, 34052, 34053, 34054, 34056, 34057, 41741, 41745, 44451, 44452, 46849, 49640, 23572, 30183
