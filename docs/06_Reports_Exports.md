# Reports & Exports

Gameplay Tag Refactor Pro can export the current scan and audit state to CSV and JSON.

## CSV export

Click **Export CSV**.

Verified default output:

`Saved/GTP_Usages.csv`

The CSV exports the current committed usage records.

Typical information includes:

- Tag name
- Asset path
- Asset class
- Property or graph locator
- Container/reference type
- Source adapter
- Blueprint graph/node/pin information when applicable

The main window reports export success after the file is written.

## JSON export

Click **Export JSON**.

Verified default output:

`Saved/GTP_Report.json`

Current v1.0 schema version:

`2`

Top-level groups:

- `dictionary`
- `usages`
- `findings`

### Dictionary data

Publicly relevant fields include:

- `tagName`
- `sourceType`
- `isExplicit`
- `isRestricted`
- `depth`

### Usage data

Depending on reference type, a usage can include:

- tag name
- asset path and class
- property/graph locator
- container type
- source adapter
- owner/scanned object paths
- locator confidence
- mutation support
- scan generation
- structured property segments
- Blueprint graph/node/pin identity

Not every field is meaningful for every reference type.

### Finding data

Audit findings include data such as:

- `ruleID`
- `tagName`
- `assetPath` when applicable
- `description`

## Scan Details semantics

Customer-facing scan counts are intentionally separated:

- `Property: <N> usages`
- `Graph: <N> usages`
- `Total: <N> usages`
- `Processed Assets: <N>`
- `Skipped Assets: <N>`
- `Errors: <N>`

`Processed Assets` is the total number of assets processed by the scan. It is not the number of assets that necessarily contain a Gameplay Tag usage.

## Freshness

Recommended export workflow:

1. Run **Run Full Scan**.
2. Run **Run Audit** if findings are required.
3. Export CSV/JSON.

After project or Gameplay Tag changes, run a fresh scan before relying on an older export.

Previous: [Project Settings](05_Settings.md) · [Documentation Index](INDEX.md) · Next: [Safe Refactoring & Advanced Usage](07_Advanced_Usage.md)
