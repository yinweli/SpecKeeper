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
- Use Obsidian by default: Wiki Links (`[[...]]`) for internal documents and Markdown Links for external URLs.
- Follow explicit project conventions when they differ from these defaults; do not restructure existing documents merely to enforce defaults.
- Keep overviews concise; maintain detailed rules in their responsible documents.
- Avoid duplicate specifications, unnecessary directories, and empty documents.

## Specification Authority

- Follow the project's designated authoritative specifications.
- Distinguish confirmed decisions from drafts, pending questions, historical records, and PoC findings.
- Never treat assumptions, proposals, or superseded information as approved requirements.
- Give each detailed rule one authoritative location; link to it rather than duplicating it.
- Identify conflicting rules and their sources. Do not silently choose, merge, or overwrite unresolved alternatives.
- Historical discussions provide context, not authority. Incorporate only confirmed, current decisions into specifications.

## Workflow

1. **Discover:** Read the relevant project conventions, overview, and authoritative specifications.
2. **Validate:** Identify confirmed rules, unresolved issues, and conflicts.
3. **Organize:** Determine which document owns each rule; reuse existing documents where possible.
4. **Maintain:** Make only the requested specification changes and necessary dependent updates.
5. **Verify:** Check terminology, conditions, cross-document references, and affected specifications.

Apply only the steps relevant to the task; do not scan the entire repository without a concrete reason.

## Pending Decisions

- Mark unresolved issues as `待確認` unless the project has an established convention.
- Record the required decision and enough context to understand it.
- Keep pending issues in the responsible specification when a suitable location exists.
- Do not create a parallel issue list or promote an unresolved item to a confirmed rule.
- If no responsible location exists, report the issue instead of inventing a document structure.

## Boundaries

- Respect established terminology, metadata, links, and document organization.
- Do not expand scope, invent future requirements, or modify unrelated files.
- Do not change Obsidian interface state or generated views unless requested.
- When only analysis or recommendations are requested, do not modify files.
- Do not claim to have performed checks that were not actually run.

## Completion

Briefly report changed documents, confirmed decisions incorporated, unresolved issues, affected references, and checks actually performed. Omit irrelevant items.
