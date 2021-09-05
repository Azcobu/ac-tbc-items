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
