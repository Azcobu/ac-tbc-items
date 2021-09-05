### Gems (class = 3): 
Vanilla has 2 ilvl 55 and 3 ilvl 60 gems, all itemid <= 12800. Highest vanilla gem index seems to be souldarite, 19774.  The TBC gems start at 55 and all have item ids > 23000. So this query finds all TBC/Wrath gems:
```SQL
SELECT it.entry, it.name, it.ItemLevel
FROM `item_template` it
WHERE it.class = 3 AND it.itemlevel >= 55 AND it.entry > 20000
```

<details>
<summary>Results</summary>
  
---
| entry | name | ItemLevel | 
| ---: | --- | ---: | 
| 21929 | Flame Spessarite | 65 | 
| 22459 | Void Sphere | 70 | 
| 22460 | Prismatic Sphere | 70 | 
| 23077 | Blood Garnet | 65 | 
| 23079 | Deep Peridot | 65 | 
| 23094 | Teardrop Blood Garnet | 60 | 
| 23095 | Bold Blood Garnet | 60 | 
| 23096 | Runed Blood Garnet | 60 | 
| 23097 | Delicate Blood Garnet | 60 | 
| 23098 | Inscribed Flame Spessarite | 60 | 
| 23099 | Luminous Flame Spessarite | 60 | 
| 23100 | Glinting Flame Spessarite | 60 | 
| 23101 | Potent Flame Spessarite | 60 | 
| 23103 | Radiant Deep Peridot | 60 | 
| 23104 | Jagged Deep Peridot | 60 | 
| 23105 | Enduring Deep Peridot | 60 | 
| 23106 | Dazzling Deep Peridot | 60 | 
| 23107 | Shadow Draenite | 65 | 
| 23108 | Glowing Shadow Draenite | 60 | 
| 23109 | Royal Shadow Draenite | 60 | 
| 23110 | Shifting Shadow Draenite | 60 | 
| 23111 | Sovereign Shadow Draenite | 60 | 
| 23112 | Golden Draenite | 65 | 
| 23113 | Brilliant Golden Draenite | 60 | 
| 23114 | Gleaming Golden Draenite | 60 | 
| 23115 | Thick Golden Draenite | 60 | 
| 23116 | Rigid Golden Draenite | 60 | 
| 23117 | Azure Moonstone | 65 | 
| 23118 | Solid Azure Moonstone | 60 | 
| 23119 | Sparkling Azure Moonstone | 60 | 
| 23120 | Stormy Azure Moonstone | 60 | 
| 23121 | Lustrous Azure Moonstone | 60 | 
| 23436 | Living Ruby | 70 | 
| 23437 | Talasite | 70 | 
| 23438 | Star of Elune | 70 | 
| 23439 | Noble Topaz | 70 | 
| 23440 | Dawnstone | 70 | 
| 23441 | Nightseye | 70 | 
| 24027 | Bold Living Ruby | 70 | 
| 24028 | Delicate Living Ruby | 70 | 
| 24029 | Teardrop Living Ruby | 70 | 
| 24030 | Runed Living Ruby | 70 | 
| 24031 | Bright Living Ruby | 70 | 
| 24032 | Subtle Living Ruby | 70 | 
| 24033 | Solid Star of Elune | 70 | 
| 24035 | Sparkling Star of Elune | 70 | 
| 24036 | Flashing Living Ruby | 70 | 
| 24037 | Lustrous Star of Elune | 70 | 
| 24039 | Stormy Star of Elune | 70 | 
| 24047 | Brilliant Dawnstone | 70 | 
| 24048 | Smooth Dawnstone | 70 | 
| 24050 | Gleaming Dawnstone | 70 | 
| 24051 | Rigid Dawnstone | 70 | 
| 24052 | Thick Dawnstone | 70 | 
| 24053 | Mystic Dawnstone | 70 | 
| 24054 | Sovereign Nightseye | 70 | 
| 24055 | Shifting Nightseye | 70 | 
| 24056 | Glowing Nightseye | 70 | 
| 24057 | Royal Nightseye | 70 | 
| 24058 | Inscribed Noble Topaz | 70 | 
| 24059 | Potent Noble Topaz | 70 | 
| 24060 | Luminous Noble Topaz | 70 | 
| 24061 | Glinting Noble Topaz | 70 | 
| 24062 | Enduring Talasite | 70 | 
| 24065 | Dazzling Talasite | 70 | 
| 24066 | Radiant Talasite | 70 | 
| 24067 | Jagged Talasite | 70 | 
| 25867 | Earthstorm Diamond | 70 | 
| 25868 | Skyfire Diamond | 70 | 
| 25890 | Destructive Skyfire Diamond | 70 | 
| 25893 | Mystical Skyfire Diamond | 70 | 
| 25894 | Swift Skyfire Diamond | 70 | 
| 25895 | Enigmatic Skyfire Diamond | 70 | 
| 25896 | Powerful Earthstorm Diamond | 70 | 
| 25897 | Bracing Earthstorm Diamond | 70 | 
| 25898 | Tenacious Earthstorm Diamond | 70 | 
| 25899 | Brutal Earthstorm Diamond | 70 | 
| 25901 | Insightful Earthstorm Diamond | 70 | 
| 27679 | Sublime Mystic Dawnstone | 60 | 
| 27777 | Stark Blood Garnet | 60 | 
| 27785 | Notched Deep Peridot | 60 | 
| 27786 | Barbed Deep Peridot | 60 | 
| 27809 | Barbed Deep Peridot | 60 | 
| 27812 | Stark Blood Garnet | 60 | 
| 27820 | Notched Deep Peridot | 60 | 
| 28118 | Runed Ornate Ruby | 60 | 
| 28119 | Smooth Ornate Dawnstone | 60 | 
| 28120 | Gleaming Ornate Dawnstone | 60 | 
| 28123 | Potent Ornate Topaz | 60 | 
| 28290 | Smooth Golden Draenite | 60 | 
| 28360 | Mighty Blood Garnet | 60 | 
| 28361 | Mighty Blood Garnet | 60 | 
| 28362 | Bold Ornate Ruby | 60 | 
| 28363 | Inscribed Ornate Topaz | 60 | 
| 28458 | Bold Tourmaline | 55 | 
| 28459 | Delicate Tourmaline | 55 | 
| 28460 | Teardrop Tourmaline | 55 | 
| 28461 | Runed Tourmaline | 55 | 
| 28462 | Bright Tourmaline | 55 | 
| 28463 | Solid Zircon | 55 | 
| 28464 | Sparkling Zircon | 55 | 
| 28465 | Lustrous Zircon | 55 | 
| 28466 | Brilliant Amber | 55 | 
| 28467 | Smooth Amber | 55 | 
| 28468 | Rigid Amber | 55 | 
| 28469 | Gleaming Amber | 55 | 
| 28470 | Thick Amber | 55 | 
| 28556 | Swift Windfire Diamond | 70 | 
| 28557 | Swift Starfire Diamond | 70 | 
| 28595 | Bright Blood Garnet | 60 | 
| 30546 | Sovereign Tanzanite | 70 | 
| 30547 | Luminous Fire Opal | 70 | 
| 30548 | Polished Chrysoprase | 70 | 
| 30549 | Shifting Tanzanite | 70 | 
| 30550 | Sundered Chrysoprase | 70 | 
| 30551 | Infused Fire Opal | 70 | 
| 30552 | Blessed Tanzanite | 70 | 
| 30553 | Pristine Fire Opal | 70 | 
| 30554 | Stalwart Fire Opal | 70 | 
| 30555 | Glowing Tanzanite | 70 | 
| 30556 | Glinting Fire Opal | 70 | 
| 30558 | Glimmering Fire Opal | 70 | 
| 30559 | Etched Fire Opal | 70 | 
| 30560 | Rune Covered Chrysoprase | 70 | 
| 30563 | Regal Tanzanite | 70 | 
| 30564 | Shining Fire Opal | 70 | 
| 30565 | Assassin's Fire Opal | 70 | 
| 30566 | Defender's Tanzanite | 70 | 
| 30571 | Don Rodrigo's Heart | 60 | 
| 30572 | Imperial Tanzanite | 70 | 
| 30573 | Mysterious Fire Opal | 70 | 
| 30574 | Brutal Tanzanite | 70 | 
| 30575 | Nimble Fire Opal | 70 | 
| 30581 | Durable Fire Opal | 70 | 
| 30582 | Deadly Fire Opal | 70 | 
| 30583 | Timeless Chrysoprase | 70 | 
| 30584 | Enscribed Fire Opal | 70 | 
| 30585 | Glistening Fire Opal | 70 | 
| 30586 | Seer's Chrysoprase | 70 | 
| 30587 | Champion's Fire Opal | 70 | 
| 30588 | Potent Fire Opal | 70 | 
| 30589 | Dazzling Chrysoprase | 70 | 
| 30590 | Enduring Chrysoprase | 70 | 
| 30591 | Empowered Fire Opal | 70 | 
| 30592 | Steady Chrysoprase | 70 | 
| 30593 | Iridescent Fire Opal | 70 | 
| 30594 | Effulgent Chrysoprase | 70 | 
| 30598 | Don Amancio's Heart | 60 | 
| 30600 | Fluorescent Tanzanite | 70 | 
| 30601 | Beaming Fire Opal | 70 | 
| 30602 | Jagged Chrysoprase | 70 | 
| 30603 | Royal Tanzanite | 70 | 
| 30604 | Resplendent Fire Opal | 70 | 
| 30605 | Vivid Chrysoprase | 70 | 
| 30606 | Lambent Chrysoprase | 70 | 
| 30607 | Splendid Fire Opal | 70 | 
| 30608 | Radiant Chrysoprase | 70 | 
| 31116 | Infused Amethyst | 70 | 
| 31117 | Soothing Amethyst | 70 | 
| 31118 | Pulsing Amethyst | 70 | 
| 31860 | Great Golden Draenite | 60 | 
| 31861 | Great Dawnstone | 70 | 
| 31862 | Balanced Shadow Draenite | 60 | 
| 31863 | Balanced Nightseye | 70 | 
| 31864 | Infused Shadow Draenite | 60 | 
| 31865 | Infused Nightseye | 70 | 
| 31866 | Veiled Flame Spessarite | 60 | 
| 31867 | Veiled Noble Topaz | 70 | 
| 31868 | Wicked Noble Topaz | 70 | 
| 31869 | Wicked Flame Spessarite | 60 | 
| 32193 | Bold Crimson Spinel | 70 | 
| 32194 | Delicate Crimson Spinel | 70 | 
| 32195 | Teardrop Crimson Spinel | 70 | 
| 32196 | Runed Crimson Spinel | 70 | 
| 32197 | Bright Crimson Spinel | 70 | 
| 32198 | Subtle Crimson Spinel | 70 | 
| 32199 | Flashing Crimson Spinel | 70 | 
| 32200 | Solid Empyrean Sapphire | 70 | 
| 32201 | Sparkling Empyrean Sapphire | 70 | 
| 32202 | Lustrous Empyrean Sapphire | 70 | 
| 32203 | Stormy Empyrean Sapphire | 70 | 
| 32204 | Brilliant Lionseye | 70 | 
| 32205 | Smooth Lionseye | 70 | 
| 32206 | Rigid Lionseye | 70 | 
| 32207 | Gleaming Lionseye | 70 | 
| 32208 | Thick Lionseye | 70 | 
| 32209 | Mystic Lionseye | 70 | 
| 32210 | Great Lionseye | 70 | 
| 32211 | Sovereign Shadowsong Amethyst | 70 | 
| 32212 | Shifting Shadowsong Amethyst | 70 | 
| 32213 | Balanced Shadowsong Amethyst | 70 | 
| 32214 | Infused Shadowsong Amethyst | 70 | 
| 32215 | Glowing Shadowsong Amethyst | 70 | 
| 32216 | Royal Shadowsong Amethyst | 70 | 
| 32217 | Inscribed Pyrestone | 70 | 
| 32218 | Potent Pyrestone | 70 | 
| 32219 | Luminous Pyrestone | 70 | 
| 32220 | Glinting Pyrestone | 70 | 
| 32221 | Veiled Pyrestone | 70 | 
| 32222 | Wicked Pyrestone | 70 | 
| 32223 | Enduring Seaspray Emerald | 70 | 
| 32224 | Radiant Seaspray Emerald | 70 | 
| 32225 | Dazzling Seaspray Emerald | 70 | 
| 32226 | Jagged Seaspray Emerald | 70 | 
| 32227 | Crimson Spinel | 70 | 
| 32228 | Empyrean Sapphire | 70 | 
| 32229 | Lionseye | 70 | 
| 32230 | Shadowsong Amethyst | 70 | 
| 32231 | Pyrestone | 70 | 
| 32249 | Seaspray Emerald | 70 | 
| 32409 | Relentless Earthstorm Diamond | 70 | 
| 32410 | Thundering Skyfire Diamond | 70 | 
| 32634 | Unstable Amethyst | 70 | 
| 32635 | Unstable Peridot | 70 | 
| 32636 | Unstable Sapphire | 70 | 
| 32637 | Unstable Citrine | 70 | 
| 32638 | Unstable Topaz | 70 | 
| 32639 | Unstable Talasite | 70 | 
| 32640 | Potent Unstable Diamond | 70 | 
| 32641 | Imbued Unstable Diamond | 70 | 
| 32735 | Radiant Spencerite | 70 | 
| 32833 | Purified Jaggal Pearl | 60 | 
| 32836 | Purified Shadow Pearl | 60 | 
| 33060 | Soulbound Test Gem | 70 | 
| 33131 | Crimson Sun | 70 | 
| 33132 | Delicate Fire Ruby | 70 | 
| 33133 | Don Julio's Heart | 70 | 
| 33134 | Kailee's Rose | 70 | 
| 33135 | Falling Star | 70 | 
| 33137 | Sparkling Falling Star | 70 | 
| 33138 | Mystic Bladestone | 70 | 
| 33139 | Brilliant Bladestone | 70 | 
| 33140 | Blood of Amber | 70 | 
| 33141 | Great Bladestone | 70 | 
| 33142 | Rigid Bladestone | 70 | 
| 33143 | Stone of Blades | 70 | 
| 33144 | Facet of Eternity | 70 | 
| 33782 | Steady Talasite | 70 | 
| 34142 | Infinite Sphere | 75 | 
| 34143 | Chromatic Sphere | 80 | 
| 34220 | Chaotic Skyfire Diamond | 70 | 
| 34256 | Charmed Amani Jewel | 70 | 
| 34627 | Heavy Tonk Armor | 70 | 
| 34831 | Eye of the Sea | 70 | 
| 34967 | Juno's Test Gem | 70 | 
| 35315 | Quick Dawnstone | 70 | 
| 35316 | Reckless Noble Topaz | 70 | 
| 35318 | Forceful Talasite | 70 | 
| 35487 | Bright Crimson Spinel | 70 | 
| 35488 | Runed Crimson Spinel | 70 | 
| 35489 | Teardrop Crimson Spinel | 70 | 
| 35501 | Eternal Earthstorm Diamond | 70 | 
| 35503 | Ember Skyfire Diamond | 70 | 
| 35707 | Regal Nightseye | 70 | 
| 35758 | Steady Seaspray Emerald | 70 | 
| 35759 | Forceful Seaspray Emerald | 70 | 
| 35760 | Reckless Pyrestone | 70 | 
| 35761 | Quick Lionseye | 70 | 
| 36766 | Bright Dragon's Eye | 80 | 
| 36767 | Solid Dragon's Eye | 80 | 
| 36783 | Northsea Pearl | 75 | 
| 36784 | Siren's Tear | 75 | 
| 36917 | Bloodstone | 75 | 
| 36918 | Scarlet Ruby | 80 | 
| 36919 | Cardinal Ruby | 80 | 
| 36920 | Sun Crystal | 75 | 
| 36921 | Autumn's Glow | 80 | 
| 36922 | King's Amber | 80 | 
| 36923 | Chalcedony | 75 | 
| 36924 | Sky Sapphire | 80 | 
| 36925 | Majestic Zircon | 80 | 
| 36926 | Shadow Crystal | 75 | 
| 36927 | Twilight Opal | 80 | 
| 36928 | Dreadstone | 80 | 
| 36929 | Huge Citrine | 75 | 
| 36930 | Monarch Topaz | 80 | 
| 36931 | Ametrine | 80 | 
| 36932 | Dark Jade | 75 | 
| 36933 | Forest Emerald | 80 | 
| 36934 | Eye of Zul | 80 | 
| 37430 | Solid Sky Sapphire (Unused) | 80 | 
| 37503 | Purified Shadowsong Amethyst | 70 | 
| 38292 | Test Living Ruby | 70 | 
| 38538 | Riding Crop | 70 | 
| 38545 | Bold Ornate Ruby | 60 | 
| 38546 | Gleaming Ornate Dawnstone | 60 | 
| 38547 | Inscribed Ornate Topaz | 60 | 
| 38548 | Potent Ornate Topaz | 60 | 
| 38549 | Runed Ornate Ruby | 60 | 
| 38550 | Smooth Ornate Dawnstone | 60 | 
| 39900 | Bold Bloodstone | 70 | 
| 39905 | Delicate Bloodstone | 70 | 
| 39906 | Bright Bloodstone | 70 | 
| 39907 | Subtle Bloodstone | 70 | 
| 39908 | Flashing Bloodstone | 70 | 
| 39909 | Fractured Bloodstone | 70 | 
| 39910 | Precise Bloodstone | 70 | 
| 39911 | Runed Bloodstone | 70 | 
| 39912 | Brilliant Sun Crystal | 70 | 
| 39914 | Smooth Sun Crystal | 70 | 
| 39915 | Rigid Sun Crystal | 70 | 
| 39916 | Thick Sun Crystal | 70 | 
| 39917 | Mystic Sun Crystal | 70 | 
| 39918 | Quick Sun Crystal | 70 | 
| 39919 | Solid Chalcedony | 70 | 
| 39920 | Sparkling Chalcedony | 70 | 
| 39927 | Lustrous Chalcedony | 70 | 
| 39932 | Stormy Chalcedony | 70 | 
| 39933 | Puissant Shadow Crystal | 70 | 
| 39934 | Sovereign Shadow Crystal | 70 | 
| 39935 | Shifting Shadow Crystal | 70 | 
| 39936 | Glowing Shadow Crystal | 70 | 
| 39937 | Balanced Shadow Crystal | 70 | 
| 39938 | Regal Shadow Crystal | 70 | 
| 39939 | Defender's Shadow Crystal | 70 | 
| 39940 | Guardian's Shadow Crystal | 70 | 
| 39941 | Purified Shadow Crystal | 70 | 
| 39942 | Tenuous Shadow Crystal | 70 | 
| 39943 | Royal Shadow Crystal | 70 | 
| 39944 | Infused Shadow Crystal | 70 | 
| 39945 | Mysterious Shadow Crystal | 70 | 
| 39946 | Luminous Huge Citrine | 70 | 
| 39947 | Inscribed Huge Citrine | 70 | 
| 39948 | Etched Huge Citrine | 70 | 
| 39949 | Champion's Huge Citrine | 70 | 
| 39950 | Resplendent Huge Citrine | 70 | 
| 39951 | Fierce Huge Citrine | 70 | 
| 39952 | Deadly Huge Citrine | 70 | 
| 39953 | Glinting Huge Citrine | 70 | 
| 39954 | Lucent Huge Citrine | 70 | 
| 39955 | Deft Huge Citrine | 70 | 
| 39956 | Potent Huge Citrine | 70 | 
| 39957 | Veiled Huge Citrine | 70 | 
| 39958 | Durable Huge Citrine | 70 | 
| 39959 | Reckless Huge Citrine | 70 | 
| 39960 | Wicked Huge Citrine | 70 | 
| 39961 | Pristine Huge Citrine | 70 | 
| 39962 | Empowered Huge Citrine | 70 | 
| 39963 | Stark Huge Citrine | 70 | 
| 39964 | Stalwart Huge Citrine | 70 | 
| 39965 | Glimmering Huge Citrine | 70 | 
| 39966 | Accurate Huge Citrine | 70 | 
| 39967 | Resolute Huge Citrine | 70 | 
| 39968 | Timeless Dark Jade | 70 | 
| 39974 | Jagged Dark Jade | 70 | 
| 39975 | Vivid Dark Jade | 70 | 
| 39976 | Enduring Dark Jade | 70 | 
| 39977 | Steady Dark Jade | 70 | 
| 39978 | Forceful Dark Jade | 70 | 
| 39979 | Seer's Dark Jade | 70 | 
| 39980 | Misty Dark Jade | 70 | 
| 39981 | Shining Dark Jade | 70 | 
| 39982 | Turbid Dark Jade | 70 | 
| 39983 | Intricate Dark Jade | 70 | 
| 39984 | Dazzling Dark Jade | 70 | 
| 39985 | Sundered Dark Jade | 70 | 
| 39986 | Lambent Dark Jade | 70 | 
| 39988 | Opaque Dark Jade | 70 | 
| 39989 | Energized Dark Jade | 70 | 
| 39990 | Radiant Dark Jade | 70 | 
| 39991 | Tense Dark Jade | 70 | 
| 39992 | Shattered Dark Jade | 70 | 
| 39996 | Bold Scarlet Ruby | 80 | 
| 39997 | Delicate Scarlet Ruby | 80 | 
| 39998 | Runed Scarlet Ruby | 80 | 
| 39999 | Bright Scarlet Ruby | 80 | 
| 40000 | Subtle Scarlet Ruby | 80 | 
| 40001 | Flashing Scarlet Ruby | 80 | 
| 40002 | Fractured Scarlet Ruby | 80 | 
| 40003 | Precise Scarlet Ruby | 80 | 
| 40008 | Solid Sky Sapphire | 80 | 
| 40009 | Sparkling Sky Sapphire | 80 | 
| 40010 | Lustrous Sky Sapphire | 80 | 
| 40011 | Stormy Sky Sapphire | 80 | 
| 40012 | Brilliant Autumn's Glow | 80 | 
| 40013 | Smooth Autumn's Glow | 80 | 
| 40014 | Rigid Autumn's Glow | 80 | 
| 40015 | Thick Autumn's Glow | 80 | 
| 40016 | Mystic Autumn's Glow | 80 | 
| 40017 | Quick Autumn's Glow | 80 | 
| 40022 | Sovereign Twilight Opal | 80 | 
| 40023 | Shifting Twilight Opal | 80 | 
| 40024 | Tenuous Twilight Opal | 80 | 
| 40025 | Glowing Twilight Opal | 80 | 
| 40026 | Purified Twilight Opal | 80 | 
| 40027 | Royal Twilight Opal | 80 | 
| 40028 | Mysterious Twilight Opal | 80 | 
| 40029 | Balanced Twilight Opal | 80 | 
| 40030 | Infused Twilight Opal | 80 | 
| 40031 | Regal Twilight Opal | 80 | 
| 40032 | Defender's Twilight Opal | 80 | 
| 40033 | Puissant Twilight Opal | 80 | 
| 40034 | Guardian's Twilight Opal | 80 | 
| 40037 | Inscribed Monarch Topaz | 80 | 
| 40038 | Etched Monarch Topaz | 80 | 
| 40039 | Champion's Monarch Topaz | 80 | 
| 40040 | Resplendent Monarch Topaz | 80 | 
| 40041 | Fierce Monarch Topaz | 80 | 
| 40043 | Deadly Monarch Topaz | 80 | 
| 40044 | Glinting Monarch Topaz | 80 | 
| 40045 | Lucent Monarch Topaz | 80 | 
| 40046 | Deft Monarch Topaz | 80 | 
| 40047 | Luminous Monarch Topaz | 80 | 
| 40048 | Potent Monarch Topaz | 80 | 
| 40049 | Veiled Monarch Topaz | 80 | 
| 40050 | Durable Monarch Topaz | 80 | 
| 40051 | Reckless Monarch Topaz | 80 | 
| 40052 | Wicked Monarch Topaz | 80 | 
| 40053 | Pristine Monarch Topaz | 80 | 
| 40054 | Empowered Monarch Topaz | 80 | 
| 40055 | Stark Monarch Topaz | 80 | 
| 40056 | Stalwart Monarch Topaz | 80 | 
| 40057 | Glimmering Monarch Topaz | 80 | 
| 40058 | Accurate Monarch Topaz | 80 | 
| 40059 | Resolute Monarch Topaz | 80 | 
| 40085 | Timeless Forest Emerald | 80 | 
| 40086 | Jagged Forest Emerald | 80 | 
| 40088 | Vivid Forest Emerald | 80 | 
| 40089 | Enduring Forest Emerald | 80 | 
| 40090 | Steady Forest Emerald | 80 | 
| 40091 | Forceful Forest Emerald | 80 | 
| 40092 | Seer's Forest Emerald | 80 | 
| 40094 | Dazzling Forest Emerald | 80 | 
| 40095 | Misty Forest Emerald | 80 | 
| 40096 | Sundered Forest Emerald | 80 | 
| 40098 | Radiant Forest Emerald | 80 | 
| 40099 | Shining Forest Emerald | 80 | 
| 40100 | Lambent Forest Emerald | 80 | 
| 40101 | Tense Forest Emerald | 80 | 
| 40102 | Turbid Forest Emerald | 80 | 
| 40103 | Opaque Forest Emerald | 80 | 
| 40104 | Intricate Forest Emerald | 80 | 
| 40105 | Energized Forest Emerald | 80 | 
| 40106 | Shattered Forest Emerald | 80 | 
| 40111 | Bold Cardinal Ruby | 80 | 
| 40112 | Delicate Cardinal Ruby | 80 | 
| 40113 | Runed Cardinal Ruby | 80 | 
| 40114 | Bright Cardinal Ruby | 80 | 
| 40115 | Subtle Cardinal Ruby | 80 | 
| 40116 | Flashing Cardinal Ruby | 80 | 
| 40117 | Fractured Cardinal Ruby | 80 | 
| 40118 | Precise Cardinal Ruby | 80 | 
| 40119 | Solid Majestic Zircon | 80 | 
| 40120 | Sparkling Majestic Zircon | 80 | 
| 40121 | Lustrous Majestic Zircon | 80 | 
| 40122 | Stormy Majestic Zircon | 80 | 
| 40123 | Brilliant King's Amber | 80 | 
| 40124 | Smooth King's Amber | 80 | 
| 40125 | Rigid King's Amber | 80 | 
| 40126 | Thick King's Amber | 80 | 
| 40127 | Mystic King's Amber | 80 | 
| 40128 | Quick King's Amber | 80 | 
| 40129 | Sovereign Dreadstone | 80 | 
| 40130 | Shifting Dreadstone | 80 | 
| 40131 | Tenuous Dreadstone | 80 | 
| 40132 | Glowing Dreadstone | 80 | 
| 40133 | Purified Dreadstone | 80 | 
| 40134 | Royal Dreadstone | 80 | 
| 40135 | Mysterious Dreadstone | 80 | 
| 40136 | Balanced Dreadstone | 80 | 
| 40137 | Infused Dreadstone | 80 | 
| 40138 | Regal Dreadstone | 80 | 
| 40139 | Defender's Dreadstone | 80 | 
| 40140 | Puissant Dreadstone | 80 | 
| 40141 | Guardian's Dreadstone | 80 | 
| 40142 | Inscribed Ametrine | 80 | 
| 40143 | Etched Ametrine | 80 | 
| 40144 | Champion's Ametrine | 80 | 
| 40145 | Resplendent Ametrine | 80 | 
| 40146 | Fierce Ametrine | 80 | 
| 40147 | Deadly Ametrine | 80 | 
| 40148 | Glinting Ametrine | 80 | 
| 40149 | Lucent Ametrine | 80 | 
| 40150 | Deft Ametrine | 80 | 
| 40151 | Luminous Ametrine | 80 | 
| 40152 | Potent Ametrine | 80 | 
| 40153 | Veiled Ametrine | 80 | 
| 40154 | Durable Ametrine | 80 | 
| 40155 | Reckless Ametrine | 80 | 
| 40156 | Wicked Ametrine | 80 | 
| 40157 | Pristine Ametrine | 80 | 
| 40158 | Empowered Ametrine | 80 | 
| 40159 | Stark Ametrine | 80 | 
| 40160 | Stalwart Ametrine | 80 | 
| 40161 | Glimmering Ametrine | 80 | 
| 40162 | Accurate Ametrine | 80 | 
| 40163 | Resolute Ametrine | 80 | 
| 40164 | Timeless Eye of Zul | 80 | 
| 40165 | Jagged Eye of Zul | 80 | 
| 40166 | Vivid Eye of Zul | 80 | 
| 40167 | Enduring Eye of Zul | 80 | 
| 40168 | Steady Eye of Zul | 80 | 
| 40169 | Forceful Eye of Zul | 80 | 
| 40170 | Seer's Eye of Zul | 80 | 
| 40171 | Misty Eye of Zul | 80 | 
| 40172 | Shining Eye of Zul | 80 | 
| 40173 | Turbid Eye of Zul | 80 | 
| 40174 | Intricate Eye of Zul | 80 | 
| 40175 | Dazzling Eye of Zul | 80 | 
| 40176 | Sundered Eye of Zul | 80 | 
| 40177 | Lambent Eye of Zul | 80 | 
| 40178 | Opaque Eye of Zul | 80 | 
| 40179 | Energized Eye of Zul | 80 | 
| 40180 | Radiant Eye of Zul | 80 | 
| 40181 | Tense Eye of Zul | 80 | 
| 40182 | Shattered Eye of Zul | 80 | 
| 40232 | Test Dazzling Talasite | 70 | 
| 41266 | Skyflare Diamond | 80 | 
| 41285 | Chaotic Skyflare Diamond | 80 | 
| 41307 | Destructive Skyflare Diamond | 80 | 
| 41333 | Ember Skyflare Diamond | 80 | 
| 41334 | Earthsiege Diamond | 80 | 
| 41335 | Enigmatic Skyflare Diamond | 80 | 
| 41339 | Swift Skyflare Diamond | 80 | 
| 41375 | Tireless Skyflare Diamond | 80 | 
| 41376 | Revitalizing Skyflare Diamond | 80 | 
| 41377 | Effulgent Skyflare Diamond | 80 | 
| 41378 | Forlorn Skyflare Diamond | 80 | 
| 41379 | Impassive Skyflare Diamond | 80 | 
| 41380 | Austere Earthsiege Diamond | 80 | 
| 41381 | Persistent Earthsiege Diamond | 80 | 
| 41382 | Trenchant Earthsiege Diamond | 80 | 
| 41385 | Invigorating Earthsiege Diamond | 80 | 
| 41389 | Beaming Earthsiege Diamond | 80 | 
| 41395 | Bracing Earthsiege Diamond | 80 | 
| 41396 | Eternal Earthsiege Diamond | 80 | 
| 41397 | Powerful Earthsiege Diamond | 80 | 
| 41398 | Relentless Earthsiege Diamond | 80 | 
| 41400 | Thundering Skyflare Diamond | 80 | 
| 41401 | Insightful Earthsiege Diamond | 80 | 
| 41429 | Perfect Wicked Huge Citrine | 70 | 
| 41432 | Perfect Bold Bloodstone | 70 | 
| 41433 | Perfect Bright Bloodstone | 70 | 
| 41434 | Perfect Delicate Bloodstone | 70 | 
| 41435 | Perfect Flashing Bloodstone | 70 | 
| 41436 | Perfect Fractured Bloodstone | 70 | 
| 41437 | Perfect Precise Bloodstone | 70 | 
| 41438 | Perfect Runed Bloodstone | 70 | 
| 41439 | Perfect Subtle Bloodstone | 70 | 
| 41440 | Perfect Lustrous Chalcedony | 70 | 
| 41441 | Perfect Solid Chalcedony | 70 | 
| 41442 | Perfect Sparkling Chalcedony | 70 | 
| 41443 | Perfect Stormy Chalcedony | 70 | 
| 41444 | Perfect Brilliant Sun Crystal | 70 | 
| 41445 | Perfect Mystic Sun Crystal | 70 | 
| 41446 | Perfect Quick Sun Crystal | 70 | 
| 41447 | Perfect Rigid Sun Crystal | 70 | 
| 41448 | Perfect Smooth Sun Crystal | 70 | 
| 41449 | Perfect Thick Sun Crystal | 70 | 
| 41450 | Perfect Balanced Shadow Crystal | 70 | 
| 41451 | Perfect Defender's Shadow Crystal | 70 | 
| 41452 | Perfect Glowing Shadow Crystal | 70 | 
| 41453 | Perfect Guardian's Shadow Crystal | 70 | 
| 41454 | Perfect Infused Shadow Crystal | 70 | 
| 41455 | Perfect Mysterious Shadow Crystal | 70 | 
| 41456 | Perfect Puissant Shadow Crystal | 70 | 
| 41457 | Perfect Purified Shadow Crystal | 70 | 
| 41458 | Perfect Regal Shadow Crystal | 70 | 
| 41459 | Perfect Royal Shadow Crystal | 70 | 
| 41460 | Perfect Shifting Shadow Crystal | 70 | 
| 41461 | Perfect Sovereign Shadow Crystal | 70 | 
| 41462 | Perfect Tenuous Shadow Crystal | 70 | 
| 41463 | Perfect Dazzling Dark Jade | 70 | 
| 41464 | Perfect Enduring Dark Jade | 70 | 
| 41465 | Perfect Energized Dark Jade | 70 | 
| 41466 | Perfect Forceful Dark Jade | 70 | 
| 41467 | Perfect Intricate Dark Jade | 70 | 
| 41468 | Perfect Jagged Dark Jade | 70 | 
| 41469 | Perfect Lambent Dark Jade | 70 | 
| 41470 | Perfect Misty Dark Jade | 70 | 
| 41471 | Perfect Opaque Dark Jade | 70 | 
| 41472 | Perfect Radiant Dark Jade | 70 | 
| 41473 | Perfect Seer's Dark Jade | 70 | 
| 41474 | Perfect Shattered Dark Jade | 70 | 
| 41475 | Perfect Shining Dark Jade | 70 | 
| 41476 | Perfect Steady Dark Jade | 70 | 
| 41477 | Perfect Sundered Dark Jade | 70 | 
| 41478 | Perfect Tense Dark Jade | 70 | 
| 41479 | Perfect Timeless Dark Jade | 70 | 
| 41480 | Perfect Turbid Dark Jade | 70 | 
| 41481 | Perfect Vivid Dark Jade | 70 | 
| 41482 | Perfect Accurate Huge Citrine | 70 | 
| 41483 | Perfect Champion's Huge Citrine | 70 | 
| 41484 | Perfect Deadly Huge Citrine | 70 | 
| 41485 | Perfect Deft Huge Citrine | 70 | 
| 41486 | Perfect Durable Huge Citrine | 70 | 
| 41487 | Perfect Empowered Huge Citrine | 70 | 
| 41488 | Perfect Etched Huge Citrine | 70 | 
| 41489 | Perfect Fierce Huge Citrine | 70 | 
| 41490 | Perfect Glimmering Huge Citrine | 70 | 
| 41491 | Perfect Glinting Huge Citrine | 70 | 
| 41492 | Perfect Inscribed Huge Citrine | 70 | 
| 41493 | Perfect Lucent Huge Citrine | 70 | 
| 41494 | Perfect Luminous Huge Citrine | 70 | 
| 41495 | Perfect Potent Huge Citrine | 70 | 
| 41496 | Perfect Pristine Huge Citrine | 70 | 
| 41497 | Perfect Reckless Huge Citrine | 70 | 
| 41498 | Perfect Resolute Huge Citrine | 70 | 
| 41499 | Perfect Resplendent Huge Citrine | 70 | 
| 41500 | Perfect Stalwart Huge Citrine | 70 | 
| 41501 | Perfect Stark Huge Citrine | 70 | 
| 41502 | Perfect Veiled Huge Citrine | 70 | 
| 42142 | Bold Dragon's Eye | 80 | 
| 42143 | Delicate Dragon's Eye | 80 | 
| 42144 | Runed Dragon's Eye | 80 | 
| 42145 | Sparkling Dragon's Eye | 80 | 
| 42146 | Lustrous Dragon's Eye | 80 | 
| 42148 | Brilliant Dragon's Eye | 80 | 
| 42149 | Smooth Dragon's Eye | 80 | 
| 42150 | Quick Dragon's Eye | 80 | 
| 42151 | Subtle Dragon's Eye | 80 | 
| 42152 | Flashing Dragon's Eye | 80 | 
| 42153 | Fractured Dragon's Eye | 80 | 
| 42154 | Precise Dragon's Eye | 80 | 
| 42155 | Stormy Dragon's Eye | 80 | 
| 42156 | Rigid Dragon's Eye | 80 | 
| 42157 | Thick Dragon's Eye | 80 | 
| 42158 | Mystic Dragon's Eye | 80 | 
| 42225 | Dragon's Eye | 80 | 
| 42701 | Enchanted Pearl | 70 | 
| 42702 | Enchanted Tear | 80 | 
| 44066 | Kharmaa's Grace | 80 | 
| 44076 | Swift Starflare Diamond | 80 | 
| 44078 | Tireless Starflare Diamond | 80 | 
| 44081 | Enigmatic Starflare Diamond | 80 | 
| 44082 | Impassive Starflare Diamond | 80 | 
| 44084 | Forlorn Starflare Diamond | 80 | 
| 44087 | Persistent Earthshatter Diamond | 80 | 
| 44088 | Powerful Earthshatter Diamond | 80 | 
| 44089 | Trenchant Earthshatter Diamond | 80 | 
| 45054 | Prismatic Black Diamond | 60 | 
| 45862 | Bold Stormjewel | 80 | 
| 45879 | Delicate Stormjewel | 80 | 
| 45880 | Solid Stormjewel | 80 | 
| 45881 | Sparkling Stormjewel | 80 | 
| 45882 | Brilliant Stormjewel | 80 | 
| 45883 | Runed Stormjewel | 80 | 
| 45987 | Rigid Stormjewel | 80 | 
| 49110 | Nightmare Tear | 80 | 

