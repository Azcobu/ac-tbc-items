## Weapons (class = 2)

Specifically concentrating on TBC NPCs in Kara/Deadwind Pass and Isle of Quel'Danas.

Kara - Deadwind Pass NPCs >60 with loot: unliving caretaker/resident, wailing spectre, damned soul, restless shade - (7370, 12377, 12378, 12379, 12380)

Islw of Q'D NPCs >60 with loot: wretched fiends/devourer/hungerer, irespeaker, unleashed hellion, dawnblade blood knight/hawkrider/marksman/reservist/summoner/charger, darkspine siren/myrmidon, abyssal flamewalker - (24996, 24960, 25047, 24999, 25002, 24976, 24978, 24979, 25063, 25087, 25548, 25073, 25060, 25001)

A general query for all open world map = 530 mobs -> items as a catchall. However, this misses Kara + Q'D and is hugely expensive
    Vanilla weapons go up to ilvl 100, all with req. lvl 60.
   TBC items seems ot start around 23300, but old world stuff is still interspersed

All Kara items (115 weapons):
```SQL
SELECT DISTINCT( it.entry), it.name, it.itemlevel, it.RequiredLevel
FROM `creature_template` ct
JOIN `creature_loot_template` clt ON ct.lootid = clt.entry
JOIN `reference_loot_template` rlt ON clt.Reference = rlt.Entry
JOIN `item_template` it ON it.entry = rlt.Item
WHERE ct.entry IN (7370, 12377, 12378, 12379, 12380) AND it.class = 2 AND it.entry > 25000
```

<details>
<summary>Results</summary>

    item_template
