# Diablo 3 Web API

This is the documentation for the Diablo 3 API resources that are a part of the Blizzard Community Platform API. ***The Diablo 3 API resources are not publicly available***, but we are providing this documentation to prepare developers and fan sites as best we can for its release.

## Overview

The Blizzard Community Platform API provides a number of resources for developers and Diablo 3 enthusiasts to gather data about their accounts and heroes. This documentation is primarily for developers and third parties.

Blizzard's epic gaming experiences often take place in game, but can lead to rewarding and lasting experiences out of game as well. Through exposing key sets of data, we can enable the community to create extended communities to continue that epic experience.

## Career Profile

The Career Profile API is the primary way to access account level career profile  information. This Career Profile API can be used to fetch a single game account at a time through a HTTP GET request to a URL describing the career profile resource.

By default, a basic dataset will be returned and with each request and zero or more additional fields can be retrieved. To access this API, craft a resource URL pointing to the battletag of an account whos information is to be retrieved.

```plain
URL = Host + "/api/d3/account/" + BattletagName + "-" + BattletagNumber
```

There are no required query string parameters when accessing this resource.

*An example Career Profile API request:*

```plain
GET /api/d3/account/Straton-1
Host: us.battle.net
```

*An example Career Profile API response:*
```plain
HTTP/1.1 200 OK
<http headers>

{"heroes": [{"name": "Yharr", "id": 1, ...}, ...], ...}
```

The core dataset returned includes a list of the account's heroes and artisans, a summary of time played by class, progression information and a list of the account's fallen heroes.

### Career Profile Example

