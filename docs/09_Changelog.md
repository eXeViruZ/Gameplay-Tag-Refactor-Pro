# Changelog

## 1.0.0 — Initial Release

**Unreal Engine:** 5.8  
**Release type:** Initial Release  
**Release date:** Pending

### Release Summary

Gameplay Tag Refactor Pro v1.0 introduces a controlled Unreal Editor workflow for scanning Gameplay Tag usage, previewing rename impact, refactoring supported references, and verifying the saved result.

### Added

- Project-wide Gameplay Tag dictionary and usage scanning.
- Tag Tree, Tag Details, and per-tag Usage inspection.
- Semantic Blueprint graph Gameplay Tag detection.
- Impact Preview with READY/BLOCKED safety state.
- Automatically refactorable vs. manual-update reference classification.
- Controlled Gameplay Tag rename workflow.
- Automatic refactoring of supported direct `FGameplayTag` properties.
- Automatic refactoring of exact semantic `FGameplayTag` Blueprint pins.
- Physical backup, package save, post-save verification, and rollback/recovery safeguards.
- Five built-in Gameplay Tag audit rules focused on actionable project-owned findings.
- CSV usage export.
- JSON dictionary/usage/finding export (schema version 2).
- Scan progress/cancel UI.
- Unreal Editor toolbar quick launch.
- **Tools → Gameplay Tags → Gameplay Tag Refactor Pro** menu entry.

### Compatibility

- Unreal Engine 5.8.
- Editor-only plugin.
- Final packaged platform list pending final BuildPlugin/packaging validation.

### Known Limitations

- Automatic Blueprint graph mutation in v1.0 is limited to supported exact `FGameplayTag` pins.
- `FGameplayTagContainer` and `FGameplayTagQuery` Blueprint graph mutation are not included in v1.0.
- Dynamic/runtime-created usages are not guaranteed to be discoverable through serialized scanning.
- Arbitrary C++ source-code refactoring is not included.
- Unreal may require an editor restart after Gameplay Tag configuration changes.

Internal pre-release bugs are intentionally not listed as public Fixed items.

Previous: [Troubleshooting, FAQ & Limitations](08_Troubleshooting_And_FAQ.md) · [Documentation Index](INDEX.md)
