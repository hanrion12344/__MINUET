---
tags: []
banner: "![[2025 4월 Weekly Banner.jpg]]"
banner_icon: 🗓️
---
---
tags:
 - "#calendar/weekly/2025"

banner: "![[2025 4월 Weekly Banner.jpg]]"
banner_icon: 🗓️
---

# 2025-04 Week 16

[[2025 Week 15|↶ Previous Week]] | [[2025 Week 17|Following Week ↷]]

> [!METADATA]-
> Created:: [[2025-04-17]] 22:00
> Updated:: 2025-04-17 22:00
> ID:: 20250417220018

**Table of Contents:**
```toc
style: number
```

___

## Memos
- [[2025-04-13|Monday]]
	![[2025-04-13#^memo-link]]
- [[2025-04-14|Tuesday]]
	![[2025-04-14#^memo-link]]
- [[2025-04-15|Wednesday]]
	![[2025-04-15#^memo-link]]
- [[2025-04-16|Thursday]]
	![[2025-04-16#^memo-link]]
- [[2025-04-17|Friday]]
	![[2025-04-17#^memo-link]]
- [[2025-04-18|Saturday]]
	![[2025-04-18#^memo-link]]
- [[2025-04-19|Sunday]]
	![[2025-04-19#^memo-link]]

## Work Log
- [[2025-04-13|Monday]]
	![[2025-04-13#^work-link]]
- [[2025-04-14|Tuesday]]
	![[2025-04-14#^work-link]]
- [[2025-04-15|Wednesday]]
	![[2025-04-15#^work-link]]
- [[2025-04-16|Thursday]]
	![[2025-04-16#^work-link]]
- [[2025-04-17|Friday]]
	![[2025-04-17#^work-link]]
- [[2025-04-18|Saturday]]
	![[2025-04-18#^work-link]]
- [[2025-04-19|Sunday]]
	![[2025-04-19#^work-link]] 

## Overview
### Week Statistics
```dataviewjs
const daysPath = dv.current().file.folder;

const attributes = {
	'panic': {
		label: 'Panic',
		average: 10,
	},
	'money-spent': {
		label: 'Money Spent',
		backgroundColor: 'rgba(85, 174, 229, 0.2)',
		borderColor: 'rgba(85, 174, 229, 1)',
		average: 20,
	},
	'prayer': {
		label: 'Prayer',
		backgroundColor: 'rgba(255, 211, 101, 0.2)',
		borderColor: 'rgba(255, 211, 101, 1)',
		average: 5,
	},
	'steps': {
		label: 'Steps',
		backgroundColor: 'rgba(141, 82, 188, 0.2)',
		borderColor: 'rgba(141, 82, 188, 1)',
		average: 10000,
	},
	'hours-worked': {
		label : 'Hours Worked',
		backgroundColor: 'rgba(143, 208, 50, 0.2)',
		borderColor: 'rgba(143, 208, 50, 1)',
		average: 6
	},
};

const date = "2025-04-17";

customJS.DvCharts.renderWeeklyChart({
	dv,
	context: this,
	daysPath: '02 Personal/02.01 Periodic Notes/2025/Daily/04 4월',
	attributes,
	type: 'average',
	date
})
```

```dataview
TABLE WITHOUT ID
	link(file.name) as "Day",
	feeling AS "💭",
	money-spent AS "💸",
	panic AS "🌪️",
	prayer AS "🕋",
	steps AS "👣",
	hours-worked AS "✏️"
FROM "02 Personal/02.01 Periodic Notes"
WHERE week = [[2025 Week 16]]
SORT file.name ASC
```

### Habits
```dataview
TABLE WITHOUT ID
	file.link AS "Day",
	anki AS "📇",
	coffee AS "☕",
	exercise AS "🏋️",
	martial-arts AS "🥋",
	reading AS "👓",
	revision AS "🔁",
	shower AS "🚿",
	typing AS "⌨️"
FROM "02 Personal/02.01 Periodic Notes"
WHERE week = [[2025 Week 16]]
SORT file.name ASC
```

### Learnt Words
```dataviewjs
dv.table(
	["Learnt Word", "Meaning"],
	dv.pages('"02 Personal"')
	.filter(p => p["Learnt Word"] && p.week.path == "2025 Week 16")
	.sort(p => dv.date(p.file.name), 'asc')
	.flatMap(p =>
		Array.from(
			{
				length: Math.floor(
					p["Learnt Word"].length / 2
				)
			},
			(_, i) => [
				`${'**'}${p["Learnt Word"][i * 2]}${'**'}`,
				p["Learnt Word"][(i * 2) +1]
			]
		)
	)
)
```

### Weather
```dataview
TABLE WITHOUT ID
	file.link AS Day,
	weather AS ☁️,
	(temperature + " °C") AS 🌡️,
	(feels-like + " °C") AS 💭,
	wind-direction AS 🧭,
	(wind-speed + " km h⁻¹") AS 🍃,
	observed AS 🕓
FROM "02 Personal/02.01 Periodic Notes"
WHERE week = [[2025 Week 16]]
SORT file.name ASC
```