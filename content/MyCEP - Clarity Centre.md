---
tag:
 - Objective

fileClass: [Objective]
Status: In Progress
Date: F24
---
# MyCEP - Clarity Centre

Progress:: `$=const setPage="MyCEP - Clarity Centre"; const value = Math.round(((dv.page(setPage).file.tasks.where(t => t.completed).length) / (dv.page(setPage).file.tasks).length) * 100); "<progress value='" + value + "' max='100'></progress>" + "<span style='font-size:smaller;color:var(--text-muted)'>" + value + "% &nbsp;| &nbsp;" + (dv.page(setPage).file.tasks.length - dv.page(setPage).file.tasks.where(t => t.completed).length) + " left</span>"`


## Objective Description
Provide a one-stop shop for the MyCEP Tribe to connect and collaborate

## Key Results
- Majority of Tribe Council feedback is positive
- Majority of Tribe Council use the Clarity Centre on a regular basis

## Tasks
- [x] Understand what the squads are currently using (Jira or Miro)
- [x] Understand the high level requirements of the Clarity Centre (from MvS and POs)
- [x] MyCEP Jira Project to capture Objectives/Big Rocks
	- [Jira Project](https://woolworths-agile.atlassian.net/jira/software/c/projects/MYCEP/boards/6634)
- [x] Miro Board built
	- [Miro Board](https://miro.com/app/board/uXjVMG2Vleg=/)
	- [x] OKRs included ✅ 2023-06-16
	- [x] Roadmap included (Program Board?) ✅ 2023-06-09
	- [x] Prioritisation Map from Tribe Council ✅ 2023-09-19
	- [x] Sprints as Rows, Squads as Columns ✅ 2023-09-19

## Analysis
Squads use a combo of Jira and Miro
With the upcoming beta release of Project Board in Miro, I think this could replace all existing planning boards.

**[[Maarten van Schagen]]'s requirements**
Must include:
- run
- roadmap
- sprints as rows, squads as verticals
- prioritisation map from tribe concil
- OKR tracker
