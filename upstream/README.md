# Upstream Spec Kit Templates

This folder is a placeholder for storing snapshots of official Spec Kit templates
fetched from the Specify CLI (`anthropics/specify`).

## Purpose

The SpecKit M365 Companion framework is designed to work alongside the upstream
Spec Kit methodology. This folder will hold:

- Template snapshots from `uvx ... specify` commands
- Reference copies of official prompts and workflows
- Version tracking for sync purposes

## Current Status

**Not yet populated.** The companion framework can be used independently, but
future versions may sync templates from upstream to ensure compatibility.

## Future Usage

When upstream sync is implemented:

1. Run the Specify CLI to fetch latest templates
2. Copy relevant templates to this folder
3. Update `VERSION.md` with the fetched version
4. Compare with `framework/_framework/` for any needed updates

## Related Files

- `VERSION.md` - Tracks the upstream template version (when populated)
- `spec-kit-base/` - Will contain the actual template files

## Note

This folder is for **maintainer reference only** and is not distributed to
corporate environments. Only the `framework/` folder is shipped to end users.
