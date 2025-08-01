---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection
author: chrisda
external help file: Microsoft.Exchange.RecordsandEdge-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/set-adminauditlogconfig
schema: 2.0.0
title: Set-AdminAuditLogConfig
---

# Set-AdminAuditLogConfig

## SYNOPSIS
This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

Use the Set-AdminAuditLogConfig cmdlet to configure the administrator audit logging configuration settings.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Set-AdminAuditLogConfig [[-Identity] <OrganizationIdParameter>]
 [-AdminAuditLogAgeLimit <EnhancedTimeSpan>]
 [-AdminAuditLogCmdlets <MultiValuedProperty>]
 [-AdminAuditLogEnabled <Boolean>]
 [-AdminAuditLogExcludedCmdlets <MultiValuedProperty>]
 [-AdminAuditLogParameters <MultiValuedProperty>]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-Force]
 [-LogLevel <AuditLogLevel>]
 [-Name <String>]
 [-TestCmdletLoggingEnabled <Boolean>]
 [-UnifiedAuditLogIngestionEnabled <Boolean>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
When audit logging is enabled, a log entry is created for each cmdlet run, excluding Get cmdlets. Log entries are stored in a hidden mailbox and accessed using the Search-AdminAuditLog or New-AdminAuditLogSearch cmdlets.

The Set-AdminAuditLogConfig, Enable-CmdletExtensionAgent, and Disable-CmdletExtensionAgent cmdlets are logged when they're run regardless of whether administrator audit logging is enabled or disabled.

Administrator audit logging relies on Active Directory replication to replicate the configuration settings you specify to the domain controllers in your organization. Depending on your replication settings, the changes you make may not be immediately applied to all Exchange servers in your organization.

Changes to the audit log configuration may take up to 60 minutes to be applied on computers that have the Exchange Management Shell open at the time a configuration change is made. If you want to apply the changes immediately, close and reopen the Exchange Management Shell on each computer.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Set-AdminAuditLogConfig -AdminAuditLogEnabled $true -AdminAuditLogCmdlets * -AdminAuditLogParameters * -AdminAuditLogExcludedCmdlets Get-*
```

This example enables administrator audit logging for every cmdlet and every parameter in the organization, with the exception of Get cmdlets.

### Example 2
```powershell
Set-AdminAuditLogConfig -AdminAuditLogEnabled $true -AdminAuditLogCmdlets *Mailbox, *Management*, *TransportRule* -AdminAuditLogParameters *
```

This example enables administrator audit logging for specific cmdlets run in the organization. Any parameter used on the specified cmdlets is logged. Every time a specified cmdlet is run, a log entry is added to the audit log.

### Example 3
```powershell
Set-AdminAuditLogConfig -AdminAuditLogEnabled $true -AdminAuditLogCmdlets *Mailbox* -AdminAuditLogParameters *Address*
```

This example enables administrator audit logging only for specific parameters that are specified when running specific cmdlets. The parameter name and the cmdlet name must match the strings specified with the AdminAuditLogCmdlets and AdminAuditLogParameters parameters. For example, a log entry is generated only when a parameter with the string "Address" in the name is run on a cmdlet with the string "Mailbox" in its name.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This parameter is available only in on-premises Exchange.

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

### -AdminAuditLogAgeLimit

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This parameter is available only in on-premises Exchange.

The AdminAuditLogAgeLimit parameter specifies how long each log entry should be kept before it's deleted. The default age limit is 90 days.

To specify a value, enter it as a time span: dd.hh:mm:ss where dd = days, hh = hours, mm = minutes, and ss = seconds.

For example, to set the audit log age limit to 120 days, use the syntax 120.00:00:00.

Setting the age limit to a value less than the current limit causes log entries older than the new limit to be deleted.

Setting the age limit to 0 purges the audit log of all entries.

```yaml
Type: EnhancedTimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdminAuditLogCmdlets

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This parameter is available only in on-premises Exchange.

The AdminAuditLogCmdlets parameter specifies which cmdlets should be audited. You can specify one or more cmdlets, separated by commas. You can also use the wildcard character (\*) to match multiple cmdlets in one or more of the entries in the cmdlet list. To audit all cmdlets, specify only the wildcard character (\*).

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdminAuditLogEnabled

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This parameter is available only in on-premises Exchange.

The AdminAuditLogEnabled parameter specifies whether administrator audit logging is enabled. Valid values are:

- $true: Administrator audit logging is enabled. This is the default value.
- $false: Administrator audit logging is disabled.

You must specify an administrator audit log mailbox before you enable logging.

Changes to the administrator audit log configuration are always logged, regardless of whether audit logging is enabled or disabled.

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

### -AdminAuditLogExcludedCmdlets

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This parameter is available only in on-premises Exchange.

The AdminAuditLogExcludedCmdlets parameter specifies which cmdlets should be excluded from auditing. Use this parameter if you want to exclude specific cmdlets you don't want to audit even if they match a wildcard string specified in the AdminAuditLogCmdlets parameter.

You can specify one or more cmdlets, separated by commas. You can also use the wildcard character (\*) to match multiple cmdlets in one or more of the entries in the cmdlet list. You can't specify only the wildcard character (\*).

If you want to clear the list, specify a value of $null.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdminAuditLogParameters

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This parameter is available only in on-premises Exchange.

The AdminAuditLogParameters parameter specifies which parameters should be audited on the cmdlets you specified using the AdminAuditLogCmdlets parameter. You can specify one or more parameters, separated by commas. You can also use the wildcard character (\*) to match multiple parameters in one or more of the entries in the parameters list. To audit all parameters, specify only the wildcard character (\*).

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

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

This parameter is available only in on-premises Exchange.

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

### -Force

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The Force switch hides warning or confirmation messages. You don't need to specify a value with this switch.

You can use this switch to run tasks programmatically where prompting for administrative input is inappropriate.

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

### -LogLevel

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This parameter is available only in on-premises Exchange.

The LogLevel parameter specifies whether additional properties should be included in the log entries. Valid values are:

- None: The CmdletName, ObjectName, Parameters (values), and the Caller, Succeeded and RunDate properties are included in log entries. This is the default value.
- Verbose: The ModifiedProperties (old and new) and ModifiedObjectResolvedName properties are also included in log entries.

```yaml
Type: AuditLogLevel
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This parameter is available only in on-premises Exchange.

The Name parameter specifies the name of the AdminAuditLogConfig object.

You don't need to specify this parameter when you configure administrator audit logging. It doesn't affect your configuration or how administrator audit logging works.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TestCmdletLoggingEnabled

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This parameter is available only in on-premises Exchange.

The TestCmdletLoggingEnabled parameter specifies whether test cmdlets (cmdlet names that begin with the verb Test) results are included in admin audit logging. Valid values are:

- $true: Test cmdlets are included in admin audit logging.
- $false: Test cmdlets aren't included in admin audit logging. This is the default value.

Test cmdlets can produce a large amount of information. As such, you should only enable logging of test cmdlets for a short period of time.

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

### -UnifiedAuditLogIngestionEnabled

> Applicable: Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

This parameter is functional only in the cloud-based service.

The UnifiedAuditLogIngestionEnabled parameter specifies whether to enable or disable the recording of user and admin activities in the Microsoft 365 audit log. Valid values are:

- $true: User and admin activities are recorded in the Microsoft 365 audit log, and admins can search the Microsoft 365 audit log. This is the default value.
- $false: User and admin activities aren't recorded in the Microsoft 365 audit log, and admins can't search the Microsoft 365 audit log.

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

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

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
