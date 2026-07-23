# aidlc-init

Bootstrap the current directory with [AI-DLC](https://github.com/awslabs/aidlc-workflows) (AI-Driven Development Life Cycle) workflow rules for your coding agent.

## Install

Put the script in `~/bin` (or any directory on your `PATH`):

```bash
mkdir -p ~/bin
curl -fsSL -o ~/bin/aidlc-init https://raw.githubusercontent.com/vdhanota/aidlc-init/main/aidlc-init
chmod +x ~/bin/aidlc-init
```

If `~/bin` isn't on your `PATH`, add it to your shell profile:

```bash
export PATH="$HOME/bin:$PATH"
```

## Usage

```bash
cd your-project
aidlc-init -v <1|2> -e <platform>
```

| Version | Platforms |
|---|---|
| `-v 1` | `kiro` `q` `cursor` `cline` `claude` `copilot` `codex` |
| `-v 2` | `kiro` `kiro-ide` `claude` `codex` `opencode` |

Examples:

```bash
aidlc-init -v 2 -e kiro      # AI-DLC v2 for Kiro CLI — invoke with /aidlc
aidlc-init -v 1 -e claude    # AI-DLC v1 for Claude Code — say "Using AI-DLC, <intent>"
```

Run `aidlc-init` with no arguments for help.

## Requirements

- `git` (required)
- [`bun`](https://bun.sh) (v2 only — needed at runtime; the script warns if missing)

## Good to Know

- Existing files are never overwritten — conflicting files are saved as `.aidlc-new` to merge manually; existing directories are merged.
- Re-running the same command safely updates the installed files.
- Codex CLI with v2 requires your project to be a git repository.

## License

Installed content comes from [aidlc-workflows](https://github.com/awslabs/aidlc-workflows) (MIT-0).
