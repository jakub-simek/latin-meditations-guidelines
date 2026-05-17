# Project Overlay Guide

This guide explains how a concrete meditation project should combine the shared
Latin meditation guidelines with project-specific rules.

The goal is consistency without forcing every project into the same source
model. A liturgical project, a Bernard of Clairvaux project, an Alphonsus
project, and a Marian anthology project may all share the same Latin and
citation discipline while differing in primary texts, source witnesses, metadata,
and required supporting authorities.

## Core and Overlay Model

Use this order:

1. Shared core guidelines from this repository.
2. Local project overlay in the consuming project.
3. The concrete source witness, metadata files, and existing meditations of the
   consuming project.

The shared core answers questions such as:

- What kind of meditation is this?
- What kind of Latin style is expected?
- How are direct quotations and paraphrases handled?
- How are sources verified?
- What belongs in a final review?

The local overlay answers questions such as:

- What is the primary text in this project?
- Where are source witnesses stored?
- Which metadata fields are required?
- Which source families are obligatory, optional, or inappropriate?
- What citation locator should be used after the first full reference?
- Which project files must be checked before writing?

## What Belongs in the Shared Core

Keep these rules in the shared repository:

- classical discursive and contemplative form
- Ecclesiastical Latin style and orthography
- direct quotation and paraphrase discipline
- source verification principles
- general Marian integration
- final Latin correction pass
- general review checklist

Do not move project-specific file paths, metadata schemas, or source corpora into
the shared core.

## What Belongs in a Project Overlay

Each consuming project should define a local overlay. A normal location is:

```text
planning/meditations-guidelines.md
```

The overlay should include only rules needed by that project.

Recommended sections:

```text
# <Project> Meditation Guidelines

## Scope
## Source Order
## Primary Texts
## Metadata
## Citation Locators
## Required Source Families
## Project-Specific Review Checklist
```

### Scope

Define the project and its normal meditation object.

Examples:

- A liturgical project may meditate on Mass or Office texts.
- A Bernard project may meditate on one sermon or a passage from a sermon.
- An Alphonsus project may meditate directly on a chapter of `Le glorie di
  Maria`, `Pratica di amar Gesu Cristo`, or `Massime eterne`.

### Source Order

State what the agent or editor must read before writing.

Examples:

- normalized index file
- source witness in a submodule
- existing meditations on the same feast, sermon, chapter, or theme
- local bibliography or edition notes

### Primary Texts

Define how the `Textus fundamentalis` is chosen and quoted.

For example:

- entire liturgical chant or reading
- a paragraph from a sermon
- one numbered maxim
- a chapter excerpt

If a project does not use liturgical context, say so explicitly.

### Metadata

Define required front matter or metadata fields.

Examples:

```yaml
---
id: meditatio-example
title: "Meditatio ..."
primary_source: ../sources/example.md#section
primary_incipit: "..."
status: draft
---
```

Liturgical projects may need celebration IDs and liturgical form. Textual
projects may instead need author, work, book, chapter, sermon, section, or
edition witness.

### Citation Locators

Define the local form for source references.

The shared rule is:

- first reference to the primary text gives the full project-required reference
- later quotations from the same primary text may use a shorter locator

The project overlay must define what that shorter locator is.

Examples:

- biblical locus: `(Act 1,7)`
- sermon and section: `(Sermo 83, 4)`
- chapter and number: `(cap. I, n. 1)`
- maxim number: `(Maxima 12)`

### Required Source Families

Define which supporting sources are required, preferred, optional, or normally
avoided.

Examples:

- A liturgical project may require Scripture, Fathers, scholastic theology,
  Catechismus Romanus, St. Alphonsus, and a Marian component.
- A Bernard project may make Bernard the primary voice and use Scripture and
  patristic parallels as supporting witnesses.
- A project on `Le glorie di Maria` may treat Alphonsus as the primary text,
  not as an added ascetical authority.
- A project on `Massime eterne` may require eschatological, ascetical, and
  moral-theological sources, but no liturgical context.

Do not blindly inherit another project's required source families.

### Project-Specific Review Checklist

Add checks that cannot live in the shared core.

Examples:

- required metadata fields are present
- primary source anchor exists
- related meditations have been checked
- project-specific edition rules have been followed
- local citation locator style is consistent

## Skill Pattern

Each project should have a local adapter skill. It should not duplicate the
shared guidelines. It should point to:

1. the shared core skill
2. the shared guideline files needed for the task
3. the local project overlay
4. the project-specific source and metadata files

Template:

```markdown
---
name: <project-meditation-skill>
description: Use this skill when creating, revising, reviewing, or adding
metadata for <project> Latin meditations. It applies the shared Latin
meditation guidelines plus the local <project> overlay.
---

# <Project> Meditation Skill

## Source of Truth

Read:

- `../../shared/latin-meditations-guidelines/skills/latin-meditations-core/SKILL.md`
- relevant files in `../../shared/latin-meditations-guidelines/guidelines/`
- `../../planning/meditations-guidelines.md`

Local rules override the shared rules when they are stricter or more concrete.

## Workflow

1. Identify the primary text.
2. Read the local source witness.
3. Check required project metadata and related meditations.
4. Compose or revise according to the shared guidelines plus local overlay.
5. Verify quotations, `cf.` references, source locators, and original-language
   rules.
6. Make the final Latin correction pass.
```

Adjust relative paths to the actual skill location.

## Submodule Pattern

A consuming project may add this repository as:

```bash
git submodule add -b main git@github.com:jakub-simek/latin-meditations-guidelines.git shared/latin-meditations-guidelines
```

Recommended location:

```text
shared/latin-meditations-guidelines/
```

Use another location only if the project has a clear convention for shared
cross-project material.
