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

### Generic Outland Armour
These are all >= ilvl 55, quality green or better, not also dropping in old world.

<details>
<summary>Results</summary>
  
---
| entry | name | RequiredLevel | 
| ---: | --- | ---: | 
| 24597 | Starfire Sash | 59 | 
| 24598 | Starfire Sandals | 59 | 
| 24599 | Starfire Vest | 59 | 
| 24600 | Starfire Gloves | 59 | 
| 24601 | Starfire Circlet | 59 | 
| 24602 | Starfire Trousers | 59 | 
| 24603 | Starfire Mantle | 59 | 
| 24604 | Starfire Wristwraps | 59 | 
| 24605 | Laughing Skull Waistguard | 60 | 
| 24606 | Laughing Skull Boot | 60 | 
| 24607 | Laughing Skull Tunic | 60 | 
| 24608 | Laughing Skull Gloves | 60 | 
| 24609 | Laughing Skull Cap | 60 | 
| 24610 | Laughing Skull Pants | 60 | 
| 24611 | Laughing Skull Shoulderpads | 60 | 
| 24612 | Laughing Skull Bracelets | 60 | 
| 24613 | Vindicator Belt | 61 | 
| 24614 | Vindicator Boots | 61 | 
| 24615 | Vindicator Tunic | 61 | 
| 24616 | Vindicator Gloves | 61 | 
| 24617 | Vindicator Cap | 61 | 
| 24618 | Vindicator Pants | 61 | 
| 24619 | Vindicator Shoulderpads | 61 | 
| 24620 | Vindicator Bracers | 61 | 
| 24621 | Slavehandler Belt | 62 | 
| 24622 | Slavehandler Footpads | 62 | 
| 24623 | Slavehandler Jerkin | 62 | 
| 24624 | Slavehandler Handwraps | 62 | 
| 24625 | Slavehandler Cap | 62 | 
| 24626 | Slavehandler Pants | 62 | 
| 24627 | Slavehandler Amice | 62 | 
| 24628 | Slavehandler Wristguards | 62 | 
| 24629 | Feralfen Sash | 63 | 
| 24630 | Feralfen Sandals | 63 | 
| 24631 | Feralfen Jerkin | 63 | 
| 24632 | Feralfen Hand | 63 | 
| 24633 | Feralfen Hood | 63 | 
| 24634 | Feralfen Pants | 63 | 
| 24635 | Feralfen Amice | 63 | 
| 24636 | Feralfen Cuffs | 63 | 
| 24685 | Elementalist Belt | 70 | 
| 24686 | Elementalist Boots | 70 | 
| 24687 | Elementalist Tunic | 70 | 
| 24688 | Elementalist Gloves | 70 | 
| 24689 | Elementalist Skullcap | 70 | 
| 24690 | Elementalist Leggings | 70 | 
| 24691 | Elementalist Mantle | 70 | 
| 24692 | Elementalist Bracelets | 70 | 
| 24710 | Vengeance Boots | 59 | 
| 24711 | Vengeance Chestpiece | 59 | 
| 24712 | Vengeance Gloves | 59 | 
| 24713 | Vengeance Helm | 59 | 
| 24714 | Vengeance Legguards | 59 | 
| 24715 | Vengeance Pauldrons | 59 | 
| 24716 | Vengeance Bands | 59 | 
| 24717 | Dreghood Belt | 60 | 
| 24718 | Dreghood Boots | 60 | 
| 24719 | Dreghood Chestpiece | 60 | 
| 24720 | Dreghood Gloves | 60 | 
| 24721 | Dreghood Cowl | 60 | 
| 24722 | Dreghood Trousers | 60 | 
| 24723 | Dreghood Pauldrons | 60 | 
| 24724 | Dreghood Bands | 60 | 
| 24725 | Dementia Cord | 61 | 
| 24726 | Dementia Boots | 61 | 
| 24727 | Dementia Vest | 61 | 
| 24728 | Dementia Gloves | 61 | 
| 24729 | Dementia Hood | 61 | 
| 24730 | Dementia Trousers | 61 | 
| 24731 | Dementia Shoulderguards | 61 | 
| 24732 | Dementia Armguards | 61 | 
| 24733 | Sunroc Waistband | 62 | 
| 24734 | Sunroc Boots | 62 | 
| 24735 | Sunroc Chestpiece | 62 | 
| 24736 | Sunroc Gloves | 62 | 
| 24737 | Sunroc Mask | 62 | 
| 24738 | Sunroc Pants | 62 | 
| 24739 | Sunroc Shoulderguards | 62 | 
| 24740 | Sunroc Armguards | 62 | 
| 24741 | Ranger Belt | 63 | 
| 24742 | Ranger Boots | 63 | 
| 24743 | Ranger Jerkin | 63 | 
| 24744 | Ranger Gloves | 63 | 
| 24745 | Ranger Hat | 63 | 
| 24746 | Ranger Pants | 63 | 
| 24747 | Ranger Pauldrons | 63 | 
| 24748 | Ranger Armguards | 63 | 
| 24798 | Dragonhawk Belt | 70 | 
| 24799 | Dragonhawk Boots | 70 | 
| 24800 | Dragonhawk Tunic | 70 | 
| 24801 | Dragonhawk Gloves | 70 | 
| 24802 | Dragonhawk Hat | 70 | 
| 24803 | Dragonhawk Pants | 70 | 
| 24804 | Dragonhawk Shoulderguards | 70 | 
| 24805 | Dragonhawk Bands | 70 | 
| 24822 | Netherstalker Belt | 59 | 
| 24823 | Netherstalker Greaves | 59 | 
| 24824 | Netherstalker Armor | 59 | 
| 24825 | Netherstalker Gloves | 59 | 
| 24826 | Netherstalker Helmet | 59 | 
| 24827 | Netherstalker Legguards | 59 | 
| 24828 | Netherstalker Mantle | 59 | 
| 24829 | Netherstalker Bracer | 59 | 
| 24830 | Nexus-Strider Belt | 60 | 
| 24831 | Nexus-Strider Greaves | 60 | 
| 24832 | Nexus-Strider Breastplate | 60 | 
| 24833 | Nexus-Strider Gloves | 60 | 
| 24834 | Nexus-Strider Helmet | 60 | 
| 24835 | Nexus-Strider Legwraps | 60 | 
| 24836 | Nexus-Strider Mantle | 60 | 
| 24837 | Nexus-Strider Bracer | 60 | 
| 24838 | Wrathfin Waistband | 61 | 
| 24839 | Wrathfin Greaves | 61 | 
| 24840 | Wrathfin Armor | 61 | 
| 24841 | Wrathfin Gloves | 61 | 
| 24842 | Wrathfin Helmet | 61 | 
| 24843 | Wrathfin Legguards | 61 | 
| 24844 | Wrathfin Mantle | 61 | 
| 24845 | Wrathfin Bindings | 61 | 
| 24846 | Fenclaw Waistband | 62 | 
| 24847 | Fenclaw Footwraps | 62 | 
| 24848 | Fenclaw Armor | 62 | 
| 24849 | Fenclaw Fists | 62 | 
| 24850 | Fenclaw Helm | 62 | 
| 24851 | Fenclaw Legguards | 62 | 
| 24852 | Fenclaw Mantle | 62 | 
| 24853 | Fenclaw Bindings | 62 | 
| 24854 | Marshcreeper Belt | 63 | 
| 24855 | Marshcreeper Sludgeboots | 63 | 
| 24856 | Marshcreeper Fen-Vest | 63 | 
| 24857 | Marshcreeper Gloves | 63 | 
| 24858 | Marshcreeper Helm | 63 | 
| 24859 | Marshcreeper Leggings | 63 | 
| 24860 | Marshcreeper Mantle | 63 | 
| 24861 | Marshcreeper Bracelets | 63 | 
| 24910 | Netherstorm Belt | 70 | 
| 24911 | Netherstorm Greaves | 70 | 
| 24912 | Netherstorm Chestpiece | 70 | 
| 24913 | Netherstorm Gauntlets | 70 | 
| 24914 | Netherstorm Helm | 70 | 
| 24915 | Netherstorm Legguards | 70 | 
| 24916 | Netherstorm Shoulderguards | 70 | 
| 24917 | Netherstorm Bracer | 70 | 
| 24934 | Darkcrest Belt | 59 | 
| 24935 | Darkcrest Sabatons | 59 | 
| 24936 | Darkcrest Breastplate | 59 | 
| 24937 | Darkcrest Gauntlets | 59 | 
| 24938 | Darkcrest Helm | 59 | 
| 24939 | Darkcrest Legguards | 59 | 
| 24940 | Darkcrest Pauldrons | 59 | 
| 24941 | Darkcrest Bracers | 59 | 
| 24942 | Bloodscale Belt | 60 | 
| 24943 | Bloodscale Sabatons | 60 | 
| 24944 | Bloodscale Breastplate | 60 | 
| 24945 | Bloodscale Gauntlets | 60 | 
| 24946 | Bloodscale Helm | 60 | 
| 24947 | Bloodscale Legguards | 60 | 
| 24948 | Bloodscale Pauldrons | 60 | 
| 24949 | Bloodscale Bracers | 60 | 
| 24950 | Bogslayer Belt | 61 | 
| 24951 | Bogslayer Sabatons | 61 | 
| 24952 | Bogslayer Breastplate | 61 | 
| 24953 | Bogslayer Gauntlets | 61 | 
| 24954 | Bogslayer Helm | 61 | 
| 24955 | Bogslayer Legplates | 61 | 
| 24956 | Bogslayer Pauldrons | 61 | 
| 24957 | Bogslayer Bracers | 61 | 
| 24958 | Khan'aish Girdle | 62 | 
| 24959 | Khan'aish Greaves | 62 | 
| 24960 | Khan'aish Breastplate | 62 | 
| 24961 | Khan'aish Gloves | 62 | 
| 24962 | Khan'aish Helmet | 62 | 
| 24963 | Khan'aish Legplates | 62 | 
| 24964 | Khan'aish Epaulets | 62 | 
| 24965 | Khan'aish Bracers | 62 | 
| 24966 | Talonguard Girdle | 63 | 
| 24967 | Talonguard Greaves | 63 | 
| 24968 | Talonguard Armor | 63 | 
| 24969 | Talonguard Gloves | 63 | 
| 24970 | Talonguard Helmet | 63 | 
| 24971 | Talonguard Legplates | 63 | 
| 24972 | Talonguard Epaulets | 63 | 
| 24973 | Talonguard Bracers | 63 | 
| 25022 | Warlord's Iron-Girdle | 70 | 
| 25023 | Warlord's Sabatons | 70 | 
| 25024 | Warlord's Iron-Breastplate | 70 | 
| 25025 | Warlord's Iron-Gauntlets | 70 | 
| 25026 | Warlord's Iron-Helm | 70 | 
| 25027 | Warlord's Iron-Legplates | 70 | 
| 25028 | Warlord's Iron-Epaulets | 70 | 
| 25029 | Warlord's Iron-Vambraces | 70 | 
| 25032 | Hellfire Cloak | 59 | 
| 25033 | Scavenger's Cloak | 60 | 
| 25034 | Elementalist Cloak | 61 | 
| 25035 | Silver-Lined Cloak | 62 | 
| 25036 | Boulderfist Cloak | 63 | 
| 25043 | Amber Cape | 70 | 
| 25046 | Spined Ring | 59 | 
| 25047 | Tourmaline Loop | 60 | 
| 25048 | Smoky Quartz Ring | 61 | 
| 25049 | Scheelite Ring | 62 | 
| 25050 | Moldavite Ring | 63 | 
| 25057 | Amber Band | 70 | 
| 25060 | Sunstone Necklace | 59 | 
| 25061 | Hiddenite Necklace | 60 | 
| 25062 | Zircon Amulet | 61 | 
| 25063 | Multi-Colored Beads | 62 | 
| 25064 | Amethyst Pendant | 63 | 
| 25071 | Tanzanite Pendant | 70 | 
| 25074 | Telaari Shield | 59 | 
| 25075 | Hardened Steel Shield | 60 | 
| 25076 | Screaming Shield | 61 | 
| 25077 | Modani War-Shield | 62 | 
| 25078 | Zangari Shield | 63 | 
| 25085 | Dragonscale Shield | 70 | 
| 25088 | Laughing Skull Orb | 59 | 
| 25089 | Supplicant's Rod | 60 | 
| 25090 | Slavehandler Rod | 61 | 
| 25091 | Mistyreed Torch | 62 | 
| 25092 | Consortium Crystal | 63 | 
| 25099 | Draenei Crystal Rod | 70 | 
| 30520 | Gold-Trimmed Cuffs | 0 | 
| 30725 | Anger-Spark Gloves | 70 | 
| 30726 | Archaic Charm of Presence | 70 | 
| 30727 | Gilded Trousers of Benediction | 70 | 
| 30728 | Fathom-Helm of the Deeps | 70 | 
| 30729 | Black-Iron Battlecloak | 70 | 
| 30730 | Terrorweave Tunic | 70 | 
| 30731 | Faceguard of the Endless Watch | 70 | 
| 30734 | Leggings of the Seventh Circle | 70 | 
| 30735 | Ancient Spellcloak of the Highborne | 70 | 
| 30736 | Ring of Flowing Light | 70 | 
| 30737 | Gold-Leaf Wildboots | 70 | 
| 30738 | Ring of Reciprocity | 70 | 
| 30739 | Scaled Greaves of the Marksman | 70 | 
| 30740 | Ripfiend Shoulderplates | 70 | 
| 30741 | Topaz-Studded Battlegrips | 70 | 
| 30986 | Bloodforged Guard | 0 | 
| 31125 | Boots of the Decimator | 60 | 
| 31126 | Gloves of Ferocity | 60 | 
| 31127 | Hauberk of Totemic Rage | 60 | 
| 31131 | Sash of Silent Blades | 60 | 
| 31133 | Leggings of Concentrated Darkness | 60 | 
| 31136 | Breastplate of Blade Turning | 61 | 
| 31137 | Gauntlets of Purification | 61 | 
| 31138 | Storm Lord's Girdle | 61 | 
| 31140 | Cloak of Entropy | 61 | 
| 31143 | Shroud of Frenzy | 62 | 
| 31145 | Headdress of the Sleeper | 62 | 
| 31147 | Pendant of Cunning | 62 | 
| 31148 | Demon Hide Spaulders | 61 | 
| 31149 | Gloves of Pandemonium | 62 | 
| 31150 | Gloves of Piety | 62 | 
| 31151 | Girdle of Siege | 63 | 
| 31152 | Chestguard of Illumination | 63 | 
| 31173 | Boots of Savagery | 63 | 
| 31175 | Blade Dancer's Wristguards | 63 | 
| 31178 | Amulet of Unstable Power | 63 | 
| 31180 | Gauntlets of the Skullsplitter | 64 | 
| 31187 | Boots of the Pathfinder | 64 | 
| 31196 | Amulet of Sanctification | 64 | 
| 31200 | Shield of the Wayward Footman | 65 | 
| 31202 | Girdle of Divine Blessing | 65 | 
| 31222 | Headdress of Inner Rage | 65 | 
| 31226 | Leggings of the Sly | 65 | 
| 31230 | Abyss Walker's Boots | 65 | 
| 31237 | Elekk Hide Leggings | 66 | 
| 31240 | Scales of the Beast | 66 | 
| 31255 | Cloak of the Craft | 66 | 
| 31258 | Band of Sorrow | 66 | 
| 31272 | Crown of Endless Knowledge | 66 | 
| 31275 | Necklace of Trophies | 67 | 
| 31276 | Boots of Zealotry | 67 | 
| 31277 | Pathfinder's Band | 67 | 
| 31280 | Thundercaller's Gauntlets | 67 | 
| 31281 | Mask of Veiled Death | 67 | 
| 31282 | Shroud of Spiritual Purity | 67 | 
| 31283 | Sash of Sealed Fate | 67 | 
| 31319 | Band of Impenetrable Defenses | 70 | 
| 31320 | Chestguard of Exile | 70 | 
| 31321 | Choker of Repentance | 70 | 
| 31326 | Truestrike Ring | 70 | 
| 31328 | Leggings of Beast Mastery | 70 | 
| 31329 | Lifegiving Cloak | 70 | 
| 31330 | Lightning Crown | 70 | 
| 31333 | The Night Watchman | 70 | 
| 31335 | Pants of Living Growth | 70 | 
| 31338 | Charlotte's Ivy | 70 | 
| 31339 | Lola's Eve | 70 | 
| 31340 | Will of Edward the Odd | 70 | 
| 31343 | Kamaei's Cerulean Skirt | 70 | 
  
