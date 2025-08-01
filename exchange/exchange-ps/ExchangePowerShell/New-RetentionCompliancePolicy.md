---
applicable: Security & Compliance
author: chrisda
external help file: Microsoft.Exchange.TransportMailflow-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/new-retentioncompliancepolicy
schema: 2.0.0
title: New-RetentionCompliancePolicy
---

# New-RetentionCompliancePolicy

## SYNOPSIS
This cmdlet is available only in Security & Compliance PowerShell. For more information, see [Security & Compliance PowerShell](https://learn.microsoft.com/powershell/exchange/scc-powershell).

Use the New-RetentionCompliancePolicy cmdlet to create new retention policies and new retention label policies in the Microsoft Purview compliance portal. Creating a new policy also requires use of the New-RetentionComplianceRule cmdlet.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

### Default
```
New-RetentionCompliancePolicy [-Name] <String>
 [-Applications <MultiValuedProperty>]
 [-Comment <String>]
 [-Confirm]
 [-Enabled <Boolean>]
 [-ExchangeLocation <MultiValuedProperty>]
 [-ExchangeLocationException <MultiValuedProperty>]
 [-Force]
 [-IsSimulation]
 [-ModernGroupLocation <MultiValuedProperty>]
 [-ModernGroupLocationException <MultiValuedProperty>]
 [-OneDriveLocation <MultiValuedProperty>]
 [-OneDriveLocationException <MultiValuedProperty>]
 [-PolicyRBACScopes <MultiValuedProperty>]
 [-PolicyTemplateInfo <PswsHashtable>]
 [-PriorityCleanup]
 [-PublicFolderLocation <MultiValuedProperty>]
 [-RestrictiveRetention <Boolean>]
 [-RetainCloudAttachment <Boolean>]
 [-SharePointLocation <MultiValuedProperty>]
 [-SharePointLocationException <MultiValuedProperty>]
 [-SkipPriorityCleanupConfirmation]
 [-SkypeLocation <MultiValuedProperty>]
 [-SkypeLocationException <MultiValuedProperty>]
 [-WhatIf]
 [<CommonParameters>]
```

### TeamLocation
```
New-RetentionCompliancePolicy [-Name] <String>
 [-Comment <String>]
 [-Confirm]
 [-Enabled <Boolean>]
 [-Force]
 [-IsSimulation]
 [-PriorityCleanup]
 [-RestrictiveRetention <Boolean>]
 [-RetainCloudAttachment <Boolean>]
 [-SkipPriorityCleanupConfirmation]
 [-TeamsChannelLocation <MultiValuedProperty>]
 [-TeamsChannelLocationException <MultiValuedProperty>]
 [-TeamsChatLocation <MultiValuedProperty>]
 [-TeamsChatLocationException <MultiValuedProperty>]
 [-WhatIf]
 [<CommonParameters>]
```

### AdaptiveScopeLocation
```
New-RetentionCompliancePolicy [-Name] <String> -AdaptiveScopeLocation <MultiValuedProperty>
 [-Applications <MultiValuedProperty>]
 [-Comment <String>]
 [-Confirm]
 [-Enabled <Boolean>]
 [-Force]
 [-IsSimulation]
 [-PriorityCleanup]
 [-RestrictiveRetention <Boolean>]
 [-RetainCloudAttachment <Boolean>]
 [-SkipPriorityCleanupConfirmation]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Policies are not valid until a rule is added (for retention policies) or a label is added (for retention label policies). For more information, see [New-RetentionComplianceRule](/powershell/module/exchangepowershell/new-retentioncompliancerule). In addition, at least one location parameter must be defined to create a retention policy or retention label policy.

To use this cmdlet in Security & Compliance PowerShell, you need to be assigned permissions. For more information, see [Permissions in the Microsoft Purview compliance portal]/purview/microsoft-365-compliance-center-permissions).

## EXAMPLES

### Example 1
```powershell
New-RetentionCompliancePolicy -Name "Regulation 123 Compliance" -ExchangeLocation "Kitty Petersen", "Scott Nakamura" -SharePointLocation "https://contoso.sharepoint.com/sites/teams/finance"
```

This example creates a retention policy named "Regulation 123 Compliance" for the mailboxes of Kitty Petersen and Scott Nakamura, and the finance SharePoint site.

The next step is to use the New-RetentionComplianceRule cmdlet to add a rule to the retention policy.

### Example 2
```powershell
New-RetentionCompliancePolicy -Name "Marketing Department" -Enabled $true -SharePointLocation https://contoso.sharepoint.com -RetainCloudAttachment $true -Comment "Regulatory compliance for Marketing Dept."
```

This example creates a new auto-apply label policy targeted to cloud attachments named Marketing Department with the specified details.

The next step is to use the New-RetentionComplianceRule cmdlet to add a retention label to the retention label policy.

## PARAMETERS

### -Name

> Applicable: Security & Compliance

The Name parameter specifies the unique name of the retention policy. If the value contains spaces, enclose the value in quotation marks.

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

### -AdaptiveScopeLocation

> Applicable: Security & Compliance

The AdaptiveScopeLocation parameter specifies the adaptive scope location to include in the policy. You create adaptive scopes by using the New-AdaptiveScope cmdlet. You can use any value that uniquely identifies the adaptive scope. For example:

- Name
- Distinguished name (DN)
- GUID

```yaml
Type: MultiValuedProperty
Parameter Sets: AdaptiveScopeLocation
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Applications

> Applicable: Security & Compliance

The Applications parameter specifies the target when Microsoft 365 Groups are included in the policy (the ModernGroups parameter is set). Valid values are:

- `Group:Exchange` for the mailbox that's connected to the Microsoft 365 Group.
- `Group:SharePoint` for the SharePoint site that's connected to the Microsoft 365 Group.
- `"Group:Exchange,SharePoint"` for both the mailbox and the SharePoint site that are connected to the Microsoft 365 Group.
- blank (`$null`): This is the default value, and is functionally equivalent to the value `"Group:Exchange,SharePoint"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Default, AdaptiveScopeLocation
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Comment

> Applicable: Security & Compliance

The Comment parameter specifies an optional comment. If you specify a value that contains spaces, enclose the value in quotation marks ("), for example: "This is an admin note".

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

> Applicable: Security & Compliance

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

### -Enabled

> Applicable: Security & Compliance

The Enabled parameter specifies whether the policy is enabled or disabled. Valid values are:

- $true: The policy is enabled. This is the default value.
- $false: The policy is disabled.

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

### -ExchangeLocation

> Applicable: Security & Compliance

The ExchangeLocation parameter specifies the mailboxes to include in the policy. Valid values are:

- A mailbox
- A distribution group or mail-enabled security group (all mailboxes that are currently members of the group).
- The value All for all mailboxes. You can only use this value by itself.

To specify a mailbox or distribution group, you can use any value that uniquely identifies it. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

If no mailboxes are specified, then no mailboxes are placed on hold.

```yaml
Type: MultiValuedProperty
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExchangeLocationException

> Applicable: Security & Compliance

The ExchangeLocationException parameter specifies the mailboxes to exclude from the policy when you use the value All for the ExchangeLocation parameter. Valid values are:

- A mailbox
- A distribution group or mail-enabled security group

To specify a mailbox or distribution group, you can use any value that uniquely identifies it. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

> Applicable: Security & Compliance

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

### -IsSimulation

> Applicable: Security & Compliance

The IsSimulation switch specifies the policy is created in simulation mode. You don't need to specify a value with this switch.

For more information about simulation mode, see [Learn about simulation mode](https://learn.microsoft.com/purview/apply-retention-labels-automatically#learn-about-simulation-mo).

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

### -ModernGroupLocation

> Applicable: Security & Compliance

The ModernGroupLocation parameter specifies the Microsoft 365 Groups to include in the policy. Valid values are:

- A Microsoft 365 Group
- The value All for all Microsoft 365 Groups. You can only use this value by itself.

To identify the Microsoft 365 Group, you can use any value that uniquely identifies it. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModernGroupLocationException

> Applicable: Security & Compliance

The ModernGroupLocationException parameter specifies the Microsoft 365 Groups to exclude from the policy when you use the value All for the ModernGroupLocation parameter.

You can use any value that uniquely identifies the Microsoft 365 Group. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OneDriveLocation

> Applicable: Security & Compliance

The OneDriveLocation parameter specifies the OneDrive sites to include. You identify the site by its URL value, or you can use the value All to include all sites.

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OneDriveLocationException

> Applicable: Security & Compliance

This parameter specifies the OneDrive sites to exclude when you use the value All for the OneDriveLocation parameter. You identify the site by its URL value.

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyRBACScopes

> Applicable: Security & Compliance

**Note**: Admin units aren't currently supported, so this parameter isn't functional. The information presented here is for informational purposes when support for admin units is released.

The PolicyRBACScopes parameter specifies the administrative units to assign to the policy. A valid value is the Microsoft Entra ObjectID (GUID value) of the administrative unit. You can specify multiple values separated by commas.

Administrative units are available only in Microsoft Entra ID P1 or P2. You create and manage administrative units in Microsoft Graph PowerShell.

```yaml
Type: MultiValuedProperty
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyTemplateInfo

> Applicable: Security & Compliance

This parameter is reserved for internal Microsoft use.

```yaml
Type: PswsHashtable
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PriorityCleanup

> Applicable: Security & Compliance

The PriorityCleanup switch specifies whether to create a Priority cleanup policy. You don't need to specify a value with this switch.

Priority cleanup policies expedite the deletion of sensitive content by overriding any existing retention settings or eDiscovery holds. For more information, see [Priority Cleanup](https://learn.microsoft.com/purview/priority-cleanup).

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

### -PublicFolderLocation

> Applicable: Security & Compliance

The PublicFolderLocation parameter specifies that you want to include all public folders in the retention policy. You use the value All for this parameter.

```yaml
Type: MultiValuedProperty
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestrictiveRetention

> Applicable: Security & Compliance

The RestrictiveRetention parameter specifies whether Preservation Lock is enabled for the policy. Valid values are:

- $true: Preservation Lock is enabled for the policy. No one -- including an administrator -- can turn off the policy or make it less restrictive.
- $false: Preservation Lock isn't enabled for the policy. This is the default value.

After a policy has been locked, no one can turn off or disable it, or remove content from the policy. And it's not possible to modify or delete content that's subject to the policy during the retention period. The only ways that you can modify the retention policy are by adding content to it, or extending its duration. A locked policy can be increased or extended, but it can't be reduced, disabled, or turned off.

Therefore, before you lock a retention policy, it's critical that you understand your organization's compliance requirements, and that you don't lock a policy until you are certain that it's what you need.

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

### -RetainCloudAttachment

> Applicable: Security & Compliance

**Note**: This parameter is currently in Preview, is not available in all organizations, and is subject to change.

The RetainCloudAttachment parameter specifies that this is a cloud attachment policy. Valid values are:

- $true: The policy is a cloud attachment policy.
- $false: The policy is not a cloud attachment policy. This is the default value.

For the value $true, you can only use the following location parameters:

- SharePointLocation and SharePointLocationException
- OneDriveLocation and OneDriveLocationException
- ModernGroupLocation and ModernGroupLocationException

A tag that uses a cloud attachment policy to create a rule can be a record label or a regulatory label. You can't use a publishing tag for a cloud attachment policy to create a rule; only apply tags are supported.

The RetainCloudAttachment parameter is not available on the Set-RetentionCompliancePolicy cmdlet.

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

### -SharePointLocation

> Applicable: Security & Compliance

The SharePointLocation parameter specifies the SharePoint sites to include. You identify the site by its URL value, or you can use the value All to include all sites.

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

SharePoint sites can't be added to the policy until they have been indexed. If no sites are specified, then no sites are placed on hold.

```yaml
Type: MultiValuedProperty
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharePointLocationException

> Applicable: Security & Compliance

This parameter specifies the SharePoint sites to exclude when you use the value All for the SharePointLocation parameter. You identify the site by its URL value.

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipPriorityCleanupConfirmation

> Applicable: Security & Compliance

{{ Fill SkipPriorityCleanupConfirmation Description }}

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

### -SkypeLocation

> Applicable: Security & Compliance

The SkypeLocation parameter specifies the Skype for Business Online users to include in the policy.

You can use any value that uniquely identifies the user. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkypeLocationException

> Applicable: Security & Compliance

This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TeamsChannelLocation

> Applicable: Security & Compliance

The TeamsChannelLocation parameter specifies the Teams to include in the policy.

You can use any value that uniquely identifies the team. For example:

- Name
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: TeamLocation
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TeamsChannelLocationException

> Applicable: Security & Compliance

The TeamsChannelLocationException parameter specifies the Teams to exclude when you use the value All for the TeamsChannelLocation parameter. You can use any value that uniquely identifies the team. For example:

- Name
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: TeamLocation
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TeamsChatLocation

> Applicable: Security & Compliance

The TeamsChatLocation parameter specifies the Teams users to include in the policy.

You can use any value that uniquely identifies the user. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: TeamLocation
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TeamsChatLocationException

> Applicable: Security & Compliance

The TeamsChatLocationException parameter specifies the Teams users to exclude when you use the value All for the TeamsChatLocation parameter. You can use any value that uniquely identifies the user. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: TeamLocation
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

> Applicable: Security & Compliance

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

## OUTPUTS

## NOTES

## RELATED LINKS
