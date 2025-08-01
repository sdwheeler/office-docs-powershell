---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online
author: chrisda
external help file: Microsoft.Exchange.RolesAndAccess-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/set-addressbookpolicy
schema: 2.0.0
title: Set-AddressBookPolicy
---

# Set-AddressBookPolicy

## SYNOPSIS
This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

Use the Set-AddressBookPolicy cmdlet to change the settings of an address book policy.

In Exchange Online, this cmdlet is available only in the Address Lists role, and by default, the role isn't assigned to any role groups. To use this cmdlet, you need to add the Address Lists role to a role group (for example, to the Organization Management role group). For more information, see [Add a role to a role group](https://learn.microsoft.com/Exchange/permissions/role-groups#add-a-role-to-a-role-group).

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Set-AddressBookPolicy [-Identity] <MailboxPolicyIdParameter>
 [-AddressLists <AddressListIdParameter[]>]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-GlobalAddressList <GlobalAddressListIdParameter>]
 [-Name <String>]
 [-OfflineAddressBook <OfflineAddressBookIdParameter>]
 [-RoomList <AddressListIdParameter>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Set-AddressBookPolicy -Identity "All Fabrikam ABP" -OfflineAddressBook \Fabrikam-OAB-2 -GlobalAddressList "\All Fabrikam GAL"
```

This example changes the OAB that the address book policy All Fabrikam ABP uses to Fabrikam-OAB-2.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Identity parameter specifies the identity of the address book policy that you want to modify.

```yaml
Type: MailboxPolicyIdParameter
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -AddressLists

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The AddressLists parameter specifies the address lists that will be used by mailbox users who are assigned this address book policy. This parameter accepts multiple values, which should be separated by a comma.

```yaml
Type: AddressListIdParameter[]
Parameter Sets: (All)
Aliases:

Required: False
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

### -GlobalAddressList

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The GlobalAddressList parameter specifies the identity of the global address list (GAL) that will be used by mailbox users who are assigned this address book policy. You can specify only one GAL for each address book policy.

```yaml
Type: GlobalAddressListIdParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Name parameter specifies the name that you want this address book policy to be called. Use this parameter to change the name of the address book policy.

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

### -OfflineAddressBook

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The OfflineAddressBook parameter specifies the identity of the offline address book (OAB) that will be used by mailbox users who are assigned this address book policy. You can specify only one OAB for each address book policy.

```yaml
Type: OfflineAddressBookIdParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoomList

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The RoomList parameter specifies an address list that used for location experiences for mailbox users who have this address book policy assigned to them.

- When using location experiences (for example, Room Finder or selecting a conference room when scheduling a meeting), users see only resources that match the [RecipientFilter](https://learn.microsoft.com/powershell/module/exchangepowershell/new-addresslist#-recipientfilter) results from the address list that's specified by this parameter.
- When using experiences that aren't location specific (for example, the To or Cc fields of a calendar event), the address lists specified by the AddressLists parameter in this address book policy are applied. The address list specified by this parameter isn't used.

A valid value for this parameter is one address list. You can use any value that uniquely identifies the address list. For example:

- Name
- Distinguished name (DN)
- GUID

> [!NOTE]
> There's no automatic association between this parameter and [room list distribution groups](https://learn.microsoft.com/exchange/recipients/room-mailboxes#create-a-room-list), which also use a parameter named RoomList in the New-DistributionGroup and Set-DistributionGroup cmdlets. You still need to create room list distribution groups and assign resources as group members. Location experiences are filtered to show only rooms included in the address list that's specified by the RoomList property of the address book policy that's assigned to the user (if any).

```yaml
Type: AddressListIdParameter
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
