---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection
author: chrisda
external help file: Microsoft.Exchange.CalendarsAndGroups-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/set-organizationrelationship
schema: 2.0.0
title: Set-OrganizationRelationship
---

# Set-OrganizationRelationship

## SYNOPSIS
This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

Use the Set-OrganizationRelationship cmdlet to modify existing organization relationships. Organization relationships define the settings that are used with external Exchange organizations to access calendar free/busy information or to move mailboxes between on-premises Exchange servers and Exchange Online as part of hybrid deployments.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Set-OrganizationRelationship [-Identity] <OrganizationRelationshipIdParameter>
 [-ArchiveAccessEnabled <Boolean>]
 [-Confirm]
 [-DeliveryReportEnabled <Boolean>]
 [-DomainController <Fqdn>]
 [-DomainNames <MultiValuedProperty>]
 [-Enabled <Boolean>]
 [-Force]
 [-FreeBusyAccessEnabled <Boolean>]
 [-FreeBusyAccessLevel <FreeBusyAccessLevel>]
 [-FreeBusyAccessScope <GroupIdParameter>]
 [-MailboxMoveCapability <MailboxMoveCapability>]
 [-MailboxMoveEnabled <Boolean>]
 [-MailboxMovePublishedScopes <MultiValuedProperty>]
 [-MailTipsAccessEnabled <Boolean>]
 [-MailTipsAccessLevel <MailTipsAccessLevel>]
 [-MailTipsAccessScope <GroupIdParameter>]
 [-Name <String>]
 [-OAuthApplicationId <String>]
 [-OrganizationContact <SmtpAddress>]
 [-PhotosEnabled <Boolean>]
 [-TargetApplicationUri <Uri>]
 [-TargetAutodiscoverEpr <Uri>]
 [-TargetOwaURL <Uri>]
 [-TargetSharingEpr <Uri>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Set-OrganizationRelationship -Identity "Fourth Coffee" -FreeBusyAccessLevel LimitedDetails
```

This example modifies the free/busy access level to LimitedDetails, which includes time, subject, and location.

### Example 2
```powershell
Set-OrganizationRelationship -Identity "Contoso" -Enabled $false
```

This example disables the organization relationship with Contoso

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The Identity parameter specifies the organization relationship that you want to modify. You can use any value that uniquely identifies the organization relationship. For example:

- Name
- Canonical name
- GUID

```yaml
Type: OrganizationRelationshipIdParameter
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -ArchiveAccessEnabled

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The ArchiveAccessEnabled parameter specifies whether the organization relationship has been configured to provide remote archive access. Valid values are:

- $true: The external organization provides remote access to mailbox archives.
- $false: The external organization doesn't provide remote access to mailbox archives. This is the default value

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

### -Confirm

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

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

### -DeliveryReportEnabled

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The DeliveryReportEnabled parameter specifies whether Delivery Reports should be shared over the organization relationship. Valid values are:

- $true: Delivery Reports should be shared over the organization relationship. This value means the organization has agreed to share all Delivery Reports with the external organization, and the organization relationship should be used to retrieve Delivery Report information from the external organization.
- $false: Delivery Reports shouldn't be shared over the organization relationship. This is the default value

For message tracking to work in a cross-premises Exchange scenario, this parameter must be set to $true on both sides of the organization relationship. If the value of this parameter is set to $false on one or both sides of the organization relationship, message tracking between the organizations won't work in either direction.

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

### -DomainNames

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The DomainNames parameter specifies the SMTP domains of the external organization. You can specify multiple domains separated by commas (for example, "contoso.com","northamerica.contoso.com").

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -Enabled

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The Enabled parameter specifies whether to enable the organization relationship. Valid values are:

- $true: The organization relationship is enabled. This is the default value.
- $false: The organization relationship is disabled. This value completely stops sharing for the organization relationship.

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

### -Force

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

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

### -FreeBusyAccessEnabled

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The FreeBusyAccessEnabled parameter specifies whether the organization relationship should be used to retrieve free/busy information from the external organization. Valid values are:

- $true: Free/busy information is retrieved from the external organization.
- $false: Free/busy information isn't retrieved from the external organization. This is the default value.

You control the free/busy access level and scope by using the FreeBusyAccessLevel and FreeBusyAccessScope parameters.

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

### -FreeBusyAccessLevel

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The FreeBusyAccessLevel parameter specifies the maximum amount of detail returned to the requesting organization. Valid values are:

- None: No free/busy access.
- AvailabilityOnly: Free/busy access with time only.
- LimitedDetails: Free/busy access with time, subject, and location.

This parameter is only meaningful when the FreeBusyAccessEnabled parameter value is $true.

```yaml
Type: FreeBusyAccessLevel
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FreeBusyAccessScope

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The FreeBusyAccessScope parameter specifies a mail-enabled security group in the internal organization that contains users whose free/busy information is accessible by an external organization. You can use any value that uniquely identifies the group. For example:

- Name
- Distinguished name (DN)
- Canonical DN
- GUID

This parameter is only meaningful when the FreeBusyAccessEnabled parameter value is $true.

```yaml
Type: GroupIdParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MailboxMoveCapability

> Applicable: Exchange Online, Exchange Online Protection

This parameter is available only in the cloud-based service.

The MailboxMoveCapability parameter is used in cross-tenant mailbox migrations. Valid values are:

- Inbound
- Outbound
- RemoteInbound
- RemoteOutbound

For more information, see [Cross-tenant mailbox migration](https://learn.microsoft.com/microsoft-365/enterprise/cross-tenant-mailbox-migration).

```yaml
Type: MailboxMoveCapability
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MailboxMoveEnabled

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The MailboxMoveEnabled parameter specifies whether the organization relationship enables moving mailboxes to or from the external organization. Valid values are:

- $true: Mailbox moves to or from the external organization are allowed.
- $false: Mailbox moves to from the external organization aren't allowed. This is the default value.

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

### -MailboxMovePublishedScopes

> Applicable: Exchange Online, Exchange Online Protection

This parameter is available only in the cloud-based service.

The MailboxMovePublishedScopes parameter is used in cross-tenant mailbox migrations to specify the mail-enabled security groups whose members are allowed to migrate. You can use any value that uniquely identifies the group. For example:

- Name
- Distinguished name (DN)
- Canonical DN
- GUID

To enter multiple values and overwrite any existing entries, use the following syntax: `Value1,Value2,...ValueN`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

To add or remove one or more values without affecting any existing entries, use the following syntax: `@{Add="Value1","Value2"...; Remove="Value3","Value4"...}`.

For more information, see [Cross-tenant mailbox migration](https://learn.microsoft.com/microsoft-365/enterprise/cross-tenant-mailbox-migration).

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

### -MailTipsAccessEnabled

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The MailTipsAccessEnabled parameter specifies whether MailTips for users in this organization are returned over this organization relationship. Valid values are:

- $true: MailTips for users in this organization are returned over the organization relationship.
- $false: MailTips for users in this organization aren't returned over the organization relationship. This is the default value.

You control the MailTips access level by using the MailTipsAccessLevel parameter.

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

### -MailTipsAccessLevel

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The MailTipsAccessLevel parameter specifies the level of MailTips data externally shared over this organization relationship. This parameter can have the following values:

- All: All MailTips are returned, but the recipients in the remote organization are considered external. For the Auto Reply MailTip, the external Auto Reply message is returned.
- Limited: Only those MailTips that could prevent a non-delivery report (NDR) or an Auto Reply are returned. Custom MailTips, the Large Audience MailTip, and Moderated Recipient MailTips won't be returned.
- None: No MailTips are returned to the remote organization. This is the default value.

This parameter is only meaningful when the MailTipsAccessEnabled parameter value is $true.

```yaml
Type: MailTipsAccessLevel
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MailTipsAccessScope

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The MailTipsAccessScope parameter specifies a mail-enabled security group in the internal organization that contains users whose free/busy information is accessible by an external organization. You can use any value that uniquely identifies the group. For example:

- Name
- Distinguished name (DN)
- Canonical DN
- GUID

The default value is blank ($null), which means no group is specified.

If you use this parameter, recipient-specific MailTips are returned only for those recipients that are members of the specified group. The recipient-specific MailTips are:

- Auto Reply
- Mailbox Full
- Custom

If you don't use this parameter, recipient-specific MailTips are returned for all recipients in the organization.

This restriction only applies to mailboxes, mail users, and mail contacts. It doesn't apply to distribution groups.

```yaml
Type: GroupIdParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The Name parameter specifies the unique name of the organization relationship. The maximum length is 64 characters.

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

### -OAuthApplicationId

> Applicable: Exchange Online, Exchange Online Protection

This parameter is available only in the cloud-based service.

The OAuthApplicationId is used in cross-tenant mailbox migrations to specify the application ID of the mailbox migration app that you consented to. For more information, see [Cross-tenant mailbox migration](https://learn.microsoft.com/microsoft-365/enterprise/cross-tenant-mailbox-migration).

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

### -OrganizationContact

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The OrganizationContact parameter specifies the email address that can be used to contact the external organization (for example, administrator@fourthcoffee.com).

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

### -PhotosEnabled

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The PhotosEnabled parameter specifies whether photos for users in the internal organization are returned over the organization relationship. Valid values are:

- $true: Photos for users in this organization are returned over the organization relationship.
- $false: Photos for users in this organization aren't returned over the organization relationship. This is the default value.

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

### -TargetApplicationUri

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The TargetApplicationUri parameter specifies the target Uniform Resource Identifier (URI) of the external organization. The TargetApplicationUri parameter is specified by Exchange when requesting a delegated token to retrieve free and busy information, for example, mail.contoso.com.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -TargetAutodiscoverEpr

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The TargetAutodiscoverEpr parameter specifies the Autodiscover URL of Exchange Web Services for the external organization, for example, `https://contoso.com/autodiscover/autodiscover.svc/wssecurity`. Exchange uses Autodiscover to automatically detect the correct Exchange server endpoint to use for external requests.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -TargetOwaURL

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The TargetOwaURL parameter specifies the Outlook on the web (formerly Outlook Web App) URL of the external organization that's defined in the organization relationship. It is used for Outlook on the web redirection in a cross-premise Exchange scenario. Configuring this attribute enables users in the organization to use their current Outlook on the web URL to access Outlook on the web in the external organization.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -TargetSharingEpr

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

The TargetSharingEpr parameter specifies the URL of the target Exchange Web Services for the external organization.

If you use this parameter, this URL is always used to reach the external Exchange server. TheURL that's specified by the TargetAutoDiscoverEpr parameter isn't used to locate the external Exchange server.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online, Exchange Online Protection

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