</details>

21929, 22459, 22460, 23077, 23079, 23094, 23095, 23096, 23097, 23098, 23099, 23100, 23101, 23103, 23104, 23105, 23106, 23107, 23108, 23109, 23110, 23111, 23112, 23113, 23114, 23115, 23116, 23117, 23118, 23119, 23120, 23121, 23436, 23437, 23438, 23439, 23440, 23441, 24027, 24028, 24029, 24030, 24031, 24032, 24033, 24035, 24036, 24037, 24039, 24047, 24048, 24050, 24051, 24052, 24053, 24054, 24055, 24056, 24057, 24058, 24059, 24060, 24061, 24062, 24065, 24066, 24067, 25867, 25868, 25890, 25893, 25894, 25895, 25896, 25897, 25898, 25899, 25901, 27679, 27777, 27785, 27786, 27809, 27812, 27820, 28118, 28119, 28120, 28123, 28290, 28360, 28361, 28362, 28363, 28458, 28459, 28460, 28461, 28462, 28463, 28464, 28465, 28466, 28467, 28468, 28469, 28470, 28556, 28557, 28595, 30546, 30547, 30548, 30549, 30550, 30551, 30552, 30553, 30554, 30555, 30556, 30558, 30559, 30560, 30563, 30564, 30565, 30566, 30571, 30572, 30573, 30574, 30575, 30581, 30582, 30583, 30584, 30585, 30586, 30587, 30588, 30589, 30590, 30591, 30592, 30593, 30594, 30598, 30600, 30601, 30602, 30603, 30604, 30605, 30606, 30607, 30608, 31116, 31117, 31118, 31860, 31861, 31862, 31863, 31864, 31865, 31866, 31867, 31868, 31869, 32193, 32194, 32195, 32196, 32197, 32198, 32199, 32200, 32201, 32202, 32203, 32204, 32205, 32206, 32207, 32208, 32209, 32210, 32211, 32212, 32213, 32214, 32215, 32216, 32217, 32218, 32219, 32220, 32221, 32222, 32223, 32224, 32225, 32226, 32227, 32228, 32229, 32230, 32231, 32249, 32409, 32410, 32634, 32635, 32636, 32637, 32638, 32639, 32640, 32641, 32735, 32833, 32836, 33060, 33131, 33132, 33133, 33134, 33135, 33137, 33138, 33139, 33140, 33141, 33142, 33143, 33144, 33782, 34142, 34143, 34220, 34256, 34627, 34831, 34967, 35315, 35316, 35318, 35487, 35488, 35489, 35501, 35503, 35707, 35758, 35759, 35760, 35761, 36766, 36767, 36783, 36784, 36917, 36918, 36919, 36920, 36921, 36922, 36923, 36924, 36925, 36926, 36927, 36928, 36929, 36930, 36931, 36932, 36933, 36934, 37430, 37503, 38292, 38538, 38545, 38546, 38547, 38548, 38549, 38550, 39900, 39905, 39906, 39907, 39908, 39909, 39910, 39911, 39912, 39914, 39915, 39916, 39917, 39918, 39919, 39920, 39927, 39932, 39933, 39934, 39935, 39936, 39937, 39938, 39939, 39940, 39941, 39942, 39943, 39944, 39945, 39946, 39947, 39948, 39949, 39950, 39951, 39952, 39953, 39954, 39955, 39956, 39957, 39958, 39959, 39960, 39961, 39962, 39963, 39964, 39965, 39966, 39967, 39968, 39974, 39975, 39976, 39977, 39978, 39979, 39980, 39981, 39982, 39983, 39984, 39985, 39986, 39988, 39989, 39990, 39991, 39992, 39996, 39997, 39998, 39999, 40000, 40001, 40002, 40003, 40008, 40009, 40010, 40011, 40012, 40013, 40014, 40015, 40016, 40017, 40022, 40023, 40024, 40025, 40026, 40027, 40028, 40029, 40030, 40031, 40032, 40033, 40034, 40037, 40038, 40039, 40040, 40041, 40043, 40044, 40045, 40046, 40047, 40048, 40049, 40050, 40051, 40052, 40053, 40054, 40055, 40056, 40057, 40058, 40059, 40085, 40086, 40088, 40089, 40090, 40091, 40092, 40094, 40095, 40096, 40098, 40099, 40100, 40101, 40102, 40103, 40104, 40105, 40106, 40111, 40112, 40113, 40114, 40115, 40116, 40117, 40118, 40119, 40120, 40121, 40122, 40123, 40124, 40125, 40126, 40127, 40128, 40129, 40130, 40131, 40132, 40133, 40134, 40135, 40136, 40137, 40138, 40139, 40140, 40141, 40142, 40143, 40144, 40145, 40146, 40147, 40148, 40149, 40150, 40151, 40152, 40153, 40154, 40155, 40156, 40157, 40158, 40159, 40160, 40161, 40162, 40163, 40164, 40165, 40166, 40167, 40168, 40169, 40170, 40171, 40172, 40173, 40174, 40175, 40176, 40177, 40178, 40179, 40180, 40181, 40182, 40232, 41266, 41285, 41307, 41333, 41334, 41335, 41339, 41375, 41376, 41377, 41378, 41379, 41380, 41381, 41382, 41385, 41389, 41395, 41396, 41397, 41398, 41400, 41401, 41429, 41432, 41433, 41434, 41435, 41436, 41437, 41438, 41439, 41440, 41441, 41442, 41443, 41444, 41445, 41446, 41447, 41448, 41449, 41450, 41451, 41452, 41453, 41454, 41455, 41456, 41457, 41458, 41459, 41460, 41461, 41462, 41463, 41464, 41465, 41466, 41467, 41468, 41469, 41470, 41471, 41472, 41473, 41474, 41475, 41476, 41477, 41478, 41479, 41480, 41481, 41482, 41483, 41484, 41485, 41486, 41487, 41488, 41489, 41490, 41491, 41492, 41493, 41494, 41495, 41496, 41497, 41498, 41499, 41500, 41501, 41502, 42142, 42143, 42144, 42145, 42146, 42148, 42149, 42150, 42151, 42152, 42153, 42154, 42155, 42156, 42157, 42158, 42225, 42701, 42702, 44066, 44076, 44078, 44081, 44082, 44084, 44087, 44088, 44089, 45054, 45862, 45879, 45880, 45881, 45882, 45883, 45987, 49110
