# Quickshell Rise agent instructions

## Runtime and installation contracts

- Preserve one shared shell/process for V1 and V2, while retaining their separate layout/style state. Variant switching must not create competing shell instances or overwrite the other variant's preferences.
- Keep controller, IPC, lifecycle, theme integration, and persistent state compatible with their consumers. Do not turn a view or startup change into an unrequested installer/update action.
- Preserve installer backups, existing user configuration, autostart choices, and uninstall/recovery behavior. Do not remove unrelated files or restart the live desktop as a test shortcut.
- Keep upstream attribution and fork-specific behavior distinct. Inspect the checked-out fork's scripts; do not validate a fork change by executing an upstream remote install command from the README.
- Keep credentials and private system/provider metadata out of tracked configuration, screenshots, and fixtures.

## Task-specific guidance

Use [docs/development.md](docs/development.md) for repository checks, [docs/architecture.md](docs/architecture.md) for lifecycle/variant work, and [docs/maintenance-and-recovery.md](docs/maintenance-and-recovery.md) for installer or recovery changes. Load only the relevant guide.

Use temporary configuration/state directories and controlled service-command fixtures for automated checks. QML/UI changes need affected variants and empty/error/reconnect states exercised; shell syntax checks alone do not prove the live interface.

Completion requires preserved variant/state and install/recovery contracts, applicable tests, and synchronized user guidance. Installation, removal, package changes, and restarting a real shell require explicit task scope.
