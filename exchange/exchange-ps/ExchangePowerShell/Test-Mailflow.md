---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.RemoteConnections-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/test-mailflow
schema: 2.0.0
title: Test-Mailflow
---

# Test-Mailflow

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the Test-Mailflow cmdlet to diagnose whether mail can be successfully sent from and delivered to the system mailbox on a Mailbox server. You can also use this cmdlet to verify that email is sent between Mailbox servers within a defined latency threshold.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

### AutoDiscoverTargetMailboxServer
```
Test-Mailflow [[-Identity] <ServerIdParameter>]
 [-AutoDiscoverTargetMailboxServer]
 [-ActiveDirectoryTimeout <Int32>]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-ErrorLatency <Int32>]
 [-ExecutionTimeout <Int32>]
 [-MonitoringContext <Boolean>]
 [-WhatIf]
 [<CommonParameters>]
```

### CrossPremises
```
Test-Mailflow -CrossPremises <Boolean>
 [-ActiveDirectoryTimeout <Int32>]
 [-CrossPremisesExpirationTimeout <EnhancedTimeSpan>]
 [-CrossPremisesPendingErrorCount <Int32>]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-ErrorLatency <Int32>]
 [-ExecutionTimeout <Int32>]
 [-MonitoringContext <Boolean>]
 [-WhatIf]
 [<CommonParameters>]
```

### TargetDatabase
```
Test-Mailflow [[-Identity] <ServerIdParameter>] -TargetDatabase <DatabaseIdParameter>
 [-ActiveDirectoryTimeout <Int32>]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-ErrorLatency <Int32>]
 [-ExecutionTimeout <Int32>]
 [-MonitoringContext <Boolean>]
 [-WhatIf]
 [<CommonParameters>]
```

### TargetEmailAddress
```
Test-Mailflow [[-Identity] <ServerIdParameter>] -TargetEmailAddress <String>
 [-TargetEmailAddressDisplayName <String>]
 [-ActiveDirectoryTimeout <Int32>]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-ErrorLatency <Int32>]
 [-ExecutionTimeout <Int32>]
 [-MonitoringContext <Boolean>]
 [-WhatIf]
 [<CommonParameters>]
```

### TargetMailboxServer
```
Test-Mailflow [[-Identity] <ServerIdParameter>] -TargetMailboxServer <ServerIdParameter>
 [-ActiveDirectoryTimeout <Int32>]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-ErrorLatency <Int32>]
 [-ExecutionTimeout <Int32>]
 [-MonitoringContext <Boolean>]
 [-WhatIf]
 [<CommonParameters>]
```

### SourceServer
```
Test-Mailflow [[-Identity] <ServerIdParameter>]
 [-ActiveDirectoryTimeout <Int32>]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-ErrorLatency <Int32>]
 [-ExecutionTimeout <Int32>]
 [-MonitoringContext <Boolean>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
The Test-Mailflow cmdlet tests mail submission, transport, and delivery. The cmdlet verifies that each Mailbox server can successfully send itself a message. You can also use this cmdlet to verify that the system mailbox on one Mailbox server can successfully send a message to the system mailbox on another Mailbox server. A system mailbox is required on all servers that are involved in the test.

The test messages are available in the target user or system mailbox. The message subject is `Test-Mailflow <GUID>`, and the message body contains the text `This is a Test-Mailflow probe message`.

The Test-Mailflow results are displayed on-screen. The interesting values in the results are:

- TestMailflowResult: The values returned are typically Success or \*FAILURE\*.
- MessageLatencyTime: The time required to complete the test (deliver the test message). The value uses the syntax hh:mm:ss.ffff where hh = hours, mm = minutes, ss = seconds and ffff = fractions of a second.

You can write the Test-Mailflow results to a file by piping the output to ConvertTo-Html or ConvertTo-Csv and adding ` > <filename>` to the command. For example: `Test-Mailflow -AutoDiscoverTargetMailboxServer | ConvertTo-Csv > "C:\My Documents\test-mailflow 2020-05-01.csv"`.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Test-Mailflow Mailbox1 -TargetMailboxServer Mailbox2
```

This example tests message flow from the server name Mailbox1 to the server named Mailbox2. Note that you need to run this command while connected to Mailbox1.

### Example 2
```powershell
Test-Mailflow -TargetEmailAddress john@contoso.com
```

This example tests message flow from the local Mailbox server where you're running this command to the email address john@contoso.com.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Identity parameter specifies the source Mailbox server name from which a test message is sent. You can use any value that uniquely identifies the server. For example:

- Name
- FQDN
- Distinguished name (DN)
- Exchange Legacy DN

If you don't use this parameter, the local Mailbox server is used.

