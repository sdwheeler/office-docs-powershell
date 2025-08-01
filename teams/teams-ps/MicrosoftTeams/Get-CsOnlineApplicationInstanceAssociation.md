---
applicable: Microsoft Teams
author: tomkau
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml
Locale: en-US
manager: bulenteg
Module Name: MicrosoftTeams
ms.author: tomkau
ms.reviewer: williamlooney
online version: https://learn.microsoft.com/powershell/module/microsoftteams/get-csonlineapplicationinstanceassociation
schema: 2.0.0
title: Get-CsOnlineApplicationInstanceAssociation
---

# Get-CsOnlineApplicationInstanceAssociation

## SYNOPSIS
Use the Get-CsOnlineApplicationInstanceAssociation cmdlet to get information about the associations setup in your organization.

## SYNTAX

```
Get-CsOnlineApplicationInstanceAssociation -Identity <String> [-Tenant <Guid>] [<CommonParameters>]
```

## DESCRIPTION
Use the Get-CsOnlineApplicationInstanceAssociation cmdlet to get information about the associations setup between online application instances and the application configurations, like auto attendants and call queues.

## EXAMPLES

### Example 1
```powershell
Get-CsOnlineApplicationInstanceAssociation -Identity "f7a821dc-2d69-5ae8-8525-bcb4a4556093"
```

This example gets the association object for the application instance that has the identity of f7a821dc-2d69-5ae8-8525-bcb4a4556093.

## PARAMETERS

### -Identity

> Applicable: Microsoft Teams

The identity for the application instance whose association is to be retrieved.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -Tenant

> Applicable: Microsoft Teams

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
The Get-CsOnlineApplicationInstanceAssociation cmdlet accepts a string as the Identity parameter.

## OUTPUTS

### Microsoft.Rtc.Management.Hosted.Online.Models.ApplicationInstanceAssociation

## NOTES

## RELATED LINKS

[Get-CsOnlineApplicationInstanceAssociationStatus](https://learn.microsoft.com/powershell/module/microsoftteams/get-csonlineapplicationinstanceassociationstatus)

[New-CsOnlineApplicationInstanceAssociation](https://learn.microsoft.com/powershell/module/microsoftteams/new-csonlineapplicationinstanceassociation)

[Remove-CsOnlineApplicationInstanceAssociation](https://learn.microsoft.com/powershell/module/microsoftteams/remove-csonlineapplicationinstanceassociation)
