---
summary: 'A technical guide for installing and applying the Add Extra Features plugin in Crome to enable advanced OBD1 tuning functions like launch control and boost tables.'
tags: [tuning, software, crome, obd1]
applies_to:
  models: [civic, del-sol, integra, prelude]
  chassis: [eg, eh, ej, dc, da]
complexity: intermediate
---

# Installing and Configuring the Add Extra Features Plugin for Crome

Crome is a ROM editing and tuning suite for OBD1 Honda ECUs. While the base software supports standard fuel and ignition tables, advanced features—such as launch control, full-throttle shifting (flat foot shift), and boost scaling—are implemented via the **Add Extra Features** (`addextrafeatures.cpf`) plugin.

## Prerequisites
*   A valid OBD1 `.bin` file (e.g., P28, P30, or P72 base map).
*   The `addextrafeatures.cpf` plugin file.

## 1. Plugin Installation
Crome requires plugin files to be placed in the local installation directory to be recognized by the software.

1. Extract the `addextrafeatures.zip` package.
2. Copy the `addextrafeatures.cpf` file to the Crome plugins directory.
   *   **Default Path:** `C:\Program Files (x86)\Crome\Plugins\`

> [!NOTE]
> If the archive is password-protected, use the standard Crome distribution password to extract the contents.

## 2. Registering the Plugin
Once the file is placed in the directory, it must be registered within the Crome interface.

1. Launch **Crome**.
2. Navigate to **Plugins** > **Install New Plugin...**
3. Select `addextrafeatures.cpf` from the `Plugins` directory.
4. Click **Open**.
5. Verify the plugin is active by checking the **Plugins** menu.

## 3. Patching the ROM
After registration, the plugin must be applied to the specific ROM file to inject the necessary code.

1. Open your target OBD1 `.bin` file in Crome.
2. Navigate to **Plugins** > **Enhancements** > **Add Extra Features**.
3. Follow the wizard prompts and click **Next** to execute the code injection.
4. Once the process completes, the new parameters will be available in the ROM.

> [!IMPORTANT]
> Always save a backup copy of your original `.bin` file before applying patches.

## 4. Configuration
After patching, the new features will appear in the Crome interface.

*   **Parameter Access:** Navigate to the **Options** menu or the newly created table tabs to adjust specific values.
*   **Common Features:**
    *   **Launch Control:** Set the RPM limit for stationary launches.
    *   **Flat Foot Shift:** Define the RPM window for full-throttle gear changes.
    *   **Boost Scaling:** Adjust maps to accommodate forced induction sensors and pressure targets.

> [!TIP]
> After configuring new features, verify the checksum of the ROM before uploading to the ECU to ensure the file integrity remains intact.
