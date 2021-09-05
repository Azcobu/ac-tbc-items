### Armour (class = 4)

Using the same NPC lists as for Weapons.

Q'D Armour: - 243 items, all unuseable anyway.
```SQL
SELECT DISTINCT( it.entry), it.name, it.itemlevel, it.RequiredLevel
FROM `creature_template` ct
JOIN `creature_loot_template` clt ON ct.lootid = clt.entry
JOIN `reference_loot_template` rlt ON clt.Reference = rlt.Entry
JOIN `item_template` it ON it.entry = rlt.Item
WHERE ct.entry IN (24996, 24960, 25047, 24999, 25002, 24976, 24978, 24979, 25063, 
25087, 25548, 25073, 25060, 25001)
AND it.class = 4 
```

<details>
<summary>Results</summary>

---
| entry | name | itemlevel | RequiredLevel | 
| ---: | --- | ---: | ---: | 
| 24653 | Consortium Sash | 108 | 66 | 
| 24654 | Consortium Boot | 108 | 66 | 
| 24655 | Consortium Robe | 108 | 66 | 
| 24656 | Consortium Gloves | 108 | 66 | 
| 24657 | Consortium Hood | 108 | 66 | 
| 24658 | Consortium Pants | 108 | 66 | 
| 24659 | Consortium Mantle | 108 | 66 | 
| 24660 | Consortium Bracer | 108 | 66 | 
| 24661 | Shadow Council Chain | 111 | 67 | 
| 24662 | Shadow Council Boots | 111 | 67 | 
| 24663 | Shadow Council Tunic | 111 | 67 | 
| 24664 | Shadow Council Gloves | 111 | 67 | 
| 24665 | Shadow Council Cowl | 111 | 67 | 
| 24666 | Shadow Council Pants | 111 | 67 | 
| 24667 | Shadow Council Mantle | 111 | 67 | 
| 24668 | Shadow Council Bracer | 111 | 67 | 
| 24669 | Eldr'naan Belt | 114 | 68 | 
| 24670 | Eldr'naan Boots | 114 | 68 | 
| 24671 | Eldr'naan Jerkin | 114 | 68 | 
| 24672 | Eldr'naan Gloves | 114 | 68 | 
| 24673 | Eldr'naan Hood | 114 | 68 | 
| 24674 | Eldr'naan Pants | 114 | 68 | 
| 24675 | Eldr'naan Shoulderpads | 114 | 68 | 
| 24676 | Eldr'naan Bracelets | 114 | 68 | 
| 24677 | Archmage Belt | 117 | 69 | 
| 24678 | Archmage Slippers | 117 | 69 | 
| 24679 | Archmage Robe | 117 | 69 | 
| 24680 | Archmage Gloves | 117 | 69 | 
| 24681 | Archmage Headpiece | 117 | 69 | 
| 24682 | Archmage Pants | 117 | 69 | 
| 24683 | Archmage Mantle | 117 | 69 | 
| 24684 | Archmage Bracelets | 117 | 69 | 
| 24685 | Elementalist Belt | 120 | 70 | 
| 24686 | Elementalist Boots | 120 | 70 | 
| 24687 | Elementalist Tunic | 120 | 70 | 
| 24688 | Elementalist Gloves | 120 | 70 | 
| 24689 | Elementalist Skullcap | 120 | 70 | 
| 24690 | Elementalist Leggings | 120 | 70 | 
| 24691 | Elementalist Mantle | 120 | 70 | 
| 24692 | Elementalist Bracelets | 120 | 70 | 
| 24765 | Clefthoof Belt | 108 | 66 | 
| 24766 | Clefthoof Wanderboots | 108 | 66 | 
| 24767 | Clefthoof Hidemantle | 108 | 66 | 
| 24768 | Clefthoof Gloves | 108 | 66 | 
| 24769 | Clefthoof Cover | 108 | 66 | 
| 24770 | Clefthoof Britches | 108 | 66 | 
| 24771 | Clefthoof Shoulderguards | 108 | 66 | 
| 24772 | Clefthoof Bracers | 108 | 66 | 
| 24773 | Boneshredder Belt | 111 | 67 | 
| 24774 | Boneshredder Boots | 111 | 67 | 
| 24775 | Boneshredder Jerkin | 111 | 67 | 
| 24776 | Boneshredder Gloves | 111 | 67 | 
| 24777 | Boneshredder Skullcap | 111 | 67 | 
| 24778 | Boneshredder Britches | 111 | 67 | 
| 24779 | Boneshredder Shoulderguards | 111 | 67 | 
| 24780 | Boneshredder Wristguards | 111 | 67 | 
| 24781 | Murkblood Belt | 114 | 68 | 
| 24783 | Murkblood Boots | 114 | 68 | 
| 24784 | Murkblood Chestpiece | 114 | 68 | 
| 24785 | Murkblood Gloves | 114 | 68 | 
| 24786 | Murkblood Cover | 114 | 68 | 
| 24787 | Murkblood Pants | 114 | 68 | 
| 24788 | Murkblood Shoulderguards | 114 | 68 | 
| 24789 | Murkblood Bracers | 114 | 68 | 
| 24790 | Expedition Girdle | 117 | 69 | 
| 24791 | Expedition Boots | 117 | 69 | 
| 24792 | Expedition Tunic | 117 | 69 | 
| 24793 | Expedition Gloves | 117 | 69 | 
| 24794 | Expedition Hood | 117 | 69 | 
| 24795 | Expedition Pants | 117 | 69 | 
| 24796 | Expedition Shoulderguards | 117 | 69 | 
| 24797 | Expedition Bracers | 117 | 69 | 
| 24798 | Dragonhawk Belt | 120 | 70 | 
| 24799 | Dragonhawk Boots | 120 | 70 | 
| 24800 | Dragonhawk Tunic | 120 | 70 | 
| 24801 | Dragonhawk Gloves | 120 | 70 | 
| 24802 | Dragonhawk Hat | 120 | 70 | 
| 24803 | Dragonhawk Pants | 120 | 70 | 
| 24804 | Dragonhawk Shoulderguards | 120 | 70 | 
| 24805 | Dragonhawk Bands | 120 | 70 | 
| 24878 | Der'izu Belt | 108 | 66 | 
| 24879 | Der'izu Greaves | 108 | 66 | 
| 24880 | Der'izu Chestpiece | 108 | 66 | 
| 24881 | Der'izu Fists | 108 | 66 | 
| 24882 | Der'izu Helm | 108 | 66 | 
| 24883 | Der'izu Legguards | 108 | 66 | 
| 24884 | Der'izu Spaulders | 108 | 66 | 
| 24885 | Der'izu Bracer | 108 | 66 | 
| 24886 | Skettis Belt | 111 | 67 | 
| 24887 | Skettis Footwraps | 111 | 67 | 
| 24888 | Skettis Chestpiece | 111 | 67 | 
| 24889 | Skettis Gauntlets | 111 | 67 | 
| 24890 | Skettis Helmet | 111 | 67 | 
| 24891 | Skettis Legguards | 111 | 67 | 
| 24892 | Skettis Spaulders | 111 | 67 | 
| 24893 | Skettis Bracer | 111 | 67 | 
| 24894 | Sundered Waistband | 114 | 68 | 
| 24895 | Sundered Footwraps | 114 | 68 | 
| 24896 | Sundered Chestpiece | 114 | 68 | 
| 24897 | Sundered Gauntlets | 114 | 68 | 
| 24898 | Sundered Helmet | 114 | 68 | 
| 24899 | Sundered Legguards | 114 | 68 | 
| 24900 | Sundered Spaulders | 114 | 68 | 
| 24901 | Tortured Bracer | 114 | 68 | 
| 24902 | Talhide Stitched-Belt | 117 | 69 | 
| 24903 | Talhide Lined-Boots | 117 | 69 | 
| 24904 | Talhide Chestpiece | 117 | 69 | 
| 24905 | Talhide Lined-Gloves | 117 | 69 | 
| 24906 | Talhide Helmet | 117 | 69 | 
| 24907 | Talhide Lined-Leggings | 117 | 69 | 
| 24908 | Talhide Shoulderguards | 117 | 69 | 
| 24909 | Talhide Lined-Bracers | 117 | 69 | 
| 24910 | Netherstorm Belt | 120 | 70 | 
| 24911 | Netherstorm Greaves | 120 | 70 | 
| 24912 | Netherstorm Chestpiece | 120 | 70 | 
| 24913 | Netherstorm Gauntlets | 120 | 70 | 
| 24914 | Netherstorm Helm | 120 | 70 | 
| 24915 | Netherstorm Legguards | 120 | 70 | 
| 24916 | Netherstorm Shoulderguards | 120 | 70 | 
| 24917 | Netherstorm Bracer | 120 | 70 | 
| 24990 | Warmaul Belt | 108 | 66 | 
| 24991 | Warmaul Greaves | 108 | 66 | 
| 24992 | Warmaul Breastplate | 108 | 66 | 
| 24993 | Warmaul Gloves | 108 | 66 | 
| 24994 | Warmaul Helmet | 108 | 66 | 
| 24995 | Warmaul Legplates | 108 | 66 | 
| 24996 | Warmaul Epaulets | 108 | 66 | 
| 24997 | Warmaul Vambraces | 108 | 66 | 
| 24998 | Bloodfist Girdle | 111 | 67 | 
| 24999 | Bloodfist Greaves | 111 | 67 | 
| 25000 | Bloodfist Breastplate | 111 | 67 | 
| 25001 | Bloodfist Gloves | 111 | 67 | 
| 25002 | Bloodfist Helmet | 111 | 67 | 
| 25003 | Bloodfist Legplates | 111 | 67 | 
| 25004 | Bloodfist Epaulets | 111 | 67 | 
| 25005 | Bloodfist Vambraces | 111 | 67 | 
| 25006 | Conqueror's Girdle | 114 | 68 | 
| 25007 | Conqueror's Greaves | 114 | 68 | 
| 25008 | Conqueror's Breastplate | 114 | 68 | 
| 25009 | Conqueror's Gauntlets | 114 | 68 | 
| 25010 | Conqueror's Helmet | 114 | 68 | 
| 25011 | Conqueror's Legplates | 114 | 68 | 
| 25012 | Conqueror's Epaulets | 114 | 68 | 
| 25013 | Conqueror's Vambraces | 114 | 68 | 
| 25014 | Shattered Hand Belt | 117 | 69 | 
| 25015 | Shattered Hand Sabatons | 117 | 69 | 
| 25016 | Shattered Hand Breastplate | 117 | 69 | 
| 25017 | Shattered Hand Gauntlets | 117 | 69 | 
| 25018 | Shattered Hand Helmet | 117 | 69 | 
| 25019 | Shattered Hand Legplates | 117 | 69 | 
| 25020 | Shattered Hand Epaulets | 117 | 69 | 
| 25021 | Shattered Hand Vambraces | 117 | 69 | 
| 25022 | Warlord's Iron-Girdle | 120 | 70 | 
| 25023 | Warlord's Sabatons | 120 | 70 | 
| 25024 | Warlord's Iron-Breastplate | 120 | 70 | 
| 25025 | Warlord's Iron-Gauntlets | 120 | 70 | 
| 25026 | Warlord's Iron-Helm | 120 | 70 | 
| 25027 | Warlord's Iron-Legplates | 120 | 70 | 
| 25028 | Warlord's Iron-Epaulets | 120 | 70 | 
| 25029 | Warlord's Iron-Vambraces | 120 | 70 | 
| 25039 | Farseer Cloak | 108 | 66 | 
| 25040 | Murkblood Cape | 111 | 67 | 
| 25041 | Ambusher's Cloak | 114 | 68 | 
| 25042 | Nether Cloak | 117 | 69 | 
| 25043 | Amber Cape | 120 | 70 | 
| 25053 | Lazuli Ring | 108 | 66 | 
| 25054 | Sodalite Band | 111 | 67 | 
| 25055 | Alexandrite Ring | 114 | 68 | 
| 25056 | Almandine Ring | 117 | 69 | 
| 25057 | Amber Band | 120 | 70 | 
| 25067 | Diopside Beads | 108 | 66 | 
| 25068 | Kunzite Necklace | 111 | 67 | 
| 25069 | Epidote Stone Necklace | 114 | 68 | 
| 25070 | Coral Beads | 117 | 69 | 
| 25071 | Tanzanite Pendant | 120 | 70 | 
| 25081 | Bayeaux Shield | 108 | 66 | 
| 25082 | Fel-Iron Shield | 111 | 67 | 
| 25083 | Smouldering Shield | 114 | 68 | 
| 25084 | Zeth'Gor Shield | 117 | 69 | 
| 25085 | Dragonscale Shield | 120 | 70 | 
| 25095 | Archmage Orb | 108 | 66 | 
| 25096 | Elementalist Star | 111 | 67 | 
| 25097 | Astralaan Orb | 114 | 68 | 
| 25098 | Tuurik Torch | 117 | 69 | 
| 25099 | Draenei Crystal Rod | 120 | 70 | 
| 25341 | Dilapidated Cloth Belt | 72 | 67 | 
| 25342 | Dilapidated Cloth Boots | 72 | 67 | 
| 25343 | Dilapidated Cloth Bracers | 72 | 67 | 
| 25344 | Dilapidated Cloth Gloves | 72 | 67 | 
| 25345 | Dilapidated Cloth Hat | 72 | 67 | 
| 25346 | Dilapidated Cloth Pants | 72 | 67 | 
| 25347 | Dilapidated Cloth Shoulderpads | 72 | 67 | 
| 25348 | Dilapidated Cloth Vest | 72 | 67 | 
| 25357 | Decaying Leather Armor | 72 | 67 | 
| 25358 | Decaying Leather Belt | 72 | 67 | 
| 25359 | Decaying Leather Boots | 72 | 67 | 
| 25360 | Decaying Leather Bracers | 72 | 67 | 
| 25361 | Decaying Leather Gloves | 72 | 67 | 
| 25362 | Decaying Leather Helmet | 72 | 67 | 
| 25363 | Decaying Leather Pants | 72 | 67 | 
| 25364 | Decaying Leather Shoulderpads | 72 | 67 | 
| 25373 | Corroded Mail Armor | 72 | 67 | 
| 25374 | Corroded Mail Belt | 72 | 67 | 
| 25375 | Corroded Mail Boots | 72 | 67 | 
| 25376 | Corroded Mail Bracers | 72 | 67 | 
| 25377 | Corroded Mail Circlet | 72 | 67 | 
| 25378 | Corroded Mail Gloves | 72 | 67 | 
| 25379 | Corroded Mail Pants | 72 | 67 | 
| 25380 | Corroded Mail Shoulderpads | 72 | 67 | 
| 25389 | Deteriorating Plate Belt | 72 | 67 | 
| 25390 | Deteriorating Plate Boots | 72 | 67 | 
| 25391 | Deteriorating Plate Bracers | 72 | 67 | 
| 25392 | Deteriorating Plate Chestpiece | 72 | 67 | 
| 25393 | Deteriorating Plate Gloves | 72 | 67 | 
| 25394 | Deteriorating Plate Helmet | 72 | 67 | 
| 25395 | Deteriorating Plate Pants | 72 | 67 | 
| 25396 | Deteriorating Plate Shoulderpads | 72 | 67 | 
| 31190 | The Dreamer's Shoulderpads | 97 | 68 | 
| 31237 | Elekk Hide Leggings | 103 | 66 | 
| 31240 | Scales of the Beast | 103 | 66 | 
| 31255 | Cloak of the Craft | 103 | 66 | 
| 31258 | Band of Sorrow | 103 | 66 | 
| 31272 | Crown of Endless Knowledge | 103 | 66 | 
| 31275 | Necklace of Trophies | 106 | 67 | 
| 31276 | Boots of Zealotry | 106 | 67 | 
| 31277 | Pathfinder's Band | 106 | 67 | 
| 31280 | Thundercaller's Gauntlets | 106 | 67 | 
| 31281 | Mask of Veiled Death | 106 | 67 | 
| 31282 | Shroud of Spiritual Purity | 106 | 67 | 
| 31283 | Sash of Sealed Fate | 106 | 67 | 
| 31284 | Bracers of Recklessness | 109 | 68 | 
| 31285 | Chestguard of the Talon | 109 | 68 | 
| 31286 | Breastplate of Rapid Striking | 109 | 68 | 
| 31287 | Draenei Honor Guard Shield | 109 | 68 | 
| 31288 | The Master's Treads | 109 | 68 | 
| 31290 | Band of Dominion | 109 | 70 | 
| 31292 | Crystal Pulse Shield | 112 | 69 | 
| 31293 | Girdle of Gale Force | 112 | 69 | 
| 31294 | Pauldrons of Surging Mana | 112 | 69 | 
| 31295 | Chestguard of the Dark Stalker | 112 | 69 | 
| 31297 | Robe of the Crimson Order | 112 | 69 | 
| 31298 | Legguards of the Shattered Hand | 115 | 70 | 
| 31306 | Leggings of the Sacred Crest | 115 | 70 | 

