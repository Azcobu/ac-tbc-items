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
