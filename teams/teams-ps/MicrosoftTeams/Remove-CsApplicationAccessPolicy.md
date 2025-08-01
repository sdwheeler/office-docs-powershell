---
applicable: Microsoft Teams
author: frankpeng7
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: zhengni
Module Name: MicrosoftTeams
ms.author: frpeng
online version: https://learn.microsoft.com/powershell/module/microsoftteams/remove-csapplicationaccesspolicy
schema: 2.0.0
title: Remove-CsApplicationAccessPolicy
---

# Remove-CsApplicationAccessPolicy

## SYNOPSIS

Deletes an existing application access policy.

## SYNTAX

### Identity

```
Remove-CsApplicationAccessPolicy [-Identity <XdsIdentity>] [<CommonParameters>]
```

## DESCRIPTION

This cmdlet deletes an existing application access policy.

## EXAMPLES

### Remove an application access policy

```
PS C:\> Remove-CsApplicationAccessPolicy -Identity "ASimplePolicy"
```

The command shown above deletes the application access policy ASimplePolicy.

## PARAMETERS

### -Identity

Unique identifier assigned to the policy when it was created.

```yaml
Type: XdsIdentity
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-CsApplicationAccessPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/new-csapplicationaccesspolicy)
[Grant-CsApplicationAccessPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/new-csapplicationaccesspolicy)
[Get-CsApplicationAccessPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/new-csapplicationaccesspolicy)
[Set-CsApplicationAccessPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/new-csapplicationaccesspolicy)
