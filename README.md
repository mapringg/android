# android

Oppo Find X9, ColorOS 17, over USB with Developer options on.

- `bin/phone`: snapshot, changes since the last one, drift from `desired/`
- `bin/phone fix`: apply the drift after confirming
- `bin/phone snap [label] | diff [old new] | smoke | ui dump | ui tap <text> | ui shot <name>`
- `desired/ui.txt`: targets only the Settings app can set
- `bin/phone save`: store `private/` in 1Password after editing it

`desired/` holds only generic targets. Anything that identifies the phone or its owner stays out of git:

- `snapshots/`: full settings dumps, kept in 1Password as `mapringg.android.snapshots` and saved after every snapshot
- `private/`: personal targets with the same file names as `desired/` (installed apps, their settings, personal UI targets), kept in 1Password as `mapringg.android.private` and added to `desired/` when the script reads it

Both come back from 1Password through `secret restore` when the folder is missing.
