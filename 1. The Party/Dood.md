---
NoteIcon: player
aliases: 
tags:
  - player
Player: Bob
Role: Player
Class: 
Race: 
level: 
hp: 
ac: 
modifier: 
pasperc: 
Status: Active
PlayerKnownLanguages:
  - Celestial
  - Common
  - Dwarvish
faction_standing:
  Faction Name 1: 1
  Faction Name 3: 3
---

<%*
const hasTitle = !tp.file.title.startsWith("NewPlayer");
let title;
if (!hasTitle) {
    title = await tp.system.prompt("Enter Player Name");
    await tp.file.rename(title);
} else {
    title = tp.file.title;
}
_%>

[[Pasted image 20220612052639.png]]

# `=this.file.name`

| Image                                              | Char Name         | Player Name    | Class         | Race         | Level         |
| -------------------------------------------------- | ----------------- | -------------- | ------------- | ------------ | ------------- |
| ![[ImagePlaceholder.png\|cover hsmall]] | `=this.file.name` |  `VIEW[{Player}]` | `VIEW[{Class}]` | `VIEW[{Race}]` | `VIEW[{level}]` |

```dataviewjs
const player = dv.current();
const factions = dv.pages('"3-Mechanics/Guilds and Groups"');
let tableData = [];
for (let faction of factions) {
    let factionName = faction.faction;
    let playerStanding = player.faction_standing?.[factionName] || 0;

    // Ensure benefits is treated as an array
    let benefitsList = Array.isArray(faction.benefits) ? faction.benefits : [];

    // Filter benefits the player qualifies for
    let qualifiedBenefits = benefitsList
        .filter(b => playerStanding >= b.standing)
        .map(b => b.reward)
        .join(", "); 

    let primaryContact = faction.primary_contact || "No contact set";

    tableData.push([factionName, playerStanding, qualifiedBenefits || "No benefits yet", primaryContact]);
}
dv.table(["Faction", "Your Standing", "Benefits", "Primary Contact"], tableData);
```

```custom-frames
frame: ConfigureInCustomFramesPlugin
```

