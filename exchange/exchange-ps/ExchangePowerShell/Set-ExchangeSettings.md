---
applicable: Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.ServerStatus-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/set-exchangesettings
schema: 2.0.0
title: Set-ExchangeSettings
---

# Set-ExchangeSettings

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the Set-ExchangeSettings cmdlet to configure Exchange setting objects that you created with the New-ExchangeSettings cmdlet.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

### ClearHistory
```
Set-ExchangeSettings [-Identity] <ExchangeSettingsIdParameter> -Reason <String>
 [-ClearHistory]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-Force]
 [-WhatIf]
 [<CommonParameters>]
```

### UpdateSetting
```
Set-ExchangeSettings [-Identity] <ExchangeSettingsIdParameter> -ConfigName <String> -ConfigValue <String> -Reason <String> [-UpdateSetting]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-Force]
 [-GroupName <String>]
 [-WhatIf]
 [<CommonParameters>]
```

### RemoveSetting
```
Set-ExchangeSettings [-Identity] <ExchangeSettingsIdParameter> -ConfigName <String> -Reason <String> [-RemoveSetting]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-Force]
 [-GroupName <String>]
 [-WhatIf]
 [<CommonParameters>]
```

### CreateSettingsGroup
```
Set-ExchangeSettings [-Identity] <ExchangeSettingsIdParameter> -ExpirationDate <DateTime> -Reason <String>
 [-ConfigPairs <String[]>]
 [-Confirm]
 [-CreateSettingsGroup]
 [-Disable]
 [-DomainController <Fqdn>]
 [-Force]
 [-GroupName <String>]
 [-MaxVersion <String>]
 [-MinVersion <String>]
 [-NameMatch <String>]
 [-Priority <Int32>]
 [-Scope <ExchangeSettingsScope>]
 [-ScopeFilter <String>]
 [-WhatIf]
 [<CommonParameters>]
```

### CreateSettingsGroupGuid
```
Set-ExchangeSettings [-Identity] <ExchangeSettingsIdParameter> -ExpirationDate <DateTime> -GuidMatch <Guid> -Reason <String>
 [-ConfigPairs <String[]>]
 [-Confirm]
 [-CreateSettingsGroup]
 [-Disable]
 [-DomainController <Fqdn>]
 [-Force]
 [-GroupName <String>]
 [-Priority <Int32>]
 [-Scope <ExchangeSettingsScope>]
 [-WhatIf]
 [<CommonParameters>]
```

### CreateSettingsGroupAdvanced
```
Set-ExchangeSettings [-Identity] <ExchangeSettingsIdParameter> -Reason <String> -SettingsGroup <String>
 [-CreateSettingsGroup]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-Force]
 [-WhatIf]
 [<CommonParameters>]
```

### CreateSettingsGroupGeneric
```
Set-ExchangeSettings [-Identity] <ExchangeSettingsIdParameter> -ExpirationDate <DateTime> -Reason <String>
 [-CreateSettingsGroup]
 [-ConfigPairs <String[]>]
 [-GenericScopeName <String>]
 [-GenericScopeValue <String>]
 [-GroupName <String>]
 [-Confirm]
 [-Disable]
 [-DomainController <Fqdn>]
 [-Force]
 [-Priority <Int32>]
 [-Scope <ExchangeSettingsScope>]
 [-WhatIf]
 [<CommonParameters>]
```

### UpdateSettingsGroup
```
Set-ExchangeSettings [-Identity] <ExchangeSettingsIdParameter> -Reason <String>
 [-ExpirationDate <DateTime>]
 [-GroupName <String>]
 [-UpdateSettingsGroup]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-Force]
 [-Priority <Int32>]
 [-ScopeFilter <String>]
 [-WhatIf]
 [<CommonParameters>]
```

### RemoveMultipleSettings
```
Set-ExchangeSettings [-Identity] <ExchangeSettingsIdParameter> -Reason <String> -ConfigPairs <String[]>
 [-GroupName <String>]
 [-RemoveSetting]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-Force]
 [-WhatIf]
 [<CommonParameters>]
```

