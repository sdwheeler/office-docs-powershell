---
applicable: Microsoft Teams
author: tomkau
external help file: Microsoft.Rtc.Management.dll-Help.xml
Locale: en-US
manager: bulenteg
Module Name: MicrosoftTeams
ms.author: tomkau
ms.reviewer: williamlooney
online version: https://learn.microsoft.com/powershell/module/microsoftteams/get-cscallqueue
schema: 2.0.0
title: Get-CsCallQueue
---

# Get-CsCallQueue

## SYNOPSIS
The Get-CsCallQueue cmdlet returns the identified Call Queues.

## SYNTAX

```
Get-CsCallQueue [-Identity <Guid>] [-Tenant <Guid>] [-First <Int32>] [-Skip <Int32>] [-ExcludeContent <Switch>] [-Sort <String>] [-Descending <Switch>] [-NameFilter <String>] [<CommonParameters>]
```

## DESCRIPTION
The Get-CsCallQueue cmdlet lets you retrieve information about the Call Queues in your organization. Call Queue output contains statistical data on the number of active calls that are in the queue.

## EXAMPLES

### Example 1
```
Get-CsCallQueue
```

This example gets the first 100 call queues in the organization.

### Example 2
```
Get-CsCallQueue -Identity 5e3a575e-1faa-49ff-83c2-5cf1c36c0e01
```

This example gets the Call Queue with the identity 5e3a575e-1faa-49ff-83c2-5cf1c36c0e01. If no Call Queue exists with the identity 5e3a575e-1faa-49ff-83c2-5cf1c36c0e01, then this example generates an error.

## PARAMETERS

### -Descending

> Applicable: Microsoft Teams

The Descending parameter sorts Call Queues in descending order

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeContent

> Applicable: Microsoft Teams

The ExcludeContent parameter only displays the Name and Id of the Call Queues

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -First

> Applicable: Microsoft Teams

The First parameter gets the first N Call Queues, up to a maximum of 100 at a time.
When not specified, the default behavior is to return the first 100 call queues. It is intended to be used in conjunction with the `-Skip` parameter for pagination purposes.
If a number greater than 100 is supplied, the request will fail.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity

> Applicable: Microsoft Teams

PARAMVALUE: Guid

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NameFilter

> Applicable: Microsoft Teams

The NameFilter parameter returns Call Queues where name contains specified string

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Skip

> Applicable: Microsoft Teams

The Skip parameter skips the first N call queues. It is intended to be used in conjunction with the `-First` parameter for pagination purposes.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sort

> Applicable: Microsoft Teams

The Sort parameter specifies the property used to sort.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: Name
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tenant

> Applicable: Microsoft Teams

PARAMVALUE: Guid

```yaml
Type: Guid
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

### Identity
Represents the unique identifier of a Call Queue.

## OUTPUTS

### Microsoft.Rtc.Management.Hosted.CallQueue.Models.CallQueue

## NOTES

## RELATED LINKS
