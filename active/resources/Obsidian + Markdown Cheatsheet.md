---
properties: ---
date:
---
>[!tip]- Tips
>- This is a callout, types are below and specified in the brackets at the top: `![[Pasted image 20260629154834.png]]`
>- the "-" after the brackets means this will be closed by default
>- the text in the brackets determines the type
>- use templates! they can be super helpful for callouts, bases, for setting up notes with certain properties, or anything you use a lot
>- also, use hotkeys! they can be useful for templates
>- each vault is a totally separate environment so settings, plugins, etc don't transfer BUT if you want to share them you can copy the .obsidian folder from one vault into another and restart obsidian

---
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
etc

**Bold**
*Italic*
==highlight==
~~strikethrough~~


- bullet list
	- nested item
- etc

1. numbered list
2. 

- [ ] checklist
- [x] checked item
- [ ] etc


`[[backlink]]` <- wikilink (to any note in the vault)
`[Google.com](https://google.com)` <- link to webpage with custom text
`[[HRI2526|Display text here]]` <- wikilink with custom text


>[!notes] Plugins
>- Community plugins are made by obsidian users
>	- Tasks (allows scheduling tasks)
>	- Dataview
>- Core plugins are native to obsidian and can be toggled on and off in settings

embedded search:
```query
embed OR search
tag: #designs
content:("darrieus") 
```

inline base:
```base
views:
  - type: table
    name: Table
    filters:
      and:
        - file.tags.contains("#parameters")
        - Target.contains("reduce pulsation")
    order:
      - file.name
      - Target
      - Outcome
    sort:
      - property: file.name
        direction: ASC
    columnSize:
      file.name: 211
      note.Target: 183
  - type: cards
    name: Cards
  - type: list
    name: List
    indentProperties: true

```

## [[Dataview Basics]]

#maintenance 
