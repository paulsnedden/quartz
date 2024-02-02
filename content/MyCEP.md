---
Tags: TeamNote
Name: MyCEP
Created: 2023-02-02
---
# MyCEP - [[2023-02-02]]
## Notes
The [[Tribe]] I'm working with, as of [[2023-01-30]]
![[MyCEP Tribe.png]]

### [[Tribe Lead]]
[[Maarten van Schagen]]

### [[Value Leads]] 
[[Chrissy Montgomery]] , [[Abigail Harris]] and [[Christopher Drummond]]

### Enablement Team
#### [[Change Lead]]
[[Angeline Wilkes]]

#### Tribe Coordinator
[[Memory Puletua]]

### Squads
```dataview
Table without id file.link as "Squad", PO, ATF
from "Work"
where contains(Tags, "Squad") and contains(Tags, "MyCEP")
sort ASC
```

![[Agile coach chat re ATFs in tribe- Marty- Sneddo - 2023-02-17 (Notes)#^4gpz9x]]

### [[Mission]] 
> Attract, develop and retain top talent through personalised career experiences to build meaningful careers for now and into the future across our retail ecosystem and platforms, in line with business strategy

<iframe src="https://docs.google.com/presentation/d/1zz8uX54f-sqhOkgciZ8nD9CCfaLXKDChrtamHT0cZ2o/edit#slide=id.g1f95189ca21_0_3639" allowfullscreen width=100% height=100%> </iframe>


## DISC Profiles
```dataview
table without id file.link as Name, DISC as "DISC Profile"
FROM #Person 

WHERE DISC
SORT DISC ASC, file.link ASC
```

## Tribe Events
### Tribe Council
```dataview
table without ID
	link(file.link, title) as "Council Event", Created as "Date Held"
	from #MeetingNote
where Type="Tribe Council"
Sort Created desc limit 5
```

### Tribe Standup
```dataview
table without ID
	link(file.link, title) as "Tribe Event", Created as "Date Held"
	from #MeetingNote
where contains(Type,"Tribe") and
	contains(Type, "StandUp")
Sort Created desc limit 5
```