### RemoveSettingsGroup
```
Set-ExchangeSettings [-Identity] <ExchangeSettingsIdParameter> -Reason <String>
 [-GroupName <String>]
 [-RemoveSettingsGroup]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-Force]
 [-WhatIf]
 [<CommonParameters>]
```

### UpdateSettingsGroupAdvanced
```
Set-ExchangeSettings [-Identity] <ExchangeSettingsIdParameter> -Reason <String> -SettingsGroup <String>
 [-UpdateSettingsGroup]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-Force]
 [-WhatIf]
 [<CommonParameters>]
```

### UpdateMultipleSettings
```
Set-ExchangeSettings [-Identity] <ExchangeSettingsIdParameter> -Reason <String> -ConfigPairs <String[]>
 [-GroupName <String>]
 [-UpdateSetting]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-Force]
 [-WhatIf]
 [<CommonParameters>]
```

### EnableSettingsGroup
```
Set-ExchangeSettings [-Identity] <ExchangeSettingsIdParameter> -Reason <String>
 [-EnableGroup <String>]
 [-DisableGroup <String>]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-Force]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Set-ExchangeSettings Audit -UpdateSetting -ConfigName AuditLogPumperEnabled -ConfigValue $true -Reason "Enable Unified Audit Logging"
```

This example allows users to see the results of Unified Audit Logging. This example assumes that you've already created an Exchange settings object for the Audit configuration schema by running the command New-ExchangeSettings -Name Audit.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2016, Exchange Server 2019

The Identity parameter specifies the name of the existing Exchange settings object that contains the Exchange settings that you want to configure.

The value of this parameter is the value of the Name parameter on the New-ExchangeSetting cmdlet when the Exchange settings object was created.

```yaml
Type: ExchangeSettingsIdParameter
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -ClearHistory

> Applicable: Exchange Server 2016, Exchange Server 2019

The ClearHistory switch specifies that you want to clear the entries in the modification history for the Exchange setting object. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: ClearHistory
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigName

> Applicable: Exchange Server 2016, Exchange Server 2019

The ConfigName parameter specifies the available Exchange setting that you want to add, remove, or update in the Exchange settings object. Valid values for this parameter are determined by the configuration schema that was specified by the Name parameter on the New-ExchangeSettings cmdlet.

For add and update operations, you also need to use the ConfigValue parameter to specify the actual value for the setting. You can't use the ConfigName parameter with the ConfigPairs parameter.

```yaml
Type: String
Parameter Sets: UpdateSetting, RemoveSetting
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigPairs

> Applicable: Exchange Server 2016, Exchange Server 2019

The ConfigName parameter specifies the available Exchange setting that you want to add, remove, or update in the Exchange settings object. Valid values for this parameter are determined by the configuration schema that was specified by the Name parameter on the New-ExchangeSettings cmdlet. The syntax for a value is `<Key>=<Value>`. You can separate multiple values separated by commas.

You can't use the ConfigPairs parameter with the ConfigName or ConfigValue parameters.

```yaml
Type: String[]
Parameter Sets: CreateSettingsGroup, CreateSettingsGroupGuid, CreateSettingsGroupGeneric, RemoveMultipleSettings, UpdateMultipleSettings
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigValue

> Applicable: Exchange Server 2016, Exchange Server 2019

The ConfigValue parameter specifies the value for the Exchange setting that you specified with the ConfigName parameter. The values are determined by the type of setting (a number, a timespan, $true or $false, etc.).

You can't use the ConfigValue parameter with the ConfigPairs parameter.

```yaml
Type: String
Parameter Sets: UpdateSetting
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreateSettingsGroup

> Applicable: Exchange Server 2016, Exchange Server 2019

The CreateSettingsGroup switch specifies that you're creating an Exchange settings group, which is a group of related Exchange settings. You don't need to specify a value with this switch.

