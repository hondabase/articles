---
summary: 'Technical reference for the legacy Crome ROM editor JavaScript API used for developing scripts, ROM handlers, and plug-ins.'
tags: [tuning, software, scripting]
applies_to:
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eh]
complexity: advanced
---

# Crome JavaScript Scripting API

Crome exposes a JavaScript API for extending the legacy OBD1 ROM editor with scripts, ROM handlers, and plug-ins. 

> [!WARNING]
> Always work on a copy of the ROM and verify every output before installing it in an ECU. API behavior can differ between Crome versions, and an incorrect script can corrupt tables, scalars, or checksums.

## Accessing API Objects

Inside a Crome script, members of the default `window` object can be called directly or through `window`. An HTML-based Crome plug-in accesses the same objects through `window.external`.

```javascript
// Direct access
refresh();
rom.byteAt(0x7FFF);

// Explicit window access
window.refresh();
window.rom.byteAt(0x7FFF);

// Plug-in access
window.external.refresh();
```

| Object | Purpose |
| :--- | :--- |
| `window` | Dialogs, plug-in registration, external commands, and display refresh |
| `window.rom` / `rom` | Read and modify the active ROM, tables, scalars, and feature flags |
| `window.files` / `files` | Open, save, read, and write files |

## Window Functions

| Function | Purpose |
| :--- | :--- |
| `addRomHandler(romtype, author, jscmd)` | Register a handler for a ROM type |
| `addPlugin(author, mnucaption, jscmd, category)` | Add an entry to Crome's plug-in menu |
| `alert(msg)` | Display a message with an OK button |
| `confirm(msg)` | Display a Yes/No confirmation; returns boolean |
| `DecToHex(dec)` | Convert a decimal value to a hexadecimal string |
| `exal(cipherstring)` | Evaluate an encoded JavaScript string |
| `GetFilePath(filename)` | Return the path portion of a filename |
| `GetFileName(filename)` | Return the name portion of a filename |
| `HiByte(w)` | Return the high byte of a word |
| `LoByte(w)` | Return the low byte of a word |
| `input(msg, options, values)` | Display an input selection dialog |
| `include(filename)` | Include another script file |
| `prompt(caption, msg, default)` | Prompt for a response |
| `select(prompt, selection)` | Return the selected item index, or `-1` when cancelled |
| `shell(filename, params, windowstate)` | Start an external application |
| `shelld(doscmd)` | Run a DOS command and return its output |
| `shellw(filename, params, windowstate)` | Start an application and wait for it to close |
| `showBrowser(url, width, height)` | Open Crome's built-in browser |
| `refresh()` | Refresh the editor after a script changes the active ROM |

> [!NOTE]
> The archived signature declares `prompt()` as returning a boolean, while its description suggests it returns the user's response or an empty string. Verify behavior in the specific Crome version being targeted.

## ROM Object

### Byte, Word, and Table Access

| Member | Access | Purpose |
| :--- | :---: | :--- |
| `byteAt(addr)` | Read/Write | Get or set one byte at a ROM address |
| `wordAt(addr)` | Read/Write | Get or set a little-endian word at a ROM address |
| `working_table` | Read/Write | Select the active fuel or ignition table |
| `tableByte(col, row)` | Read/Write | Get or set a raw byte in the active table |
| `tableValue(col, row)` | Read/Write | Get or set the interpreted table value |
| `tableWidth` | Read-only | Width of the active table |
| `tableHeight` | Read-only | Height of the active table |
| `mapScalar(table, col)` | Read/Write | Get or set a MAP scalar in millibars |
| `revScalar(table, row)` | Read/Write | Get or set an RPM scalar |

**Working Table Values:**
* `0`: Low fuel
* `1`: High fuel
* `2`: Low ignition
* `3`: High ignition

### ROM Metadata and Feature Flags

| Member | Access | Purpose |
| :--- | :---: | :--- |
| `addressOf(name)` | Read/Write | Address stored in a named special register |
| `addressIn(index)` | Read/Write | Address stored in special-register index `0`–`63` |
| `base` | Read/Write | Base ROM used for default address locations |
| `title` | Read/Write | Text shown in Crome's status bar |
| `filename` | Read-only | Full filename of the active ROM |
| `OBDMode` | Read/Write | Formula mode: `0` OBD0, `1` OBD1, `2` OBD2 |
| `notes` | Read/Write | Notes attached to the active ROM |
| `gup()` | Function | Create a group undo point |

**Feature Flags (Read/Write Byte):**
* `hasLaunchControl`, `hasFullThrottleShift`, `hasFinalMultiplier`, `hasShiftLight`, `hasIAB` (Set to `1` to enable).
* `hasBoost`: `0` none, `1` stock MAP, `2` 3-bar, `3` custom.

## Files Object

| Member | Purpose |
| :--- | :--- |
| `showSave(filter, filterindex)` | Show save dialog; returns filename |
| `showOpen(filter, filterindex)` | Show open dialog; returns filename |
| `exists(filename)` | Return true if file exists |
| `getFile(filename)` | Read a text file |
| `putFile(filename, data)` | Write data to a file |
| `browseFolder` | Show folder browser; returns path |

## Special Register Names

Use these names with `rom.addressOf('NAME')` or their numeric index with `rom.addressIn(index)`.

| Name | Index | Purpose |
| :--- | :---: | :--- |
| `CHECKSUM` | 0 | Checksum correction address |
| `LOW_MAP_SCALAR` | 1 | Low MAP scalar address |
| `HIGH_MAP_SCALAR` | 2 | High MAP scalar address |
| `LOW_REV_SCALAR` | 3 | Low RPM scalar address |
| `HIGH_REV_SCALAR` | 4 | High RPM scalar address |
| `LOW_FUEL` | 5 | Low fuel table address |
| `HIGH_FUEL` | 6 | High fuel table address |
| `LOW_IGNITION` | 7 | Low ignition table address |
| `HIGH_IGNITION` | 8 | High ignition table address |
| `REVCUT1` | 11 | First rev-cut value address |
| `VTEC_TABLE` | 15 | VTEC table address |
| `IDLE` | 25 | Idle value address |
| `LAUNCH_CUT` | 40 | Launch-control cut value address |
| `SPEED_LIMIT` | 44 | Speed-limiter value address |
| `SL_RPM` | 57 | Shift-light RPM address |
