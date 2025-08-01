---
applicable: Microsoft Teams
author: tomkau
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml
Locale: en-US
manager: bulenteg
Module Name: MicrosoftTeams
ms.author: tomkau
ms.reviewer: williamlooney
online version: https://learn.microsoft.com/powershell/module/microsoftteams/remove-csonlineschedule
schema: 2.0.0
title: Remove-CsOnlineSchedule
---

# Remove-CsOnlineSchedule

## SYNOPSIS
Use the Remove-CsOnlineSchedule cmdlet to remove a schedule.

## SYNTAX
```
Remove-CsOnlineSchedule -Id <String> [-Tenant <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The Remove-CsOnlineSchedule cmdlet deletes a schedule that is specified by using the Id parameter.

## EXAMPLES

### Example 1
```
Remove-CsOnlineSchedule -Id "fa9081d6-b4f3-5c96-baec-0b00077709e5"
```

This example deletes the schedule that has an Id of fa9081d6-b4f3-5c96-baec-0b00077709e5.

## PARAMETERS

### -Id

> Applicable: Microsoft Teams

The Id for the schedule to be removed.

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
The Remove-CsOnlineSchedule cmdlet accepts a string as the Id parameter.

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS

[New-CsOnlineSchedule](https://learn.microsoft.com/powershell/module/microsoftteams/new-csonlineschedule)

[Set-CsOnlineSchedule](https://learn.microsoft.com/powershell/module/microsoftteams/set-csonlineschedule)
