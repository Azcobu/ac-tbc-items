### Projectiles (class = 6)
Vanilla projectiles go up to lvl 61. TBC projectiles start at ilvl 80 (wicked arrows/impact shot, lvl 55 req.) - however, as of 2.0, both these were sold in the old world. Quick check shows they are already sold by 53 vendors across the old world. 

The next TBC ammo is ilvl 97, so easy to define a breakpoint. 

```SQL
SELECT it.entry, it.name,it.ItemLevel, it.RequiredLevel
FROM `item_template` it
WHERE it.class = 6
AND it.ItemLevel >= 97
```

<details>
<summary>Results</summary>

item_template
---
| entry | name | ItemLevel | RequiredLevel | 
| ---: | --- | ---: | ---: | 
| 23772 | Fel Iron Shells | 97 | 57 | 
| 23773 | Adamantite Shells | 118 | 62 | 
| 24412 | Warden's Arrow | 115 | 62 | 
| 24417 | Scout's Arrow | 97 | 61 | 
| 28056 | Blackflight Arrow | 118 | 65 | 
| 28061 | Ironbite Shell | 118 | 65 | 
| 29885 | Hunter 120 Epic Test Bullets | 120 | 62 | 
| 30319 | Nether Spike | 175 | 70 | 
| 30611 | Halaani Razorshaft | 107 | 66 | 
| 30612 | Halaani Grimshot | 107 | 66 | 
| 31735 | Timeless Shell | 145 | 70 | 
| 31737 | Timeless Arrow | 145 | 70 | 
| 31949 | Warden's Arrow | 115 | 68 | 
| 32760 | The Macho Gnome's Arrow | 145 | 70 | 
| 32761 | The Sarge's Bullet | 145 | 70 | 
| 32882 | Hellfire Shot | 115 | 68 | 
| 32883 | Felbane Slugs | 115 | 68 | 
| 33803 | Adamantite Stinger | 118 | 62 | 
| 34581 | Mysterious Arrow | 120 | 70 | 
| 34582 | Mysterious Shell | 120 | 70 | 
| 41164 | Mammoth Cutters | 200 | 72 | 
| 41165 | Saronite Razorheads | 200 | 72 | 
| 41584 | Frostbite Bullets | 154 | 75 | 
| 41586 | Terrorshaft Arrow | 154 | 75 | 
| 52020 | Shatter Rounds | 230 | 80 | 
| 52021 | Iceblade Arrow | 230 | 80 | 

</details>

This is **without** Wicked Arrows/Impact Shot:

23772, 23773, 24412, 24417, 28056, 28061, 29885, 30319, 30611, 30612, 31735, 31737, 31949, 32760, 32761, 32882, 32883, 33803, 34581, 34582, 41164, 41165, 41584, 41586, 52020, 52021