---
| entry | name | itemlevel | RequiredLevel | 
| ---: | --- | ---: | ---: | 
| 25107 | Draconic Dagger | 102 | 64 | 
| 25108 | Grave Keeper Knife | 105 | 65 | 
| 25109 | Moon Blade | 108 | 66 | 
| 25110 | Sharp Bowie Knife | 111 | 67 | 
| 25111 | Lionhead Dagger | 114 | 68 | 
| 25112 | Fel Ripper | 117 | 69 | 
| 25121 | Dreaded Mace | 102 | 64 | 
| 25122 | Khorium Plated Bludgeon | 105 | 65 | 
| 25123 | Boneshredder Mace | 108 | 66 | 
| 25124 | Footman Mace | 111 | 67 | 
| 25125 | Retro-Spike Club | 114 | 68 | 
| 25126 | Anvilmar Hammer | 117 | 69 | 
| 25135 | Clefthoof Mace | 102 | 64 | 
| 25136 | Blood Stained Hammer | 105 | 65 | 
| 25137 | Draenethyst Mallet | 108 | 66 | 
| 25138 | Blood Knight Maul | 111 | 67 | 
| 25139 | Algaz Battle Hammer | 114 | 68 | 
| 25140 | Commanding Mallet | 117 | 69 | 
| 25149 | Baron's Broadsword | 102 | 64 | 
| 25150 | Honor Hold Saber | 105 | 65 | 
| 25151 | Assassins' Short Blade | 108 | 66 | 
| 25152 | Howling Sword | 111 | 67 | 
| 25153 | Gladiator Greatblade | 114 | 68 | 
| 25154 | Blood Groove Blade | 117 | 69 | 
| 25163 | Elexorien Blade | 102 | 64 | 
| 25164 | Crude Umbrafen Blade | 105 | 65 | 
| 25165 | Boulderfist Claymore | 108 | 66 | 
| 25166 | Mok'Nathal Warblade | 111 | 67 | 
| 25167 | Nethersteel Claymore | 114 | 68 | 
| 25168 | Sha'tari Longsword | 117 | 69 | 
| 25177 | Tanjo Staff | 102 | 64 | 
| 25178 | Bata Staff | 105 | 65 | 
| 25179 | Nguni Stick | 108 | 66 | 
| 25180 | Calenda Fighting Stick | 111 | 67 | 
| 25181 | Tapered Staff | 114 | 68 | 
| 25182 | Crystal-Etched Warstaff | 117 | 69 | 
| 25191 | Dread Fangs | 102 | 64 | 
| 25192 | Gutrippers | 105 | 65 | 
| 25193 | Deathclaw Talons | 108 | 66 | 
| 25194 | Serpent's Fangs | 111 | 67 | 
| 25195 | Diamond Tipped Claws | 114 | 68 | 
| 25196 | Boneshredder Claws | 117 | 69 | 
| 25205 | Silvermoon Crescent Axe | 102 | 64 | 
| 25206 | Berserker Axe | 105 | 65 | 
| 25207 | Shadowmoon Cleaver | 108 | 66 | 
| 25208 | Bladespire Broadaxe | 111 | 67 | 
| 25209 | Amani Tomahawk | 114 | 68 | 
| 25210 | Double-Bladed Axe | 117 | 69 | 
| 25219 | Rending Claw | 102 | 64 | 
| 25220 | Glorious War-Axe | 105 | 65 | 
| 25221 | Ghostly Battle Axe | 108 | 66 | 
| 25222 | Ceremonial Slayer's Axe | 111 | 67 | 
| 25223 | Windcaller Hatchet | 114 | 68 | 
| 25224 | Slavemaster Axe | 117 | 69 | 
| 25233 | Battle Scythe | 102 | 64 | 
| 25234 | Telaari Polearm | 105 | 65 | 
| 25235 | Ethereal-Etched Glaive | 108 | 66 | 
| 25236 | Grim Scythe | 111 | 67 | 
| 25237 | Nether Trident | 114 | 68 | 
| 25238 | Hellfire War Spear | 117 | 69 | 
| 25247 | Expert's Bow | 102 | 64 | 
| 25248 | Talbuk Hunting Bow | 105 | 65 | 
| 25249 | Ranger's Recurved Bow | 108 | 66 | 
| 25250 | Rocslayer Longbow | 111 | 67 | 
| 25251 | Orc Flatbow | 114 | 68 | 
| 25252 | Dream Catcher Bow | 117 | 69 | 
| 25261 | Mighty Crossbow | 102 | 64 | 
| 25262 | Battle Damaged Crossbow | 105 | 65 | 
| 25263 | Assassins' Silent Crossbow | 108 | 66 | 
| 25264 | Pocket Ballista | 111 | 67 | 
| 25265 | Barreled Crossbow | 114 | 68 | 
| 25266 | Well-Balanced Crossbow | 117 | 69 | 
| 25275 | Dragonbreath Musket | 102 | 64 | 
| 25276 | Tauren Runed Musket | 105 | 65 | 
| 25277 | Sporting Rifle | 108 | 66 | 
| 25278 | Nesingwary Longrifle | 111 | 67 | 
| 25279 | Sen'jin Longrifle | 114 | 68 | 
| 25280 | Game Hunter Musket | 117 | 69 | 
| 25289 | Majestic Wand | 102 | 64 | 
| 25290 | Solitaire Wand | 105 | 65 | 
| 25291 | Nobility Torch | 108 | 66 | 
| 25292 | Mechano-Wand | 111 | 67 | 
| 25293 | Draenethyst Wand | 114 | 68 | 
| 25294 | Dragonscale Wand | 117 | 69 | 
| 25303 | Amplifying Blade | 102 | 64 | 
| 25304 | Destructo-Blade | 105 | 65 | 
| 25305 | Elemental Dagger | 108 | 66 | 
| 25306 | Permafrost Dagger | 111 | 67 | 
| 25307 | Shadow Dagger | 114 | 68 | 
| 25308 | Thunder Spike | 117 | 69 | 
| 25317 | Lesser Sledgemace | 102 | 64 | 
| 25318 | Ancestral Hammer | 105 | 65 | 
| 25319 | Tranquility Mace | 108 | 66 | 
| 25320 | Queen's Insignia | 111 | 67 | 
| 25321 | Divine Hammer | 114 | 68 | 
| 25322 | Lordly Scepter | 117 | 69 | 
| 25331 | Vengeance Staff | 102 | 64 | 
| 25332 | Reflective Staff | 105 | 65 | 
| 25333 | Purification Staff | 108 | 66 | 
| 25334 | Intimidating Greatstaff | 111 | 67 | 
| 25335 | Feral Warp-Staff | 114 | 68 | 
| 25336 | Splintering Greatstaff | 117 | 69 | 
| 28538 | Forked Shuriken | 102 | 64 | 
| 28539 | Razor-Edged Boomerang | 105 | 65 | 
| 28540 | Arakkoa Talon-Axe | 108 | 66 | 
| 28541 | Sawshrike | 111 | 67 | 
| 28542 | Heartseeker Knives | 114 | 68 | 
| 28543 | Dreghood Throwing Axe | 117 | 69 | 
| 31289 | Staff of Divine Infusion | 109 | 68 | 
| 31291 | Crystalforged War Axe | 112 | 69 | 
| 31299 | The Oathkeeper | 115 | 68 | 
| 31303 | Valanos' Longbow | 115 | 70 | 
| 31304 | The Essence Focuser | 115 | 70 | 
| 31305 | Ced's Carver | 115 | 70 | 
| 31308 | The Bringer of Death | 115 | 70 | 

