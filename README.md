# Irotahl

Obsidian vault and git repo for the world of Irotahl and every campaign set in it.

## First-Time Setup in Obsidian

1. **Open the vault:** Open folder as vault, then pick `D:\D&D\Irotahl`.
2. **Install community plugins:** Dataview, Templater, and Leaflet. Canvas is built in.
3. **Dataview settings:** turn on **Enable JavaScript Queries**. The DM Secrets dashboard needs it.
4. **Templater settings:** set **Template folder location** to `00_System/Templates`.
5. **Appearance settings:** under CSS snippets, make sure `callouts` is on. It colors the secret and read-aloud callouts.

## Conventions

- **Links:** use `[[wikilinks]]`. Note names should be unique across the vault.
- **Frontmatter:** every note has a `type` (npc, pc, location, faction, lore, item, adventure, session). Dataview queries depend on it.
- **DM secrets:** live inline in the note they belong to, as a callout:

  ```text
  > [!secret] Short title
  > revealed:: false
  > The secret itself.
  ```

  `00_System/Dashboards/DM Secrets.md` collects all of them and splits them into hidden and revealed.
- **Read-aloud text:** use `> [!readaloud]`.
- **Items:** fill in `base_item` with the official item being re-flavored. Write "homebrew" if the item is fully custom.

## Git

Commit after each prep session or lore change:

```bash
git add -A
git commit -m "Session 53 prep"
```

To back the vault up to GitHub later:

```bash
gh repo create irotahl --private --source=. --push
```
