# Hondatabase - Wiki Porting Assessment & Progress Plan

This plan assesses all **513 topics** in the `library` web of the `pgmfi` wiki archive database. It categorizes them, identifies valuable articles vs stubs, and establishes a clear path to complete the porting process.

## 1. Overall Progress Summary

| Status | Count | Percentage | Description |
| :--- | :---: | :---: | :--- |
| **Completed** | 34 | 6.6% | Articles ported, cleaned, and merged to main |
| **Pending Porting** | 391 | 76.2% | Relevant content articles remaining to be ported |
| **Stubs / Ignored** | 88 | 17.2% | Wiki pages with < 100 characters of text (empty templates, personal placeholders) |
| **Total** | **513** | **100%** | All topics in `library` web |

## 2. Category Breakdown

| Category | Total | Completed | Pending | Stubs |
| :--- | :---: | :---: | :---: | :---: |
| Unclassified/Other | 252 | 0 | **202** | 50 |
| Electronics/ECU hardware & chipping | 88 | 13 | **62** | 13 |
| Electronics/Sensors & solenoids | 71 | 17 | **44** | 10 |
| Tuning & ROM editing | 43 | 3 | **34** | 6 |
| Electronics/Wiring & conversion | 17 | 0 | **16** | 1 |
| General Info & History | 15 | 0 | **10** | 5 |
| Diagnostics & troubleshooting | 11 | 1 | **9** | 1 |
| Engine & Drivetrain mechanical | 11 | 0 | **9** | 2 |
| Fueling & Injectors | 5 | 0 | **5** | 0 |

## 3. Prioritized Pending Articles by Category

Below are the top pending articles in each category, sorted by length (approximate value/content depth). This serves as our prioritized backlog.

### Unclassified/Other (Top 15 prioritized)

| Title | Slug | Length (chars) | Priority / Note |
| :--- | :--- | :---: | :--- |
| OBD | `obd` | 22774 | **High** (Rich content) |
| Debugging Data Logging | `debugging-data-logging` | 7969 | **High** (Rich content) |
| Easy Rtp V10 | `easy-rtp-v10` | 7513 | **High** (Rich content) |
| Sim | `sim` | 7008 | **High** (Rich content) |
| Pgsrc Translation | `pgsrc-translation` | 6960 | **High** (Rich content) |
| Oki6260A | `oki6260a` | 6036 | **High** (Rich content) |
| Release Notes | `release-notes` | 5466 | **High** (Rich content) |
| Text Formatting Rules | `text-formatting-rules` | 4598 | **High** (Rich content) |
| Willem | `willem` | 3806 | **High** (Rich content) |
| Basic Concepts | `basic-concepts` | 3706 | **High** (Rich content) |
| UPD7004C | `upd7004c` | 3451 | **High** (Rich content) |
| P0A | `p0a` | 3373 | **High** (Rich content) |
| Easy Rtp Install | `easy-rtp-install` | 3369 | **High** (Rich content) |
| DLC | `dlc` | 2956 | **High** (Rich content) |
| 82C55 | `82c55` | 2880 | **High** (Rich content) |

### Electronics/ECU hardware & chipping (Top 15 prioritized)

| Title | Slug | Length (chars) | Priority / Note |
| :--- | :--- | :---: | :--- |
| Ecu Definition Codes | `ecu-definition-codes` | 24956 | **High** (Rich content) |
| P30 | `p30` | 9648 | **Completed** (Batch 4) |
| Ecu Chipping Wirelist | `ecu-chipping-wirelist` | 7799 | **Completed** (Batch 2) |
| Chipping An88-89ECU | `chipping-an88-89ecu` | 6471 | **High** (Rich content) |
| P72 | `p72` | 6267 | **Completed** (Batch 5) |
| Ecu Tuning | `ecu-tuning` | 5899 | **Completed** (Batch 5) |
| Doc ECU School | `doc-ecu-school` | 5503 | **High** (Rich content) |
| P13 | `p13` | 5414 | **Completed** (Batch 5) |
| Ecu Families | `ecu-families` | 4626 | **Completed** (Batch 4) |
| P28 | `p28` | 3833 | **Completed** (Batch 4) |
| Japanese Domestic Market P30D12 Modification | `japanese-domestic-market-p30d12-modification` | 3808 | **High** (Rich content) |
| PW0 | `pw0` | 2928 | **Completed** (Batch 5) |
| OBD0 Inter Chip Communication | `obd0-inter-chip-communication` | 2924 | **High** (Rich content) |
| PR3 | `pr3` | 2584 | **Completed** (Batch 5) |
| OBD0PM6PM7RAM Locations | `obd0pm6pm7ram-locations` | 2478 | Medium |

