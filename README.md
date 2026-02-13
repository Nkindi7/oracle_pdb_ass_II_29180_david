# Oracle PDB Management Assignment

## Student Information
- **Name:** NYIRINKINDI David
- **Student ID:** 29180
- **Course:** INSY 8311 - Database Development with PL/SQL
- **Date:** February 13, 2026

---

## Overview

Hands-on Oracle Multitenant Architecture assignment demonstrating PDB creation, deletion, user management, and OEM dashboard access.

---

## Oracle Environment
- **Database:** Oracle 21c Express Edition (21.3.0.0.0)
- **OS:** [Windows 11]
- **Tools:** SQL*Plus, Oracle Enterprise Manager

---

## Task 1: Create Main PDB

**PDB Created:** `[DA_pdb_29180]`  
**Username:** `[DAVID_PLSQLAUCA_29180]`

**Commands:**
```sql
CREATE PLUGGABLE DATABASE [DA_pdb_29180 ]
ADMIN USER [DAVID_PLSQLAUCA_29180] IDENTIFIED BY [12345]
FILE_NAME_CONVERT = ('pdbseed', '[pdb_DA_pdb_29180]');

ALTER PLUGGABLE DATABASE [pdb_DA_pdb_29180] OPEN;
GRANT CONNECT, RESOURCE, DBA TO [DAVID_PLSQLAUCA_29180];
```

**Evidence:** Screenshots show PDB creation, open state (READ WRITE), and user verification.
<img width="423" height="112" alt="pdb creation" src="https://github.com/user-attachments/assets/12625ae7-d73d-4cf3-a2c1-89fc0d91b9e9" />

<img width="458" height="404" alt="pdb open" src="https://github.com/user-attachments/assets/e41c51bc-2afe-449b-9d21-c8dd9fff80c5" />

<img width="464" height="162" alt="User exists" src="https://github.com/user-attachments/assets/86708d4a-6cc3-4d22-a7f0-9570644ca721" />



---

## Task 2: Create and Delete Temporary PDB

**Temp PDB:** `[DA_pdb_29180]`

**Commands:**
```sql
CREATE PLUGGABLE DATABASE [DA_pdb_29180]
ADMIN USER temp_admin IDENTIFIED BY [12345]
FILE_NAME_CONVERT = ('pdbseed', '[DA_pdb_29180]');

ALTER PLUGGABLE DATABASE [DA_pdb_29180] CLOSE IMMEDIATE;
DROP PLUGGABLE DATABASE [DA_pdb_29180] INCLUDING DATAFILES;
```

**Evidence:** Screenshots show creation, both PDBs existing, deletion, and verification.
<img width="452" height="209" alt="temp creation" src="https://github.com/user-attachments/assets/70512baa-8f2c-46c4-b085-836e565c3452" />

<img width="676" height="428" alt="both pdbs" src="https://github.com/user-attachments/assets/318a0726-4cd4-40b0-add0-e9f55e98288a" />

<img width="462" height="137" alt="drop pdb" src="https://github.com/user-attachments/assets/c057c9d3-4319-47e8-bf0d-4b11c23195b4" />

<img width="451" height="353" alt="verify deletion" src="https://github.com/user-attachments/assets/d221f3c4-818b-4771-95bb-16a3ad4a9957" />



---

## Task 3: Oracle Enterprise Manager

**Access:** https://localhost:5500/em (SYS as SYSDBA)

**Evidence:** OEM dashboard screenshot showing PDB status and username.
<img width="922" height="395" alt="oem dashboard" src="https://github.com/user-attachments/assets/0e71085e-a07f-4774-b8eb-b9bee2313ed0" />



---



---


---

## Academic Integrity Statement

I, **NYIRINKINDI David** (ID: **29180**), declare this work is completed individually. All commands, screenshots, and documentation are my own. No AI tools or collaboration were used.

**Signed:** NYIRINKINDI David
**Date:** 13 february 2026

---
