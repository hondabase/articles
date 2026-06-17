---
summary: 'Software guide for downloading, installing, and applying the Add Extra Features plugin in the Crome OBD1 ROM editor to enable launch control and boost tables.'
tags: [tuning, rom, software]
applies_to:
  obd: [1]
  models: [civic, del-sol]
  chassis: [eg, eg-eh]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Howto Add Extra Features In Crome'
    url: /pgmfi/wiki/library/howto-add-extra-features-in-crome
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# How to Install the "Add Extra Features" Plugin in Crome

Crome is a popular ROM editing and tuning suite for OBD1 Honda ECUs. While the base software supports standard fuel and ignition tables, advanced features—such as launch control, full-throttle shifting (flat foot shift), and boost scaling—must be added via external plugins. 

The **Add Extra Features** plugin (`addextrafeatures.cpf`) is one of the most common packages used to patch standard ROMs with these options.

---

## Step 1: Place the Plugin File in the Crome Directory

Crome plugins use the `.cpf` file extension. To be recognized by the software, these files must reside in Crome's local plugins folder.

1. Download the `addextrafeatures.zip` package from an authorized Honda tuning archive.
2. Extract the ZIP file contents.
3. Copy the `addextrafeatures.cpf` file and paste it into Crome's installation plugin directory. By default, this is located at:
 `C:\Program Files (x86)\Crome\Plugins\` (on 64-bit Windows systems)
 
> [!NOTE]
> Historically, legacy Crome plugin archives were password-protected to prevent corruption. If prompted during extraction, use the standard Crome installation password.

---

## Step 2: Register the Plugin in Crome

Once the file is in the directory, you must register it in Crome's settings interface:

1. Launch **Crome**.
2. In the top menu, navigate to **Plugins** -> **Install New Plugin...**
3. In the file explorer window that appears, navigate to Crome's `Plugins` directory.
4. Select **`addextrafeatures.cpf`** and click **Open**.
5. Verify that the plugin appears in the list of active plugins.

---

## Step 3: Patch Your ROM BIN

After registration, you must apply the plugin patches to the specific ROM file you are editing.

1. Open the desired OBD1 `.bin` file in Crome (typically a stock P28 or P30 ROM).
2. Navigate to **Plugins** -> **Enhancements** -> **Add Extra Features**.
3. A wizard dialog will appear. Click **Next** to run the code injection script.
4. Once the patching process finishes, the new parameters will be added to the ROM.
5. To configure the newly added parameters (such as launch RPM limits or boost cut pressures), go to the **Options** menu or access the relevant table tabs in Crome.