### Electronics/Sensors & solenoids (Top 15 prioritized)

| Title | Slug | Length (chars) | Priority / Note |
| :--- | :--- | :---: | :--- |
| Wide Band O2 | `wide-band-o2` | 7161 | **Completed** (Batch 2) |
| Understanding Maps | `understanding-maps` | 3845 | **Completed** (Batch 4) |
| Inter Wiki Map | `inter-wiki-map` | 3554 | **High** (Rich content) |
| How To Log External Data Such As An Egt Sensor | `how-to-log-external-data-such-as-an-egt-sensor` | 3319 | **High** (Rich content) |
| Turbo Compressor Map | `turbo-compressor-map` | 2833 | **High** (Rich content) |
| Rom Maps | `rom-maps` | 2810 | **High** (Rich content) |
| Disable Vtec VSS Check P30 203 | `disable-vtec-vss-check-p30-203` | 1975 | Medium |
| Engine Coolant Temperature | `engine-coolant-temperature` | 1957 | Medium |
| Electronic Part Supplier | `electronic-part-supplier` | 1775 | Medium |
| RTP Project | `rtp-project` | 1701 | Medium |
| O2 Input Mod | `o2-input-mod` | 1050 | Medium |
| OBD1 Civic Integra EC Us | `obd1-civic-integra-ec-us` | 1017 | Medium |
| Add Knock To P30G00 | `add-knock-to-p30g00` | 981 | Medium |
| Remove A Knock Sensor | `remove-a-knock-sensor` | 949 | Medium |
| Adjust PR4 Pa Sensor | `adjust-pr4-pa-sensor` | 948 | Medium |

### Tuning & ROM editing (Top 15 prioritized)

| Title | Slug | Length (chars) | Priority / Note |
| :--- | :--- | :---: | :--- |
| Crome Script | `crome-script` | 18510 | **High** (Rich content) |
| Crome FAQ | `crome-faq` | 5233 | **Completed** (Batch 4) |
| Proposed Datalogging Protocol | `proposed-datalogging-protocol` | 4149 | **High** (Rich content) |
| Turbo Edit | `turbo-edit` | 4038 | **High** (Rich content) |
| Serial Communication | `serial-communication` | 3177 | **High** (Rich content) |
| Howto Add Extra Features In Crome | `howto-add-extra-features-in-crome` | 3130 | **High** (Rich content) |
| Second Gen Usb To Serial Converter | `second-gen-usb-to-serial-converter` | 2869 | **High** (Rich content) |
| Tuning Timing | `tuning-timing` | 2734 | **High** (Rich content) |
| Tuning For Smog | `tuning-for-smog` | 2727 | **High** (Rich content) |
| Nokia Cable Datalogging | `nokia-cable-datalogging` | 2533 | **High** (Rich content) |
| Common TE Problems | `common-te-problems` | 2333 | Medium |
| Usb To Serial Converter Second Gen | `usb-to-serial-converter-second-gen` | 1850 | Medium |
| Rtp Truth Table | `rtp-truth-table` | 1514 | Medium |
| Full Duplex Datalogging | `full-duplex-datalogging` | 1415 | Medium |
| Pre Ignition | `pre-ignition` | 1166 | Medium |

### Electronics/Wiring & conversion (Top 15 prioritized)

| Title | Slug | Length (chars) | Priority / Note |
| :--- | :--- | :---: | :--- |
| Kurts OBD0-OBD1 | `kurts-obd0-obd1` | 15121 | **High** (Rich content) |
| Accord Auto OBD2-OBD1 | `accord-auto-obd2-obd1` | 13050 | **High** (Rich content) |
| D16Z6-4G-swapnotes | `d16z6-4g-swapnotes` | 7300 | **High** (Rich content) |
| Wiki Plugin | `wiki-plugin` | 2552 | **High** (Rich content) |
| Calendar Plugin | `calendar-plugin` | 1794 | Medium |
| OBD1P08 Auto Manual | `obd1p08-auto-manual` | 888 | Medium |
| Wire Harness | `wire-harness` | 582 | Medium |
| OBD0 Conversion Formula | `obd0-conversion-formula` | 511 | Medium |
| OBD0 Conversion Formulas | `obd0-conversion-formulas` | 511 | Medium |
| OBD0 Conversion Formulae | `obd0-conversion-formulae` | 510 | Medium |
| OBD1P13 Auto Manual | `obd1p13-auto-manual` | 493 | Medium |
| OBD1 Conversion Formulae | `obd1-conversion-formulae` | 438 | Medium |
| PS9 Auto Manual | `ps9-auto-manual` | 356 | Medium |
| OBD2P5M Auto Manual | `obd2p5m-auto-manual` | 214 | Low (Short reference) |
| Conversion | `conversion` | 211 | Low (Short reference) |

