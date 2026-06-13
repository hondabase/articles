---
summary: 'Reference for the legacy Crome ROM editor JavaScript API used by scripts, ROM handlers, and plug-ins.'
applies_to:
  obd: [1]
complexity: advanced
tags:
  - tuning
  - rom
  - software
---

# Crome JavaScript scripting API

Crome exposes a JavaScript API for extending the legacy OBD1 ROM editor with scripts,
ROM handlers, and plug-ins. This reference preserves the API documented by the original
Crome community.

> **Warning:** Work on a copy of the ROM and verify every output before installing it in
> an ECU. API behavior can differ between Crome versions, and an incorrect script can
> corrupt tables, scalars, or checksums.

## Accessing API objects

Inside a Crome script, members of the default `window` object can be called directly or
through `window`:

```javascript
refresh();
window.refresh();
rom.byteAt(0x7FFF);
window.rom.byteAt(0x7FFF);
```

An HTML-based Crome plug-in accesses the same objects through `window.external`:

```javascript
window.external.refresh();
window.external.rom.byteAt(0x7FFF);
```

The archived documentation describes three main objects:

| Object | Purpose |
| :--- | :--- |
| `window` | Dialogs, plug-in registration, external commands, and display refresh |
| `window.rom` / `rom` | Read and modify the active ROM, tables, scalars, and feature flags |
| `window.files` / `files` | Open, save, read, and write files |

## Window functions

| Function | Documented purpose |
| :--- | :--- |
| `addRomHandler(romtype, author, jscmd)` | Register a handler for a ROM type |
| `addPlugin(author, mnucaption, jscmd, category)` | Add an entry to Crome's plug-in menu |
| `alert(msg)` | Display a message with an OK button |
| `confirm(msg)` | Display a Yes/No confirmation; returns false or true |
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

> **Note:** The archived signature declares `prompt()` as returning a boolean, while its
> description says it returns the user's response or an empty string. Verify behavior in
> the Crome version being targeted.

Examples from the archived API:

```javascript
addRomHandler(rtP30, 'Author', '_handle_p30_rom()');
addPlugin('Author', 'Test Plugin', '_run_test_plugin()', 0);
shell('notepad.exe', 'C:\\autoexec.bat', 0);
showBrowser('my_html_plugin.html', 400, 250);
```

An older quick reference also lists `_rom_write(start, values, count)` and
`_rom_fill(fromAddr, toAddr, byteFill)`, plus a `rom.type` property with examples such
as `rp30`, `rp72`, `rp28`, and `rpCustom`. Their availability is version-dependent.

## ROM object

### Byte, word, and table access

| Member | Access | Documented purpose |
| :--- | :---: | :--- |
| `byteAt(addr)` | Read/write | Get or set one byte at a ROM address |
| `wordAt(addr)` | Read/write | Get or set a little-endian word at a ROM address |
| `working_table` | Read/write | Select the active fuel or ignition table |
| `tableByte(col, row)` | Read/write | Get or set a raw byte in the active table |
| `tableValue(col, row)` | Read/write | Get or set the interpreted table value |
| `tableWidth` | Read-only | Width of the active table |
| `tableHeight` | Read-only | Height of the active table |
| `mapScalar(table, col)` | Read/write | Get or set a MAP scalar in millibars |
| `revScalar(table, row)` | Read/write | Get or set an RPM scalar |

`working_table` uses these documented values:

| Value | Table |
| :---: | :--- |
| `0` | Low fuel |
| `1` | High fuel |
| `2` | Low ignition |
| `3` | High ignition |

```javascript
rom.working_table = 2;
var ignitionByte = rom.tableByte(0, 5);

var lastByte = rom.byteAt(0x7FFF);
rom.byteAt(0x7FFF) = 0xFF;
```

`wordAt()` accounts for little-endian storage. The source says bytes stored as
`[0xAB][0xCD]` are returned as `0xCDAB`.

### ROM metadata and feature flags

