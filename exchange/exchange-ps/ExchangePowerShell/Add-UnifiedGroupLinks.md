---
applicable: Exchange Online, Exchange Online Protection
author: chrisda
external help file: Microsoft.Exchange.RolesAndAccess-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/add-unifiedgrouplinks
schema: 2.0.0
title: Add-UnifiedGroupLinks
---

# Add-UnifiedGroupLinks

## SYNOPSIS
This cmdlet is available only in the cloud-based service.

Use the Add-UnifiedGroupLinks cmdlet to add members, owners and subscribers to Microsoft 365 Groups in your cloud-based organization. To remove members, owners, and subscribers, use the Remove-UnifiedGroupLinks cmdlet. To modify other properties of Microsoft 365 Groups, use the Set-UnifiedGroup cmdlet.

> [!NOTE]
> You can't use this cmdlet to modify Microsoft 365 Group members, owners, or subscribers if you connect using certificate based authentication (also known as CBA or app-only authentication for unattended scripts) or Azure managed identity. You can use Microsoft Graph instead. For more information, see [Group resource type](https://learn.microsoft.com/graph/api/resources/group).
>
> Using this cmdlet, only group members can be owners of the group. Add users as members before you add them as owners. This limitation doesn't apply in web management portals where you can add non-members as group owners. Guest users can never be group owners.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Add-UnifiedGroupLinks [-Identity] <UnifiedGroupIdParameter> -Links <RecipientIdParameter[]> -LinkType <LinkType>
 [-Confirm]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Microsoft 365 Groups are group objects that are available across Microsoft 365 services.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

**Note**: Only members can be owners of a group, so you must first add a user as member before adding it as an owner. Guest users cannot be an owner of groups, even if the users are members of the groups.

## EXAMPLES

### Example 1
```powershell
Add-UnifiedGroupLinks -Identity "Legal Department" -LinkType Members -Links chris@contoso.com,michelle@contoso.com
```

This example adds members `chris@contoso.com` and `michelle@contoso.com` to the Microsoft 365 Group named Legal Department.

### Example 2
```powershell
$users= Get-User -ResultSize unlimited | where {$_.Department -eq "Marketing" -AND $_.RecipientType -eq "UserMailbox"}

Add-UnifiedGroupLinks -Identity Marketing -LinkType members -Links ($users.UserPrincipalName)
```

This example shows how to add bulk members to a Microsoft 365 Group. Mailboxes where the Department attribute is "Marketing" are added to Microsoft 365 Group named Marketing.

## PARAMETERS

### -Identity

> Applicable: Exchange Online, Exchange Online Protection

The Identity parameter specifies the Microsoft 365 Group that you want to modify. You can use any value that uniquely identifies the Microsoft 365 Group. For example:

- Name
- Alias
- Distinguished name (DN)
- Canonical DN
- Email address
- GUID

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

### -Links

> Applicable: Exchange Online, Exchange Online Protection

The Links parameter specifies the recipients to add to the Microsoft 365 Group. You specify whether these recipients are members, owners, or subscribers by using the LinkType parameter.

You can use any value that uniquely identifies the recipient. For example:

- Name
- Alias
- Distinguished name (DN)
- Canonical DN
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

You must use this parameter with the LinkType parameter, which means the specified recipients receive the same role in the Microsoft 365 Group (you can't add recipients with different roles in the same command).

**Note**: Using this cmdlet, only group members can be owners of the group. Add users as members before you add them as owners. This limitation doesn't apply in web management portals where you can add non-members as group owners. Guest users can never be group owners.

```yaml
Type: RecipientIdParameter[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinkType

> Applicable: Exchange Online, Exchange Online Protection

The LinkType parameter specifies the recipient's role in the Microsoft 365 Group that you want to add. Valid values are:

- Members: Participate in conversations, create Teams channels, collaborate on files, and edit the connected SharePoint site.
- Owners: Add or remove members, delete conversations, changes Team settings, delete the Team, and full control of the connected SharePoint site. A group must have at least one owner.
- Subscribers: Existing group members who receive conversation and calendar event notifications from the group. All subscribers are members of the group, but all members aren't necessarily subscribers (depending on the AutoSubscribeNewMembers property value of the group and when the member was added).

You must use this parameter with the Links parameter.

**Note**: Using this cmdlet, only group members can be owners of the group. Add users as members before you add them as owners. This limitation doesn't apply in web management portals where you can add non-members as group owners. Guest users can never be group owners.

```yaml
Type: LinkType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

> Applicable: Exchange Online, Exchange Online Protection

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

> Applicable: Exchange Online, Exchange Online Protection

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