</details>

25107, 25108, 25109, 25110, 25111, 25112, 25121, 25122, 25123, 25124, 25125, 25126, 25135, 25136, 25137, 25138, 25139, 25140, 25149, 25150, 25151, 25152, 25153, 25154, 25163, 25164, 25165, 25166, 25167, 25168, 25177, 25178, 25179, 25180, 25181, 25182, 25191, 25192, 25193, 25194, 25195, 25196, 25205, 25206, 25207, 25208, 25209, 25210, 25219, 25220, 25221, 25222, 25223, 25224, 25233, 25234, 25235, 25236, 25237, 25238, 25247, 25248, 25249, 25250, 25251, 25252, 25261, 25262, 25263, 25264, 25265, 25266, 25275, 25276, 25277, 25278, 25279, 25280, 25289, 25290, 25291, 25292, 25293, 25294, 25303, 25304, 25305, 25306, 25307, 25308, 25317, 25318, 25319, 25320, 25321, 25322, 25331, 25332, 25333, 25334, 25335, 25336, 28538, 28539, 28540, 28541, 28542, 28543, 31289, 31291, 31299, 31303, 31304, 31305, 31308


All Q'D weapons (108 weapons):
```SQL
SELECT DISTINCT( it.entry), it.name, it.itemlevel, it.RequiredLevel
FROM `creature_template` ct
JOIN `creature_loot_template` clt ON ct.lootid = clt.entry
JOIN `reference_loot_template` rlt ON clt.Reference = rlt.Entry
JOIN `item_template` it ON it.entry = rlt.Item
WHERE ct.entry IN (24996, 24960, 25047, 24999, 25002, 24976, 24978, 24979, 25063, 25087, 
25548, 25073, 25060, 25001) AND it.class = 2 
```

<details>
<summary>Results</summary>

    item_template
