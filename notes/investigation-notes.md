# Investigation Notes

## Lab Summary

This investigation focused on understanding and analyzing Windows Environment Variables using native Windows tools and PowerShell.

The investigation demonstrated how environment variables resolve to actual filesystem locations, how attackers frequently abuse these variables to hide file locations, and how investigators can validate logical paths against physical directories.

---

## Analyst Methodology

1. Create investigation workspace.
2. Enumerate Windows Environment Variables.
3. Examine commonly used variables.
4. Navigate using environment variables.
5. Validate resolved filesystem locations.
6. Create sample artifacts.
7. Correlate logical and physical paths.
8. Resolve investigation paths.
9. Remove lab artifacts.
10. Document findings.

---

## Investigation Scenario

An analyst discovers multiple paths inside a suspicious PowerShell script:

- %USERPROFILE%\Desktop\Finance
- %APPDATA%\Microsoft
- %TEMP%\update.exe

The investigation aims to determine:

- What each environment variable represents.
- Which physical directory each variable resolves to.
- Whether the referenced paths exist.
- How environment variables can be interpreted during DFIR investigations.

---

## Evidence Collected

### Evidence 1 – Environment Variables

Collected:

- USERPROFILE
- APPDATA
- LOCALAPPDATA
- TEMP
- WINDIR

Finding:

Successfully enumerated system and user environment variables.

---

### Evidence 2 – User Profile Enumeration

Collected:

- Desktop
- Documents
- Downloads
- Pictures
- AppData

Finding:

Verified USERPROFILE resolved correctly.

---

### Evidence 3 – AppData Investigation

Collected:

Roaming AppData contents.

Finding:

Confirmed APPDATA resolves to the Roaming profile directory.

---

### Evidence 4 – Temp Directory

Collected:

Temporary files stored under LOCALAPPDATA\Temp.

Finding:

Validated TEMP variable resolution.

---

### Evidence 5 – Sample Artifact

Collected:

```
Payroll.txt
```

Location:

```
Desktop\Finance
```

Finding:

Successfully created a sample artifact using only environment variables.

---

### Evidence 6 – Logical vs Physical Path Resolution

Command Used

```powershell
Resolve-Path "$env:USERPROFILE\Desktop\Finance"
```

Finding:

Confirmed logical environment variable paths resolve to their actual physical locations.

---

### Evidence 7 – Investigation Path Resolution

Resolved:

- %APPDATA%\Microsoft
- %USERPROFILE%\Desktop
- %TEMP%\update.exe

Finding:

Two paths successfully resolved.

One path (update.exe) did not exist, demonstrating how investigators validate suspicious references.

---

## DFIR Analysis

Environment variables frequently appear within malware, persistence mechanisms, registry entries, scheduled tasks, and PowerShell scripts because they provide portable references to user and system directories.

This investigation demonstrated how PowerShell can resolve these variables into physical paths, enabling investigators to verify artifact locations and determine whether referenced files actually exist.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Discovery | File and Directory Discovery | T1083 |
| Collection | Data from Local System | T1005 |
| Defense Evasion | Indicator Removal on Host (Potential Cleanup) | T1070 |

---

## Analyst Observations

- Environment variables simplify access to important Windows directories.
- Malware commonly references variables instead of full filesystem paths.
- Resolve-Path provides quick validation of logical paths.
- Missing files can be valuable investigative findings.
- PowerShell offers efficient validation without requiring third-party forensic tools.

---

## Conclusion

The investigation successfully demonstrated how Windows Environment Variables can be analyzed during DFIR investigations by resolving logical paths, validating physical directories, correlating evidence, and identifying both existing and missing artifacts using native Windows PowerShell.
