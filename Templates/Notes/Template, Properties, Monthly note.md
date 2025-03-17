

[[Calendar/Notes/Monthly/<%moment(tp.file.title).subtract(1,'month').format("YYYY-MM") %> | Minulý měsíc]] ⏪⏩ [[Calendar/Notes/Monthly/<%moment(tp.file.title).add(1,'month').format("YYYY-MM") %> | Příští měsíc]]

[[Calendar/Notes/Weekly/<%moment(tp.file.title).format("gggg-[W]ww", 0) %> | ① První týden]]
[[Calendar/Notes/Weekly/<%moment(tp.file.title).add(1,'week').format("gggg-[W]ww", 7) %> | ② Druhý týden]]
[[Calendar/Notes/Weekly/<%moment(tp.file.title).add(2,'week').format("gggg-[W]ww", 14) %> | ③ Třetí týden]]
[[Calendar/Notes/Weekly/<%moment(tp.file.title).add(3,'week').format("gggg-[W]ww", 21) %> | ④ Čtvrtý týden]]

---
# Tracker
[[Tracker návyků]]
[[Plánované aktivity]]

## Graf

``` tracker
searchType: frontmatter
searchTarget: sleepschedule[0], sleepschedule[1]
folder: Calendar/Notes/Daily
datasetName: spát, vstávat
startDate: <%moment(tp.file.title).startOf('month').format("YYYY-MM-DD")%>
endDate: <%moment(tp.file.title).endOf('month').format("YYYY-MM-DD")%>
line:
    title: Spánek
    lineColor: yellow, red
	yAxisLabel: čas
    showLegend: true
    legendPosition: bottom
```

``` tracker
searchType: frontmatter
searchTarget: watering, vytírání, prach, pračka, povlečení, ručníky, okna, odpadky 
datasetName: Watering, Vytírání, Prach, Pračka, Povlečení, Ručníky, Okna, Odpadky  
folder: Calendar/Notes/Daily
month:
    startWeekOn: 'Mon'
    color: green
    headerMonthColor: orange
    dimNotInMonth: true
    todayRingColor: orange
    selectedRingColor: steelblue
    showSelectedValue: true
```

## Osobní přehled

```dataview  
TABLE WITHOUT ID  
	file.link as "Den",   
	mood AS "🌞",
	choice(sleep > 7, "🟩", "🟥") AS "💤", 
	choice(journal, "🟩", "🟥") AS "📓",
	choice(meditation, "🟩", "🟥") AS "🧘" 
FROM "Calendar/Notes/Daily"
WHERE week = "<% tp.date.now("gggg-[W]ww") %>" OR week = "<% tp.date.now("gggg-[W]ww", 1) %>" OR week = "<% tp.date.now("gggg-[W]ww", 2) %>" OR week = "<% tp.date.now("gggg-[W]ww", 3) %>"
SORT file.day ASC  
```

## Přehled návyků 
```dataview  
TABLE WITHOUT ID  
	file.link as "Den",   
	choice(flextraining, "🟩", "🟥") AS "🤸",
	choice(gaming < 4, "🟩", "🟥") AS "🎮", 
	choice(commskills, "🟩", "🟥") AS "🔊",
	workout AS "💪", 
	printed AS "🖨️",
	choice(AI, "🟩", "🟥") AS "🤖" 
FROM "Calendar/Notes/Daily"
WHERE week = "<% tp.date.now("gggg-[W]ww") %>" OR week = "<% tp.date.now("gggg-[W]ww", 1) %>" OR week = "<% tp.date.now("gggg-[W]ww", 2) %>" OR week = "<% tp.date.now("gggg-[W]ww", 3) %>"
SORT file.day ASC  
```

## Domácnost
---
```dataview  
TABLE WITHOUT ID  
	file.link as "Den",   
	choice(watering, "🟩", "🟥") AS "🌻",
	choice(photopurge, "🟩", "🟥") AS "🛑📷",
	choice(povlečení, "🟩", "🟥") AS "🛏️",
	choice(vytírání, "🟩", "🟥") AS "🧹💦",
	choice(vysávání, "🟩", "🟥") AS "🧹🌫️",
	choice(prach, "🟩", "🟥") AS "🌫️",
	choice(pračka, "🟩", "🟥") AS "🫧",
	choice(nádobí, "🟩", "🟥") AS "🍽️",	
	choice(okna, "🟩", "🟥") AS "🪟",
	choice(odpadky, "🟩", "🟥") AS "🚮",
	choice(ručníky, "🟩", "🟥") AS "💦"
FROM "Calendar/Notes/Daily"
WHERE week = "<% tp.date.now("gggg-[W]ww") %>" OR week = "<% tp.date.now("gggg-[W]ww", 1) %>" OR week = "<% tp.date.now("gggg-[W]ww", 2) %>" OR week = "<% tp.date.now("gggg-[W]ww", 3) %>"
SORT file.day ASC  
```
