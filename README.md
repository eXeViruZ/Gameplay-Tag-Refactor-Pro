# Gameplay Tag Refactor Pro

**Project-wide Gameplay Tag usage scanning, impact preview, safe refactoring, verification, auditing, and reporting for Unreal Engine.**

Gameplay Tag Refactor Pro helps you understand where Gameplay Tags are used before you change them. It combines a searchable tag tree, project-wide usage scanning, per-tag inspection, Impact Preview, controlled rename execution, backup and verification safeguards, audit rules, and CSV/JSON reporting in one editor-only Unreal Engine plugin.

[Watch the Gameplay Tag Refactor Pro product showcase on YouTube](https://youtu.be/cwRiiMac3x0)

| Product | Details |
|---|---|
| Version | 1.0.0 |
| Unreal Engine | 5.8 |
| Plugin Type | Editor-only C++ plugin |
| Required Editor Dependency | Epic's built-in `GameplayTagsEditor` plugin |
| Runtime Gameplay Dependency | None |

> **Dependency:** GTRP requires Epic's built-in **GameplayTagsEditor** plugin, included with Unreal Engine 5.8. GTRP uses its editor-side Gameplay Tag APIs for the controlled rename workflow. This dependency is editor-only and does not add a runtime gameplay dependency.

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
2. Confirm Epic's built-in **GameplayTagsEditor** plugin is enabled for the project.
3. Open **Tools → Gameplay Tags → Gameplay Tag Refactor Pro**, or use the toolbar icon.
4. Click **Run Full Scan**.
5. Select an explicit Gameplay Tag in the **Tag Tree** and inspect **Tag Details** and **Usages**.
6. Enter the desired Target tag and click **Preview Impact**.
7. Resolve blockers and review warnings.
8. When Preview is **READY**, click **Rename Tag**.
9. Review the execution result, verification status, changed assets, and backup location.
10. Restart Unreal Editor if Unreal requests it, then run a fresh scan.

> **Scan performance:** The first Full Scan after starting Unreal Editor can take noticeably longer while project assets and editor-side data are loaded and cached. Subsequent scans during the same editor session are typically faster. Scan time depends on project size, asset count, and editor state.

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
