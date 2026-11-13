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

## Workflow

1. **Discover:** Read `Design/總覽.md`, then only the specifications relevant to the task. Read frontmatter first to check `status`. If the overview is missing, locate documents by filename or search instead of reading `Design/` wholesale.
2. **Validate:** Identify confirmed rules, pending items, and conflicts.
3. **Organize:** Determine which document owns each rule; reuse existing documents where possible.
4. **Maintain:** Make only the requested specification changes and necessary dependent updates, including `Design/總覽.md` when documents are added, renamed, or removed.
5. **Verify:** Check terminology, conditions, cross-document references, and affected specifications.

Apply only the steps relevant to the task; do not scan the entire repository without a concrete reason.

## Pending Decisions

- Mark unresolved issues with the Obsidian tag `#待確認`, unless the project has an established convention. Find them by searching for `#待確認` rather than reading every document.
- Write the tag inline with the required decision and enough context to understand it, e.g. `#待確認 每日登入獎勵是否可補領？`.
- Keep pending issues in the responsible specification; do not create a parallel issue list.
- Remove the tag only when the user confirms the decision.
- If no responsible location exists, report the issue instead of inventing a document structure.

## Boundaries

- Respect established terminology, metadata, links, and document organization.
- Do not expand scope, invent future requirements, or modify unrelated files.
- Do not change Obsidian interface state or generated views unless requested.
- When only analysis or recommendations are requested, do not modify files.

## Completion

Briefly report changed documents, confirmed decisions incorporated, remaining `#待確認` items, affected references, and checks actually performed. Omit irrelevant items.