```yaml
Type: ServerIdParameter
Parameter Sets: AutoDiscoverTargetMailboxServer, TargetDatabase, TargetEmailAddress, TargetMailboxServer, SourceServer
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -AutoDiscoverTargetMailboxServer

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The AutoDiscoverTargetMailboxServer switch specifies whether to automatically populate a list of target Mailbox servers to which to send a test message. You don't need to specify a value with this switch.

The task queries Active Directory to discover all Mailbox servers and then sends each server a test message.

When you use this switch, you can't use the CrossPremises, TargetDatabase, TargetEmailAddress or TargetMailboxServer parameters.

```yaml
Type: SwitchParameter
Parameter Sets: AutoDiscoverTargetMailboxServer
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CrossPremises

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The CrossPremises parameter specifies whether the mail flow test will be conducted in cross-premises mode.

Set this parameter to $true if your organization is using a cross-premises deployment and you want to verify cross-premises mail flow.

When you use this parameter, you can't use the AutoDiscoverTargetMailboxServer, TargetDatabase, TargetEmailAddress or TargetMailboxServer parameters.

```yaml
Type: Boolean
Parameter Sets: CrossPremises
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetDatabase

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The TargetDatabase parameter specifies the mailbox database to which test messages are sent. You can use any value that uniquely identifies the database. For example:

- Name
- Distinguished name (DN)
- GUID

You can't use this parameter with the AutoDiscoverTargetMailboxServer, CrossPremises, TargetEmailAddress or TargetMailboxServer parameters.

```yaml
Type: DatabaseIdParameter
Parameter Sets: TargetDatabase
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetEmailAddress

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The TargetEmailAddress parameter specifies the SMTP address of the mailbox to which test messages are sent. Use this parameter to send test messages to a Mailbox server in a remote forest. If this parameter is used, the test is always a remote test.

When you use this parameter, you can't use the AutoDiscoverTargetMailboxServer, CrossPremises, TargetDatabase or TargetMailboxServer parameters.

```yaml
Type: String
Parameter Sets: TargetEmailAddress
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetMailboxServer

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The TargetMailboxServer parameter specifies one or more Mailbox servers in the local Exchange organization to send test messages to. You can use any value that uniquely identifies the server. For example:

- Name
- FQDN
- Distinguished name (DN)
- Exchange Legacy DN

When you use this parameter, you can't use the AutoDiscoverTargetMailboxServer, CrossPremises, TargetDatabase or TargetEmailAddress parameters.

```yaml
Type: ServerIdParameter
Parameter Sets: TargetMailboxServer
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ActiveDirectoryTimeout

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ActiveDirectoryTimeout parameter specifies the number of seconds that elapse before the task provides an informational message about the delay. The default value is 15 seconds.

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

### -CrossPremisesExpirationTimeout

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The CrossPremisesExpirationTimeout parameter is used when this cmdlet is run by Microsoft System Center Operations Manager 2007 agents for asynchronous monitoring. We don't recommend using this parameter when running this cmdlet manually.

```yaml
Type: EnhancedTimeSpan
Parameter Sets: CrossPremises
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CrossPremisesPendingErrorCount

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The CrossPremisesPendingErrorCount parameter is used when this cmdlet is run by System Center Operations Manager 2007 agents for asynchronous monitoring. We don't recommend using this parameter when running this cmdlet manually.

```yaml
Type: Int32
Parameter Sets: CrossPremises
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainController

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The DomainController parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, dc01.contoso.com.

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

### -ErrorLatency

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ErrorLatency parameter specifies how long to wait for a test message to be delivered before an error event is logged in Microsoft System Center Operations Manager 2007. The default value when a test message is sent to the local Mailbox server is 15 seconds and 180 seconds when a test message is sent to a remote Mailbox server.

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

### -ExecutionTimeout

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ExecutionTimeout parameter specifies the maximum time that this task can run before the test is determined to be a failure. If no test message or delivery report arrives before this time expires, the task ends and an error is reported. When the task is run in the Exchange Management Shell, the default setting is 240 seconds. When the MonitoringContext parameter is used, the default setting is 15 seconds.

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

### -TargetEmailAddressDisplayName

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The TargetEmailAddressDisplayName parameter specifies a custom display name that's used on events and reports in Microsoft System Center Operations Manager 2007 when the TargetEmailAddress parameter is used. If you don't use the TargetEmailAddressDisplayName parameter, the events and reports use the email address value specified by the TargetEmailAddress parameter.

This parameter is available only with the TargetEmailAddress parameter and has no effect on the output of the cmdlet outside of Microsoft System Center Operations Manager.

```yaml
Type: String
Parameter Sets: TargetEmailAddress
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
