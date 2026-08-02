# Troubleshooting Notes

## Issue 1

Finance folder not found.

### Cause

Sample folder had not yet been created.

### Resolution

Create it first:

```powershell
mkdir "$env:USERPROFILE\Desktop\Finance"
```

---

## Issue 2

Resolve-Path returned an error.

### Cause

Referenced file or folder does not exist.

### Resolution

Verify the path first:

```powershell
Get-ChildItem "$env:USERPROFILE\Desktop"
```

---

## Issue 3

%TEMP%\update.exe could not be resolved.

### Cause

The file was intentionally absent.

### Resolution

Expected behavior during validation. Investigators should confirm whether referenced files actually exist.

---

## Issue 4

Unable to navigate using environment variables.

### Cause

Incorrect variable syntax.

### Resolution

Use:

```powershell
cd $env:USERPROFILE
```

instead of:

```text
%USERPROFILE%
```

inside PowerShell.

---

## Issue 5

Unable to create Payroll.txt.

### Cause

Finance folder did not exist.

### Resolution

Create the folder first:

```powershell
mkdir "$env:USERPROFILE\Desktop\Finance"
```

---

## Issue 6

Cleanup verification returned no output.

### Cause

Folder was successfully removed.

### Resolution

Expected behavior. Verify Desktop contents:

```powershell
Get-ChildItem "$env:USERPROFILE\Desktop"
```

Finance should no longer appear.
