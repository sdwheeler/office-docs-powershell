---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.TransportMailflow-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/install-transportagent
schema: 2.0.0
title: Install-TransportAgent
---

# Install-TransportAgent

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the Install-TransportAgent cmdlet to register transport agents on Exchange servers.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Install-TransportAgent [-Name] <String> -AssemblyPath <String> -TransportAgentFactory <String>
 [-Confirm]
 [-DomainController <Fqdn>]
 [-TransportService <TransportService>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Transport agents have full access to all email messages that they encounter. Exchange puts no restrictions on a transport agent's behavior. Transport agents that are unstable or contain security flaws may affect the stability and security of Exchange. Therefore, you need to only install transport agents that you fully trust and that have been fully tested.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Install-TransportAgent -Name "Test App" -TransportAgentFactory "vendor.exchange.avTransportAgentfactory" -AssemblyPath "c:\Program Files\Vendor\TransportAgent\AvTransportAgentFactory.dll" -TransportService Hub
```

This example shows how a fictitious application named Test App is installed in the Transport service on a Mailbox server.

## PARAMETERS

### -Name

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Name parameter specifies the display name of the transport agent to be installed. The length of the name can't exceed 64 characters.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AssemblyPath

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The AssemblyPath parameter specifies the location of the transport agent Microsoft.NET assembly. Universal Naming Convention (UNC) file paths can't be used.

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

### -TransportAgentFactory

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The TransportAgentFactory parameter specifies the Microsoft.NET class type of the transport agent factory. The developer of the transport agent being installed provides the transport agent factory and related information. For more information, see the documentation provided by the developer of the transport agent.

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

### -Confirm

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Confirm switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding.

- Destructive cmdlets (for example, Remove-\* cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.
- Most other cmdlets (for example, New-\* and Set-\* cmdlets) don't have a built-in pause. For these cmdlets, specifying the Confirm switch without a value introduces a pause that forces you acknowledge the command before proceeding.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -TransportService

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The TransportService parameter specifies the transport service that you want to view or modify. Valid values for this parameter are:

- Hub for the Transport service on Mailbox servers.
- MailboxSubmission for the Mailbox Transport Submission service on Mailbox servers.
- MailboxDelivery for the Mailbox Transport Delivery service on Mailbox servers.
- FrontEnd for the Front End Transport service on Mailbox servers.
- Edge on Edge Transport servers.

```yaml
Type: TransportService
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The WhatIf switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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
