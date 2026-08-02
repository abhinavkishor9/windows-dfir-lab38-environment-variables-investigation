# Investigation Timeline

| Time | Activity | Evidence |
|------|----------|----------|
| 09:00 | Created investigation workspace | EnvironmentVariablesLab |
| 09:05 | Enumerated environment variables | Get-ChildItem Env: |
| 09:10 | Reviewed common variables | USERPROFILE, APPDATA, TEMP |
| 09:15 | Navigated using USERPROFILE | PowerShell |
| 09:20 | Examined user profile folders | Desktop, Downloads, AppData |
| 09:25 | Navigated to Roaming AppData | APPDATA |
| 09:30 | Navigated to Temp directory | TEMP |
| 09:35 | Created Finance folder | Desktop |
| 09:40 | Created Payroll.txt | Finance |
| 09:45 | Resolved logical paths | Resolve-Path |
| 09:50 | Validated investigation paths | Existing & Missing Paths |
| 09:55 | Removed lab artifacts | Cleanup |

---

# Investigation Flow

Investigation Started

↓

Created Lab Workspace

↓

Enumerated Environment Variables

↓

Reviewed Common Variables

↓

Navigated Using Environment Variables

↓

Examined User Profile

↓

Validated AppData

↓

Validated Temp Directory

↓

Created Sample Artifact

↓

Resolved Logical Paths

↓

Validated Investigation Paths

↓

Removed Lab Artifacts

↓

Investigation Completed

---

# Summary

The investigation demonstrated how Windows Environment Variables can be analyzed using native Windows PowerShell to resolve logical paths into actual filesystem locations. By enumerating variables, navigating user directories, validating path resolution, creating sample artifacts, and correlating logical versus physical paths, the lab illustrated a practical DFIR workflow commonly used during malware analysis and host-based investigations.
