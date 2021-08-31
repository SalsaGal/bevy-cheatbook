# Setting the Window Icon

[Click here for the full example code.](../code/examples/window-icon.rs)

---

You might want to set a custom Window Icon. On Windows and Linux, this is
the icon image shown in the window title bar (if any) and task bar (if any).

Unfortunately, Bevy does not yet provide an easy and ergonomic built-in way
to do this. However, it can be done via the `winit` APIs.

The way shown here is quite hacky. To save on code complexity, instead of
using Bevy's asset system to load the image in the background, we bypass
the assets system and directly load the file using the `image` library.

There is some WIP on adding a proper API for this to Bevy; see
[PR #2268](https://github.com/bevyengine/bevy/pull/2268) and
[Issue #1031](https://github.com/bevyengine/bevy/issues/1031).

This example shows how to set the icon for the primary/main window, from
a Bevy startup system.

```rust,no_run,noplayground
{{#include ../code/examples/window-icon.rs:main}}
```