# Latin Meditations Guidelines

This repository contains shared guidelines for traditional Catholic Latin
meditation projects.

It is meant to be used as a Git submodule in concrete projects. The shared
guidelines define the common core: meditation form, Ecclesiastical Latin style,
citation discipline, source verification, and review practice. Each concrete
project should add a local project overlay for its own primary texts, metadata,
source witnesses, and required source families.

## Architecture

```text
latin-meditations-guidelines/
|-- guidelines/
|   |-- general-meditation-principles.md
|   |-- latin-style.md
|   |-- citation-style.md
|   |-- source-verification.md
|   |-- review-checklist.md
|   `-- project-overlay-guide.md
`-- skills/
    `-- latin-meditations-core/
        `-- SKILL.md
```

The intended order of authority is:

1. shared guidelines in this repository
2. local project overlay in the consuming project
3. concrete source files and existing meditations in the consuming project

Local project rules may specialize or tighten the shared rules. They should not
copy the shared rules wholesale.

## For New Projects

Read:

```text
guidelines/project-overlay-guide.md
```

Then create a local overlay in the consuming project, for example:

```text
planning/meditations-guidelines.md
skills/<project-meditation-skill>/SKILL.md
```

The local skill should be a project adapter: it points first to the shared core
skill and guidelines, then to the local overlay.
