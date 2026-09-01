# Quick Start

## Prerequisites

- GTRP is installed and enabled.
- The project runs Unreal Engine 5.8.
- The project contains registered Gameplay Tags.

## First scan

1. Open GTRP through **Tools → Gameplay Tags → Gameplay Tag Refactor Pro**, or click the GTRP toolbar icon.
2. Click **Run Full Scan**.
3. Wait for the scan to complete. The progress dialog can be cancelled if needed.
4. Review the compact scan summary.
5. Expand a namespace in **Tag Tree**.
6. Select a Gameplay Tag.
7. Review **Tag Details**.
8. Open **Usages** to inspect supported references for the selected tag.
9. Optionally click **Run Audit**.
10. Use **Export CSV** or **Export JSON** if you need an external report.

## Expected result

After a successful scan you should see:

- A populated **Tag Tree**.
- Current tag, usage, processed-asset, and duration counts.
- **Tag Details** for the selected tag.
- Usage rows when supported references exist.

If no supported usage exists for the selected tag, GTRP displays:

**No usages found for this tag.**

## Next step

Before performing your first rename, read [Core Workflow](03_Core_Workflow.md).

Previous: [Installation](01_Installation.md) · [Documentation Index](INDEX.md) · Next: [Core Workflow](03_Core_Workflow.md)
