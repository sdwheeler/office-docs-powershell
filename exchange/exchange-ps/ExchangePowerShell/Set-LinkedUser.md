---
applicable: Exchange Online, Exchange Online Protection
author: chrisda
external help file: Microsoft.Exchange.RolesAndAccess-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/set-linkeduser
schema: 2.0.0
title: Set-LinkedUser
---

# Set-LinkedUser

## SYNOPSIS
This cmdlet is available only in the cloud-based service.

Use the Set-LinkedUser cmdlet to modify the properties of an existing linked user account. The Outlook Live Directory Sync (OLSync) service account is a linked user.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Set-LinkedUser [-Identity] <UserIdParameter>
 [-CertificateSubject <MultiValuedProperty>]
 [-Confirm]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
The OLSync service account is the only linked user in your organization. By default, the account is named GALSync-ServiceAccount.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Set-LinkedUser "GALSync-ServiceAccount" -CertificateSubject "X509:<I>CN=3rdPartyCAExample.com<S>C=US,O=Contoso Corp, CN=contoso.com"
```

This example modifies the certificate subject for the linked user "GALSync-ServiceAccount".

## PARAMETERS

### -Identity

> Applicable: Exchange Online, Exchange Online Protection

The Identity parameter specifies the linked user. You can use any value that uniquely identifies the linked user, for example:

- Name
- Distinguished name (DN)

```yaml
Type: UserIdParameter
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -CertificateSubject

> Applicable: Exchange Online

The CertificateSubject parameter specifies the value of the subject field of the user's digital certificate. The syntax of the CertificateSubject value is `X509:<I>Issuer<S>Subject`. The values of Issuer and Subject are required and must be in X.500 format. To remove the value of CertificateSubject, specify the value $null.

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

> Applicable: Exchange Online, Exchange Online Protection

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

### -WhatIf

> Applicable: Exchange Online, Exchange Online Protection

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