</details>

24653, 24654, 24655, 24656, 24657, 24658, 24659, 24660, 24661, 24662, 24663, 24664, 24665, 24666, 24667, 24668, 24669, 24670, 24671, 24672, 24673, 24674, 24675, 24676, 24677, 24678, 24679, 24680, 24681, 24682, 24683, 24684, 24685, 24686, 24687, 24688, 24689, 24690, 24691, 24692, 24765, 24766, 24767, 24768, 24769, 24770, 24771, 24772, 24773, 24774, 24775, 24776, 24777, 24778, 24779, 24780, 24781, 24783, 24784, 24785, 24786, 24787, 24788, 24789, 24790, 24791, 24792, 24793, 24794, 24795, 24796, 24797, 24798, 24799, 24800, 24801, 24802, 24803, 24804, 24805, 24878, 24879, 24880, 24881, 24882, 24883, 24884, 24885, 24886, 24887, 24888, 24889, 24890, 24891, 24892, 24893, 24894, 24895, 24896, 24897, 24898, 24899, 24900, 24901, 24902, 24903, 24904, 24905, 24906, 24907, 24908, 24909, 24910, 24911, 24912, 24913, 24914, 24915, 24916, 24917, 24990, 24991, 24992, 24993, 24994, 24995, 24996, 24997, 24998, 24999, 25000, 25001, 25002, 25003, 25004, 25005, 25006, 25007, 25008, 25009, 25010, 25011, 25012, 25013, 25014, 25015, 25016, 25017, 25018, 25019, 25020, 25021, 25022, 25023, 25024, 25025, 25026, 25027, 25028, 25029, 25039, 25040, 25041, 25042, 25043, 25053, 25054, 25055, 25056, 25057, 25067, 25068, 25069, 25070, 25071, 25081, 25082, 25083, 25084, 25085, 25095, 25096, 25097, 25098, 25099, 25341, 25342, 25343, 25344, 25345, 25346, 25347, 25348, 25357, 25358, 25359, 25360, 25361, 25362, 25363, 25364, 25373, 25374, 25375, 25376, 25377, 25378, 25379, 25380, 25389, 25390, 25391, 25392, 25393, 25394, 25395, 25396, 31190, 31237, 31240, 31255, 31258, 31272, 31275, 31276, 31277, 31280, 31281, 31282, 31283, 31284, 31285, 31286, 31287, 31288, 31290, 31292, 31293, 31294, 31295, 31297, 31298, 31306

