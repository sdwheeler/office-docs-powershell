---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.TransportMailControl-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/get-ipblocklistprovidersconfig
schema: 2.0.0
title: Get-IPBlockListProvidersConfig
---

# Get-IPBlockListProvidersConfig

## SYNOPSIS
This cmdlet is available or effective only on Edge Transport servers in on-premises Exchange.

Use the Get-IPBlockListProvidersConfig cmdlet to view the settings that affect all IP Block list providers that are configured on an Edge Transport server.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Get-IPBlockListProvidersConfig [-DomainController <Fqdn>]
 [<CommonParameters>]
```

## DESCRIPTION
On Edge Transport servers, IP Block list providers are used by the Connection Filtering agent. The Connection Filtering agent acts on the IP address of the incoming SMTP connection to determine what action, if any, to take on an incoming message.

On Edge Transport servers, you need to be a member of the local Administrators group to run this cmdlet.

## EXAMPLES

### Example 1
```powershell
Get-IPBlockListProvidersConfig | Format-List
```

This example returns detailed information about the IP Block list providers on the local Edge Transport server.

## PARAMETERS

### -DomainController

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The DomainController parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, dc01.contoso.com.

The DomainController parameter isn't supported on Edge Transport servers. An Edge Transport server uses the local instance of Active Directory Lightweight Directory Services (AD LDS) to read and write data.

```yaml
Type: Fqdn
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/p/?LinkID=113216).

## INPUTS

### Input types
To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](https://go.microsoft.com/fwlink/p/?LinkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data.

## OUTPUTS

### Output types
To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](https://go.microsoft.com/fwlink/p/?LinkId=616387). If the Output Type field is blank, the cmdlet doesn't return data.

## NOTES

## RELATED LINKS
