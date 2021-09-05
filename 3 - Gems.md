- gems (class = 3): vanilla has 2 ilvl 55 and 3 ilvl 60 gems, all itemid <= 12800. Highest vanilla gem index seems to be souldarite, 19774.  The TBC gems start at 55 and all have item ids > 23000
So this query finds all TBC/Wrath gems:

SELECT it.entry, it.name, it.ItemLevel
FROM `item_template` it
WHERE it.class = 3 AND it.itemlevel >= 55 AND it.entry > 20000