<hr>

Kara armour:
```SQL
SELECT DISTINCT( it.entry), it.name, it.itemlevel, it.RequiredLevel
FROM `creature_template` ct
JOIN `creature_loot_template` clt ON ct.lootid = clt.entry
JOIN `reference_loot_template` rlt ON clt.Reference = rlt.Entry
JOIN `item_template` it ON it.entry = rlt.Item
WHERE ct.entry IN (7370, 12377, 12378, 12379, 12380) AND it.class = 4 AND it.entry >= 24637
```

<details>
<summary>Results</summary>

---
| entry | name | itemlevel | RequiredLevel | 
| ---: | --- | ---: | ---: | 
| 24637 | Mistyreed Belt | 102 | 64 | 
| 24638 | Mistyreed Boots | 102 | 64 | 
| 24639 | Mistyreed Tunic | 102 | 64 | 
| 24640 | Mistyreed Gloves | 102 | 64 | 
| 24641 | Mistyreed Hood | 102 | 64 | 
| 24642 | Mistyreed Pants | 102 | 64 | 
| 24643 | Mistyreed Shoulderpads | 102 | 64 | 
| 24644 | Mistyreed Bracers | 102 | 64 | 
| 24645 | Astralaan Belt | 105 | 65 | 
| 24646 | Astralaan Boots | 105 | 65 | 
| 24647 | Astralaan Robe | 105 | 65 | 
| 24648 | Astralaan Gloves | 105 | 65 | 
| 24649 | Astralaan Headdress | 105 | 65 | 
| 24650 | Astralaan Pants | 105 | 65 | 
| 24651 | Astralaan Shoulderpads | 105 | 65 | 
| 24652 | Astralaan Bracer | 105 | 65 | 
| 24653 | Consortium Sash | 108 | 66 | 
| 24654 | Consortium Boot | 108 | 66 | 
| 24655 | Consortium Robe | 108 | 66 | 
| 24656 | Consortium Gloves | 108 | 66 | 
| 24657 | Consortium Hood | 108 | 66 | 
| 24658 | Consortium Pants | 108 | 66 | 
| 24659 | Consortium Mantle | 108 | 66 | 
| 24660 | Consortium Bracer | 108 | 66 | 
| 24661 | Shadow Council Chain | 111 | 67 | 
| 24662 | Shadow Council Boots | 111 | 67 | 
| 24663 | Shadow Council Tunic | 111 | 67 | 
| 24664 | Shadow Council Gloves | 111 | 67 | 
| 24665 | Shadow Council Cowl | 111 | 67 | 
| 24666 | Shadow Council Pants | 111 | 67 | 
| 24667 | Shadow Council Mantle | 111 | 67 | 
| 24668 | Shadow Council Bracer | 111 | 67 | 
| 24669 | Eldr'naan Belt | 114 | 68 | 
| 24670 | Eldr'naan Boots | 114 | 68 | 
| 24671 | Eldr'naan Jerkin | 114 | 68 | 
| 24672 | Eldr'naan Gloves | 114 | 68 | 
| 24673 | Eldr'naan Hood | 114 | 68 | 
| 24674 | Eldr'naan Pants | 114 | 68 | 
| 24675 | Eldr'naan Shoulderpads | 114 | 68 | 
| 24676 | Eldr'naan Bracelets | 114 | 68 | 
| 24677 | Archmage Belt | 117 | 69 | 
| 24678 | Archmage Slippers | 117 | 69 | 
| 24679 | Archmage Robe | 117 | 69 | 
| 24680 | Archmage Gloves | 117 | 69 | 
| 24681 | Archmage Headpiece | 117 | 69 | 
| 24682 | Archmage Pants | 117 | 69 | 
| 24683 | Archmage Mantle | 117 | 69 | 
| 24684 | Archmage Bracelets | 117 | 69 | 
| 24749 | Daggerfen Belt | 102 | 64 | 
| 24750 | Daggerfen Boots | 102 | 64 | 
| 24751 | Daggerfen Battlevest | 102 | 64 | 
| 24752 | Daggerfen Gloves | 102 | 64 | 
| 24753 | Daggerfen Cowl | 102 | 64 | 
| 24754 | Daggerfen Stitchpants | 102 | 64 | 
| 24755 | Daggerfen Pauldrons | 102 | 64 | 
| 24756 | Daggerfen Bindings | 102 | 64 | 
| 24757 | Umbrafen Waistband | 105 | 65 | 
| 24758 | Umbrafen Boots | 105 | 65 | 
| 24759 | Umbrafen Tunic | 105 | 65 | 
| 24760 | Umbrafen Gloves | 105 | 65 | 
| 24761 | Umbrafen Cap | 105 | 65 | 
| 24762 | Umbrafen Britches | 105 | 65 | 
| 24763 | Umbrafen Shoulderguards | 105 | 65 | 
| 24764 | Umbrafen Bindings | 105 | 65 | 
| 24765 | Clefthoof Belt | 108 | 66 | 
| 24766 | Clefthoof Wanderboots | 108 | 66 | 
| 24767 | Clefthoof Hidemantle | 108 | 66 | 
| 24768 | Clefthoof Gloves | 108 | 66 | 
| 24769 | Clefthoof Cover | 108 | 66 | 
| 24770 | Clefthoof Britches | 108 | 66 | 
| 24771 | Clefthoof Shoulderguards | 108 | 66 | 
| 24772 | Clefthoof Bracers | 108 | 66 | 
| 24773 | Boneshredder Belt | 111 | 67 | 
| 24774 | Boneshredder Boots | 111 | 67 | 
| 24775 | Boneshredder Jerkin | 111 | 67 | 
| 24776 | Boneshredder Gloves | 111 | 67 | 
| 24777 | Boneshredder Skullcap | 111 | 67 | 
| 24778 | Boneshredder Britches | 111 | 67 | 
| 24779 | Boneshredder Shoulderguards | 111 | 67 | 
| 24780 | Boneshredder Wristguards | 111 | 67 | 
| 24781 | Murkblood Belt | 114 | 68 | 
| 24783 | Murkblood Boots | 114 | 68 | 
| 24784 | Murkblood Chestpiece | 114 | 68 | 
| 24785 | Murkblood Gloves | 114 | 68 | 
| 24786 | Murkblood Cover | 114 | 68 | 
| 24787 | Murkblood Pants | 114 | 68 | 
| 24788 | Murkblood Shoulderguards | 114 | 68 | 
| 24789 | Murkblood Bracers | 114 | 68 | 
| 24790 | Expedition Girdle | 117 | 69 | 
| 24791 | Expedition Boots | 117 | 69 | 
| 24792 | Expedition Tunic | 117 | 69 | 
| 24793 | Expedition Gloves | 117 | 69 | 
| 24794 | Expedition Hood | 117 | 69 | 
| 24795 | Expedition Pants | 117 | 69 | 
| 24796 | Expedition Shoulderguards | 117 | 69 | 
| 24797 | Expedition Bracers | 117 | 69 | 
| 24862 | Blood Knight Girdle | 102 | 64 | 
| 24863 | Blood Knight Boots | 102 | 64 | 
| 24864 | Blood Knight Breastplate | 102 | 64 | 
| 24865 | Blood Knight Gauntlets | 102 | 64 | 
| 24866 | Blood Knight Helm | 102 | 64 | 
| 24867 | Blood Knight Greaves | 102 | 64 | 
| 24868 | Blood Knight Pauldrons | 102 | 64 | 
| 24869 | Blood Knight Bracers | 102 | 64 | 
| 24870 | Ironspine Belt | 105 | 65 | 
| 24871 | Ironspine Greaves | 105 | 65 | 
| 24872 | Ironspine Chain Vest | 105 | 65 | 
| 24873 | Ironspine Gloves | 105 | 65 | 
| 24874 | Ironspine Helm | 105 | 65 | 
| 24875 | Ironspine Legguards | 105 | 65 | 
| 24876 | Ironspine Shoulderguards | 105 | 65 | 
| 24877 | Ironspine Bracelets | 105 | 65 | 
| 24878 | Der'izu Belt | 108 | 66 | 
| 24879 | Der'izu Greaves | 108 | 66 | 
| 24880 | Der'izu Chestpiece | 108 | 66 | 
| 24881 | Der'izu Fists | 108 | 66 | 
| 24882 | Der'izu Helm | 108 | 66 | 
| 24883 | Der'izu Legguards | 108 | 66 | 
| 24884 | Der'izu Spaulders | 108 | 66 | 
| 24885 | Der'izu Bracer | 108 | 66 | 
| 24886 | Skettis Belt | 111 | 67 | 
| 24887 | Skettis Footwraps | 111 | 67 | 
| 24888 | Skettis Chestpiece | 111 | 67 | 
| 24889 | Skettis Gauntlets | 111 | 67 | 
| 24890 | Skettis Helmet | 111 | 67 | 
| 24891 | Skettis Legguards | 111 | 67 | 
| 24892 | Skettis Spaulders | 111 | 67 | 
| 24893 | Skettis Bracer | 111 | 67 | 
| 24894 | Sundered Waistband | 114 | 68 | 
| 24895 | Sundered Footwraps | 114 | 68 | 
| 24896 | Sundered Chestpiece | 114 | 68 | 
| 24897 | Sundered Gauntlets | 114 | 68 | 
| 24898 | Sundered Helmet | 114 | 68 | 
| 24899 | Sundered Legguards | 114 | 68 | 
| 24900 | Sundered Spaulders | 114 | 68 | 
| 24901 | Tortured Bracer | 114 | 68 | 
| 24902 | Talhide Stitched-Belt | 117 | 69 | 
| 24903 | Talhide Lined-Boots | 117 | 69 | 
| 24904 | Talhide Chestpiece | 117 | 69 | 
| 24905 | Talhide Lined-Gloves | 117 | 69 | 
| 24906 | Talhide Helmet | 117 | 69 | 
| 24907 | Talhide Lined-Leggings | 117 | 69 | 
| 24908 | Talhide Shoulderguards | 117 | 69 | 
| 24909 | Talhide Lined-Bracers | 117 | 69 | 
| 24974 | Reaver Girdle | 102 | 64 | 
| 24975 | Reaver Greaves | 102 | 64 | 
| 24976 | Reaver Armor | 102 | 64 | 
| 24977 | Reaver Gloves | 102 | 64 | 
| 24978 | Reaver Helmet | 102 | 64 | 
| 24979 | Reaver Legplates | 102 | 64 | 
| 24980 | Reaver Epaulets | 102 | 64 | 
| 24981 | Reaver Bracers | 102 | 64 | 
| 24982 | Boulderfist Belt | 105 | 65 | 
| 24983 | Boulderfist Greaves | 105 | 65 | 
| 24984 | Boulderfist Armor | 105 | 65 | 
| 24985 | Boulderfist Gloves | 105 | 65 | 
| 24986 | Boulderfist Helm | 105 | 65 | 
| 24987 | Boulderfist Legplates | 105 | 65 | 
| 24988 | Boulderfist Epaulets | 105 | 65 | 
| 24989 | Boulderfist Bracers | 105 | 65 | 
| 24990 | Warmaul Belt | 108 | 66 | 
| 24991 | Warmaul Greaves | 108 | 66 | 
| 24992 | Warmaul Breastplate | 108 | 66 | 
| 24993 | Warmaul Gloves | 108 | 66 | 
| 24994 | Warmaul Helmet | 108 | 66 | 
| 24995 | Warmaul Legplates | 108 | 66 | 
| 24996 | Warmaul Epaulets | 108 | 66 | 
| 24997 | Warmaul Vambraces | 108 | 66 | 
| 24998 | Bloodfist Girdle | 111 | 67 | 
| 24999 | Bloodfist Greaves | 111 | 67 | 
| 25000 | Bloodfist Breastplate | 111 | 67 | 
| 25001 | Bloodfist Gloves | 111 | 67 | 
| 25002 | Bloodfist Helmet | 111 | 67 | 
| 25003 | Bloodfist Legplates | 111 | 67 | 
| 25004 | Bloodfist Epaulets | 111 | 67 | 
| 25005 | Bloodfist Vambraces | 111 | 67 | 
| 25006 | Conqueror's Girdle | 114 | 68 | 
| 25007 | Conqueror's Greaves | 114 | 68 | 
| 25008 | Conqueror's Breastplate | 114 | 68 | 
| 25009 | Conqueror's Gauntlets | 114 | 68 | 
| 25010 | Conqueror's Helmet | 114 | 68 | 
| 25011 | Conqueror's Legplates | 114 | 68 | 
| 25012 | Conqueror's Epaulets | 114 | 68 | 
| 25013 | Conqueror's Vambraces | 114 | 68 | 
| 25014 | Shattered Hand Belt | 117 | 69 | 
| 25015 | Shattered Hand Sabatons | 117 | 69 | 
| 25016 | Shattered Hand Breastplate | 117 | 69 | 
| 25017 | Shattered Hand Gauntlets | 117 | 69 | 
| 25018 | Shattered Hand Helmet | 117 | 69 | 
| 25019 | Shattered Hand Legplates | 117 | 69 | 
| 25020 | Shattered Hand Epaulets | 117 | 69 | 
| 25021 | Shattered Hand Vambraces | 117 | 69 | 
| 25037 | Patched Cape | 102 | 64 | 
| 25038 | Forest Shroud | 105 | 65 | 
| 25039 | Farseer Cloak | 108 | 66 | 
| 25040 | Murkblood Cape | 111 | 67 | 
| 25041 | Ambusher's Cloak | 114 | 68 | 
| 25042 | Nether Cloak | 117 | 69 | 
| 25051 | Blue Topaz Band | 102 | 64 | 
| 25052 | Hauyne Ring | 105 | 65 | 
| 25053 | Lazuli Ring | 108 | 66 | 
| 25054 | Sodalite Band | 111 | 67 | 
| 25055 | Alexandrite Ring | 114 | 68 | 
| 25056 | Almandine Ring | 117 | 69 | 
| 25065 | Turquoise Brooch | 102 | 64 | 
| 25066 | Pink Sapphire Necklace | 105 | 65 | 
| 25067 | Diopside Beads | 108 | 66 | 
| 25068 | Kunzite Necklace | 111 | 67 | 
| 25069 | Epidote Stone Necklace | 114 | 68 | 
| 25070 | Coral Beads | 117 | 69 | 
| 25079 | Outland Shield | 102 | 64 | 
| 25080 | Spell-Breaker Shield | 105 | 65 | 
| 25081 | Bayeaux Shield | 108 | 66 | 
| 25082 | Fel-Iron Shield | 111 | 67 | 
| 25083 | Smouldering Shield | 114 | 68 | 
| 25084 | Zeth'Gor Shield | 117 | 69 | 
| 25093 | Shadow Council Orb | 102 | 64 | 
| 25094 | Eldr'naan Scepter | 105 | 65 | 
| 25095 | Archmage Orb | 108 | 66 | 
| 25096 | Elementalist Star | 111 | 67 | 
| 25097 | Astralaan Orb | 114 | 68 | 
| 25098 | Tuurik Torch | 117 | 69 | 
| 25341 | Dilapidated Cloth Belt | 72 | 67 | 
| 25342 | Dilapidated Cloth Boots | 72 | 67 | 
| 25343 | Dilapidated Cloth Bracers | 72 | 67 | 
| 25344 | Dilapidated Cloth Gloves | 72 | 67 | 
| 25345 | Dilapidated Cloth Hat | 72 | 67 | 
| 25346 | Dilapidated Cloth Pants | 72 | 67 | 
| 25347 | Dilapidated Cloth Shoulderpads | 72 | 67 | 
| 25348 | Dilapidated Cloth Vest | 72 | 67 | 
| 25357 | Decaying Leather Armor | 72 | 67 | 
| 25358 | Decaying Leather Belt | 72 | 67 | 
| 25359 | Decaying Leather Boots | 72 | 67 | 
| 25360 | Decaying Leather Bracers | 72 | 67 | 
| 25361 | Decaying Leather Gloves | 72 | 67 | 
| 25362 | Decaying Leather Helmet | 72 | 67 | 
| 25363 | Decaying Leather Pants | 72 | 67 | 
| 25364 | Decaying Leather Shoulderpads | 72 | 67 | 
| 25373 | Corroded Mail Armor | 72 | 67 | 
| 25374 | Corroded Mail Belt | 72 | 67 | 
| 25375 | Corroded Mail Boots | 72 | 67 | 
| 25376 | Corroded Mail Bracers | 72 | 67 | 
| 25377 | Corroded Mail Circlet | 72 | 67 | 
| 25378 | Corroded Mail Gloves | 72 | 67 | 
| 25379 | Corroded Mail Pants | 72 | 67 | 
| 25380 | Corroded Mail Shoulderpads | 72 | 67 | 
| 25389 | Deteriorating Plate Belt | 72 | 67 | 
| 25390 | Deteriorating Plate Boots | 72 | 67 | 
| 25391 | Deteriorating Plate Bracers | 72 | 67 | 
| 25392 | Deteriorating Plate Chestpiece | 72 | 67 | 
| 25393 | Deteriorating Plate Gloves | 72 | 67 | 
| 25394 | Deteriorating Plate Helmet | 72 | 67 | 
| 25395 | Deteriorating Plate Pants | 72 | 67 | 
| 25396 | Deteriorating Plate Shoulderpads | 72 | 67 | 
| 31190 | The Dreamer's Shoulderpads | 97 | 68 | 
| 31284 | Bracers of Recklessness | 109 | 68 | 
| 31285 | Chestguard of the Talon | 109 | 68 | 
| 31286 | Breastplate of Rapid Striking | 109 | 68 | 
| 31287 | Draenei Honor Guard Shield | 109 | 68 | 
| 31288 | The Master's Treads | 109 | 68 | 
| 31290 | Band of Dominion | 109 | 70 | 
| 31292 | Crystal Pulse Shield | 112 | 69 | 
| 31293 | Girdle of Gale Force | 112 | 69 | 
| 31294 | Pauldrons of Surging Mana | 112 | 69 | 
| 31295 | Chestguard of the Dark Stalker | 112 | 69 | 
| 31297 | Robe of the Crimson Order | 112 | 69 | 
| 31298 | Legguards of the Shattered Hand | 115 | 70 | 
| 31306 | Leggings of the Sacred Crest | 115 | 70 | 

