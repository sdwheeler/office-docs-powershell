---
applicable: Exchange Online
author: chrisda
external help file: Microsoft.Exchange.RolesAndAccess-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/undo-softdeletedunifiedgroup
schema: 2.0.0
title: Undo-SoftDeletedUnifiedGroup
---

# Undo-SoftDeletedUnifiedGroup

## SYNOPSIS
This cmdlet is available only in the cloud-based service.

Use the Undo-SoftDeletedUnifiedGroup cmdlet to restore soft-deleted Microsoft 365 Groups in your cloud-based organization.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Undo-SoftDeletedUnifiedGroup [-SoftDeletedObject] <UnifiedGroupIdParameter>
 [-Confirm]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Microsoft 365 Groups are group objects that are available across Microsoft 365 services.

Soft-deleted Microsoft 365 Groups are groups that have been deleted, but can be restored within 30 days of being deleted. All of the group contents can be restored within this period. After 30 days, soft-deleted Microsoft 365 Groups are marked for permanent deletion and can't be restored.

To display all soft-deleted Microsoft 365 Groups in your organization, use the [Get-MgDirectoryDeletedItemAsGroup](https://learn.microsoft.com/powershell/module/microsoft.graph.identity.directorymanagement/get-mgdirectorydeleteditemasgroup) cmdlet in Microsoft Graph PowerShell. To permanently remove (purge) a soft-deleted Microsoft 365 Group, use the [Remove-MgDirectoryDeletedItem](https://learn.microsoft.com/powershell/module/microsoft.graph.identity.directorymanagement/remove-mgdirectorydeleteditem) cmdlet in Microsoft Graph PowerShell.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Undo-SoftDeletedUnifiedGroup -SoftDeletedObject "Marketing Department"
```

This example restores the soft-deleted Microsoft 365 Group named Marketing Department.

## PARAMETERS

### -SoftDeletedObject

> Applicable: Exchange Online

The SoftDeletedObject parameter specifies the soft-deleted Microsoft 365 Group that you want to restore. You can use any value that uniquely identifies the Microsoft 365 Group. For example:

- Name
- Alias
- Distinguished name (DN)
- Canonical DN
- Domain\\Username
- Email address
- GUID
- LegacyExchangeDN
- SamAccountName
- User ID or user principal name (UPN)

**Note**: You might need to use the DistinguishedName or ExchangeGuid property to identify the soft-deleted Microsoft 365 Group, because it's possible for an active Microsoft 365 Group and a soft-deleted Microsoft 365 Group to have the same primary SMTP address.

```yaml
Type: UnifiedGroupIdParameter
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -Confirm

> Applicable: Exchange Online

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

### -WhatIf

> Applicable: Exchange Online

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
