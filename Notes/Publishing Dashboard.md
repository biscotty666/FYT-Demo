---
action: true
type:
  - canvas
status: 20
related: 
created: 2023-08-26 Sat
last edit: 2023-08-26 Sat
cssclasses: 
---
%%
topic:: [[Projects]]
%%
# Publishing Dashboard

## Unfinished

```dataviewjs
const {fieldModifier: f} = this.app.plugins.plugins["metadata-menu"].api;

dv.table(["Title", "Type", "Stage", "Last Edited"],
	await Promise.all(dv.pages('')
	.where(t => ((t["type"] == "article") || (t["type"] == "video") || (t["type"] == "script")) && t["Published"] == false && t["Stage"] != "final")
	.sort(d => d["last edit"])
	.map(async p => [
		p.file.link,
		p.type,
		await f(dv, p, "Stage"),
		await f(dv, p, "last edit"),
	])
))
```

## Published

```dataviewjs
const {fieldModifier: f} = this.app.plugins.plugins["metadata-menu"].api;

dv.table(["Title", "Type", "PubDate","Outlet"],
	await Promise.all(dv.pages('')
	.where(t => ((t["type"] == "article") || t["type"] == "video") && t["Published"] == true)
	.sort(d=>d.PubDate, "desc")
  .map(async p => [
		p.file.link,
		p.type,
		await f(dv, p, "PubDate"),
		await f(dv, p, "Published to"),
	])
))
```

## Unpublished

```dataviewjs
const {fieldModifier: f} = this.app.plugins.plugins["metadata-menu"].api;

dv.table(["Title", "Project", "Item Action", "Notes", "Type"],
	await Promise.all(dv.pages('')
	.where(t => ((t["type"] == "article") || t["type"] == "video") && t["action"] == true)
	.sort(d=>d.file.link)
	.sort(d=>d.type)
  .map(async p => [
		p.file.link,
		await f(dv, p, "Project Name"),
		await f(dv, p, "Item Action"),
		await f(dv, p, "Item Notes"),
		p.type,
	])
))
```



