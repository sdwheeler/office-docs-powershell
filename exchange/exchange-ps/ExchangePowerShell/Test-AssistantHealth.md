---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.ServerStatus-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/test-assistanthealth
schema: 2.0.0
title: Test-AssistantHealth
---

# Test-AssistantHealth

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the Test-AssistantHealth cmdlet to verify that the Microsoft Exchange Mailbox Assistants service (MSExchangeMailboxAssistants) is healthy, to recover from health issues, and to report the status of the diagnosis or recovery action.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Test-AssistantHealth [[-ServerName] <ServerIdParameter>]
 [-Confirm]
 [-IncludeCrashDump]
 [-MaxProcessingTimeInMinutes <UInt32>]
 [-MonitoringContext]
 [-ResolveProblems]
 [-WatermarkBehindWarningThreholdInMinutes <UInt32>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
The Mailbox Assistants service runs on all servers that have the Mailbox server role installed. This service is responsible for scheduling and dispatching several assistants that ensure mailboxes function correctly.

By default, when you run this cmdlet, it returns the RunspaceId, events, and performance counters in a table format.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Test-AssistantHealth -ServerName MBXSVR01 -IncludeCrashDump -ResolveProblems | Format-List
```

This example detects and repairs the mailbox assistant's health on MBXSVR01, includes the error information, and formats the output to a list.

### Example 2
```powershell
Test-AssistantHealth -MaxProcessingTimeInMinutes 30 | Format-List
```

This example detects the mailbox assistant's health on the local Mailbox server. The MaxProcessingTimeInMinutes parameter specifies 30 minutes as the maximum amount of time the service is allowed to process an event without responding, and formats the output to a list.

## PARAMETERS

### -ServerName

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ServerName parameter specifies the Mailbox server where you want to run this command. You can use any value that uniquely identifies the server. For example:

- Name
- FQDN
- Distinguished name (DN)
- Exchange Legacy DN

If you don't use this parameter, the command is run on the local server.

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

### -IncludeCrashDump

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The IncludeCrashDump switch specifies that the command should take an error report prior to taking any recovery actions. You don't need to specify a value with this switch.

You should only use this switch on the local computer. If you use this switch while connected remotely, the command will fail.

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

### -MaxProcessingTimeInMinutes

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The MaxProcessingTimeInMinutes parameter specifies the maximum amount of time the MSExchangeMailboxAssistants service is allowed to process an event without responding. You can specify a value from 1 through 3600 minutes. The default value is 15 minutes.

```yaml
Type: UInt32
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

The MonitoringContext switch includes the associated monitoring events and performance counters in the results. You don't need to specify a value with this switch.

Typically, you include the monitoring events and performance counters in the results when the output is passed to Microsoft System Center Operations Manager (SCOM).

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

### -ResolveProblems

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This ResolveProblems switch specifies that if the command detects an issue, it attempts to fix it. You don't need to specify a value with this switch.

This command attempts to fix the following issues:

- Starts the Mailbox Assistants service if it isn't running.
- Restarts the Mailbox Assistants service if it detects that the service is hung or deadlocked for more than 15 minutes.

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

### -WatermarkBehindWarningThreholdInMinutes

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The WatermarkBehindWarningThreholdInMinutes parameter specifies the threshold for watermark age. Event watermarks indicate the last time that events were successfully processed by an assistant. An event watermark that hasn't been updated in a while may indicate a problem. For each Mailbox Assistant, the Test-AssistantHealth cmdlet compares the current time with the time stamp of the last event watermark to determine the watermark age. If that age exceeds the value set by the WatermarkBehindWarningThreholdInMinutes parameter, a warning is generated.

You can specify a value from 1 through 10080 minutes. The default value is 60 minutes.

```yaml
Type: UInt32
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