</details>

24597, 24598, 24599, 24600, 24601, 24602, 24603, 24604, 24605, 24606, 24607, 24608, 24609, 24610, 24611, 24612, 24613, 24614, 24615, 24616, 24617, 24618, 24619, 24620, 24621, 24622, 24623, 24624, 24625, 24626, 24627, 24628, 24629, 24630, 24631, 24632, 24633, 24634, 24635, 24636, 24685, 24686, 24687, 24688, 24689, 24690, 24691, 24692, 24710, 24711, 24712, 24713, 24714, 24715, 24716, 24717, 24718, 24719, 24720, 24721, 24722, 24723, 24724, 24725, 24726, 24727, 24728, 24729, 24730, 24731, 24732, 24733, 24734, 24735, 24736, 24737, 24738, 24739, 24740, 24741, 24742, 24743, 24744, 24745, 24746, 24747, 24748, 24798, 24799, 24800, 24801, 24802, 24803, 24804, 24805, 24822, 24823, 24824, 24825, 24826, 24827, 24828, 24829, 24830, 24831, 24832, 24833, 24834, 24835, 24836, 24837, 24838, 24839, 24840, 24841, 24842, 24843, 24844, 24845, 24846, 24847, 24848, 24849, 24850, 24851, 24852, 24853, 24854, 24855, 24856, 24857, 24858, 24859, 24860, 24861, 24910, 24911, 24912, 24913, 24914, 24915, 24916, 24917, 24934, 24935, 24936, 24937, 24938, 24939, 24940, 24941, 24942, 24943, 24944, 24945, 24946, 24947, 24948, 24949, 24950, 24951, 24952, 24953, 24954, 24955, 24956, 24957, 24958, 24959, 24960, 24961, 24962, 24963, 24964, 24965, 24966, 24967, 24968, 24969, 24970, 24971, 24972, 24973, 25022, 25023, 25024, 25025, 25026, 25027, 25028, 25029, 25032, 25033, 25034, 25035, 25036, 25043, 25046, 25047, 25048, 25049, 25050, 25057, 25060, 25061, 25062, 25063, 25064, 25071, 25074, 25075, 25076, 25077, 25078, 25085, 25088, 25089, 25090, 25091, 25092, 25099, 30520, 30725, 30726, 30727, 30728, 30729, 30730, 30731, 30734, 30735, 30736, 30737, 30738, 30739, 30740, 30741, 30986, 31125, 31126, 31127, 31131, 31133, 31136, 31137, 31138, 31140, 31143, 31145, 31147, 31148, 31149, 31150, 31151, 31152, 31173, 31175, 31178, 31180, 31187, 31196, 31200, 31202, 31222, 31226, 31230, 31237, 31240, 31255, 31258, 31272, 31275, 31276, 31277, 31280, 31281, 31282, 31283, 31319, 31320, 31321, 31326, 31328, 31329, 31330, 31333, 31335, 31338, 31339, 31340, 31343

