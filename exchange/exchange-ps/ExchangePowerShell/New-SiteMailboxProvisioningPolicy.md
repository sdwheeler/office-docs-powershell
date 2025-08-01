---
applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.WebClient-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/new-sitemailboxprovisioningpolicy
schema: 2.0.0
title: New-SiteMailboxProvisioningPolicy
---

# New-SiteMailboxProvisioningPolicy

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the New-SiteMailboxProvisioningPolicy cmdlet to create provisioning policies for site mailboxes.

Site mailboxes were deprecated in Exchange Online and SharePoint Online in 2017. For more information, see [Deprecation of Site Mailboxes](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/deprecation-of-site-mailboxes/ba-p/93028).

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
New-SiteMailboxProvisioningPolicy [-Name] <String>
 [-AliasPrefix <String>]
 [-Confirm]
 [-DefaultAliasPrefixEnabled <Boolean>]
 [-DomainController <Fqdn>]
 [-IsDefault]
 [-IssueWarningQuota <ByteQuantifiedSize>]
 [-MaxReceiveSize <ByteQuantifiedSize>]
 [-ProhibitSendReceiveQuota <ByteQuantifiedSize>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Site mailboxes allow access to both Microsoft SharePoint documents and Exchange email using the same client interface. Site mailbox provisioning policies apply settings to new site mailboxes that you create. You can create multiple site mailbox provisioning policies, but only the default policy is followed when users create site mailboxes. The default site mailbox provisioning policy is named Default.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
New-SiteMailboxProvisioningPolicy -Name SM_ProvisioningPolicy -IsDefault -IssueWarningQuota 9GB -ProhibitSendReceiveQuota 10GB -MaxReceiveSize 50MB
```

This example creates the default provisioning policy named SM\_ProvisioningPolicy that has the following settings:

- The warning quota for the site mailboxes is 9 GB.
- The site mailboxes are prohibited from receiving messages when the mailbox size reaches 10 GB.
- The maximum size of email messages that can be sent to site mailboxes is 50 MB.

### Example 2
```powershell
New-SiteMailboxProvisioningPolicy -Name SM_DefaultPolicy -IsDefault
```

This example creates the default provisioning policy named SM\_DefaultPolicy that uses the defaults for send and receive quotas.

### Example 3
```powershell
New-SiteMailboxProvisioningPolicy -Name SM_DefaultPolicy -IsDefault -AliasPrefix Project
```

This example creates the default provisioning policy named SM\_DefaultPolicy and sets the AliasPrefix value to Project. When you create new site mailboxes, the prefix Project- is automatically added to the alias.

## PARAMETERS

### -Name

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Name parameter specifies the unique name of the site mailbox provisioning policy. The maximum length is 64 characters. If the value contains spaces, enclose the value in quotation marks (").

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

### -AliasPrefix

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The AliasPrefix parameter specifies the custom text prefix to add to the aliases of new site mailboxes. Valid values are:

- A text string that's 8 characters or less. When you specify a text value, the value of the DefaultAliasPrefixEnabled parameter ignored and aliases get the text prefix you specified.
- The value $null. This is the default value. The results of this value depend on the DefaultAliasPrefixEnabled parameter value. When it's $true, aliases get the default prefix text. When it's $false, aliases don't get any prefix text.

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

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

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

### -DefaultAliasPrefixEnabled

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The DefaultAliasPrefixEnabled parameter specifies whether new site mailboxes have the default prefix text added to the alias. Valid values are:

- $true: Aliases get the default prefix text. This is the default value. In Microsoft 365, the default prefix text is `SMO-` (for example, the alias value `BugBash_2016` becomes `SMO-BugBash_2016`). In on-premises Exchange, the default prefix text is `SM-` (for example, the alias value `BugBash_2016` becomes `SM-BugBash_2016`).
- $false: Aliases don't get the default prefix text.

The value of this parameter is related to the value of the AliasPrefix parameter. If you specify a text string for AliasPrefix, the DefaultAliasPrefixEnabled value is ignored. Specifying a text value for AliasPrefix automatically sets the value to $false, but even if you set it to $true, the default alias prefix text isn't used.

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

### -DomainController

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

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

### -IsDefault

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The IsDefault switch specifies that the site mailbox provisioning policy is the default policy. You don't need to specify a value with this switch.

You can have multiple policies, but only the default policy is followed when users create site mailboxes.

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

### -IssueWarningQuota

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The IssueWarningQuota parameter specifies the warning threshold for the size of the mailbox. If the mailbox reaches or exceeds this size, the user receives a descriptive warning message.

A valid value is a number up to 1.999999999 terabytes (2199023254528 bytes) or the value unlimited. When you enter a number, you can qualify it with one of the following units:

- B (bytes)
- KB (kilobytes)
- MB (megabytes)
- GB (gigabytes)
- TB (terabytes)

Unqualified values are typically treated as bytes, but small values may be rounded up to the nearest kilobyte.

The IssueWarningQuota value must be less than or equal to the ProhibitSendReceiveQuota value.

The default value is 49 GB.

```yaml
Type: ByteQuantifiedSize
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxReceiveSize

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The MaxReceiveSize parameter specifies the maximum size of a message that can be sent to the site mailbox. Messages larger than the maximum size are rejected.

When you enter a value, qualify the value with one of the following units:

- B (bytes)
- KB (kilobytes)
- MB (megabytes)
- GB (gigabytes)

Unqualified values are typically treated as bytes, but small values may be rounded up to the nearest kilobyte.

A valid value is a number up to 1.999999 gigabytes (2147482624 bytes) or the value unlimited. The default value is 36 MB.

```yaml
Type: ByteQuantifiedSize
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProhibitSendReceiveQuota

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ProhibitSendReceiveQuota parameter specifies a size limit for the mailbox. If the mailbox reaches or exceeds this size, the mailbox can't send or receive new messages. Messages sent to the mailbox are returned to the sender with a descriptive error message. This value effectively determines the maximum size of the mailbox.

A valid value is a number up to 1.999999999 terabytes (2199023254528 bytes) or the value unlimited. When you enter a number, you can qualify it with one of the following units:

- B (bytes)
- KB (kilobytes)
- MB (megabytes)
- GB (gigabytes)
- TB (terabytes)

Unqualified values are typically treated as bytes, but small values may be rounded up to the nearest kilobyte.

The value must be greater than or equal to the ProhibitSendQuota or IssueWarningQuota values.

The default value is 50 GB.

```yaml
Type: ByteQuantifiedSize
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

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