---
| entry | name | itemlevel | RequiredLevel | 
| ---: | --- | ---: | ---: | 
| 25109 | Moon Blade | 108 | 66 | 
| 25110 | Sharp Bowie Knife | 111 | 67 | 
| 25111 | Lionhead Dagger | 114 | 68 | 
| 25112 | Fel Ripper | 117 | 69 | 
| 25113 | Phantom Dagger | 120 | 70 | 
| 25123 | Boneshredder Mace | 108 | 66 | 
| 25124 | Footman Mace | 111 | 67 | 
| 25125 | Retro-Spike Club | 114 | 68 | 
| 25126 | Anvilmar Hammer | 117 | 69 | 
| 25127 | Knight's War Hammer | 120 | 70 | 
| 25137 | Draenethyst Mallet | 108 | 66 | 
| 25138 | Blood Knight Maul | 111 | 67 | 
| 25139 | Algaz Battle Hammer | 114 | 68 | 
| 25140 | Commanding Mallet | 117 | 69 | 
| 25141 | Halaani Hammer | 120 | 70 | 
| 25151 | Assassins' Short Blade | 108 | 66 | 
| 25152 | Howling Sword | 111 | 67 | 
| 25153 | Gladiator Greatblade | 114 | 68 | 
| 25154 | Blood Groove Blade | 117 | 69 | 
| 25155 | Iron Skull Sword | 120 | 70 | 
| 25165 | Boulderfist Claymore | 108 | 66 | 
| 25166 | Mok'Nathal Warblade | 111 | 67 | 
| 25167 | Nethersteel Claymore | 114 | 68 | 
| 25168 | Sha'tari Longsword | 117 | 69 | 
| 25169 | Fel Orc Brute Sword | 120 | 70 | 
| 25179 | Nguni Stick | 108 | 66 | 
| 25180 | Calenda Fighting Stick | 111 | 67 | 
| 25181 | Tapered Staff | 114 | 68 | 
| 25182 | Crystal-Etched Warstaff | 117 | 69 | 
| 25183 | Voodoo Hex-Staff | 120 | 70 | 
| 25193 | Deathclaw Talons | 108 | 66 | 
| 25194 | Serpent's Fangs | 111 | 67 | 
| 25195 | Diamond Tipped Claws | 114 | 68 | 
| 25196 | Boneshredder Claws | 117 | 69 | 
| 25197 | Razor Scythes | 120 | 70 | 
| 25207 | Shadowmoon Cleaver | 108 | 66 | 
| 25208 | Bladespire Broadaxe | 111 | 67 | 
| 25209 | Amani Tomahawk | 114 | 68 | 
| 25210 | Double-Bladed Axe | 117 | 69 | 
| 25211 | Rockbiter Cutter | 120 | 70 | 
| 25221 | Ghostly Battle Axe | 108 | 66 | 
| 25222 | Ceremonial Slayer's Axe | 111 | 67 | 
| 25223 | Windcaller Hatchet | 114 | 68 | 
| 25224 | Slavemaster Axe | 117 | 69 | 
| 25225 | Deepforge Broadaxe | 120 | 70 | 
| 25235 | Ethereal-Etched Glaive | 108 | 66 | 
| 25236 | Grim Scythe | 111 | 67 | 
| 25237 | Nether Trident | 114 | 68 | 
| 25238 | Hellfire War Spear | 117 | 69 | 
| 25239 | Legend's Glaive | 120 | 70 | 
| 25249 | Ranger's Recurved Bow | 108 | 66 | 
| 25250 | Rocslayer Longbow | 111 | 67 | 
| 25251 | Orc Flatbow | 114 | 68 | 
| 25252 | Dream Catcher Bow | 117 | 69 | 
| 25253 | Windspear Longbow | 120 | 70 | 
| 25263 | Assassins' Silent Crossbow | 108 | 66 | 
| 25264 | Pocket Ballista | 111 | 67 | 
| 25265 | Barreled Crossbow | 114 | 68 | 
| 25266 | Well-Balanced Crossbow | 117 | 69 | 
| 25267 | Rampant Crossbow | 120 | 70 | 
| 25277 | Sporting Rifle | 108 | 66 | 
| 25278 | Nesingwary Longrifle | 111 | 67 | 
| 25279 | Sen'jin Longrifle | 114 | 68 | 
| 25280 | Game Hunter Musket | 117 | 69 | 
| 25281 | Big-Boar Battle Rifle | 120 | 70 | 
| 25291 | Nobility Torch | 108 | 66 | 
| 25292 | Mechano-Wand | 111 | 67 | 
| 25293 | Draenethyst Wand | 114 | 68 | 
| 25294 | Dragonscale Wand | 117 | 69 | 
| 25295 | Flawless Wand | 120 | 70 | 
| 25305 | Elemental Dagger | 108 | 66 | 
| 25306 | Permafrost Dagger | 111 | 67 | 
| 25307 | Shadow Dagger | 114 | 68 | 
| 25308 | Thunder Spike | 117 | 69 | 
| 25309 | Warpdagger | 120 | 70 | 
| 25319 | Tranquility Mace | 108 | 66 | 
| 25320 | Queen's Insignia | 111 | 67 | 
| 25321 | Divine Hammer | 114 | 68 | 
| 25322 | Lordly Scepter | 117 | 69 | 
| 25323 | Ascendant's Scepter | 120 | 70 | 
| 25333 | Purification Staff | 108 | 66 | 
| 25334 | Intimidating Greatstaff | 111 | 67 | 
| 25335 | Feral Warp-Staff | 114 | 68 | 
| 25336 | Splintering Greatstaff | 117 | 69 | 
| 25337 | Swarming Sting-Staff | 120 | 70 | 
| 25397 | Eroded Axe | 69 | 64 | 
| 25398 | Stone Reaper | 69 | 64 | 
| 25399 | Deteriorating Blade | 69 | 64 | 
| 25400 | Tarnished Claymore | 69 | 64 | 
| 25401 | Corroded Mace | 69 | 64 | 
| 25402 | The Stoppable Force | 69 | 64 | 
| 25403 | Sharpened Stilleto | 69 | 64 | 
| 25404 | Dense War Staff | 69 | 64 | 
| 25405 | Rusted Musket | 69 | 64 | 
| 25406 | Broken Longbow | 69 | 64 | 
| 28540 | Arakkoa Talon-Axe | 108 | 66 | 
| 28541 | Sawshrike | 111 | 67 | 
| 28542 | Heartseeker Knives | 114 | 68 | 
| 28543 | Dreghood Throwing Axe | 117 | 69 | 
| 28544 | Assassin's Shuriken | 120 | 70 | 
| 31234 | Crystalblade of the Draenei | 103 | 66 | 
| 31289 | Staff of Divine Infusion | 109 | 68 | 
| 31291 | Crystalforged War Axe | 112 | 69 | 
| 31299 | The Oathkeeper | 115 | 68 | 
| 31303 | Valanos' Longbow | 115 | 70 | 
| 31304 | The Essence Focuser | 115 | 70 | 
| 31305 | Ced's Carver | 115 | 70 | 
| 31308 | The Bringer of Death | 115 | 70 | 

</details>

25109, 25110, 25111, 25112, 25113, 25123, 25124, 25125, 25126, 25127, 25137, 25138, 25139, 25140, 25141, 25151, 25152, 25153, 25154, 25155, 25165, 25166, 25167, 25168, 25169, 25179, 25180, 25181, 25182, 25183, 25193, 25194, 25195, 25196, 25197, 25207, 25208, 25209, 25210, 25211, 25221, 25222, 25223, 25224, 25225, 25235, 25236, 25237, 25238, 25239, 25249, 25250, 25251, 25252, 25253, 25263, 25264, 25265, 25266, 25267, 25277, 25278, 25279, 25280, 25281, 25291, 25292, 25293, 25294, 25295, 25305, 25306, 25307, 25308, 25309, 25319, 25320, 25321, 25322, 25323, 25333, 25334, 25335, 25336, 25337, 25397, 25398, 25399, 25400, 25401, 25402, 25403, 25404, 25405, 25406, 28540, 28541, 28542, 28543, 28544, 31234, 31289, 31291, 31299, 31303, 31304, 31305, 31308

