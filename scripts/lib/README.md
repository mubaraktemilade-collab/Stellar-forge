# scripts/lib

Shared shell libraries used by the scripts in this repository. This folder holds reusable bash helpers that are sourced by other scripts to provide common error handling, health-check steps, and version utilities, keeping that logic in one place instead of duplicating it across scripts.

## Files

- `errors.sh` - Error-handling helpers (e.g. failure messages and exit handling) shared by scripts.
- `health-steps.sh` - Definitions and helpers for the health-check steps run by the scripts.
- `versions.sh` - Utilities for reading, comparing, and managing version strings.
