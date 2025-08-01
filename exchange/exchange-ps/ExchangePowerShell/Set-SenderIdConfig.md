---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.TransportMailControl-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/set-senderidconfig
schema: 2.0.0
title: Set-SenderIdConfig
---

# Set-SenderIdConfig

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the Set-SenderIdConfig cmdlet to modify the configuration of the Sender ID agent.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Set-SenderIdConfig
 [-BypassedRecipients <MultiValuedProperty>]
 [-BypassedSenderDomains <MultiValuedProperty>]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-Enabled <Boolean>]
 [-ExternalMailEnabled <Boolean>]
 [-InternalMailEnabled <Boolean>]
 [-SpoofedDomainAction <SenderIdAction>]
 [-TempErrorAction <SenderIdAction>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Set-SenderIdConfig -SpoofedDomainAction Delete -BypassedRecipients user1@contoso.com,user2@contoso.com
```

This example makes the following modifications to the Sender ID configuration:

- It sets the Sender ID agent to delete all messages sent from spoofed domains.
- It specifies two recipients for the Sender ID agent to exclude when it processes messages.

## PARAMETERS

### -BypassedRecipients

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The BypassedRecipients parameter specifies one or more SMTP email addresses. Messages bound for the email addresses listed in this parameter are excluded from processing by the Sender ID agent. You can specify multiple values separated by commas. You can enter a maximum of 100 email addresses.

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

### -BypassedSenderDomains

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The BypassedSenderDomains parameter specifies one or more domain names. Messages that originate from the domains listed in this parameter are excluded from processing by the Sender ID agent. You can specify multiple values separated by commas. You can enter a maximum of 100 domain names.

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

### -Confirm

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

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

The DomainController parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, dc01.contoso.com.

The DomainController parameter isn't supported on Edge Transport servers. An Edge Transport server uses the local instance of Active Directory Lightweight Directory Services (AD LDS) to read and write data.

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

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Enabled parameter specifies whether the Sender ID agent is enabled on the computer on which you're running the command. Valid input for the Enabled parameter is $true or $false. The default setting is $true. When the Enabled parameter is set to $true, the Sender ID agent is enabled on the computer on which you're running the command.

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

### -ExternalMailEnabled

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ExternalMailEnabled parameter specifies whether all messages from unauthenticated connections external to your organization are passed through the Sender ID agent for processing. Valid input for the ExternalMailEnabled parameter is $true or $false. The default setting is $true. When the ExternalMailEnabled parameter is set to $true, all messages from unauthenticated connections external to your organization are passed through the Sender ID agent for processing.

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

### -InternalMailEnabled

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The InternalMailEnabled parameter specifies whether all messages from authenticated sender domains that belong to authoritative domains in your enterprise are passed through the Sender ID agent for processing. Valid input for the InternalMailEnabled parameter is $true or $false. The default setting is $false. When the InternalMailEnabled parameter is set to $true, all messages from authenticated sender domains that belong to authoritative domains in your enterprise are passed through the Sender ID agent for processing.

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

### -SpoofedDomainAction

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The SpoofedDomainAction parameter specifies the action that the Sender ID agent takes on the message when the sender domain shows evidence of being spoofed. The SpoofedDomainAction parameter takes the following values: StampStatus, Reject or Delete. The default value is StampStatus.

```yaml
Type: SenderIdAction
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TempErrorAction

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The TempErrorAction parameter specifies the action that the Sender ID agent takes on the message when a Sender ID status of TempError is returned. The TempErrorAction parameter takes the following values: StampStatus, Reject or Delete. The default value is StampStatus.

```yaml
Type: SenderIdAction
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

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
