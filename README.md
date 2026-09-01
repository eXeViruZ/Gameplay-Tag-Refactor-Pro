# Gameplay Tag Refactor Pro

**Project-wide Gameplay Tag usage scanning, impact preview, safe refactoring, verification, auditing, and reporting for Unreal Engine.**

Gameplay Tag Refactor Pro helps you understand where Gameplay Tags are used before you change them. It combines a searchable tag tree, project-wide usage scanning, per-tag inspection, Impact Preview, controlled rename execution, backup and verification safeguards, audit rules, and CSV/JSON reporting in one editor-only Unreal Engine plugin.

| Product | Details |
|---|---|
| Version | 1.0.0 |
| Unreal Engine | 5.8 |
| Plugin Type | Editor-only C++ plugin |
| Runtime Gameplay Dependency | None |

## Main Features

- **Project-wide Gameplay Tag scan** — Build a current dictionary and usage index across the project.
- **Tag Tree & Tag Details** — Browse explicit/implicit tags, source information, hierarchy, children, and detected usage counts.
- **Per-tag Usage inspection** — Inspect supported serialized property and semantic Blueprint graph references.
- **Semantic Blueprint graph detection** — Detect real Gameplay Tag struct pins without treating generic dotted strings as tags.
- **Impact Preview** — Review Source, Target, affected assets, property references, graph references, warnings, blockers, and safety state before execution.
- **Controlled Rename** — Refactor supported direct `FGameplayTag` properties and exact semantic `FGameplayTag` Blueprint pins.
- **Safety workflow** — Physical backup, fresh source revalidation, package save, post-save verification, and rollback/recovery safeguards.
- **Actionable Audit** — Run five built-in rules focused on project-owned/config-defined Gameplay Tags rather than non-actionable engine/native noise.
- **CSV & JSON reports** — Export the current usage index and audit data for review or external workflows.
- **Editor integration** — Open GTRP from **Tools → Gameplay Tags → Gameplay Tag Refactor Pro** or from its quick-launch toolbar icon.

## Quick Start

1. Install and enable **Gameplay Tag Refactor Pro** for Unreal Engine 5.8.
2. Open **Tools → Gameplay Tags → Gameplay Tag Refactor Pro**, or use the toolbar icon.
3. Click **Run Full Scan**.
4. Select an explicit Gameplay Tag in the **Tag Tree** and inspect **Tag Details** and **Usages**.
5. Enter the desired Target tag and click **Preview Impact**.
6. Resolve blockers and review warnings.
7. When Preview is **READY**, click **Rename Tag**.
8. Review the execution result, verification status, changed assets, and backup location.
9. Restart Unreal Editor if Unreal requests it, then run a fresh scan.

For the complete workflow, start with [Quick Start](docs/02_Quick_Start.md) and [Core Workflow](docs/03_Core_Workflow.md).

## Documentation

- [Documentation Index](docs/INDEX.md)
- [Installation](docs/01_Installation.md)
- [Quick Start](docs/02_Quick_Start.md)
- [Core Workflow](docs/03_Core_Workflow.md)
- [Feature & Audit Reference](docs/04_Reference.md)
- [Project Settings](docs/05_Settings.md)
- [Reports & Exports](docs/06_Reports_Exports.md)
- [Safe Refactoring & Advanced Usage](docs/07_Advanced_Usage.md)
- [Troubleshooting, FAQ & Limitations](docs/08_Troubleshooting_And_FAQ.md)
- [Changelog](docs/09_Changelog.md)

## v1.0 Refactor Scope

| Reference type | Detection | Automatic v1.0 refactor |
|---|---:|---:|
| Supported direct `FGameplayTag` property | Yes | Yes |
| Exact semantic `FGameplayTag` Blueprint pin | Yes | Yes |
| `FGameplayTagContainer` / `FGameplayTagQuery` graph reference | Where semantically supported | No |
| Generic String/Name/Text that only resembles a tag | Not accepted as semantic tag usage | No |
| Dynamic/runtime-created usage | Not guaranteed | No |
| Arbitrary C++ source-code reference | No automatic source rewrite | No |

Unsupported detected references are handled conservatively and can block automatic execution rather than being silently ignored.

## Support

Discord is the primary channel for support, bug reports, and feature requests.

- [Hanke Unreal Tools Discord](https://discord.gg/vgpmnN6nCR)
- [GitHub Issues](https://github.com/eXeViruZ/Gameplay-Tag-Refactor-Pro/issues)
- [Email Support](mailto:Tom.Hanke.Official@web.de)

## Copyright

Copyright © 2026 Tom Leon Vincent Hanke. All rights reserved.
