---
applicable: Microsoft Teams
author: serdarsoysal
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml
Locale: en-US
manager: bulenteg
Module Name: MicrosoftTeams
ms.author: serdars
online version: https://learn.microsoft.com/powershell/module/microsoftteams/get-csteamscallingpolicy
schema: 2.0.0
title: Get-CsTeamsCallingPolicy
---

# Get-CsTeamsCallingPolicy

## SYNOPSIS

Returns information about the teams calling policies configured for use in your organization.
Teams calling policies help determine which users are able to use calling functionality within Microsoft Teams.

## SYNTAX

### Identity (Default)
```
Get-CsTeamsCallingPolicy [[-Identity] <string>] [<CommonParameters>]
```

### Filter
```
Get-CsTeamsCallingPolicy [-Filter <string>] [<CommonParameters>]
```

## DESCRIPTION

Returns information about the teams calling policies configured for use in your organization.
Teams calling policies help determine which users are able to use calling functionality within Microsoft Teams and interoperability with Skype for Business.

## EXAMPLES

### Example 1
```powershell
Get-CsTeamsCallingPolicy -Identity SalesCallingPolicy
```

Retrieves the calling policy with the Identity "SalesCallingPolicy".

### Example 2
```powershell
Get-CsTeamsCallingPolicy -Filter "tag:Sales*"
```

Retrieves the calling policies with Identity starting with Sales.

## PARAMETERS

### -Filter
Enables you to use wildcard characters when indicating the policy (or policies) to be returned.
To return a collection of all the per-user policies, use this syntax: -Filter "tag:*".

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Specify the TeamsCallingPolicy that you would like to retrieve.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Set-CsTeamsCallingPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/set-csteamscallingpolicy)

[Remove-CsTeamsCallingPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/remove-csteamscallingpolicy)

[Grant-CsTeamsCallingPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/grant-csteamscallingpolicy)

[New-CsTeamsCallingPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/new-csteamscallingpolicy)
