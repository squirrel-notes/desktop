# Squirrel Notes for desktop (beta)

A desktop app for [Squirrel Notes](https://squirrelnotes.app), the private, encrypted notes app, for Windows, macOS and Linux.

It opens your Squirrel Notes account in its own window, with a dock or taskbar icon, a launcher entry, and the app's own title bar with search and the focus timer. Your notes are encrypted on your device exactly as they are in the browser: the app runs the same Squirrel Notes you use at [my.squirrelnotes.app](https://my.squirrelnotes.app).

> **Beta.** These builds are early and **not signed**. Expect rough edges, and install each new version by hand (there are no automatic updates yet).

## Download

Get the latest build from [Releases](https://github.com/squirrel-notes/desktop/releases).

| You have | Download |
|---|---|
| Ubuntu or Debian (x64) | `squirrel-notes-desktop_<version>_amd64.deb` |
| Mac with Apple silicon (M1 or later) | `squirrel-notes-desktop-<version>-mac-apple-silicon.zip` |
| Mac with an Intel processor | `squirrel-notes-desktop-<version>-mac-intel.zip` |
| Windows PC (most PCs) | `squirrel-notes-desktop-<version>-windows-x64-setup.exe` |
| Windows on Arm (Snapdragon, Copilot+ PCs) | `squirrel-notes-desktop-<version>-windows-arm64-setup.exe` |

Each release has a `SHA256SUMS.txt` to check your download against.

## Install

### Linux (Ubuntu, Debian)

```
sudo apt install ./squirrel-notes-desktop_<version>_amd64.deb
```

This also installs an AppArmor profile, which Ubuntu 24.04 and later need to run the app's sandbox.

### macOS

1. Unzip the download and move **Squirrel Notes.app** to Applications.
2. Because the beta isn't signed yet, macOS will refuse to open it. Run this once in Terminal:
   ```
   xattr -cr "/Applications/Squirrel Notes.app" && codesign --force --deep -s - "/Applications/Squirrel Notes.app"
   ```
3. Open it as usual.

### Windows

> **The Windows build is new and hasn't been tested on Windows yet.** Please [tell us](https://github.com/squirrel-notes/desktop/issues) how it goes.

1. Run the setup file. It installs for your account only, with no admin prompt.
2. Because the beta isn't signed yet, Windows shows **Windows protected your PC**. Choose **More info**, then **Run anyway**.
3. Squirrel Notes opens, and is in the Start menu and on your desktop.

## Good to know

- **Sign-in** works the same as on the web, Google included. Passkeys don't work in the desktop app yet: on the passkey prompt, choose **Try another way**.
- **Find on page:** Ctrl+F (⌘F on a Mac). Like a browser's find, it only sees what's on screen, so in a long note it can miss lines further down.
- **Overdue tasks on the icon:** the number of overdue tasks shows as a badge on the app's icon (Dock on a Mac, taskbar on Windows and Linux), like an unread count. It updates as soon as a task changes, while the app is open.
- **Links** to other websites open in your normal browser.
- **Diagnostics:** the beta keeps a small log of which sites the window opened (site and path only, never codes, tokens or note content) in its settings folder, to help fix sign-in problems. It never leaves your computer.

## Feedback

Found a problem? [Open an issue](https://github.com/squirrel-notes/desktop/issues).
