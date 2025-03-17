**# <%moment(tp.file.title).startOf('isoWeek').format("MMM DD")%> - <%moment(tp.file.title).endOf('isoWeek').format("MMM DD")%>

[[<% tp.date.now("YYYY-MM") %> | Plán na tento měsíc]] 

[[Calendar/Notes/Weekly/<%moment(tp.file.title).subtract(1,'week').format("gggg-[W]ww")%> |  Předchozí týden]] ⏪⏩ [[Calendar/Notes/Weekly/<%moment(tp.file.title).add(1,'week').format("gggg-[W]ww")%> | Příští týden]]

---
- [[Calendar/Notes/Daily/<%moment(tp.file.title).startOf('isoWeek').add(0,'day').format("YYYY-MM-DD")%> |Pondělí]]
- [[Calendar/Notes/Daily/<%moment(tp.file.title).startOf('isoWeek').add(1,'day').format("YYYY-MM-DD")%> |Úterý]]
- [[Calendar/Notes/Daily/<%moment(tp.file.title).startOf('isoWeek').add(2,'day').format("YYYY-MM-DD")%> |Středa]]
- [[Calendar/Notes/Daily/<%moment(tp.file.title).startOf('isoWeek').add(3,'day').format("YYYY-MM-DD")%> |Čtvrtek]]
- [[Calendar/Notes/Daily/<%moment(tp.file.title).startOf('isoWeek').add(4,'day').format("YYYY-MM-DD")%> |Pátek]]
- [[Calendar/Notes/Daily/<%moment(tp.file.title).startOf('isoWeek').add(5,'day').format("YYYY-MM-DD")%> |Sobota]]
- [[Calendar/Notes/Daily/<%moment(tp.file.title).startOf('isoWeek').add(6,'day').format("YYYY-MM-DD")%> |Neděle]]
---
# Co se zvládlo z minulého týdnu?
---
Jakým výzvám jsem čelil a jak jsem je překonal?

Co jsem se tento týden naučil?

**Jak jsem zvládl/a mé různé role a jak se cítím ohledně mého přístupu a chování v každé z nich?** (partner, syn, tiskař, tester, kamarád, ...)

# Co je v plánu na tento týden?
---
Jak se mohu zlepšit pro příští týden?

## Práce
- 

## Osobní život
- 

# Tracker
---

## Osobní přehled
---

```dataview  
TABLE WITHOUT ID  
	file.link as "Den",   
	mood AS "🌞",
	choice(sleep > 7, "🟩", "🟥") AS "💤", 
	choice(journal, "🟩", "🟥") AS "📓",
	choice(meditation, "🟩", "🟥") AS "🧘" 
FROM "Calendar/Notes/Daily"
where week = "<% moment(tp.file.title).format("gggg-[W]ww") %>"
SORT file.day ASC  
```
## Přehled návyků 
---
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
where week = "<% moment(tp.file.title).format("gggg-[W]ww") %>"
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
where week = "<% moment(tp.file.title).format("gggg-[W]ww") %>"
SORT file.day ASC  
```



