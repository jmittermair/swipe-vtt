# Local Taskbar compatibility patch

This checkout includes the runtime files from Swipe v2.9.2's official
`module.zip`; the public Git repository only contains release metadata.
The local change is `styles/compat-foundry-taskbar.css`, registered after
Swipe's main stylesheet in `module.json`.

The stylesheet hides Ripper's Taskbar, start menu, workspace controls,
docking container, and minimize-to-taskbar controls whenever Swipe applies
`body.swipe-vtt`. Leaving Swipe mode restores normal styling. No world or
player settings are changed, and no Taskbar-side patch is required.

## Install and verify

Copy this checkout's module.json, scripts/, styles/, templates/, lang/, and
any other release assets into your Foundry Data/modules/swipe-vtt directory
with Foundry stopped. Keep its module directory name `swipe-vtt`. Restart
Foundry and fully reload clients so the changed manifest loads the new CSS.
An upstream module update will replace this local patch.

- With Taskbar enabled for players, enter Swipe mode: Taskbar, its open
  start/workspace menus, and its minimize buttons should be hidden.
- Test phone portrait/landscape, tablet, and Swipe sheets-only mode.
- Leave Swipe mode: the Taskbar should be visible again.
- A desktop client with Swipe mode off should retain its Taskbar.

This patch has not been tested in a live Foundry session.
