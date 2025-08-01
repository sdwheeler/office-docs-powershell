---
applicable: Exchange Online
author: chrisda
external help file: Microsoft.Exchange.RolesAndAccess-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/disable-journalarchiving
schema: 2.0.0
title: Disable-JournalArchiving
---

# Disable-JournalArchiving

## SYNOPSIS
This cmdlet is available only in the cloud-based service.

Use the Disable-JournalArchiving cmdlet to disable journal archiving for specific users. Microsoft 365 journal archiving uses mailboxes in Exchange Online to record or journal messages for mailboxes in on-premises organizations.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Disable-JournalArchiving [-Identity] <MailboxIdParameter>
 [-Confirm]
 [-PreserveMailUser]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
For each on-premise mailbox that's configured for journal archiving in Microsoft 365, a mail user (also known as a mail-enabled user) and a journal archive mailbox are created in Exchange Online. The mail user routes the incoming journaled messages from the on-premises organization, and the journal archive mailbox stores the journaled messages in the cloud.

The Disable-JournalArchiving cmdlet removes the mail user and converts the journal archive mailbox into an inactive mailbox. The inactive mailbox remains fully available for In-place eDiscovery.

In hybrid organizations that use DirSync, this cmdlet doesn't remove the mail user. Removal of the mail user is handled by DirSync.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Disable-JournalArchiving -Identity TimothyAmaral_Archive
```

This example disables the journal archiving for the user named Timothy Amaral. Timothy's journal archive mailbox in Exchange Online is named TimothyAmaral\_Archive.

## PARAMETERS

### -Identity

> Applicable: Exchange Online

The Identity parameter specifies the identity of the user's journal archive mailbox in Exchange Online. You can use any value that uniquely identifies the journal archive mailbox. For example:

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

```yaml
Type: MailboxIdParameter
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

This parameter is reserved for internal Microsoft use.

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

### -PreserveMailUser

> Applicable: Exchange Online

The PreserveMailUser switch specifies that you want to keep the mail user that's associated with the archive mailbox. You don't need to specify a value with this switch.

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

> Applicable: Exchange Online

This parameter is reserved for internal Microsoft use.

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
