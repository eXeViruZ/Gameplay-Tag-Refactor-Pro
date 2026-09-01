# Installation

## Requirements

- **Gameplay Tag Refactor Pro:** v1.0.0
- **Unreal Engine:** 5.8
- **Plugin type:** Editor-only C++ plugin
- Your project must use Unreal Engine's Gameplay Tags system.

Final packaged platform details should be treated as authoritative only after the final BuildPlugin/packaging validation.

## Install from Fab

1. Add Gameplay Tag Refactor Pro to your Fab library.
2. Install it for Unreal Engine 5.8 using the normal Fab/Epic workflow.
3. Open your UE 5.8 project.
4. Open **Edit → Plugins**.
5. Search for **Gameplay Tag Refactor Pro**.
6. Enable the plugin if required.
7. Restart Unreal Editor if prompted.

## Open GTRP

After installation, GTRP is available through:

- **Tools → Gameplay Tags → Gameplay Tag Refactor Pro**
- The GTRP quick-launch icon in the main Unreal Editor toolbar

Both entry points open or focus the same dockable GTRP tab.

## Updating

1. Close Unreal Editor.
2. Update the plugin through the same installation method.
3. Reopen the UE 5.8 project.
4. Confirm GTRP opens normally.
5. Run **Run Full Scan** before performing a rename after an update.

## Removing

1. Close the GTRP tab.
2. Disable **Gameplay Tag Refactor Pro** in **Edit → Plugins**.
3. Restart if prompted.
4. Remove/uninstall the plugin through the same installation method.

Removing the editor plugin does not itself delete Gameplay Tags, redirects, or project assets that Unreal already saved.

Previous: [Documentation Index](INDEX.md) · Next: [Quick Start](02_Quick_Start.md)
