# Troubleshooting, FAQ & Limitations

## GTRP does not appear in the editor

1. Open **Edit → Plugins**.
2. Search for **Gameplay Tag Refactor Pro**.
3. Enable it.
4. Restart Unreal Editor if prompted.
5. Open **Tools → Gameplay Tags → Gameplay Tag Refactor Pro**.

## Full Scan takes a noticeable amount of time

The first Full Scan after starting Unreal Editor can take noticeably longer because project assets and editor-side data may need to be loaded and cached.

Subsequent Full Scans during the same editor session are typically faster. Scan time depends on project size, asset count, and the current editor state.

This is expected behavior and does not mean every scan in the same editor session will take as long as the initial cold scan.

Use the progress dialog and **Cancel** if necessary. Run a fresh Full Scan before an actual rename.

## A tag shows zero Usages

Possible reasons:

- no supported serialized usage was found
- the tag is used dynamically/runtime-only
- an implicit parent was selected instead of a used explicit leaf tag

Run a fresh Full Scan and confirm the exact selected tag.

## Preview is BLOCKED

Check Source and Target, run **Preview Impact** again, and review the displayed blocker/manual-reference information.

GTRP keeps Rename disabled when the current execution cannot be safely supported.

## Preview is stale

Click **Preview Impact** again for the current Source/Target pair.

## Unreal requests a restart after Rename

Use Unreal's normal restart flow after reviewing the GTRP result. Then run a fresh Full Scan.

## Export file location

Verified defaults:

- `Saved/GTP_Usages.csv`
- `Saved/GTP_Report.json`

## Known limitations

### Unreal Engine 5.8 only
GTRP v1.0 targets Unreal Engine 5.8.

### Automatic refactor scope is intentionally narrow
v1.0 automatically refactors supported direct `FGameplayTag` properties and exact semantic `FGameplayTag` Blueprint pins.

### `FGameplayTagContainer` and `FGameplayTagQuery` graph mutation
These are not part of the v1.0 automatic Blueprint graph mutation scope.

### Dynamic/runtime-created usage
Serialized scanning cannot guarantee discovery of every runtime-generated or code-driven usage.

### C++ source-code refactoring
v1.0 does not automatically rewrite arbitrary C++ source references.

### Generic dotted strings are not treated as Gameplay Tags
A generic dotted String/Name/Text value is not accepted merely because it resembles a Gameplay Tag. GTRP requires semantic Gameplay Tag evidence for supported graph usage detection.

### Audit focuses on actionable project-owned findings
Native/engine-defined tags are excluded from the v1.0 missing-comment and no-supported-usage rules where those findings would not be customer-actionable.

## FAQ

### Why can the first Full Scan take longer?
The first Full Scan after starting Unreal Editor can take longer because project assets and editor-side data may need to be loaded and cached. Subsequent scans during the same editor session are typically faster. Scan time depends on project size, asset count, and the current editor state.

### Does GTRP rewrite every Gameplay Tag reference?
No. v1.0 automatically refactors confirmed supported exact reference types.

### Are exact Blueprint `FGameplayTag` pins supported?
Yes, when they satisfy exact locator/type/freshness checks.

### Are `FGameplayTagContainer` or `FGameplayTagQuery` Blueprint graph mutations supported?
No, not for automatic v1.0 graph mutation.

### Are all dynamic/runtime usages guaranteed to be found?
No.

### Where can I get support?

- [Hanke Unreal Tools Discord](https://discord.gg/vgpmnN6nCR)
- [GitHub Issues](https://github.com/eXeViruZ/Gameplay-Tag-Refactor-Pro/issues)
- [Email Support](mailto:Tom.Hanke.Official@web.de)

Previous: [Safe Refactoring & Advanced Usage](07_Advanced_Usage.md) · [Documentation Index](INDEX.md) · Next: [Changelog](09_Changelog.md)
