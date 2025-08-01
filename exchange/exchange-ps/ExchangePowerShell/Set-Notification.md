---
applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online
author: chrisda
external help file: Microsoft.Exchange.WebClient-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/set-notification
schema: 2.0.0
title: Set-Notification
---

# Set-Notification

## SYNOPSIS
This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

> [!NOTE]
> This cmdlet will be deprecated in the cloud-based service. The classic Exchange admin center was deprecated in the cloud-based service in 2023.

Use the Set-Notification cmdlet to modify notification events that are shown in the notification viewer in the Exchange admin center (EAC). These notifications are related to the following events:

- Mailbox moves and migrations.
- Expiring and expired certificates.
- Exporting mailbox content to .pst files.
- Importing mailbox content from .pst files.
- Restoring deleted mailboxes.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

### Identity
```
Set-Notification [-Identity] <EwsStoreObjectIdParameter> -NotificationEmails <MultiValuedProperty>
 [-Confirm]
 [-DomainController <Fqdn>]
 [-WhatIf]
 [<CommonParameters>]
```

### Settings
```
Set-Notification -NotificationEmails <MultiValuedProperty> -ProcessType <AsyncOperationType>
 [-Confirm]
 [-DomainController <Fqdn>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Set-Notification -NotificationEmails john@contoso.com,kweku@contoso.com -ProcessType CertExpiry
```

This example configures all expiring and expired certificate notification events to send notification email messages to john@contoso.com and kweku@contoso.com.

### Example 2
```powershell
Set-Notification -Identity 0259ec74-3539-4195-ab4f-de93e654ceaf -NotificationEmails laura@contoso.com,julia@contoso.com
```

This example configures the specified notification event to send notification email messages to laura@contoso.com and julia@contoso.com.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Identity parameter specifies the notification event that you want to modify. You identify the notification event by its AlternativeID property value (a GUID). You can find this value by running the command: `Get-Notification | Format-List DisplayName,AlternativeID,StartTime,Status,Type`.

Typically, it only makes sense to modify notification recipients for events that haven't completed (if the event has completed, no more notification messages will be sent).

You can't use this parameter with the ProcessType parameter.

```yaml
Type: EwsStoreObjectIdParameter
Parameter Sets: Identity
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -NotificationEmails

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The NotificationEmails parameter specifies the recipients for notification emails related to notification events. You can specify multiple recipients separated by commas.

You need to use this parameter with either the ProcessType or Identity parameters:

- ProcessType: The only ProcessType value that's allowed is CertExpiry.
- Identity: You can modify the notification recipients for all types of notification events (CertExpiry, ExportPST, ImportPST, MailboxRestore, and Migration).

For Migration events, you can also use the NotificationEmails parameter on the New-MigrationBatch, Set-MigrationBatch and Complete-MigrationBatch cmdlets to specify the notification email recipients.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProcessType

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This parameter is available only in on-premises Exchange.

The ProcessType parameter specifies the notification event type that sends notification emails to users (specified by the required NotificationEmails parameter). The users receive email notification messages for all events of the specified type. The only valid value for this is parameter is CertExpiry.

You can't use this parameter with the Identity parameter.

```yaml
Type: AsyncOperationType
Parameter Sets: Settings
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

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

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

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

### -WhatIf

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

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
To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](https://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data.

## OUTPUTS

### Output types
To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](https://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data.

## NOTES

## RELATED LINKS
