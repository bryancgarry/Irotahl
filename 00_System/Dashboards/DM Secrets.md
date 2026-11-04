---
type: dashboard
tags: [dashboard]
---
# DM Secrets

Every `> [!secret]` callout in the vault, pulled from the notes they live in. When a secret comes out at the table, change `revealed:: false` to `revealed:: true` in its note.

To add one anywhere, insert the **Secret** template, or type:

```text
> [!secret] Short title
> revealed:: false
> The secret itself.
```

```dataviewjs
const secretPattern = /^> \[!secret\][-+]?[ \t]*(.*)\r?\n((?:>.*(?:\r?\n|$))*)/gm;
const hidden = [];
const revealed = [];

for (const page of dv.pages('-"00_System"')) {
  const text = await dv.io.load(page.file.path);
  for (const match of text.matchAll(secretPattern)) {
    const row = [page.file.link, match[1].trim() || "(untitled)"];
    if (/revealed::\s*true/i.test(match[2])) revealed.push(row);
    else hidden.push(row);
  }
}

dv.header(2, `Hidden (${hidden.length})`);
dv.table(["Note", "Secret"], hidden);
dv.header(2, `Revealed (${revealed.length})`);
dv.table(["Note", "Secret"], revealed);
```
