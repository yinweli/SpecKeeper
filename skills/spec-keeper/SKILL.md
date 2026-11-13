---
name: spec-keeper
description: >
  Use when creating, organizing, reviewing, or maintaining software design
  specification documents, including conflicts, pending decisions, and consistency
  across specifications. Not for general coding, debugging, or UI changes unless
  the task also involves specification documents.
---

# SpecKeeper

Maintain accurate, consistent, and authoritative software design specifications.

## Document Organization

- Store specifications in `Design/` by default.
- Place documents directly in `Design/` or in **one classification subdirectory** (e.g., `Design/會員/登入.md`). Do not create deeper classification directories.
- `Design/總覽.md` is the entry point: a concise index linking to each specification with a one-line purpose. Keep detailed rules in their responsible documents, not in the overview.
- Use Obsidian by default: Wiki Links (`[[...]]`) for internal documents and Markdown Links for external URLs.
- Follow explicit project conventions when they differ from these defaults; do not restructure existing documents merely to enforce defaults.
- Avoid unnecessary directories and empty documents.

## Document Status

Declare each specification's status in frontmatter:

```yaml
---
status: 定案   # 定案 | 草稿 | 歷史 | PoC
---
```

- Only `定案` documents are authoritative, unless the project designates authority differently.
- Treat a document without `status` as unconfirmed; do not assume it is `定案`.
- Set `status` on documents you create. Do not add or change `status` on existing documents unless requested; change to `定案` only when the user confirms.

## Specification Authority

- Never treat assumptions, proposals, drafts, history, or PoC findings as approved requirements.
- Give each detailed rule one authoritative location; link to it rather than duplicating it.
- Identify conflicting rules and their sources. Do not silently choose, merge, or overwrite unresolved alternatives.
- Incorporate only confirmed, current decisions into `定案` specifications; historical discussions provide context only.
- Write specifications as current rules only. Do not record change history, reasons for a change, or contrasts with superseded designs (e.g. 「不再區分 A 與 B」); remove superseded concepts entirely. Git keeps the history.

## Workflow

1. **Discover:** Read `Design/總覽.md`, then only the specifications relevant to the task. Read frontmatter first to check `status`. If the overview is missing, locate documents by filename or search instead of reading `Design/` wholesale.
2. **Validate:** Identify confirmed rules, pending items, and conflicts.
3. **Organize:** Determine which document owns each rule; reuse existing documents where possible.
4. **Maintain:** Make only the requested specification changes and necessary dependent updates, including `Design/總覽.md` when documents are added, renamed, or removed.
5. **Verify:** Check terminology, conditions, cross-document references, and affected specifications.

Apply only the steps relevant to the task; do not scan the entire repository without a concrete reason.

## Pending Decisions

- Record all unresolved issues in one central document, `Design/待決事項.md`, unless the project has an established name or convention. Create it when the first pending item needs recording.
- Group items by topic. Each item states the required decision with enough context to understand it, e.g. `- 待決：每日登入獎勵是否可補領？`.
- In the responsible specification, state only that the topic is undecided and link to the pending-decisions document; do not restate the pending item in full.
- Never write a pending item into a specification as if it were a confirmed rule.
- When the user confirms a decision, write it into the responsible specification and remove the item from the pending-decisions document.

## Boundaries

- Respect established terminology, metadata, links, and document organization.
- Do not expand scope, invent future requirements, or modify unrelated files.
- Do not change Obsidian interface state or generated views unless requested.
- When only analysis or recommendations are requested, do not modify files.

## Completion

Briefly report changed documents, confirmed decisions incorporated, remaining pending items, affected references, and checks actually performed. Omit irrelevant items.
