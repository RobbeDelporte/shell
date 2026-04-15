# Caelestia Shell — personal fork

This is **RobbeDelporte/shell**, a fork of `caelestia-dots/shell` (the Quickshell
QML UI: bar, launcher, notifications, session lock, etc.).

Location: `~/.config/quickshell/caelestia` — Quickshell picks this up automatically
and it **overrides the AUR-installed `caelestia-shell`** when running
`caelestia shell` or `qs -c caelestia`.

## Remotes

- `origin`   → `https://github.com/RobbeDelporte/shell.git`
- `upstream` → `https://github.com/caelestia-dots/shell.git`

## Workflow

1. Branch off `main`:
   ```sh
   git checkout main && git pull upstream main
   git checkout -b <topic>
   ```
2. Edit QML/JS. Reload the running shell to see changes:
   ```sh
   caelestia shell -d         # or: qs -c caelestia
   ```
   Most QML changes hot-reload. If not, kill and restart the shell.
3. Commit → push to `origin`.
4. Sync with upstream via `git fetch upstream && git merge upstream/main`.
5. PR back via `gh pr create` against `caelestia-dots/shell:main`.

## Layout hints

- `config/` — runtime config schema/defaults
- `modules/` — feature areas (bar, launcher, lock, notifications, …)
- `services/` — long-running singletons (audio, network, …)
- `utils/` — shared helpers
- `shell.qml` — top-level entry

When making an "impactful" change, read the existing module's neighbors before
editing — naming and property conventions matter for the theme to stay coherent.

## Do not

- Do not edit the AUR-installed copy at `/usr/share/caelestia-shell/` — changes
  there are overwritten on upgrade.
- Do not push to `upstream`.