</details>

24637, 24638, 24639, 24640, 24641, 24642, 24643, 24644, 24645, 24646, 24647, 24648, 24649, 24650, 24651, 24652, 24653, 24654, 24655, 24656, 24657, 24658, 24659, 24660, 24661, 24662, 24663, 24664, 24665, 24666, 24667, 24668, 24669, 24670, 24671, 24672, 24673, 24674, 24675, 24676, 24677, 24678, 24679, 24680, 24681, 24682, 24683, 24684, 24749, 24750, 24751, 24752, 24753, 24754, 24755, 24756, 24757, 24758, 24759, 24760, 24761, 24762, 24763, 24764, 24765, 24766, 24767, 24768, 24769, 24770, 24771, 24772, 24773, 24774, 24775, 24776, 24777, 24778, 24779, 24780, 24781, 24783, 24784, 24785, 24786, 24787, 24788, 24789, 24790, 24791, 24792, 24793, 24794, 24795, 24796, 24797, 24862, 24863, 24864, 24865, 24866, 24867, 24868, 24869, 24870, 24871, 24872, 24873, 24874, 24875, 24876, 24877, 24878, 24879, 24880, 24881, 24882, 24883, 24884, 24885, 24886, 24887, 24888, 24889, 24890, 24891, 24892, 24893, 24894, 24895, 24896, 24897, 24898, 24899, 24900, 24901, 24902, 24903, 24904, 24905, 24906, 24907, 24908, 24909, 24974, 24975, 24976, 24977, 24978, 24979, 24980, 24981, 24982, 24983, 24984, 24985, 24986, 24987, 24988, 24989, 24990, 24991, 24992, 24993, 24994, 24995, 24996, 24997, 24998, 24999, 25000, 25001, 25002, 25003, 25004, 25005, 25006, 25007, 25008, 25009, 25010, 25011, 25012, 25013, 25014, 25015, 25016, 25017, 25018, 25019, 25020, 25021, 25037, 25038, 25039, 25040, 25041, 25042, 25051, 25052, 25053, 25054, 25055, 25056, 25065, 25066, 25067, 25068, 25069, 25070, 25079, 25080, 25081, 25082, 25083, 25084, 25093, 25094, 25095, 25096, 25097, 25098, 25341, 25342, 25343, 25344, 25345, 25346, 25347, 25348, 25357, 25358, 25359, 25360, 25361, 25362, 25363, 25364, 25373, 25374, 25375, 25376, 25377, 25378, 25379, 25380, 25389, 25390, 25391, 25392, 25393, 25394, 25395, 25396, 31190, 31284, 31285, 31286, 31287, 31288, 31290, 31292, 31293, 31294, 31295, 31297, 31298, 31306
