---
applicable: Exchange Server 2016, Exchange Server 2019, Security & Compliance
author: chrisda
external help file: Microsoft.Exchange.RecordsandEdge-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/new-compliancesearch
schema: 2.0.0
title: New-ComplianceSearch
---

# New-ComplianceSearch

## SYNOPSIS
This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

Use the New-ComplianceSearch cmdlet to create compliance searches in Exchange Server 2016 or later and in the Microsoft Purview compliance portal. You use this cmdlet to define the search criteria.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
New-ComplianceSearch [-Name] <String>
 [-AllowNotFoundExchangeLocationsEnabled <Boolean>]
 [-Case <String>]
 [-Confirm]
 [-ContentMatchQuery <String>]
 [-Description <String>]
 [-ExchangeLocation <String[]>]
 [-ExchangeLocationExclusion <String[]>]
 [-Force]
 [-HoldNames <String[]>]
 [-IncludeOrgContent <Boolean>]
 [-IncludeUserAppContent <Boolean>]
 [-Language <CultureInfo>]
 [-LogLevel <ComplianceJobLogLevel>]
 [-PublicFolderLocation <String[]>]
 [-RefinerNames <String[]>]
 [-SharePointLocation <String[]>]
 [-SharePointLocationExclusion <String[]>]
 [-StatusMailRecipients <String[]>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
A compliance search requires at least one location. For example, mailboxes using the ExchangeLocation parameter, or SharePoint sites using the SharePointLocation parameter.

After you create a compliance search using the New-ComplianceSearch cmdlet, you run the search using the Start-ComplianceSearch cmdlet.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

In on-premises Exchange, this cmdlet is available in the Mailbox Search role. By default, this role is assigned only to the Discovery Management role group.

To use this cmdlet in Security & Compliance PowerShell, you need to be assigned permissions. For more information, see [Permissions in the Microsoft Purview compliance portal](https://learn.microsoft.com/purview/microsoft-365-compliance-center-permissions).

## EXAMPLES

### Example 1
```powershell
New-ComplianceSearch -Name "Hold Project X" -ExchangeLocation "Finance Department"
```

This example creates a new compliance search named Hold-Project X that searches all members of the distribution group named Finance Department. Because the search doesn't use the ContentMatchQuery parameter, all items in the mailboxes are searched.

### Example 2
```powershell
New-ComplianceSearch -Name "Hold-Tailspin Toys" -ExchangeLocation "Research Department" -ContentMatchQuery "'Patent' AND 'Project Tailspin Toys'"
```

This example creates a new compliance search named Hold-Tailspin Toys that searches all member of the distribution group named Research Department. Because the search uses the ContentMatchQuery parameter, only messages that match the query are searched.

### Example 3
```powershell
New-ComplianceSearch -Name "AnnBeebe-InactiveMailbox" -ExchangeLocation .annb@contoso.onmicrosoft.com -AllowNotFoundExchangeLocationsEnabled $true
```

This example creates a new compliance search named AnnBeebe-InactiveMailbox that searches an inactive mailbox and returns all items in the mailbox. To search inactive mailboxes, you need to use the primary SMTP address of the inactive mailbox, prepended with a period ("."). You also need to include the AllowNotFoundExchangeLocationsEnabled parameter so the search doesn't try to validate the existence of the inactive mailbox.

## PARAMETERS

### -Name

> Applicable: Exchange Server 2016, Exchange Server 2019, Security & Compliance

The Name parameter specifies the name of the compliance search. If the value contains spaces, enclose the value in quotation marks.

Don't use spaces in the value of this parameter if you plan on using the Case parameter. If the Name parameter contains spaces, the value of the ExchangeLocation parameter is cleared when you use the Case parameter.

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

### -AllowNotFoundExchangeLocationsEnabled

> Applicable: Exchange Server 2016, Exchange Server 2019, Security & Compliance

The AllowNotFoundExchangeLocationsEnabled parameter specifies whether to include mailboxes other than regular user mailboxes in the compliance search. Valid values are:

- $true: The search doesn't try to validate the existence of the mailbox before proceeding. This value is required if you want to search mailboxes that don't resolve as regular mailboxes.
- $false: The search tries to validate the existence of the mailbox before proceeding. If you specify a mailbox that isn't a regular user mailbox, the search will fail. This is the default value.

The mailbox types that are affected by the value of this parameter include:

- Inactive mailboxes
- Users without an Exchange Online license who use Office applications
- Microsoft 365 guest users
- On-premises users whose identity is synchronized with your Microsoft 365 organization

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

### -Case

> Applicable: Security & Compliance

This parameter is available only in the cloud-based service.

The Case parameter specifies the name of an eDiscovery Standard case to associate the new compliance search with. If the value contains spaces, enclose the value in quotation marks.

You can't use this parameter to create compliance searches associated with eDiscovery Premium cases.

If the Name parameter contains spaces, the value of the ExchangeLocation parameter is cleared when you use the Case parameter.

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

> Applicable: Exchange Server 2016, Exchange Server 2019, Security & Compliance

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

### -ContentMatchQuery

> Applicable: Exchange Server 2016, Exchange Server 2019, Security & Compliance

The ContentMatchQuery parameter specifies a content search filter.

This parameter uses a text search string or a query that's formatted by using the Keyword Query Language (KQL). For more information, see [Keyword Query Language (KQL) syntax reference](https://learn.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) and [Keyword queries and search conditions for eDiscovery](https://learn.microsoft.com/purview/ediscovery-keyword-queries-and-search-conditions).

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

### -Description

> Applicable: Exchange Server 2016, Exchange Server 2019, Security & Compliance

The Description parameter specifies an optional description for the compliance search. If the value contains spaces, enclose the value in quotation marks.

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

### -ExchangeLocation

> Applicable: Exchange Server 2016, Exchange Server 2019, Security & Compliance

The ExchangeLocation parameter specifies the mailboxes to include. Valid values are:

- A regular user mailbox. Including other types of mailboxes (for example, inactive mailboxes or Microsoft 365 guest users) is controlled by the AllowNotFoundExchangeLocationsEnabled parameter.
- A distribution group or mail-enabled security group (all mailboxes that are currently members of the group).
- The value All for all mailboxes. You can only use this value by itself.

To specify a mailbox or distribution group, use the email address. You can specify multiple values separated by commas.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -ExchangeLocationExclusion

> Applicable: Exchange Server 2016, Exchange Server 2019, Security & Compliance

This parameter is functional only in on-premises Exchange.

This parameter specifies the mailboxes to exclude when you use the value All for the ExchangeLocation parameter. Valid values are:

- A mailbox
- A distribution group or mail-enabled security group (all mailboxes that are currently members of the group).

To specify a mailbox or distribution group, use the email address. You can specify multiple values separated by commas.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

> Applicable: Exchange Server 2016, Exchange Server 2019, Security & Compliance

The Force switch hides warning or confirmation messages. You don't need to specify a value with this switch.

You can use this switch to run tasks programmatically where prompting for administrative input is inappropriate.

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

### -HoldNames

> Applicable: Security & Compliance

This parameter is available only in the cloud-based service.

The HoldNames parameter specifies that the content locations that have been placed on hold in the specified eDiscovery case will be searched. You use the value All for this parameter. You also need to specify the name of an eDiscovery case by using the Case parameter.

Also, if a content location was placed on a query-based case hold, only items that are on hold will be searched when you run this compliance search. For example, if a user was placed on a query-based case hold that preserves items that were sent or created before a specific date, only those items would be searched by using the search criteria specified by this compliance search.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeOrgContent

> Applicable: Security & Compliance

{{ Fill IncludeOrgContent Description }}

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

### -IncludeUserAppContent

> Applicable: Security & Compliance

This parameter is available only in the cloud-based service.

The IncludeUserAppContent parameter specifies that you want to search the cloud-based storage location for users who don't have a regular Microsoft 365 user account in your organization. These types of users include users without an Exchange Online license who use Office applications, Microsoft 365 guest users, and on-premises users whose identity is synchronized with your Microsoft 365 organization. Valid values are:

- $true: The cloud-based storage location for the users specified in the ExchangeLocation parameter will be included in the search. If you use the value All for the ExchangeLocation parameter, the cloud-based storage location for any guest or on-premises user will be included in the search.
- $false: The cloud-based storage location for the users specified in the ExchangeLocation parameter won't be included in the search. This is the default value.

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

### -Language

> Applicable: Exchange Server 2016, Exchange Server 2019, Security & Compliance

The Language parameter specifies the language for the compliance search.

Valid input for this parameter is a supported culture code value from the Microsoft .NET Framework CultureInfo class. For example, da-DK for Danish or ja-JP for Japanese. For more information, see [CultureInfo Class](https://learn.microsoft.com/dotnet/api/system.globalization.cultureinfo).

```yaml
Type: CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogLevel

> Applicable: Exchange Server 2016, Exchange Server 2019

This parameter is available only in on-premises Exchange.

This parameter is reserved for internal Microsoft use.

```yaml
Type: ComplianceJobLogLevel
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicFolderLocation

> Applicable: Security & Compliance

This parameter is available only in the cloud-based service.

The PublicFolderLocation parameter specifies that you want to include all public folders in the search. You use the value All for this parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RefinerNames

> Applicable: Security & Compliance

This parameter is available only in the cloud-based service.

This parameter is reserved for internal Microsoft use.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharePointLocation

> Applicable: Security & Compliance

This parameter is available only in the cloud-based service.

The SharePointLocation parameter specifies the SharePoint sites to include. You identify the site by its URL value, or you can use the value All to include all sites.

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharePointLocationExclusion

> Applicable: Security & Compliance

This parameter is available only in the cloud-based service.

This parameter is reserved for internal Microsoft use.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StatusMailRecipients

> Applicable: Exchange Server 2016, Exchange Server 2019

This parameter is available only in on-premises Exchange.

This parameter is reserved for internal Microsoft use.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

> Applicable: Exchange Server 2016, Exchange Server 2019, Security & Compliance

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
