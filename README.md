# x-ghub
**A better GHub macro editor**

x-ghub is a custom macro editor built with Vue, designed to streamline the process of editing macros created by the Logitech GHub software. This tool provides an intuitive interface, making it easier to modify and manage your macros.

## Features
- Simple import/export functionality for GHub macro data.
- Edit macros directly from GHub’s internal database.
- User-friendly interface built with Vue for smoother workflow.

## Getting Started

To begin using x-ghub with your GHub macros, follow the steps below to import and export the necessary data.

### Step 1: Access GHub's Settings Database
1. Use an SQLite file editor such as [DataGrip](https://www.jetbrains.com/datagrip/) or any other preferred SQLite tool.
2. Navigate to the following directory on your system: ```C:\Users<YOURUSERNAME>\AppData\Local\LGHUB```

3. Open the `settings.db` file located in this directory using your SQLite editor.

### Step 2: Locate and Export Macro Data
1. In the SQLite editor, locate the `data` table within the `settings.db` file. The table structure is as follows:
```sql
_id           INTEGER PRIMARY KEY,
_date_created DATETIME DEFAULT CURRENT_TIMESTAMP,
file          BLOB NOT NULL
```
3. Find the relevant record and copy the entire contents of the `file` field. This field contains the macro data in binary format.

### Step 3: Import Data into x-ghub
1. Paste the copied `file` data into the x-ghub website's import function.
2. Make the necessary modifications to your macros using the user-friendly interface provided by x-ghub.

### Step 4: Export Modified Data
1. After making your changes, use the export function in x-ghub to generate the updated data.
2. Copy the exported data and paste it back into the `file` field of the `settings.db` file, overwriting the existing content.

### Step 5: Save and Apply Changes
1. Before importing the modified data back into GHub, ensure that the GHub software is **completely closed**.
2. Save the changes to the `settings.db` file in your SQLite editor.
3. Reopen GHub to apply the modifications to your macros.

## Important Notes
- Always close Logitech GHub before re-importing the modified database file. Failing to do so might result in conflicts or data corruption.
- Ensure you keep a backup of the original `settings.db` file before making any changes, to avoid accidental loss of data.

## License
This project is licensed under the [MIT License](LICENSE), which allows for open-source use, modification, and distribution, with proper attribution to the original creator.

## Acknowledgments
x-ghub was developed to provide an easier way to manage GHub macros. Special thanks to the open-source community for their contributions and support.

---

Enjoy a more efficient macro editing experience with **x-ghub**!
