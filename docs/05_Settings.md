# Project Settings

Gameplay Tag Refactor Pro exposes its customer-facing settings under:

`Edit → Project Settings → Plugins → Gameplay Tag Refactor Pro`

GTRP v1.0 intentionally exposes only settings that are connected to active production behavior.

## Max Hierarchy Depth

**Max Hierarchy Depth** controls when audit rule **GTR015 — Deep Hierarchy** reports a Gameplay Tag hierarchy as too deep.

- Default: `8`
- Minimum: `1`
- Maximum: `20`
- Used by: `GTR015`

A tag hierarchy deeper than the configured value can produce a GTR015 audit finding.

Use a lower value when your project deliberately enforces a flatter Gameplay Tag hierarchy. Use a higher value when deeper namespaces are an intentional part of your project structure.

## Max Children Per Parent

**Max Children Per Parent** controls when audit rule **GTR108 — Broad Root / High Child Count** reports that a tag parent has too many direct children.

- Default: `50`
- Minimum: `1`
- Maximum: `500`
- Used by: `GTR108`

A parent with more direct children than the configured value can produce a GTR108 audit finding.

Use a lower value when you want narrower namespaces. Use a higher value when broad tag groups are intentional for your project.

## Persistence

The settings are provided by `UGTPDeveloperSettings` using Unreal Engine's editor configuration workflow.

Changes made through Project Settings are intended to persist through Unreal's normal config/default-config system for the project.

## v1.0 public settings scope

Only these two active settings are exposed publicly in GTRP v1.0:

| Setting | Default | Range | Audit Rule |
|---|---:|---:|---|
| Max Hierarchy Depth | 8 | 1–20 | GTR015 |
| Max Children Per Parent | 50 | 1–500 | GTR108 |

Earlier development-only/inactive policy fields are not exposed as customer settings in v1.0 because they are not connected to production behavior.

## Recommended workflow

1. Open **Edit → Project Settings → Plugins → Gameplay Tag Refactor Pro**.
2. Adjust the thresholds only if the defaults do not fit your project's tag structure.
3. Run **Run Full Scan** in GTRP.
4. Run **Run Audit**.
5. Review any GTR015 or GTR108 findings against the thresholds you configured.

Previous: [Feature & Audit Reference](04_Reference.md) · [Documentation Index](INDEX.md) · Next: [Reports & Exports](06_Reports_Exports.md)
