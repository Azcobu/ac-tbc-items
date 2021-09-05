recipes (class = 9)
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
