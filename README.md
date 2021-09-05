# ac-tbc-items
Listing all prematurely available TBC/WotLK items

##Consumeables (Class = 0)
- ###consumable (subclass = 0) - there are lots of ilvl 60 classic items, and lots more TBC items that have no ilvl. Highest ID for classic 65 items is 23796 for perm. swift. of sheen. However, some overlap - fel blossoms are ilvl 65 with item id 22795. only 3 vanilla items > 60 though, and they may not even be in game. So cutoff >= 61 + manually adding 58-60 TBC items works. list of TBC items 55-60: stouthammer lite 23585, grunt's waterskin 24006, footman's waterskin 24007, brewfest items: should skip (stout shrunken head 34022, Pickled Sausage 33024, Thunderbrew Stout 33033), DMF sells Iced Berry Slush 33234 - mark of honor hold 24579, mark of thrallmar 24581, honor hold favor 24520, thrallmar favor 24522, chronoboon displacer 184937, primal stone statue 25884, supercharged chronoboon displacer 184938, + 4 bombs that are quest items so not really useful anyway.

So query becomes:
``SQL
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

Plus (23585, 24006, 24007, 24579, 24581, 24520, 24522, 184937, 25884, 184938)

Results: 

 - potion (subclass = 1): >= 60 is fine except for 3 classic items - Flask of Petrification, major rejuv potion, greater dreamless sleep potion.
  - elixir (subclass = 2): there are 3 ilvl 65 elixirs in Z'G - swiftness/spirit/sheen of zanza. >= 60 works fine as long as these 3 are removed
  - flask (subclass = 3): 4 ilvl 60 classic flasks - distilled wisdom, supreme power, chromatic resistance, titans - highest item id is 13513.
  - scroll (subclass = 4): classic scrolls go up to ilvl 65, agility/strength IV. highest item id is 10310. >= 70 works though, lv V scrolls from TBC start there.
  - food & drink (subclass = 5): tons of TBC food added across all level ranges. Meanwhile classic food goes up to ilvl 65 and has required player lvl of 55..  highest classic item id 22895.  The TBC lvl 65 food all seemed comfortably higher than this id.
  - item enhancement (subclass = 6): 
    -  TEMPORARY - only vanilla items at 60 are elemental sharpening stone 18262 and 2 rogue poisons, instant poison VI  and Deadly Poison V id 20844. There are 3 TBC items at 60, lowest id is fel sharpening stone id 23528.
    - PERMANENT: lots of ilvl 60 vanilla enhances, but none higher, and only 1 ilvl 60 TBC item, knothide armor kit 25650
    - summation: >= 61 plus knothide armor kit, fel sharpening stone, comfortable insoles, fel weightstone
  - bandages (subclass = 7): 1 vanilla 60 item, crystal infused bandage, probably not obtainable. >= 64 catches all TBC.
  - other (subclass = 8): highest vanilla is 58, lowest TBC is 60, so >= 60 works fine here.

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







