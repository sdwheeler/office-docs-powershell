---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online
author: chrisda
external help file: Microsoft.Exchange.RecordsandEdge-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/set-retentionpolicytag
schema: 2.0.0
title: Set-RetentionPolicyTag
---

# Set-RetentionPolicyTag

## SYNOPSIS
This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

Use the Set-RetentionPolicyTag cmdlet to modify the properties of a retention tag.

For more information about retention tags, see [Retention tags and retention policies in Exchange Server](https://learn.microsoft.com/Exchange/policy-and-compliance/mrm/retention-tags-and-retention-policies).

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

### Identity
```
Set-RetentionPolicyTag [-Identity] <RetentionPolicyTagIdParameter>
 [-AddressForJournaling <RecipientIdParameter>]
 [-AgeLimitForRetention <EnhancedTimeSpan>]
 [-Comment <String>]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-Force]
 [-JournalingEnabled <Boolean>]
 [-LabelForJournaling <String>]
 [-LegacyManagedFolder <ELCFolderIdParameter>]
 [-LocalizedComment <MultiValuedProperty>]
 [-LocalizedRetentionPolicyTagName <MultiValuedProperty>]
 [-MessageClass <String>]
 [-MessageFormatForJournaling <JournalingFormat>]
 [-MustDisplayCommentEnabled <Boolean>]
 [-Name <String>]
 [-RetentionAction <RetentionAction>]
 [-RetentionEnabled <Boolean>]
 [-RetentionId <Guid>]
 [-SystemTag <Boolean>]
 [-WhatIf]
 [<CommonParameters>]
```

### MailboxTask
```
Set-RetentionPolicyTag -Mailbox <MailboxIdParameter>
 [-Comment <String>]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-Force]
 [-LegacyManagedFolder <ELCFolderIdParameter>]
 [-LocalizedComment <MultiValuedProperty>]
 [-LocalizedRetentionPolicyTagName <MultiValuedProperty>]
 [-MustDisplayCommentEnabled <Boolean>]
 [-Name <String>]
 [-OptionalInMailbox <RetentionPolicyTagIdParameter[]>]
 [-RetentionId <Guid>]
 [-SystemTag <Boolean>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Retention tags are used to apply message retention settings to folders and items in a mailbox.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Set-RetentionPolicyTag "AllUsers-DeletedItems" -Comment "Items in the Deleted Items folder will be automatically deleted in 120 days"
```

This example changes the comment for the AllUsers-DeletedItems retention policy tag.

### Example 2
```powershell
Set-RetentionPolicyTag -Mailbox "Terry Adams" -OptionalInMailbox "ProjectA","ProjectB"
```

This example makes optional retention tags available to user Terry Adams using the Mailbox and OptionalInMailbox parameters.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Identity parameter specifies the name, distinguished name (DN), or GUID of the retention policy tag to be modified.

```yaml
Type: RetentionPolicyTagIdParameter
Parameter Sets: Identity
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -Mailbox

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Mailbox parameter specifies a mailbox for assigning opt-in tags. You can use any value that uniquely identifies the mailbox. For example:

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

You must use this parameter with the OptionalInMailbox parameter.

```yaml
Type: MailboxIdParameter
Parameter Sets: MailboxTask
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddressForJournaling

> Applicable: Exchange Server 2010

This parameter is available only in Exchange Server 2010.

This parameter is reserved for internal Microsoft use.

```yaml
Type: RecipientIdParameter
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AgeLimitForRetention

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The AgeLimitForRetention parameter specifies the age at which retention is enforced on an item. The age limit corresponds to the number of days from the date the item was delivered, or the date an item was created if it wasn't delivered. If this parameter isn't present and the RetentionEnabled parameter is set to $true, an error is returned.

```yaml
Type: EnhancedTimeSpan
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Comment

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Comment parameter specifies a comment for the retention policy tag.

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

### -Force

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Force switch hides warning or confirmation messages. You don't need to specify a value with this switch.

Use this switch to hide the confirmation prompt when you use the RetentionId parameter.

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

### -JournalingEnabled

> Applicable: Exchange Server 2010

This parameter is available only in Exchange Server 2010.

This parameter is reserved for internal Microsoft use.

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LabelForJournaling

> Applicable: Exchange Server 2010

This parameter is available only in Exchange Server 2010.

This parameter is reserved for internal Microsoft use.

```yaml
Type: String
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LegacyManagedFolder

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The LegacyManagedFolder parameter specifies the name of a managed folder. The retention tag is created by using retention settings from the managed folder and its managed content settings. You can use this parameter to create retention tags based on existing managed folders to migrate users from managed folder mailbox policies to retention policies.

```yaml
Type: ELCFolderIdParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalizedComment

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The LocalizedComment parameter specifies the localized comment and language for the retention policy tag. This comment is displayed in Microsoft Outlook based on the user's locale.

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

### -LocalizedRetentionPolicyTagName

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The LocalizedRetentionPolicyTagName parameter specifies a localized name for the retention policy tag. This name is displayed in Outlook based on the user's locale.

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

### -MessageClass

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The MessageClass parameter specifies the message type to which the tag applies. If not specified, the default value is set to \*.

With the exception of a default policy tag (DPT) for voicemail, Exchange doesn't support retention tags for different message types. Only tags with a MessageClass of \* are supported and they apply to all message types.

To create a DPT for voice mail messages, set the MessageClass parameter to voicemail and the Type parameter to All.

A DPT for voice mail messages applies only to Microsoft Exchange Unified Messaging voice mail messages (identified by the PR\_MESSAGE\_CLASS MAPI property value IPM.Note.Microsoft.Voicemail\*).

```yaml
Type: String
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MessageFormatForJournaling

> Applicable: Exchange Server 2010

This parameter is available only in Exchange Server 2010.

This parameter is reserved for internal Microsoft use.

```yaml
Type: JournalingFormat
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MustDisplayCommentEnabled

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The MustDisplayCommentEnabled parameter specifies whether the comment can be hidden. The default value is $true.

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

### -Name

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Name parameter specifies the name of the retention policy tag.

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

### -OptionalInMailbox

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The OptionalInMailbox parameter is used with the Mailbox parameter to assign personal tags to the mailbox. You can use this parameter to make available to a user a personal tag that isn't assigned to the retention policy applied to the specified mailbox. You can specify multiple personal tags separated by commas.

```yaml
Type: RetentionPolicyTagIdParameter[]
Parameter Sets: MailboxTask
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionAction

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The RetentionAction parameter specifies the action for the retention policy. Valid values are:

- DeleteAndAllowRecovery: Deletes a message and allows recovery from the Recoverable Items folder.
- MarkAsPastRetentionLimit: Messages are marked as past the retention limit.
- MoveToArchive: Moves a message to the user's archive mailbox. You can use this action for retention tags of type All, Personal, and RecoverableItems.
- PermanentlyDelete: Permanently deletes a message. A message that has been permanently deleted can't be recovered using the Recoverable Items folder. Permanently deleted messages aren't returned in a Discovery search, unless litigation hold is enabled for the mailbox.

The MoveToDeletedItems and MoveToFolder actions are available, but don't work. These actions are available for upgrades from messaging records management (MRM) 1.0 (managed folders) to MRM 2.0 (retention policies). MRM 2.0 was introduced in Exchange 2010 Service Pack 1 (SP1).

If this parameter isn't present and the RetentionEnabled parameter is set to $true, an error is returned.

```yaml
Type: RetentionAction
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionEnabled

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The RetentionEnabled parameter specifies whether the tag is enabled. When set to $false, the tag is disabled and no retention action is taken on messages that have the tag applied.

Messages with a disabled tag are still considered tagged, so any default policy tags in the user's retention policy aren't applied to such messages.

When you set the RetentionEnabled parameter to $false, the retention period for the tag is shown as Never. Users may apply this tag to items that they want to indicate should never be deleted or should never be moved to the archive. Enabling the tag later may result in unintentional deletion or archiving of items. To avoid this situation, if a retention policy is disabled temporarily, it may be advisable to change the name of that tag so that users are discouraged from using it, such as `DISABLED_<Original Name>`.

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionId

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The RetentionId parameter specifies an alternate tag ID to ensure the retention tag found on mailbox items tagged in one Exchange organization matches the tag when the mailbox is moved to another Exchange organization (for example, in a cross-forest deployment or in a cross-premises deployment, when a mailbox is moved from an on-premises Exchange server to the cloud, or a cloud-based mailbox is moved to an on-premises Exchange server).

Typically, you don't need to specify or modify the RetentionId parameter for a retention tag. This parameter is populated automatically when importing retention tags in a cross-forest or cross-premises deployment.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SystemTag

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The SystemTag parameter specifies whether the retention policy tag is created for internal Exchange functionality.

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
