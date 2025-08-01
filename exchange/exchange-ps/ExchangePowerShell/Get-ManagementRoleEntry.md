---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection
author: chrisda
external help file: Microsoft.Exchange.RolesAndAccess-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/get-managementroleentry
schema: 2.0.0
title: Get-ManagementRoleEntry
---

# Get-ManagementRoleEntry

## SYNOPSIS
This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

Use the Get-ManagementRoleEntry cmdlet to retrieve management role entries that have been configured on management roles.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Get-ManagementRoleEntry [-Identity] <RoleEntryIdParameter>
 [-DomainController <Fqdn>]
 [-Parameters <String[]>]
 [-PSSnapinName <String>]
 [-ResultSize <Unlimited>]
 [-Type <ManagementRoleEntryType[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The Get-ManagementRoleEntry cmdlet retrieves role entries that have been configured on roles. You can retrieve specific role entries that match specific criteria such as role name, cmdlet name, parameter name, or a combination of each, or role entry type or the associated Windows PowerShell snap-in.

For more information about management role entries, see [Understanding management roles](https://learn.microsoft.com/exchange/understanding-management-roles-exchange-2013-help).

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Get-ManagementRoleEntry "Transport Rules\*"
```

This example retrieves a list of all the role entries that exist on the Transport Rules management role.

### Example 2
```powershell
Get-ManagementRoleEntry *\Get-Recipient
```

This example retrieves a list of all the role entries that contain the Get-Recipient cmdlet.

### Example 3
```powershell
Get-ManagementRoleEntry "Tier 2 Help Desk\Set-Mailbox" | Format-List Name, Parameters, Role, Type
```

This example retrieves the Tier 2 Help Desk\\Set-Mailbox role entry and pipes the output of the Get-ManagementRoleEntry cmdlet to the Format-List cmdlet. The Format-List cmdlet then outputs only the Name, Parameters, Role and Type properties from the role entry.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The Identity parameter specifies the role entry that you want to view. This parameter uses the syntax: `<management role>\<role entry name>` (for example, `CustomRole\Set-Mailbox`).

For more information about how management role entries work, see [Understanding management roles](https://learn.microsoft.com/exchange/understanding-management-roles-exchange-2013-help).

You can use the wildcard character (\*) instead of the role, cmdlet name or both.

If the role entry name contains spaces, enclose the name in quotation marks (").

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

### -Parameters

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The Parameters parameter includes only the role entries that contain the parameters specified. You can specify multiple parameters, separated by commas. You can use the wildcard character (\*) with partial parameter names to retrieve all parameters that match the value you specify.

This parameter is useful when you use the wildcard character (\*) with the value you specify in the Identity parameter.

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

### -PSSnapinName

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The PSSnapinName parameter specifies the Windows PowerShell snap-in that contains the role entry to return. Use the Get-PSSnapin cmdlet to retrieve a list of available Windows PowerShell snap-ins.

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

### -ResultSize

> Applicable: Exchange Online, Exchange Online Protection

This parameter is available only in the cloud-based service.

The ResultSize parameter specifies the maximum number of results to return. If you want to return all requests that match the query, use unlimited for the value of this parameter. The default value is 1000.

```yaml
Type: Unlimited
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The Type parameter specifies the type of role entry to return. The valid values for the Type parameter are any combination of the following parameters, separated by commas: Cmdlet, Script and ApplicationPermission.

```yaml
Type: ManagementRoleEntryType[]
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
