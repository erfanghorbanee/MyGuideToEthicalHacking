# `desktop.ini`

The `desktop.ini` file is a hidden system file used by Windows to customize and control the appearance and behavior of folders. Each folder can have its own `desktop.ini` file to specify unique settings for that folder.

## Key Features of `desktop.ini`

- Custom icons for folders.
- Localized names for folders (displayed differently depending on the system language).
- Custom folder views and templates.

## How `desktop.ini` is Used

When you customize a folder (e.g., change its icon, set a background picture, or apply a specific folder template), Windows creates or modifies the `desktop.ini` file within that folder to store these settings.

**Note: An attacker can use this feature to hide malwares.**

## Example of `desktop.ini`

Here's an example of a typical `desktop.ini` file:

```ini
[.ShellClassInfo]
IconResource=C:\Windows\system32\shell32.dll,3
LocalizedResourceName=@%SystemRoot%\system32\shell32.dll,-21769
```

**Explanation:**

- `[.ShellClassInfo]`: This section contains the settings for customizing the folder.
- `IconResource=C:\Windows\system32\shell32.dll,3`: Specifies the icon for the folder, with the icon being the third one in the `shell32.dll` file.
- `LocalizedResourceName=@%SystemRoot%\system32\shell32.dll,-21769`: Sets a localized name for the folder based on the system language.

### Creating and Modifying `desktop.ini`

You can manually create or edit a `desktop.ini` file to customize a folder's appearance. Here's a step-by-step guide:

1. **Enable Viewing Hidden/System Files**:
   - Open File Explorer.
   - Go to the "View" tab.
   - Check "Hidden items" and "File name extensions".
   - Click on "Options", then "Change folder and search options".
   - Go to the "View" tab and uncheck "Hide protected operating system files (Recommended)".

2. **Create/Edit `desktop.ini`**:
   - Open Notepad or any text editor.
   - Enter the desired settings (as shown in the example above).
   - Save the file as `desktop.ini` in the folder you wish to customize.
   - Set the file attribute to system and hidden using Command Prompt:

     ```cmd
     attrib +h +s C:\Path\To\Your\Folder\desktop.ini
     ```
