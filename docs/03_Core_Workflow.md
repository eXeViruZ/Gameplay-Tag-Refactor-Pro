# Core Workflow

Gameplay Tag Refactor Pro is built around a conservative rename workflow:

**Full Scan → Inspect Usages → Impact Preview → Rename → Verification**

## 1. Run Full Scan

Click **Run Full Scan** before planning a rename.

The scan refreshes:

- Gameplay Tag dictionary/tree data
- supported serialized property usages
- supported semantic Blueprint graph usages
- scan counts and detailed scan information

Use **Show Scan Details** for the technical breakdown.

## 2. Select the Source tag

Select an explicit Gameplay Tag in the **Tag Tree**.

The selected explicit tag can populate the **Source** field automatically.

Review **Tag Details** and **Usages** before changing anything.

## 3. Enter Target

Enter the desired new Gameplay Tag in **Target**.

Rename execution remains unavailable until the current Source/Target pair has a valid Impact Preview.

## 4. Preview Impact

Click **Preview Impact**.

The Preview can show:

- Source and Target
- definition source
- affected assets
- property references
- graph references
- automatically refactorable references
- manual update required references
- warnings and blockers
- backup / verification / rollback safety state

### READY

`Impact Preview: READY` means the currently detected supported reference set can proceed through the controlled rename path.

Warnings can still require review, for example when the Target already exists or Unreal will create a redirect.

### BLOCKED

A blocked Preview prevents execution.

Common causes include invalid inputs, stale Preview state, unsupported references, or another failed safety/preflight condition.

## 5. Execute Rename

When Preview is READY, click **Rename Tag**.

Supported v1.0 automatic refactoring includes:

- supported direct `FGameplayTag` properties
- exact semantic `FGameplayTag` Blueprint pins
- Gameplay Tag definition / redirect handling through Unreal's Gameplay Tag workflow

The controlled execution path also includes:

- physical backup
- fresh Source revalidation before mutation
- Blueprint compilation where required
- package save
- fresh post-save verification
- rollback/recovery safeguards when verified execution fails

## 6. Review Execution Result

A successful execution reports:

**Gameplay Tag rename completed successfully.**

Review:

- Changed assets
- Backup location
- Verification result
- Rollback result
- Errors
- Warnings

Normal success should show:

- Verification: **Passed**
- Rollback: **Not attempted**
- Errors: **none**

## 7. Restart when Unreal requests it

Unreal can display **Restart required to apply new settings** after a Gameplay Tag rename.

Use Unreal's normal restart flow.

## 8. Re-scan

After restart, run **Run Full Scan** again and verify the expected Target/redirect/reference state.

## Safe-use recommendations

- Use source control or an independent project backup for important projects.
- Run a fresh Full Scan before a rename.
- Do not execute from a stale Impact Preview.
- Review warnings before execution.
- Do not assume every runtime/dynamic tag usage can be discovered from serialized project data.

Previous: [Quick Start](02_Quick_Start.md) · [Documentation Index](INDEX.md) · Next: [Feature & Audit Reference](04_Reference.md)
