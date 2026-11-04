---
type: campaign
campaign: C1
status: active
tags: [campaign]
---
# The Embers of Sacrifice

*Also known as The Off-Branded Misfits.* A Berserk-inspired campaign about five branded souls and the Godhand.

## Party
```dataview
TABLE player, race, class, level FROM "04_Campaigns/C1 - The Embers of Sacrifice/Party" WHERE type = "pc" SORT file.name ASC
```

## Adventures
```dataview
TABLE status FROM "04_Campaigns/C1 - The Embers of Sacrifice/Adventures" WHERE type = "adventure"
```

## Sessions
```dataview
TABLE date, arc, status FROM "04_Campaigns/C1 - The Embers of Sacrifice/Sessions" WHERE type = "session" SORT session DESC LIMIT 10
```

## Open Prep Tasks
```dataview
TASK FROM "04_Campaigns/C1 - The Embers of Sacrifice/Sessions" WHERE !completed
```
