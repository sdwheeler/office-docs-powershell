---
applicable: Exchange Online, Security & Compliance, Exchange Online Protection
author: chrisda
external help file: Microsoft.Exchange.ServerStatus-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/release-quarantinemessage
schema: 2.0.0
title: Release-QuarantineMessage
---

# Release-QuarantineMessage

## SYNOPSIS
This cmdlet is available only in the cloud-based service.

Use the Release-QuarantineMessage cmdlet to release messages from quarantine in your cloud-based organization. You can release messages to all original recipients, or to specific recipients.

For files that were quarantined by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you can unblock the files in the respective team sites and document libraries by using the Release-QuarantineMessage cmdlet so users can access, share, and download the files.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

### OrgReleaseToUser
```
Release-QuarantineMessage -User <String[]> [-Identities <QuarantineMessageIdentity[]>]
 [-Identity <QuarantineMessageIdentity>]
 [-AllowSender]
 [-Confirm]
 [-EntityType <Microsoft.Exchange.Management.FfoQuarantine.EntityType>]
 [-Force]
 [-ReportFalsePositive]
 [-WhatIf]
 [<CommonParameters>]
```

### OrgReleaseToAll
```
Release-QuarantineMessage [-Identities <QuarantineMessageIdentity[]>] [-Identity <QuarantineMessageIdentity>]
 [-ReleaseToAll]
 [-AllowSender]
 [-Confirm]
 [-EntityType <Microsoft.Exchange.Management.FfoQuarantine.EntityType>]
 [-Force]
 [-ReportFalsePositive]
 [-WhatIf]
 [<CommonParameters>]
```

### Identities
```
Release-QuarantineMessage -Identities <QuarantineMessageIdentity[]>
 [-Identity <QuarantineMessageIdentity>]
 [-ActionType <ReleaseActionType>]
 [-AllowSender]
 [-Confirm]
 [-EntityType <Microsoft.Exchange.Management.FfoQuarantine.EntityType>]
 [-Force]
 [-ReportFalsePositive]
 [-WhatIf]
 [<CommonParameters>]
```

### IdentityOnly
```
Release-QuarantineMessage -Identity <QuarantineMessageIdentity>
 [-AllowSender]
 [-Confirm]
 [-EntityType <Microsoft.Exchange.Management.FfoQuarantine.EntityType>]
 [-Force]
 [-ReportFalsePositive]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com. Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft. An admin releases both of these messages to admin@contoso.com. The first released message that reaches the admin mailbox is delivered. The second released message is identified as duplicate delivery and is skipped. Message are identified as duplicates if they have the same message ID and received time.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Get-QuarantineMessage -MessageID "<5c695d7e-6642-4681-a4b0-9e7a86613cb7@contoso.com>" | Release-QuarantineMessage -User julia@contoso.com
```

This example uses the Get-QuarantineMessage cmdlet to release the quarantined message with the Message-ID value `<5c695d7e-6642-4681-a4b0-9e7a86613cb7@contoso.com>` to an original recipient julia@contoso.com.

### Example 2
```powershell
Release-QuarantineMessage -Identity c14401cf-aa9a-465b-cfd5-08d0f0ca37c5\4c2ca98e-94ea-db3a-7eb8-3b63657d4db7 -ReleaseToAll
```

This example releases the quarantined message with the specified Identity value to all original recipients.

### Example 3
```powershell
Get-QuarantineMessage | Release-QuarantineMessage -ReleaseToAll
```

This example releases all messages to all original recipients.

### Example 4
```powershell
$q = Get-QuarantineMessage -QuarantineTypes SPOMalware

$q[-1] | Release-QuarantineMessage -ReleaseToAll
```

