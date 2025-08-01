---
applicable: Exchange Online, Exchange Online Protection
author: chrisda
external help file: Microsoft.Exchange.ServerStatus-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/stop-historicalsearch
schema: 2.0.0
title: Stop-HistoricalSearch
---

# Stop-HistoricalSearch

## SYNOPSIS
This cmdlet is available only in the cloud-based service.

Use the Stop-HistoricalSearch cmdlet to stop an existing historical search that has a status value of NotStarted.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Stop-HistoricalSearch -JobId <Guid>
 [<CommonParameters>]
```

## DESCRIPTION
A historical search provides message trace and report details in a comma-separated value (CSV) file for messages that are less than 90 days old.

After you start a historical search by using the Start-HistoricalSearch cmdlet, the search is queued, but not actually running. While the search is queued and has the status value of NotStarted, you can use the Stop-HistoricalSearch cmdlet to stop it. After the search is actively running, and has a status value of InProgress, you can't stop it. When you stop a historical search, it's given a status value of Cancelled.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Stop-HistoricalSearch -JobId f9c66f83-b5c8-4a0c-91f4-a38376f74182
```

This example stops the historical search that has the JobId value f9c66f83-b5c8-4a0c-91f4-a38376f74182.

## PARAMETERS

### -JobId

> Applicable: Exchange Online, Exchange Online Protection

The JobId parameter specifies the identity GUID value of the historical search that you want to stop.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/p/?LinkID=113216).

## INPUTS

### Input types
To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](https://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data.

## OUTPUTS

### Output types
To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](https://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data.

## NOTES

## RELATED LINKS
