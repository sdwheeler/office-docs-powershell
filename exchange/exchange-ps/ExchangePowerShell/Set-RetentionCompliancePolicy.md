---
applicable: Security & Compliance
author: chrisda
external help file: Microsoft.Exchange.TransportMailflow-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/set-retentioncompliancepolicy
schema: 2.0.0
title: Set-RetentionCompliancePolicy
---

# Set-RetentionCompliancePolicy

## SYNOPSIS
This cmdlet is available only in Security & Compliance PowerShell. For more information, see [Security & Compliance PowerShell](https://learn.microsoft.com/powershell/exchange/scc-powershell).

Use the Set-RetentionCompliancePolicy cmdlet to modify existing retention policies in the Microsoft Purview compliance portal.

**Note**: Running this cmdlet causes a full synchronization across your organization, which is a significant operation. If you need to update multiple policies, wait until the policy distribution is successful before running the cmdlet again for the next policy. For information about the distribution status, see [Get-RetentionCompliancePolicy](https://learn.microsoft.com/powershell/module/exchangepowershell/get-retentioncompliancepolicy).

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

### Identity
```
Set-RetentionCompliancePolicy [-Identity] <PolicyIdParameter>
 [-AddExchangeLocation <MultiValuedProperty>]
 [-AddExchangeLocationException <MultiValuedProperty>]
 [-AddModernGroupLocation <MultiValuedProperty>]
 [-AddModernGroupLocationException <MultiValuedProperty>]
 [-AddOneDriveLocation <MultiValuedProperty>]
 [-AddOneDriveLocationException <MultiValuedProperty>]
 [-AddPublicFolderLocation <MultiValuedProperty>]
 [-AddSharePointLocation <MultiValuedProperty>]
 [-AddSharePointLocationException <MultiValuedProperty>]
 [-AddSkypeLocation <MultiValuedProperty>]
 [-AddSkypeLocationException <MultiValuedProperty>]
 [-Applications <MultiValuedProperty>]
 [-Comment <String>]
 [-Confirm]
 [-DeletedResources <String>]
 [-Enabled <Boolean>]
 [-EnforceSimulationPolicy <Boolean>]
 [-Force]
 [-PolicyTemplateInfo <PswsHashtable>]
 [-PolicyRBACScopes <MultiValuedProperty>]
 [-PriorityCleanup]
 [-RemoveExchangeLocation <MultiValuedProperty>]
 [-RemoveExchangeLocationException <MultiValuedProperty>]
 [-RemoveModernGroupLocation <MultiValuedProperty>]
 [-RemoveModernGroupLocationException <MultiValuedProperty>]
 [-RemoveOneDriveLocation <MultiValuedProperty>]
 [-RemoveOneDriveLocationException <MultiValuedProperty>]
 [-RemovePublicFolderLocation <MultiValuedProperty>]
 [-RemoveSharePointLocation <MultiValuedProperty>]
 [-RemoveSharePointLocationException <MultiValuedProperty>]
 [-RemoveSkypeLocation <MultiValuedProperty>]
 [-RemoveSkypeLocationException <MultiValuedProperty>]
 [-RestrictiveRetention <Boolean>]
 [-StartSimulation <Boolean>]
 [-WhatIf]
 [<CommonParameters>]
```

### AdaptiveScopeLocation
```
Set-RetentionCompliancePolicy [-Identity] <PolicyIdParameter> [-AddAdaptiveScopeLocation <MultiValuedProperty>]
 [-Applications <MultiValuedProperty>]
 [-Comment <String>]
 [-Confirm]
 [-DeletedResources <String>]
 [-Enabled <Boolean>]
 [-EnforceSimulationPolicy <Boolean>]
 [-Force]
 [-PriorityCleanup]
 [-RemoveAdaptiveScopeLocation <MultiValuedProperty>]
 [-StartSimulation <Boolean>]
 [-WhatIf]
 [<CommonParameters>]
```

### RetryDistribution
```
Set-RetentionCompliancePolicy [-Identity] <PolicyIdParameter> [-RetryDistribution]
 [-Confirm]
 [-DeletedResources <String>]
 [-EnforceSimulationPolicy <Boolean>]
 [-PriorityCleanup]
 [-StartSimulation <Boolean>]
 [-WhatIf]
 [<CommonParameters>]
```

### TeamLocation
```
Set-RetentionCompliancePolicy [-Identity] <PolicyIdParameter>
 [-AddTeamsChannelLocation <MultiValuedProperty>]
 [-AddTeamsChannelLocationException <MultiValuedProperty>]
 [-AddTeamsChatLocation <MultiValuedProperty>]
 [-AddTeamsChatLocationException <MultiValuedProperty>]
 [-Comment <String>]
 [-Confirm]
 [-DeletedResources <String>]
 [-Enabled <Boolean>]
 [-EnforceSimulationPolicy <Boolean>]
 [-Force]
 [-PriorityCleanup]
 [-RemoveTeamsChannelLocation <MultiValuedProperty>]
 [-RemoveTeamsChannelLocationException <MultiValuedProperty>]
 [-RemoveTeamsChatLocation <MultiValuedProperty>]
 [-RemoveTeamsChatLocationException <MultiValuedProperty>]
 [-StartSimulation <Boolean>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
To use this cmdlet in Security & Compliance PowerShell, you need to be assigned permissions. For more information, see [Permissions in the Microsoft Purview compliance portal](https://learn.microsoft.com/purview/microsoft-365-compliance-center-permissions).

**Note**: Don't use a piped Foreach-Object command when adding or removing scope locations: `"Value1","Value2",..."ValueN" | Foreach-Object {Set-RetentionCompliancePolicy -Identity "Regulation 123 Compliance" -RemoveExchangeLocation $_}`.

## EXAMPLES

### Example 1
```powershell
Set-RetentionCompliancePolicy -Identity "Regulation 123 Compliance" -AddExchangeLocation "Kitty Petersen" -AddSharePointLocation "https://contoso.sharepoint.com/sites/teams/finance" -RemovePublicFolderLocation All -Comment "Added new counsel, 9/9/14"
```

This example makes the following changes to the existing retention policy named "Regulation 123 Compliance":

- Adds the mailbox for the user named Kitty Petersen.
- Adds the SharePoint site `https://contoso.sharepoint.com/sites/teams/finance`.
- Removes public folders.
- Updates the comment.

### Example 2
```powershell
$stringJson = @"
[{
     'EmailAddress': 'USSales@contoso.onmicrosoft.com',
     'SiteId': '9b2a8116-b9ec-4e2c-bf31-7eaa83697c4b'
}]
"@

Set-RetentionCompliancePolicy -Identity "Sales Policy" -RemoveModernGroupLocation "USSales@contoso.onmicrosoft.com" -DeletedResources $stringJson
```

The example removes the specified deleted Microsoft 365 Group and site from the specified policy. You identify the deleted resources using the Microsoft 365 Group email address and the related site ID.

**IMPORTANT**: Before you run this command, make sure you read the Caution information for the [DeletedResources parameter](#-deletedresources) about duplicate SMTP addresses.

### Example 3
```powershell
$stringJson = @"
[{
     'EmailAddress': 'USSales@contoso.onmicrosoft.com',
     'SiteId': '8b2a8345-b9ec-3b6a-bf31-6eaa83697c4b'
}]
"@

Set-RetentionCompliancePolicy -Identity "Tenant Level Policy" -AddModernGroupLocationException "USSales@contoso.onmicrosoft.com" -DeletedResources $stringJson
```

The example excludes the specified deleted Microsoft 365 Group and site from the specified tenant level policy. You identify the deleted resources using the Microsoft 365 Group email address and the related site ID.

**IMPORTANT**: Before you run this command, make sure you read the Caution information for the [DeletedResources parameter](#-deletedresources) about duplicate SMTP addresses.

### Example 4
```powershell
$stringJson = @"
[{
     'EmailAddress': 'USSales2@contoso.onmicrosoft.com',
     'SiteId': '9b2a8116-b9ec-4e2c-bf31-7eaa83697c4b'
 },
{
     'EmailAddress': 'USSales2@contoso.onmicrosoft.com',
     'SiteId': '4afb7116-b9ec-4b2c-bf31-4abb83697c4b'
}]
"@

Set-RetentionCompliancePolicy -Identity "Sales Policy" -RemoveModernGroupLocation "USSales2@contoso.onmicrosoft.com" -DeletedResources $stringJson
```

This example is similar to Example 2, except multiple deleted resources are specified.

**IMPORTANT**: Before you run this command, make sure you read the Caution information for the [DeletedResources parameter](#-deletedresources) about duplicate SMTP addresses.

### Example 5
```powershell
$stringJson = @"
[{
     'EmailAddress': 'SalesUser@contoso.onmicrosoft.com'
}]
"@

Set-RetentionCompliancePolicy -Identity "Teams Chat Retention Policy" -AddTeamsChatLocationException "SalesUser@contoso.onmicrosoft.com" -DeletedResources $stringJson
```

This example excludes the specified soft-deleted mailbox or mail user from the mentioned Teams Retention Policy. You can identify the deleted resources using the mailbox or mail user's email address.

**IMPORTANT**: Before you run this command, make sure you read the Caution information for the [DeletedResources parameter](#-deletedresources) about duplicate SMTP addresses.

### Example 6
```powershell
$stringJson = @"
[{
     'EmailAddress': 'SalesUser1@contoso.onmicrosoft.com'
},
{
     'EmailAddress': 'SalesUser2@contoso.onmicrosoft.com'
}]
"@

Set-RetentionCompliancePolicy -Identity "Teams Chat Retention Policy" -AddTeamsChatLocationException "SalesUser1@contoso.onmicrosoft.com", "SalesUser2@contoso.onmicrosoft.com" -DeletedResources $stringJson
```

This example is similar to Example 5, except multiple deleted resources are specified.

**IMPORTANT**: Before you run this command, make sure you read the Caution information for the [DeletedResources parameter](#-deletedresources) about duplicate SMTP addresses.

Policy exclusions must remain within the supported limits for retention policies: [Limits for Microsoft 365 retention policies and retention label policies](https://learn.microsoft.com/purview/retention-limits#maximum-number-of-items-per-policy)

## PARAMETERS

### -Identity

> Applicable: Security & Compliance

The Identity parameter specifies the retention policy that you want to modify. You can use any value that uniquely identifies the policy. For example:

- Name
- Distinguished name (DN)
- GUID

```yaml
Type: PolicyIdParameter
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -RetryDistribution

> Applicable: Security & Compliance

The RetryDistribution switch specifies whether to redistribute the policy to all Exchange Online and SharePoint locations. You don't need to specify a value with this switch.

Locations whose initial distributions succeeded aren't included in the retry. Policy distribution errors are reported when you use this switch.

```yaml
Type: SwitchParameter
Parameter Sets: RetryDistribution
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddAdaptiveScopeLocation

> Applicable: Security & Compliance

The AddAdaptiveScopeLocation parameter specifies the adaptive scope location to add to the policy. You create adaptive scopes by using the New-AdaptiveScope cmdlet. You can use any value that uniquely identifies the adaptive scope. For example:

- Name
- Distinguished name (DN)
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: AdaptiveScopeLocation
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddExchangeLocation

> Applicable: Security & Compliance

The AddExchangeLocation parameter specifies the mailboxes to add to the list of included mailboxes when you aren't using the value All for the ExchangeLocation parameter. Valid values are:

- A mailbox
- A distribution group or mail-enabled security group (all mailboxes that are currently members of the group).

To specify a mailbox or distribution group, you can use any value that uniquely identifies it. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddExchangeLocationException

> Applicable: Security & Compliance

This parameter specifies the mailboxes to add to the list of excluded mailboxes when you use the value All for the ExchangeLocation parameter. Valid values are:

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
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddModernGroupLocation

> Applicable: Security & Compliance

The AddModernGroupLocation parameter specifies the Microsoft 365 Groups to add to the list of included Microsoft 365 Groups when you aren't using the value All for the ModernGroupLocation parameter.

You can use any value that uniquely identifies the Microsoft 365 Group. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddModernGroupLocationException

> Applicable: Security & Compliance

The AddModernGroupLocationException parameter specifies the Microsoft 365 Groups to add to the list of excluded Microsoft 365 Groups when you're using the value All for the ModernGroupLocation parameter.

You can use any value that uniquely identifies the Microsoft 365 Group. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddOneDriveLocation

> Applicable: Security & Compliance

The AddOneDriveLocation parameter specifies the OneDrive sites to add to the list of included sites when you aren't using the value All for the OneDriveLocation parameter. You identify the site by its URL value.

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddOneDriveLocationException

> Applicable: Security & Compliance

This parameter specifies the OneDrive sites to add to the list of excluded sites when you use the value All for the OneDriveLocation parameter. You identify the site by its URL value.

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddPublicFolderLocation

> Applicable: Security & Compliance

The AddPublicFolderLocation parameter specifies that you want to add all public folders to the retention policy. You use the value All for this parameter.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddSharePointLocation

> Applicable: Security & Compliance

The AddSharePointLocation parameter specifies the SharePoint sites to add to the list of included sites when you aren't using the value All for the SharePointLocation parameter. You identify the site by its URL value.

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

SharePoint sites can't be added to the policy until they have been indexed.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddSharePointLocationException

> Applicable: Security & Compliance

This parameter specifies the SharePoint sites to add to the list of excluded sites when you use the value All for the SharePointLocation parameter. You identify the site by its URL value.

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddSkypeLocation

> Applicable: Security & Compliance

The AddSkypeLocation parameter specifies the Skype for Business Online users to add from the list of included Skype for Business Online users.

You can use any value that uniquely identifies the user. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddSkypeLocationException

> Applicable: Security & Compliance

This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddTeamsChannelLocation

> Applicable: Security & Compliance

The AddTeamsChannelLocation parameter specifies the Teams to add to the policy.

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

### -AddTeamsChannelLocationException

> Applicable: Security & Compliance

The AddTeamsChannelLocationException parameter specifies the Teams to add to the exclusion list when you use the value All for the TeamsChannelLocation parameter. You can use any value that uniquely identifies the team. For example:

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

### -AddTeamsChatLocation

> Applicable: Security & Compliance

The AddTeamsChatLocation parameter specifies the Teams users to add to the policy.

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

### -AddTeamsChatLocationException

> Applicable: Security & Compliance

The AddTeamsChatLocationException parameter specifies the Teams users to add to the exclusion list when you use the value All for the TeamsChatLocation parameter. You can use any value that uniquely identifies the user. For example:

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

### -Applications

> Applicable: Security & Compliance

The Applications parameter specifies the target when Microsoft 365 Groups are included in the policy (the ModernGroups parameter is set). Valid values are:

- `Group:Exchange` for the mailbox that's connected to the Microsoft 365 Group.
- `Group:SharePoint` for the SharePoint site that's connected to the Microsoft 365 Group.
- `"Group:Exchange,SharePoint"` for both the mailbox and the SharePoint site that are connected to the Microsoft 365 Group.
- blank (`$null`): This is the default value, and is functionally equivalent to the value `"Group:Exchange,SharePoint"`. To return to the default value of both the mailbox and SharePoint site for the selected Microsoft 365 groups, specify `"Group:Exchange,SharePoint"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
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
Parameter Sets: Identity, TeamLocation
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

### -DeletedResources

> Applicable: Security & Compliance

The DeletedResources parameter specifies the deleted Microsoft 365 Group, mailbox, or mail user to be removed or added as an exclusion to the respective location list. Use this parameter with the AddModernGroupLocationException and RemoveModernGroupLocation parameters for deleted Microsoft 365 Groups, or with the AddTeamsChatLocationException parameter for deleted mailboxes or mail users.

A valid value is a JSON string. Refer to the Examples section for syntax and usage examples of this parameter.

**CAUTION**: When you use a SMTP address with this parameter, be aware that the same address might also be in use for other mailboxes or mail users. To check for additional mailboxes or mail users with the same SMTP address, use the following command and replace `user@contoso.com` with the SMTP address to check: `Get-Recipient -IncludeSoftDeletedRecipients user@contoso.com | Select-Object DisplayName, EmailAddresses, Description, Alias, RecipientTypeDetails, WhenSoftDeleted`

To prevent active mailboxes or mail users with the same SMTP address from being excluded, put the mailbox on [Litigation Hold](https://learn.microsoft.com/purview/ediscovery-create-a-litigation-hold) before you run the command with the DeletedResources parameter.

For more information about the deleted Microsoft 365 Group scenario, see [Learn more about modern group deletion under retention hold](https://learn.microsoft.com/purview/retention-settings#what-happens-if-a-microsoft-365-group-is-deleted-after-a-policy-is-applied).

For more information about the inactive mailbox scenario, see [Learn about inactive mailboxes](https://learn.microsoft.com/purview/inactive-mailboxes-in-office-365).

```yaml
Type: String
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled

> Applicable: Security & Compliance

The Enabled parameter specifies whether the policy is enabled. Valid values are:

- $true: The policy is enabled. This is the default value.
- $false: The policy is disabled.

```yaml
Type: Boolean
Parameter Sets: Identity, TeamLocation
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnforceSimulationPolicy

> Applicable: Security & Compliance

The EnforceSimulationPolicy parameter specifies whether to enforce a simulation policy as an active policy. Valid values are:

- $true: Enforce the simulation policy as an active policy.
- $false: Don't enforce the simulation policy as an active policy. This is the default value.

For more information about simulation mode, see [Learn about simulation mode](https://learn.microsoft.com/purview/apply-retention-labels-automatically#learn-about-simulation-mo).

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

> Applicable: Security & Compliance

The Force switch hides warning or confirmation messages. You don't need to specify a value with this switch.

You can use this switch to run tasks programmatically where prompting for administrative input is inappropriate.

```yaml
Type: SwitchParameter
Parameter Sets: Identity, TeamLocation
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
Parameter Sets: Identity
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
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PriorityCleanup

> Applicable: Security & Compliance

The PriorityCleanup switch specifies whether to update a Priority cleanup policy. You don't need to specify a value with this switch.

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

### -RemoveAdaptiveScopeLocation

> Applicable: Security & Compliance

The RemoveAdaptiveScopeLocation parameter specifies the adaptive scope location to remove from the policy. You create adaptive scopes by using the New-AdaptiveScope cmdlet. You can use any value that uniquely identifies the adaptive scope. For example:

- Name
- Distinguished name (DN)
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: AdaptiveScopeLocation
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveExchangeLocation

> Applicable: Security & Compliance

The RemoveExchangeLocation parameter specifies the mailboxes to remove from the list of included mailboxes when you aren't using the value All for the ExchangeLocation parameter.

You can use any value that uniquely identifies the mailbox. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveExchangeLocationException

> Applicable: Security & Compliance

The RemoveExchangeLocationException parameter specifies the mailboxes to remove from the list of excluded mailboxes when you use the value All for the ExchangeLocation parameter.

You can use any value that uniquely identifies the mailbox. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveModernGroupLocation

> Applicable: Security & Compliance

The RemoveModernGroupLocation parameter specifies the Microsoft 365 Groups to remove from the list of included groups when you aren't using the value All for the ModernGroupLocation parameter.

You can use any value that uniquely identifies the Microsoft 365 Group. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveModernGroupLocationException

> Applicable: Security & Compliance

The RemoveModernGroupLocationException parameter specifies the Microsoft 365 Groups to remove from the list of excluded groups when you're using the value All for the ModernGroupLocation parameter.

You can use any value that uniquely identifies the Microsoft 365 Group. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveOneDriveLocation

> Applicable: Security & Compliance

The RemoveOneDriveLocation parameter specifies the OneDrive sites to remove from the list of included sites when you aren't using the value All for the OneDriveLocation parameter. You identify the site by its URL value.

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveOneDriveLocationException

> Applicable: Security & Compliance

This parameter specifies the OneDrive sites to remove from the list of excluded sites when you use the value All for the OneDriveLocation parameter. You identify the site by its URL value.

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemovePublicFolderLocation

> Applicable: Security & Compliance

The RemovePublicFolderLocation parameter specifies that you want to remove all public folders from the retention policy. You use the value All for this parameter.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveSharePointLocation

> Applicable: Security & Compliance

The RemoveSharePointLocation parameter specifies the SharePoint sites to remove from the list of included sites when you aren't using the value All for the SharePointLocation parameter. You identify the site by its URL value.

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveSharePointLocationException

> Applicable: Security & Compliance

This parameter specifies the SharePoint sites to remove from the list of excluded sites when you use the value All for the SharePointLocation parameter. You identify the site by its URL value.

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveSkypeLocation

> Applicable: Security & Compliance

The RemoveSkypeLocation parameter specifies the Skype for Business Online users to remove from the list of included Skype for Business Online users.

You can use any value that uniquely identifies the user. For example:

- Name
- Distinguished name (DN)
- Email address
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveSkypeLocationException

> Applicable: Security & Compliance

This parameter is reserved for internal Microsoft use.

```yaml
Type: MultiValuedProperty
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestrictiveRetention

> Applicable: Security & Compliance

The RestrictiveRetention parameter specifies whether Preservation Lock is enabled for a retention policy or retention label policy. Valid values are:

- $true: Preservation Lock is enabled for the policy. No one (including an administrator) can turn off the policy or make it less restrictive.
- $false: Preservation Lock isn't enabled for the policy. This is the default value.

After a policy has been locked, no one can turn off or disable it, or remove content from the policy. And it's not possible to modify or delete content that's subject to the policy during the retention period. The only way that you can modify the retention policy are by adding content to it, or extending its duration. A locked policy can be increased or extended, but it can't be reduced, disabled, or turned off.

Therefore, before you lock a policy for retention, it's critical that you understand your organization's compliance requirements, and that you don't lock a policy until you are certain that it's what you need.

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveTeamsChannelLocation

> Applicable: Security & Compliance

The RemoveTeamsChannelLocation parameter specifies the Teams to remove from the policy.

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

### -RemoveTeamsChannelLocationException

> Applicable: Security & Compliance

The RemoveTeamsChannelLocationException parameter specifies the Teams to remove from the exclusion list when you use the value All for the TeamsChannelLocation parameter. You can use any value that uniquely identifies the team. For example:

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

### -RemoveTeamsChatLocation

> Applicable: Security & Compliance

The RemoveTeamsChatLocation parameter specifies the Teams users to remove from the policy.

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

### -RemoveTeamsChatLocationException

> Applicable: Security & Compliance

The RemoveTeamsChatLocationException parameter specifies the Teams users to remove from the exclusion list when you use the value All for the TeamsChatLocation parameter. You can use any value that uniquely identifies the user. For example:

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

### -StartSimulation

> Applicable: Security & Compliance

The StartSimulation parameter specifies whether to start the simulation for a policy that was created in simulation mode. Valid values are:

- $true: Start the simulation.
- $false: Don't start the simulation. This is the default value.

For more information about simulation mode, see [Learn about simulation mode](https://learn.microsoft.com/purview/apply-retention-labels-automatically#learn-about-simulation-mo).

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