```json
{
    "id": 1,
    "name": "Yharr",
    "class": "barbarian",
    "gender": 0,
    "level": 54,
    "hardcore": false,
    "skills": {
        "active": [
            {
                "skill": {
                    "slug": "frenzy",
                    "name": "Frenzy",
                    "icon": "barbarian_frenzy",
                    "tooltipParams": "skill/barbarian/frenzy",
                    "description": "Generate: 3 Fury per attack\r\n\r\nSwing for 110% weapon damage. Frenzy attack speed increases by 15% with each swing. This effect can stack up to 5 times for a total bonus of 75% attack speed.",
                    "simpleDescription": "Generate: 3 Fury per attack\r\n\r\nEnter a frenzied state that increases your attack speed with each hit."
                },
                "rune": {
                    "slug": "frenzy-d",
                    "type": "d",
                    "name": "Smite",
                    "description": "Add a 20% chance to call down a bolt of lightning from above, stunning your target for 1.5 seconds.",
                    "simpleDescription": "Add a chance to call down a bolt of lightning that stuns your target.",
                    "tooltipParams": "rune/frenzy/d",
                    "orderIndex": 3
                }
            },
            {
                "skill": {
                    "slug": "seismic-slam",
                    "name": "Seismic Slam",
                    "icon": "barbarian_seismicslam",
                    "tooltipParams": "skill/barbarian/seismic-slam",
                    "description": "Cost: 30 Fury\r\n\r\nSlam the ground and cause a wave of destruction that deals 155% weapon damage and Knockback to targets in a 45 yard arc.",
                    "simpleDescription": "Cost: 30 Fury\r\n\r\nCreate shockwaves that damage enemies in their path."
                },
                "rune": {
                    "slug": "seismic-slam-a",
                    "type": "a",
                    "name": "Shattered Ground",
                    "description": "Increase damage to 202% weapon damage and increases Knockback distance by 100%.",
                    "simpleDescription": "Increase the damage and Knockback distance.",
                    "tooltipParams": "rune/seismic-slam/a",
                    "orderIndex": 1
                }
            },
            {
                "skill": {
                    "slug": "earthquake",
                    "name": "Earthquake",
                    "icon": "barbarian_earthquake",
                    "tooltipParams": "skill/barbarian/earthquake",
                    "description": "Cost: 50 Fury\r\nCooldown: 120 seconds\r\n\r\nShake the ground violently, dealing 2000% weapon damage as Fire over 8 seconds to all enemies within 18 yards.",
                    "simpleDescription": "Cost: 50 Fury\r\nCooldown: 120 seconds\r\n\r\nViolent tremors shake the earth and damage nearby enemies."
                },
                "rune": {
                    "slug": "earthquake-d",
                    "type": "d",
                    "name": "The Mountain's Call",
                    "description": "Removes the Fury cost and reduces the cooldown to 105 seconds.",
                    "simpleDescription": "Removes the Fury cost and reduces the cooldown of Earthquake.",
                    "tooltipParams": "rune/earthquake/d",
                    "orderIndex": 2
                }
            },
            {
                "skill": {
                    "slug": "wrath-of-the-berserker",
                    "name": "Wrath of the Berserker",
                    "icon": "barbarian_wrathoftheberserker",
                    "tooltipParams": "skill/barbarian/wrath-of-the-berserker",
                    "description": "Cost: 50 Fury \r\nCooldown: 120 seconds\r\n\r\nEnter a berserker rage which raises several attributes for 15 seconds.\r\n\r\nCritical Hit Chance: 10%\r\nAttack Speed: 25%\r\nDodge Chance: 20%\r\nMovement Speed: 20%",
                    "simpleDescription": "Cost: 50 Fury \r\nCooldown: 120 seconds\r\n\r\nBecome Fury incarnate for 15 seconds."
                },
                "rune": {
                    "slug": "wrath-of-the-berserker-a",
                    "type": "a",
                    "name": "Insanity",
                    "description": "While active your damage is also increased by 100%.",
                    "simpleDescription": "Increase your damage while Wrath of the Berserker is active.",
                    "tooltipParams": "rune/wrath-of-the-berserker/a",
                    "orderIndex": 1
                }
            },
            {
                "skill": {
                    "slug": "war-cry",
                    "name": "War Cry",
                    "icon": "barbarian_warcry",
                    "tooltipParams": "skill/barbarian/war-cry",
                    "description": "Generate: 30 Fury\r\nCooldown: 30 seconds\r\n\r\nUnleash a rallying cry to increase Armor for you and all allies within 50 yards by 20% for 60 seconds.",
                    "simpleDescription": "Generate: 30 Fury\r\nCooldown: 30 seconds\r\n\r\nA rallying cry increases Armor for you and your allies for 60 seconds."
                },
                "rune": {
                    "slug": "war-cry-e",
                    "type": "e",
                    "name": "Invigorate",
                    "description": "Increases maximum Life by 10% and regenerates 310 Life per second while affected by War Cry.",
                    "simpleDescription": "Increase your maximum Life and regenerate Life while War Cry is active.",
                    "tooltipParams": "rune/war-cry/e",
                    "orderIndex": 2
                }
            },
            {
                "skill": {
                    "slug": "ignore-pain",
                    "name": "Ignore Pain",
                    "icon": "barbarian_ignorepain",
                    "tooltipParams": "skill/barbarian/ignore-pain",
                    "description": "Cooldown: 30 seconds\r\n\r\nReduces all damage taken by 65% for 5 seconds.",
                    "simpleDescription": "Cooldown: 30 seconds\r\n\r\nYour rage protects you from most damage for a limited time."
                },
                "rune": {
                    "slug": "ignore-pain-e",
                    "type": "e",
                    "name": "Ignorance is Bliss",
                    "description": "While Ignore Pain is active, gain 20% of all damage dealt as Life.",
                    "simpleDescription": "While Ignore Pain is active, gain Life for damage dealt to enemies.",
                    "tooltipParams": "rune/ignore-pain/e",
                    "orderIndex": 2
                }
            }
        ],
        "passive": [
            {
                "slug": "ruthless",
                "name": "Ruthless",
                "icon": "barbarian_passive_ruthless",
                "tooltipParams": "skill/barbarian/ruthless",
                "description": "Critical Hit Chance increased by 5%. Critical Hit Damage increased by 50%.\r\n\r\nMany skills and runes rely on Critical Hits to trigger their effects.",
                "flavor": "The clans each paint their warriors in their own unique way. Some celebrate the mountain, others honor the fire, but the Targos clan worships the purifying virtue of pain."
            },
            {
                "slug": "weapons-master",
                "name": "Weapons Master",
                "icon": "barbarian_passive_weaponsmaster",
                "tooltipParams": "skill/barbarian/weapons-master",
                "description": "Gain a bonus based on the weapon type of your main hand weapon:\r\nSwords/Daggers: 15% increased damage\r\nMaces/Axes: 10% Critical Hit Chance\r\nPolearms/Spears: 10% attack speed\r\nMighty Weapons: 3 Fury per hit",
                "flavor": "\"My men ambushed the traveler in the woods, but it was we who were surprised. Such keen senses, swift motions, flawless strikes. We never stood a chance.\" ?Redjack the Bandit"
            },
            {
                "slug": "nerves-of-steel",
                "name": "Nerves Of Steel",
                "icon": "barbarian_passive_nervesofsteel",
                "tooltipParams": "skill/barbarian/nerves-of-steel",
                "description": "Your Armor is increased by 100% of your Vitality.",
                "flavor": "\"The trials begin with childhood; skinning ferocious beasts, climbing windswept cliffs and carrying weapons heavy enough to make a southern soldier weep. Is it any wonder that they never give ground?\" ?Sir Aric of Duncraig"
            }
        ]
    },
    "items": {
        "head": {
            "name": "Wild Casque of Invasion",
            "icon": "helm_104",
            "displayColor": "blue",
            "tooltipParams": "item-data/CPvK9pADEgcIBBU69U5dHTIL5KIdAn-SATAJOPUDQABIFVAIYPUD"
        },
        "torso": {
            "name": "Covenant Invasion",
            "icon": "chestarmor_105",
            "displayColor": "yellow",
            "tooltipParams": "item-data/CJrCw64IEgcIBBXtHRlgHQJ_kgEd6SuJOh3Y7Sq9HZMCY-oiCwgBFWdCAwAYDiAUMAk4qAVAAEgNUAxgqAVqJQoMCAAQ8--hp4CAgOAwEhUIqNWDxQMSBwgEFfSe2KswCTgAQAFqJQoMCAAQifChp4CAgOAwEhUIvbPojwkSBwgEFfSe2KswCTgAQAFqJQoMCAAQp_Chp4CAgOAwEhUI17rWjQwSBwgEFfSe2KswCTgAQAE"
        },
        "feet": {
            "name": "Relentless Battle Greaves of Invasion",
            "icon": "boots_105",
            "displayColor": "blue",
            "tooltipParams": "item-data/CILd8t4NEgcIBBVcQZt_HdM9BzUdQzTvhjAJOIYEQABIDVAIYIYE"
        },
        "hands": {
            "name": "Cruel Gage",
            "icon": "gloves_103",
            "displayColor": "yellow",
            "tooltipParams": "item-data/CMzrzgESBwgEFYNXkqQd9ORSKh3gzHZQHRCRU2gdvdK3LR0Cf5IBIgsIABW6RAMAGBogGDAJONgDQABIDVAOYNgD"
        },
        "shoulders": {
            "name": "Champion Reprisal",
            "icon": "shoulders_104",
            "displayColor": "yellow",
            "tooltipParams": "item-data/CIuLmwMSBwgEFY30yBUd0cIitx0axFF0HeE5hwIdvlvoSCILCAEVu0QDABgUICYwCTiDBUAASBJQDGCDBQ"
        },
        "legs": {
            "name": "Battle Cinder",
            "icon": "pants_102",
            "displayColor": "yellow",
            "tooltipParams": "item-data/CI-_yboGEgcIBBVYjtWlHbyNjMMdidXDnR25MEgIHQvRkggdGE28Kh2UvzSKIgsIARV1QgMAGAIgGDAJOLEEQABIDVAQYLEEaiUKDAgAEOaWgIuAgICAEBIVCIaN74UDEgcIBBVG9YtfMAk4AEAB"
        },
        "bracers": {
            "name": "Protection Mettle",
            "icon": "bracers_103",
            "displayColor": "yellow",
            "tooltipParams": "item-data/CIW466IFEgcIBBWVKMrLHQJ_kgEdD9xxfB2crKCYHRKHPlYdSFJ1-h1DYFFAIgsIARVvQgMAGAQgADAJOOEDQABQEGDhAw"
        },
        "mainHand": {
            "name": "Destruction Wisp",
            "icon": "sword_2h_201",
            "displayColor": "yellow",
            "tooltipParams": "item-data/CMGq1KMEEgcIBBX6_S7yHZtssxQdS2NPMB2o7995HWPY6agiCwgBFXdCAwAYACAUMAk4hQRAAFAMYIUE"
        },
        "offHand": null,
        "waist": {
            "name": "Scale Envy",
            "icon": "belt_105",
            "displayColor": "yellow",
            "tooltipParams": "item-data/CMXv_fcHEgcIBBV8o0LUHUoyxxwd3WH9HR0fhz5WHUM074YiCwgBFXVCAwAYDiASMAk4wQNAAFAMYMED"
        },
        "rightFinger": {
            "name": "Empty Band",
            "icon": "ring_09",
            "displayColor": "yellow",
            "tooltipParams": "item-data/CMn4h5MJEgcIBBX4VF1EHRhNvCodulvoSB2FvzSKHUDxmysiCwgAFcv-AQAYDCAGMAk47QJAAFAMYO0CaiUKDAgAELTa1JqAgIDgIBIVCJvB4cEOEgcIBBVF9YtfMAk4AEAB"
        },
        "leftFinger": {
            "name": "Gambler's Loop",
            "icon": "ring_10",
            "displayColor": "yellow",
            "tooltipParams": "item-data/CNT-vN0DEgcIBBUQVV1EHYutUmgdRH0C5R0-vYo1HRjTLBAdjrDM0B0WpNPYIgsIABW2_gEAGCQgCDAJOKwDQABQEGCsA2okCgwIABCk2tSagICA4CASFAjysbA9EgcIBBVF9YtfMAk4AEAB"
        },
        "neck": {
            "name": "Nobility Aim",
            "icon": "amulet07",
            "displayColor": "yellow",
            "tooltipParams": "item-data/COCVqNAHEgcIBBWPxURkHSUlWp4dO7LM0B29_O7IHTKHYggiCwgBFcZEAwAYGiAkMAk4kANAAFAMYJADaiUKDAgAEKimv5GAgICgAxIVCOfkurINEgcIBBVG9YtfMAk4AEAB"
        }
    },
    "followers": {
        "templar": {
            "slug": "templar",
            "level": 47,
            "items": {
                "mainHand": {
                    "name": "Slice Favor",
                    "icon": "dagger_105",
                    "displayColor": "yellow",
                    "tooltipParams": "item-data/COTwoI4GEgcIBBU_ek-yHdaqHqYdCCTSvx2OsMzQHWGvmYwiCwgBFcBEAwAYJCAQMAk49gNAAFAMYPYD"
                },
                "offHand": {
                    "name": "Socketed Ironwood Shield of the Lion",
                    "icon": "shield_104",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CPqUoIcLEgcIBBXNBztsHYYCY-odVS2mmjAJONgEQABQCGDYBA"
                },
                "rightFinger": {
                    "name": "Socketed Ring",
                    "icon": "ring_11",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CIHsvdQHEgcIBBURVV1EHTuyzNAwCTilBEAAUAZgpQQ"
                },
                "leftFinger": {
                    "name": "Ring of Focus",
                    "icon": "ring_11",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CLTkz_ELEgcIBBURVV1EHYkH0n8wCTjcA0AAUAZg3AM"
                },
                "neck": {
                    "name": "Amulet of the Hawk",
                    "icon": "amulet04",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CI_H2LkPEgcIBBWMxURkHXT3SgcwCTjTA0AAUAZg0wM"
                },
                "special": {
                    "name": "Devotion Defiance",
                    "icon": "templar_special_001",
                    "displayColor": "yellow",
                    "tooltipParams": "item-data/CIGQjbsGEgcIBBVlA2NEHV1QqgcdpL9pwB2YkYQeHeQriToiCwgBFYVCAwAYACAMMAk4AEAAUAw"
                }
            },
            "skills": [
                {
                    "slug": "heal",
                    "name": "Heal",
                    "icon": "templar_heal",
                    "tooltipParams": "skill/templar/heal",
                    "description": "Heals you or the Templar for 4651 Life.\r\n\r\nCooldown: 30 seconds",
                    "simpleDescription": "Heals you or the Templar."
                },
                {
                    "slug": "loyalty",
                    "name": "Loyalty",
                    "icon": "templar_loyalty",
                    "tooltipParams": "skill/templar/loyalty",
                    "description": "Regenerates 155 Life per second for you and the Templar.",
                    "simpleDescription": "Provides Life regeneration for you and the Templar."
                },
                {
                    "slug": "charge",
                    "name": "Charge",
                    "icon": "templar_shieldcharge",
                    "tooltipParams": "skill/templar/charge",
                    "description": "Charges a target, dealing 50% weapon damage and stunning all enemies within 8 yards for 2 seconds.\r\n\r\nCooldown: 30 seconds",
                    "simpleDescription": "Charges an enemy, dealing damage and stunning the target."
                },
                {
                    "slug": "guardian",
                    "name": "Guardian",
                    "icon": "templar_guardian",
                    "tooltipParams": "skill/templar/guardian",
                    "description": "Rush to the aid of wounded ally, knocking back enemies within 15 yards and healing the wounded ally for 4651 Life.\r\n\r\nCooldown: 30 seconds",
                    "simpleDescription": "When hero Life is low, the Templar will come to your aid, knocking back nearby enemies and healing you."
                }
            ]
        },
        "scoundrel": {
            "slug": "scoundrel",
            "level": 51,
            "items": {
                "mainHand": {
                    "name": "Outcast Shrike",
                    "icon": "crossbow_105",
                    "displayColor": "yellow",
                    "tooltipParams": "item-data/CJ--6v8OEgcIBBXHV8oKHaAjvEgdZFCqBx07sszQHdqQjBQiCwgAFcv-AQAYFiAIMAk4kQRAAFAMYJEE"
                },
                "offHand": null,
                "rightFinger": {
                    "name": "Keen Ring",
                    "icon": "ring_05",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CMvwx6MFEgcIBBX0VF1EHe9xwNAwCTi_A0AAUAZgvwM"
                },
                "leftFinger": {
                    "name": "Scouting Ring of the Lion",
                    "icon": "ring_04",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/COmIkpQCEgcIBBXzVF1EHc2PnK4dFHhJFTAJOMUDQABQCGDFAw"
                },
                "neck": {
                    "name": "Scouting Amulet of Wounding",
                    "icon": "amulet02",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CIf0ie4BEgcIBBWKxURkHZZocwUdvHs9ADAJOPsDQABQCGD7Aw"
                },
                "special": {
                    "name": "Disciple's Poise",
                    "icon": "scoundrel_special_102",
                    "displayColor": "yellow",
                    "tooltipParams": "item-data/CK7y3O8JEgcIBBVh_UvyHXb3SgcdJSVanh2akYQeHWRQqgciCwgBFXFCAwAYGCAaMAk4AEAAUAw"
                }
            },
            "skills": [
                {
                    "slug": "crippling-shot",
                    "name": "Crippling Shot",
                    "icon": "scoundrel_cripplingshot",
                    "tooltipParams": "skill/scoundrel/crippling-shot",
                    "description": "Ranged attack that slows the target by 60% for 3 seconds.\r\n\r\nCooldown: 6 seconds",
                    "simpleDescription": "Deals damage and slows the target."
                },
                {
                    "slug": "dirty-fighting",
                    "name": "Dirty Fighting",
                    "icon": "scoundrel_dirtyfighting",
                    "tooltipParams": "skill/scoundrel/dirty-fighting",
                    "description": "Blinds enemies in front of the Scoundrel for 3 seconds.\r\n\r\nCooldown: 30 seconds",
                    "simpleDescription": "Blinds nearby enemies."
                },
                {
                    "slug": "powered-shot",
                    "name": "Powered Shot",
                    "icon": "scoundrel_powershot",
                    "tooltipParams": "skill/scoundrel/powered-shot",
                    "description": "Powerful ranged attack that explodes on impact, dealing 25% weapon damage as Arcane to targets within 6 yards and has a 50% chance to Stun targets for 2 seconds.\r\n\r\nCooldown: 20 seconds",
                    "simpleDescription": "Deals massive damage in an area and knocks back enemies."
                },
                {
                    "slug": "anatomy",
                    "name": "Anatomy",
                    "icon": "scoundrel_anatomy",
                    "tooltipParams": "skill/scoundrel/anatomy",
                    "description": "Increases Critical Hit Chance by 3% for the Scoundrel and his allies.",
                    "simpleDescription": "Increases the Critical Hit Chance of the Scoundrel and his allies."
                }
            ]
        },
        "enchantress": {
            "slug": "enchantress",
            "level": 53,
            "items": {
                "mainHand": {
                    "name": "Skywarden",
                    "icon": "unique_mace_2h_010",
                    "displayColor": "orange",
                    "tooltipParams": "item-data/CPjT4eQLEgcIBBX1otksHZuwzNAdPoRWVB2xIBV7HTeqe1AdSmNPMDAJOLwDQABQEmC8Aw"
                },
                "offHand": null,
                "rightFinger": {
                    "name": "Invigorating Ring",
                    "icon": "ring_17",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CJfa5qkPEgcIBBUXVV1EHb5b6EgwCTjzAkAAUAZg8wI"
                },
                "leftFinger": {
                    "name": "Proud Ring",
                    "icon": "ring_09",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CJnK6b0KEgcIBBX4VF1EHQ_ccXwwCTjFA0AAUAZgxQM"
                },
                "neck": {
                    "name": "Clever Amulet of Mutilation",
                    "icon": "amulet06",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CKTpw-YKEgcIBBWOxURkHQJEX6Adx5dAYDAJOOwDQABQCGDsAw"
                },
                "special": {
                    "name": "Steadfast Root of Mutilation",
                    "icon": "enchantress_special_104",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CMWEkoMLEgcIBBXynmItHQVEX6AdInwGyDAJOABAAFAI"
                }
            },
            "skills": [
                {
                    "slug": "forceful-push",
                    "name": "Forceful Push",
                    "icon": "enchantress_forcefulpush",
                    "tooltipParams": "skill/enchantress/forceful-push",
                    "description": "Summon an Arcane explosion 8 yards around an enemy, dealing 100% weapon damage as Arcane and knocking back all monsters caught within it.\r\n\r\nCooldown: 10 seconds",
                    "simpleDescription": "Creates an explosion that deals massive damage and knocks back enemies."
                },
                {
                    "slug": "powered-armor",
                    "name": "Powered Armor",
                    "icon": "enchantress_poweredarmor",
                    "tooltipParams": "skill/enchantress/powered-armor",
                    "description": "Enchantress buffs herself and her allies, increasing Armor by 15%. Attackers are slowed by 30% for 3 seconds.",
                    "simpleDescription": "Increases the armor of the Enchantress and her allies, and slows attacking enemies."
                },
                {
                    "slug": "erosion",
                    "name": "Erosion",
                    "icon": "enchantress_scorchedearth",
                    "tooltipParams": "skill/enchantress/erosion",
                    "description": "Conjures a pool of energy that deals 50% weapon damage as Arcane  per second. Affected enemies take an extra 15% damage from all attacks for 3 seconds.\r\n\r\nCooldown: 15 seconds",
                    "simpleDescription": "Blasts a target area, causing enemies to take damage over time."
                },
                {
                    "slug": "focused-mind",
                    "name": "Focused Mind",
                    "icon": "enchantress_focusedmind",
                    "tooltipParams": "skill/enchantress/focused-mind",
                    "description": "An aura that increases attack speed by 3% for allies within 40 yards.",
                    "simpleDescription": "Increases the attack speed of the Enchantress and her allies."
                }
            ]
        }
    },
    "stats": {
        "damageIncrease": 10.06,
        "damageReduction": 0.52,
        "critChance": 0.10,
        "life": 17285,
        "strength": 1007,
        "dexterity": 295,
        "intelligence": 156,
        "vitality": 570,
        "armor": 2934,
        "coldResist": 0,
        "fireResist": 0,
        "lightningResist": 0,
        "poisonResist": 0,
        "arcaneResist": 0,
        "damage": 4763.17
    },
    "progress": {
        "normal": {
            "act1": {
                "completed": true,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-fallen-star",
                            "name": "The Fallen Star"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-legacy-of-cain",
                            "name": "The Legacy of Cain"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "a-shattered-crown",
                            "name": "A Shattered Crown"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "reign-of-the-black-king",
                            "name": "Reign of the Black King"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "sword-of-the-stranger",
                            "name": "Sword of the Stranger"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-broken-blade",
                            "name": "The Broken Blade"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-doom-in-wortham",
                            "name": "The Doom in Wortham"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "trailing-the-coven",
                            "name": "Trailing the Coven"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-imprisoned-angel",
                            "name": "The Imprisoned Angel"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "return-to-new-tristram",
                            "name": "Return to New Tristram"
                        }
                    }
                ]
            },
            "act2": {
                "completed": true,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "shadows-in-the-desert",
                            "name": "Shadows in the Desert"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-road-to-alcarnus",
                            "name": "The Road to Alcarnus"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "city-of-blood",
                            "name": "City of Blood"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "a-royal-audience",
                            "name": "A Royal Audience"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "unexpected-allies",
                            "name": "Unexpected Allies"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "betrayer-of-the-horadrim",
                            "name": "Betrayer of the Horadrim"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "blood-and-sand",
                            "name": "Blood and Sand"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-black-soulstone",
                            "name": "The Black Soulstone"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-scouring-of-caldeum",
                            "name": "The Scouring of Caldeum"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "lord-of-lies",
                            "name": "Lord of Lies"
                        }
                    }
                ]
            },
            "act3": {
                "completed": true,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-siege-of-bastions-keep",
                            "name": "The Siege of Bastion's Keep"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "turning-the-tide",
                            "name": "Turning the Tide"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-breached-keep",
                            "name": "The Breached Keep"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "tremors-in-the-stone",
                            "name": "Tremors in the Stone"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "machines-of-war",
                            "name": "Machines of War"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "siegebreaker",
                            "name": "Siegebreaker"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "heart-of-sin",
                            "name": "Heart of Sin"
                        }
                    }
                ]
            },
            "act4": {
                "completed": true,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "fall-of-the-high-heavens",
                            "name": "Fall of the High Heavens"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-light-of-hope",
                            "name": "The Light of Hope"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "beneath-the-spire",
                            "name": "Beneath the Spire"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "prime-evil",
                            "name": "Prime Evil"
                        }
                    }
                ]
            }
        },
        "nightmare": {
            "act1": {
                "completed": true,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-fallen-star",
                            "name": "The Fallen Star"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-legacy-of-cain",
                            "name": "The Legacy of Cain"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "a-shattered-crown",
                            "name": "A Shattered Crown"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "reign-of-the-black-king",
                            "name": "Reign of the Black King"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "sword-of-the-stranger",
                            "name": "Sword of the Stranger"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-broken-blade",
                            "name": "The Broken Blade"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-doom-in-wortham",
                            "name": "The Doom in Wortham"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "trailing-the-coven",
                            "name": "Trailing the Coven"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-imprisoned-angel",
                            "name": "The Imprisoned Angel"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "return-to-new-tristram",
                            "name": "Return to New Tristram"
                        }
                    }
                ]
            },
            "act2": {
                "completed": true,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "shadows-in-the-desert",
                            "name": "Shadows in the Desert"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-road-to-alcarnus",
                            "name": "The Road to Alcarnus"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "city-of-blood",
                            "name": "City of Blood"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "a-royal-audience",
                            "name": "A Royal Audience"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "unexpected-allies",
                            "name": "Unexpected Allies"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "betrayer-of-the-horadrim",
                            "name": "Betrayer of the Horadrim"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "blood-and-sand",
                            "name": "Blood and Sand"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-black-soulstone",
                            "name": "The Black Soulstone"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-scouring-of-caldeum",
                            "name": "The Scouring of Caldeum"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "lord-of-lies",
                            "name": "Lord of Lies"
                        }
                    }
                ]
            },
            "act3": {
                "completed": true,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-siege-of-bastions-keep",
                            "name": "The Siege of Bastion's Keep"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "turning-the-tide",
                            "name": "Turning the Tide"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-breached-keep",
                            "name": "The Breached Keep"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "tremors-in-the-stone",
                            "name": "Tremors in the Stone"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "machines-of-war",
                            "name": "Machines of War"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "siegebreaker",
                            "name": "Siegebreaker"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "heart-of-sin",
                            "name": "Heart of Sin"
                        }
                    }
                ]
            },
            "act4": {
                "completed": true,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "fall-of-the-high-heavens",
                            "name": "Fall of the High Heavens"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-light-of-hope",
                            "name": "The Light of Hope"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "beneath-the-spire",
                            "name": "Beneath the Spire"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "prime-evil",
                            "name": "Prime Evil"
                        }
                    }
                ]
            }
        },
        "hell": {
            "act1": {
                "completed": true,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-fallen-star",
                            "name": "The Fallen Star"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-legacy-of-cain",
                            "name": "The Legacy of Cain"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "a-shattered-crown",
                            "name": "A Shattered Crown"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "reign-of-the-black-king",
                            "name": "Reign of the Black King"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "sword-of-the-stranger",
                            "name": "Sword of the Stranger"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-broken-blade",
                            "name": "The Broken Blade"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-doom-in-wortham",
                            "name": "The Doom in Wortham"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "trailing-the-coven",
                            "name": "Trailing the Coven"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-imprisoned-angel",
                            "name": "The Imprisoned Angel"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "return-to-new-tristram",
                            "name": "Return to New Tristram"
                        }
                    }
                ]
            },
            "act2": {
                "completed": false,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "shadows-in-the-desert",
                            "name": "Shadows in the Desert"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-road-to-alcarnus",
                            "name": "The Road to Alcarnus"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "city-of-blood",
                            "name": "City of Blood"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "a-royal-audience",
                            "name": "A Royal Audience"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "unexpected-allies",
                            "name": "Unexpected Allies"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "betrayer-of-the-horadrim",
                            "name": "Betrayer of the Horadrim"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "blood-and-sand",
                            "name": "Blood and Sand"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-black-soulstone",
                            "name": "The Black Soulstone"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-scouring-of-caldeum",
                            "name": "The Scouring of Caldeum"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "lord-of-lies",
                            "name": "Lord of Lies"
                        }
                    }
                ]
            },
            "act3": {
                "completed": false,
                "quests": [
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-siege-of-bastions-keep",
                            "name": "The Siege of Bastion's Keep"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "turning-the-tide",
                            "name": "Turning the Tide"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-breached-keep",
                            "name": "The Breached Keep"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "tremors-in-the-stone",
                            "name": "Tremors in the Stone"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "machines-of-war",
                            "name": "Machines of War"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "siegebreaker",
                            "name": "Siegebreaker"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "heart-of-sin",
                            "name": "Heart of Sin"
                        }
                    }
                ]
            },
            "act4": {
                "completed": false,
                "quests": [
                    {
                        "completed": false,
                        "quest": {
                            "slug": "fall-of-the-high-heavens",
                            "name": "Fall of the High Heavens"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-light-of-hope",
                            "name": "The Light of Hope"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "beneath-the-spire",
                            "name": "Beneath the Spire"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "prime-evil",
                            "name": "Prime Evil"
                        }
                    }
                ]
            }
        },
        "inferno": {
            "act1": {
                "completed": false,
                "quests": [
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-fallen-star",
                            "name": "The Fallen Star"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-legacy-of-cain",
                            "name": "The Legacy of Cain"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "a-shattered-crown",
                            "name": "A Shattered Crown"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "reign-of-the-black-king",
                            "name": "Reign of the Black King"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "sword-of-the-stranger",
                            "name": "Sword of the Stranger"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-broken-blade",
                            "name": "The Broken Blade"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-doom-in-wortham",
                            "name": "The Doom in Wortham"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "trailing-the-coven",
                            "name": "Trailing the Coven"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-imprisoned-angel",
                            "name": "The Imprisoned Angel"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "return-to-new-tristram",
                            "name": "Return to New Tristram"
                        }
                    }
                ]
            },
            "act2": {
                "completed": false,
                "quests": [
                    {
                        "completed": false,
                        "quest": {
                            "slug": "shadows-in-the-desert",
                            "name": "Shadows in the Desert"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-road-to-alcarnus",
                            "name": "The Road to Alcarnus"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "city-of-blood",
                            "name": "City of Blood"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "a-royal-audience",
                            "name": "A Royal Audience"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "unexpected-allies",
                            "name": "Unexpected Allies"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "betrayer-of-the-horadrim",
                            "name": "Betrayer of the Horadrim"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "blood-and-sand",
                            "name": "Blood and Sand"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-black-soulstone",
                            "name": "The Black Soulstone"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-scouring-of-caldeum",
                            "name": "The Scouring of Caldeum"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "lord-of-lies",
                            "name": "Lord of Lies"
                        }
                    }
                ]
            },
            "act3": {
                "completed": false,
                "quests": [
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-siege-of-bastions-keep",
                            "name": "The Siege of Bastion's Keep"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "turning-the-tide",
                            "name": "Turning the Tide"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-breached-keep",
                            "name": "The Breached Keep"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "tremors-in-the-stone",
                            "name": "Tremors in the Stone"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "machines-of-war",
                            "name": "Machines of War"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "siegebreaker",
                            "name": "Siegebreaker"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "heart-of-sin",
                            "name": "Heart of Sin"
                        }
                    }
                ]
            },
            "act4": {
                "completed": false,
                "quests": [
                    {
                        "completed": false,
                        "quest": {
                            "slug": "fall-of-the-high-heavens",
                            "name": "Fall of the High Heavens"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-light-of-hope",
                            "name": "The Light of Hope"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "beneath-the-spire",
                            "name": "Beneath the Spire"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "prime-evil",
                            "name": "Prime Evil"
                        }
                    }
                ]
            }
        }
    },
    "kills": {
        "elites": 1064
    },
    "last-updated": 1339069947
}
```

