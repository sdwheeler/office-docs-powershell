---
applicable: Exchange Online
author: chrisda
external help file: Microsoft.Exchange.TransportMailflow-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/get-perimeterconfig
schema: 2.0.0
title: Get-PerimeterConfig
---

# Get-PerimeterConfig

## SYNOPSIS
This cmdlet is available only in the cloud-based service.

Use the Get-PerimeterConfig cmdlet to view the list of gateway server and internal mail server IP addresses that have been added to the cloud-based safelists.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Get-PerimeterConfig [[-Identity] <OrganizationIdParameter>]
 [<CommonParameters>]
```

## DESCRIPTION
If you have an on-premises email system, you can use the Set-PerimeterConfig cmdlet to add the IP addresses of your gateway servers to cloud-based safelists (also known as whitelists) to make sure that messages sent from your on-premises email system aren't treated as spam.

## EXAMPLES

### Example 1
```powershell
Get-PerimeterConfig
```

This example returns the list of gateway servers and internal email servers in your organization that have been added to cloud-based safelists.

## PARAMETERS

### -Identity

> Applicable: Exchange Online

This parameter is reserved for internal Microsoft use.

```yaml
Type: OrganizationIdParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
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
