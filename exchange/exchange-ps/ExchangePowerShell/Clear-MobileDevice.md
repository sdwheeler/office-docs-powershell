---
applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online
author: chrisda
external help file: Microsoft.Exchange.MediaAndDevices-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/clear-mobiledevice
schema: 2.0.0
title: Clear-MobileDevice
---

# Clear-MobileDevice

## SYNOPSIS
This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

Use the Clear-MobileDevice cmdlet to delete all data from a mobile phone. This action is often called a remote device wipe.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Clear-MobileDevice [-Identity] <MobileDeviceIdParameter>
 [-AccountOnly]
 [-Cancel]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-NotificationEmailAddresses <MultiValuedProperty>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
The Clear-MobileDevice cmdlet deletes all user data from a mobile device the next time that the device receives data from the Microsoft Exchange server. This cmdlet sets the DeviceWipeStatus parameter to $true. The mobile device acknowledges the cmdlet and records the time stamp in the DeviceWipeAckTime parameter.

After you run this cmdlet, you receive a warning that states: "This command will force all the data on the device to be permanently deleted. Do you want to continue?" You must respond to the warning for the cmdlet to run on the mobile phone.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Clear-MobileDevice -Identity TonySmith\ExchangeActiveSyncDevices\REST§Outlook§5eec4e941e0748a264512fd83770d5ac
```

This example clears all data from the specified mobile device.

### Example 2
```powershell
Clear-MobileDevice -Identity TonySmith\ExchangeActiveSyncDevices\REST§Outlook§5eec4e941e0748a264512fd83770d5ac -NotificationEmailAddresses "chris@contoso.com"
```

This example clears all data from the specified mobile device and sends a confirmation email message to chris@contoso.com.

### Example 3
```powershell
Clear-MobileDevice -Identity TonySmith\ExchangeActiveSyncDevices\REST§Outlook§5eec4e941e0748a264512fd83770d5ac -Cancel
```

This example cancels a previously sent Clear-MobileDevice command request for the specified mobile device.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Identity parameter specifies the mobile device that you want to reset. You can use the following values that uniquely identifies the mobile device:

- Identity (`<Mailbox Name>\ExchangeActiveSyncDevices\<MobileDeviceObjectName>` for example, `CarlosM\ExchangeActiveSyncDevices\REST§Outlook§5eec4e941e0748a264512fd83770d5ac`)
- Distinguished name (DN)
- GUID (same as ExchangeObjectId)

```yaml
Type: MobileDeviceIdParameter
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -AccountOnly

> Applicable: Exchange Server 2016, Exchange Server 2019, Exchange Online

The AccountOnly switch specifies whether to perform an account-only remote device wipe where only Exchange mailbox data is removed from the device. You don't need to specify a value with this switch.

You don't need to use this switch for the DeviceType value Outlook, because an account-only remote device wipe is the only type of wipe that's used on Outlook devices.

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

### -Cancel

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Cancel switch specifies whether to issue a cancellation request for a pending remote device wipe. You don't need to specify a value with this switch.

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

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Confirm switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding.

- Destructive cmdlets (for example, Remove-\* cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.
- Most other cmdlets (for example, New-\* and Set-\* cmdlets) don't have a built-in pause. For these cmdlets, specifying the Confirm switch without a value introduces a pause that forces you acknowledge the command before proceeding.

This cmdlet has a built-in pause, so use `-Confirm:$false` to skip the confirmation.

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

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

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

### -NotificationEmailAddresses

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The NotificationEmailAddresses parameter specifies the notification email address for the remote device wipe confirmation. You can specify multiple values separated by commas.

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

### -WhatIf

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

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