## Hero Profile

The Hero Profile API is the primary way to access hero profile  information. This Hero Profile API can be used to fetch a single hero at a time through a HTTP GET request to a URL describing the hero profile resource.

By default, a basic dataset will be returned and with each request and zero or more additional fields can be retrieved. To access this API, craft a resource URL pointing to the hero of an account whos information is to be retrieved.

```plain
URL = Host + "/api/d3/hero/" + BattletagName + "-" + BattletagNumber + "/" + HeroId
```

There are no required query string parameters when accessing this resource.

*An example Career Profile API request:*

```plain
GET /api/d3/account/Straton-1/hero/1
Host: us.battle.net
```

*An example Career Profile API response:*
```plain
HTTP/1.1 200 OK
<http headers>

{ "id" : 1, "name" : "Yharr", "class" : "barbarian", "gender" : 0, "level" : 54, "hardcore" : false, ... }

```

The core dataset returned includes several key hero elements (name, level class, gender, hardcore flag, etc) as well as skills (both active and passive), equipped items, follower information (including items and skills), statis (attributes, resistances, etc) and progress.

### Hero Profile Example

```json
{
    "id": 182,
    "name": "Yharr",
    "class": "barbarian",
    "gender": 0,
    "level": 54,
    "hardcore": false,
    "skills": {
        "active": [
            {
                "skill": {
                    "slug": "frenzy",
                    "name": "Frenzy",
                    "icon": "barbarian_frenzy",
                    "tooltipParams": "skill/barbarian/frenzy",
                    "description": "Generate: 3 Fury per attack\r\n\r\nSwing for 110% weapon damage. Frenzy attack speed increases by 15% with each swing. This effect can stack up to 5 times for a total bonus of 75% attack speed.",
                    "simpleDescription": "Generate: 3 Fury per attack\r\n\r\nEnter a frenzied state that increases your attack speed with each hit."
                },
                "rune": {
                    "slug": "frenzy-d",
                    "type": "d",
                    "name": "Smite",
                    "description": "Add a 20% chance to call down a bolt of lightning from above, stunning your target for 1.5 seconds.",
                    "simpleDescription": "Add a chance to call down a bolt of lightning that stuns your target.",
                    "tooltipParams": "rune/frenzy/d",
                    "orderIndex": 3
                }
            },
            {
                "skill": {
                    "slug": "seismic-slam",
                    "name": "Seismic Slam",
                    "icon": "barbarian_seismicslam",
                    "tooltipParams": "skill/barbarian/seismic-slam",
                    "description": "Cost: 30 Fury\r\n\r\nSlam the ground and cause a wave of destruction that deals 155% weapon damage and Knockback to targets in a 45 yard arc.",
                    "simpleDescription": "Cost: 30 Fury\r\n\r\nCreate shockwaves that damage enemies in their path."
                },
                "rune": {
                    "slug": "seismic-slam-a",
                    "type": "a",
                    "name": "Shattered Ground",
                    "description": "Increase damage to 202% weapon damage and increases Knockback distance by 100%.",
                    "simpleDescription": "Increase the damage and Knockback distance.",
                    "tooltipParams": "rune/seismic-slam/a",
                    "orderIndex": 1
                }
            },
            {
                "skill": {
                    "slug": "earthquake",
                    "name": "Earthquake",
                    "icon": "barbarian_earthquake",
                    "tooltipParams": "skill/barbarian/earthquake",
                    "description": "Cost: 50 Fury\r\nCooldown: 120 seconds\r\n\r\nShake the ground violently, dealing 2000% weapon damage as Fire over 8 seconds to all enemies within 18 yards.",
                    "simpleDescription": "Cost: 50 Fury\r\nCooldown: 120 seconds\r\n\r\nViolent tremors shake the earth and damage nearby enemies."
                },
                "rune": {
                    "slug": "earthquake-d",
                    "type": "d",
                    "name": "The Mountain's Call",
                    "description": "Removes the Fury cost and reduces the cooldown to 105 seconds.",
                    "simpleDescription": "Removes the Fury cost and reduces the cooldown of Earthquake.",
                    "tooltipParams": "rune/earthquake/d",
                    "orderIndex": 2
                }
            },
            {
                "skill": {
                    "slug": "wrath-of-the-berserker",
                    "name": "Wrath of the Berserker",
                    "icon": "barbarian_wrathoftheberserker",
                    "tooltipParams": "skill/barbarian/wrath-of-the-berserker",
                    "description": "Cost: 50 Fury \r\nCooldown: 120 seconds\r\n\r\nEnter a berserker rage which raises several attributes for 15 seconds.\r\n\r\nCritical Hit Chance: 10%\r\nAttack Speed: 25%\r\nDodge Chance: 20%\r\nMovement Speed: 20%",
                    "simpleDescription": "Cost: 50 Fury \r\nCooldown: 120 seconds\r\n\r\nBecome Fury incarnate for 15 seconds."
                },
                "rune": {
                    "slug": "wrath-of-the-berserker-a",
                    "type": "a",
                    "name": "Insanity",
                    "description": "While active your damage is also increased by 100%.",
                    "simpleDescription": "Increase your damage while Wrath of the Berserker is active.",
                    "tooltipParams": "rune/wrath-of-the-berserker/a",
                    "orderIndex": 1
                }
            },
            {
                "skill": {
                    "slug": "war-cry",
                    "name": "War Cry",
                    "icon": "barbarian_warcry",
                    "tooltipParams": "skill/barbarian/war-cry",
                    "description": "Generate: 30 Fury\r\nCooldown: 30 seconds\r\n\r\nUnleash a rallying cry to increase Armor for you and all allies within 50 yards by 20% for 60 seconds.",
                    "simpleDescription": "Generate: 30 Fury\r\nCooldown: 30 seconds\r\n\r\nA rallying cry increases Armor for you and your allies for 60 seconds."
                },
                "rune": {
                    "slug": "war-cry-e",
                    "type": "e",
                    "name": "Invigorate",
                    "description": "Increases maximum Life by 10% and regenerates 310 Life per second while affected by War Cry.",
                    "simpleDescription": "Increase your maximum Life and regenerate Life while War Cry is active.",
                    "tooltipParams": "rune/war-cry/e",
                    "orderIndex": 2
                }
            },
            {
                "skill": {
                    "slug": "ignore-pain",
                    "name": "Ignore Pain",
                    "icon": "barbarian_ignorepain",
                    "tooltipParams": "skill/barbarian/ignore-pain",
                    "description": "Cooldown: 30 seconds\r\n\r\nReduces all damage taken by 65% for 5 seconds.",
                    "simpleDescription": "Cooldown: 30 seconds\r\n\r\nYour rage protects you from most damage for a limited time."
                },
                "rune": {
                    "slug": "ignore-pain-e",
                    "type": "e",
                    "name": "Ignorance is Bliss",
                    "description": "While Ignore Pain is active, gain 20% of all damage dealt as Life.",
                    "simpleDescription": "While Ignore Pain is active, gain Life for damage dealt to enemies.",
                    "tooltipParams": "rune/ignore-pain/e",
                    "orderIndex": 2
                }
            }
        ],
        "passive": [
            {
                "slug": "ruthless",
                "name": "Ruthless",
                "icon": "barbarian_passive_ruthless",
                "tooltipParams": "skill/barbarian/ruthless",
                "description": "Critical Hit Chance increased by 5%. Critical Hit Damage increased by 50%.\r\n\r\nMany skills and runes rely on Critical Hits to trigger their effects.",
                "flavor": "The clans each paint their warriors in their own unique way. Some celebrate the mountain, others honor the fire, but the Targos clan worships the purifying virtue of pain."
            },
            {
                "slug": "weapons-master",
                "name": "Weapons Master",
                "icon": "barbarian_passive_weaponsmaster",
                "tooltipParams": "skill/barbarian/weapons-master",
                "description": "Gain a bonus based on the weapon type of your main hand weapon:\r\nSwords/Daggers: 15% increased damage\r\nMaces/Axes: 10% Critical Hit Chance\r\nPolearms/Spears: 10% attack speed\r\nMighty Weapons: 3 Fury per hit",
                "flavor": "\"My men ambushed the traveler in the woods, but it was we who were surprised. Such keen senses, swift motions, flawless strikes. We never stood a chance.\" ?Redjack the Bandit"
            },
            {
                "slug": "nerves-of-steel",
                "name": "Nerves Of Steel",
                "icon": "barbarian_passive_nervesofsteel",
                "tooltipParams": "skill/barbarian/nerves-of-steel",
                "description": "Your Armor is increased by 100% of your Vitality.",
                "flavor": "\"The trials begin with childhood; skinning ferocious beasts, climbing windswept cliffs and carrying weapons heavy enough to make a southern soldier weep. Is it any wonder that they never give ground?\" ?Sir Aric of Duncraig"
            }
        ]
    },
    "items": {
        "head": {
            "name": "Wild Casque of Invasion",
            "icon": "helm_104",
            "displayColor": "blue",
            "tooltipParams": "item-data/CPvK9pADEgcIBBU69U5dHTIL5KIdAn-SATAJOPUDQABIFVAIYPUD"
        },
        "torso": {
            "name": "Covenant Invasion",
            "icon": "chestarmor_105",
            "displayColor": "yellow",
            "tooltipParams": "item-data/CJrCw64IEgcIBBXtHRlgHQJ_kgEd6SuJOh3Y7Sq9HZMCY-oiCwgBFWdCAwAYDiAUMAk4qAVAAEgNUAxgqAVqJQoMCAAQ8--hp4CAgOAwEhUIqNWDxQMSBwgEFfSe2KswCTgAQAFqJQoMCAAQifChp4CAgOAwEhUIvbPojwkSBwgEFfSe2KswCTgAQAFqJQoMCAAQp_Chp4CAgOAwEhUI17rWjQwSBwgEFfSe2KswCTgAQAE"
        },
        "feet": {
            "name": "Relentless Battle Greaves of Invasion",
            "icon": "boots_105",
            "displayColor": "blue",
            "tooltipParams": "item-data/CILd8t4NEgcIBBVcQZt_HdM9BzUdQzTvhjAJOIYEQABIDVAIYIYE"
        },
        "hands": {
            "name": "Cruel Gage",
            "icon": "gloves_103",
            "displayColor": "yellow",
            "tooltipParams": "item-data/CMzrzgESBwgEFYNXkqQd9ORSKh3gzHZQHRCRU2gdvdK3LR0Cf5IBIgsIABW6RAMAGBogGDAJONgDQABIDVAOYNgD"
        },
        "shoulders": {
            "name": "Champion Reprisal",
            "icon": "shoulders_104",
            "displayColor": "yellow",
            "tooltipParams": "item-data/CIuLmwMSBwgEFY30yBUd0cIitx0axFF0HeE5hwIdvlvoSCILCAEVu0QDABgUICYwCTiDBUAASBJQDGCDBQ"
        },
        "legs": {
            "name": "Battle Cinder",
            "icon": "pants_102",
            "displayColor": "yellow",
            "tooltipParams": "item-data/CI-_yboGEgcIBBVYjtWlHbyNjMMdidXDnR25MEgIHQvRkggdGE28Kh2UvzSKIgsIARV1QgMAGAIgGDAJOLEEQABIDVAQYLEEaiUKDAgAEOaWgIuAgICAEBIVCIaN74UDEgcIBBVG9YtfMAk4AEAB"
        },
        "bracers": {
            "name": "Protection Mettle",
            "icon": "bracers_103",
            "displayColor": "yellow",
            "tooltipParams": "item-data/CIW466IFEgcIBBWVKMrLHQJ_kgEdD9xxfB2crKCYHRKHPlYdSFJ1-h1DYFFAIgsIARVvQgMAGAQgADAJOOEDQABQEGDhAw"
        },
        "mainHand": {
            "name": "Destruction Wisp",
            "icon": "sword_2h_201",
            "displayColor": "yellow",
            "tooltipParams": "item-data/CMGq1KMEEgcIBBX6_S7yHZtssxQdS2NPMB2o7995HWPY6agiCwgBFXdCAwAYACAUMAk4hQRAAFAMYIUE"
        },
        "offHand": null,
        "waist": {
            "name": "Scale Envy",
            "icon": "belt_105",
            "displayColor": "yellow",
            "tooltipParams": "item-data/CMXv_fcHEgcIBBV8o0LUHUoyxxwd3WH9HR0fhz5WHUM074YiCwgBFXVCAwAYDiASMAk4wQNAAFAMYMED"
        },
        "rightFinger": {
            "name": "Empty Band",
            "icon": "ring_09",
            "displayColor": "yellow",
            "tooltipParams": "item-data/CMn4h5MJEgcIBBX4VF1EHRhNvCodulvoSB2FvzSKHUDxmysiCwgAFcv-AQAYDCAGMAk47QJAAFAMYO0CaiUKDAgAELTa1JqAgIDgIBIVCJvB4cEOEgcIBBVF9YtfMAk4AEAB"
        },
        "leftFinger": {
            "name": "Gambler's Loop",
            "icon": "ring_10",
            "displayColor": "yellow",
            "tooltipParams": "item-data/CNT-vN0DEgcIBBUQVV1EHYutUmgdRH0C5R0-vYo1HRjTLBAdjrDM0B0WpNPYIgsIABW2_gEAGCQgCDAJOKwDQABQEGCsA2okCgwIABCk2tSagICA4CASFAjysbA9EgcIBBVF9YtfMAk4AEAB"
        },
        "neck": {
            "name": "Nobility Aim",
            "icon": "amulet07",
            "displayColor": "yellow",
            "tooltipParams": "item-data/COCVqNAHEgcIBBWPxURkHSUlWp4dO7LM0B29_O7IHTKHYggiCwgBFcZEAwAYGiAkMAk4kANAAFAMYJADaiUKDAgAEKimv5GAgICgAxIVCOfkurINEgcIBBVG9YtfMAk4AEAB"
        }
    },
    "followers": {
        "templar": {
            "slug": "templar",
            "level": 47,
            "items": {
                "mainHand": {
                    "name": "Slice Favor",
                    "icon": "dagger_105",
                    "displayColor": "yellow",
                    "tooltipParams": "item-data/COTwoI4GEgcIBBU_ek-yHdaqHqYdCCTSvx2OsMzQHWGvmYwiCwgBFcBEAwAYJCAQMAk49gNAAFAMYPYD"
                },
                "offHand": {
                    "name": "Socketed Ironwood Shield of the Lion",
                    "icon": "shield_104",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CPqUoIcLEgcIBBXNBztsHYYCY-odVS2mmjAJONgEQABQCGDYBA"
                },
                "rightFinger": {
                    "name": "Socketed Ring",
                    "icon": "ring_11",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CIHsvdQHEgcIBBURVV1EHTuyzNAwCTilBEAAUAZgpQQ"
                },
                "leftFinger": {
                    "name": "Ring of Focus",
                    "icon": "ring_11",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CLTkz_ELEgcIBBURVV1EHYkH0n8wCTjcA0AAUAZg3AM"
                },
                "neck": {
                    "name": "Amulet of the Hawk",
                    "icon": "amulet04",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CI_H2LkPEgcIBBWMxURkHXT3SgcwCTjTA0AAUAZg0wM"
                },
                "special": {
                    "name": "Devotion Defiance",
                    "icon": "templar_special_001",
                    "displayColor": "yellow",
                    "tooltipParams": "item-data/CIGQjbsGEgcIBBVlA2NEHV1QqgcdpL9pwB2YkYQeHeQriToiCwgBFYVCAwAYACAMMAk4AEAAUAw"
                }
            },
            "skills": [
                {
                    "slug": "heal",
                    "name": "Heal",
                    "icon": "templar_heal",
                    "tooltipParams": "skill/templar/heal",
                    "description": "Heals you or the Templar for 4651 Life.\r\n\r\nCooldown: 30 seconds",
                    "simpleDescription": "Heals you or the Templar."
                },
                {
                    "slug": "loyalty",
                    "name": "Loyalty",
                    "icon": "templar_loyalty",
                    "tooltipParams": "skill/templar/loyalty",
                    "description": "Regenerates 155 Life per second for you and the Templar.",
                    "simpleDescription": "Provides Life regeneration for you and the Templar."
                },
                {
                    "slug": "charge",
                    "name": "Charge",
                    "icon": "templar_shieldcharge",
                    "tooltipParams": "skill/templar/charge",
                    "description": "Charges a target, dealing 50% weapon damage and stunning all enemies within 8 yards for 2 seconds.\r\n\r\nCooldown: 30 seconds",
                    "simpleDescription": "Charges an enemy, dealing damage and stunning the target."
                },
                {
                    "slug": "guardian",
                    "name": "Guardian",
                    "icon": "templar_guardian",
                    "tooltipParams": "skill/templar/guardian",
                    "description": "Rush to the aid of wounded ally, knocking back enemies within 15 yards and healing the wounded ally for 4651 Life.\r\n\r\nCooldown: 30 seconds",
                    "simpleDescription": "When hero Life is low, the Templar will come to your aid, knocking back nearby enemies and healing you."
                }
            ]
        },
        "scoundrel": {
            "slug": "scoundrel",
            "level": 51,
            "items": {
                "mainHand": {
                    "name": "Outcast Shrike",
                    "icon": "crossbow_105",
                    "displayColor": "yellow",
                    "tooltipParams": "item-data/CJ--6v8OEgcIBBXHV8oKHaAjvEgdZFCqBx07sszQHdqQjBQiCwgAFcv-AQAYFiAIMAk4kQRAAFAMYJEE"
                },
                "offHand": null,
                "rightFinger": {
                    "name": "Keen Ring",
                    "icon": "ring_05",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CMvwx6MFEgcIBBX0VF1EHe9xwNAwCTi_A0AAUAZgvwM"
                },
                "leftFinger": {
                    "name": "Scouting Ring of the Lion",
                    "icon": "ring_04",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/COmIkpQCEgcIBBXzVF1EHc2PnK4dFHhJFTAJOMUDQABQCGDFAw"
                },
                "neck": {
                    "name": "Scouting Amulet of Wounding",
                    "icon": "amulet02",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CIf0ie4BEgcIBBWKxURkHZZocwUdvHs9ADAJOPsDQABQCGD7Aw"
                },
                "special": {
                    "name": "Disciple's Poise",
                    "icon": "scoundrel_special_102",
                    "displayColor": "yellow",
                    "tooltipParams": "item-data/CK7y3O8JEgcIBBVh_UvyHXb3SgcdJSVanh2akYQeHWRQqgciCwgBFXFCAwAYGCAaMAk4AEAAUAw"
                }
            },
            "skills": [
                {
                    "slug": "crippling-shot",
                    "name": "Crippling Shot",
                    "icon": "scoundrel_cripplingshot",
                    "tooltipParams": "skill/scoundrel/crippling-shot",
                    "description": "Ranged attack that slows the target by 60% for 3 seconds.\r\n\r\nCooldown: 6 seconds",
                    "simpleDescription": "Deals damage and slows the target."
                },
                {
                    "slug": "dirty-fighting",
                    "name": "Dirty Fighting",
                    "icon": "scoundrel_dirtyfighting",
                    "tooltipParams": "skill/scoundrel/dirty-fighting",
                    "description": "Blinds enemies in front of the Scoundrel for 3 seconds.\r\n\r\nCooldown: 30 seconds",
                    "simpleDescription": "Blinds nearby enemies."
                },
                {
                    "slug": "powered-shot",
                    "name": "Powered Shot",
                    "icon": "scoundrel_powershot",
                    "tooltipParams": "skill/scoundrel/powered-shot",
                    "description": "Powerful ranged attack that explodes on impact, dealing 25% weapon damage as Arcane to targets within 6 yards and has a 50% chance to Stun targets for 2 seconds.\r\n\r\nCooldown: 20 seconds",
                    "simpleDescription": "Deals massive damage in an area and knocks back enemies."
                },
                {
                    "slug": "anatomy",
                    "name": "Anatomy",
                    "icon": "scoundrel_anatomy",
                    "tooltipParams": "skill/scoundrel/anatomy",
                    "description": "Increases Critical Hit Chance by 3% for the Scoundrel and his allies.",
                    "simpleDescription": "Increases the Critical Hit Chance of the Scoundrel and his allies."
                }
            ]
        },
        "enchantress": {
            "slug": "enchantress",
            "level": 53,
            "items": {
                "mainHand": {
                    "name": "Skywarden",
                    "icon": "unique_mace_2h_010",
                    "displayColor": "orange",
                    "tooltipParams": "item-data/CPjT4eQLEgcIBBX1otksHZuwzNAdPoRWVB2xIBV7HTeqe1AdSmNPMDAJOLwDQABQEmC8Aw"
                },
                "offHand": null,
                "rightFinger": {
                    "name": "Invigorating Ring",
                    "icon": "ring_17",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CJfa5qkPEgcIBBUXVV1EHb5b6EgwCTjzAkAAUAZg8wI"
                },
                "leftFinger": {
                    "name": "Proud Ring",
                    "icon": "ring_09",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CJnK6b0KEgcIBBX4VF1EHQ_ccXwwCTjFA0AAUAZgxQM"
                },
                "neck": {
                    "name": "Clever Amulet of Mutilation",
                    "icon": "amulet06",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CKTpw-YKEgcIBBWOxURkHQJEX6Adx5dAYDAJOOwDQABQCGDsAw"
                },
                "special": {
                    "name": "Steadfast Root of Mutilation",
                    "icon": "enchantress_special_104",
                    "displayColor": "blue",
                    "tooltipParams": "item-data/CMWEkoMLEgcIBBXynmItHQVEX6AdInwGyDAJOABAAFAI"
                }
            },
            "skills": [
                {
                    "slug": "forceful-push",
                    "name": "Forceful Push",
                    "icon": "enchantress_forcefulpush",
                    "tooltipParams": "skill/enchantress/forceful-push",
                    "description": "Summon an Arcane explosion 8 yards around an enemy, dealing 100% weapon damage as Arcane and knocking back all monsters caught within it.\r\n\r\nCooldown: 10 seconds",
                    "simpleDescription": "Creates an explosion that deals massive damage and knocks back enemies."
                },
                {
                    "slug": "powered-armor",
                    "name": "Powered Armor",
                    "icon": "enchantress_poweredarmor",
                    "tooltipParams": "skill/enchantress/powered-armor",
                    "description": "Enchantress buffs herself and her allies, increasing Armor by 15%. Attackers are slowed by 30% for 3 seconds.",
                    "simpleDescription": "Increases the armor of the Enchantress and her allies, and slows attacking enemies."
                },
                {
                    "slug": "erosion",
                    "name": "Erosion",
                    "icon": "enchantress_scorchedearth",
                    "tooltipParams": "skill/enchantress/erosion",
                    "description": "Conjures a pool of energy that deals 50% weapon damage as Arcane  per second. Affected enemies take an extra 15% damage from all attacks for 3 seconds.\r\n\r\nCooldown: 15 seconds",
                    "simpleDescription": "Blasts a target area, causing enemies to take damage over time."
                },
                {
                    "slug": "focused-mind",
                    "name": "Focused Mind",
                    "icon": "enchantress_focusedmind",
                    "tooltipParams": "skill/enchantress/focused-mind",
                    "description": "An aura that increases attack speed by 3% for allies within 40 yards.",
                    "simpleDescription": "Increases the attack speed of the Enchantress and her allies."
                }
            ]
        }
    },
    "stats": {
        "damageIncrease": 10.069999694824219,
        "damageReduction": 0.5207669734954834,
        "critChance": 0.10999999940395355,
        "life": 17285,
        "strength": 1007,
        "dexterity": 295,
        "intelligence": 156,
        "vitality": 570,
        "armor": 2934,
        "coldResist": 0,
        "fireResist": 0,
        "lightningResist": 0,
        "poisonResist": 0,
        "arcaneResist": 0,
        "damage": 4763.17
    },
    "progress": {
        "normal": {
            "act1": {
                "completed": true,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-fallen-star",
                            "name": "The Fallen Star"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-legacy-of-cain",
                            "name": "The Legacy of Cain"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "a-shattered-crown",
                            "name": "A Shattered Crown"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "reign-of-the-black-king",
                            "name": "Reign of the Black King"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "sword-of-the-stranger",
                            "name": "Sword of the Stranger"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-broken-blade",
                            "name": "The Broken Blade"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-doom-in-wortham",
                            "name": "The Doom in Wortham"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "trailing-the-coven",
                            "name": "Trailing the Coven"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-imprisoned-angel",
                            "name": "The Imprisoned Angel"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "return-to-new-tristram",
                            "name": "Return to New Tristram"
                        }
                    }
                ]
            },
            "act2": {
                "completed": true,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "shadows-in-the-desert",
                            "name": "Shadows in the Desert"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-road-to-alcarnus",
                            "name": "The Road to Alcarnus"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "city-of-blood",
                            "name": "City of Blood"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "a-royal-audience",
                            "name": "A Royal Audience"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "unexpected-allies",
                            "name": "Unexpected Allies"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "betrayer-of-the-horadrim",
                            "name": "Betrayer of the Horadrim"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "blood-and-sand",
                            "name": "Blood and Sand"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-black-soulstone",
                            "name": "The Black Soulstone"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-scouring-of-caldeum",
                            "name": "The Scouring of Caldeum"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "lord-of-lies",
                            "name": "Lord of Lies"
                        }
                    }
                ]
            },
            "act3": {
                "completed": true,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-siege-of-bastions-keep",
                            "name": "The Siege of Bastion's Keep"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "turning-the-tide",
                            "name": "Turning the Tide"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-breached-keep",
                            "name": "The Breached Keep"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "tremors-in-the-stone",
                            "name": "Tremors in the Stone"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "machines-of-war",
                            "name": "Machines of War"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "siegebreaker",
                            "name": "Siegebreaker"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "heart-of-sin",
                            "name": "Heart of Sin"
                        }
                    }
                ]
            },
            "act4": {
                "completed": true,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "fall-of-the-high-heavens",
                            "name": "Fall of the High Heavens"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-light-of-hope",
                            "name": "The Light of Hope"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "beneath-the-spire",
                            "name": "Beneath the Spire"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "prime-evil",
                            "name": "Prime Evil"
                        }
                    }
                ]
            }
        },
        "nightmare": {
            "act1": {
                "completed": true,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-fallen-star",
                            "name": "The Fallen Star"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-legacy-of-cain",
                            "name": "The Legacy of Cain"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "a-shattered-crown",
                            "name": "A Shattered Crown"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "reign-of-the-black-king",
                            "name": "Reign of the Black King"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "sword-of-the-stranger",
                            "name": "Sword of the Stranger"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-broken-blade",
                            "name": "The Broken Blade"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-doom-in-wortham",
                            "name": "The Doom in Wortham"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "trailing-the-coven",
                            "name": "Trailing the Coven"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-imprisoned-angel",
                            "name": "The Imprisoned Angel"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "return-to-new-tristram",
                            "name": "Return to New Tristram"
                        }
                    }
                ]
            },
            "act2": {
                "completed": true,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "shadows-in-the-desert",
                            "name": "Shadows in the Desert"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-road-to-alcarnus",
                            "name": "The Road to Alcarnus"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "city-of-blood",
                            "name": "City of Blood"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "a-royal-audience",
                            "name": "A Royal Audience"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "unexpected-allies",
                            "name": "Unexpected Allies"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "betrayer-of-the-horadrim",
                            "name": "Betrayer of the Horadrim"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "blood-and-sand",
                            "name": "Blood and Sand"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-black-soulstone",
                            "name": "The Black Soulstone"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-scouring-of-caldeum",
                            "name": "The Scouring of Caldeum"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "lord-of-lies",
                            "name": "Lord of Lies"
                        }
                    }
                ]
            },
            "act3": {
                "completed": true,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-siege-of-bastions-keep",
                            "name": "The Siege of Bastion's Keep"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "turning-the-tide",
                            "name": "Turning the Tide"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-breached-keep",
                            "name": "The Breached Keep"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "tremors-in-the-stone",
                            "name": "Tremors in the Stone"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "machines-of-war",
                            "name": "Machines of War"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "siegebreaker",
                            "name": "Siegebreaker"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "heart-of-sin",
                            "name": "Heart of Sin"
                        }
                    }
                ]
            },
            "act4": {
                "completed": true,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "fall-of-the-high-heavens",
                            "name": "Fall of the High Heavens"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-light-of-hope",
                            "name": "The Light of Hope"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "beneath-the-spire",
                            "name": "Beneath the Spire"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "prime-evil",
                            "name": "Prime Evil"
                        }
                    }
                ]
            }
        },
        "hell": {
            "act1": {
                "completed": true,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-fallen-star",
                            "name": "The Fallen Star"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-legacy-of-cain",
                            "name": "The Legacy of Cain"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "a-shattered-crown",
                            "name": "A Shattered Crown"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "reign-of-the-black-king",
                            "name": "Reign of the Black King"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "sword-of-the-stranger",
                            "name": "Sword of the Stranger"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-broken-blade",
                            "name": "The Broken Blade"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-doom-in-wortham",
                            "name": "The Doom in Wortham"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "trailing-the-coven",
                            "name": "Trailing the Coven"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-imprisoned-angel",
                            "name": "The Imprisoned Angel"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "return-to-new-tristram",
                            "name": "Return to New Tristram"
                        }
                    }
                ]
            },
            "act2": {
                "completed": false,
                "quests": [
                    {
                        "completed": true,
                        "quest": {
                            "slug": "shadows-in-the-desert",
                            "name": "Shadows in the Desert"
                        }
                    },
                    {
                        "completed": true,
                        "quest": {
                            "slug": "the-road-to-alcarnus",
                            "name": "The Road to Alcarnus"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "city-of-blood",
                            "name": "City of Blood"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "a-royal-audience",
                            "name": "A Royal Audience"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "unexpected-allies",
                            "name": "Unexpected Allies"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "betrayer-of-the-horadrim",
                            "name": "Betrayer of the Horadrim"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "blood-and-sand",
                            "name": "Blood and Sand"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-black-soulstone",
                            "name": "The Black Soulstone"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-scouring-of-caldeum",
                            "name": "The Scouring of Caldeum"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "lord-of-lies",
                            "name": "Lord of Lies"
                        }
                    }
                ]
            },
            "act3": {
                "completed": false,
                "quests": [
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-siege-of-bastions-keep",
                            "name": "The Siege of Bastion's Keep"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "turning-the-tide",
                            "name": "Turning the Tide"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-breached-keep",
                            "name": "The Breached Keep"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "tremors-in-the-stone",
                            "name": "Tremors in the Stone"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "machines-of-war",
                            "name": "Machines of War"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "siegebreaker",
                            "name": "Siegebreaker"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "heart-of-sin",
                            "name": "Heart of Sin"
                        }
                    }
                ]
            },
            "act4": {
                "completed": false,
                "quests": [
                    {
                        "completed": false,
                        "quest": {
                            "slug": "fall-of-the-high-heavens",
                            "name": "Fall of the High Heavens"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-light-of-hope",
                            "name": "The Light of Hope"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "beneath-the-spire",
                            "name": "Beneath the Spire"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "prime-evil",
                            "name": "Prime Evil"
                        }
                    }
                ]
            }
        },
        "inferno": {
            "act1": {
                "completed": false,
                "quests": [
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-fallen-star",
                            "name": "The Fallen Star"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-legacy-of-cain",
                            "name": "The Legacy of Cain"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "a-shattered-crown",
                            "name": "A Shattered Crown"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "reign-of-the-black-king",
                            "name": "Reign of the Black King"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "sword-of-the-stranger",
                            "name": "Sword of the Stranger"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-broken-blade",
                            "name": "The Broken Blade"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-doom-in-wortham",
                            "name": "The Doom in Wortham"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "trailing-the-coven",
                            "name": "Trailing the Coven"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-imprisoned-angel",
                            "name": "The Imprisoned Angel"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "return-to-new-tristram",
                            "name": "Return to New Tristram"
                        }
                    }
                ]
            },
            "act2": {
                "completed": false,
                "quests": [
                    {
                        "completed": false,
                        "quest": {
                            "slug": "shadows-in-the-desert",
                            "name": "Shadows in the Desert"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-road-to-alcarnus",
                            "name": "The Road to Alcarnus"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "city-of-blood",
                            "name": "City of Blood"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "a-royal-audience",
                            "name": "A Royal Audience"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "unexpected-allies",
                            "name": "Unexpected Allies"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "betrayer-of-the-horadrim",
                            "name": "Betrayer of the Horadrim"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "blood-and-sand",
                            "name": "Blood and Sand"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-black-soulstone",
                            "name": "The Black Soulstone"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-scouring-of-caldeum",
                            "name": "The Scouring of Caldeum"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "lord-of-lies",
                            "name": "Lord of Lies"
                        }
                    }
                ]
            },
            "act3": {
                "completed": false,
                "quests": [
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-siege-of-bastions-keep",
                            "name": "The Siege of Bastion's Keep"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "turning-the-tide",
                            "name": "Turning the Tide"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-breached-keep",
                            "name": "The Breached Keep"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "tremors-in-the-stone",
                            "name": "Tremors in the Stone"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "machines-of-war",
                            "name": "Machines of War"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "siegebreaker",
                            "name": "Siegebreaker"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "heart-of-sin",
                            "name": "Heart of Sin"
                        }
                    }
                ]
            },
            "act4": {
                "completed": false,
                "quests": [
                    {
                        "completed": false,
                        "quest": {
                            "slug": "fall-of-the-high-heavens",
                            "name": "Fall of the High Heavens"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "the-light-of-hope",
                            "name": "The Light of Hope"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "beneath-the-spire",
                            "name": "Beneath the Spire"
                        }
                    },
                    {
                        "completed": false,
                        "quest": {
                            "slug": "prime-evil",
                            "name": "Prime Evil"
                        }
                    }
                ]
            }
        }
    },
    "kills": {
        "elites": 1064
    },
    "last-updated": 1339069947
}
```