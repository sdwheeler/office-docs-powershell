---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online
author: chrisda
external help file: Microsoft.Exchange.TransportMailControl-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/set-journalrule
schema: 2.0.0
title: Set-JournalRule
---

# Set-JournalRule

## SYNOPSIS
This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

Use the Set-JournalRule cmdlet to modify an existing journal rule in your organization.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Set-JournalRule [-Identity] <RuleIdParameter>
 [-Confirm]
 [-DomainController <Fqdn>]
 [-JournalEmailAddress <RecipientIdParameter>]
 [-Name <String>]
 [-Recipient <SmtpAddress>]
 [-Scope <JournalRuleScope>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
The Set-JournalRule cmdlet modifies an existing journal rule used in your organization.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Set-JournalRule "Consolidated Messenger" -JournalEmailAddress "ArchiveMailbox@contoso.com"
```

This example modifies the journal email address to which journal reports are sent by the existing journal rule Consolidated Messenger.

### Example 2
```powershell
Get-JournalRule | Set-JournalRule -JournalEmailAddress "Archive Mailbox"
```

This example modifies the journal email address for all journal rules. The Get-JournalRule cmdlet is used to retrieve all journal rules. The results are piped to the Set-JournalRule cmdlet to modify the journal recipient.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Identity parameter specifies the name or GUID of the rule you want to modify.

The Identity parameter is a positional parameter. When using positional parameters in a command, you can omit the parameter label.

```yaml
Type: RuleIdParameter
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True
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

### -JournalEmailAddress

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The JournalEmailAddress parameter specifies a journal recipient. Journal reports for the specified rule are sent to the journal recipient. You can use any value that uniquely identifies the recipient. For example:

- Name
- Alias
- Distinguished name (DN)
- Canonical DN
- Email address
- GUID

```yaml
Type: RecipientIdParameter
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

The Name parameter specifies the name of the journal rule. The name of the rule can be up to 64 characters.

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

### -Recipient

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Recipient parameter specifies the SMTP address of a mailbox, contact, or distribution group to journal. If you specify a distribution group, all recipients in that distribution group are journaled. All messages sent to or received from a recipient are journaled.

To journal messages from all recipients, use the value $null for this parameter.

```yaml
Type: SmtpAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scope

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Scope parameter specifies the scope of email messages to which the journal rule is applied. You can use the following values:

- Global: Global rules process all email messages that pass through a Transport service. This includes email messages that were already processed by the external and internal rules.
- Internal: Internal rules process email messages sent to and received by recipients in your organization.
- External: External rules process email messages sent to recipients or from senders outside your organization.

```yaml
Type: JournalRuleScope
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