Depending on how you want to configure the settings group, you use either the GroupName parameter or the SettingsGroup parameter to specify the name of the Exchange settings group. Choose carefully, because you can't rename an existing settings group.

```yaml
Type: SwitchParameter
Parameter Sets: CreateSettingsGroup, CreateSettingsGroupGuid, CreateSettingsGroupAdvanced, CreateSettingsGroupGeneric
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpirationDate

> Applicable: Exchange Server 2016, Exchange Server 2019

The ExpirationDate parameter specifies the end date/time of the Exchange settings that are defined by the specified Exchange settings group.

Use the short date format that's defined in the Regional Options settings on the computer where you're running the command. For example, if the computer is configured to use the short date format MM/dd/yyyy, enter 09/01/2018 to specify September 1, 2018. You can enter the date only, or you can enter the date and time of day. If you enter the date and time of day, enclose the value in quotation marks ("), for example, "09/01/2018 5:00 PM".

You can only use the ExpirationDate parameter with the CreateSettingsGroup or UpdateSettings group parameters.

```yaml
Type: DateTime
Parameter Sets: CreateSettingsGroup, CreateSettingsGroupGuid, CreateSettingsGroupGeneric, UpdateSettingsGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GuidMatch

> Applicable: Exchange Server 2016, Exchange Server 2019

The GuidMatch parameter specifies the scope of an Exchange settings group based on the GUID of the object (for example, the GUID of the mailbox database). This parameter is available for use with all Scope parameter values other than Forest.

You use the GuidMatch parameter only when you create Exchange settings groups by using the CreateSettingsGroup switch with the GroupName parameter.

You can't use this parameter with the GenericScopeName, GenericScopeValue, MaxVersion, MinVersion, or NameMatch parameters.

```yaml
Type: Guid
Parameter Sets: CreateSettingsGroupGuid
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Reason

> Applicable: Exchange Server 2016, Exchange Server 2019

The Reason parameter specifies a description for why the Exchange setting or settings group was created or modified. If the value contains spaces, enclose the value in quotation marks (").

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

### -RemoveSetting

> Applicable: Exchange Server 2016, Exchange Server 2019

The RemoveSetting switch specifies that you're removing an existing Exchange setting from an Exchange settings object. You don't need to specify a value with this switch.

You use the ConfigPairs parameter or the ConfigName parameter to specify the setting that you want to remove.

```yaml
Type: SwitchParameter
Parameter Sets: RemoveSetting, RemoveMultipleSettings
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveSettingsGroup

> Applicable: Exchange Server 2016, Exchange Server 2019

The RemoveSettingsGroup switch specifies that you're removing an Exchange settings group. You don't need to specify a value with this switch.

You use the GroupName parameter to specify the Exchange settings group that you want to remove.

```yaml
Type: SwitchParameter
Parameter Sets: RemoveSettingsGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingsGroup

> Applicable: Exchange Server 2016, Exchange Server 2019

The SettingsGroup parameter specifies an existing Exchange settings group that's used to create a new settings group, or modify an existing settings group.

You can't use the SettingsGroup parameter with the GroupName parameter.

```yaml
Type: String
Parameter Sets: CreateSettingsGroupAdvanced, UpdateSettingsGroupAdvanced
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateSetting

> Applicable: Exchange Server 2016, Exchange Server 2019

The UpdateSetting switch specifies that you're updating an Exchange setting in an existing Exchange settings object. You don't need to specify a value with this switch.

You use the ConfigPairs parameter or the ConfigName and ConfigValue parameters to configure the Exchange setting.

```yaml
Type: SwitchParameter
Parameter Sets: UpdateSetting, UpdateMultipleSettings
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateSettingsGroup

> Applicable: Exchange Server 2016, Exchange Server 2019

The UpdateSettingsGroup switch specifies that you're modifying an Exchange settings group. You don't need to specify a value with this switch.

Depending on how you want to configure the settings group, you use either the GroupName parameter or the SettingsGroup parameter to specify the Exchange settings group that you want to modify.

```yaml
Type: SwitchParameter
Parameter Sets: UpdateSettingsGroup, UpdateSettingsGroupAdvanced
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

