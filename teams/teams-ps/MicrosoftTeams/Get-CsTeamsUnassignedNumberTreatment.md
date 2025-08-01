---
applicable: Microsoft Teams
author: serdarsoysal
external help file: Microsoft.Open.Teams.CommonLibrary.dll-Help.xml
Locale: en-US
Module Name: MicrosoftTeams
ms.author: serdars
online version: https://learn.microsoft.com/powershell/module/microsoftteams/get-csteamsunassignednumbertreatment
schema: 2.0.0
title: Get-CsTeamsUnassignedNumberTreatment
---

# Get-CsTeamsUnassignedNumberTreatment

## SYNOPSIS
Displays a specific or all treatments for how calls to an unassigned number range should be routed.

## SYNTAX

### Identity (Default)
```
Get-CsTeamsUnassignedNumberTreatment [[-Identity] <String>] [-MsftInternalProcessingMode <String>]
 [<CommonParameters>]
```

### Filter
```
Get-CsTeamsUnassignedNumberTreatment [-MsftInternalProcessingMode <String>] [-Filter <String>]
 [<CommonParameters>]
```

## DESCRIPTION
This cmdlet displays a specific or all treatments for how calls to an unassigned number range should be routed.

## EXAMPLES

### Example 1
```powershell
Get-CsTeamsUnassignedNumberTreatment -Identity MainAA
```
This example displays the treatment MainAA.

### Example 2
```powershell
Get-CsTeamsUnassignedNumberTreatment
```
This example displays all configured treatments.

### Example 3
```powershell
Get-CsTeamsUnassignedNumberTreatment -Filter Ann*
```
This example displays all configured treatments with an Identity starting with Ann.

## PARAMETERS

### -Filter

> Applicable: Microsoft Teams

Enables you to limit the returned data by filtering on the Identity attribute.

```yaml
Type: System.String
Parameter Sets: Filter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
The Id of the specific treatment to show.

```yaml
Type: System.String
Parameter Sets: Identity
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MsftInternalProcessingMode
{{ Fill MsftInternalProcessingMode Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES
The cmdlet is available in Teams PS module 2.5.1 or later.

## RELATED LINKS

[Remove-CsTeamsUnassignedNumberTreatment](https://learn.microsoft.com/powershell/module/microsoftteams/remove-csteamsunassignednumbertreatment)

[New-CsTeamsUnassignedNumberTreatment](https://learn.microsoft.com/powershell/module/microsoftteams/new-csteamsunassignednumbertreatment)

[Set-CsTeamsUnassignedNumberTreatment](https://learn.microsoft.com/powershell/module/microsoftteams/set-csteamsunassignednumbertreatment)
