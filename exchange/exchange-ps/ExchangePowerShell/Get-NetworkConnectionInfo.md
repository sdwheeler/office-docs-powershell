---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.TransportMailflow-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/get-networkconnectioninfo
schema: 2.0.0
title: Get-NetworkConnectionInfo
---

# Get-NetworkConnectionInfo

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the Get-NetworkConnectionInfo cmdlet to view the network configuration information for all network adapters configured on the local server.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Get-NetworkConnectionInfo [[-Identity] <ServerIdParameter>]
 [-DomainController <Fqdn>]
 [<CommonParameters>]
```

## DESCRIPTION
This cmdlet retrieves the following configuration information for each network adapter configured on the server:

- Name: This field displays the name of the network adapter. This name indicates the manufacturer and model of the network adapter or the administrator-specified name of the network adapter.
- DnsServers: This field displays the DNS servers used by the network adapter. The server names are separated by commas.
- IPAddresses: This field displays the IP addresses used by the network adapter. The IP addresses are separated by commas.
- AdapterGuid: This field displays the GUID assigned to the network adapter by Windows.
- MacAddress: This field displays the media access control (MAC) address of the network adapter.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Get-NetworkConnectionInfo Mailbox01
```

This example retrieves network configuration information for all network adapters on the server named Mailbox01.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Identity parameter specifies the server you want to query. You can use any value that uniquely identifies the server. For example:

- Name
- FQDN
- Distinguished name (DN)
- Exchange Legacy DN

If you don't use the Identity parameter, the command is run on the local server.

```yaml
Type: ServerIdParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

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