> Applicable: Exchange Server 2016, Exchange Server 2019

The Confirm switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding.

- Destructive cmdlets (for example, Remove-\* cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.
- Most other cmdlets (for example, New-\* and Set-\* cmdlets) don't have a built-in pause. For these cmdlets, specifying the Confirm switch without a value introduces a pause that forces you acknowledge the command before proceeding.

This cmdlet has a built-in pause, so use `-Confirm:$false` to skip the confirmation.

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

### -Disable

> Applicable: Exchange Server 2016, Exchange Server 2019

The Disable switch specifies that the Exchange settings group is disabled. You don't need to specify a value with this switch.

You can only use this switch with the CreateSettingsGroup switch.

To use this switch to enable an Exchange settings group, use this exact syntax `-Disable:$false`.

```yaml
Type: SwitchParameter
Parameter Sets: CreateSettingsGroup, CreateSettingsGroupGuid, CreateSettingsGroupGeneric
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableGroup

> Applicable: Exchange Server 2016, Exchange Server 2019

The DisableGroup parameter specifies the name of the enabled Exchange settings group that you want to disable. If the value contains spaces, enclose the value in quotation marks (").

You can use the DisableGroup and EnableGroup parameters together in the same command to enable and disable different Exchange settings groups at the same time.

```yaml
Type: String
Parameter Sets: EnableSettingsGroup
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainController

> Applicable: Exchange Server 2016, Exchange Server 2019

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

### -EnableGroup

> Applicable: Exchange Server 2016, Exchange Server 2019

The EnableGroup parameter specifies the name of the disabled Exchange settings group that you want to enable. If the value contains spaces, enclose the value in quotation marks (").

You can use the DisableGroup and EnableGroup parameters together in the same command to enable and disable different Exchange settings groups at the same time.

```yaml
Type: String
Parameter Sets: EnableSettingsGroup
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

> Applicable: Exchange Server 2016, Exchange Server 2019

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

### -GenericScopeName

> Applicable: Exchange Server 2016, Exchange Server 2019

The GenericScopeName parameter specifies the name of the scope. The available values are determined by the schema of the Exchange setting object.

```yaml
Type: String
Parameter Sets: CreateSettingsGroupGeneric
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GenericScopeValue

> Applicable: Exchange Server 2016, Exchange Server 2019

The GenericScopeValue parameter specifies the value of the scope specified by the GenericScopeName parameter. The available values are determined by the schema of the Exchange setting object.

```yaml
Type: String
Parameter Sets: CreateSettingsGroupGeneric
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupName

> Applicable: Exchange Server 2016, Exchange Server 2019

The GroupName parameter specifies the name of the Exchange settings group in group operations. For example:

- Create Exchange settings groups and simultaneously configure the group scope and priority.
- Modify the ExpirationDate, Priority, and ScopeFilter values of existing Exchange settings groups.
- Remove existing Exchange settings groups.
- Add, remove, or update Exchange setting objects in existing Exchange settings groups.

If the value contains spaces, enclose the value in quotation marks (").

```yaml
Type: String
Parameter Sets: UpdateSetting, RemoveSetting, CreateSettingsGroup, CreateSettingsGroupGuid, CreateSettingsGroupGeneric, UpdateSettingsGroup, RemoveMultipleSettings, RemoveSettingsGroup, UpdateMultipleSettings
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxVersion

> Applicable: Exchange Server 2016, Exchange Server 2019

The MaxVersion parameter specifies the scope of an Exchange settings group based on the version of the object (for example, the version of Exchange that's installed on the server). This parameter is available for use with all Scope parameter values other than Forest.

You use the MaxVersion parameter together with the MinVersion parameter only when you create Exchange settings groups by using the CreateSettingsGroup switch with the GroupName parameter.

You can't use this parameter with the GuidMatch, GenericScopeName, or GenericScopeValue parameters.

```yaml
Type: String
Parameter Sets: CreateSettingsGroup
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinVersion

> Applicable: Exchange Server 2016, Exchange Server 2019

The MinVersion parameter specifies the scope of an Exchange settings group based on the version of the object (for example, the version of Exchange that's installed on the server). This parameter is available for use with all Scope parameter values other than Forest.

You use the MinVersion parameter together with the MaxVersion parameter only when you create Exchange settings groups by using the CreateSettingsGroup switch with the GroupName parameter.

You can't use this parameter with GuidMatch, GenericScopeName, or GenericScopeValue parameters.

```yaml
Type: String
Parameter Sets: CreateSettingsGroup
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NameMatch

> Applicable: Exchange Server 2016, Exchange Server 2019

The NameMatch parameter specifies the scope of an Exchange settings group based on the name of the object (for example, the process name). This parameter is available for use with all Scope parameter values other than Forest.

You use the NameMatch parameter only when you create Exchange settings groups by using the CreateSettingsGroup switch with the GroupName parameter.

You can't use this parameter with the GuidMatch, GenericScopeName, or GenericScopeValue parameters.

```yaml
Type: String
Parameter Sets: CreateSettingsGroup
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Priority

> Applicable: Exchange Server 2016, Exchange Server 2019

The Priority parameter specifies the priority of an Exchange settings group. The priority value for every group must be unique. A lower priority value indicates a higher priority.

```yaml
Type: Int32
Parameter Sets: CreateSettingsGroup, CreateSettingsGroupGuid, CreateSettingsGroupGeneric, UpdateSettingsGroup
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scope

> Applicable: Exchange Server 2016, Exchange Server 2019

The Scope parameter specifies the scope of the Exchange settings object. Valid values are:

- Dag
- Database
- Forest
- Generic
- Organization
- Process
- Server
- User

```yaml
Type: ExchangeSettingsScope
Parameter Sets: CreateSettingsGroup, CreateSettingsGroupGuid, CreateSettingsGroupGeneric
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScopeFilter

> Applicable: Exchange Server 2016, Exchange Server 2019

The ScopeFilter parameter uses OPATH filter syntax to specify the scope of an Exchange settings group based. The syntax is `"Property -ComparisonOperator 'Value'"` (for example, `"ServerRole -like 'Mailbox*'"`).

- Enclose the whole OPATH filter in double quotation marks " ". If the filter contains system values (for example, `$true`, `$false`, or `$null`), use single quotation marks ' ' instead. Although this parameter is a string (not a system block), you can also use braces { }, but only if the filter doesn't contain variables.
- Property is a filterable property.
- ComparisonOperator is an OPATH comparison operator (for example `-eq` for equals and `-like` for string comparison). For more information about comparison operators, see [about_Comparison_Operators](https://learn.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators).
- Value is the property value to search for. Enclose text values and variables in single quotation marks (`'Value'` or `'$Variable'`). If a variable value contains single quotation marks, you need to identify (escape) the single quotation marks to expand the variable correctly. For example, instead of `'$User'`, use `'$($User -Replace "'","''")'`. Don't enclose integers or system values in quotation marks (for example, use `500`, `$true`, `$false`, or `$null` instead).

You can chain multiple search criteria together using the logical operators `-and` and `-or`. For example, `"Criteria1 -and Criteria2"` or `"(Criteria1 -and Criteria2) -or Criteria3"`.

For detailed information about OPATH filters in Exchange, see [Additional OPATH syntax information](https://learn.microsoft.com/powershell/exchange/recipient-filters#additional-opath-syntax-information).

You can't use this parameter with the Scope parameter and the value Forest or other scope-related parameters.

You use this parameter only when you update Exchange settings groups by using the UpdateSettingsGroup switch with the GroupName parameter.

```yaml
Type: String
Parameter Sets: CreateSettingsGroup, UpdateSettingsGroup
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

> Applicable: Exchange Server 2016, Exchange Server 2019

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

## OUTPUTS

## NOTES

## RELATED LINKS
