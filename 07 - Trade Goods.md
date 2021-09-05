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
    
  - metal and stone (subclass = 7) - CANNOT use >=60 as breakpoint, there are vanilla metal/stone drops that are ilvl 60 -  query needs to be >= 61 + felsteel bar, fel iron bar, fel iron ore

    ```SQL

    ```

    <details>
    <summary>Results</summary>


    </details>

    <hr>
    
  - meat (subclass = 8): >= 60 seems to be fine with 1 exception, 21024 Chimaerok Tenderloin in Feralas is 60

    ```SQL

    ```

    <details>
    <summary>Results</summary>


    </details>

    <hr>
    
  - herbs (subclass = 9): there are 2 ilvl 60 classic herbs, black lotus and bloodvine, and blood scythe (a tool) . >= 61 is fine + 22789 terocone, 22786 dreaming glory, 22785 felweed

    ```SQL

    ```

    <details>
    <summary>Results</summary>


    </details>

    <hr>
    
  - elemental (subclass = 10): >= 60 is fne, nice clear divide for once

    ```SQL

    ```

    <details>
    <summary>Results</summary>


    </details>

    <hr>
    
  - other (subclass = 11): lots of overlap. >=61 is fine, but needs to add soul essence, inscribed scrollcase, curious crate, Charged Draenethyst Crystal which are all 60

    ```SQL

    ```

    <details>
    <summary>Results</summary>


    </details>

    <hr>
    
    
  - enchanting (subclass = 12): >= 60 is fine except for 1 overlap, 20725 nexus crystals

    ```SQL

    ```

    <details>
    <summary>Results</summary>


    </details>

    <hr>
    
    
  - materials (subclass = 13): only 1, 23572 primal nether

    ```SQL

    ```

    <details>
    <summary>Results</summary>


    </details>

    <hr>
    
    
  - armour enchant (subclass = 14): empty set, armour vellums

    ```SQL

    ```

    <details>
    <summary>Results</summary>


    </details>

    <hr>
    
    
  - weapon enchantments (subclass = 15): ditto

    ```SQL

    ```

    <details>
    <summary>Results</summary>


    </details>

    <hr>
