# Microsoft Graph - The Missing PowerShell Format Files

This module supplies additional format files you can use with the Microsoft.Graph and Microsoft.Graph.Beta PowerShell Modules.

The default output for many of the commands in the Microsoft GRaph modules outputs a table with all properties in an unhelpful order.  These format files will display more relevant information, and provide some additional quality of life improvments such as conditional formatting (ex. red for non-compliant status and green for compliant) and clickable links that will open the objects portal page.

Note: Colorization and clickable hyperlinks require PowerShell 6+ and the use of an ANSI terminal like Windows Terminal.

## Example - Get-MGBetaDeviceManagementManagedDevice 

This is the default output for a Managed Device object with the beta module:

![Image of the default output, showing properties Id,AadRegistered, ActivationLockByPassCode,AndroidSecurityPatchLevel and AutoPilotEnrolled](<Images/Screenshot 2025-07-24 113158.png>)

This is the output with the missing format file:

![Image of the new output, showing properties DeviceName, UserPrincipalName, UserDisplayName, OSVersion, SerialNumber and ComplianceState](<Images/Screenshot 2025-07-24 112045.png>)

With clickable link of course!

![Image of the new output showing the DeviceName is a clickable link](<Images/Screenshot 2025-07-24 112143.png>)

## Installation

Clone the repository to your local machine:

```powershell
git clone https://github.com/TheRealZero/MGMissingFormatFiles.git
```

Then import the format files into your PowerShell session:

```powershell
Get-ChildItem -Path .\MGMissingFormatFiles\*.format.ps1xml | ForEach-Object { Import-FormatData -PrependPath $_.FullName }
```

You can add this command to your PowerShell profile to automatically import the format files in every session.