### General Info & History (Top 10 prioritized)

| Title | Slug | Length (chars) | Priority / Note |
| :--- | :--- | :---: | :--- |
| Uber Data FAQ | `uber-data-faq` | 6847 | **High** (Rich content) |
| Begginers FAQ | `begginers-faq` | 4405 | **High** (Rich content) |
| Php Wiki Administration | `php-wiki-administration` | 3032 | **High** (Rich content) |
| Wiki Word | `wiki-word` | 2126 | Medium |
| How To Use Wiki | `how-to-use-wiki` | 1987 | Medium |
| Magic Php Wiki UR Ls | `magic-php-wiki-ur-ls` | 1699 | Medium |
| Inter Wiki | `inter-wiki` | 1647 | Medium |
| Wiki Wiki Web | `wiki-wiki-web` | 847 | Medium |
| Php Wiki | `php-wiki` | 255 | Low (Short reference) |
| Php Wiki Documentation | `php-wiki-documentation` | 121 | Low (Short reference) |

### Diagnostics & troubleshooting (Top 9 prioritized)

| Title | Slug | Length (chars) | Priority / Note |
| :--- | :--- | :---: | :--- |
| Honda Error Codes | `honda-error-codes` | 21603 | **High** (Rich content) |
| OBD1 Code Compatibility | `obd1-code-compatibility` | 1675 | Medium |
| CEL | `cel` | 1612 | Medium |
| OBD0 Code Compatibility | `obd0-code-compatibility` | 1385 | Medium |
| 91PM6 Target Idle | `91pm6-target-idle` | 1316 | Medium |
| Label Decode | `label-decode` | 778 | Medium |
| Limp Mode | `limp-mode` | 489 | Medium |
| 91PM7 Target Idle | `91pm7-target-idle` | 367 | Medium |
| Idle Air Control Valve | `idle-air-control-valve` | 190 | Low (Short reference) |

### Engine & Drivetrain mechanical (Top 9 prioritized)

| Title | Slug | Length (chars) | Priority / Note |
| :--- | :--- | :---: | :--- |
| OBD1 8bit Low Cam RPM | `obd1-8bit-low-cam-rpm` | 1567 | Medium |
| Engine Sim | `engine-sim` | 919 | Medium |
| OBD1 8bit High Cam RPM | `obd1-8bit-high-cam-rpm` | 917 | Medium |
| Low Cam | `low-cam` | 352 | Medium |
| High Cam | `high-cam` | 348 | Medium |
| Dual Runner Manifold | `dual-runner-manifold` | 307 | Medium |
| Prelude Accord | `prelude-accord` | 305 | Medium |
| Turbo | `turbo` | 294 | Low (Short reference) |
| Cam Profile | `cam-profile` | 151 | Low (Short reference) |

### Fueling & Injectors (Top 5 prioritized)

| Title | Slug | Length (chars) | Priority / Note |
| :--- | :--- | :---: | :--- |
| Air Fuel Ratio | `air-fuel-ratio` | 3036 | **High** (Rich content) |
| OBD1 8bit Fuel | `obd1-8bit-fuel` | 648 | Medium |
| Fuel Cut | `fuel-cut` | 410 | Medium |
| Fuel Octane | `fuel-octane` | 292 | Low (Short reference) |
| OBD0 Fuel | `obd0-fuel` | 111 | Low (Short reference) |

## 4. Porting Roadmap & Next Steps

1. **Phase 1: High-Priority Electronics & Tuning (Next Batch)**: Port and reformat high-content articles (length > 2500 chars) such as `ecu-definition-codes`, `ecu-chipping-wirelist`, `kurts-obd0-obd1`, and `obd0ecuautotomanualwithoutremoveanyhardware`.
2. **Phase 2: Wiring & Conversions**: Focus on the harness and swaps category to help enthusiasts with swaps.
3. **Phase 3: Diagnostics & Troubleshooting**: Standardize error code guides and symptom-based checklists.
4. **Phase 4: Mechanical & Drivetrain**: Port mechanical guides like RT4WD details, cams, and mechanical engine basics.
5. **Phase 5: Cleaning Stubs**: Review the 88 stubs and decide whether to delete them or write thin helper summaries.
