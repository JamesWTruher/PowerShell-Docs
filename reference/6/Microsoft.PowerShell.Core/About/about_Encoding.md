---
ms.date:  11/02/2018
schema:  2.0.0
locale:  en-us
keywords:  powershell,cmdlet,provider
title:  about_Encoding
---

# about_Encoding

## SHORT DESCRIPTION

Describes how PowerShell creates files with regard to text encoding; including
the encoding used when PowerShell exchanges strings with native applications.

## LONG DESCRIPTION

### PowerShell History

Historically, when Windows PowerShell 5.1 and earlier versions created a text
file, the encoding used in creating the file would be different based on the
command used to create the file. Additionally, the type of the encoding
parameter varied from cmdlet to cmdlet. The following table shows the cmdlet
and the default encoding used:

| Cmdlet Name | Encoding | Parameter Type |
| --- | --- | --- |
| Add-Content | ASCII | FileSystemCmdletProviderEncoding |
| Export-Clixml | UTF16 | string |
| Export-CSV | ASCII | string |
| Out-File | UTF16 | string |
| New-ModuleManifest | UTF16 | N/A |
| Get-Content | N/A | FileSystemCmdletProviderEncoding |
| Set-Content | ASCII | FileSystemCmdletProviderEncoding |
| Export-PSSession | UTF8 (with Byte Order Mark) | string |
| Redirection | UTF16 | N/A |
| Send-MailMessage | UTF16 | System.Text.Encoding |

Additionally, the type of the encoding parameter varied from cmdlet to c
This obviously lead to very inconsistent behavior. This inconsistency became a
greater issue when viewed from a cross-platform perspective because of the
differences that Windows and non-Windows platforms behave. This makes exchanging
files between systems extremely difficult.

### PowerShell 6

In PowerShell 6, the decision was to unify encoding across all cmdlets which had
an Encoding parameter to simplify the experience and create consistency when
creating files.

## EXAMPLE

## SEE ALSO

[about_Providers](about_Providers.md)