This example releases a file that was quarantined as part of Safe Attachments for SharePoint, OneDrive, and Microsoft Teams. The first command stores all quarantined files in the variable $q. The second command releases the last file in the list. For more information about elements in arrays and index numbers, see [Accessing and Using Array Elements](https://learn.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays#accessing-and-using-array-elements).

## PARAMETERS

### -Identities

> Applicable: Exchange Online, Security & Compliance, Exchange Online Protection

The Identities parameter identifies quarantined messages for bulk operations. You identify the messages by using the syntax: `value1,value2,...valueN`. The value is a unique quarantined message identifier in the format `GUID1\GUID2` (for example `c14401cf-aa9a-465b-cfd5-08d0f0ca37c5\4c2ca98e-94ea-db3a-7eb8-3b63657d4db7`).

You can find the identity value for a quarantined message by using the Get-QuarantineMessage cmdlet.

When you use this parameter, the Identity parameter is required, but the value is ignored. For example, use the value 000 for the Identity parameter.

```yaml
Type: QuarantineMessageIdentity[]
Parameter Sets: Identities, OrgReleaseToAll, OrgReleaseToUser
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity

> Applicable: Exchange Online, Security & Compliance, Exchange Online Protection

The Identity parameter specifies the quarantined message that you want to release. The value is a unique quarantined message identifier in the format `GUID1\GUID2` (for example `c14401cf-aa9a-465b-cfd5-08d0f0ca37c5\4c2ca98e-94ea-db3a-7eb8-3b63657d4db7`).

You can find the Identity value for a quarantined message by using the Get-QuarantineMessage cmdlet.

```yaml
Type: QuarantineMessageIdentity
Parameter Sets: Identities, OrgReleaseToAll, OrgReleaseToUser, IdentityOnly
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -ReleaseToAll

> Applicable: Exchange Online, Security & Compliance, Exchange Online Protection

The ReleaseToAll switch releases the quarantined message to all original recipients. You don't need to specify a value with this switch.

This switch is required for the quarantine type SPOMalware.

If you previously used the User parameter or the ReleaseToAll switch to release the quarantined message to some or all of the original recipients, those recipients are skipped when you use the ReleaseToAll switch again.

You can't use the ReleaseToAll switch and the User parameter in the same command.

```yaml
Type: SwitchParameter
Parameter Sets: OrgReleaseToAll
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User

> Applicable: Exchange Online, Security & Compliance, Exchange Online Protection

The User parameter specifies the email address of the user to whom you want to release the quarantined message. You can specify multiple email addresses separated by commas.

You can use this parameter to release the message to recipients of the original message, or to any other email addresses in the organization.

If you previously used the ReleaseToAll switch to release the quarantined message to all original recipients, and you later release the message again with the User parameter, any original recipients you specify with the User parameter are skipped.

```yaml
Type: String[]
Parameter Sets: OrgReleaseToUser
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ActionType

> Applicable: Exchange Online, Security & Compliance, Exchange Online Protection

The ActionType parameter specifies the release action type. Valid values are:

- Deny
- Release: Use this value to release messages or approve requests to release messages.
- Request

```yaml
Type: ReleaseActionType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowSender

> Applicable: Exchange Online, Security & Compliance, Exchange Online Protection

The AllowSender switch specifies that all future messages from the sender won't be quarantined. You don't need to specify a value with this switch.

If the message was quarantined because of a transport rule or blocked sender, messages from the sender can still be blocked in the future.

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

> Applicable: Exchange Online, Security & Compliance, Exchange Online Protection

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

### -EntityType

> Applicable: Exchange Online, Security & Compliance, Exchange Online Protection

The EntityType parameter filters the results by EntityType. Valid values are:

- Email
- SharePointOnline
- Teams (currently in Preview)
- DataLossPrevention

```yaml
Type: Microsoft.Exchange.Management.FfoQuarantine.EntityType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

> Applicable: Exchange Online, Security & Compliance, Exchange Online Protection

The Force switch hides warning or confirmation messages. You don't need to specify a value with this switch.

Use this switch whenever you attempt to re-release previously released messages from quarantine.

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

### -ReportFalsePositive

> Applicable: Exchange Online, Security & Compliance, Exchange Online Protection

The ReportFalsePositive switch specifies whether to report the message as a false positive to Microsoft (good message marked as bad). You don't need to specify a value with this switch.

This switch is available only for quarantined spam messages.

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

> Applicable: Exchange Online, Security & Compliance, Exchange Online Protection

The WhatIf switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch.

The WhatIf switch doesn't work in Security & Compliance PowerShell.

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