## Concatenated Armour

Concatenating the 3 lists above introduced 243 duplicates, which have been removed from this list.

[24597](https://tbc.wowhead.com/item=24597), [24598](https://tbc.wowhead.com/item=24598), [24599](https://tbc.wowhead.com/item=24599), [24600](https://tbc.wowhead.com/item=24600), [24601](https://tbc.wowhead.com/item=24601), [24602](https://tbc.wowhead.com/item=24602), [24603](https://tbc.wowhead.com/item=24603), [24604](https://tbc.wowhead.com/item=24604), [24605](https://tbc.wowhead.com/item=24605), [24606](https://tbc.wowhead.com/item=24606), [24607](https://tbc.wowhead.com/item=24607), [24608](https://tbc.wowhead.com/item=24608), [24609](https://tbc.wowhead.com/item=24609), [24610](https://tbc.wowhead.com/item=24610), [24611](https://tbc.wowhead.com/item=24611), [24612](https://tbc.wowhead.com/item=24612), [24613](https://tbc.wowhead.com/item=24613), [24614](https://tbc.wowhead.com/item=24614), [24615](https://tbc.wowhead.com/item=24615), [24616](https://tbc.wowhead.com/item=24616), [24617](https://tbc.wowhead.com/item=24617), [24618](https://tbc.wowhead.com/item=24618), [24619](https://tbc.wowhead.com/item=24619), [24620](https://tbc.wowhead.com/item=24620), [24621](https://tbc.wowhead.com/item=24621), [24622](https://tbc.wowhead.com/item=24622), [24623](https://tbc.wowhead.com/item=24623), [24624](https://tbc.wowhead.com/item=24624), [24625](https://tbc.wowhead.com/item=24625), [24626](https://tbc.wowhead.com/item=24626), [24627](https://tbc.wowhead.com/item=24627), [24628](https://tbc.wowhead.com/item=24628), [24629](https://tbc.wowhead.com/item=24629), [24630](https://tbc.wowhead.com/item=24630), [24631](https://tbc.wowhead.com/item=24631), [24632](https://tbc.wowhead.com/item=24632), [24633](https://tbc.wowhead.com/item=24633), [24634](https://tbc.wowhead.com/item=24634), [24635](https://tbc.wowhead.com/item=24635), [24636](https://tbc.wowhead.com/item=24636), [24637](https://tbc.wowhead.com/item=24637), [24638](https://tbc.wowhead.com/item=24638), [24639](https://tbc.wowhead.com/item=24639), [24640](https://tbc.wowhead.com/item=24640), [24641](https://tbc.wowhead.com/item=24641), [24642](https://tbc.wowhead.com/item=24642), [24643](https://tbc.wowhead.com/item=24643), [24644](https://tbc.wowhead.com/item=24644), [24645](https://tbc.wowhead.com/item=24645), [24646](https://tbc.wowhead.com/item=24646), [24647](https://tbc.wowhead.com/item=24647), [24648](https://tbc.wowhead.com/item=24648), [24649](https://tbc.wowhead.com/item=24649), [24650](https://tbc.wowhead.com/item=24650), [24651](https://tbc.wowhead.com/item=24651), [24652](https://tbc.wowhead.com/item=24652), [24653](https://tbc.wowhead.com/item=24653), [24654](https://tbc.wowhead.com/item=24654), [24655](https://tbc.wowhead.com/item=24655), [24656](https://tbc.wowhead.com/item=24656), [24657](https://tbc.wowhead.com/item=24657), [24658](https://tbc.wowhead.com/item=24658), [24659](https://tbc.wowhead.com/item=24659), [24660](https://tbc.wowhead.com/item=24660), [24661](https://tbc.wowhead.com/item=24661), [24662](https://tbc.wowhead.com/item=24662), [24663](https://tbc.wowhead.com/item=24663), [24664](https://tbc.wowhead.com/item=24664), [24665](https://tbc.wowhead.com/item=24665), [24666](https://tbc.wowhead.com/item=24666), [24667](https://tbc.wowhead.com/item=24667), [24668](https://tbc.wowhead.com/item=24668), [24669](https://tbc.wowhead.com/item=24669), [24670](https://tbc.wowhead.com/item=24670), [24671](https://tbc.wowhead.com/item=24671), [24672](https://tbc.wowhead.com/item=24672), [24673](https://tbc.wowhead.com/item=24673), [24674](https://tbc.wowhead.com/item=24674), [24675](https://tbc.wowhead.com/item=24675), [24676](https://tbc.wowhead.com/item=24676), [24677](https://tbc.wowhead.com/item=24677), [24678](https://tbc.wowhead.com/item=24678), [24679](https://tbc.wowhead.com/item=24679), [24680](https://tbc.wowhead.com/item=24680), [24681](https://tbc.wowhead.com/item=24681), [24682](https://tbc.wowhead.com/item=24682), [24683](https://tbc.wowhead.com/item=24683), [24684](https://tbc.wowhead.com/item=24684), [24685](https://tbc.wowhead.com/item=24685), [24686](https://tbc.wowhead.com/item=24686), [24687](https://tbc.wowhead.com/item=24687), [24688](https://tbc.wowhead.com/item=24688), [24689](https://tbc.wowhead.com/item=24689), [24690](https://tbc.wowhead.com/item=24690), [24691](https://tbc.wowhead.com/item=24691), [24692](https://tbc.wowhead.com/item=24692), [24710](https://tbc.wowhead.com/item=24710), [24711](https://tbc.wowhead.com/item=24711), [24712](https://tbc.wowhead.com/item=24712), [24713](https://tbc.wowhead.com/item=24713), [24714](https://tbc.wowhead.com/item=24714), [24715](https://tbc.wowhead.com/item=24715), [24716](https://tbc.wowhead.com/item=24716), [24717](https://tbc.wowhead.com/item=24717), [24718](https://tbc.wowhead.com/item=24718), [24719](https://tbc.wowhead.com/item=24719), [24720](https://tbc.wowhead.com/item=24720), [24721](https://tbc.wowhead.com/item=24721), [24722](https://tbc.wowhead.com/item=24722), [24723](https://tbc.wowhead.com/item=24723), [24724](https://tbc.wowhead.com/item=24724), [24725](https://tbc.wowhead.com/item=24725), [24726](https://tbc.wowhead.com/item=24726), [24727](https://tbc.wowhead.com/item=24727), [24728](https://tbc.wowhead.com/item=24728), [24729](https://tbc.wowhead.com/item=24729), [24730](https://tbc.wowhead.com/item=24730), [24731](https://tbc.wowhead.com/item=24731), [24732](https://tbc.wowhead.com/item=24732), [24733](https://tbc.wowhead.com/item=24733), [24734](https://tbc.wowhead.com/item=24734), [24735](https://tbc.wowhead.com/item=24735), [24736](https://tbc.wowhead.com/item=24736), [24737](https://tbc.wowhead.com/item=24737), [24738](https://tbc.wowhead.com/item=24738), [24739](https://tbc.wowhead.com/item=24739), [24740](https://tbc.wowhead.com/item=24740), [24741](https://tbc.wowhead.com/item=24741), [24742](https://tbc.wowhead.com/item=24742), [24743](https://tbc.wowhead.com/item=24743), [24744](https://tbc.wowhead.com/item=24744), [24745](https://tbc.wowhead.com/item=24745), [24746](https://tbc.wowhead.com/item=24746), [24747](https://tbc.wowhead.com/item=24747), [24748](https://tbc.wowhead.com/item=24748), [24749](https://tbc.wowhead.com/item=24749), [24750](https://tbc.wowhead.com/item=24750), [24751](https://tbc.wowhead.com/item=24751), [24752](https://tbc.wowhead.com/item=24752), [24753](https://tbc.wowhead.com/item=24753), [24754](https://tbc.wowhead.com/item=24754), [24755](https://tbc.wowhead.com/item=24755), [24756](https://tbc.wowhead.com/item=24756), [24757](https://tbc.wowhead.com/item=24757), [24758](https://tbc.wowhead.com/item=24758), [24759](https://tbc.wowhead.com/item=24759), [24760](https://tbc.wowhead.com/item=24760), [24761](https://tbc.wowhead.com/item=24761), [24762](https://tbc.wowhead.com/item=24762), [24763](https://tbc.wowhead.com/item=24763), [24764](https://tbc.wowhead.com/item=24764), [24765](https://tbc.wowhead.com/item=24765), [24766](https://tbc.wowhead.com/item=24766), [24767](https://tbc.wowhead.com/item=24767), [24768](https://tbc.wowhead.com/item=24768), [24769](https://tbc.wowhead.com/item=24769), [24770](https://tbc.wowhead.com/item=24770), [24771](https://tbc.wowhead.com/item=24771), [24772](https://tbc.wowhead.com/item=24772), [24773](https://tbc.wowhead.com/item=24773), [24774](https://tbc.wowhead.com/item=24774), [24775](https://tbc.wowhead.com/item=24775), [24776](https://tbc.wowhead.com/item=24776), [24777](https://tbc.wowhead.com/item=24777), [24778](https://tbc.wowhead.com/item=24778), [24779](https://tbc.wowhead.com/item=24779), [24780](https://tbc.wowhead.com/item=24780), [24781](https://tbc.wowhead.com/item=24781), [24783](https://tbc.wowhead.com/item=24783), [24784](https://tbc.wowhead.com/item=24784), [24785](https://tbc.wowhead.com/item=24785), [24786](https://tbc.wowhead.com/item=24786), [24787](https://tbc.wowhead.com/item=24787), [24788](https://tbc.wowhead.com/item=24788), [24789](https://tbc.wowhead.com/item=24789), [24790](https://tbc.wowhead.com/item=24790), [24791](https://tbc.wowhead.com/item=24791), [24792](https://tbc.wowhead.com/item=24792), [24793](https://tbc.wowhead.com/item=24793), [24794](https://tbc.wowhead.com/item=24794), [24795](https://tbc.wowhead.com/item=24795), [24796](https://tbc.wowhead.com/item=24796), [24797](https://tbc.wowhead.com/item=24797), [24798](https://tbc.wowhead.com/item=24798), [24799](https://tbc.wowhead.com/item=24799), [24800](https://tbc.wowhead.com/item=24800), [24801](https://tbc.wowhead.com/item=24801), [24802](https://tbc.wowhead.com/item=24802), [24803](https://tbc.wowhead.com/item=24803), [24804](https://tbc.wowhead.com/item=24804), [24805](https://tbc.wowhead.com/item=24805), [24822](https://tbc.wowhead.com/item=24822), [24823](https://tbc.wowhead.com/item=24823), [24824](https://tbc.wowhead.com/item=24824), [24825](https://tbc.wowhead.com/item=24825), [24826](https://tbc.wowhead.com/item=24826), [24827](https://tbc.wowhead.com/item=24827), [24828](https://tbc.wowhead.com/item=24828), [24829](https://tbc.wowhead.com/item=24829), [24830](https://tbc.wowhead.com/item=24830), [24831](https://tbc.wowhead.com/item=24831), [24832](https://tbc.wowhead.com/item=24832), [24833](https://tbc.wowhead.com/item=24833), [24834](https://tbc.wowhead.com/item=24834), [24835](https://tbc.wowhead.com/item=24835), [24836](https://tbc.wowhead.com/item=24836), [24837](https://tbc.wowhead.com/item=24837), [24838](https://tbc.wowhead.com/item=24838), [24839](https://tbc.wowhead.com/item=24839), [24840](https://tbc.wowhead.com/item=24840), [24841](https://tbc.wowhead.com/item=24841), [24842](https://tbc.wowhead.com/item=24842), [24843](https://tbc.wowhead.com/item=24843), [24844](https://tbc.wowhead.com/item=24844), [24845](https://tbc.wowhead.com/item=24845), [24846](https://tbc.wowhead.com/item=24846), [24847](https://tbc.wowhead.com/item=24847), [24848](https://tbc.wowhead.com/item=24848), [24849](https://tbc.wowhead.com/item=24849), [24850](https://tbc.wowhead.com/item=24850), [24851](https://tbc.wowhead.com/item=24851), [24852](https://tbc.wowhead.com/item=24852), [24853](https://tbc.wowhead.com/item=24853), [24854](https://tbc.wowhead.com/item=24854), [24855](https://tbc.wowhead.com/item=24855), [24856](https://tbc.wowhead.com/item=24856), [24857](https://tbc.wowhead.com/item=24857), [24858](https://tbc.wowhead.com/item=24858), [24859](https://tbc.wowhead.com/item=24859), [24860](https://tbc.wowhead.com/item=24860), [24861](https://tbc.wowhead.com/item=24861), [24862](https://tbc.wowhead.com/item=24862), [24863](https://tbc.wowhead.com/item=24863), [24864](https://tbc.wowhead.com/item=24864), [24865](https://tbc.wowhead.com/item=24865), [24866](https://tbc.wowhead.com/item=24866), [24867](https://tbc.wowhead.com/item=24867), [24868](https://tbc.wowhead.com/item=24868), [24869](https://tbc.wowhead.com/item=24869), [24870](https://tbc.wowhead.com/item=24870), [24871](https://tbc.wowhead.com/item=24871), [24872](https://tbc.wowhead.com/item=24872), [24873](https://tbc.wowhead.com/item=24873), [24874](https://tbc.wowhead.com/item=24874), [24875](https://tbc.wowhead.com/item=24875), [24876](https://tbc.wowhead.com/item=24876), [24877](https://tbc.wowhead.com/item=24877), [24878](https://tbc.wowhead.com/item=24878), [24879](https://tbc.wowhead.com/item=24879), [24880](https://tbc.wowhead.com/item=24880), [24881](https://tbc.wowhead.com/item=24881), [24882](https://tbc.wowhead.com/item=24882), [24883](https://tbc.wowhead.com/item=24883), [24884](https://tbc.wowhead.com/item=24884), [24885](https://tbc.wowhead.com/item=24885), [24886](https://tbc.wowhead.com/item=24886), [24887](https://tbc.wowhead.com/item=24887), [24888](https://tbc.wowhead.com/item=24888), [24889](https://tbc.wowhead.com/item=24889), [24890](https://tbc.wowhead.com/item=24890), [24891](https://tbc.wowhead.com/item=24891), [24892](https://tbc.wowhead.com/item=24892), [24893](https://tbc.wowhead.com/item=24893), [24894](https://tbc.wowhead.com/item=24894), [24895](https://tbc.wowhead.com/item=24895), [24896](https://tbc.wowhead.com/item=24896), [24897](https://tbc.wowhead.com/item=24897), [24898](https://tbc.wowhead.com/item=24898), [24899](https://tbc.wowhead.com/item=24899), [24900](https://tbc.wowhead.com/item=24900), [24901](https://tbc.wowhead.com/item=24901), [24902](https://tbc.wowhead.com/item=24902), [24903](https://tbc.wowhead.com/item=24903), [24904](https://tbc.wowhead.com/item=24904), [24905](https://tbc.wowhead.com/item=24905), [24906](https://tbc.wowhead.com/item=24906), [24907](https://tbc.wowhead.com/item=24907), [24908](https://tbc.wowhead.com/item=24908), [24909](https://tbc.wowhead.com/item=24909), [24910](https://tbc.wowhead.com/item=24910), [24911](https://tbc.wowhead.com/item=24911), [24912](https://tbc.wowhead.com/item=24912), [24913](https://tbc.wowhead.com/item=24913), [24914](https://tbc.wowhead.com/item=24914), [24915](https://tbc.wowhead.com/item=24915), [24916](https://tbc.wowhead.com/item=24916), [24917](https://tbc.wowhead.com/item=24917), [24934](https://tbc.wowhead.com/item=24934), [24935](https://tbc.wowhead.com/item=24935), [24936](https://tbc.wowhead.com/item=24936), [24937](https://tbc.wowhead.com/item=24937), [24938](https://tbc.wowhead.com/item=24938), [24939](https://tbc.wowhead.com/item=24939), [24940](https://tbc.wowhead.com/item=24940), [24941](https://tbc.wowhead.com/item=24941), [24942](https://tbc.wowhead.com/item=24942), [24943](https://tbc.wowhead.com/item=24943), [24944](https://tbc.wowhead.com/item=24944), [24945](https://tbc.wowhead.com/item=24945), [24946](https://tbc.wowhead.com/item=24946), [24947](https://tbc.wowhead.com/item=24947), [24948](https://tbc.wowhead.com/item=24948), [24949](https://tbc.wowhead.com/item=24949), [24950](https://tbc.wowhead.com/item=24950), [24951](https://tbc.wowhead.com/item=24951), [24952](https://tbc.wowhead.com/item=24952), [24953](https://tbc.wowhead.com/item=24953), [24954](https://tbc.wowhead.com/item=24954), [24955](https://tbc.wowhead.com/item=24955), [24956](https://tbc.wowhead.com/item=24956), [24957](https://tbc.wowhead.com/item=24957), [24958](https://tbc.wowhead.com/item=24958), [24959](https://tbc.wowhead.com/item=24959), [24960](https://tbc.wowhead.com/item=24960), [24961](https://tbc.wowhead.com/item=24961), [24962](https://tbc.wowhead.com/item=24962), [24963](https://tbc.wowhead.com/item=24963), [24964](https://tbc.wowhead.com/item=24964), [24965](https://tbc.wowhead.com/item=24965), [24966](https://tbc.wowhead.com/item=24966), [24967](https://tbc.wowhead.com/item=24967), [24968](https://tbc.wowhead.com/item=24968), [24969](https://tbc.wowhead.com/item=24969), [24970](https://tbc.wowhead.com/item=24970), [24971](https://tbc.wowhead.com/item=24971), [24972](https://tbc.wowhead.com/item=24972), [24973](https://tbc.wowhead.com/item=24973), [24974](https://tbc.wowhead.com/item=24974), [24975](https://tbc.wowhead.com/item=24975), [24976](https://tbc.wowhead.com/item=24976), [24977](https://tbc.wowhead.com/item=24977), [24978](https://tbc.wowhead.com/item=24978), [24979](https://tbc.wowhead.com/item=24979), [24980](https://tbc.wowhead.com/item=24980), [24981](https://tbc.wowhead.com/item=24981), [24982](https://tbc.wowhead.com/item=24982), [24983](https://tbc.wowhead.com/item=24983), [24984](https://tbc.wowhead.com/item=24984), [24985](https://tbc.wowhead.com/item=24985), [24986](https://tbc.wowhead.com/item=24986), [24987](https://tbc.wowhead.com/item=24987), [24988](https://tbc.wowhead.com/item=24988), [24989](https://tbc.wowhead.com/item=24989), [24990](https://tbc.wowhead.com/item=24990), [24991](https://tbc.wowhead.com/item=24991), [24992](https://tbc.wowhead.com/item=24992), [24993](https://tbc.wowhead.com/item=24993), [24994](https://tbc.wowhead.com/item=24994), [24995](https://tbc.wowhead.com/item=24995), [24996](https://tbc.wowhead.com/item=24996), [24997](https://tbc.wowhead.com/item=24997), [24998](https://tbc.wowhead.com/item=24998), [24999](https://tbc.wowhead.com/item=24999), [25000](https://tbc.wowhead.com/item=25000), [25001](https://tbc.wowhead.com/item=25001), [25002](https://tbc.wowhead.com/item=25002), [25003](https://tbc.wowhead.com/item=25003), [25004](https://tbc.wowhead.com/item=25004), [25005](https://tbc.wowhead.com/item=25005), [25006](https://tbc.wowhead.com/item=25006), [25007](https://tbc.wowhead.com/item=25007), [25008](https://tbc.wowhead.com/item=25008), [25009](https://tbc.wowhead.com/item=25009), [25010](https://tbc.wowhead.com/item=25010), [25011](https://tbc.wowhead.com/item=25011), [25012](https://tbc.wowhead.com/item=25012), [25013](https://tbc.wowhead.com/item=25013), [25014](https://tbc.wowhead.com/item=25014), [25015](https://tbc.wowhead.com/item=25015), [25016](https://tbc.wowhead.com/item=25016), [25017](https://tbc.wowhead.com/item=25017), [25018](https://tbc.wowhead.com/item=25018), [25019](https://tbc.wowhead.com/item=25019), [25020](https://tbc.wowhead.com/item=25020), [25021](https://tbc.wowhead.com/item=25021), [25022](https://tbc.wowhead.com/item=25022), [25023](https://tbc.wowhead.com/item=25023), [25024](https://tbc.wowhead.com/item=25024), [25025](https://tbc.wowhead.com/item=25025), [25026](https://tbc.wowhead.com/item=25026), [25027](https://tbc.wowhead.com/item=25027), [25028](https://tbc.wowhead.com/item=25028), [25029](https://tbc.wowhead.com/item=25029), [25032](https://tbc.wowhead.com/item=25032), [25033](https://tbc.wowhead.com/item=25033), [25034](https://tbc.wowhead.com/item=25034), [25035](https://tbc.wowhead.com/item=25035), [25036](https://tbc.wowhead.com/item=25036), [25037](https://tbc.wowhead.com/item=25037), [25038](https://tbc.wowhead.com/item=25038), [25039](https://tbc.wowhead.com/item=25039), [25040](https://tbc.wowhead.com/item=25040), [25041](https://tbc.wowhead.com/item=25041), [25042](https://tbc.wowhead.com/item=25042), [25043](https://tbc.wowhead.com/item=25043), [25046](https://tbc.wowhead.com/item=25046), [25047](https://tbc.wowhead.com/item=25047), [25048](https://tbc.wowhead.com/item=25048), [25049](https://tbc.wowhead.com/item=25049), [25050](https://tbc.wowhead.com/item=25050), [25051](https://tbc.wowhead.com/item=25051), [25052](https://tbc.wowhead.com/item=25052), [25053](https://tbc.wowhead.com/item=25053), [25054](https://tbc.wowhead.com/item=25054), [25055](https://tbc.wowhead.com/item=25055), [25056](https://tbc.wowhead.com/item=25056), [25057](https://tbc.wowhead.com/item=25057), [25060](https://tbc.wowhead.com/item=25060), [25061](https://tbc.wowhead.com/item=25061), [25062](https://tbc.wowhead.com/item=25062), [25063](https://tbc.wowhead.com/item=25063), [25064](https://tbc.wowhead.com/item=25064), [25065](https://tbc.wowhead.com/item=25065), [25066](https://tbc.wowhead.com/item=25066), [25067](https://tbc.wowhead.com/item=25067), [25068](https://tbc.wowhead.com/item=25068), [25069](https://tbc.wowhead.com/item=25069), [25070](https://tbc.wowhead.com/item=25070), [25071](https://tbc.wowhead.com/item=25071), [25074](https://tbc.wowhead.com/item=25074), [25075](https://tbc.wowhead.com/item=25075), [25076](https://tbc.wowhead.com/item=25076), [25077](https://tbc.wowhead.com/item=25077), [25078](https://tbc.wowhead.com/item=25078), [25079](https://tbc.wowhead.com/item=25079), [25080](https://tbc.wowhead.com/item=25080), [25081](https://tbc.wowhead.com/item=25081), [25082](https://tbc.wowhead.com/item=25082), [25083](https://tbc.wowhead.com/item=25083), [25084](https://tbc.wowhead.com/item=25084), [25085](https://tbc.wowhead.com/item=25085), [25088](https://tbc.wowhead.com/item=25088), [25089](https://tbc.wowhead.com/item=25089), [25090](https://tbc.wowhead.com/item=25090), [25091](https://tbc.wowhead.com/item=25091), [25092](https://tbc.wowhead.com/item=25092), [25093](https://tbc.wowhead.com/item=25093), [25094](https://tbc.wowhead.com/item=25094), [25095](https://tbc.wowhead.com/item=25095), [25096](https://tbc.wowhead.com/item=25096), [25097](https://tbc.wowhead.com/item=25097), [25098](https://tbc.wowhead.com/item=25098), [25099](https://tbc.wowhead.com/item=25099), [25341](https://tbc.wowhead.com/item=25341), [25342](https://tbc.wowhead.com/item=25342), [25343](https://tbc.wowhead.com/item=25343), [25344](https://tbc.wowhead.com/item=25344), [25345](https://tbc.wowhead.com/item=25345), [25346](https://tbc.wowhead.com/item=25346), [25347](https://tbc.wowhead.com/item=25347), [25348](https://tbc.wowhead.com/item=25348), [25357](https://tbc.wowhead.com/item=25357), [25358](https://tbc.wowhead.com/item=25358), [25359](https://tbc.wowhead.com/item=25359), [25360](https://tbc.wowhead.com/item=25360), [25361](https://tbc.wowhead.com/item=25361), [25362](https://tbc.wowhead.com/item=25362), [25363](https://tbc.wowhead.com/item=25363), [25364](https://tbc.wowhead.com/item=25364), [25373](https://tbc.wowhead.com/item=25373), [25374](https://tbc.wowhead.com/item=25374), [25375](https://tbc.wowhead.com/item=25375), [25376](https://tbc.wowhead.com/item=25376), [25377](https://tbc.wowhead.com/item=25377), [25378](https://tbc.wowhead.com/item=25378), [25379](https://tbc.wowhead.com/item=25379), [25380](https://tbc.wowhead.com/item=25380), [25389](https://tbc.wowhead.com/item=25389), [25390](https://tbc.wowhead.com/item=25390), [25391](https://tbc.wowhead.com/item=25391), [25392](https://tbc.wowhead.com/item=25392), [25393](https://tbc.wowhead.com/item=25393), [25394](https://tbc.wowhead.com/item=25394), [25395](https://tbc.wowhead.com/item=25395), [25396](https://tbc.wowhead.com/item=25396), [30520](https://tbc.wowhead.com/item=30520), [30725](https://tbc.wowhead.com/item=30725), [30726](https://tbc.wowhead.com/item=30726), [30727](https://tbc.wowhead.com/item=30727), [30728](https://tbc.wowhead.com/item=30728), [30729](https://tbc.wowhead.com/item=30729), [30730](https://tbc.wowhead.com/item=30730), [30731](https://tbc.wowhead.com/item=30731), [30734](https://tbc.wowhead.com/item=30734), [30735](https://tbc.wowhead.com/item=30735), [30736](https://tbc.wowhead.com/item=30736), [30737](https://tbc.wowhead.com/item=30737), [30738](https://tbc.wowhead.com/item=30738), [30739](https://tbc.wowhead.com/item=30739), [30740](https://tbc.wowhead.com/item=30740), [30741](https://tbc.wowhead.com/item=30741), [30986](https://tbc.wowhead.com/item=30986), [31125](https://tbc.wowhead.com/item=31125), [31126](https://tbc.wowhead.com/item=31126), [31127](https://tbc.wowhead.com/item=31127), [31131](https://tbc.wowhead.com/item=31131), [31133](https://tbc.wowhead.com/item=31133), [31136](https://tbc.wowhead.com/item=31136), [31137](https://tbc.wowhead.com/item=31137), [31138](https://tbc.wowhead.com/item=31138), [31140](https://tbc.wowhead.com/item=31140), [31143](https://tbc.wowhead.com/item=31143), [31145](https://tbc.wowhead.com/item=31145), [31147](https://tbc.wowhead.com/item=31147), [31148](https://tbc.wowhead.com/item=31148), [31149](https://tbc.wowhead.com/item=31149), [31150](https://tbc.wowhead.com/item=31150), [31151](https://tbc.wowhead.com/item=31151), [31152](https://tbc.wowhead.com/item=31152), [31173](https://tbc.wowhead.com/item=31173), [31175](https://tbc.wowhead.com/item=31175), [31178](https://tbc.wowhead.com/item=31178), [31180](https://tbc.wowhead.com/item=31180), [31187](https://tbc.wowhead.com/item=31187), [31190](https://tbc.wowhead.com/item=31190), [31196](https://tbc.wowhead.com/item=31196), [31200](https://tbc.wowhead.com/item=31200), [31202](https://tbc.wowhead.com/item=31202), [31222](https://tbc.wowhead.com/item=31222), [31226](https://tbc.wowhead.com/item=31226), [31230](https://tbc.wowhead.com/item=31230), [31237](https://tbc.wowhead.com/item=31237), [31240](https://tbc.wowhead.com/item=31240), [31255](https://tbc.wowhead.com/item=31255), [31258](https://tbc.wowhead.com/item=31258), [31272](https://tbc.wowhead.com/item=31272), [31275](https://tbc.wowhead.com/item=31275), [31276](https://tbc.wowhead.com/item=31276), [31277](https://tbc.wowhead.com/item=31277), [31280](https://tbc.wowhead.com/item=31280), [31281](https://tbc.wowhead.com/item=31281), [31282](https://tbc.wowhead.com/item=31282), [31283](https://tbc.wowhead.com/item=31283), [31284](https://tbc.wowhead.com/item=31284), [31285](https://tbc.wowhead.com/item=31285), [31286](https://tbc.wowhead.com/item=31286), [31287](https://tbc.wowhead.com/item=31287), [31288](https://tbc.wowhead.com/item=31288), [31290](https://tbc.wowhead.com/item=31290), [31292](https://tbc.wowhead.com/item=31292), [31293](https://tbc.wowhead.com/item=31293), [31294](https://tbc.wowhead.com/item=31294), [31295](https://tbc.wowhead.com/item=31295), [31297](https://tbc.wowhead.com/item=31297), [31298](https://tbc.wowhead.com/item=31298), [31306](https://tbc.wowhead.com/item=31306), [31319](https://tbc.wowhead.com/item=31319), [31320](https://tbc.wowhead.com/item=31320), [31321](https://tbc.wowhead.com/item=31321), [31326](https://tbc.wowhead.com/item=31326), [31328](https://tbc.wowhead.com/item=31328), [31329](https://tbc.wowhead.com/item=31329), [31330](https://tbc.wowhead.com/item=31330), [31333](https://tbc.wowhead.com/item=31333), [31335](https://tbc.wowhead.com/item=31335), [31338](https://tbc.wowhead.com/item=31338), [31339](https://tbc.wowhead.com/item=31339), [31340](https://tbc.wowhead.com/item=31340), [31343](https://tbc.wowhead.com/item=31343)
