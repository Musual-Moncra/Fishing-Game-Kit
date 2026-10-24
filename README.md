# Fishing Game Kit

A Roblox fishing game kit built with [Rojo](https://github.com/rojo-rbx/rojo) and [Wally](https://wally.run).

## Project structure

`default.project.json` maps the source tree into the DataModel:

| DataModel | Contents |
| --- | --- |
| `ReplicatedStorage` | `Modules`, `Packages`, `Assets` |
| `ServerStorage` | `Modules`, `ServerPackages`, `Assets` |
| `ServerScriptService` | server entry point (`Main.server.luau`) |
| `StarterPlayer.StarterPlayerScripts` | client entry point (`Main.client.luau`) |

`Packages/` and `ServerPackages/` live at the repository root and are mapped by Rojo;
Wally installs into them directly.

## Libraries (Wally)

| Package | Version | Realm | Location |
| --- | --- | --- | --- |
| [Packet](https://devforum.roblox.com/t/3573907) | 1.7.0 | shared | `ReplicatedStorage.Packages.Packet` |
| [Signal](https://github.com/Sleitnick/rbx-signal) | 2.0.3 | shared | `ReplicatedStorage.Packages.Signal` |
| [React](https://github.com/jsdotlua/react-lua) | 17.2.1 | shared | `ReplicatedStorage.Packages.React` |
| [ProfileStore](https://github.com/MadStudioRoblox/ProfileStore) | 1.0.3 | server | `ServerStorage.ServerPackages.ProfileStore` |

Restore or update dependencies with:

```bash
wally install
```

## Build and run

```bash
rojo build -o "Fishing Game Kit.rbxlx"
rojo serve
```

Open the built place (or connect Studio to `rojo serve`) to run the kit.

## Notes

- `Fishing Game Kit.rbxlx` and `sourcemap.json` are generated and ignored by git.
- Empty folders (`Modules`, `Assets`) sync into the built place; they are skipped by
  `rojo sourcemap` until they contain a file.
