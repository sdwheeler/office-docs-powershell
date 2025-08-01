---
applicable: Exchange Online
author: chrisda
external help file: Microsoft.Exchange.RolesAndAccess-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/undo-softdeletedmailbox
schema: 2.0.0
title: Undo-SoftDeletedMailbox
---

# Undo-SoftDeletedMailbox

## SYNOPSIS
This cmdlet is available only in the cloud-based service.

Use the Undo-SoftDeletedMailbox cmdlet to recover a mailbox that has been deleted. Mailboxes can be recovered within 30 days of being deleted.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

### PublicFolder
```
Undo-SoftDeletedMailbox [-SoftDeletedObject] <MailboxIdParameter>
 [-DisplayName <String>]
 [-PublicFolder]
 [-Confirm]
 [-Name <String>]
 [-WhatIf]
 [<CommonParameters>]
```

### SoftDeletedMailbox
```
Undo-SoftDeletedMailbox [-SoftDeletedObject] <MailboxIdParameter>
 [-Password <SecureString>]
 [-WindowsLiveID <WindowsLiveId>]
 [-Confirm]
 [-DisplayName <String>]
 [-Name <String>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Use the Undo-SoftDeletedMailbox cmdlet to recover a mailbox that has been deleted. When a mailbox is deleted with the Remove-Mailbox or Disable-Mailbox cmdlet, it's not actually deleted. It's hidden in Exchange and moved in Active Directory to the organizational unit (OU) Soft Deleted Objects. This enables administrators to recover deleted mailboxes for up to 30 days after deletion.

If the Microsoft account (formerly known as a Windows Live ID) wasn't deleted when the mailbox was deleted, you have to specify a new Microsoft account and password when you use the Undo-SoftDeletedMailbox cmdlet to recover a mailbox.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Undo-SoftDeletedMailbox -SoftDeletedObject florencef
```

This example recovers the deleted mailbox for the user Florence Flipo. When this mailbox was deleted, the associated Microsoft account was also deleted.

### Example 2
```powershell
Undo-SoftDeletedMailbox bjohnson@contoso.edu -WindowsLiveID brianj@contoso.edu -Password (Get-Credential).password
```

This example recovers the deleted mailbox for the user Brian Johnson. When this mailbox was deleted, the associated Microsoft account wasn't deleted. Note that a new Microsoft account and password have to be created to recover this mailbox. In the scenario, the old Microsoft account is retained as a proxy address for the mailbox.

## PARAMETERS

### -SoftDeletedObject

> Applicable: Exchange Online

The SoftDeletedObject parameter specifies the deleted mailbox to recover. You can use the alias or the email address of the deleted mailbox for the value of this parameter. Use the Get-Mailbox -SoftDeletedMailbox command to get information for deleted mailboxes.

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

### -PublicFolder

> Applicable: Exchange Online

The PublicFolder switch is required to recover public folder mailboxes. You don't need to specify a value with this switch.

Public folder mailboxes are specially designed mailboxes that store the hierarchy and content of public folders.

```yaml
Type: SwitchParameter
Parameter Sets: PublicFolder
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### -DisplayName

> Applicable: Exchange Online

The DisplayName parameter specifies the new display name for the recovered mailbox.

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

### -Name

> Applicable: Exchange Online

The Name parameter specifies a new value for the Name property of the recovered mailbox. Otherwise, the original value is retained when the mailbox is recovered. The new name value is also used in the DistinguishedName property.

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

### -Password

> Applicable: Exchange Online

The Password parameter specifies a new password for the mailbox.

You can use the following methods as a value for this parameter:

- `(ConvertTo-SecureString -String '<password>' -AsPlainText -Force)`.
- Before you run this command, store the password as a variable (for example, `$password = Read-Host "Enter password" -AsSecureString`), and then use the variable (`$password`) for the value.
- `(Get-Credential).password` to be prompted to enter the password securely when you run this command.

You have to include the Password parameter to recover a deleted mailbox with an existing Microsoft account (formerly known as a Windows Live ID) that wasn't deleted with the mailbox.

```yaml
Type: SecureString
Parameter Sets: SoftDeletedMailbox
Aliases:

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

### -WindowsLiveID

> Applicable: Exchange Online

The WindowsLiveID parameter specifies a new Microsoft account (formerly known as a Windows Live ID) and primary SMTP address for the mailbox. The previous Microsoft account is retained as a proxy address for the mailbox.

You have to include the WindowsLiveID parameter to recover a deleted mailbox with an existing Microsoft account that wasn't deleted with the mailbox.

```yaml
Type: WindowsLiveId
Parameter Sets: SoftDeletedMailbox
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
To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](https://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data.

## OUTPUTS

### Output types
To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](https://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data.

## NOTES

## RELATED LINKS
