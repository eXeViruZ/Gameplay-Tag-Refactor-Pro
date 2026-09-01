# Safe Refactoring & Advanced Usage

GTRP v1.0 is an editor workflow tool rather than a commandlet/API automation product.

## Recommended production workflow

1. Sync/update the project.
2. Start from a known-good source-control state.
3. Open GTRP and run **Run Full Scan**.
4. Inspect the Source tag and its Usages.
5. Enter Target.
6. Run **Preview Impact**.
7. Resolve blockers.
8. Review warnings.
9. Execute **Rename Tag** only when Preview is READY.
10. Review the execution result and verification.
11. Restart Unreal if requested.
12. Run a fresh Full Scan.
13. Review the resulting project diff before commit.

## Source control guidance

GTRP includes execution safeguards, but source control remains your project-level safety net.

Recommended:

- Avoid unrelated local edits in the same affected assets before a large refactor.
- Review changed `.uasset` and config files after execution.
- Commit tag refactors separately when practical.
- Keep the GTRP-generated backup until the change has been reviewed.

## Exact Blueprint pin refactoring

v1.0 can automatically rewrite exact semantic `FGameplayTag` Blueprint pins when GTRP can freshly resolve the Blueprint, graph, node, and pin and confirm the current raw Source value before mutation.

The workflow is intentionally fail-closed:

- exact locator required
- exact semantic `FGameplayTag` type required
- current Source value is revalidated before mutation
- Blueprint is compiled where required
- package is saved through Unreal's editor save path
- the saved pin is freshly re-resolved and verified

This is intentionally narrower than "rewrite every possible Gameplay Tag-related Blueprint value."

## Unsupported references

Preview distinguishes:

- Automatically refactorable
- Manual update required

Unsupported references can block execution rather than being silently ignored.

## Large projects

Full Scan duration depends on project size, asset count, and serialized/Blueprint data.

Use the progress dialog and cancel control as needed. A fresh Full Scan is most important immediately before an actual refactor.

Previous: [Reports & Exports](06_Reports_Exports.md) · [Documentation Index](INDEX.md) · Next: [Troubleshooting, FAQ & Limitations](08_Troubleshooting_And_FAQ.md)
