# Feature & Audit Reference

## Main UI

### Filter tags
Filters the visible Tag Tree by tag text.

### Run Full Scan
Builds a fresh project-wide GTRP scan index.

### Run Audit
Runs the five built-in audit rules against the current scan/dictionary state.

Native/engine-defined tags are excluded from rules where the finding would not be actionable for the customer, including the v1.0 missing-comment and no-supported-usage checks.

### Export CSV
Exports the current committed usage data to:

`Saved/GTP_Usages.csv`

### Export JSON
Exports the current dictionary, usages, and findings to:

`Saved/GTP_Report.json`

### Tag Tree
Shows Gameplay Tag hierarchy plus relevant states such as Explicit/Implicit and source type.

### Tag Details
Shows information including tag name, source type, explicit/restricted state, child count, and usage count.

### Usages
Shows supported detected references for the selected tag.

Rows include customer-readable information such as Asset, Property/graph locator, and Reference type.

### Audit Findings
Shows audit results using customer-facing severities:

- Error
- Warning
- Info

## Rename panel

### Source
The Gameplay Tag being refactored.

### Target
The desired new Gameplay Tag.

### Preview Impact
Required for the current Source/Target pair before execution.

### Rename Tag
Executes the controlled rename only when the current Preview is executable.

### Show Technical Details
Expands technical execution information for troubleshooting/support.

## v1.0 refactor support matrix

| Reference type | Detection | Automatic refactor |
|---|---:|---:|
| Supported direct `FGameplayTag` property | Yes | Yes |
| Exact semantic `FGameplayTag` Blueprint pin | Yes | Yes |
| `FGameplayTagContainer` graph reference | Semantic detection where supported | No |
| `FGameplayTagQuery` graph reference | Semantic detection where supported | No |
| Generic dotted String/Name/Text | Not accepted as semantic tag usage | No |
| Dynamic/runtime-created usage | Not guaranteed | No |
| Arbitrary C++ source-code reference | No automatic source rewrite | No |

Unsupported detected references are handled conservatively and can block automatic execution rather than being silently ignored.

## Built-in audit rules

### GTR002 — Explicit Tag Without Developer Comment
Highlights applicable project-owned/config-defined explicit tags with no developer comment. Native/engine-defined tags are excluded.

### GTR003 — Multiple Definition Sources
Highlights a tag defined from more than one source.

### GTR015 — Deep Hierarchy
Highlights hierarchies exceeding the configured depth threshold.

### GTR101 — No Supported Serialized Usage
Highlights applicable project-owned/config-defined tags with no supported serialized usage. Dynamic usages may still exist. Native/engine-defined tags are excluded.

### GTR108 — Broad Root / High Child Count
Highlights tag parents/namespaces exceeding the configured child-count threshold.

The exact customer-visible threshold/setting values are documented in [Project Settings](05_Settings.md).

Previous: [Core Workflow](03_Core_Workflow.md) · [Documentation Index](INDEX.md) · Next: [Project Settings](05_Settings.md)
