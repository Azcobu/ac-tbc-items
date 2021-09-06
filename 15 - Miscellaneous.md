

## Miscellaneous (class = 15)
	Vanilla has 102 60+ items, and 4 63+, including 1 70 - lots of loot tokens and mounts. TBC items start at 60. Also, AC DB has lots of misallocated items that are in wrong categories here.
	
  - Junk (subclass = 0)
	Vanilla ends at 65, but the item in question (stormwind medallion) isn't in the AC DB. TBC starts at 60, index breakpoint seems to be 24242. Also note all the TBC/WotLK raid reward tokens are in this category.
	
	```SQL
	SELECT it.entry, it.name, it.ItemLevel, it.RequiredSkillRank 
	FROM item_template it 
	WHERE it.class = 15 AND it.subclass = 0
	AND it.ItemLevel >= 60 AND it.entry >= 24242

	```

	<details>
	<summary>Results</summary>

	---
	| entry | name | ItemLevel | RequiredSkillRank | 
	| ---: | --- | ---: | ---: | 
	| 24242 | Fel Iron Powder | 60 | 0 | 
	| 24504 | Howling Wind | 65 | 0 | 
	| 24558 | Murkblood Invasion Plans | 67 | 0 | 
	| 24559 | Murkblood Invasion Plans | 67 | 0 | 
	| 25596 | Peep's Whistle | 70 | 0 | 
	| 25641 | Broken Fitz's Throwing Axe | 103 | 0 | 
	| 26042 | Oshu'gun Crystal Powder Sample | 65 | 0 | 
	| 26043 | Oshu'gun Crystal Powder Sample | 65 | 0 | 
	| 27441 | Felblood Snapper | 60 | 0 | 
	| 27442 | Goldenscale Vendorfish | 70 | 0 | 
	| 27443 | Steam Pump Debris | 70 | 0 | 
	| 27446 | Mr. Pinchy's Gift | 70 | 0 | 
	| 28499 | Arakkoa Hunter's Supplies | 65 | 0 | 
	| 29569 | Strong Junkbox | 60 | 0 | 
	| 29753 | Chestguard of the Fallen Defender | 70 | 0 | 
	| 29754 | Chestguard of the Fallen Champion | 70 | 0 | 
	| 29755 | Chestguard of the Fallen Hero | 70 | 0 | 
	| 29756 | Gloves of the Fallen Hero | 70 | 0 | 
	| 29757 | Gloves of the Fallen Champion | 70 | 0 | 
	| 29758 | Gloves of the Fallen Defender | 70 | 0 | 
	| 29759 | Helm of the Fallen Hero | 70 | 0 | 
	| 29760 | Helm of the Fallen Champion | 70 | 0 | 
	| 29761 | Helm of the Fallen Defender | 70 | 0 | 
	| 29762 | Pauldrons of the Fallen Hero | 70 | 0 | 
	| 29763 | Pauldrons of the Fallen Champion | 70 | 0 | 
	| 29764 | Pauldrons of the Fallen Defender | 70 | 0 | 
	| 29765 | Leggings of the Fallen Hero | 70 | 0 | 
	| 29766 | Leggings of the Fallen Champion | 70 | 0 | 
	| 29767 | Leggings of the Fallen Defender | 70 | 0 | 
	| 30236 | Chestguard of the Vanquished Champion | 70 | 0 | 
	| 30237 | Chestguard of the Vanquished Defender | 70 | 0 | 
	| 30238 | Chestguard of the Vanquished Hero | 70 | 0 | 
	| 30239 | Gloves of the Vanquished Champion | 70 | 0 | 
	| 30240 | Gloves of the Vanquished Defender | 70 | 0 | 
	| 30241 | Gloves of the Vanquished Hero | 70 | 0 | 
	| 30242 | Helm of the Vanquished Champion | 70 | 0 | 
	| 30243 | Helm of the Vanquished Defender | 70 | 0 | 
	| 30244 | Helm of the Vanquished Hero | 70 | 0 | 
	| 30245 | Leggings of the Vanquished Champion | 70 | 0 | 
	| 30246 | Leggings of the Vanquished Defender | 70 | 0 | 
	| 30247 | Leggings of the Vanquished Hero | 70 | 0 | 
	| 30248 | Pauldrons of the Vanquished Champion | 70 | 0 | 
	| 30249 | Pauldrons of the Vanquished Defender | 70 | 0 | 
	| 30250 | Pauldrons of the Vanquished Hero | 70 | 0 | 
	| 30320 | Bundle of Nether Spikes | 175 | 0 | 
	| 30427 | Naga Treasure Map - Questgiver (PH) | 70 | 0 | 
	| 31089 | Chestguard of the Forgotten Conqueror | 70 | 0 | 
	| 31090 | Chestguard of the Forgotten Vanquisher | 70 | 0 | 
	| 31091 | Chestguard of the Forgotten Protector | 70 | 0 | 
	| 31092 | Gloves of the Forgotten Conqueror | 70 | 0 | 
	| 31093 | Gloves of the Forgotten Vanquisher | 70 | 0 | 
	| 31094 | Gloves of the Forgotten Protector | 70 | 0 | 
	| 31095 | Helm of the Forgotten Protector | 70 | 0 | 
	| 31096 | Helm of the Forgotten Vanquisher | 70 | 0 | 
	| 31097 | Helm of the Forgotten Conqueror | 70 | 0 | 
	| 31098 | Leggings of the Forgotten Conqueror | 70 | 0 | 
	| 31099 | Leggings of the Forgotten Vanquisher | 70 | 0 | 
	| 31100 | Leggings of the Forgotten Protector | 70 | 0 | 
	| 31101 | Pauldrons of the Forgotten Conqueror | 70 | 0 | 
	| 31102 | Pauldrons of the Forgotten Vanquisher | 70 | 0 | 
	| 31103 | Pauldrons of the Forgotten Protector | 70 | 0 | 
	| 31760 | Miniwing | 96 | 0 | 
	| 31800 | Outcast's Cache | 65 | 0 | 
	| 31952 | Khorium Lockbox | 68 | 0 | 
	| 32385 | Magtheridon's Head | 70 | 0 | 
	| 32386 | Magtheridon's Head | 70 | 0 | 
	| 32405 | Verdant Sphere | 70 | 0 | 
	| 32506 | Netherwing Egg | 70 | 0 | 
	| 32543 | Tier 5 Druid Test Gear | 70 | 0 | 
	| 32544 | Tier 5 Druid Test Gear Box 2 | 70 | 0 | 
	| 32545 | Tier 5 Hunter Test Gear | 70 | 0 | 
	| 32546 | Tier 5 Hunter Test Gear Box 2 | 70 | 0 | 
	| 32547 | Tier 5 Mage Test Gear | 70 | 0 | 
	| 32548 | Tier 5 Mage Test Gear Box 2 | 70 | 0 | 
	| 32549 | Tier 5 Paladin Test Gear | 70 | 0 | 
	| 32550 | Tier 5 Paladin Test Gear Box 2 | 70 | 0 | 
	| 32551 | Tier 5 Priest Test Gear | 70 | 0 | 
	| 32552 | Tier 5 Priest Test Gear Box 2 | 70 | 0 | 
	| 32553 | Tier 5 Rogue Test Gear | 70 | 0 | 
	| 32554 | Tier 5 Rogue Test Gear Box 2 | 70 | 0 | 
	| 32555 | Tier 5 Shaman Test Gear | 70 | 0 | 
	| 32556 | Tier 5 Shaman Test Gear Box 2 | 70 | 0 | 
	| 32557 | Tier 5 Warlock Test Gear | 70 | 0 | 
	| 32558 | Tier 5 Warlock Test Gear Box 2 | 70 | 0 | 
	| 32559 | Tier 5 Warrior Test Gear | 70 | 0 | 
	| 32560 | Tier 5 Warrior Test Gear Box 2 | 70 | 0 | 
	| 32561 | Tier 5 Arrow Box | 70 | 0 | 
	| 32595 | Ogrela Reagent Dust | 70 | 0 | 
	| 32670 | Depleted Two-Handed Axe | 115 | 0 | 
	| 32671 | Depleted Mace | 115 | 0 | 
	| 32672 | Depleted Badge | 115 | 0 | 
	| 32673 | Depleted Dagger | 115 | 0 | 
	| 32674 | Depleted Sword | 115 | 0 | 
	| 32675 | Depleted Mail Gauntlets | 105 | 0 | 
	| 32676 | Depleted Cloth Bracers | 105 | 0 | 
	| 32677 | Depleted Cloak | 115 | 0 | 
	| 32678 | Depleted Ring | 115 | 0 | 
	| 32679 | Depleted Staff | 115 | 0 | 
	| 32725 | Murkblood Miner's Pick | 70 | 0 | 
	| 32727 | Vial of Tears | 70 | 0 | 
	| 32728 | Sludge | 70 | 0 | 
	| 32835 | Ogri'la Care Package | 70 | 0 | 
	| 32895 | Scroll of the Maelstrom | 70 | 0 | 
	| 32896 | Scroll of the Sun | 70 | 0 | 
	| 33147 | Formula: Enchant Cloak - Subtlety | 70 | 0 | 
	| 33844 | Barrel of Fish | 65 | 0 | 
	| 34025 | Clayton's Test Item | 116 | 0 | 
	| 34544 | Essence of the Immortals | 70 | 0 | 
	| 34548 | Cache of the Shattered Sun | 70 | 0 | 
	| 34822 | Ancient Coin | 70 | 0 | 
	| 34823 | Beautiful Glass Eye | 70 | 0 | 
	| 34824 | Silver Statuette | 70 | 0 | 
	| 34825 | Mithril Shaving Razor | 70 | 0 | 
	| 34848 | Bracers of the Forgotten Conqueror | 70 | 0 | 
	| 34851 | Bracers of the Forgotten Protector | 70 | 0 | 
	| 34852 | Bracers of the Forgotten Vanquisher | 70 | 0 | 
	| 34853 | Belt of the Forgotten Conqueror | 70 | 0 | 
	| 34854 | Belt of the Forgotten Protector | 70 | 0 | 
	| 34855 | Belt of the Forgotten Vanquisher | 70 | 0 | 
	| 34856 | Boots of the Forgotten Conqueror | 70 | 0 | 
	| 34857 | Boots of the Forgotten Protector | 70 | 0 | 
	| 34858 | Boots of the Forgotten Vanquisher | 70 | 0 | 
	| 34863 | Bag of Fishing Treasures | 70 | 0 | 
	| 35314 | Partially Digested Weeds | 60 | 0 | 
	| 35348 | Bag of Fishing Treasures | 70 | 0 | 
	| 37126 | Clayton's Test Item Three | 115 | 0 | 
	| 37839 | Abomination Stitching | 80 | 0 | 
	| 38348 | Damaged Eye | 70 | 0 | 
	| 38581 | Adventurer's Skull | 80 | 0 | 
	| 40392 | Cracked Diamond | 60 | 0 | 
	| 40610 | Chestguard of the Lost Conqueror | 80 | 0 | 
	| 40611 | Chestguard of the Lost Protector | 80 | 0 | 
	| 40612 | Chestguard of the Lost Vanquisher | 80 | 0 | 
	| 40613 | Gloves of the Lost Conqueror | 80 | 0 | 
	| 40614 | Gloves of the Lost Protector | 80 | 0 | 
	| 40615 | Gloves of the Lost Vanquisher | 80 | 0 | 
	| 40616 | Helm of the Lost Conqueror | 80 | 0 | 
	| 40617 | Helm of the Lost Protector | 80 | 0 | 
	| 40618 | Helm of the Lost Vanquisher | 80 | 0 | 
	| 40619 | Leggings of the Lost Conqueror | 80 | 0 | 
	| 40620 | Leggings of the Lost Protector | 80 | 0 | 
	| 40621 | Leggings of the Lost Vanquisher | 80 | 0 | 
	| 40622 | Spaulders of the Lost Conqueror | 80 | 0 | 
	| 40623 | Spaulders of the Lost Protector | 80 | 0 | 
	| 40624 | Spaulders of the Lost Vanquisher | 80 | 0 | 
	| 40625 | Breastplate of the Lost Conqueror | 80 | 0 | 
	| 40626 | Breastplate of the Lost Protector | 80 | 0 | 
	| 40627 | Breastplate of the Lost Vanquisher | 80 | 0 | 
	| 40628 | Gauntlets of the Lost Conqueror | 80 | 0 | 
	| 40629 | Gauntlets of the Lost Protector | 80 | 0 | 
	| 40630 | Gauntlets of the Lost Vanquisher | 80 | 0 | 
	| 40631 | Crown of the Lost Conqueror | 80 | 0 | 
	| 40632 | Crown of the Lost Protector | 80 | 0 | 
	| 40633 | Crown of the Lost Vanquisher | 80 | 0 | 
	| 40634 | Legplates of the Lost Conqueror | 80 | 0 | 
	| 40635 | Legplates of the Lost Protector | 80 | 0 | 
	| 40636 | Legplates of the Lost Vanquisher | 80 | 0 | 
	| 40637 | Mantle of the Lost Conqueror | 80 | 0 | 
	| 40638 | Mantle of the Lost Protector | 80 | 0 | 
	| 40639 | Mantle of the Lost Vanquisher | 80 | 0 | 
	| 43556 | Patroller's Pack | 75 | 0 | 
	| 43575 | Reinforced Junkbox | 70 | 0 | 
	| 43622 | Froststeel Lockbox | 73 | 0 | 
	| 43624 | Titanium Lockbox | 78 | 0 | 
	| 43851 | Fur Clothing Scraps | 70 | 0 | 
	| 43852 | Thick Fur Clothing Scraps | 70 | 0 | 
	| 44299 | Crinkly Grass | 85 | 0 | 
	| 45632 | Breastplate of the Wayward Conqueror | 80 | 0 | 
	| 45633 | Breastplate of the Wayward Protector | 80 | 0 | 
	| 45634 | Breastplate of the Wayward Vanquisher | 80 | 0 | 
	| 45635 | Chestguard of the Wayward Conqueror | 80 | 0 | 
	| 45636 | Chestguard of the Wayward Protector | 80 | 0 | 
	| 45637 | Chestguard of the Wayward Vanquisher | 80 | 0 | 
	| 45638 | Crown of the Wayward Conqueror | 80 | 0 | 
	| 45639 | Crown of the Wayward Protector | 80 | 0 | 
	| 45640 | Crown of the Wayward Vanquisher | 80 | 0 | 
	| 45641 | Gauntlets of the Wayward Conqueror | 80 | 0 | 
	| 45642 | Gauntlets of the Wayward Protector | 80 | 0 | 
	| 45643 | Gauntlets of the Wayward Vanquisher | 80 | 0 | 
	| 45644 | Gloves of the Wayward Conqueror | 80 | 0 | 
	| 45645 | Gloves of the Wayward Protector | 80 | 0 | 
	| 45646 | Gloves of the Wayward Vanquisher | 80 | 0 | 
	| 45647 | Helm of the Wayward Conqueror | 80 | 0 | 
	| 45648 | Helm of the Wayward Protector | 80 | 0 | 
	| 45649 | Helm of the Wayward Vanquisher | 80 | 0 | 
	| 45650 | Leggings of the Wayward Conqueror | 80 | 0 | 
	| 45651 | Leggings of the Wayward Protector | 80 | 0 | 
	| 45652 | Leggings of the Wayward Vanquisher | 80 | 0 | 
	| 45653 | Legplates of the Wayward Conqueror | 80 | 0 | 
	| 45654 | Legplates of the Wayward Protector | 80 | 0 | 
	| 45655 | Legplates of the Wayward Vanquisher | 80 | 0 | 
	| 45656 | Mantle of the Wayward Conqueror | 80 | 0 | 
	| 45657 | Mantle of the Wayward Protector | 80 | 0 | 
	| 45658 | Mantle of the Wayward Vanquisher | 80 | 0 | 
	| 45659 | Spaulders of the Wayward Conqueror | 80 | 0 | 
	| 45660 | Spaulders of the Wayward Protector | 80 | 0 | 
	| 45661 | Spaulders of the Wayward Vanquisher | 80 | 0 | 
	| 45924 | Certificate of Appreciation | 174 | 0 | 
	| 45977 | Porcelain Bell | 70 | 0 | 
	| 45978 | Solid Gold Coin | 80 | 0 | 
	| 45979 | Tower Key | 80 | 0 | 
	| 45980 | Whale Statue | 80 | 0 | 
	| 45981 | New Age Painting | 80 | 0 | 
	| 45984 | Unusual Compass | 80 | 0 | 
	| 45986 | Tiny Titanium Lockbox | 80 | 0 | 
	| 45999 | Worthless Piece of White Glass | 80 | 0 | 
	| 46000 | Worthless Piece of Red Glass | 80 | 0 | 
	| 46001 | Worthless Piece of Green Glass | 80 | 0 | 
	| 46002 | Worthless Piece of Violet Glass | 80 | 0 | 
	| 46003 | Worthless Piece of Orange Glass | 80 | 0 | 
	| 46007 | Bag of Fishing Treasures | 80 | 0 | 
	| 46110 | Alchemist's Cache | 80 | 425 | 
	| 46359 | Velociraptor Skull | 80 | 0 | 
	| 46360 | Stuffed Shark Head | 80 | 0 | 
	| 46812 | Northrend Mystery Gem Pouch | 80 | 0 | 
	| 47557 | Regalia of the Grand Conqueror | 80 | 0 | 
	| 47558 | Regalia of the Grand Protector | 80 | 0 | 
	| 47559 | Regalia of the Grand Vanquisher | 80 | 0 | 
	| 49917 | Brazie's Gnomish Pleasure Device | 80 | 0 | 
	| 52004 | Satchel of Helpful Goods | 62 | 0 | 
	| 52005 | Satchel of Helpful Goods | 66 | 0 | 
	| 52025 | Vanquisher's Mark of Sanctification | 80 | 0 | 
	| 52026 | Protector's Mark of Sanctification | 80 | 0 | 
	| 52027 | Conqueror's Mark of Sanctification | 80 | 0 | 
	| 52028 | Vanquisher's Mark of Sanctification | 80 | 0 | 
	| 52029 | Protector's Mark of Sanctification | 80 | 0 | 
	| 52030 | Conqueror's Mark of Sanctification | 80 | 0 | 
	| 54516 | Loot-Filled Pumpkin | 80 | 0 | 
	| 54535 | Keg-Shaped Treasure Chest | 80 | 0 | 
	| 54536 | Satchel of Chilled Goods | 80 | 0 | 
	| 54537 | Heart-Shaped Box | 80 | 0 | 

	</details>
	
	24242, 24504, 24558, 24559, 25596, 25641, 26042, 26043, 27441, 27442, 27443, 27446, 28499, 29569, 29753, 29754, 29755, 29756, 29757, 29758, 29759, 29760, 29761, 29762, 29763, 29764, 29765, 29766, 29767, 30236, 30237, 30238, 30239, 30240, 30241, 30242, 30243, 30244, 30245, 30246, 30247, 30248, 30249, 30250, 30320, 30427, 31089, 31090, 31091, 31092, 31093, 31094, 31095, 31096, 31097, 31098, 31099, 31100, 31101, 31102, 31103, 31760, 31800, 31952, 32385, 32386, 32405, 32506, 32543, 32544, 32545, 32546, 32547, 32548, 32549, 32550, 32551, 32552, 32553, 32554, 32555, 32556, 32557, 32558, 32559, 32560, 32561, 32595, 32670, 32671, 32672, 32673, 32674, 32675, 32676, 32677, 32678, 32679, 32725, 32727, 32728, 32835, 32895, 32896, 33147, 33844, 34025, 34544, 34548, 34822, 34823, 34824, 34825, 34848, 34851, 34852, 34853, 34854, 34855, 34856, 34857, 34858, 34863, 35314, 35348, 37126, 37839, 38348, 38581, 40392, 40610, 40611, 40612, 40613, 40614, 40615, 40616, 40617, 40618, 40619, 40620, 40621, 40622, 40623, 40624, 40625, 40626, 40627, 40628, 40629, 40630, 40631, 40632, 40633, 40634, 40635, 40636, 40637, 40638, 40639, 43556, 43575, 43622, 43624, 43851, 43852, 44299, 45632, 45633, 45634, 45635, 45636, 45637, 45638, 45639, 45640, 45641, 45642, 45643, 45644, 45645, 45646, 45647, 45648, 45649, 45650, 45651, 45652, 45653, 45654, 45655, 45656, 45657, 45658, 45659, 45660, 45661, 45924, 45977, 45978, 45979, 45980, 45981, 45984, 45986, 45999, 46000, 46001, 46002, 46003, 46007, 46110, 46359, 46360, 46812, 47557, 47558, 47559, 49917, 52004, 52005, 52025, 52026, 52027, 52028, 52029, 52030, 54516, 54535, 54536, 54537

	<hr>
	
  - Reagent (subclass = 1)
    5 x ilvl 60 vanilla reagents, highest index id is 21177. TBC reagents start at 70 (only 5 as they were mostly phased out anyway.) As all of these are widely sold throughout the old world however, not going to list them.
	
	```SQL
	SELECT it.entry, it.name, it.ItemLevel, it.RequiredSkillRank 
	FROM item_template it 
	WHERE it.class = 15 AND it.subclass = 1
	AND it.ItemLevel >= 70

	```

	Skipped.

	<hr>
	
  - Pet (subclass = 2)
    Leaving this class alone as they are sold in the CC store.
  
  - Holiday (subclass = 3)
    Skipping.
  
  - Other (subclass = 4)
    Vanilla goes to 60, with 1 x ilvl 70 item (Adamantite Arrow Maker 20475) which is listed as Consumeable -> Other on AC and handled there. TBC items start at ilvl 60, but most are listed under other categories so not many left here.
	
	```SQL
	SELECT it.entry, it.name, it.ItemLevel, it.RequiredSkillRank 
	FROM item_template it 
	WHERE it.class = 15 AND it.subclass = 4
	AND it.ItemLevel >= 60

	```

	<details>
	<summary>Results</summary>

	---
	| entry | name | ItemLevel | RequiredSkillRank | 
	| ---: | --- | ---: | ---: | 
	| 27481 | Heavy Supply Crate | 60 | 0 | 
	| 32897 | Mark of the Illidari | 70 | 0 | 
	| 35286 | Bloated Giant Sunfish | 70 | 0 | 
	| 47242 | Trophy of the Crusade | 80 | 0 | 
	| 52201 | Muradin's Favor | 80 | 0 | 
	| 52251 | Jaina's Locket | 80 | 0 | 
	| 52253 | Sylvanas's Music Box | 80 | 0 | 

	</details>
	
	27481, 32897, 35286, 47242, 52201, 52251, 52253

	<hr>

  - Mounts (subclass = 5)
    Leaving this class alone as they are sold in the CC store, and are unlikely to be obtained illegally in any case.
