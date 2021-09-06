
## Quest Items (class = 12)
  Vanilla quest items go to ilvl 80 (Thunderfury precursor) and some 71s (hunter quest items). TBC quest items can have no ilvl, or any lvl from 1 upwards, e.g. DMF decks are ilvl 1. So query based on ilvl won't work, thus a query based on spawn location is needed - still some overlap with older DMF decks that drop in old world and Outland, so using index cutoff of 20K.

```SQL
SELECT distinct(it.entry), it.name, it.RequiredLevel
FROM `creature_loot_template` clt
JOIN `item_template` it ON clt.Item = it.entry
WHERE it.class = 12 AND it.entry > 20000
AND clt.entry IN 
(
    SELECT distinct(ct.lootid)
    FROM `creature_template` ct
    JOIN `creature` c ON c.id = ct.entry
    WHERE c.map = 530 AND ct.minlevel >= 58
)
```

<details>
  
<summary>Results</summary>
  
---
| entry | name | RequiredLevel | 
| ---: | --- | ---: | 
| 23217 | Ravager Egg | 0 | 
| 23218 | Condensed Voidwalker Essence | 0 | 
| 23239 | Plump Buzzard Wing | 0 | 
| 23269 | Felblood Sample | 0 | 
| 23270 | Tainted Helboar Meat | 0 | 
| 23336 | Helboar Blood Sample | 0 | 
| 23338 | Eroded Leather Case | 58 | 
| 23339 | Arelion's Journal | 0 | 
| 23387 | Bonestripper Tail Feather | 0 | 
| 23460 | Broken Blood Sample | 0 | 
| 23483 | Haal'eshi Scroll | 0 | 
| 23580 | Avruu's Orb | 60 | 
| 23588 | Kaliri Feather | 0 | 
| 23589 | Mag'har Ancestral Beads | 0 | 
| 23687 | Blacktalon's Claws | 0 | 
| 24005 | NPC Equip 24005 | 0 | 
| 24238 | Mushroom Sample | 0 | 
| 24240 | Box of Mushrooms | 0 | 
| 24279 | Vicious Teromoth Sample | 0 | 
| 24280 | Naga Claws | 0 | 
| 24291 | Bog Lord Tendril | 0 | 
| 24372 | Diaphanous Wing | 0 | 
| 24373 | Scout Jyoba's Report | 0 | 
| 24374 | Eel Filet | 0 | 
| 24375 | Thick Hydra Scale | 0 | 
| 24401 | Unidentified Plant Parts | 0 | 
| 24426 | Sporebat Eye | 0 | 
| 24427 | Fen Strider Tentacle | 0 | 
| 24449 | Fertile Spores | 0 | 
| 24469 | Muck-ridden Core | 0 | 
| 24472 | Boss Grog'ak's Head | 0 | 
| 24473 | Enraged Crusher Core | 0 | 
| 24483 | Withered Basidium | 60 | 
| 24484 | Withered Basidium | 60 | 
| 24485 | Marshlight Bleeder Venom | 0 | 
| 24486 | Fenclaw Hide | 0 | 
| 24493 | Marshfang Slicer Blade | 0 | 
| 24496 | Horn of Banthar | 0 | 
| 24497 | Feralfen Protection Totem | 0 | 
| 24505 | Heart of Tusker | 0 | 
| 24513 | Eye of Gutripper | 0 | 
| 24523 | Hoof of Bach'lor | 0 | 
| 24542 | Murkblood Idol | 0 | 
| 24543 | Head of Ortor of Murkblood | 0 | 
| 25416 | Oshu'gun Crystal Fragment | 0 | 
| 25433 | Obsidian Warbeads | 0 | 
| 25448 | Blacksting's Stinger | 0 | 
| 25459 | "Count" Ungula's Mandible | 62 | 
| 25460 | Bleeding Hollow Supply Crate | 0 | 
| 25463 | Pair of Ivory Tusks | 0 | 
| 25490 | Boulderfist Key | 0 | 
| 25509 | Northwind Cleft Key | 0 | 
| 25554 | Kil'sorrow Armaments | 0 | 
| 25590 | Head of Cho'war | 0 | 
| 25648 | Cho'war's Key | 0 | 
| 25666 | Mug'gok's Head | 0 | 
| 25672 | Teromoth Sample | 0 | 
| 25678 | Warp Hunter Essence | 0 | 
| 25719 | Arakkoa Feather | 0 | 
| 25744 | Dampscale Basilisk Eye | 0 | 
| 25751 | The Master Planner's Blueprints | 0 | 
| 25767 | Raliq's Debt | 0 | 
| 25768 | Coosh'coosh's Debt | 0 | 
| 25769 | Floon's Debt | 0 | 
| 25770 | Fel Cannon Activator | 0 | 
| 25771 | Fel Cannon Activator | 0 | 
| 25802 | Dreadfang Venom Sac | 0 | 
| 25807 | Timber Worg Tail | 0 | 
| 25812 | Timber Worg Pelt | 0 | 
| 25815 | Stonegazer's Blood | 0 | 
| 25837 | Ironjaw's Pelt | 0 | 
| 25852 | Tail Feather of Torgos | 0 | 
| 25891 | Pristine Shimmerscale Eel | 0 | 
| 27807 | Air Elemental Gas | 0 | 
| 27861 | Lathrai's Stolen Goods | 0 | 
| 27943 | Chieftain Mummaki's Totem | 0 | 
| 28368 | Sigil of Krasus | 0 | 
| 28376 | B'naar Personnel Roster | 0 | 
| 28417 | Nether Ray Stinger | 0 | 
| 28452 | Bloodgem Shard | 0 | 
| 28475 | Heliotrope Oculus | 0 | 
| 28479 | Stone of Glacius | 0 | 
| 28527 | Mana Wraith Essence | 0 | 
| 28550 | Flaming Torch | 0 | 
| 28552 | A Mysterious Tome | 58 | 
| 28562 | Unyielding Battle Horn | 1 | 
| 28563 | Doomclaw's Hand | 0 | 
| 28665 | Mountain Gronn Eyeball | 0 | 
| 28667 | Flawless Greater Windroc Beak | 0 | 
| 28668 | Aged Clefthoof Blubber | 0 | 
| 28786 | Apex's Crystal Focus | 0 | 
| 28787 | Annihilator Servo | 0 | 
| 28829 | Arklon Crystal Artifact | 0 | 
| 28970 | Nether Dragon Essence | 0 | 
| 29026 | Ata'mal Crystal | 0 | 
| 29113 | Demonic Essence | 0 | 
| 29154 | Legion Cannon | 0 | 
| 29161 | Void Ridge Soul Shard | 0 | 
| 29163 | Raw Farahlite | 0 | 
| 29164 | Farahlite Core | 0 | 
| 29205 | Inquisitor's Crest - Top Half | 0 | 
| 29206 | Inquisitor's Crest - Bottom Half | 0 | 
| 29209 | Zaxxis Insignia | 0 | 
| 29216 | Flawless Crystal Shard | 0 | 
| 29233 | Dathric's Blade | 67 | 
| 29234 | Belmara's Tome | 67 | 
| 29235 | Luminrath's Mantle | 67 | 
| 29236 | Cohlien's Cap | 67 | 
| 29260 | Heart of the Fel Reaver | 0 | 
| 29331 | Annals of Kirin'Var | 0 | 
| 29338 | Loathsome Remnant | 0 | 
| 29365 | Smithing Hammer | 0 | 
| 29366 | B'naar Access Crystal | 0 | 
| 29396 | Coruu Access Crystal | 0 | 
| 29397 | Duro Access Crystal | 0 | 
| 29411 | Ara Access Crystal | 0 | 
| 29425 | Mark of Kil'jaeden | 0 | 
| 29426 | Firewing Signet | 0 | 
| 29459 | Ethereum Relay Data | 0 | 
| 29464 | Shaleskin Shale | 0 | 
| 29475 | Pacifying Dust | 0 | 
| 29476 | Crimson Crystal Shard | 61 | 
| 29480 | Parched Hydra Sample | 0 | 
| 29481 | Withered Bog Lord Sample | 0 | 
| 29545 | Sunfury Military Briefing | 0 | 
| 29546 | Sunfury Arcane Briefing | 0 | 
| 29586 | Head of Forgefiend Razorsaw | 0 | 
| 29591 | Prepared Ethereum Wrapping | 0 | 
| 29738 | Vial of Void Horror Ooze | 68 | 
| 29739 | Arcane Tome | 0 | 
| 29740 | Fel Armament | 0 | 
| 29768 | Hulking Hydra Heart | 0 | 
| 29795 | Burning Legion Gate Key | 0 | 
| 29797 | Orders From Kael'thas | 0 | 
| 29801 | Ripfang Lynx Pelt | 0 | 
| 29822 | Fragment of Dimensius | 0 | 
| 29912 | The Final Code | 0 | 
| 30157 | Cursed Talisman | 0 | 
| 30158 | Morkh's Shattered Armor | 0 | 
| 30174 | Dust of the Fey Drake | 0 | 
| 30177 | Stronglimb Deeproot's Trunk | 0 | 
| 30184 | Thunderlord Dire Wolf Tail | 0 | 
| 30315 | Draenethyst Mine Crystal | 0 | 
| 30327 | Bonechewer Blood | 0 | 
| 30413 | Vindicator Vuuleen's Blade | 0 | 
| 30415 | Vindicator Vuuleen's Shield | 0 | 
| 30416 | Bladespire Clan Banner | 0 | 
| 30425 | Bleeding Hollow Blood | 0 | 
| 30431 | Thunderlord Clan Artifact | 65 | 
| 30442 | Crystalline Key | 0 | 
| 30451 | Lohn'goron, Bow of the Torn-heart | 0 | 
| 30529 | Plucked Lashh'an Feather | 0 | 
| 30561 | Vekh'nir Crystal | 0 | 
| 30579 | Illidari-Bane Shard | 67 | 
| 30596 | Baa'ri Tablet Fragment | 1 | 
| 30618 | Trachela's Carcass | 0 | 
| 30640 | Eclipsion Armor | 0 | 
| 30645 | Third Fragment of the Cipher of Damnation | 0 | 
| 30649 | Orders From Akama | 0 | 
| 30655 | Infused Vekh'nir Crystal | 0 | 
| 30672 | Elemental Displacer | 0 | 
| 30679 | Sunfury Glaive | 0 | 
| 30689 | Razuun's Orders | 0 | 
| 30691 | Haalum's Medallion Fragment | 0 | 
| 30692 | Eykenen's Medallion Fragment | 0 | 
| 30693 | Lakaan's Medallion Fragment | 0 | 
| 30694 | Uylaru's Medallion Fragment | 0 | 
| 30695 | Legion Teleporter Control | 0 | 
| 30704 | Ruuan'ok Claw | 0 | 
| 30756 | Illidari-Bane Shard | 67 | 
| 30785 | Morgroron's Glaive | 0 | 
| 30786 | Makazradon's Glaive | 0 | 
| 30791 | Silkwing Cocoon | 0 | 
| 30792 | Iridescent Wing | 0 | 
| 30797 | Gorefiend's Armor | 0 | 
| 30798 | Extra Sharp Daggermaw Tooth | 0 | 
| 30799 | Gorefiend's Cloak | 0 | 
| 30800 | Gorefiend's Truncheon | 0 | 
| 30807 | Uvuros's Fiery Mane | 0 | 
| 30809 | Mark of Sargeras | 0 | 
| 30810 | Sunfury Signet | 0 | 
| 30819 | Felfire Spleen | 0 | 
| 30840 | Ether-Energized Flesh | 0 | 
| 30849 | Scalewing Lightning Gland | 0 | 
| 30850 | Freshly Drawn Blood | 0 | 
| 30851 | Felspine's Hide | 0 | 
| 30867 | Overdeveloped Felfire Gizzard | 0 | 
| 31119 | Wyrmcult Net | 0 | 
| 31120 | Meeting Note | 65 | 
| 31132 | Crust Burster Venom Gland | 0 | 
| 31169 | Sketh'lon War Totem | 0 | 
| 31239 | Primed Key Mold | 68 | 
| 31241 | Primed Key Mold | 68 | 
| 31245 | Primed Key Mold | 0 | 
| 31260 | Sketh'lon Commander's Journal - Page 1 | 0 | 
| 31261 | Sketh'lon Commander's Journal - Page 2 | 0 | 
| 31262 | Sketh'lon Commander's Journal - Page 3 | 0 | 
| 31271 | Illidan's Command | 0 | 
| 31278 | Illidari Tabard | 0 | 
| 31307 | Heart of Fury | 0 | 
| 31316 | Lianthe's Key | 0 | 
| 31345 | The Journal of Val'zareq | 68 | 
| 31347 | Bleeding Hollow Torch | 0 | 
| 31363 | Gorgrom's Favor | 65 | 
| 31372 | Rocknail Flayer Carcass | 0 | 
| 31373 | Rocknail Flayer Giblets | 0 | 
| 31374 | Worg Master's Head | 0 | 
| 31384 | Damaged Mask | 65 | 
| 31489 | Orb of the Grishna | 65 | 
| 31529 | Grillok's Eyepatch | 0 | 
| 31651 | Bladespire Totem | 0 | 
| 31653 | Condensed Nether Gas | 0 | 
| 31656 | Lesser Nether Drake Spirit | 0 | 
| 31707 | Cabal Orders | 62 | 
| 31754 | Grisly Totem | 0 | 
| 31755 | Wyvern Cage Key | 0 | 
| 31757 | Fel Cannonball | 0 | 
| 31812 | Doom Skull | 1 | 
| 31815 | Zeppit's Crystal | 0 | 
| 31885 | Four of Blessings | 0 | 
| 31888 | Three of Blessings | 0 | 
| 31889 | Two of Blessings | 0 | 
| 31895 | Four of Storms | 0 | 
| 31899 | Three of Storms | 0 | 
| 31900 | Two of Storms | 0 | 
| 31902 | Eight of Furies | 0 | 
| 31904 | Four of Furies | 0 | 
| 31905 | Seven of Furies | 0 | 
| 31908 | Three of Furies | 0 | 
| 31909 | Two of Furies | 0 | 
| 31911 | Eight of Lunacy | 0 | 
| 31913 | Four of Lunacy | 0 | 
| 31917 | Three of Lunacy | 0 | 
| 31918 | Two of Lunacy | 0 | 
| 32379 | Grulloc's Dragon Skull | 0 | 
| 32388 | Shadow Dust | 0 | 
| 32464 | Nethercite Ore | 0 | 
| 32470 | Nethermine Flayer Hide | 0 | 
| 32502 | Fel Gland | 0 | 
| 32509 | Netherwing Relic | 0 | 
| 32523 | Ishaal's Almanac | 70 | 
| 32567 | Aether Ray Eye | 0 | 
| 32620 | Time-Lost Scroll | 0 | 
| 32621 | Partially Digested Hand | 70 | 
| 32666 | Hardened Hide of Tyrantus | 0 | 
| 32723 | Nethermine Cargo | 0 | 
| 33838 | Giant Kaliri Wing | 0 | 
| 34248 | Bash'ir Phasing Device | 0 | 
| 34255 | Razorthorn Flayer Gland | 0 | 
| 34259 | Demonic Blood | 0 | 
| 34338 | Mana Remnants | 0 | 
| 34483 | Orb of Murloc Control | 0 | 
| 34500 | Ata'mal Armament | 0 | 
| 35231 | Sunfury Attack Plans | 0 | 
</details>
  

