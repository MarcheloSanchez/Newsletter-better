---
up: 
related:
  - "[[Dataview syntax]]"
created: 2024-12-11
tags:
  - note/cheatsheet
URLs:
  - https://github.com/mulfok/periodic-note-templates/blob/main/Weekly%20Note%20Template.md
  - https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Examples.md
---


```chart
type: line
labels: [Pondělí, Úterý, Středa, Čtvrtek, Pátek, Sobota, Neděle]
series:
  - title: mood
    data: [1,2,3,4,5,6,7,8,9,10]
tension: 0.2
width: 80%
labelColors: false
fill: false
beginAtZero: false
bestFit: true
bestFitTitle: undefined
bestFitNumber: 0
```

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

const date = "<% tp.date.now('YYYY-MM-DD') %>";

customJS.DvCharts.renderWeeklyChart({
	dv,
	context: this,
	daysPath: 'Calendar/Notes/Daily/<% tp.date.now("YYYY") %>/Daily/<%tp.date.now("MM MMMM")%>',
	attributes,
	type: 'average',
	date
})
```

# Nápady pro zlepšení

``` tracker
searchType: frontmatter
searchTarget: journal 
folder: Calendar/Notes/Daily
datasetName: journal 
summary: 
    template: "Nejdelší řada zapisování deníku: {{maxStreak()}} day(s)\nNejdelší pauza zapisování: {{maxBreaks()}} day(s)\nPoslední záznam zápisu: {{currentStreak()}} day(s)"
```

## Funkce pro sledování návyků - analýza, přehled 
X
``` tracker
searchType: frontmatter
searchTarget: journal 
folder: Calendar/Notes/Daily
datasetName: journal 
startDate: 2024-01-01
summary:
    template: 'Počet záznamu v zápisech: {{numDaysHavingData()::i}}'
```
X
``` tracker
searchType: frontmatter
searchTarget: journal 
folder: Calendar/Notes/Daily
startDate: 2024-01-01
summary:
    template: 'Maximální počet dní: {{numDays()::i}}'
```
X
``` tracker
searchType: frontmatter
searchTarget: journal 
folder: Calendar/Notes/Daily
datasetName: journal 
startDate: 2024-01-01
summary:
    template: "Počet záznamu v zápisech: {{numDaysHavingData()::i}} <-- Maximální počet dní: {{numDays()::i}}"
```
X
``` tracker
searchType: frontmatter
searchTarget: povlečení 
folder: Calendar/Notes/Daily
datasetName: povlečení
summary: 
    template: "Nejdelší řada zapisování deníku: {{maxStreak()}} day(s)\nNejdelší pauza zapisování: {{maxBreaks()}} day(s)\nPoslední záznam zápisu: {{currentStreak()}} day(s)"
```



# NEW
- DONE

``` tracker
searchType: frontmatter
searchTarget: sleep1[0], sleep1[1]
folder: Calendar/Notes/Daily
datasetName: spát, vstávat
startDate: 2024-04-01
endDate: 2024-04-28
line:
    title: Spánek
    lineColor: yellow, red
	yAxisLabel: čas
    showLegend: true
    legendPosition: bottom
```
## Kalendář pro návyky
X
``` tracker
searchType: frontmatter
searchTarget: journal, gaming
datasetName: PushUp, Meditation
folder: Calendar/Notes/Daily
month:
    mode: annotation
    startWeekOn: 'Mon'
    threshold: 0, 0
    color: green
    headerMonthColor: orange
    dimNotInMonth: false
    annotation: 💪, 🧘‍♂️
    showAnnotationOfAllTargets: true
```
X
``` tracker
searchType: frontmatter
searchTarget: read, gaming 
datasetName: Čtení, Gaming 
folder: Calendar/Notes/Daily
month:
    mode: annotation
    startWeekOn: 'Mon'
    threshold: 0, 0
    color: green
    headerMonthColor: orange
    dimNotInMonth: false
    annotation: 📖, 🎮
    showAnnotationOfAllTargets: false
```
X
``` tracker
searchType: frontmatter
searchTarget: read, gaming 
datasetName: Čtení, Gaming 
folder: Calendar/Notes/Daily
month:
    mode: annotation
    startWeekOn: 'Mon'
    threshold: 0, 0
    color: green
    headerMonthColor: orange
    dimNotInMonth: false
    annotation: 📖, 🎮
    showAnnotationOfAllTargets: false
```
X
``` tracker
searchType: frontmatter
searchTarget: read, gaming 
datasetName: Čtení, Gaming 
folder: Calendar/Notes/Daily
month:
    dataset: 0, 1
    startWeekOn: 'Mon'
    threshold: 0, 0
    color: green
    headerMonthColor: orange
    dimNotInMonth: false
    todayRingColor: orange
    selectedRingColor: steelblue
    circleColorByValue: true
    showSelectedValue: true
```
X - BEST 
``` tracker
searchType: frontmatter
searchTarget: read, gaming 
datasetName: Čtení, Gaming 
folder: Calendar/Notes/Daily
month:
    dataset: 0, 1
    startWeekOn: 'Mon'
    threshold: 0, 0
    color: green
    headerMonthColor: orange
    dimNotInMonth: true
    todayRingColor: orange
    selectedRingColor: steelblue
    showSelectedValue: true
```
X - BEST, pro domácnost
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
# LINE GRAPH
```tracker
searchType: frontmatter
searchTarget: mood
folder: Calendar/Notes/Daily
startDate: 2024-04-01
endDate: 2024-04-28
textValueMap:
    😀: 10
    😀: 9
    🙂: 8
    🙂: 7
    😐: 6
    😐: 5
    🙁: 4
    🙁: 3
    😞: 2
	😞: 1    
line:
    title: "Mood"
    yAxisLabel: Mood
    lineColor: "#d65d0e"
    yAxisTickInterval: 1
    yAxisTickLabelFormat: i
    yMin: 0
```
x
```tracker
searchType: frontmatter
searchTarget: journal
folder: Calendar/Notes/Daily
startDate: 2024-03-21
endDate: 2024-03-28 
line:
    title: "Journal"
    yAxisLabel: Journal
    lineColor: "#d65d0e"
    yAxisTickInterval: 1
    yAxisTickLabelFormat: i
    yMin: 0
```

# Bulet GRAF meter

```tracker
searchType: frontmatter
searchTarget: flextraining
folder: Calendar/Notes/Daily
endDate: 2024-04-28
fixedScale: 1.1
bullet:
    title: "Protahování se"
    dataset: 0
    orientation: horizontal
    range: 10, 20, 40
    rangeColor: darkgray, silver, lightgray
    value: "{{currentBreaks()}}"
    valueUnit: kolikrát
    valueColor: '#69b3a2'
    showMarker: true
    markerValue: 24
    markerColor: black
```

```tracker
searchType: frontmatter
searchTarget: flextraining
folder: Calendar/Notes/Daily
endDate: 2024-04-28
bullet:
    title: "Meditation"
    dataset: 0
    orientation: vertical
    range: 30, 60, 100
    rangeColor: darkgray, silver, lightgray
    value: "{{sum()}}"
    valueUnit: times
    valueColor: steelblue
    showMarker: true
    markerValue: 80
    markerColor: red
```