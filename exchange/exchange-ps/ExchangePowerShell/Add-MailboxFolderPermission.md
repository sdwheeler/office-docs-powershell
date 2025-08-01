---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online
author: chrisda
external help file: Microsoft.Exchange.CalendarsAndGroups-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/add-mailboxfolderpermission
schema: 2.0.0
title: Add-MailboxFolderPermission
---

# Add-MailboxFolderPermission

## SYNOPSIS
This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

Use the Add-MailboxFolderPermission cmdlet to add folder-level permissions for users in mailboxes.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Add-MailboxFolderPermission [-Identity] <MailboxFolderIdParameter> -AccessRights <MailboxFolderAccessRight[]> -User <MailboxFolderUserIdParameter>
 [-Confirm]
 [-DomainController <Fqdn>]
 [-SendNotificationToUser <Boolean>]
 [-SharingPermissionFlags <MailboxFolderPermissionFlags>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
To modify the permissions that are assigned to the user on a mailbox folder, use the Set-MailboxFolderPermission cmdlet. To remove all permissions that are assigned to a user on a mailbox folder, use the Remove-MailboxFolderPermission cmdlet.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Add-MailboxFolderPermission -Identity ayla@contoso.com:\Marketing -User ed@contoso.com -AccessRights Owner
```

This example grants the Owner role to Ed on the Marketing folder in Ayla's mailbox.

### Example 2
```powershell
Add-MailboxFolderPermission -Identity ayla@contoso.com:\Calendar -User julia@contoso.com -AccessRights Editor -SharingPermissionFlags Delegate
```

In Exchange Online, this example adds Julia as a calendar delegate to Ayla's mailbox, but without access to private items.

### Example 3
```powershell
Add-MailboxFolderPermission -Identity ayla@contoso.com:\Calendar -User laura@contoso.com -AccessRights Editor -SharingPermissionFlags Delegate,CanViewPrivateItems
```

In Exchange Online, this example adds Laura as a calendar delegate to Ayla's mailbox with access to private items.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Identity parameter specifies the target mailbox and folder. The syntax is `MailboxID:\ParentFolder[\SubFolder]`.

For the value of `MailboxID`, you can use any value that uniquely identifies the mailbox. For example:

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

Example values for this parameter are `john@contoso.com:\Calendar` or `John:\Inbox\Reports`.

```yaml
Type: MailboxFolderIdParameter
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -AccessRights

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The AccessRights parameter specifies the permissions that you want to add for the user on the mailbox folder.

You can specify individual folder permissions or roles, which are combinations of permissions. You can specify multiple permissions and roles separated by commas.

The following individual permissions are available:

- None: The user has no access to view or interact with the folder or its contents.
- CreateItems: The user can create items within the specified folder.
- CreateSubfolders: The user can create subfolders in the specified folder.
- DeleteAllItems: The user can delete all items in the specified folder.
- DeleteOwnedItems: The user can only delete items that they created from the specified folder.
- EditAllItems: The user can edit all items in the specified folder.
- EditOwnedItems: The user can only edit items that they created in the specified folder.
- FolderContact: The user is the contact for the specified public folder.
- FolderOwner: The user is the owner of the specified folder. The user can view the folder, move the folder and create subfolders. The user can't read items, edit items, delete items or create items.
- FolderVisible: The user can view the specified folder, but can't read or edit items within the specified public folder.
- ReadItems: The user can read items within the specified folder.

The roles that are available, along with the permissions that they assign, are described in the following list:

- Author: CreateItems, DeleteOwnedItems, EditOwnedItems, FolderVisible, ReadItems
- Contributor: CreateItems, FolderVisible
- Editor: CreateItems, DeleteAllItems, DeleteOwnedItems, EditAllItems, EditOwnedItems, FolderVisible, ReadItems
- NonEditingAuthor: CreateItems, DeleteOwnedItems, FolderVisible, ReadItems
- Owner: CreateItems, CreateSubfolders, DeleteAllItems, DeleteOwnedItems, EditAllItems, EditOwnedItems, FolderContact, FolderOwner, FolderVisible, ReadItems
- PublishingAuthor: CreateItems, CreateSubfolders, DeleteOwnedItems, EditOwnedItems, FolderVisible, ReadItems
- PublishingEditor: CreateItems, CreateSubfolders, DeleteAllItems, DeleteOwnedItems, EditAllItems, EditOwnedItems, FolderVisible, ReadItems
- Reviewer: FolderVisible, ReadItems

The following roles apply specifically to calendar folders:

- AvailabilityOnly: View only availability data
- LimitedDetails: View availability data with subject and location

When the Editor role is applied to calendar folders, delegates can accept or decline meetings by manually selecting the meeting request in the mailbox. In Exchange Online, to send meeting requests to delegates where they can accept or decline meetings, also use the SharingPermissionFlags parameter with the value Delegate.

```yaml
Type: MailboxFolderAccessRight[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The User parameter specifies who's granted permission to the mailbox folder. Valid values are mail-enabled security principals (mail-enabled accounts or groups that have security identifiers or SIDs that can have permissions assigned to them). For example:

- User mailboxes
- Mail users
- Mail-enabled security groups (including nested mail-enabled security groups)

For the best results, we recommend using the following values:

- UPN: For example, `user@contoso.com` (users only).
- Domain\\SamAccountName: For example, `contoso\user`.

Otherwise, you can use any value that uniquely identifies the user or group. For example:

- Name
- Alias
- Distinguished name (DN)
- Canonical DN
- Email address
- GUID

```yaml
Type: MailboxFolderUserIdParameter
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

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

### -SendNotificationToUser

> Applicable: Exchange Online

This parameter is available only in the cloud-based service.

The SendNotificationToUser parameter specifies whether to send a sharing invitation to the user when you add calendar permissions for them. The message will be a normal calendar sharing invitation that can be accepted by the recipient. Valid values are:

- $true: A sharing invitation is sent.
- $false: No sharing invitation is sent. This is the default value.

This parameter only applies to calendar folders and can only be used with the following AccessRights parameter values:

- AvailabilityOnly
- LimitedDetails
- Reviewer
- Editor

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

### -SharingPermissionFlags

> Applicable: Exchange Online

This parameter is available only in the cloud-based service.

The SharingPermissionFlags parameter assigns calendar delegate permissions. This parameter only applies to calendar folders and can only be used when the AccessRights parameter value is Editor. Valid values are:

- None: Has no effect. This is the default value.
- Delegate: The user is made a calendar delegate, which includes receiving meeting invites and responses. If there are no other delegates, this value will create the meeting message rule. If there are existing delegates, the user is added to the meeting message rule without changing how delegate messages are sent.
- CanViewPrivateItems: The user can access private items on the calendar. You must use this value with the Delegate value.

You can specify multiple values separated by commas.

**Note**: You can't configure the **Deliver meeting requests addressed to me and responses to meeting requests where I am the organizer to** Outlook setting in PowerShell. But, you can configure the setting using Exchange Web Services (EWS). For more information, see [MeetingRequestsDeliveryScope Enum](https://learn.microsoft.com/dotnet/api/microsoft.exchange.webservices.data.meetingrequestsdeliveryscope).

```yaml
Type: MailboxFolderPermissionFlags
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

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

[Get-MailboxFolderPermission](https://learn.microsoft.com/powershell/module/exchangepowershell/get-mailboxfolderpermission)

[Set-MailboxFolderPermission](https://learn.microsoft.com/powershell/module/exchangepowershell/set-mailboxfolderpermission)

[Remove-MailboxFolderPermission](https://learn.microsoft.com/powershell/module/exchangepowershell/remove-mailboxfolderpermission)

[Get-EXOMailboxFolderPermission](https://learn.microsoft.com/powershell/module/exchangepowershell/get-exomailboxfolderpermission)
