
- ## Quivers (class = 11)
	Vanilla quivers go up to ilvl 75 (Ancient Sinew Wrapped Lamina 18714) and 2 x ilvl 60s (harpy hide quiver 19319, gnoll skin bandolier 19320). TBC quivers start at ilvl 70, but have indices in the 29K range. So item ID breakpoint works:
	
	```SQL
	SELECT it.entry , it.name, it.ItemLevel, it.RequiredSkillRank 
	FROM item_template it 
	WHERE it.class = 11
	AND it.ItemLevel >= 60 AND it.entry > 29000
	```
	
	<details>
	<summary>Results</summary>
	
	---
	| entry | name | ItemLevel | RequiredSkillRank | 
	| ---: | --- | ---: | ---: | 
	| 29118 | Smuggler's Ammo Pouch | 103 | 0 | 
	| 29143 | Clefthoof Hide Quiver | 109 | 0 | 
	| 29144 | Worg Hide Quiver | 109 | 0 | 
	| 34099 | Knothide Ammo Pouch | 70 | 0 | 
	| 34100 | Knothide Quiver | 70 | 0 | 
	| 34105 | Quiver of a Thousand Feathers | 70 | 0 | 
	| 34106 | Netherscale Ammo Pouch | 70 | 0 | 
	| 44447 | Dragonscale Ammo Pouch | 75 | 0 | 
	| 44448 | Nerubian Reinforced Quiver | 75 | 0 | 

	</details>
	
	29118, 29143, 29144, 34099, 34100, 34105, 34106, 44447, 44448