23217, 23218, 23239, 23269, 23270, 23336, 23338, 23339, 23387, 23460, 23483, 23580, 23588, 23589, 23687, 24005, 24238, 24240, 24279, 24280, 24291, 24372, 24373, 24374, 24375, 24401, 24426, 24427, 24449, 24469, 24472, 24473, 24483, 24484, 24485, 24486, 24493, 24496, 24497, 24505, 24513, 24523, 24542, 24543, 25416, 25433, 25448, 25459, 25460, 25463, 25490, 25509, 25554, 25590, 25648, 25666, 25672, 25678, 25719, 25744, 25751, 25767, 25768, 25769, 25770, 25771, 25802, 25807, 25812, 25815, 25837, 25852, 25891, 27807, 27861, 27943, 28368, 28376, 28417, 28452, 28475, 28479, 28527, 28550, 28552, 28562, 28563, 28665, 28667, 28668, 28786, 28787, 28829, 28970, 29026, 29113, 29154, 29161, 29163, 29164, 29205, 29206, 29209, 29216, 29233, 29234, 29235, 29236, 29260, 29331, 29338, 29365, 29366, 29396, 29397, 29411, 29425, 29426, 29459, 29464, 29475, 29476, 29480, 29481, 29545, 29546, 29586, 29591, 29738, 29739, 29740, 29768, 29795, 29797, 29801, 29822, 29912, 30157, 30158, 30174, 30177, 30184, 30315, 30327, 30413, 30415, 30416, 30425, 30431, 30442, 30451, 30529, 30561, 30579, 30596, 30618, 30640, 30645, 30649, 30655, 30672, 30679, 30689, 30691, 30692, 30693, 30694, 30695, 30704, 30756, 30785, 30786, 30791, 30792, 30797, 30798, 30799, 30800, 30807, 30809, 30810, 30819, 30840, 30849, 30850, 30851, 30867, 31119, 31120, 31132, 31169, 31239, 31241, 31245, 31260, 31261, 31262, 31271, 31278, 31307, 31316, 31345, 31347, 31363, 31372, 31373, 31374, 31384, 31489, 31529, 31651, 31653, 31656, 31707, 31754, 31755, 31757, 31812, 31815, 31885, 31888, 31889, 31895, 31899, 31900, 31902, 31904, 31905, 31908, 31909, 31911, 31913, 31917, 31918, 32379, 32388, 32464, 32470, 32502, 32509, 32523, 32567, 32620, 32621, 32666, 32723, 33838, 34248, 34255, 34259, 34338, 34483, 34500, 35231
