---
applicable: Microsoft Teams
author: tomkau
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml
Locale: en-US
Module Name: MicrosoftTeams
ms.author: tomkau
ms.reviewer: williamlooney
online version: https://learn.microsoft.com/powershell/module/microsoftteams/Remove-CsComplianceRecordingForCallQueueTemplate
schema: 2.0.0
title: Remove-CsComplianceRecordingForCallQueueTemplate
---

# Remove-CsComplianceRecordingForCallQueueTemplate

## SYNOPSIS
Use the Remove-CsComplianceRecordingForCallQueueTemplate cmdlet to delete a Compliance Recording for Call Queues template.

## SYNTAX

```powershell
Remove-CsComplianceRecordingForCallQueueTemplate -Id <String> [<CommonParameters>]
```

## DESCRIPTION
Use the Remove-CsComplianceRecordingForCallQueueTemplate cmdlet to delete a Compliance Recording for Call Queues template. If the template is currently assigned to a call queue, an error will be returned.

> [!CAUTION]
> This cmdlet will only work for customers that are participating in the Voice Applications private preview for this feature. General Availability for this functionality has not been determined at this time.

## EXAMPLES

### Example 1
```
Remove-CsComplianceRecordingForCallQueueTemplate -Id 5e3a575e-1faa-49ff-83c2-5cf1c36c0e01
```

This example deletes the Compliance Recording for Call Queue template with the identity 5e3a575e-1faa-49ff-83c2-5cf1c36c0e01. If no Compliance Recording for Call Queue template exists with the identity 5e3a575e-1faa-49ff-83c2-5cf1c36c0e01, then this example generates an error.

## PARAMETERS

### -Id

> Applicable: Microsoft Teams

The Id parameter is the unique identifier assigned to the Compliance Recording for Call Queue template.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Rtc.Management.OAA.Models.AutoAttendant

## NOTES

## RELATED LINKS

[New-CsComplianceRecordingForCallQueueTemplate](./New-CsComplianceRecordingForCallQueueTemplate.md)

[Set-CsComplianceRecordingForCallQueueTemplate](./Set-CsComplianceRecordingForCallQueueTemplate.md)

[Get-CsComplianceRecordingForCallQueueTemplate](./Get-CsComplianceRecordingForCallQueueTemplate.md)

[Get-CsCallQueue](./Get-CsCallQueue.md)

[New-CsCallQueue](./New-CsCallQueue.md)

[Set-CsCallQueue](./Set-CsCallQueue.md)

[Remove-CsCallQueue](./Remove-CsCallQueue.md)

