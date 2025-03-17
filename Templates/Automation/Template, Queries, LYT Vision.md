# LYT Vision
---

> [!Cone] This is must have - Basic navigation through structured notes 

Activate "LYT Vision" to resurface thoughts in context. When you twirl this open, it's like you are putting on night vision goggles: you see things hidden in the shadows.

> [!Venetian]+ Unrequited notes
> These notes point directly to this note. But this note doesn't point back (yet). This is the strongest contextual query. **Outlinks + Tags**.
> 
> ```dataview
> LIST
> 
> FROM SOURCE
> and !outgoing(SOURCE)
> and -#map
> 
> SORT file.mtime desc
> ```

> [!Venetian]- Unmentioned notes in common
> These notes share the tag `#concept` and are not mentioned above.
> 
> ```dataview
> LIST
> 
> FROM x#TAG
> and !outgoing(Concepts Map)
> 
> SORT file.name asc
> ```

---

Back to: [[Home]]