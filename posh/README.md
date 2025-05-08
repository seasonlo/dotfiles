# Create Symbolic Links for Oh My Posh Themes

To create symbolic links for all `.omp.json` theme files in the current directory to your Oh My Posh themes directory, follow these steps:

1. Open PowerShell as Administrator

2. Navigate to the directory containing your `.omp.json` files

3. Run the following command:

```powershell
Get-ChildItem -Filter "*.omp.json" | ForEach-Object {
    New-Item -ItemType SymbolicLink -Path "$env:POSH_THEMES_PATH\$($_.Name)" -Target $_.FullName -Force
}
```

This command will create symbolic links for all `.omp.json` files in the current directory to your Oh My Posh themes directory.

# Activate specific themes.

```powershell
Get-Content "profile.ps1" | Add-Content $PROFILE
```

To enable autocomplete, you may need to install PSReadline:

```powershell
Install-Module PSReadLine -RequiredVersion 2.3.6
```