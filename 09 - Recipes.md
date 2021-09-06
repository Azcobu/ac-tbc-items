
## Recipes (class = 9)

- ### Book (subclass = 0)
	Highest vanilla book is ilvl 60, lots of them. Highest index is 24102. TBC books go down to 50, but they are demon training books which were removed in 3.0.2 (see https://wowwiki-archive.fandom.com/wiki/Demon_Trainer_grimoires) Skipping those, next lowest in TBC is ilvl 60, a druid book teaching Cower, which is useless since it can be learned at the trainer anyway. Moving on, lots more 61-69 demon trainer books, all junk, before we get to lvl 70 and some worthwhile items. So really looks like itemlevel >= 70 is fine.
	
	```SQL
	SELECT it.entry, it.name, it.ItemLevel, it.RequiredLevel
	FROM `item_template` it
	WHERE it.class = 9 AND it.subclass = 0
	AND it.ItemLevel >= 70
	```
	
	<details>
	<summary>Results</summary>
	
	---
	| entry | name | ItemLevel | RequiredLevel | 
	| ---: | --- | ---: | ---: | 
	| 22146 | Book: Gift of the Wild III | 70 | 70 | 
	| 22153 | Tome of Arcane Brilliance 2 | 70 | 70 | 
	| 22182 | Grimoire of Torment (Rank 7) | 70 | 70 | 
	| 22187 | Grimoire of Soothing Kiss (Rank 5) | 70 | 70 | 
	| 22189 | Grimoire of Devour Magic (Rank 6) | 70 | 70 | 
	| 28073 | Grimoire of Anguish (Rank 3) | 70 | 70 | 
	| 29549 | Codex: Prayer of Fortitude III | 70 | 70 | 
	| 29550 | Tome of Conjure Water IX | 70 | 70 | 
	| 31501 | Tome of Conjure Food VIII | 70 | 70 | 
	| 31837 | Codex: Prayer of Shadow Protection II | 70 | 70 | 
	| 33316 | Tome of Arcane Brilliance | 80 | 80 | 
	| 35273 | Study of Advanced Smelting | 70 | 0 | 
	| 36955 | Grimoire of Firebolt (Rank 9) | 78 | 78 | 
	| 36959 | Grimoire of Blood Pact (Rank 7) | 74 | 74 | 
	| 36960 | Grimoire of Fire Shield (Rank 7) | 76 | 76 | 
	| 36964 | Grimoire of Sacrifice (Rank 8) | 72 | 72 | 
	| 36965 | Grimoire of Sacrifice (Rank 9) | 79 | 79 | 
	| 36966 | Grimoire of Consume Shadows (Rank 8) | 73 | 73 | 
	| 36967 | Grimoire of Consume Shadows (Rank 9) | 78 | 78 | 
	| 36968 | Grimoire of Suffering (Rank 7) | 75 | 75 | 
	| 36970 | Grimoire of Suffering (Rank 8) | 80 | 80 | 
	| 44602 | Tome of Dalaran Intellect | 80 | 80 | 
	| 44714 | Tome of Dalaran Brilliance | 80 | 80 | 
	| 45912 | Book of Glyph Mastery | 80 | 0 | 
	| 46108 | Technique: Rituals of the New Moon | 70 | 0 | 
	| 49177 | Tome of Cold Weather Flight | 80 | 68 | 
	| 50167 | Technique: Glyph of Rapid Rejuvenation | 70 | 0 | 
	| 50168 | Technique: Glyph of Quick Decay | 70 | 0 | 

	</details>
	
	22146, 22153, 22182, 22187, 22189, 28073, 29549, 29550, 31501, 31837, 33316, 35273, 36955, 36959, 36960, 36964, 36965, 36966, 36967, 36968, 36970, 44602, 44714, 45912, 46108, 49177, 50167, 50168
	
	<hr>
	
-  ### Leatherworking (subclass = 1)
	Vanilla LW recipes go up to ilvl 80/skill 300. TBC LW recipes start at 57/285 skill, but that's only 1 (pattern: winter boots 34262). There's 1 x ilvl 60/skill 300 (pattern: comfortable insoles 25726), and the rest are ilvl 65/skill 325. Index breakpoint is ~25K. So a query for >= ilvl 60 and index > 25K + winter boots should work.

	```SQL
	SELECT it.entry  , it.name, it.ItemLevel, it.RequiredLevel
	FROM `item_template` it
	WHERE it.class = 9 AND it.subclass = 1
	AND it.ItemLevel >= 60 AND it.entry >= 25000 
	```
	
	<details>
	<summary>Results</summary>
	
	---
	| entry | name | ItemLevel | RequiredLevel | 
	| ---: | --- | ---: | ---: | 
	| 25720 | Pattern: Heavy Knothide Leather | 65 | 0 | 
	| 25721 | Pattern: Vindicator's Armor Kit | 65 | 0 | 
	| 25722 | Pattern: Magister's Armor Kit | 65 | 0 | 
	| 25725 | Pattern: Riding Crop | 70 | 0 | 
	| 25726 | Pattern: Comfortable Insoles | 60 | 0 | 
	| 25728 | Pattern: Stylin' Purple Hat | 70 | 0 | 
	| 25729 | Pattern: Stylin' Adventure Hat | 70 | 0 | 
	| 25730 | Pattern: Stylin' Jungle Hat | 70 | 0 | 
	| 25731 | Pattern: Stylin' Crimson Hat | 70 | 0 | 
	| 25732 | Pattern: Fel Leather Gloves | 68 | 0 | 
	| 25733 | Pattern: Fel Leather Boots | 70 | 0 | 
	| 25734 | Pattern: Fel Leather Leggings | 70 | 0 | 
	| 25735 | Pattern: Heavy Clefthoof Vest | 72 | 0 | 
	| 25736 | Pattern: Heavy Clefthoof Leggings | 71 | 0 | 
	| 25737 | Pattern: Heavy Clefthoof Boots | 71 | 0 | 
	| 25738 | Pattern: Felstalker Belt | 70 | 0 | 
	| 25739 | Pattern: Felstalker Bracers | 72 | 0 | 
	| 25740 | Pattern: Felstalker Breastplate | 72 | 0 | 
	| 25741 | Pattern: Netherfury Belt | 68 | 0 | 
	| 25742 | Pattern: Netherfury Leggings | 68 | 0 | 
	| 25743 | Pattern: Netherfury Boots | 70 | 0 | 
	| 29213 | Pattern: Felstalker Belt | 70 | 0 | 
	| 29214 | Pattern: Felstalker Bracers | 72 | 0 | 
	| 29215 | Pattern: Felstalker Breastplate | 72 | 0 | 
	| 29217 | Pattern: Netherfury Belt | 68 | 0 | 
	| 29218 | Pattern: Netherfury Boots | 70 | 0 | 
	| 29219 | Pattern: Netherfury Leggings | 68 | 0 | 
	| 29664 | Pattern: Reinforced Mining Bag | 65 | 0 | 
	| 29669 | Pattern: Shadow Armor Kit | 68 | 0 | 
	| 29672 | Pattern: Flame Armor Kit | 68 | 0 | 
	| 29673 | Pattern: Frost Armor Kit | 68 | 0 | 
	| 29674 | Pattern: Nature Armor Kit | 68 | 0 | 
	| 29675 | Pattern: Arcane Armor Kit | 68 | 0 | 
	| 29677 | Pattern: Enchanted Felscale Leggings | 70 | 0 | 
	| 29682 | Pattern: Enchanted Felscale Gloves | 70 | 0 | 
	| 29684 | Pattern: Enchanted Felscale Boots | 70 | 0 | 
	| 29689 | Pattern: Flamescale Leggings | 70 | 0 | 
	| 29691 | Pattern: Flamescale Boots | 70 | 0 | 
	| 29693 | Pattern: Flamescale Belt | 70 | 0 | 
	| 29698 | Pattern: Enchanted Clefthoof Leggings | 70 | 0 | 
	| 29700 | Pattern: Enchanted Clefthoof Gloves | 70 | 0 | 
	| 29701 | Pattern: Enchanted Clefthoof Boots | 70 | 0 | 
	| 29702 | Pattern: Blastguard Pants | 70 | 0 | 
	| 29703 | Pattern: Blastguard Boots | 70 | 0 | 
	| 29704 | Pattern: Blastguard Belt | 70 | 0 | 
	| 29713 | Pattern: Drums of Panic | 74 | 0 | 
	| 29714 | Pattern: Drums of Restoration | 70 | 0 | 
	| 29717 | Pattern: Drums of Battle | 73 | 0 | 
	| 29718 | Pattern: Drums of Speed | 69 | 0 | 
	| 29719 | Pattern: Cobrahide Leg Armor | 67 | 0 | 
	| 29720 | Pattern: Clefthide Leg Armor | 67 | 0 | 
	| 29721 | Pattern: Nethercleft Leg Armor | 73 | 0 | 
	| 29722 | Pattern: Nethercobra Leg Armor | 73 | 0 | 
	| 29723 | Pattern: Cobrascale Hood | 73 | 0 | 
	| 29724 | Pattern: Cobrascale Gloves | 73 | 0 | 
	| 29725 | Pattern: Windscale Hood | 73 | 0 | 
	| 29726 | Pattern: Hood of Primal Life | 73 | 0 | 
	| 29727 | Pattern: Gloves of the Living Touch | 73 | 0 | 
	| 29728 | Pattern: Windslayer Wraps | 73 | 0 | 
	| 29729 | Pattern: Living Dragonscale Helm | 73 | 0 | 
	| 29730 | Pattern: Earthen Netherscale Boots | 73 | 0 | 
	| 29731 | Pattern: Windstrike Gloves | 73 | 0 | 
	| 29732 | Pattern: Netherdrake Helm | 73 | 0 | 
	| 29733 | Pattern: Netherdrake Gloves | 73 | 0 | 
	| 29734 | Pattern: Thick Netherscale Breastplate | 73 | 0 | 
	| 30301 | Pattern: Belt of Natural Power | 75 | 0 | 
	| 30302 | Pattern: Belt of Deep Shadow | 75 | 0 | 
	| 30303 | Pattern: Belt of the Black Eagle | 75 | 0 | 
	| 30304 | Pattern: Monsoon Belt | 75 | 0 | 
	| 30305 | Pattern: Boots of Natural Grace | 75 | 0 | 
	| 30306 | Pattern: Boots of Utter Darkness | 75 | 0 | 
	| 30307 | Pattern: Boots of the Crimson Hawk | 75 | 0 | 
	| 30308 | Pattern: Hurricane Boots | 75 | 0 | 
	| 30444 | Pattern: Reinforced Mining Bag | 65 | 0 | 
	| 31361 | Pattern: Cobrahide Leg Armor | 67 | 0 | 
	| 31362 | Pattern: Nethercobra Leg Armor | 73 | 0 | 
	| 32429 | Pattern: Boots of Shackled Souls | 75 | 0 | 
	| 32430 | Pattern: Bracers of Shackled Souls | 75 | 0 | 
	| 32431 | Pattern: Greaves of Shackled Souls | 75 | 0 | 
	| 32432 | Pattern: Waistguard of Shackled Souls | 75 | 0 | 
	| 32433 | Pattern: Redeemed Soul Moccasins | 75 | 0 | 
	| 32434 | Pattern: Redeemed Soul Wristguards | 75 | 0 | 
	| 32435 | Pattern: Redeemed Soul Legguards | 75 | 0 | 
	| 32436 | Pattern: Redeemed Soul Cinch | 75 | 0 | 
	| 32744 | Pattern: Bracers of Renewed Life | 70 | 0 | 
	| 32745 | Pattern: Shoulderpads of Renewed Life | 70 | 0 | 
	| 32746 | Pattern: Swiftstrike Bracers | 70 | 0 | 
	| 32747 | Pattern: Swiftstrike Shoulders | 70 | 0 | 
	| 32748 | Pattern: Bindings of Lightning Reflexes | 70 | 0 | 
	| 32749 | Pattern: Shoulders of Lightning Reflexes | 70 | 0 | 
	| 32750 | Pattern: Living Earth Bindings | 70 | 0 | 
	| 32751 | Pattern: Living Earth Shoulders | 70 | 0 | 
	| 33124 | Pattern: Cloak of Darkness | 70 | 0 | 
	| 33205 | Pattern: Shadowprowler's Chestguard | 73 | 0 | 
	| 34172 | Pattern: Drums of Speed | 69 | 0 | 
	| 34173 | Pattern: Drums of Speed | 69 | 0 | 
	| 34174 | Pattern: Drums of Restoration | 70 | 0 | 
	| 34175 | Pattern: Drums of Restoration | 70 | 0 | 
	| 34200 | Pattern: Quiver of a Thousand Feathers | 70 | 0 | 
	| 34201 | Pattern: Netherscale Ammo Pouch | 70 | 0 | 
	| 34218 | Pattern: Netherscale Ammo Pouch | 70 | 0 | 
	| 34491 | Pattern: Bag of Many Hides | 72 | 0 | 
	| 35212 | Pattern: Leather Gauntlets of the Sun | 75 | 0 | 
	| 35213 | Pattern: Fletcher's Gloves of the Phoenix | 75 | 0 | 
	| 35214 | Pattern: Gloves of Immortal Dusk | 75 | 0 | 
	| 35215 | Pattern: Sun-Drenched Scale Gloves | 75 | 0 | 
	| 35216 | Pattern: Leather Chestguard of the Sun | 75 | 0 | 
	| 35217 | Pattern: Embrace of the Phoenix | 75 | 0 | 
	| 35218 | Pattern: Carapace of Sun and Shadow | 75 | 0 | 
	| 35219 | Pattern: Sun-Drenched Scale Chestguard | 75 | 0 | 
	| 35300 | Pattern: Windstrike Gloves | 73 | 0 | 
	| 35301 | Pattern: Netherdrake Gloves | 73 | 0 | 
	| 35302 | Pattern: Cobrascale Gloves | 73 | 0 | 
	| 35303 | Pattern: Gloves of the Living Touch | 73 | 0 | 
	| 35517 | Pattern: Bindings of Lightning Reflexes | 70 | 70 | 
	| 35519 | Pattern: Bracers of Renewed Life | 70 | 70 | 
	| 35520 | Pattern: Living Earth Bindings | 70 | 70 | 
	| 35521 | Pattern: Living Earth Shoulders | 70 | 70 | 
	| 35523 | Pattern: Shoulderpads of Renewed Life | 70 | 70 | 
	| 35524 | Pattern: Shoulders of Lightning Reflexes | 70 | 70 | 
	| 35527 | Pattern: Swiftstrike Bracers | 70 | 70 | 
	| 35528 | Pattern: Swiftstrike Shoulders | 70 | 70 | 
	| 35539 | Pattern: Carapace of Sun and Shadow | 75 | 70 | 
	| 35541 | Pattern: Fletcher's Gloves of the Phoenix | 75 | 70 | 
	| 35545 | Pattern: Leather Chestguard of the Sun | 75 | 70 | 
	| 35546 | Pattern: Leather Gauntlets of the Sun | 75 | 70 | 
	| 35549 | Pattern: Sun-Drenched Scale Chestguard | 75 | 70 | 
	| 35550 | Pattern: Sun-Drenched Scale Gloves | 75 | 70 | 
	| 38597 | Pattern: Dark Arctic Boots | 75 | 0 | 
	| 44509 | Pattern: Trapper's Traveling Pack | 75 | 0 | 
	| 44510 | Pattern: Mammoth Mining Bag | 75 | 0 | 
	| 44511 | Pattern: Dragonscale Ammo Pouch | 75 | 0 | 
	| 44512 | Pattern: Nerubian Reinforced Quiver | 75 | 0 | 
	| 44513 | Pattern: Eviscerator's Facemask | 80 | 0 | 
	| 44514 | Pattern: Eviscerator's Shoulderpads | 80 | 0 | 
	| 44515 | Pattern: Eviscerator's Chestguard | 80 | 0 | 
	| 44516 | Pattern: Eviscerator's Bindings | 80 | 0 | 
	| 44517 | Pattern: Eviscerator's Gauntlets | 80 | 0 | 
	| 44518 | Pattern: Eviscerator's Waistguard | 80 | 0 | 
	| 44519 | Pattern: Eviscerator's Legguards | 80 | 0 | 
	| 44520 | Pattern: Eviscerator's Treads | 80 | 0 | 
	| 44521 | Pattern: Overcast Headguard | 80 | 0 | 
	| 44522 | Pattern: Overcast Spaulders | 80 | 0 | 
	| 44523 | Pattern: Overcast Chestguard | 80 | 0 | 
	| 44524 | Pattern: Overcast Bracers | 80 | 0 | 
	| 44525 | Pattern: Overcast Handwraps | 80 | 0 | 
	| 44526 | Pattern: Overcast Belt | 80 | 0 | 
	| 44527 | Pattern: Overcast Leggings | 80 | 0 | 
	| 44528 | Pattern: Overcast Boots | 80 | 0 | 
	| 44530 | Pattern: Swiftarrow Helm | 80 | 0 | 
	| 44531 | Pattern: Swiftarrow Shoulderguards | 80 | 0 | 
	| 44532 | Pattern: Swiftarrow Hauberk | 80 | 0 | 
	| 44533 | Pattern: Swiftarrow Bracers | 80 | 0 | 
	| 44534 | Pattern: Swiftarrow Gauntlets | 80 | 0 | 
	| 44535 | Pattern: Swiftarrow Belt | 80 | 0 | 
	| 44536 | Pattern: Swiftarrow Leggings | 80 | 0 | 
	| 44537 | Pattern: Swiftarrow Boots | 80 | 0 | 
	| 44538 | Pattern: Stormhide Crown | 80 | 0 | 
	| 44539 | Pattern: Stormhide Shoulders | 80 | 0 | 
	| 44540 | Pattern: Stormhide Hauberk | 80 | 0 | 
	| 44541 | Pattern: Stormhide Wristguards | 80 | 0 | 
	| 44542 | Pattern: Stormhide Grips | 80 | 0 | 
	| 44543 | Pattern: Stormhide Belt | 80 | 0 | 
	| 44544 | Pattern: Stormhide Legguards | 80 | 0 | 
	| 44545 | Pattern: Stormhide Stompers | 80 | 0 | 
	| 44546 | Pattern: Giantmaim Legguards | 80 | 0 | 
	| 44547 | Pattern: Giantmaim Bracers | 80 | 0 | 
	| 44548 | Pattern: Revenant's Breastplate | 80 | 0 | 
	| 44549 | Pattern: Revenant's Treads | 80 | 0 | 
	| 44550 | Pattern: Trollwoven Spaulders | 80 | 0 | 
	| 44551 | Pattern: Trollwoven Girdle | 80 | 0 | 
	| 44552 | Pattern: Earthgiving Legguards | 80 | 0 | 
	| 44553 | Pattern: Earthgiving Boots | 80 | 0 | 
	| 44559 | Pattern: Fur Lining - Fire Resist | 80 | 0 | 
	| 44560 | Pattern: Fur Lining - Frost Resist | 80 | 0 | 
	| 44561 | Pattern: Fur Lining - Shadow Resist | 80 | 0 | 
	| 44562 | Pattern: Fur Lining - Nature Resist  | 80 | 0 | 
	| 44563 | Pattern: Fur Lining - Arcane Resist | 80 | 0 | 
	| 44584 | Pattern: Polar Vest | 80 | 0 | 
	| 44585 | Pattern: Polar Cord | 80 | 0 | 
	| 44586 | Pattern: Polar Boots | 80 | 0 | 
	| 44587 | Pattern: Icy Scale Chestguard | 80 | 0 | 
	| 44588 | Pattern: Icy Scale Belt | 80 | 0 | 
	| 44589 | Pattern: Icy Scale Boots | 80 | 0 | 
	| 44932 | Pattern: Windripper Boots | 80 | 0 | 
	| 44933 | Pattern: Windripper Leggings | 80 | 0 | 
	| 45094 | Pattern: Belt of Dragons | 85 | 0 | 
	| 45095 | Pattern: Boots of Living Scale | 85 | 0 | 
	| 45096 | Pattern: Blue Belt of Chaos | 85 | 0 | 
	| 45097 | Pattern: Lightning Grounded Boots | 85 | 0 | 
	| 45098 | Pattern: Death-warmed Belt | 85 | 0 | 
	| 45099 | Pattern: Footpads of Silence | 85 | 0 | 
	| 45100 | Pattern: Belt of Arctic Life | 85 | 0 | 
	| 45101 | Pattern: Boots of Wintry Endurance | 85 | 0 | 
	| 47628 | Pattern: Ensorcelled Nerubian Breastplate | 85 | 0 | 
	| 47629 | Pattern: Black Chitin Bracers | 85 | 0 | 
	| 47630 | Pattern: Crusader's Dragonscale Breastplate | 85 | 0 | 
	| 47631 | Pattern: Crusader's Dragonscale Bracers | 85 | 0 | 
	| 47632 | Pattern: Lunar Eclipse Robes | 85 | 0 | 
	| 47633 | Pattern: Moonshadow Armguards | 85 | 0 | 
	| 47634 | Pattern: Knightbane Carapace | 85 | 0 | 
	| 47635 | Pattern: Bracers of Swift Death | 85 | 0 | 
	| 47646 | Pattern: Black Chitin Bracers | 85 | 0 | 
	| 47647 | Pattern: Bracers of Swift Death | 85 | 0 | 
	| 47648 | Pattern: Crusader's Dragonscale Bracers | 85 | 0 | 
	| 47649 | Pattern: Crusader's Dragonscale Breastplate | 85 | 0 | 
	| 47650 | Pattern: Ensorcelled Nerubian Breastplate | 85 | 0 | 
	| 47651 | Pattern: Knightbane Carapace | 85 | 0 | 
	| 47652 | Pattern: Lunar Eclipse Robes | 85 | 0 | 
	| 47653 | Pattern: Moonshadow Armguards | 85 | 0 | 
	| 49957 | Pattern: Legwraps of Unleashed Nature | 85 | 0 | 
	| 49958 | Pattern: Blessed Cenarion Boots | 85 | 0 | 
	| 49959 | Pattern: Bladeborn Leggings | 85 | 0 | 
	| 49961 | Pattern: Footpads of Impending Death | 85 | 0 | 
	| 49962 | Pattern: Lightning-Infused Leggings | 85 | 0 | 
	| 49963 | Pattern: Earthsoul Boots | 85 | 0 | 
	| 49965 | Pattern: Draconic Bonesplinter Legguards | 85 | 0 | 
	| 49966 | Pattern: Rock-Steady Treads | 85 | 0 | 
	
	</details>
	
	Note: manually added 34262
	
	25720, 25721, 25722, 25725, 25726, 25728, 25729, 25730, 25731, 25732, 25733, 25734, 25735, 25736, 25737, 25738, 25739, 25740, 25741, 25742, 25743, 29213, 29214, 29215, 29217, 29218, 29219, 29664, 29669, 29672, 29673, 29674, 29675, 29677, 29682, 29684, 29689, 29691, 29693, 29698, 29700, 29701, 29702, 29703, 29704, 29713, 29714, 29717, 29718, 29719, 29720, 29721, 29722, 29723, 29724, 29725, 29726, 29727, 29728, 29729, 29730, 29731, 29732, 29733, 29734, 30301, 30302, 30303, 30304, 30305, 30306, 30307, 30308, 30444, 31361, 31362, 32429, 32430, 32431, 32432, 32433, 32434, 32435, 32436, 32744, 32745, 32746, 32747, 32748, 32749, 32750, 32751, 33124, 33205, 34172, 34173, 34174, 34175, 34200, 34201, 34218, 34491, 35212, 35213, 35214, 35215, 35216, 35217, 35218, 35219, 35300, 35301, 35302, 35303, 35517, 35519, 35520, 35521, 35523, 35524, 35527, 35528, 35539, 35541, 35545, 35546, 35549, 35550, 38597, 44509, 44510, 44511, 44512, 44513, 44514, 44515, 44516, 44517, 44518, 44519, 44520, 44521, 44522, 44523, 44524, 44525, 44526, 44527, 44528, 44530, 44531, 44532, 44533, 44534, 44535, 44536, 44537, 44538, 44539, 44540, 44541, 44542, 44543, 44544, 44545, 44546, 44547, 44548, 44549, 44550, 44551, 44552, 44553, 44559, 44560, 44561, 44562, 44563, 44584, 44585, 44586, 44587, 44588, 44589, 44932, 44933, 45094, 45095, 45096, 45097, 45098, 45099, 45100, 45101, 47628, 47629, 47630, 47631, 47632, 47633, 47634, 47635, 47646, 47647, 47648, 47649, 47650, 47651, 47652, 47653, 49957, 49958, 49959, 49961, 49962, 49963, 49965, 49966, 34262
	
	<hr>
	
- ### Tailoring patterns (subclass = 2)
	Lowest TBC pattern is 62/300 skill (Truefaith Vestments 29120) which looks very much like a vanilla item added later. (It was added in TBC but uniquely only uses vanilla ingredients and 300 skill.) From there on all TBC recipes need 325+ skill. Vanilla recipes go up to lvl 80, all below id 23000 though and all needing skill = 300. So the query could just be skill >= 325.
	
	```SQL
	SELECT it.entry, it.name, it.ItemLevel, it.RequiredSkillRank
	FROM `item_template` it
	WHERE it.class = 9 AND it.subclass = 2 
	AND it.RequiredSkillRank >= 325
	```
	
	<details>
	<summary>Results</summary>
	
	---
	| entry | name | ItemLevel | RequiredSkillRank | 
	| ---: | --- | ---: | ---: | 
	| 21892 | Pattern: Bolt of Imbued Netherweave | 65 | 325 | 
	| 21893 | Pattern: Imbued Netherweave Bag | 68 | 340 | 
	| 21894 | Pattern: Bolt of Soulcloth | 69 | 345 | 
	| 21895 | Pattern: Primal Mooncloth | 70 | 350 | 
	| 21896 | Pattern: Netherweave Robe | 68 | 340 | 
	| 21897 | Pattern: Netherweave Tunic | 69 | 345 | 
	| 21898 | Pattern: Imbued Netherweave Pants | 68 | 340 | 
	| 21899 | Pattern: Imbued Netherweave Boots | 70 | 350 | 
	| 21900 | Pattern: Imbued Netherweave Robe | 72 | 360 | 
	| 21901 | Pattern: Imbued Netherweave Tunic | 72 | 360 | 
	| 21902 | Pattern: Soulcloth Gloves | 71 | 355 | 
	| 21903 | Pattern: Soulcloth Shoulders | 73 | 365 | 
	| 21904 | Pattern: Soulcloth Vest | 75 | 375 | 
	| 21905 | Pattern: Arcanoweave Bracers | 70 | 350 | 
	| 21906 | Pattern: Arcanoweave Boots | 72 | 360 | 
	| 21907 | Pattern: Arcanoweave Robe | 74 | 370 | 
	| 21908 | Pattern: Spellfire Belt | 71 | 355 | 
	| 21909 | Pattern: Spellfire Gloves | 73 | 365 | 
	| 21910 | Pattern: Spellfire Robe | 75 | 375 | 
	| 21911 | Pattern: Spellfire Bag | 75 | 375 | 
	| 21912 | Pattern: Frozen Shadoweave Shoulders | 71 | 355 | 
	| 21913 | Pattern: Frozen Shadoweave Robe | 75 | 375 | 
	| 21914 | Pattern: Frozen Shadoweave Boots | 73 | 365 | 
	| 21915 | Pattern: Ebon Shadowbag | 75 | 375 | 
	| 21916 | Pattern: Primal Mooncloth Belt | 71 | 355 | 
	| 21917 | Pattern: Primal Mooncloth Robe | 75 | 375 | 
	| 21918 | Pattern: Primal Mooncloth Shoulders | 73 | 365 | 
	| 21919 | Pattern: Primal Mooncloth Bag | 75 | 375 | 
	| 24292 | Pattern: Mystic Spellthread | 67 | 335 | 
	| 24293 | Pattern: Silver Spellthread | 67 | 335 | 
	| 24294 | Pattern: Runic Spellthread | 75 | 375 | 
	| 24295 | Pattern: Golden Spellthread | 75 | 375 | 
	| 24296 | Pattern: Unyielding Bracers | 70 | 350 | 
	| 24297 | Pattern: Bracers of Havok | 70 | 350 | 
	| 24298 | Pattern: Blackstrike Bracers | 70 | 350 | 
	| 24299 | Pattern: Cloak of the Black Void | 70 | 350 | 
	| 24300 | Pattern: Cloak of Eternity | 70 | 350 | 
	| 24301 | Pattern: White Remedy Cape | 70 | 350 | 
	| 24302 | Pattern: Unyielding Girdle | 73 | 365 | 
	| 24303 | Pattern: Girdle of Ruination | 73 | 365 | 
	| 24304 | Pattern: Black Belt of Knowledge | 73 | 365 | 
	| 24305 | Pattern: Resolute Cape | 73 | 365 | 
	| 24306 | Pattern: Vengeance Wrap | 73 | 365 | 
	| 24307 | Pattern: Manaweave Cloak | 73 | 365 | 
	| 24308 | Pattern: Whitemend Pants | 75 | 375 | 
	| 24309 | Pattern: Spellstrike Pants | 75 | 375 | 
	| 24310 | Pattern: Battlecast Pants | 75 | 375 | 
	| 24311 | Pattern: Whitemend Hood | 75 | 375 | 
	| 24312 | Pattern: Spellstrike Hood | 75 | 375 | 
	| 24313 | Pattern: Battlecast Hood | 75 | 375 | 
	| 24314 | Pattern: Bag of Jewels | 68 | 340 | 
	| 24315 | Pattern: Heavy Netherweave Net | 65 | 325 | 
	| 24316 | Pattern: Spellcloth | 70 | 350 | 
	| 30280 | Pattern: Belt of Blasting | 75 | 375 | 
	| 30281 | Pattern: Belt of the Long Road | 75 | 375 | 
	| 30282 | Pattern: Boots of Blasting | 75 | 375 | 
	| 30283 | Pattern: Boots of the Long Road | 75 | 375 | 
	| 30483 | Pattern: Shadowcloth | 70 | 350 | 
	| 30833 | Pattern: Cloak of Arcane Evasion | 70 | 350 | 
	| 30842 | Pattern: Flameheart Bracers | 70 | 350 | 
	| 30843 | Pattern: Flameheart Gloves | 70 | 360 | 
	| 30844 | Pattern: Flameheart Vest | 70 | 370 | 
	| 32437 | Pattern: Soulguard Slippers | 75 | 375 | 
	| 32438 | Pattern: Soulguard Bracers | 75 | 375 | 
	| 32439 | Pattern: Soulguard Leggings | 75 | 375 | 
	| 32440 | Pattern: Soulguard Girdle | 75 | 375 | 
	| 32447 | Pattern: Night's End | 75 | 375 | 
	| 32752 | Pattern: Swiftheal Wraps | 70 | 375 | 
	| 32753 | Pattern: Swiftheal Mantle | 70 | 375 | 
	| 32754 | Pattern: Bracers of Nimble Thought | 70 | 375 | 
	| 32755 | Pattern: Mantle of Nimble Thought | 70 | 375 | 
	| 35204 | Pattern: Sunfire Handwraps | 70 | 365 | 
	| 35205 | Pattern: Hands of Eternal Light | 70 | 365 | 
	| 35206 | Pattern: Sunfire Robe | 70 | 365 | 
	| 35207 | Pattern: Robe of Eternal Light | 70 | 365 | 
	| 35308 | Pattern: Unyielding Bracers | 70 | 350 | 
	| 35309 | Pattern: Unyielding Girdle | 73 | 365 | 
	| 35518 | Pattern: Bracers of Nimble Thought | 70 | 375 | 
	| 35522 | Pattern: Mantle of Nimble Thought | 70 | 375 | 
	| 35525 | Pattern: Swiftheal Mantle | 70 | 375 | 
	| 35526 | Pattern: Swiftheal Wraps | 70 | 375 | 
	| 35544 | Pattern: Hands of Eternal Light | 70 | 365 | 
	| 35548 | Pattern: Robe of Eternal Light | 70 | 365 | 
	| 35551 | Pattern: Sunfire Handwraps | 70 | 365 | 
	| 38229 | Pattern: Mycah's Botanical Bag | 75 | 375 | 
	| 42172 | Pattern: Red Lumberjack Shirt | 72 | 400 | 
	| 42173 | Pattern: Blue Lumberjack Shirt | 72 | 400 | 
	| 42174 | Pattern: Yellow Lumberjack Shirt | 72 | 400 | 
	| 42175 | Pattern: Green Lumberjack Shirt | 72 | 400 | 
	| 42176 | Pattern: Blue Workman's Shirt | 72 | 400 | 
	| 42177 | Pattern: Red Workman's Shirt | 72 | 400 | 
	| 42178 | Pattern: Rustic Workman's Shirt | 72 | 400 | 
	| 42179 | Pattern: Green Workman's Shirt | 72 | 400 | 
	| 42180 | Pattern: Ebonweave | 78 | 415 | 
	| 42181 | Pattern: Moonshroud | 78 | 415 | 
	| 42182 | Pattern: Spellweave | 78 | 415 | 
	| 42183 | Pattern: Abyssal Bag | 78 | 435 | 
	| 42184 | Pattern: Glacial Bag | 78 | 445 | 
	| 42185 | Pattern: Mysterious Bag | 78 | 440 | 
	| 42186 | Pattern: Frostweave Bag | 78 | 410 | 
	| 42187 | Pattern: Brilliant Spellthread | 78 | 430 | 
	| 42188 | Pattern: Sapphire Spellthread | 78 | 430 | 
	| 42189 | Pattern: Wispcloak | 78 | 415 | 
	| 42190 | Pattern: Deathchill Cloak | 78 | 420 | 
	| 42191 | Pattern: Hat of Wintry Doom | 78 | 425 | 
	| 42192 | Pattern: Silky Iceshard Boots | 78 | 425 | 
	| 42193 | Pattern: Glacial Cord | 78 | 425 | 
	| 42194 | Pattern: Frostmoon Pants | 78 | 425 | 
	| 42195 | Pattern: Light Blessed Mittens | 78 | 425 | 
	| 42196 | Pattern: Aurora Slippers | 78 | 425 | 
	| 42197 | Pattern: Moonshroud Robe | 80 | 450 | 
	| 42198 | Pattern: Moonshroud Gloves | 80 | 440 | 
	| 42199 | Pattern: Ebonweave Robe | 80 | 450 | 
	| 42200 | Pattern: Ebonweave Gloves | 80 | 440 | 
	| 42201 | Pattern: Spellweave Robe | 80 | 450 | 
	| 42202 | Pattern: Spellweave Gloves | 80 | 440 | 
	| 43876 | A Guide to Northern Cloth Scavenging | 70 | 325 | 
	| 45102 | Pattern: Sash of Ancient Power | 85 | 450 | 
	| 45103 | Pattern: Spellslinger's Slippers | 85 | 450 | 
	| 45104 | Pattern: Cord of the White Dawn | 85 | 450 | 
	| 45105 | Pattern: Savior's Slippers | 85 | 450 | 
	| 45774 | Pattern: Emerald Bag | 78 | 435 | 
	| 47636 | Pattern: Royal Moonshroud Robe | 85 | 450 | 
	| 47637 | Pattern: Royal Moonshroud Bracers | 85 | 450 | 
	| 47638 | Pattern: Merlin's Robe | 85 | 450 | 
	| 47639 | Pattern: Bejeweled Wizard's Bracers | 85 | 450 | 
	| 47654 | Pattern: Bejeweled Wizard's Bracers | 85 | 450 | 
	| 47655 | Pattern: Merlin's Robe | 85 | 450 | 
	| 47656 | Pattern: Royal Moonshroud Bracers | 85 | 450 | 
	| 47657 | Pattern: Royal Moonshroud Robe | 85 | 450 | 
	| 49953 | Pattern: Leggings of Woven Death | 85 | 450 | 
	| 49954 | Pattern: Deathfrost Boots | 85 | 450 | 
	| 49955 | Pattern: Lightweave Leggings | 85 | 450 | 
	| 49956 | Pattern: Sandals of Consecration | 85 | 450 | 
	| 54798 | Pattern: Frosty Flying Carpet | 70 | 425 | 

	</details>
	
	Note: this list excludes Truefaith Vestments 29120 as I'm not sure how it should be counted.
	
	21892, 21893, 21894, 21895, 21896, 21897, 21898, 21899, 21900, 21901, 21902, 21903, 21904, 21905, 21906, 21907, 21908, 21909, 21910, 21911, 21912, 21913, 21914, 21915, 21916, 21917, 21918, 21919, 24292, 24293, 24294, 24295, 24296, 24297, 24298, 24299, 24300, 24301, 24302, 24303, 24304, 24305, 24306, 24307, 24308, 24309, 24310, 24311, 24312, 24313, 24314, 24315, 24316, 30280, 30281, 30282, 30283, 30483, 30833, 30842, 30843, 30844, 32437, 32438, 32439, 32440, 32447, 32752, 32753, 32754, 32755, 35204, 35205, 35206, 35207, 35308, 35309, 35518, 35522, 35525, 35526, 35544, 35548, 35551, 38229, 42172, 42173, 42174, 42175, 42176, 42177, 42178, 42179, 42180, 42181, 42182, 42183, 42184, 42185, 42186, 42187, 42188, 42189, 42190, 42191, 42192, 42193, 42194, 42195, 42196, 42197, 42198, 42199, 42200, 42201, 42202, 43876, 45102, 45103, 45104, 45105, 45774, 47636, 47637, 47638, 47639, 47654, 47655, 47656, 47657, 49953, 49954, 49955, 49956, 54798 
	
	<hr>

- ### Engineering (subclass = 3)
	Vanilla goes up to ilvl 65/300 skill. TBC eng recipes are all through old world lvl range, but new ones are all 61+ and 305+ skill. So just skill >= 305 works.

	```SQL
	SELECT it.entry, it.name, it.ItemLevel, it.RequiredSkillRank
	FROM `item_template` it
	WHERE it.class = 9 AND it.subclass = 3
	AND it.RequiredSkillRank >= 305
	```
	
	<details>
	<summary>Results</summary>
	
	---
	| entry | name | ItemLevel | RequiredSkillRank | 
	| ---: | --- | ---: | ---: | 
	| 23799 | Schematic: Adamantite Rifle | 70 | 350 | 
	| 23800 | Schematic: Felsteel Boomstick | 72 | 360 | 
	| 23802 | Schematic: Ornate Khorium Rifle | 75 | 375 | 
	| 23803 | Schematic: Cogspinner Goggles | 68 | 340 | 
	| 23804 | Schematic: Power Amplification Goggles | 68 | 340 | 
	| 23805 | Schematic: Ultra-Spectropic Detection Goggles | 70 | 350 | 
	| 23806 | Schematic: Hyper-Vision Goggles | 72 | 360 | 
	| 23807 | Schematic: Adamantite Scope | 67 | 335 | 
	| 23808 | Schematic: Khorium Scope | 72 | 360 | 
	| 23809 | Schematic: Stabilized Eternium Scope | 75 | 375 | 
	| 23810 | Schematic: Crashin' Thrashin' Robot | 65 | 325 | 
	| 23811 | Schematic: White Smoke Flare | 67 | 335 | 
	| 23814 | Schematic: Green Smoke Flare | 67 | 335 | 
	| 23815 | Schematic: Adamantite Shell Machine | 67 | 335 | 
	| 23816 | Schematic: Fel Iron Toolbox | 65 | 325 | 
	| 23817 | Schematic: Titanium Toolbox | 75 | 405 | 
	| 23874 | Schematic: Elemental Seaforium Charge | 70 | 350 | 
	| 23882 | Schematic: Critter Enlarger | 65 | 325 | 
	| 23883 | Schematic: Healing Potion Injector | 66 | 330 | 
	| 23884 | Schematic: Mana Potion Injector | 69 | 345 | 
	| 23885 | Schematic: Remote Mail Terminal | 67 | 335 | 
	| 23887 | Schematic: Rocket Boots Xtreme | 71 | 355 | 
	| 23888 | Schematic: Zapthrottle Mote Extractor | 61 | 305 | 
	| 25887 | Schematic: Purple Smoke Flare | 67 | 335 | 
	| 33804 | Schematic: Adamantite Arrow Maker | 67 | 335 | 
	| 34114 | Schematic: Field Repair Bot 110G | 70 | 360 | 
	| 35186 | Schematic: Annihilator Holo-Gogs | 70 | 375 | 
	| 35187 | Schematic: Justicebringer 3000 Specs | 70 | 375 | 
	| 35189 | Schematic: Powerheal 9000 Lens | 70 | 375 | 
	| 35190 | Schematic: Hyper-Magnified Moon Specs | 70 | 375 | 
	| 35191 | Schematic: Wonderheal XT68 Shades | 70 | 375 | 
	| 35192 | Schematic: Primal-Attuned Goggles | 70 | 375 | 
	| 35193 | Schematic: Lightning Etched Specs | 70 | 375 | 
	| 35194 | Schematic: Surestrike Goggles v3.0 | 70 | 375 | 
	| 35195 | Schematic: Mayhem Projection Goggles | 70 | 375 | 
	| 35196 | Schematic: Hard Khorium Goggles | 70 | 375 | 
	| 35197 | Schematic: Quad Deathblow X44 Goggles | 70 | 375 | 
	| 35310 | Schematic: Healing Potion Injector | 66 | 330 | 
	| 35311 | Schematic: Mana Potion Injector | 69 | 345 | 
	| 35582 | Schematic: Rocket Boots Xtreme Lite | 71 | 355 | 
	| 44502 | Schematic: Mechano-hog | 80 | 450 | 
	| 44503 | Schematic: Mekgineer's Chopper | 80 | 450 | 
	| 49050 | Schematic: Jeeves | 80 | 450 | 
	| 52022 | Plans: Shatter Rounds | 85 | 450 | 
	| 52023 | Plans: Iceblade Arrow | 85 | 450 | 
	
	</details>
	
	23799, 23800, 23802, 23803, 23804, 23805, 23806, 23807, 23808, 23809, 23810, 23811, 23814, 23815, 23816, 23817, 23874, 23882, 23883, 23884, 23885, 23887, 23888, 25887, 33804, 34114, 35186, 35187, 35189, 35190, 35191, 35192, 35193, 35194, 35195, 35196, 35197, 35310, 35311, 35582, 44502, 44503, 49050, 52022, 52023 
	
	<hr>
	
- ### Blacksmithing (subclass = 4)
	Vanilla BS recipes go up to ilvl 80/300 skill. TBC recipes starts at ilvl 63/325 skill. So again, >= 325 skill works.

	```SQL
	SELECT it.entry  , it.name, it.ItemLevel, it.RequiredSkillRank
	FROM `item_template` it
	WHERE it.class = 9 AND it.subclass = 4
	AND it.RequiredSkillRank >= 325
	```
	
	<details>
	<summary>Results</summary>
	
	---
	| entry | name | ItemLevel | RequiredSkillRank | 
	| ---: | --- | ---: | ---: | 
	| 23590 | Plans: Adamantite Maul | 65 | 325 | 
	| 23591 | Plans: Adamantite Cleaver | 66 | 330 | 
	| 23592 | Plans: Adamantite Dagger | 66 | 330 | 
	| 23593 | Plans: Adamantite Rapier | 67 | 335 | 
	| 23594 | Plans: Adamantite Plate Bracers | 67 | 335 | 
	| 23595 | Plans: Adamantite Plate Gloves | 67 | 335 | 
	| 23596 | Plans: Adamantite Breastplate | 68 | 340 | 
	| 23597 | Plans: Enchanted Adamantite Belt | 71 | 355 | 
	| 23598 | Plans: Enchanted Adamantite Boots | 71 | 355 | 
	| 23599 | Plans: Enchanted Adamantite Breastplate | 72 | 360 | 
	| 23600 | Plans: Enchanted Adamantite Leggings | 73 | 365 | 
	| 23601 | Plans: Flamebane Bracers | 70 | 350 | 
	| 23602 | Plans: Flamebane Helm | 71 | 355 | 
	| 23603 | Plans: Flamebane Gloves | 72 | 360 | 
	| 23604 | Plans: Flamebane Breastplate | 73 | 365 | 
	| 23605 | Plans: Felsteel Gloves | 72 | 360 | 
	| 23606 | Plans: Felsteel Leggings | 72 | 360 | 
	| 23607 | Plans: Felsteel Helm | 73 | 365 | 
	| 23608 | Plans: Khorium Belt | 72 | 360 | 
	| 23609 | Plans: Khorium Pants | 72 | 360 | 
	| 23610 | Plans: Khorium Boots | 73 | 365 | 
	| 23611 | Plans: Ragesteel Gloves | 73 | 365 | 
	| 23612 | Plans: Ragesteel Helm | 73 | 365 | 
	| 23613 | Plans: Ragesteel Breastplate | 74 | 370 | 
	| 23615 | Plans: Swiftsteel Gloves | 74 | 370 | 
	| 23617 | Plans: Earthpeace Breastplate | 74 | 370 | 
	| 23618 | Plans: Adamantite Sharpening Stone | 70 | 350 | 
	| 23619 | Plans: Felsteel Shield Spike | 72 | 360 | 
	| 23620 | Plans: Felfury Gauntlets | 73 | 365 | 
	| 23621 | Plans: Gauntlets of the Iron Tower | 73 | 365 | 
	| 23622 | Plans: Steelgrip Gauntlets | 73 | 365 | 
	| 23623 | Plans: Storm Helm | 73 | 365 | 
	| 23624 | Plans: Helm of the Stalwart Defender | 73 | 365 | 
	| 23625 | Plans: Oathkeeper's Helm | 73 | 365 | 
	| 23626 | Plans: Black Felsteel Bracers | 73 | 365 | 
	| 23627 | Plans: Bracers of the Green Fortress | 73 | 365 | 
	| 23628 | Plans: Blessed Bracers | 73 | 365 | 
	| 23629 | Plans: Felsteel Longblade | 73 | 365 | 
	| 23630 | Plans: Khorium Champion | 73 | 365 | 
	| 23631 | Plans: Fel Edged Battleaxe | 73 | 365 | 
	| 23632 | Plans: Felsteel Reaper | 73 | 365 | 
	| 23633 | Plans: Runic Hammer | 73 | 365 | 
	| 23634 | Plans: Fel Hardened Maul | 73 | 365 | 
	| 23635 | Plans: Eternium Runed Blade | 73 | 365 | 
	| 23636 | Plans: Dirge | 73 | 365 | 
	| 23637 | Plans: Hand of Eternity | 73 | 365 | 
	| 23638 | Plans: Lesser Ward of Shielding | 68 | 340 | 
	| 23639 | Plans: Greater Ward of Shielding | 75 | 375 | 
	| 24002 | Plans: Felsteel Shield Spike | 72 | 360 | 
	| 25526 | Plans: Greater Rune of Warding | 70 | 350 | 
	| 25846 | Plans: Adamantite Rod | 70 | 350 | 
	| 25847 | Plans: Eternium Rod | 75 | 360 | 
	| 28632 | Plans: Adamantite Weightstone | 70 | 350 | 
	| 30321 | Plans: Belt of the Guardian | 75 | 375 | 
	| 30322 | Plans: Red Belt of Battle | 75 | 375 | 
	| 30323 | Plans: Boots of the Protector | 75 | 375 | 
	| 30324 | Plans: Red Havoc Boots | 75 | 375 | 
	| 31390 | Plans: Wildguard Breastplate | 75 | 375 | 
	| 31391 | Plans: Wildguard Leggings | 75 | 375 | 
	| 31392 | Plans: Wildguard Helm | 75 | 375 | 
	| 31393 | Plans: Iceguard Breastplate | 75 | 375 | 
	| 31394 | Plans: Iceguard Leggings | 75 | 375 | 
	| 31395 | Plans: Iceguard Helm | 75 | 375 | 
	| 32441 | Plans: Shadesteel Sabots | 75 | 375 | 
	| 32442 | Plans: Shadesteel Bracers | 75 | 375 | 
	| 32443 | Plans: Shadesteel Greaves | 75 | 375 | 
	| 32444 | Plans: Shadesteel Girdle | 75 | 375 | 
	| 32736 | Plans: Swiftsteel Bracers | 70 | 375 | 
	| 32737 | Plans: Swiftsteel Shoulders | 70 | 375 | 
	| 32738 | Plans: Dawnsteel Bracers | 70 | 375 | 
	| 32739 | Plans: Dawnsteel Shoulders | 70 | 375 | 
	| 33174 | Plans: Ragesteel Shoulders | 73 | 365 | 
	| 33186 | Plans: Adamantite Weapon Chain | 63 | 335 | 
	| 33954 | Plans: Hammer of Righteous Might | 73 | 365 | 
	| 35208 | Plans: Sunblessed Gauntlets | 70 | 365 | 
	| 35209 | Plans: Hard Khorium Battlefists | 70 | 365 | 
	| 35210 | Plans: Sunblessed Breastplate | 70 | 365 | 
	| 35211 | Plans: Hard Khorium Battleplate | 70 | 365 | 
	| 35296 | Plans: Adamantite Weapon Chain | 63 | 335 | 
	| 35529 | Plans: Dawnsteel Bracers | 70 | 375 | 
	| 35530 | Plans: Dawnsteel Shoulders | 70 | 375 | 
	| 35531 | Plans: Swiftsteel Bracers | 70 | 375 | 
	| 35532 | Plans: Swiftsteel Shoulders | 70 | 375 | 
	| 35553 | Plans: Hard Khorium Battlefists | 70 | 365 | 
	| 35555 | Plans: Sunblessed Breastplate | 70 | 365 | 
	| 41120 | Plans: Reinforced Cobalt Legplates | 75 | 375 | 
	| 41122 | Plans: Reinforced Cobalt Chestpiece | 75 | 375 | 
	| 41123 | Plans: Reinforced Cobalt Helm | 75 | 375 | 
	| 41124 | Plans: Reinforced Cobalt Shoulders | 75 | 375 | 
	| 44937 | Plans: Titanium Plating | 80 | 450 | 
	| 44938 | Plans: Titanium Plating | 80 | 450 | 
	| 45088 | Plans: Belt of the Titans | 85 | 450 | 
	| 45089 | Plans: Battlelord's Plate Boots | 85 | 450 | 
	| 45090 | Plans: Plate Girdle of Righteousness | 85 | 450 | 
	| 45091 | Plans: Treads of Destiny | 85 | 450 | 
	| 45092 | Plans: Indestructible Plate Girdle | 85 | 450 | 
	| 45093 | Plans: Spiked Deathdealers | 85 | 450 | 
	| 47622 | Plans: Breastplate of the White Knight | 85 | 450 | 
	| 47623 | Plans: Saronite Swordbreakers | 85 | 450 | 
	| 47624 | Plans: Titanium Razorplate | 85 | 450 | 
	| 47625 | Plans: Titanium Spikeguards | 85 | 450 | 
	| 47626 | Plans: Sunforged Breastplate | 85 | 450 | 
	| 47627 | Plans: Sunforged Bracers | 85 | 450 | 
	| 47640 | Plans: Breastplate of the White Knight | 85 | 450 | 
	| 47641 | Plans: Saronite Swordbreakers | 85 | 450 | 
	| 47642 | Plans: Sunforged Bracers | 85 | 450 | 
	| 47643 | Plans: Sunforged Breastplate | 85 | 450 | 
	| 47644 | Plans: Titanium Razorplate | 85 | 450 | 
	| 47645 | Plans: Titanium Spikeguards | 85 | 450 | 
	| 49969 | Plans: Puresteel Legplates | 85 | 450 | 
	| 49970 | Plans: Protectors of Life | 85 | 450 | 
	| 49971 | Plans: Legplates of Painful Death | 85 | 450 | 
	| 49972 | Plans: Hellfrozen Bonegrinders | 85 | 450 | 
	| 49973 | Plans: Pillars of Might | 85 | 450 | 
	| 49974 | Plans: Boots of Kingly Upheaval | 85 | 450 | 

	</details>
	
	23590, 23591, 23592, 23593, 23594, 23595, 23596, 23597, 23598, 23599, 23600, 23601, 23602, 23603, 23604, 23605, 23606, 23607, 23608, 23609, 23610, 23611, 23612, 23613, 23615, 23617, 23618, 23619, 23620, 23621, 23622, 23623, 23624, 23625, 23626, 23627, 23628, 23629, 23630, 23631, 23632, 23633, 23634, 23635, 23636, 23637, 23638, 23639, 24002, 25526, 25846, 25847, 28632, 30321, 30322, 30323, 30324, 31390, 31391, 31392, 31393, 31394, 31395, 32441, 32442, 32443, 32444, 32736, 32737, 32738, 32739, 33174, 33186, 33954, 35208, 35209, 35210, 35211, 35296, 35529, 35530, 35531, 35532, 35553, 35555, 41120, 41122, 41123, 41124, 44937, 44938, 45088, 45089, 45090, 45091, 45092, 45093, 47622, 47623, 47624, 47625, 47626, 47627, 47640, 47641, 47642, 47643, 47644, 47645, 49969, 49970, 49971, 49972, 49973, 49974
	
	<hr>
	
- ### Cooking (subclass = 5)
	Vanilla recipes go up to ilvl 60/300 skill. (only 1 though, "Recipe: Dirge's Kickin' Chimaerok Chops" 21025.) TBC cooking recipes are all through the old world level range, but have some overlap at lvl 60, with 8 more 60/300 skill recipes. Lowest TBC ID is 27684. Easiest to just take >= 60 ilvl and ID > 22000 - verified no TBC cooking recipes have a lower ID than this.

	```SQL
	SELECT it.entry , it.name, it.ItemLevel, it.RequiredSkillRank
	FROM `item_template` it
	WHERE it.class = 9 AND it.subclass = 5
	AND it.itemlevel >= 60 AND it.entry >= 22000
	```
	
	<details>
	<summary>Results</summary>
	
	---
	| entry | name | ItemLevel | RequiredSkillRank | 
	| ---: | --- | ---: | ---: | 
	| 27684 | Recipe: Buzzard Bites | 60 | 300 | 
	| 27688 | Recipe: Ravager Dog | 60 | 300 | 
	| 27689 | Recipe: Sporeling Snack | 62 | 310 | 
	| 27690 | Recipe: Blackened Basilisk | 62 | 315 | 
	| 27691 | Recipe: Roasted Clefthoof | 65 | 325 | 
	| 27692 | Recipe: Warp Burger | 65 | 325 | 
	| 27693 | Recipe: Talbuk Steak | 65 | 325 | 
	| 27694 | Recipe: Blackened Trout | 60 | 300 | 
	| 27695 | Recipe: Feltail Delight | 60 | 300 | 
	| 27696 | Recipe: Blackened Sporefish | 62 | 310 | 
	| 27697 | Recipe: Grilled Mudfish | 64 | 320 | 
	| 27698 | Recipe: Poached Bluefish | 64 | 320 | 
	| 27699 | Recipe: Golden Fish Sticks | 65 | 325 | 
	| 27700 | Recipe: Spicy Crawdad | 65 | 350 | 
	| 30156 | Recipe: Clam Bar | 60 | 300 | 
	| 31674 | Recipe: Crunchy Serpent | 67 | 335 | 
	| 31675 | Recipe: Mok'Nathal Shortribs | 67 | 335 | 
	| 33869 | Recipe: Broiled Bloodfin | 60 | 300 | 
	| 33870 | Recipe: Skullfish Soup | 60 | 325 | 
	| 33871 | Recipe: Stormchops | 60 | 300 | 
	| 33873 | Recipe: Spicy Hot Talbuk | 60 | 325 | 
	| 33875 | Recipe: Kibler's Bits | 60 | 300 | 
	| 34126 | Recipe: Shoveltusk Soup | 70 | 350 | 
	| 39644 | Recipe: Kungaloosh | 75 | 375 | 
	| 39692 | Recipe: Succulent Orca Stew | 70 | 350 | 
	| 43017 | Recipe: Fish Feast | 75 | 450 | 
	| 43018 | Recipe: Mega Mammoth Meal | 75 | 400 | 
	| 43019 | Recipe: Tender Shoveltusk Steak | 75 | 400 | 
	| 43020 | Recipe: Spiced Worm Burger | 75 | 400 | 
	| 43021 | Recipe: Very Burnt Worg | 75 | 400 | 
	| 43022 | Recipe: Mighty Rhino Dogs | 75 | 400 | 
	| 43023 | Recipe: Poached Northern Sculpin | 75 | 400 | 
	| 43024 | Recipe: Firecracker Salmon | 75 | 400 | 
	| 43025 | Recipe: Spicy Blue Nettlefish | 75 | 400 | 
	| 43026 | Recipe: Imperial Manta Steak | 75 | 400 | 
	| 43027 | Recipe: Spicy Fried Herring | 75 | 400 | 
	| 43028 | Recipe: Rhinolicious Wormsteak | 75 | 400 | 
	| 43029 | Recipe: Critter Bites | 75 | 400 | 
	| 43030 | Recipe: Hearty Rhino | 75 | 400 | 
	| 43031 | Recipe: Snapper Extreme | 75 | 400 | 
	| 43032 | Recipe: Blackened Worg Steak | 75 | 400 | 
	| 43033 | Recipe: Cuttlesteak | 75 | 400 | 
	| 43034 | Recipe: Spiced Mammoth Treats | 75 | 400 | 
	| 43035 | Recipe: Blackened Dragonfin | 75 | 400 | 
	| 43036 | Recipe: Dragonfin Filet | 75 | 400 | 
	| 43037 | Recipe: Tracker Snacks | 75 | 400 | 
	| 43505 | Recipe: Gigantic Feast | 75 | 425 | 
	| 43506 | Recipe: Small Feast | 75 | 425 | 
	| 43507 | Recipe: Tasty Cupcake | 75 | 350 | 
	| 43508 | Recipe: Last Week's Mammoth | 75 | 350 | 
	| 43509 | Recipe: Bad Clams | 75 | 350 | 
	| 43510 | Recipe: Haunted Herring | 75 | 350 | 
	| 44954 | Recipe: Worg Tartare | 75 | 400 | 
	
	</details>
	
	27684, 27688, 27689, 27690, 27691, 27692, 27693, 27694, 27695, 27696, 27697, 27698, 27699, 27700, 30156, 31674, 31675, 33869, 33870, 33871, 33873, 33875, 34126, 39644, 39692, 43017, 43018, 43019, 43020, 43021, 43022, 43023, 43024, 43025, 43026, 43027, 43028, 43029, 43030, 43031, 43032, 43033, 43034, 43035, 43036, 43037, 43505, 43506, 43507, 43508, 43509, 43510, 44954
	
	<hr>
	
- ### Alchemy (subclass = 6)
	Vanilla goes up to 60/300 skill, 5 recipes from scholo/UBRS/BRD, etc and 1 ilvl 70, Recipe: Alchemist's Stone 13517, a TBC item added in vanilla (sold in Shattrath). The exact same 5 recipes are then duplicated in TBC as rep items. Highest vanilla 60/300 recipe index is 20761. The 5 TBC recipes at 60 are all in the 31K range, and other TBC recipes are all 61/305 and up. Multiple other TBC 61+ recipes have a 22.9K index. So query is

	```SQL
	SELECT it.entry, it.name, it.ItemLevel, it.RequiredSkillRank 
	FROM `item_template` it 
	WHERE it.class = 9 AND it.subclass = 6 
	AND it.ItemLevel >= 60 AND it.entry > 21000 OR it.entry = 13517
	```
	
	<details>
	<summary>Results</summary>
	
	---
	| entry | name | ItemLevel | RequiredSkillRank | 
	| ---: | --- | ---: | ---: | 
	| 13517 | Recipe: Alchemist's Stone | 70 | 350 | 
	| 22900 | Recipe: Elixir of Camouflage | 61 | 305 | 
	| 22901 | Recipe: Sneaking Potion | 63 | 315 | 
	| 22902 | Recipe: Elixir of Major Frost Power | 64 | 320 | 
	| 22903 | Recipe: Insane Strength Potion | 64 | 320 | 
	| 22904 | Recipe: Elixir of the Searching Eye | 65 | 325 | 
	| 22905 | Recipe: Elixir of Major Agility | 66 | 330 | 
	| 22906 | Recipe: Shrouding Potion | 67 | 335 | 
	| 22907 | Recipe: Super Mana Potion | 68 | 340 | 
	| 22908 | Recipe: Elixir of Major Firepower | 69 | 345 | 
	| 22909 | Recipe: Elixir of Major Defense | 69 | 345 | 
	| 22910 | Recipe: Elixir of Major Shadow Power | 70 | 350 | 
	| 22911 | Recipe: Major Dreamless Sleep Potion | 70 | 350 | 
	| 22912 | Recipe: Heroic Potion | 70 | 350 | 
	| 22913 | Recipe: Haste Potion | 70 | 350 | 
	| 22914 | Recipe: Destruction Potion | 70 | 350 | 
	| 22915 | Recipe: Transmute Primal Air to Fire | 70 | 350 | 
	| 22916 | Recipe: Transmute Primal Earth to Water | 70 | 350 | 
	| 22917 | Recipe: Transmute Primal Fire to Earth | 70 | 350 | 
	| 22918 | Recipe: Transmute Primal Water to Air | 70 | 350 | 
	| 22919 | Recipe: Elixir of Major Mageblood | 71 | 355 | 
	| 22920 | Recipe: Major Fire Protection Potion | 72 | 360 | 
	| 22921 | Recipe: Major Frost Protection Potion | 72 | 360 | 
	| 22922 | Recipe: Major Nature Protection Potion | 72 | 360 | 
	| 22923 | Recipe: Major Arcane Protection Potion | 72 | 360 | 
	| 22924 | Recipe: Major Shadow Protection Potion | 72 | 360 | 
	| 22925 | Recipe: Major Holy Protection Potion | 72 | 360 | 
	| 22926 | Recipe: Elixir of Empowerment | 73 | 365 | 
	| 22927 | Recipe: Ironshield Potion | 73 | 365 | 
	| 23574 | Recipe: Transmute Primal Might | 70 | 350 | 
	| 24001 | Recipe: Elixir of Major Agility | 66 | 330 | 
	| 25869 | Recipe: Transmute Earthstorm Diamond | 70 | 350 | 
	| 25870 | Recipe: Transmute Skyfire Diamond | 70 | 350 | 
	| 29232 | Recipe: Transmute Skyfire Diamond | 70 | 350 | 
	| 30443 | Recipe: Transmute Primal Fire to Earth | 70 | 350 | 
	| 31354 | Recipe: Flask of the Titans | 60 | 300 | 
	| 31355 | Recipe: Flask of Supreme Power | 60 | 300 | 
	| 31356 | Recipe: Flask of Distilled Wisdom | 60 | 300 | 
	| 31357 | Recipe: Flask of Chromatic Resistance | 60 | 300 | 
	| 31680 | Recipe: Fel Strength Elixir | 67 | 335 | 
	| 31681 | Recipe: Fel Regeneration Potion | 69 | 345 | 
	| 31682 | Recipe: Fel Mana Potion | 72 | 360 | 
	| 32070 | Recipe: Earthen Elixir | 64 | 320 | 
	| 32071 | Recipe: Elixir of Ironskin | 66 | 330 | 
	| 33209 | Recipe: Flask of Chromatic Wonder | 70 | 375 | 
	| 35294 | Recipe: Elixir of Empowerment | 73 | 365 | 
	| 35295 | Recipe: Haste Potion | 70 | 350 | 
	| 35752 | Recipe: Guardian's Alchemist Stone | 70 | 375 | 
	| 35753 | Recipe: Sorcerer's Alchemist Stone | 70 | 375 | 
	| 35754 | Recipe: Redeemer's Alchemist Stone | 70 | 375 | 
	| 35755 | Recipe: Assassin's Alchemist Stone | 70 | 375 | 
	| 44564 | Recipe: Mighty Arcane Protection Potion | 75 | 400 | 
	| 44565 | Recipe: Mighty Fire Protection Potion | 75 | 400 | 
	| 44566 | Recipe: Mighty Frost Protection Potion | 75 | 400 | 
	| 44567 | Recipe: Mighty Nature Protection Potion | 75 | 400 | 
	| 44568 | Recipe: Mighty Shadow Protection Potion | 75 | 400 | 
	| 47507 | Recipe: Flask of the North | 80 | 425 | 

	</details>
	
	13517, 22900, 22901, 22902, 22903, 22904, 22905, 22906, 22907, 22908, 22909, 22910, 22911, 22912, 22913, 22914, 22915, 22916, 22917, 22918, 22919, 22920, 22921, 22922, 22923, 22924, 22925, 22926, 22927, 23574, 24001, 25869, 25870, 29232, 30443, 31354, 31355, 31356, 31357, 31680, 31681, 31682, 32070, 32071, 33209, 35294, 35295, 35752, 35753, 35754, 35755, 44564, 44565, 44566, 44567, 44568, 47507
	
	<hr>
	
- ### First aid (subclass = 7)
	Vanilla goes up to 60/300 with crystal-infused bandages, which aren't available in game. TBC starts at 60/300, so a simple >=60 ilvl should be fine.
	
	```SQL
	SELECT it.entry  , it.name, it.ItemLevel, it.RequiredSkillRank 
	FROM `item_template` it 
	WHERE it.class = 9 AND it.subclass = 7
	AND it.ItemLevel >= 60
	```
	
	<details>
	<summary>Results</summary>
	
	---
	| entry | name | ItemLevel | RequiredSkillRank | 
	| ---: | --- | ---: | ---: | 
	| 21992 | Manual: Netherweave Bandage | 64 | 330 | 
	| 21993 | Manual: Heavy Netherweave Bandage | 70 | 360 | 
	| 22012 | Master First Aid - Doctor in the House | 60 | 300 | 
	| 39152 | Manual: Heavy Frostweave Bandage | 80 | 400 | 
	| 39153 | Manual: Dense Frostweave Bandage | 85 | 450 | 

	</details>
	
	21992, 21993, 22012, 39152, 39153
	
	<hr>
	
- ### Enchanting (subclass = 8)
	Vanilla recipes go up to ilvl 70, skill 300. TBC recipes start at ilvl 61 but all have skill >= 305. So skill >= 305 is enough.

	```SQL
	SELECT it.entry, it.name, it.ItemLevel, it.RequiredSkillRank 
	FROM `item_template` it 
	WHERE it.class = 9 AND it.subclass = 8
	AND it.RequiredSkillRank >= 305
	```
	
	<details>
	<summary>Results</summary>

	---
	| entry | name | ItemLevel | RequiredSkillRank | 
	| ---: | --- | ---: | ---: | 
	| 22530 | Formula: Enchant Bracer - Major Defense | 64 | 320 | 
	| 22531 | Formula: Enchant Bracer - Superior Healing | 65 | 325 | 
	| 22532 | Formula: Enchant Bracer - Restore Mana Prime | 67 | 335 | 
	| 22533 | Formula: Enchant Bracer - Fortitude | 70 | 350 | 
	| 22534 | Formula: Enchant Bracer - Spellpower | 72 | 360 | 
	| 22535 | Formula: Enchant Ring - Striking | 72 | 360 | 
	| 22536 | Formula: Enchant Ring - Spellpower | 72 | 360 | 
	| 22537 | Formula: Enchant Ring - Healing Power | 74 | 370 | 
	| 22538 | Formula: Enchant Ring - Stats | 75 | 375 | 
	| 22539 | Formula: Enchant Shield - Intellect | 65 | 325 | 
	| 22540 | Formula: Enchant Shield - Shield Block | 68 | 340 | 
	| 22541 | Formula: Enchant Shield - Resistance | 72 | 360 | 
	| 22542 | Formula: Enchant Boots - Vitality | 61 | 305 | 
	| 22543 | Formula: Enchant Boots - Fortitude | 64 | 320 | 
	| 22544 | Formula: Enchant Boots - Dexterity | 68 | 340 | 
	| 22545 | Formula: Enchant Boots - Surefooted | 74 | 370 | 
	| 22547 | Formula: Enchant Chest - Exceptional Stats | 69 | 345 | 
	| 22548 | Formula: Enchant Cloak - Major Resistance | 66 | 330 | 
	| 22551 | Formula: Enchant Weapon - Major Intellect | 68 | 340 | 
	| 22552 | Formula: Enchant Weapon - Major Striking | 68 | 340 | 
	| 22553 | Formula: Enchant Weapon - Potency | 70 | 350 | 
	| 22554 | Formula: Enchant 2H Weapon - Savagery | 70 | 350 | 
	| 22555 | Formula: Enchant Weapon - Major Spellpower | 70 | 350 | 
	| 22556 | Formula: Enchant 2H Weapon - Major Agility | 72 | 360 | 
	| 22557 | Formula: Enchant Weapon - Battlemaster | 72 | 360 | 
	| 22558 | Formula: Enchant Weapon - Spellsurge | 72 | 360 | 
	| 22559 | Formula: Enchant Weapon - Mongoose | 75 | 375 | 
	| 22560 | Formula: Enchant Weapon - Sunfire | 75 | 375 | 
	| 22561 | Formula: Enchant Weapon - Soulfrost | 75 | 375 | 
	| 22562 | Formula: Superior Mana Oil | 62 | 310 | 
	| 22563 | Formula: Superior Wizard Oil | 68 | 340 | 
	| 22565 | Formula: Large Prismatic Shard | 67 | 335 | 
	| 24000 | Formula: Enchant Bracer - Superior Healing | 65 | 325 | 
	| 24003 | Formula: Enchant Chest - Exceptional Stats | 69 | 345 | 
	| 25848 | Formula: Runed Adamantite Rod | 70 | 350 | 
	| 25849 | Formula: Runed Eternium Rod | 75 | 375 | 
	| 28270 | Formula: Enchant Chest - Major Resilience | 69 | 345 | 
	| 28271 | Formula: Enchant Gloves - Precise Strikes | 72 | 360 | 
	| 28272 | Formula: Enchant Gloves - Major Spellpower | 72 | 360 | 
	| 28273 | Formula: Enchant Gloves - Major Healing | 70 | 350 | 
	| 28274 | Formula: Enchant Cloak - Spell Penetration | 65 | 325 | 
	| 28276 | Formula: Enchant Cloak - Greater Arcane Resistance | 70 | 350 | 
	| 28277 | Formula: Enchant Cloak - Greater Shadow Resistance | 70 | 350 | 
	| 28279 | Formula: Enchant Boots - Cat's Swiftness | 72 | 360 | 
	| 28280 | Formula: Enchant Boots - Boar's Speed | 72 | 360 | 
	| 28281 | Formula: Enchant Weapon - Major Healing | 70 | 350 | 
	| 28282 | Formula: Enchant Shield - Major Stamina | 65 | 325 | 
	| 33165 | Formula: Enchant Weapon - Greater Agility | 70 | 350 | 
	| 33307 | Formula: Enchant Weapon - Executioner | 75 | 375 | 
	| 34872 | Formula: Void Shatter | 72 | 375 | 
	| 35297 | Formula: Enchant Boots - Boar's Speed | 72 | 360 | 
	| 35298 | Formula: Enchant Boots - Vitality | 61 | 305 | 
	| 35299 | Formula: Enchant Boots - Cat's Swiftness | 72 | 360 | 
	| 35498 | Formula: Enchant Weapon - Deathfrost | 75 | 350 | 
	| 35500 | Formula: Enchant Chest - Defense | 70 | 360 | 
	| 35756 | Formula: Enchant Cloak - Steelweave | 70 | 375 | 
	| 37326 | Formula: Enchant Bracer - Major Spirit | 80 | 400 | 
	| 37329 | Formula: Enchant Weapon - Exceptional Spirit | 80 | 400 | 
	| 37330 | Formula: Enchant Cloak - Superior Arcane Resistance | 80 | 400 | 
	| 37331 | Formula: Enchant Cloak - Superior Fire Resistance | 80 | 400 | 
	| 37332 | Formula: Enchant Cloak - Superior Frost Resistance | 80 | 400 | 
	| 37333 | Formula: Enchant Cloak - Superior Nature Resistance | 80 | 400 | 
	| 37334 | Formula: Enchant Cloak - Superior Shadow Resistance | 80 | 400 | 
	| 37335 | Formula: Enchant Cloak - Superior Agility | 80 | 400 | 
	| 37336 | Formula: Enchant Chest - Greater Dodge | 80 | 400 | 
	| 37337 | Formula: Enchant Bracer - Greater Stats | 80 | 400 | 
	| 37338 | Formula: Enchant Weapon - Greater Savagery | 82 | 410 | 
	| 37339 | Formula: Enchant Weapon - Giant Slayer | 82 | 430 | 
	| 37340 | Formula: Enchant Chest - Exceptional Resilience | 82 | 410 | 
	| 37343 | Formula: Enchant Weapon - Exceptional Agility | 84 | 420 | 
	| 37344 | Formula: Enchant Weapon - Icebreaker | 84 | 425 | 
	| 37345 | Formula: Enchant Gloves - Greater Assault | 84 | 420 | 
	| 37346 | Formula: Enchant Bracer - Expertise | 84 | 420 | 
	| 37347 | Formula: Enchant Cloak - Titanweave | 85 | 435 | 
	| 37348 | Formula: Enchant Cloak - Haste | 85 | 425 | 
	| 37349 | Formula: Enchant Cloak - Shadow Armor | 85 | 440 | 
	| 44471 | Formula: Enchant Cloak - Mighty Armor | 70 | 430 | 
	| 44472 | Formula: Enchant Cloak - Greater Speed | 70 | 430 | 
	| 44473 | Formula: Enchant Weapon - Scourgebane | 70 | 430 | 
	| 44483 | Formula: Enchant 2H Weapon - Massacre | 82 | 430 | 
	| 44484 | Formula: Enchant Bracers - Greater Assault | 82 | 430 | 
	| 44485 | Formula: Enchant Gloves - Armsman | 85 | 435 | 
	| 44486 | Formula: Enchant Weapon - Superior Potency | 82 | 435 | 
	| 44487 | Formula: Enchant Weapon - Mighty Spellpower | 82 | 435 | 
	| 44488 | Formula: Enchant Cloak - Wisdom | 85 | 440 | 
	| 44489 | Formula: Enchant Chest - Powerful Stats | 85 | 440 | 
	| 44490 | Formula: Enchant Boots - Greater Assault | 85 | 440 | 
	| 44491 | Formula: Enchant Boots - Tuskarr's Vitality | 85 | 440 | 
	| 44492 | Formula: Enchant Weapon - Berserking | 82 | 440 | 
	| 44494 | Formula: Enchant Weapon - Lifeward | 82 | 425 | 
	| 44495 | Formula: Enchant Weapon - Black Magic | 82 | 440 | 
	| 44496 | Formula: Enchant Weapon - Accuracy | 82 | 440 | 
	| 44498 | Formula: Enchant Bracer - Superior Spellpower | 85 | 440 | 
	| 44944 | Formula: Enchant Bracer - Major Stamina | 85 | 450 | 
	| 44945 | Formula: Enchant Weapon - Titanguard | 85 | 450 | 
	| 45059 | Formula: Enchant Staff - Greater Spellpower | 85 | 450 | 
	| 46027 | Formula: Enchant Weapon - Blade Ward | 75 | 450 | 
	| 46348 | Formula: Enchant Weapon - Blood Draining | 75 | 450 | 
	| 50406 | Formula: Enchant Gloves - Angler | 80 | 375 | 

	</details>
	
	22530, 22531, 22532, 22533, 22534, 22535, 22536, 22537, 22538, 22539, 22540, 22541, 22542, 22543, 22544, 22545, 22547, 22548, 22551, 22552, 22553, 22554, 22555, 22556, 22557, 22558, 22559, 22560, 22561, 22562, 22563, 22565, 24000, 24003, 25848, 25849, 28270, 28271, 28272, 28273, 28274, 28276, 28277, 28279, 28280, 28281, 28282, 33165, 33307, 34872, 35297, 35298, 35299, 35498, 35500, 35756, 37326, 37329, 37330, 37331, 37332, 37333, 37334, 37335, 37336, 37337, 37338, 37339, 37340, 37343, 37344, 37345, 37346, 37347, 37348, 37349, 44471, 44472, 44473, 44483, 44484, 44485, 44486, 44487, 44488, 44489, 44490, 44491, 44492, 44494, 44495, 44496, 44498, 44944, 44945, 45059, 46027, 46348, 50406
	
	<hr>
	
- ### Fishing (subclass = 9)
	No vanilla recipes in the 55+ range. 1 TBC recipe (ilvl 55/skill 275) sold in Zangarmarsh, ID = 27532.

	```SQL
	SELECT it.entry , it.name, it.ItemLevel, it.RequiredSkillRank 
	FROM `item_template` it 
	WHERE it.class = 9 AND it.subclass = 9
	AND it.ItemLevel >= 55
	```
	
	<details>
	<summary>Results</summary>
	
	---
	| entry | name | ItemLevel | RequiredSkillRank | 
	| ---: | --- | ---: | ---: | 
	| 27532 | Master Fishing - The Art of Angling | 55 | 275 | 
	| 46055 | Grand Master Fishing - Deep Sea Adventures | 70 | 275 | 

	</details>
	
	27532, 46055
	
	<hr>
	
- ### Jewelcrafting (subclass = 10)
	No vanilla JC designs for obvious reasons. TBC added recipes at all level ranges, going as high as 2 x ilvl 60/300 recipes in UBRS/BRD. Outlands JC recipes also start at 60/300 and share same index range as old world. Best approach is just take >= ilvl 60/skill 300 and substract the 2 old world 60s, Design: Black Diamond Crab 21955 and Design: Dark Iron Scorpid 21956. ItemID 21957 is breakpoint:

	```SQL
	SELECT it.entry, it.name, it.ItemLevel, it.RequiredSkillRank 
	FROM item_template it 
	WHERE it.class = 9 AND it.subclass = 10 
	AND it.ItemLevel >= 60 AND it.RequiredSkillRank >= 300 AND it.entry >= 21957
	```
	
	<details>
	<summary>Results</summary>
	
	---
	| entry | name | ItemLevel | RequiredSkillRank | 
	| ---: | --- | ---: | ---: | 
	| 21957 | Design: Necklace of the Diamond Tower | 61 | 305 | 
	| 23130 | Design: Teardrop Blood Garnet | 60 | 300 | 
	| 23131 | Design: Bold Blood Garnet | 61 | 305 | 
	| 23133 | Design: Runed Blood Garnet | 63 | 315 | 
	| 23134 | Design: Delicate Blood Garnet | 65 | 325 | 
	| 23135 | Design: Inscribed Flame Spessarite | 60 | 300 | 
	| 23136 | Design: Luminous Flame Spessarite | 61 | 305 | 
	| 23137 | Design: Glinting Flame Spessarite | 63 | 315 | 
	| 23138 | Design: Potent Flame Spessarite | 65 | 325 | 
	| 23140 | Design: Radiant Deep Peridot | 60 | 300 | 
	| 23141 | Design: Jagged Deep Peridot | 61 | 305 | 
	| 23142 | Design: Enduring Deep Peridot | 63 | 315 | 
	| 23143 | Design: Dazzling Deep Peridot | 65 | 325 | 
	| 23144 | Design: Glowing Shadow Draenite | 60 | 300 | 
	| 23145 | Design: Royal Shadow Draenite | 61 | 305 | 
	| 23146 | Design: Shifting Shadow Draenite | 63 | 315 | 
	| 23147 | Design: Sovereign Shadow Draenite | 65 | 325 | 
	| 23148 | Design: Brilliant Golden Draenite | 60 | 300 | 
	| 23149 | Design: Gleaming Golden Draenite | 61 | 305 | 
	| 23150 | Design: Thick Golden Draenite | 63 | 315 | 
	| 23151 | Design: Rigid Golden Draenite | 65 | 325 | 
	| 23152 | Design: Solid Azure Moonstone | 60 | 300 | 
	| 23153 | Design: Sparkling Azure Moonstone | 61 | 305 | 
	| 23154 | Design: Stormy Azure Moonstone | 63 | 315 | 
	| 23155 | Design: Lustrous Azure Moonstone | 65 | 325 | 
	| 24158 | Design: Khorium Band of Shadows | 70 | 350 | 
	| 24159 | Design: Khorium Band of Frost | 71 | 355 | 
	| 24160 | Design: Khorium Inferno Band | 71 | 355 | 
	| 24161 | Design: Khorium Band of Leaves | 72 | 360 | 
	| 24162 | Design: Arcane Khorium Band | 73 | 365 | 
	| 24163 | Design: Heavy Felsteel Ring | 69 | 345 | 
	| 24164 | Design: Delicate Eternium Ring | 71 | 355 | 
	| 24165 | Design: Blazing Eternium Band | 73 | 365 | 
	| 24166 | Design: Thick Felsteel Necklace | 71 | 355 | 
	| 24167 | Design: Living Ruby Pendant | 71 | 355 | 
	| 24168 | Design: Braided Eternium Chain | 72 | 360 | 
	| 24169 | Design: Eye of the Night | 72 | 360 | 
	| 24170 | Design: Embrace of the Dawn | 73 | 365 | 
	| 24171 | Design: Chain of the Twilight Owl | 73 | 365 | 
	| 24172 | Design: Coronet of Verdant Flame | 74 | 370 | 
	| 24173 | Design: Circlet of Arcane Might | 74 | 370 | 
	| 24174 | Design: Pendant of Frozen Flame | 72 | 360 | 
	| 24175 | Design: Pendant of Thawing | 72 | 360 | 
	| 24176 | Design: Pendant of Withering | 72 | 360 | 
	| 24177 | Design: Pendant of Shadow's End | 72 | 360 | 
	| 24178 | Design: Pendant of the Null Rune | 72 | 360 | 
	| 24179 | Design: Felsteel Boar | 74 | 370 | 
	| 24180 | Design: Dawnstone Crab | 74 | 370 | 
	| 24181 | Design: Living Ruby Serpent | 74 | 370 | 
	| 24182 | Design: Talasite Owl | 74 | 370 | 
	| 24183 | Design: Nightseye Panther | 74 | 370 | 
	| 24192 | Design: Bright Living Ruby | 70 | 350 | 
	| 24193 | Design: Bold Living Ruby | 70 | 350 | 
	| 24194 | Design: Delicate Living Ruby | 70 | 350 | 
	| 24195 | Design: Teardrop Living Ruby | 70 | 350 | 
	| 24196 | Design: Runed Living Ruby | 70 | 350 | 
	| 24197 | Design: Subtle Living Ruby | 70 | 350 | 
	| 24198 | Design: Flashing Living Ruby | 70 | 350 | 
	| 24199 | Design: Solid Star of Elune | 70 | 350 | 
	| 24200 | Design: Sparkling Star of Elune | 70 | 350 | 
	| 24201 | Design: Lustrous Star of Elune | 70 | 350 | 
	| 24202 | Design: Stormy Star of Elune | 70 | 350 | 
	| 24203 | Design: Brilliant Dawnstone | 70 | 350 | 
	| 24204 | Design: Smooth Dawnstone | 70 | 350 | 
	| 24205 | Design: Rigid Dawnstone | 70 | 350 | 
	| 24206 | Design: Gleaming Dawnstone | 70 | 350 | 
	| 24207 | Design: Thick Dawnstone | 70 | 350 | 
	| 24208 | Design: Mystic Dawnstone | 70 | 350 | 
	| 24209 | Design: Sovereign Nightseye | 70 | 350 | 
	| 24210 | Design: Shifting Nightseye | 70 | 350 | 
	| 24211 | Design: Glowing Nightseye | 70 | 350 | 
	| 24212 | Design: Royal Nightseye | 70 | 350 | 
	| 24213 | Design: Inscribed Noble Topaz | 70 | 350 | 
	| 24214 | Design: Potent Noble Topaz | 70 | 350 | 
	| 24215 | Design: Luminous Noble Topaz | 70 | 350 | 
	| 24216 | Design: Glinting Noble Topaz | 70 | 350 | 
	| 24217 | Design: Enduring Talasite | 70 | 350 | 
	| 24218 | Design: Radiant Talasite | 70 | 350 | 
	| 24219 | Design: Dazzling Talasite | 70 | 350 | 
	| 24220 | Design: Jagged Talasite | 70 | 350 | 
	| 25902 | Design: Powerful Earthstorm Diamond | 73 | 365 | 
	| 25903 | Design: Bracing Earthstorm Diamond | 73 | 365 | 
	| 25904 | Design: Insightful Earthstorm Diamond | 73 | 365 | 
	| 25905 | Design: Tenacious Earthstorm Diamond | 73 | 365 | 
	| 25906 | Design: Brutal Earthstorm Diamond | 73 | 365 | 
	| 25907 | Design: Destructive Skyfire Diamond | 73 | 365 | 
	| 25908 | Design: Swift Skyfire Diamond | 73 | 365 | 
	| 25909 | Design: Mystical Skyfire Diamond | 73 | 365 | 
	| 25910 | Design: Enigmatic Skyfire Diamond | 73 | 365 | 
	| 28291 | Design: Smooth Golden Draenite | 65 | 325 | 
	| 28596 | Design: Bright Blood Garnet | 61 | 305 | 
	| 30826 | Design: Ring of Arcane Shielding | 72 | 360 | 
	| 31358 | Design: Dawnstone Crab | 74 | 370 | 
	| 31359 | Design: Enduring Deep Peridot | 63 | 315 | 
	| 31401 | Design: The Frozen Eye | 75 | 375 | 
	| 31402 | Design: The Natural Ward | 75 | 375 | 
	| 31870 | Design: Great Golden Draenite | 65 | 325 | 
	| 31871 | Design: Balanced Shadow Draenite | 65 | 325 | 
	| 31872 | Design: Infused Shadow Draenite | 65 | 325 | 
	| 31873 | Design: Veiled Flame Spessarite | 65 | 325 | 
	| 31874 | Design: Wicked Flame Spessarite | 65 | 325 | 
	| 31875 | Design: Great Dawnstone | 70 | 350 | 
	| 31876 | Design: Balanced Nightseye | 70 | 350 | 
	| 31877 | Design: Infused Nightseye | 70 | 350 | 
	| 31878 | Design: Veiled Noble Topaz | 70 | 350 | 
	| 31879 | Design: Wicked Noble Topaz | 70 | 350 | 
	| 32274 | Design: Bold Crimson Spinel | 75 | 375 | 
	| 32277 | Design: Delicate Crimson Spinel | 75 | 375 | 
	| 32281 | Design: Teardrop Crimson Spinel | 75 | 375 | 
	| 32282 | Design: Runed Crimson Spinel | 75 | 375 | 
	| 32283 | Design: Bright Crimson Spinel | 75 | 375 | 
	| 32284 | Design: Subtle Crimson Spinel | 75 | 375 | 
	| 32285 | Design: Flashing Crimson Spinel | 75 | 375 | 
	| 32286 | Design: Solid Empyrean Sapphire | 75 | 375 | 
	| 32287 | Design: Sparkling Empyrean Sapphire | 75 | 375 | 
	| 32288 | Design: Lustrous Empyrean Sapphire | 75 | 375 | 
	| 32289 | Design: Stormy Empyrean Sapphire | 75 | 375 | 
	| 32290 | Design: Brilliant Lionseye | 75 | 375 | 
	| 32291 | Design: Smooth Lionseye | 75 | 375 | 
	| 32292 | Design: Rigid Lionseye | 75 | 375 | 
	| 32293 | Design: Gleaming Lionseye | 75 | 375 | 
	| 32294 | Design: Thick Lionseye | 75 | 375 | 
	| 32295 | Design: Mystic Lionseye | 75 | 375 | 
	| 32296 | Design: Great Lionseye | 75 | 375 | 
	| 32297 | Design: Sovereign Shadowsong Amethyst | 75 | 375 | 
	| 32298 | Design: Shifting Shadowsong Amethyst | 75 | 375 | 
	| 32299 | Design: Balanced Shadowsong Amethyst | 75 | 375 | 
	| 32300 | Design: Infused Shadowsong Amethyst | 75 | 375 | 
	| 32301 | Design: Glowing Shadowsong Amethyst | 75 | 375 | 
	| 32302 | Design: Royal Shadowsong Amethyst | 75 | 375 | 
	| 32303 | Design: Inscribed Pyrestone | 75 | 375 | 
	| 32304 | Design: Potent Pyrestone | 75 | 375 | 
	| 32305 | Design: Luminous Pyrestone | 75 | 375 | 
	| 32306 | Design: Glinting Pyrestone | 75 | 375 | 
	| 32307 | Design: Veiled Pyrestone | 75 | 375 | 
	| 32308 | Design: Wicked Pyrestone | 75 | 375 | 
	| 32309 | Design: Enduring Seaspray Emerald | 75 | 375 | 
	| 32310 | Design: Radiant Seaspray Emerald | 75 | 375 | 
	| 32311 | Design: Dazzling Seaspray Emerald | 75 | 375 | 
	| 32312 | Design: Jagged Seaspray Emerald | 75 | 375 | 
	| 32411 | Design: Thundering Skyfire Diamond | 73 | 365 | 
	| 32412 | Design: Relentless Earthstorm Diamond | 73 | 365 | 
	| 33155 | Design: Kailee's Rose | 70 | 360 | 
	| 33156 | Design: Crimson Sun | 70 | 360 | 
	| 33157 | Design: Falling Star | 70 | 360 | 
	| 33158 | Design: Stone of Blades | 70 | 360 | 
	| 33159 | Design: Blood of Amber | 70 | 360 | 
	| 33160 | Design: Facet of Eternity | 70 | 360 | 
	| 33305 | Design: Don Julio's Heart | 70 | 360 | 
	| 33622 | Design: Relentless Earthstorm Diamond | 73 | 365 | 
	| 33783 | Design: Steady Talasite | 70 | 350 | 
	| 34221 | Design: Chaotic Skyfire Diamond | 73 | 365 | 
	| 34689 | Design: Chaotic Skyfire Diamond | 73 | 365 | 
	| 35198 | Design: Loop of Forged Power | 70 | 365 | 
	| 35199 | Design: Ring of Flowing Life | 70 | 365 | 
	| 35200 | Design: Hard Khorium Band | 70 | 365 | 
	| 35201 | Design: Pendant of Sunfire | 70 | 365 | 
	| 35202 | Design: Amulet of Flowing Life | 70 | 365 | 
	| 35203 | Design: Hard Khorium Choker | 70 | 365 | 
	| 35238 | Design: Balanced Shadowsong Amethyst | 75 | 375 | 
	| 35239 | Design: Glowing Shadowsong Amethyst | 75 | 375 | 
	| 35240 | Design: Infused Shadowsong Amethyst | 75 | 375 | 
	| 35241 | Design: Royal Shadowsong Amethyst | 75 | 375 | 
	| 35242 | Design: Shifting Shadowsong Amethyst | 75 | 375 | 
	| 35243 | Design: Sovereign Shadowsong Amethyst | 75 | 375 | 
	| 35244 | Design: Bold Crimson Spinel | 75 | 375 | 
	| 35245 | Design: Bright Crimson Spinel | 75 | 375 | 
	| 35246 | Design: Delicate Crimson Spinel | 75 | 375 | 
	| 35247 | Design: Flashing Crimson Spinel | 75 | 375 | 
	| 35248 | Design: Runed Crimson Spinel | 75 | 375 | 
	| 35249 | Design: Subtle Crimson Spinel | 75 | 375 | 
	| 35250 | Design: Teardrop Crimson Spinel | 75 | 375 | 
	| 35251 | Design: Dazzling Seaspray Emerald | 75 | 375 | 
	| 35252 | Design: Enduring Seaspray Emerald | 75 | 375 | 
	| 35253 | Design: Jagged Seaspray Emerald | 75 | 375 | 
	| 35254 | Design: Radiant Seaspray Emerald | 75 | 375 | 
	| 35255 | Design: Brilliant Lionseye | 75 | 375 | 
	| 35256 | Design: Gleaming Lionseye | 75 | 375 | 
	| 35257 | Design: Great Lionseye | 75 | 375 | 
	| 35258 | Design: Mystic Lionseye | 75 | 375 | 
	| 35259 | Design: Rigid Lionseye | 75 | 375 | 
	| 35260 | Design: Smooth Lionseye | 75 | 375 | 
	| 35261 | Design: Thick Lionseye | 75 | 375 | 
	| 35262 | Design: Lustrous Empyrean Sapphire | 75 | 375 | 
	| 35263 | Design: Solid Empyrean Sapphire | 75 | 375 | 
	| 35264 | Design: Sparkling Empyrean Sapphire | 75 | 375 | 
	| 35265 | Design: Stormy Empyrean Sapphire | 75 | 375 | 
	| 35266 | Design: Glinting Pyrestone | 75 | 375 | 
	| 35267 | Design: Inscribed Pyrestone | 75 | 375 | 
	| 35268 | Design: Luminous Pyrestone | 75 | 375 | 
	| 35269 | Design: Potent Pyrestone | 75 | 375 | 
	| 35270 | Design: Veiled Pyrestone | 75 | 375 | 
	| 35271 | Design: Wicked Pyrestone | 75 | 375 | 
	| 35304 | Design: Solid Star of Elune | 70 | 350 | 
	| 35305 | Design: Runed Living Ruby | 70 | 350 | 
	| 35306 | Design: Bright Living Ruby | 70 | 350 | 
	| 35307 | Design: Rigid Dawnstone | 70 | 350 | 
	| 35322 | Design: Quick Dawnstone | 70 | 350 | 
	| 35323 | Design: Reckless Noble Topaz | 70 | 350 | 
	| 35325 | Design: Forceful Talasite | 70 | 350 | 
	| 35502 | Design: Eternal Earthstorm Diamond | 74 | 370 | 
	| 35505 | Design: Ember Skyfire Diamond | 74 | 370 | 
	| 35533 | Design: Amulet of Flowing Life | 70 | 365 | 
	| 35535 | Design: Hard Khorium Choker | 70 | 365 | 
	| 35537 | Design: Pendant of Sunfire | 70 | 365 | 
	| 35538 | Design: Ring of Flowing Life | 70 | 365 | 
	| 35695 | Design: Figurine - Empyrean Tortoise | 75 | 375 | 
	| 35696 | Design: Figurine - Khorium Boar | 75 | 375 | 
	| 35697 | Design: Figurine - Crimson Serpent | 75 | 375 | 
	| 35698 | Design: Figurine - Shadowsong Panther | 75 | 375 | 
	| 35699 | Design: Figurine - Seaspray Albatross | 75 | 375 | 
	| 35708 | Design: Regal Nightseye | 70 | 350 | 
	| 35762 | Design: Reckless Pyrestone | 75 | 375 | 
	| 35763 | Design: Quick Lionseye | 75 | 375 | 
	| 35764 | Design: Steady Seaspray Emerald | 75 | 375 | 
	| 35765 | Design: Forceful Seaspray Emerald | 75 | 375 | 
	| 35766 | Design: Steady Seaspray Emerald | 75 | 375 | 
	| 35767 | Design: Reckless Pyrestone | 75 | 375 | 
	| 35768 | Design: Quick Lionseye | 75 | 375 | 
	| 35769 | Design: Forceful Seaspray Emerald | 75 | 375 | 
	| 37504 | Design: Purified Shadowsong Amethyst | 75 | 375 | 
	| 41403 | ZZOLD Design: Insightful Earthsiege Diamond | 80 | 440 | 
	| 41404 | ZZOLD Design: Bracing Earthsiege Diamond | 80 | 440 | 
	| 41405 | ZZOLD Design: Eternal Earthsiege Diamond | 80 | 440 | 
	| 41406 | ZZOLD Design: Powerful Earthsiege Diamond | 80 | 440 | 
	| 41407 | ZZOLD Design: Relentless Earthsiege Diamond | 80 | 440 | 
	| 41408 | ZZOLD Design: Austere Earthsiege Diamond | 80 | 440 | 
	| 41409 | ZZOLD Design: Persistent Earthsiege Diamond | 80 | 440 | 
	| 41410 | ZZOLD Design: Trenchant Earthsiege Diamond | 80 | 440 | 
	| 41411 | ZZOLD Design: Invigorating Earthsiege Diamond | 80 | 440 | 
	| 41412 | ZZOLD Design: Beaming Earthsiege Diamond | 80 | 440 | 
	| 41413 | ZZOLD Design: Revitalizing Skyflare Diamond | 80 | 440 | 
	| 41414 | ZZOLD Design: Effulgent Skyflare Diamond | 80 | 440 | 
	| 41415 | ZZOLD Design: Tireless Skyflare Diamond | 80 | 440 | 
	| 41416 | ZZOLD Design: Forlorn Skyflare Diamond | 80 | 440 | 
	| 41417 | ZZOLD Design: Impassive Skyflare Diamond | 80 | 440 | 
	| 41418 | ZZOLD Design: Chaotic Skyflare Diamond | 80 | 440 | 
	| 41419 | ZZOLD Design: Destructive Skyflare Diamond | 80 | 440 | 
	| 41420 | ZZOLD Design: Ember Skyflare Diamond | 80 | 440 | 
	| 41421 | ZZOLD Design: Enigmatic Skyflare Diamond | 80 | 440 | 
	| 41422 | ZZOLD Design: Swift Skyflare Diamond | 80 | 440 | 
	| 41423 | ZZOLDDesign: Thundering Skyflare Diamond | 80 | 440 | 
	| 41559 | Design: Mystic Sun Crystal | 70 | 350 | 
	| 41560 | Design: Stormy Chalcedony | 70 | 350 | 
	| 41561 | Design: Reckless Huge Citrine | 70 | 350 | 
	| 41562 | Design: Deadly Huge Citrine | 70 | 350 | 
	| 41563 | Design: Durable Huge Citrine | 70 | 350 | 
	| 41564 | Design: Empowered Huge Citrine | 70 | 350 | 
	| 41565 | Design: Lucent Huge Citrine | 70 | 350 | 
	| 41566 | Design: Resplendent Huge Citrine | 70 | 350 | 
	| 41567 | Design: Vivid Dark Jade | 70 | 350 | 
	| 41568 | Design: Seer's Dark Jade | 70 | 350 | 
	| 41569 | Design: Shattered Dark Jade | 70 | 350 | 
	| 41570 | Design: Tense Dark Jade | 70 | 350 | 
	| 41571 | Design: Turbid Dark Jade | 70 | 350 | 
	| 41572 | Design: Steady Dark Jade | 70 | 350 | 
	| 41573 | Design: Opaque Dark Jade | 70 | 350 | 
	| 41574 | Design: Defender's Shadow Crystal | 70 | 350 | 
	| 41575 | Design: Mysterious Shadow Crystal | 70 | 350 | 
	| 41576 | Design: Bold Scarlet Ruby | 80 | 390 | 
	| 41577 | Design: Delicate Scarlet Ruby | 80 | 390 | 
	| 41578 | Design: Flashing Scarlet Ruby | 80 | 390 | 
	| 41579 | Design: Quick Autumn's Glow | 80 | 390 | 
	| 41580 | Design: Rigid Autumn's Glow | 80 | 390 | 
	| 41581 | Design: Lustrous Sky Sapphire | 80 | 390 | 
	| 41582 | Design: Glinting Monarch Topaz | 80 | 390 | 
	| 41686 | Design: Potent Monarch Topaz | 80 | 390 | 
	| 41687 | Design: Stark Monarch Topaz | 80 | 390 | 
	| 41688 | Design: Veiled Monarch Topaz | 80 | 390 | 
	| 41689 | Design: Luminous Monarch Topaz | 80 | 390 | 
	| 41690 | Design: Reckless Monarch Topaz | 80 | 390 | 
	| 41692 | Design: Energized Forest Emerald | 80 | 390 | 
	| 41693 | Design: Forceful Forest Emerald | 80 | 390 | 
	| 41694 | Design: Intricate Forest Emerald | 80 | 390 | 
	| 41696 | Design: Lambent Forest Emerald | 80 | 390 | 
	| 41697 | Design: Enduring Forest Emerald | 80 | 390 | 
	| 41698 | Design: Vivid Forest Emerald | 80 | 390 | 
	| 41699 | Design: Seer's Forest Emerald | 80 | 390 | 
	| 41701 | Design: Royal Twilight Opal | 80 | 390 | 
	| 41702 | Design: Puissant Twilight Opal | 80 | 390 | 
	| 41703 | Design: Regal Twilight Opal | 80 | 390 | 
	| 41704 | Design: Chaotic Skyflare Diamond | 80 | 420 | 
	| 41705 | Design: Effulgent Skyflare Diamond | 80 | 420 | 
	| 41706 | Design: Ember Skyflare Diamond | 80 | 420 | 
	| 41707 | Design: Revitalizing Skyflare Diamond | 80 | 420 | 
	| 41708 | Design: Insightful Earthsiege Diamond | 80 | 420 | 
	| 41709 | Design: Invigorating Earthsiege Diamond | 80 | 420 | 
	| 41710 | Design: Relentless Earthsiege Diamond | 80 | 420 | 
	| 41711 | Design: Trenchant Earthsiege Diamond | 80 | 420 | 
	| 41718 | Design: Runed Scarlet Ruby | 80 | 390 | 
	| 41719 | Design: Subtle Scarlet Ruby | 80 | 390 | 
	| 41720 | Design: Smooth Autumn's Glow | 80 | 390 | 
	| 41721 | Design: Wicked Monarch Topaz | 80 | 390 | 
	| 41722 | Design: Glimmering Monarch Topaz | 80 | 390 | 
	| 41723 | Design: Jagged Forest Emerald | 80 | 390 | 
	| 41724 | Design: Sundered Forest Emerald | 80 | 390 | 
	| 41725 | Design: Glowing Twilight Opal | 80 | 390 | 
	| 41726 | Design: Guardian's Twilight Opal | 80 | 390 | 
	| 41727 | Design: Mystic Autumn's Glow | 80 | 390 | 
	| 41728 | Design: Stormy Sky Sapphire | 80 | 390 | 
	| 41730 | Design: Durable Monarch Topaz | 80 | 390 | 
	| 41732 | Design: Empowered Monarch Topaz | 80 | 390 | 
	| 41733 | Design: Lucent Monarch Topaz | 80 | 390 | 
	| 41734 | Design: Resplendent Monarch Topaz | 80 | 390 | 
	| 41735 | Design: Shattered Forest Emerald | 80 | 390 | 
	| 41736 | Design: Tense Forest Emerald | 80 | 390 | 
	| 41737 | Design: Turbid Forest Emerald | 80 | 390 | 
	| 41738 | Design: Steady Forest Emerald | 80 | 390 | 
	| 41739 | Design: Opaque Forest Emerald | 80 | 390 | 
	| 41740 | Design: Mysterious Twilight Opal | 80 | 390 | 
	| 41742 | Design: Enigmatic Skyflare Diamond | 80 | 420 | 
	| 41743 | Design: Forlorn Skyflare Diamond | 80 | 420 | 
	| 41744 | Design: Impassive Skyflare Diamond | 80 | 420 | 
	| 41747 | Design: Shifting Twilight Opal | 80 | 390 | 
	| 41777 | Design: Etched Monarch Topaz | 80 | 390 | 
	| 41778 | Design: Resolute Monarch Topaz | 80 | 390 | 
	| 41779 | Design: Stalwart Monarch Topaz | 80 | 390 | 
	| 41780 | Design: Champion's Monarch Topaz | 80 | 390 | 
	| 41781 | Design: Misty Forest Emerald | 80 | 390 | 
	| 41782 | Design: Shining Forest Emerald | 80 | 390 | 
	| 41783 | Design: Purified Twilight Opal | 80 | 390 | 
	| 41784 | Design: Sovereign Twilight Opal | 80 | 390 | 
	| 41785 | Design: Tenuous Twilight Opal | 80 | 390 | 
	| 41786 | Design: Destructive Skyflare Diamond | 80 | 420 | 
	| 41787 | Design: Thundering Skyflare Diamond | 80 | 420 | 
	| 41788 | Design: Beaming Earthsiege Diamond | 80 | 420 | 
	| 41789 | Design: Inscribed Monarch Topaz | 80 | 390 | 
	| 41790 | Design: Precise Scarlet Ruby | 80 | 390 | 
	| 41791 | Design: Thick Autumn's Glow | 80 | 390 | 
	| 41792 | Design: Deft Monarch Topaz | 80 | 390 | 
	| 41793 | Design: Fierce Monarch Topaz | 80 | 390 | 
	| 41794 | Design: Deadly Monarch Topaz | 80 | 390 | 
	| 41795 | Design: Timeless Forest Emerald | 80 | 390 | 
	| 41796 | Design: Infused Twilight Opal | 80 | 390 | 
	| 41797 | Design: Austere Earthsiege Diamond | 80 | 420 | 
	| 41798 | Design: Bracing Earthsiege Diamond | 80 | 420 | 
	| 41799 | Design: Eternal Earthsiege Diamond | 80 | 420 | 
	| 41817 | Design: Fractured Scarlet Ruby | 80 | 390 | 
	| 41818 | Design: Accurate Monarch Topaz | 80 | 390 | 
	| 41819 | Design: Radiant Forest Emerald | 80 | 390 | 
	| 41820 | Design: Defender's Twilight Opal | 80 | 390 | 
	| 42138 | Design: Solid Sky Sapphire | 80 | 390 | 
	| 42298 | Design: Bold Dragon's Eye | 78 | 370 | 
	| 42299 | Design: Bright Dragon's Eye | 78 | 370 | 
	| 42300 | Design: Brilliant Dragon's Eye | 78 | 370 | 
	| 42301 | Design: Delicate Dragon's Eye | 78 | 370 | 
	| 42302 | Design: Flashing Dragon's Eye | 78 | 370 | 
	| 42303 | Design: Fractured Dragon's Eye | 78 | 370 | 
	| 42304 | Design: Lustrous Dragon's Eye | 78 | 370 | 
	| 42305 | Design: Mystic Dragon's Eye | 78 | 370 | 
	| 42306 | Design: Precise Dragon's Eye | 78 | 370 | 
	| 42307 | Design: Quick Dragon's Eye | 78 | 370 | 
	| 42308 | Design: Rigid Dragon's Eye | 78 | 370 | 
	| 42309 | Design: Runed Dragon's Eye | 78 | 370 | 
	| 42310 | Design: Smooth Dragon's Eye | 78 | 370 | 
	| 42311 | Design: Solid Dragon's Eye | 78 | 370 | 
	| 42312 | Design: Sparkling Dragon's Eye | 78 | 370 | 
	| 42313 | Design: Stormy Dragon's Eye | 78 | 370 | 
	| 42314 | Design: Subtle Dragon's Eye | 78 | 370 | 
	| 42315 | Design: Thick Dragon's Eye | 78 | 370 | 
	| 42648 | Design: Titanium Impact Band | 80 | 430 | 
	| 42649 | Design: Titanium Earthguard Ring | 80 | 430 | 
	| 42650 | Design: Titanium Spellshock Ring | 80 | 430 | 
	| 42651 | Design: Titanium Impact Choker | 80 | 440 | 
	| 42652 | Design: Titanium Earthguard Chain | 80 | 440 | 
	| 42653 | Design: Titanium Spellshock Necklace | 80 | 440 | 
	| 43317 | Design: Ring of Earthen Might | 80 | 420 | 
	| 43318 | Design: Ring of Scarlet Shadows | 80 | 420 | 
	| 43319 | Design: Windfire Band | 80 | 420 | 
	| 43320 | Design: Ring of Northern Tears | 80 | 420 | 
	| 43485 | Design: Savage Titanium Ring | 80 | 420 | 
	| 43497 | Design: Savage Titanium Band | 80 | 420 | 
	| 43597 | Design: Titanium Frostguard Ring | 80 | 420 | 
	| 46897 | Design: Enduring Eye of Zul | 80 | 450 | 
	| 46898 | Design: Steady Eye of Zul | 80 | 450 | 
	| 46899 | Design: Vivid Eye of Zul | 80 | 450 | 
	| 46900 | Design: Dazzling Eye of Zul | 80 | 450 | 
	| 46901 | Design: Jagged Eye of Zul | 80 | 450 | 
	| 46902 | Design: Timeless Eye of Zul | 80 | 450 | 
	| 46903 | Design: Seer's Eye of Zul | 80 | 450 | 
	| 46904 | Design: Forceful Eye of Zul | 80 | 450 | 
	| 46905 | Design: Misty Eye of Zul | 80 | 450 | 
	| 46906 | Design: Sundered Eye of Zul | 80 | 450 | 
	| 46907 | Design: Shining Eye of Zul | 80 | 450 | 
	| 46908 | Design: Tense Eye of Zul | 80 | 450 | 
	| 46909 | Design: Lambent Eye of Zul | 80 | 450 | 
	| 46910 | Design: Intricate Eye of Zul | 80 | 450 | 
	| 46911 | Design: Radiant Eye of Zul | 80 | 450 | 
	| 46912 | Design: Energized Eye of Zul | 80 | 450 | 
	| 46913 | Design: Shattered Eye of Zul | 80 | 450 | 
	| 46914 | Design: Opaque Eye of Zul | 80 | 450 | 
	| 46915 | Design: Turbid Eye of Zul | 80 | 450 | 
	| 46916 | Design: Runed Cardinal Ruby | 80 | 450 | 
	| 46917 | Design: Bold Cardinal Ruby | 80 | 450 | 
	| 46918 | Design: Delicate Cardinal Ruby | 80 | 450 | 
	| 46919 | Design: Bright Cardinal Ruby | 80 | 450 | 
	| 46920 | Design: Precise Cardinal Ruby | 80 | 450 | 
	| 46921 | Design: Fractured Cardinal Ruby | 80 | 450 | 
	| 46922 | Design: Subtle Cardinal Ruby | 80 | 450 | 
	| 46923 | Design: Flashing Cardinal Ruby | 80 | 450 | 
	| 46924 | Design: Solid Majestic Zircon | 80 | 450 | 
	| 46925 | Design: Sparkling Majestic Zircon | 80 | 450 | 
	| 46926 | Design: Stormy Majestic Zircon | 80 | 450 | 
	| 46927 | Design: Lustrous Majestic Zircon | 80 | 450 | 
	| 46928 | Design: Rigid King's Amber | 80 | 450 | 
	| 46929 | Design: Smooth King's Amber | 80 | 450 | 
	| 46930 | Design: Brilliant King's Amber | 80 | 450 | 
	| 46931 | Design: Thick King's Amber | 80 | 450 | 
	| 46932 | Design: Mystic King's Amber | 80 | 450 | 
	| 46933 | Design: Quick King's Amber | 80 | 450 | 
	| 46934 | Design: Balanced Dreadstone | 80 | 450 | 
	| 46935 | Design: Sovereign Dreadstone | 80 | 450 | 
	| 46936 | Design: Glowing Dreadstone | 80 | 450 | 
	| 46937 | Design: Purified Dreadstone | 80 | 450 | 
	| 46938 | Design: Shifting Dreadstone | 80 | 450 | 
	| 46939 | Design: Royal Dreadstone | 80 | 450 | 
	| 46940 | Design: Regal Dreadstone | 80 | 450 | 
	| 46941 | Design: Defender's Dreadstone | 80 | 450 | 
	| 46942 | Design: Guardian's Dreadstone | 80 | 450 | 
	| 46943 | Design: Mysterious Dreadstone | 80 | 450 | 
	| 46944 | Design: Puissant Dreadstone | 80 | 450 | 
	| 46945 | Design: Infused Dreadstone | 80 | 450 | 
	| 46946 | Design: Tenuous Dreadstone | 80 | 450 | 
	| 46947 | Design: Luminous Ametrine | 80 | 450 | 
	| 46948 | Design: Inscribed Ametrine | 80 | 450 | 
	| 46949 | Design: Deadly Ametrine | 80 | 450 | 
	| 46950 | Design: Potent Ametrine | 80 | 450 | 
	| 46951 | Design: Veiled Ametrine | 80 | 450 | 
	| 46952 | Design: Durable Ametrine | 80 | 450 | 
	| 46953 | Design: Etched Ametrine | 80 | 450 | 
	| 46956 | Design: Pristine Ametrine | 80 | 450 | 
	| 47007 | Design: Reckless Ametrine | 80 | 450 | 
	| 47008 | Design: Glinting Ametrine | 80 | 450 | 
	| 47010 | Design: Accurate Ametrine | 80 | 450 | 
	| 47011 | Design: Wicked Ametrine | 80 | 450 | 
	| 47012 | Design: Glimmering Ametrine | 80 | 450 | 
	| 47015 | Design: Champion's Ametrine | 80 | 450 | 
	| 47016 | Design: Empowered Ametrine | 80 | 450 | 
	| 47017 | Design: Stalwart Ametrine | 80 | 450 | 
	| 47018 | Design: Resplendent Ametrine | 80 | 450 | 
	| 47019 | Design: Fierce Ametrine | 80 | 450 | 
	| 47020 | Design: Deft Ametrine | 80 | 450 | 
	| 47021 | Design: Lucent Ametrine | 80 | 450 | 
	| 47022 | Design: Resolute Ametrine | 80 | 450 | 
	| 47023 | Design: Stark Ametrine | 80 | 450 | 
	| 49112 | Design: Nightmare Tear | 80 | 450 | 
	
	</details>
	
	21957, 23130, 23131, 23133, 23134, 23135, 23136, 23137, 23138, 23140, 23141, 23142, 23143, 23144, 23145, 23146, 23147, 23148, 23149, 23150, 23151, 23152, 23153, 23154, 23155, 24158, 24159, 24160, 24161, 24162, 24163, 24164, 24165, 24166, 24167, 24168, 24169, 24170, 24171, 24172, 24173, 24174, 24175, 24176, 24177, 24178, 24179, 24180, 24181, 24182, 24183, 24192, 24193, 24194, 24195, 24196, 24197, 24198, 24199, 24200, 24201, 24202, 24203, 24204, 24205, 24206, 24207, 24208, 24209, 24210, 24211, 24212, 24213, 24214, 24215, 24216, 24217, 24218, 24219, 24220, 25902, 25903, 25904, 25905, 25906, 25907, 25908, 25909, 25910, 28291, 28596, 30826, 31358, 31359, 31401, 31402, 31870, 31871, 31872, 31873, 31874, 31875, 31876, 31877, 31878, 31879, 32274, 32277, 32281, 32282, 32283, 32284, 32285, 32286, 32287, 32288, 32289, 32290, 32291, 32292, 32293, 32294, 32295, 32296, 32297, 32298, 32299, 32300, 32301, 32302, 32303, 32304, 32305, 32306, 32307, 32308, 32309, 32310, 32311, 32312, 32411, 32412, 33155, 33156, 33157, 33158, 33159, 33160, 33305, 33622, 33783, 34221, 34689, 35198, 35199, 35200, 35201, 35202, 35203, 35238, 35239, 35240, 35241, 35242, 35243, 35244, 35245, 35246, 35247, 35248, 35249, 35250, 35251, 35252, 35253, 35254, 35255, 35256, 35257, 35258, 35259, 35260, 35261, 35262, 35263, 35264, 35265, 35266, 35267, 35268, 35269, 35270, 35271, 35304, 35305, 35306, 35307, 35322, 35323, 35325, 35502, 35505, 35533, 35535, 35537, 35538, 35695, 35696, 35697, 35698, 35699, 35708, 35762, 35763, 35764, 35765, 35766, 35767, 35768, 35769, 37504, 41403, 41404, 41405, 41406, 41407, 41408, 41409, 41410, 41411, 41412, 41413, 41414, 41415, 41416, 41417, 41418, 41419, 41420, 41421, 41422, 41423, 41559, 41560, 41561, 41562, 41563, 41564, 41565, 41566, 41567, 41568, 41569, 41570, 41571, 41572, 41573, 41574, 41575, 41576, 41577, 41578, 41579, 41580, 41581, 41582, 41686, 41687, 41688, 41689, 41690, 41692, 41693, 41694, 41696, 41697, 41698, 41699, 41701, 41702, 41703, 41704, 41705, 41706, 41707, 41708, 41709, 41710, 41711, 41718, 41719, 41720, 41721, 41722, 41723, 41724, 41725, 41726, 41727, 41728, 41730, 41732, 41733, 41734, 41735, 41736, 41737, 41738, 41739, 41740, 41742, 41743, 41744, 41747, 41777, 41778, 41779, 41780, 41781, 41782, 41783, 41784, 41785, 41786, 41787, 41788, 41789, 41790, 41791, 41792, 41793, 41794, 41795, 41796, 41797, 41798, 41799, 41817, 41818, 41819, 41820, 42138, 42298, 42299, 42300, 42301, 42302, 42303, 42304, 42305, 42306, 42307, 42308, 42309, 42310, 42311, 42312, 42313, 42314, 42315, 42648, 42649, 42650, 42651, 42652, 42653, 43317, 43318, 43319, 43320, 43485, 43497, 43597, 46897, 46898, 46899, 46900, 46901, 46902, 46903, 46904, 46905, 46906, 46907, 46908, 46909, 46910, 46911, 46912, 46913, 46914, 46915, 46916, 46917, 46918, 46919, 46920, 46921, 46922, 46923, 46924, 46925, 46926, 46927, 46928, 46929, 46930, 46931, 46932, 46933, 46934, 46935, 46936, 46937, 46938, 46939, 46940, 46941, 46942, 46943, 46944, 46945, 46946, 46947, 46948, 46949, 46950, 46951, 46952, 46953, 46956, 47007, 47008, 47010, 47011, 47012, 47015, 47016, 47017, 47018, 47019, 47020, 47021, 47022, 47023, 49112
	
	<hr>
	
	## Concatenated Recipes:
	
	22146, 22153, 22182, 22187, 22189, 28073, 29549, 29550, 31501, 31837, 33316, 35273, 36955, 36959, 36960, 36964, 36965, 36966, 36967, 36968, 36970, 44602, 44714, 45912, 46108, 49177, 50167, 50168, 25720, 25721, 25722, 25725, 25726, 25728, 25729, 25730, 25731, 25732, 25733, 25734, 25735, 25736, 25737, 25738, 25739, 25740, 25741, 25742, 25743, 29213, 29214, 29215, 29217, 29218, 29219, 29664, 29669, 29672, 29673, 29674, 29675, 29677, 29682, 29684, 29689, 29691, 29693, 29698, 29700, 29701, 29702, 29703, 29704, 29713, 29714, 29717, 29718, 29719, 29720, 29721, 29722, 29723, 29724, 29725, 29726, 29727, 29728, 29729, 29730, 29731, 29732, 29733, 29734, 30301, 30302, 30303, 30304, 30305, 30306, 30307, 30308, 30444, 31361, 31362, 32429, 32430, 32431, 32432, 32433, 32434, 32435, 32436, 32744, 32745, 32746, 32747, 32748, 32749, 32750, 32751, 33124, 33205, 34172, 34173, 34174, 34175, 34200, 34201, 34218, 34491, 35212, 35213, 35214, 35215, 35216, 35217, 35218, 35219, 35300, 35301, 35302, 35303, 35517, 35519, 35520, 35521, 35523, 35524, 35527, 35528, 35539, 35541, 35545, 35546, 35549, 35550, 38597, 44509, 44510, 44511, 44512, 44513, 44514, 44515, 44516, 44517, 44518, 44519, 44520, 44521, 44522, 44523, 44524, 44525, 44526, 44527, 44528, 44530, 44531, 44532, 44533, 44534, 44535, 44536, 44537, 44538, 44539, 44540, 44541, 44542, 44543, 44544, 44545, 44546, 44547, 44548, 44549, 44550, 44551, 44552, 44553, 44559, 44560, 44561, 44562, 44563, 44584, 44585, 44586, 44587, 44588, 44589, 44932, 44933, 45094, 45095, 45096, 45097, 45098, 45099, 45100, 45101, 47628, 47629, 47630, 47631, 47632, 47633, 47634, 47635, 47646, 47647, 47648, 47649, 47650, 47651, 47652, 47653, 49957, 49958, 49959, 49961, 49962, 49963, 49965, 49966, 34262, 21892, 21893, 21894, 21895, 21896, 21897, 21898, 21899, 21900, 21901, 21902, 21903, 21904, 21905, 21906, 21907, 21908, 21909, 21910, 21911, 21912, 21913, 21914, 21915, 21916, 21917, 21918, 21919, 24292, 24293, 24294, 24295, 24296, 24297, 24298, 24299, 24300, 24301, 24302, 24303, 24304, 24305, 24306, 24307, 24308, 24309, 24310, 24311, 24312, 24313, 24314, 24315, 24316, 30280, 30281, 30282, 30283, 30483, 30833, 30842, 30843, 30844, 32437, 32438, 32439, 32440, 32447, 32752, 32753, 32754, 32755, 35204, 35205, 35206, 35207, 35308, 35309, 35518, 35522, 35525, 35526, 35544, 35548, 35551, 38229, 42172, 42173, 42174, 42175, 42176, 42177, 42178, 42179, 42180, 42181, 42182, 42183, 42184, 42185, 42186, 42187, 42188, 42189, 42190, 42191, 42192, 42193, 42194, 42195, 42196, 42197, 42198, 42199, 42200, 42201, 42202, 43876, 45102, 45103, 45104, 45105, 45774, 47636, 47637, 47638, 47639, 47654, 47655, 47656, 47657, 49953, 49954, 49955, 49956, 54798, 23799, 23800, 23802, 23803, 23804, 23805, 23806, 23807, 23808, 23809, 23810, 23811, 23814, 23815, 23816, 23817, 23874, 23882, 23883, 23884, 23885, 23887, 23888, 25887, 33804, 34114, 35186, 35187, 35189, 35190, 35191, 35192, 35193, 35194, 35195, 35196, 35197, 35310, 35311, 35582, 44502, 44503, 49050, 52022, 52023, 23590, 23591, 23592, 23593, 23594, 23595, 23596, 23597, 23598, 23599, 23600, 23601, 23602, 23603, 23604, 23605, 23606, 23607, 23608, 23609, 23610, 23611, 23612, 23613, 23615, 23617, 23618, 23619, 23620, 23621, 23622, 23623, 23624, 23625, 23626, 23627, 23628, 23629, 23630, 23631, 23632, 23633, 23634, 23635, 23636, 23637, 23638, 23639, 24002, 25526, 25846, 25847, 28632, 30321, 30322, 30323, 30324, 31390, 31391, 31392, 31393, 31394, 31395, 32441, 32442, 32443, 32444, 32736, 32737, 32738, 32739, 33174, 33186, 33954, 35208, 35209, 35210, 35211, 35296, 35529, 35530, 35531, 35532, 35553, 35555, 41120, 41122, 41123, 41124, 44937, 44938, 45088, 45089, 45090, 45091, 45092, 45093, 47622, 47623, 47624, 47625, 47626, 47627, 47640, 47641, 47642, 47643, 47644, 47645, 49969, 49970, 49971, 49972, 49973, 49974, 27684, 27688, 27689, 27690, 27691, 27692, 27693, 27694, 27695, 27696, 27697, 27698, 27699, 27700, 30156, 31674, 31675, 33869, 33870, 33871, 33873, 33875, 34126, 39644, 39692, 43017, 43018, 43019, 43020, 43021, 43022, 43023, 43024, 43025, 43026, 43027, 43028, 43029, 43030, 43031, 43032, 43033, 43034, 43035, 43036, 43037, 43505, 43506, 43507, 43508, 43509, 43510, 44954, 13517, 22900, 22901, 22902, 22903, 22904, 22905, 22906, 22907, 22908, 22909, 22910, 22911, 22912, 22913, 22914, 22915, 22916, 22917, 22918, 22919, 22920, 22921, 22922, 22923, 22924, 22925, 22926, 22927, 23574, 24001, 25869, 25870, 29232, 30443, 31354, 31355, 31356, 31357, 31680, 31681, 31682, 32070, 32071, 33209, 35294, 35295, 35752, 35753, 35754, 35755, 44564, 44565, 44566, 44567, 44568, 47507, 21992, 21993, 22012, 39152, 39153, 22530, 22531, 22532, 22533, 22534, 22535, 22536, 22537, 22538, 22539, 22540, 22541, 22542, 22543, 22544, 22545, 22547, 22548, 22551, 22552, 22553, 22554, 22555, 22556, 22557, 22558, 22559, 22560, 22561, 22562, 22563, 22565, 24000, 24003, 25848, 25849, 28270, 28271, 28272, 28273, 28274, 28276, 28277, 28279, 28280, 28281, 28282, 33165, 33307, 34872, 35297, 35298, 35299, 35498, 35500, 35756, 37326, 37329, 37330, 37331, 37332, 37333, 37334, 37335, 37336, 37337, 37338, 37339, 37340, 37343, 37344, 37345, 37346, 37347, 37348, 37349, 44471, 44472, 44473, 44483, 44484, 44485, 44486, 44487, 44488, 44489, 44490, 44491, 44492, 44494, 44495, 44496, 44498, 44944, 44945, 45059, 46027, 46348, 50406, 27532, 46055, 21957, 23130, 23131, 23133, 23134, 23135, 23136, 23137, 23138, 23140, 23141, 23142, 23143, 23144, 23145, 23146, 23147, 23148, 23149, 23150, 23151, 23152, 23153, 23154, 23155, 24158, 24159, 24160, 24161, 24162, 24163, 24164, 24165, 24166, 24167, 24168, 24169, 24170, 24171, 24172, 24173, 24174, 24175, 24176, 24177, 24178, 24179, 24180, 24181, 24182, 24183, 24192, 24193, 24194, 24195, 24196, 24197, 24198, 24199, 24200, 24201, 24202, 24203, 24204, 24205, 24206, 24207, 24208, 24209, 24210, 24211, 24212, 24213, 24214, 24215, 24216, 24217, 24218, 24219, 24220, 25902, 25903, 25904, 25905, 25906, 25907, 25908, 25909, 25910, 28291, 28596, 30826, 31358, 31359, 31401, 31402, 31870, 31871, 31872, 31873, 31874, 31875, 31876, 31877, 31878, 31879, 32274, 32277, 32281, 32282, 32283, 32284, 32285, 32286, 32287, 32288, 32289, 32290, 32291, 32292, 32293, 32294, 32295, 32296, 32297, 32298, 32299, 32300, 32301, 32302, 32303, 32304, 32305, 32306, 32307, 32308, 32309, 32310, 32311, 32312, 32411, 32412, 33155, 33156, 33157, 33158, 33159, 33160, 33305, 33622, 33783, 34221, 34689, 35198, 35199, 35200, 35201, 35202, 35203, 35238, 35239, 35240, 35241, 35242, 35243, 35244, 35245, 35246, 35247, 35248, 35249, 35250, 35251, 35252, 35253, 35254, 35255, 35256, 35257, 35258, 35259, 35260, 35261, 35262, 35263, 35264, 35265, 35266, 35267, 35268, 35269, 35270, 35271, 35304, 35305, 35306, 35307, 35322, 35323, 35325, 35502, 35505, 35533, 35535, 35537, 35538, 35695, 35696, 35697, 35698, 35699, 35708, 35762, 35763, 35764, 35765, 35766, 35767, 35768, 35769, 37504, 41403, 41404, 41405, 41406, 41407, 41408, 41409, 41410, 41411, 41412, 41413, 41414, 41415, 41416, 41417, 41418, 41419, 41420, 41421, 41422, 41423, 41559, 41560, 41561, 41562, 41563, 41564, 41565, 41566, 41567, 41568, 41569, 41570, 41571, 41572, 41573, 41574, 41575, 41576, 41577, 41578, 41579, 41580, 41581, 41582, 41686, 41687, 41688, 41689, 41690, 41692, 41693, 41694, 41696, 41697, 41698, 41699, 41701, 41702, 41703, 41704, 41705, 41706, 41707, 41708, 41709, 41710, 41711, 41718, 41719, 41720, 41721, 41722, 41723, 41724, 41725, 41726, 41727, 41728, 41730, 41732, 41733, 41734, 41735, 41736, 41737, 41738, 41739, 41740, 41742, 41743, 41744, 41747, 41777, 41778, 41779, 41780, 41781, 41782, 41783, 41784, 41785, 41786, 41787, 41788, 41789, 41790, 41791, 41792, 41793, 41794, 41795, 41796, 41797, 41798, 41799, 41817, 41818, 41819, 41820, 42138, 42298, 42299, 42300, 42301, 42302, 42303, 42304, 42305, 42306, 42307, 42308, 42309, 42310, 42311, 42312, 42313, 42314, 42315, 42648, 42649, 42650, 42651, 42652, 42653, 43317, 43318, 43319, 43320, 43485, 43497, 43597, 46897, 46898, 46899, 46900, 46901, 46902, 46903, 46904, 46905, 46906, 46907, 46908, 46909, 46910, 46911, 46912, 46913, 46914, 46915, 46916, 46917, 46918, 46919, 46920, 46921, 46922, 46923, 46924, 46925, 46926, 46927, 46928, 46929, 46930, 46931, 46932, 46933, 46934, 46935, 46936, 46937, 46938, 46939, 46940, 46941, 46942, 46943, 46944, 46945, 46946, 46947, 46948, 46949, 46950, 46951, 46952, 46953, 46956, 47007, 47008, 47010, 47011, 47012, 47015, 47016, 47017, 47018, 47019, 47020, 47021, 47022, 47023, 49112
	
