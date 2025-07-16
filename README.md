
# Informatica IDMC Excel

**Informatica IDMC Excel** is a utility for interacting with the Informatica Intelligent Data Management Cloud (IDMC) platform using Microsoft Excel and Power Query.

This tool simplifies daily work with metadata, tasks, and IDMC objects via a familiar Excel interface.

---

## Features

- Connect to IDMC via REST API
- Retrieve lists of mappings, tasks, connections, and other metadata objects
- Load metadata directly into Excel
- Select which asset types to retrieve
- Set custom record limits for asset queries
- Option to include disabled fields from B360 metadat
- Support for multiple organizations and environments


---

## Installation and Usage

1. Download the Excel file (`.xlsm`) with macros enabled.
2. Open it in Excel and enable macros when prompted.
3. On the `Config` sheet, provide:
   - `Login URL`
   - `Username`
4. Click the **Login** button and enter your password when prompted.
5. After successful login, you can refresh the following data sheets:
   - *Assets List*
   - *B360 Model-Business Entities*
   - *B360 Model-BE Field*
6. You can also use **Power Query Editor** to inspect and customize data queries:
   `Data > Get Data > Launch Power Query Editor`.

---

## Configuration

![settings]('/images/config-content.png')

### Main Fields (`Config` sheet)

- **Login URL** — IDMC v3 REST API login endpoint  
- **Username** — your IDMC login email  
- **Session Id** — auto-filled upon successful login and used for API requests

### API Base URLs

The following URLs are auto-filled after login. To override them manually, uncheck `Overwrite URLs by login data`.

- `baseApiUrl` — Base API for CDI and Administrator services  
- `frsApiUrl` — FRS API used for various UI metadata (e.g., B360, CDI, CAI)  
- `mdmApiUrl` — API endpoint for MDM metadata and operations  
- `avosApiUrl` — API endpoint for CAI (Cloud Application Integration)  

---

## New UI Elements

### Retrieve disabled fields (B360)

This checkbox allows you to include **disabled fields** in B360 metadata queries. When checked, disabled (hidden or deprecated) fields will be retrieved along with active ones.

### Assets List Selector

![settings]('/images/assets-list-filter.png')

This section lets you choose which object types should be retrieved when refreshing the `Assets List` worksheet. Objects are grouped by service module:

- **B360** — Business Entities, Events, Reference Data, Rules, etc.
- **CDQ / Profiling** — Cleanse, Deduplicate, Verifier, Parser, etc.
- **CDI** — Mappings, Tasks, Mapplets, Replication Tasks, etc.
- **CAI** — App Connections, Services, Processes, etc.
- **Administrator** — Runtime Environments, Schedules, Connections

You can enable or disable specific types using checkboxes.

### Limit of records

A numeric input field for specifying the maximum number of records to fetch for each selected object type.  
**Default:** `1000`.

---

## Content Worksheets

### Assets List

Populated with metadata based on selected object types and record limit.  
Click the **Refresh Assets List** button to retrieve the latest data.

### B360 Model-Business Entities

Displays business entity definitions from B360. Useful for analyzing model structure and entity relationships.

### B360 Model-BE Fields

Displays detailed field-level metadata for B360 entities.  
If **Retrieve disabled fields (B360)** is enabled, it will also include non-active fields.

---

## Authorization Script

A PowerShell script is available on the hidden sheet `sys_PS_Script` for obtaining the Session ID manually via API.  
This sheet is intended for advanced use and can be hidden during normal operation.

---

## License

MIT License