| Member | Access | Documented meaning |
| :--- | :---: | :--- |
| `addressOf(name)` | Read/write | Address stored in a named special register |
| `addressIn(index)` | Read/write | Address stored in special-register index `0` through `63` |
| `base` | Read/write | Base ROM used for default address locations |
| `title` | Read/write | Text shown in Crome's status bar |
| `filename` | Read-only | Full filename of the active ROM |
| `OBDMode` | Read/write | Formula mode: `0` OBD0, `1` OBD1, `2` OBD2, `3` unknown |
| `notes` | Read/write | Notes attached to the active ROM |
| `gup()` | Function | Create a group undo point around a multi-change operation |

Feature flags are documented as read/write byte properties:

| Property | Values |
| :--- | :--- |
| `hasLaunchControl` | `0` off, `1` on |
| `hasFullThrottleShift` | `0` off, `1` on |
| `hasBoost` | `0` none, `1` stock MAP boost, `2` 3-bar boost, `3` custom |
| `hasFinalMultiplier` | `0` off, `1` on |
| `hasShiftLight` | `0` off, `1` on |
| `hasIAB` | `0` off, `1` on |

Use `gup()` before and after a group of changes so Crome can undo them as one action:

```javascript
rom.gup();
for (var i = 0; i <= 0x7FFF; i++) {
    rom.byteAt(i) = LoByte(i);
}
rom.gup();
refresh();
```

## Files object

| Member | Documented purpose |
| :--- | :--- |
| `showSave(filter, filterindex)` | Show a save dialog and return the selected filename |
| `showOpen(filter, filterindex)` | Show an open dialog and return the selected filename |
| `exists(filename)` | Return true when a file exists |
| `getFile(filename)` | Read a text file |
| `putFile(filename, data)` | Write data to a file |
| `browseFolder` | Show a folder browser and return the selected path |

Cancelled open, save, and folder dialogs are documented as returning an empty string.

## Special register names

Use these names with `rom.addressOf('NAME')` or their numeric index with
`rom.addressIn(index)`.

| Name | Index | Documented purpose |
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
| `NFO_LOW_TABLE` | 9 | Low-table dimensions; high byte is height, low byte is width |
| `NFO_HIGH_TABLE` | 10 | High-table dimensions; high byte is height, low byte is width |
| `REVCUT1` | 11 | First rev-cut value address |
| `REVRES1` | 12 | First rev-resume value address |
| `REVCUT2` | 13 | Second rev-cut value address |
| `REVRES2` | 14 | Second rev-resume value address |
| `VTEC_TABLE` | 15 | VTEC table address |
| `NFO_VTEC_TABLE` | 16 | VTEC table information |
| `VTEC` | 17 | VTEC configuration byte address |
| `IDLE` | 25 | Idle value address |
| `KNOCK` | 26 | Knock configuration byte address |
| `ELD` | 27 | ELD configuration byte address |
| `BARO` | 29 | Barometric-pressure configuration byte address |
| `VTECVSS` | 30 | VTEC VSS-check configuration byte address |
| `VTECCOOL` | 31 | VTEC coolant-check configuration byte address |
| `DEBUGMODE` | 32 | Debug-mode configuration byte address |
| `OXYHEAT` | 33 | O2-heater-check configuration byte address |
| `LAUNCH_CUT` | 40 | Launch-control cut value address |
| `LAUNCH_RES` | 41 | Launch-control resume value address |
| `SHIFT_CUT` | 42 | Full-throttle-shift cut value address |
| `SHIFT_RES` | 43 | Full-throttle-shift resume value address |
| `SPEED_LIMIT` | 44 | Speed-limiter value address |
| `NFO_MAP_MIN` | 45 | Minimum MAP information; no description in source |
| `NFO_MAP_MAX` | 46 | Maximum MAP information; no description in source |
| `MTX1` | 50 | Final fuel multiplier address |
| `MTX2` | 51 | No description in source |
| `MTX3` | 52 | Cranking fuel multiplier address |
| `MTX4` | 53 | No description in source |
| `MTX5` | 54 | Tip-in fuel multiplier address |
| `MTX6` | 55 | No description in source |
| `SL_BYTE` | 56 | Shift-light configuration byte address |
| `SL_RPM` | 57 | Shift-light RPM address |

The archived documentation says a ROM handler must set the corresponding
`hasLaunchControl`, `hasFullThrottleShift`, `hasFinalMultiplier`, `hasShiftLight`, and
`hasIAB` properties to `1` for Crome's built-in option editors to use them.
