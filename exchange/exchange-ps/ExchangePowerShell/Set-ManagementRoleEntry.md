---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection
author: chrisda
external help file: Microsoft.Exchange.RolesAndAccess-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/set-managementroleentry
schema: 2.0.0
title: Set-ManagementRoleEntry
---

# Set-ManagementRoleEntry

## SYNOPSIS
This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

Use the Set-ManagementRoleEntry cmdlet to change the available parameters on an existing management role entry.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Set-ManagementRoleEntry [-Identity] <RoleEntryIdParameter>
 [-AddParameter]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-Force]
 [-Parameters <String[]>]
 [-RemoveParameter]
 [-UnScopedTopLevel]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
The Set-ManagementRoleEntry cmdlet changes the available parameters on an existing role entry. If you want to add parameters to a role entry, the parameters must exist in the role entry in the parent management role. If you want to remove parameters from a role entry, there can be no role entries in child roles that inherit those parameters from the role entry you want to change. You can't change role entries associated with built-in roles.

For more information about management role entries, see [Understanding management roles](https://learn.microsoft.com/exchange/understanding-management-roles-exchange-2013-help).

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Set-ManagementRoleEntry "Help Desk Personnel\Get-Mailbox" -Parameters "Anr","Database" -RemoveParameter
```

This example removes the Anr and Database parameters from the Get-Mailbox role entry on the Help Desk Personnel role.

### Example 2
```powershell
Get-ManagementRoleEntry "Help Desk Personnel\*" | Set-ManagementRoleEntry -Parameters WhatIf -AddParameter
```

This example retrieves a list of role entries on the Help Desk Personnel role and adds the WhatIf switch to each role entry using the Set-ManagementRoleEntry cmdlet.

### Example 3
```powershell
Set-ManagementRoleEntry "Tier 1 Help Desk\Set-Mailbox" -Parameters "DisplayName","ForwardingAddress"
```

This example adds the DisplayName and ForwardingAddress parameters to the Set-Mailbox role entry on the Tier 1 Help Desk role and removes all other parameters from the role entry.

### Example 4
```powershell
Set-ManagementRoleEntry "IT Scripts\MailboxAudit" -Parameters Location -AddParameter -UnScopedTopLevel
```

In on-premises Exchange, this example adds the Location parameter to the MailboxAudit custom script on the IT Scripts unscoped top level role. Note that the UnScopedTopLevel switch requires the UnScoped Role Management role, which isn't assigned to any role groups by default.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The Identity parameter specifies the role entry that you want to modify. This parameter uses the syntax: `<management role>\<role entry name>` (for example, `CustomRole\Set-Mailbox`).

For more information about how management role entries work, see [Understanding management roles](https://learn.microsoft.com/exchange/understanding-management-roles-exchange-2013-help).

If the role entry name contains spaces, enclose it in quotation marks (").

```yaml
Type: RoleEntryIdParameter
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -AddParameter

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The AddParameter switch specifies that you're adding parameters to the specified role entry. You don't need to specify a value with this switch.

Use the Parameters parameter to specify the parameters to add.

You can't use the AddParameter switch and the RemoveParameter switch together in the same command.

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

> Applicable: Exchange Online, Exchange Online Protection

This parameter is available only in the cloud-based service.

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

### -Parameters

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The Parameters parameter specifies the parameters to be added to or removed from the role entry.

The Parameters parameter has the following modes:

- When used with the AddParameter parameter, the parameters you specify are added to the role entry.
- When used with the RemoveParameter parameter, the parameters you specify are removed from the role entry.
- When neither the AddParameter nor RemoveParameter parameters are used, only the parameters you specify are included in the role entry. If you specify a value of $Null and neither the AddParameter nor RemoveParameter parameters are used, all of the parameters on the role entry are removed.

You can specify multiple parameters, separated with commas.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveParameter

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The RemoveParameter switch specifies that you're removing parameters to the specified role entry. You don't need to specify a value with this switch.

Use the Parameters parameter to specify the parameters to remove.

You can't use the AddParameter switch and the RemoveParameter switch together in the same command.

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

### -UnScopedTopLevel

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This parameter is available only in on-premises Exchange.

By default, this parameter is available only in the UnScoped Role Management role, and that role isn't assigned to any role groups. To use this parameter, you need to add the UnScoped Role Management role to a role group (for example, to the Organization Management role group). For more information, see [Add a role to a role group](https://learn.microsoft.com/Exchange/permissions/role-groups#add-a-role-to-a-role-group).

The UnScopedTopLevel switch specifies the role entry that you want to modify is on an unscoped top-level role. You don't need to specify a value with this switch.

Unscoped top-level management roles can only contain custom scripts or non-Exchange cmdlets. For more information, see [Create an unscoped role](https://learn.microsoft.com/exchange/create-an-unscoped-role-exchange-2013-help).

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
