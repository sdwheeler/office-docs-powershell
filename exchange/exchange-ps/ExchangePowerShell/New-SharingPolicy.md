---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online
author: chrisda
external help file: Microsoft.Exchange.CalendarsAndGroups-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/new-sharingpolicy
schema: 2.0.0
title: New-SharingPolicy
---

# New-SharingPolicy

## SYNOPSIS
This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

Use the New-SharingPolicy cmdlet to create a sharing policy to regulate how users inside your organization can share calendar and contact information with users outside the organization. Users can only share this information after federation has been configured in Exchange. After federation is configured, users can send sharing invitations that comply with a sharing policy to external recipients in other Exchange Server 2010 or later organizations that have federation enabled. A sharing policy needs to get assigned to a mailbox to be effective. If a mailbox doesn't have a specific sharing policy assigned, a default policy enforces the level of sharing permitted for this mailbox.

Sharing policies provide user-established, people-to-people sharing of both calendar and contact information with different types of external users. Sharing policies allow users to share both their free/busy and contact information (including the Calendar and Contacts folders) with recipients in other external federated Exchange organizations. For recipients that aren't in an external federated organization or are in non-Exchange organizations, sharing policies allow people-to-people sharing of their calendar information with anonymous users through the use of Internet Calendar Publishing.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
New-SharingPolicy [-Name] <String> -Domains <MultiValuedProperty>
 [-Confirm]
 [-Default]
 [-DomainController <Fqdn>]
 [-Enabled <Boolean>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
New-SharingPolicy -Name "Contoso" -Domains 'mail.contoso.com: CalendarSharingFreeBusyDetail, ContactsSharing'
```

This example creates the sharing policy Contoso for the contoso.com domain, which is a domain outside the organization. This policy allows users in the contoso.com domain to see detailed free/busy information and contacts. By default, this policy is enabled.

### Example 2
```powershell
New-SharingPolicy -Name "SharingPolicy01" -Domains 'mail.contoso.com: CalendarSharingFreeBusySimple', 'mail.fabrikam.com: CalendarSharingFreeBusySimple' -Enabled $false -Default $true
```

This example creates a default sharing policy, which is applied to all mailboxes that don't implicitly have a sharing policy assigned to them. This sharing policy SharingPolicy01 applies to two different domains, and the sharing policy is disabled.

## PARAMETERS

### -Name

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Name parameter specifies the name of the new sharing policy.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domains

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Domains parameter specifies the domains and the associated sharing options for those domains in the sharing policy. Values for this parameter use the basic syntax: `'Domain: SharingPolicyAction'`.

You can use the following values for `Domain`:

- A domain: For example, `mail.contoso.com`. A domain doesn't include subdomains. You must configure each subdomain separately.
- \*: Share with external federated organizations. For example, another Microsoft 365 organization or an on-premises Exchange organization.
- Anonymous: Share with external, non-federated organizations and individuals with internet access.

You can use the following values for `SharingPolicyAction`:

- CalendarSharingFreeBusySimple: Share free/busy hours only
- CalendarSharingFreeBusyDetail: Share free/busy hours, subject and location
- CalendarSharingFreeBusyReviewer: Share free/busy hours, subject, location and the body of the message or calendar item
- ContactsSharing: Share contacts only

You can specify multiple `'Domain: SharingPolicyAction'` values separated by commas, and you can specify multiple `SharingPolicyAction` values for the same domain separated by commas. For example, `'mail.contoso.com: CalendarSharingFreeBusySimple', 'mail.fabrikam.com: CalendarSharingFreeBusyDetail, ContactsSharing'`.

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

### -Default

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Default switch specifies that this sharing policy is the default sharing policy for all mailboxes. You don't need to specify a value with this switch.

If no sharing policy has been applied to a mailbox, the default policy is automatically applied. If you want to disable sharing across your organization, you can set the default policy as disabled.

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

### -Enabled

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Enabled parameter specifies whether to enable the new sharing policy. Valid input for this parameter is $true or $false. The default is $true.

When the sharing policy is disabled, users who are provisioned to use this policy continue to share information until the sharing policy assistant runs and removes the permissions on the shared folder. The frequency with which the sharing policy assistant runs is assigned in the Set-MailboxServer cmdlet using the SharingPolicySchedule parameter.

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
