# windows-dfir-lab38-environment-variables-investigation
## Overview

Windows Environment Variables provide shortcuts to important system and user directories. During Digital Forensics and Incident Response (DFIR), analysts frequently encounter these variables inside PowerShell scripts, registry entries, scheduled tasks, malware, and persistence mechanisms. Understanding how these variables resolve to actual filesystem locations is essential for locating evidence and validating suspicious paths.

In this hands-on DFIR lab, PowerShell was used to enumerate Windows Environment Variables, navigate user directories, resolve logical paths into physical locations, and validate both existing and non-existent artifacts. The investigation demonstrates how analysts can interpret environment variable references during host-based forensic investigations using native Windows tools.

---

# Executive Summary

This investigation demonstrates how Windows Environment Variables can be analyzed using native Windows tools without requiring third-party forensic software. By enumerating variables, navigating to their corresponding directories, resolving logical paths, and validating suspicious references, the investigation shows how analysts can accurately interpret Windows path information during incident response.

The workflow mirrors a common DFIR process of identifying system variables, validating filesystem locations, correlating logical and physical paths, and documenting investigative findings.

---

# Investigation Objectives

- Enumerate Windows Environment Variables.
- Understand commonly used system variables.
- Navigate directories using environment variables.
- Resolve logical paths into physical filesystem locations.
- Validate existing and non-existent paths.
- Create sample artifacts using environment variables.
- Correlate logical and physical paths.
- Document investigation findings.

---

# Skills Demonstrated

- Windows Environment Variable Analysis
- Windows DFIR Methodology
- Host-Based Forensic Investigation
- PowerShell Navigation
- Path Resolution
- Filesystem Validation
- Evidence Correlation
- Windows Artifact Analysis
- Investigation Documentation
- Incident Reporting

---

# Tools Used

- Windows 10
- Windows PowerShell
- File Explorer

---

# Lab Environment

| Component | Details |
|-----------|---------|
| Operating System | Windows 10 |
| Investigation Type | Host-Based DFIR |
| Analysis Method | Native Windows Tools |
| Primary Artifact | Windows Environment Variables |
| Shell | Windows PowerShell |
| Privileges | Administrator |

---

# Investigation Workflow

1. Create investigation workspace.
2. Enumerate environment variables.
3. Review common variables.
4. Navigate using environment variables.
5. Resolve logical paths.
6. Create sample artifacts.
7. Validate investigation paths.
8. Correlate logical and physical locations.
9. Remove lab artifacts.

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1083 | File and Directory Discovery |
| T1005 | Data from Local System |
| T1070 | Indicator Removal on Host (Cleanup) |

---

# Evidence Collected

- Environment variable enumeration
- USERPROFILE contents
- APPDATA directory listing
- TEMP directory listing
- Resolve-Path outputs
- Sample folder creation
- Sample file creation
- Path validation results

---

# Evidence Correlation

The investigation correlated multiple Windows artifacts to validate environment variable resolution:

- Environment variables were mapped to their physical filesystem locations.
- PowerShell navigation confirmed directory resolution.
- Resolve-Path validated both existing and missing paths.
- Sample artifacts demonstrated how files can be created using environment variables rather than absolute paths.

---

# Investigation Findings

The investigation confirmed that Windows Environment Variables provide reliable references to critical user and system directories. PowerShell successfully resolved logical paths into physical locations, enabling quick validation of investigation artifacts. The lab also demonstrated how missing paths can be identified during forensic analysis, helping investigators distinguish between valid and suspicious references.

---

# Key Takeaway

Windows Environment Variables are frequently referenced in malware, scripts, registry entries, and persistence mechanisms. Understanding how to enumerate, resolve, and validate these variables enables DFIR analysts to quickly locate artifacts, interpret suspicious paths, and reconstruct attacker activity using native Windows tools.
