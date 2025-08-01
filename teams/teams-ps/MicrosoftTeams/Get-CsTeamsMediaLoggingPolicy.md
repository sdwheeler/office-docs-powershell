---
applicable: Microsoft Teams
author: LeoKuhorev
external help file: Microsoft.TeamsCmdlets.PowerShell.Custom.dll-Help.xml
Locale: en-US
manager: shalages
Module Name: MicrosoftTeams
ms.author: leokukharau
online version: https://learn.microsoft.com/powershell/module/microsoftteams/get-csteamsmedialoggingpolicy
schema: 2.0.0
title: Get-CsTeamsMediaLoggingPolicy
---

# Get-CsTeamsMediaLoggingPolicy

## SYNOPSIS

Returns information about the Teams Media Logging policy.

## SYNTAX

### Identity (Default)

```
Get-CsTeamsMediaLoggingPolicy [[-Identity] <String>] [<CommonParameters>]
```

### Filter

```
Get-CsTeamsMediaLoggingPolicy [-Filter <String>] [<CommonParameters>]
```

## DESCRIPTION

Returns information about the Teams Media Logging policy.
TeamsMediaLoggingPolicy allows administrators to enable media logging for users. When assigned, it will enable media logging for the user overriding other settings. After removing the policy, media logging setting will revert to the previous value.

NOTES:
TeamsMediaLoggingPolicy has only one instance that is built into the system, so there is no corresponding New cmdlet.

## EXAMPLES

### EXAMPLE 1

```PowerShell
PS C:\> Get-CsTeamsMediaLoggingPolicy
```

Return information for all Teams Media Logging policies available for use in the tenant.

### EXAMPLE 2

```PowerShell
PS C:\> Get-CsTeamsMediaLoggingPolicy -Identity Global
```

Return Teams Media Logging policy that is set for the entire tenant.

## PARAMETERS

### -Filter

> Applicable: Microsoft Teams

Enables using wildcards when specifying the policy (or policies) to be retrieved.
Note that you cannot use both the Filter and the Identity parameters in the same command.

```yaml
Type: String
Parameter Sets: Filter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity

> Applicable: Microsoft Teams

Unique identifier assigned to the Teams Media Logging policy. Note that Teams Media Logging policy has only one instance that has Identity "Enabled".

Use the "Global" Identity if you wish to retrieve the policy set for the entire tenant.

```yaml
Type: String
Parameter Sets: Identity
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```
### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Grant-CsTeamsMediaLoggingPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/grant-csteamsmedialoggingpolicy)
