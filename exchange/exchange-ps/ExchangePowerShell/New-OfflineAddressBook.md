---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online
author: chrisda
external help file: Microsoft.Exchange.RolesAndAccess-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/new-offlineaddressbook
schema: 2.0.0
title: New-OfflineAddressBook
---

# New-OfflineAddressBook

## SYNOPSIS
This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

Use the New-OfflineAddressBook cmdlet to create offline address books (OABs).

In Exchange Online, this cmdlet is available only in the Address Lists role, and by default, the role isn't assigned to any role groups. To use this cmdlet, you need to add the Address Lists role to a role group (for example, to the Organization Management role group). For more information, see [Add a role to a role group](https://learn.microsoft.com/Exchange/permissions/role-groups#add-a-role-to-a-role-group).

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
New-OfflineAddressBook [-Name] <String> -AddressLists <AddressBookBaseIdParameter[]>
 [-Confirm]
 [-DiffRetentionPeriod <Unlimited>]
 [-DomainController <Fqdn>]
 [-GeneratingMailbox <MailboxIdParameter>]
 [-GlobalWebDistributionEnabled <Boolean>]
 [-IsDefault <Boolean>]
 [-PublicFolderDatabase <DatabaseIdParameter>]
 [-PublicFolderDistributionEnabled <Boolean>]
 [-Schedule <Schedule>]
 [-Server <ServerIdParameter>]
 [-ShadowMailboxDistributionEnabled <Boolean>]
 [-SkipPublicFolderInitialization]
 [-Versions <MultiValuedProperty>]
 [-VirtualDirectories <VirtualDirectoryIdParameter[]>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
$a = Get-AddressList | Where {$_.Name -Like "*AgencyB*"}

New-OfflineAddressBook -Name "OAB_AgencyB" -Server myserver.contoso.com -AddressLists $a -Schedule "Mon.01:00-Mon.02:00, Wed.01:00-Wed.02:00"
```

In Exchange Server 2010 and 2013, this example uses two commands to create the OAB named OAB\_AgencyB that includes all address lists in which AgencyB is part of the name. By using the settings shown, an OAB is generated by myserver.contoso.com on Mondays and Wednesdays from 01:00 (1 A.M.) to 02:00 (2 A.M.). This example command also creates the default OAB for the organization.

### Example 2
```powershell
New-OfflineAddressBook -Name "Contoso Executives OAB" -AddressLists "Default Global Address List","Contoso Executives Address List" -GlobalWebDistributionEnabled $true
```

This example creates a new OAB named Contoso Executives OAB with the following properties:

- Address lists included in the OAB: Default Global Address List and Contoso Executives Address List
- All OAB virtual directories in the organization can accept requests to download the OAB.

The organization mailbox that's responsible for generating the OAB is SystemMailbox{bb558c35-97f1-4cb9-8ff7-d53741dc928c} (we didn't use the GeneratingMailbox parameter to specify a different organization mailbox).

The OAB isn't used by mailboxes and mailbox databases that don't have an OAB specified (we didn't use the IsDefault parameter with the value $true).

### Example 3
```powershell
New-OfflineAddressBook -Name "New OAB" -AddressLists "\Default Global Address List" -Server SERVER01 -VirtualDirectories "SERVER01\OAB (Default Web Site)"
```

In Exchange Server 2010, this example creates the OAB New OAB that uses Web-based distribution for Microsoft Office Outlook 2007 or later clients on SERVER01 by using the default virtual directory.

### Example 4
```powershell
New-OfflineAddressBook -Name "Legacy OAB" -AddressLists "\Default Global Address List" -Server SERVER01 -PublicFolderDatabase "PFDatabase" -PublicFolderDistributionEnabled $true -Versions Version1,Version2
```

In Exchange Server 2010, this example creates the OAB Legacy OAB that uses public folder distribution for Outlook 2003 Service Pack 1 (SP1) and Outlook 98 Service Pack 2 (SP2) clients on SERVER01.

If you configure OABs to use public folder distribution, but your organization doesn't have any public folder infrastructure, an error will be returned. For more information, see [Managing Public Folders](https://learn.microsoft.com/previous-versions/office/exchange-server-2010/bb124411(v=exchg.141)).

## PARAMETERS

### -Name

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Name parameter specifies the unique name of the OAB. The maximum length is 64 characters. If the value contains spaces, enclose the value in quotation marks.

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

### -AddressLists

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The AddressLists parameter specifies the address lists or global address lists that are included in the OAB. You can use any value that uniquely identifies the address list. For example:

- Name
- Distinguished name (DN)
- GUID

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

You can find the identify values of address lists and global address lists by using the Get-AddressList and Get-GlobalAddressList cmdlets.

```yaml
Type: AddressBookBaseIdParameter[]
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

### -DiffRetentionPeriod

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The DiffRetentionPeriod parameter specifies the number of days that the OAB difference files are stored on the server. Valid values are integers from 7 to 1825, or the value unlimited. The default value is 30.

```yaml
Type: Unlimited
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

### -GeneratingMailbox

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This parameter is available only in on-premises Exchange.

The GeneratingMailbox parameter specifies the arbitration mailbox where the OAB is generated. Specifically, the arbitration mailbox must contain the OrganizationCapabilityOABGen value for the PersistedCapability property. An arbitration mailbox with this capability is also known as an organization mailbox. You can use any value that uniquely identifies the mailbox. For example:

- Name
- Alias
- Distinguished name (DN)
- Canonical DN
- Domain\\Username
- Email address
- GUID
- LegacyExchangeDN
- SamAccountName
- User ID or user principal name (UPN)

The default value for this parameter is the organization mailbox named SystemMailbox{bb558c35-97f1-4cb9-8ff7-d53741dc928c}.

A single organization mailbox can generate multiple OABs (you can use the same value for this parameter in the settings of multiple OABs), but in Exchange 2013 CU5 or later, an OAB can only be generated by a single organization mailbox (this parameter doesn't accept multiple values). To have a read only copy of the OAB (also known as a shadow copy) available in other organization mailboxes, use the ShadowMailboxDistributionEnabled parameter.

```yaml
Type: MailboxIdParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalWebDistributionEnabled

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This parameter is available only in on-premises Exchange.

The GlobalWebDistributionEnabled parameter specifies whether all OAB virtual directories in the organization can accept requests to download the OAB. These locations are advertised by the Autodiscover service. Valid values are:

- $true: Any OAB virtual directory in the organization can accept requests to download the OAB. You can't use this setting with the VirtualDirectories parameter.
- $false: Only the OAB virtual directories that are specified by the VirtualDirectories parameter accept requests to download the OAB. This is the default value.

In Exchange 2013 CU7 or later, we recommend that you use the value $true for this parameter. The Client Access services on any Mailbox server can proxy incoming OAB download requests to the correct location.

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

### -IsDefault

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The IsDefault parameter specifies whether the OAB is used by all mailboxes and mailbox databases that don't have an OAB specified. Valid values are:

- $true: The OAB is the default OAB.
- $false: The OAB is isn't the default OAB. This is the default value.

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

### -PublicFolderDatabase

> Applicable: Exchange Server 2010

This parameter is available only in Exchange Server 2010.

The PublicFolderDatabase parameter specifies the public folder database that's used to distribute the OAB. You can use any value that uniquely identifies the database. For example:

- Name
- Distinguished name (DN)
- GUID

To use this parameter, the PublicFolderDistributionEnabled parameter must be set to $true.

```yaml
Type: DatabaseIdParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicFolderDistributionEnabled

> Applicable: Exchange Server 2010

This parameter is available only in Exchange Server 2010.

The PublicFolderDistributionEnabled parameter specifies whether the OAB is distributed via public folders. If the value of the PublicFolderDistributionEnabled parameter is $true, the OAB is distributed via public folders.

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

### -Schedule

> Applicable: Exchange Server 2010

This parameter is available only in Exchange Server 2010.

The Schedule parameter specifies the interval for generating the OAB in Exchange 2010 or earlier.

The syntax for this parameter is: `StartDay.Hour:Minute [AM | PM]-EndDay.Hour:Minute [AM | PM]`.

You can use the following values for days:

- Full name of the day.
- Abbreviated name of the day.
- Integer from 0 through 6, where 0 = Sunday.

You can enter the time in 24 hour format and omit the AM/PM value. If you enter the time in 12 time hour format, include a space between the time and the AM/PM value.

You can mix and match date/time formats.

The start time and end time must be at least 15 minutes apart. Minutes are rounded down to 0, 15, 30, or 45.

Here are some examples:

- "Sun.11:30 PM-Mon.1:30 AM"
- "6.22:00-6.22:15" (Run from Saturday at 10:00 PM until Saturday at 10:15 PM.)
- "Sun.1:15 AM-Monday.23:00"

```yaml
Type: Schedule
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server

> Applicable: Exchange Server 2010

This parameter is available only in Exchange Server 2010.

The Server parameter specifies the Exchange server where you want to run this command. You can use any value that uniquely identifies the server. For example:

- Name
- FQDN
- Distinguished name (DN)
- ExchangeLegacyDN

If you don't use this parameter, the command is run on the local server.

```yaml
Type: ServerIdParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -ShadowMailboxDistributionEnabled

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This parameter is available only in on-premises Exchange.

The ShadowMailboxDistributionEnabled parameter specifies whether a read only copy of the OAB (also known as a shadow copy) is distributed to all other OAB generation mailboxes (also known as organization mailboxes). This allows additional Mailbox servers to be endpoints for requests to download the OAB, which can help prevent users from downloading the OAB across slow WAN links. Valid values are:

- $true: The OAB is distributed to all other organization mailboxes.
- $false: The OAB is isn't distributed to other organization mailboxes. This is the default value.

The value of this parameter is only meaningful if you have multiple organization mailboxes, and is only beneficial in Exchange organizations that have multiple Active Directory sites.

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

### -SkipPublicFolderInitialization

> Applicable: Exchange Server 2010

This parameter is available only in Exchange Server 2010.

The SkipPublicFolderInitialization switch specifies whether to skip the immediate creation of the OAB public folders if you're creating an OAB that uses public folder distribution. You don't need to specify a value with this switch.

The OAB isn't available for download until the next site folder maintenance cycle has completed. Omitting this switch might cause the task to pause while it contacts the responsible public folder server to create the necessary public folders. If the server is presently unreachable, or is otherwise costly to contact, the pause could be significant.

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

### -Versions

> Applicable: Exchange Server 2010

This parameter is available only in Exchange Server 2010.

The Versions parameter specifies the OAB versions that are generated for client download. Valid values are:

- Version2 (requires public folder distribution)
- Version3 (requires public folder distribution)
- Version4 (default value)

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

### -VirtualDirectories

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This parameter is available only in on-premises Exchange.

The VirtualDirectories parameter specifies the OAB virtual directories that accept requests to download the OAB. These locations are advertised in the Autodiscover service.

You can use any value that uniquely identifies the virtual directory. For example:

- Name or Server\\Name
- Distinguished name (DN)
- GUID

The Name value uses the syntax `"VirtualDirectoryName (WebsiteName)"` from the properties of the virtual directory. You can specify the wildcard character (\*) instead of the default website by using the syntax `VirtualDirectoryName*`.

The default value of this parameter is the Client Access services (frontend) and backend OAB virtual directories on the Mailbox server that holds the OAB generation mailbox (the GeneratingMailbox parameter or SystemMailbox{bb558c35-97f1-4cb9-8ff7-d53741dc928c}). For example, Mailbox01\\OAB (Default Web Site),Mailbox01\\OAB (Exchange Back End.

To use this parameter, the value of the GlobalWebDistributionEnabled parameter must be $false.

In Exchange 2013 CU7 or later, we recommend that you set the GlobalWebDistributionEnabled parameter to $true, because the Client Access services on any Mailbox server can proxy incoming OAB download requests to the correct location.

```yaml
Type: VirtualDirectoryIdParameter[]
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
