---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.ServerStatus-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/test-smtpconnectivity
schema: 2.0.0
title: Test-SmtpConnectivity
---

# Test-SmtpConnectivity

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the Test-SmtpConnectivity cmdlet to diagnose whether an SMTP connection can successfully be established to the Receive connectors on a specific server. Although you can run this cmdlet manually to verify SMTP connectivity for a specified server, it's primarily used by Microsoft System Center Operations Manager 2007 to test your transport servers' ability to receive SMTP connections to each of the bindings on all the Receive connectors on those servers.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Test-SmtpConnectivity [[-Identity] <ServerIdParameter>]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-MonitoringContext <Boolean>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
When you run the Test-SmtpConnectivity cmdlet against a Mailbox server, the cmdlet attempts to establish an SMTP connection to all bindings of all Receive connectors hosted on that server. For each attempt, the cmdlet returns the following information:

- Server: The name of the server that hosts the Receive connector.
- ReceiveConnector: The name of the Receive connector to which the SMTP connection was attempted.
- Binding: The binding that was configured on the Receive connector.
- EndPoint: The actual IP address and port to which the SMTP connection was attempted.
- StatusCode: The result of the connection attempt. This can be one of the following values: Success, Unable to connect, Transient error, Permanent error, External error.
- Details: The actual response received from the server being tested. If the connection attempt isn't successful, this field contains an error string.

You can write the results to a file by piping the output to ConvertTo-Html or ConvertTo-Csv and adding ` > <filename>` to the command. For example: `Test-SmtpConnectivity Mailbox01 | ConvertTo-Csv > "C:\My Documents\SMTP Test.csv"`.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Test-SmtpConnectivity Mailbox01
```

This example verifies SMTP connectivity for all Receive connectors on the Mailbox server named Mailbox01.

### Example 2
```powershell
Get-TransportService | Test-SmtpConnectivity
```

This example verifies SMTP connectivity for all Receive connectors on all Mailbox servers in the organization.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Identity parameter specifies the transport server for which the cmdlet verifies SMTP connectivity .

The Identity parameter specifies the transport server where you want to verify SMTP connectivity (test all Receive connectors on the specified server). You can use any value that uniquely identifies the server. For example:

- Name
- FQDN
- Distinguished name (DN)
- Exchange Legacy DN

 If you don't use this parameter, all Receive connectors on the local server are tested.

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

### -MonitoringContext

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The MonitoringContext parameter specifies whether to include the associated monitoring events and performance counters in the results. Valid values are:

- $true: Monitoring events and performance counters are included in the command results. Typically, you include the monitoring events and performance counters in the results when the output is passed to Microsoft System Center Operations Manager (SCOM).
- $false: Monitoring events and performance counters aren't included in the command results. This is the default value.

```yaml
Type: Boolean
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
