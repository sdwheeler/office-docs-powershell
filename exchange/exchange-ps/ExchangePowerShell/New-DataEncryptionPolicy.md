---
applicable: Exchange Online
author: chrisda
external help file: Microsoft.Exchange.WebClient-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/new-dataencryptionpolicy
schema: 2.0.0
title: New-DataEncryptionPolicy
---

# New-DataEncryptionPolicy

## SYNOPSIS
This cmdlet is available only in the cloud-based service.

Use the New-DataEncryptionPolicy cmdlet to create data encryption policies in Exchange Online.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
New-DataEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty>
 [-Confirm]
 [-Description <String>]
 [-DomainController <Fqdn>]
 [-Enabled <Boolean>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Data encryption policy cmdlets are the Exchange Online part of Customer Key. For more information, see [Controlling your data in Microsoft 365 using Customer Key](https://aka.ms/customerkey).

You can assign a data encryption policy to a mailbox by using the DataEncryptionPolicy parameter on the Set-Mailbox cmdlet in Exchange Online PowerShell.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
New-DataEncryptionPolicy -Name "US Mailboxes" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/USA_Key_01","https://contosoEastUSvault01.vault.azure.net/keys/USA_Key_02" -Description "Root key for mailboxes located in US territories"
```

This example creates a data encryption policy named US Mailboxes with the specified Azure Key Vault keys and description.

## PARAMETERS

### -Name

> Applicable: Exchange Online

The Name parameter specifies the unique name for the data encryption policy. If the value contains spaces, enclose the value in quotation marks.

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

### -AzureKeyIDs

> Applicable: Exchange Online

The AzureKeyIDs parameter specifies the URI values of the Azure Key Vault keys to associate with the data encryption policy. You need to specify at least two Azure Key Vault keys separated by commas. For example, `"https://contosoWestUSvault01.vault.azure.net/keys/USA_Key_01","https://contosoEastUSvault01.vault.azure.net/keys/USA_Key_02"`.

To find the URI value for an Azure Key Vault, replace `<VaultName>` with the name of the vault, and run this command in Azure Rights Management PowerShell: `Get-AzureKeyVaultKey -VaultName <VaultName>).id`. For more information, see [About Azure Key Vault](https://learn.microsoft.com/azure/key-vault/general/overview).

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

> Applicable: Exchange Online

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

### -Description

> Applicable: Exchange Online

The Description parameter specifies an optional description for the data encryption policy. If the value contains spaces, enclose the value in quotation marks.

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

### -DomainController

> Applicable: Exchange Online

This parameter is reserved for internal Microsoft use.

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

> Applicable: Exchange Online

The Enabled parameter enables or disable the data encryption policy. Valid values are:

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

### -WhatIf

> Applicable: Exchange Online

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

## OUTPUTS

## NOTES

## RELATED LINKS
