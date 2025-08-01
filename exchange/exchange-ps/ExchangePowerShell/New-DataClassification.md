---
applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online
author: chrisda
external help file: Microsoft.Exchange.RemoteConnections-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/new-dataclassification
schema: 2.0.0
title: New-DataClassification
---

# New-DataClassification

## SYNOPSIS
This cmdlet is functional only in on-premises Exchange.

In Exchange Online, this cmdlet has been replaced by the [New-DlpSensitiveInformationType](https://learn.microsoft.com/powershell/module/exchangepowershell/new-dlpsensitiveinformationtype) cmdlet in Security & Compliance PowerShell.

Use the New-DataClassification cmdlet to create data classification rules that use document fingerprints.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
New-DataClassification [-Name] <String> -Description <String> -Fingerprints <MultiValuedProperty>
 [-ClassificationRuleCollectionIdentity <ClassificationRuleCollectionIdParameter>]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-Locale <CultureInfo>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Classification rule packages are used by data loss prevention (DLP) to detect sensitive content in messages.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
$Employee_Template = [System.IO.File]::ReadAllBytes('C:\My Documents\Contoso Employee Template.docx')

$Employee_Fingerprint = New-Fingerprint -FileData $Employee_Template -Description "Contoso Employee Template"

$Customer_Template = [System.IO.File]::ReadAllBytes('D:\Data\Contoso Customer Template.docx')

$Customer_Fingerprint = New-Fingerprint -FileData $Customer_Template -Description "Contoso Customer Template"

New-DataClassification -Name "Contoso Employee-Customer Confidential" -Fingerprints $Employee_Fingerprint,$Customer_Fingerprint -Description "Message contains Contoso employee or customer information."
```

This example creates a new data classification rule named "Contoso Employee-Customer Confidential" that uses the document fingerprints of the files C:\\My Documents\\Contoso Employee Template.docx and D:\\Data\\Contoso Customer Template.docx.

## PARAMETERS

### -Description

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Description parameter specifies a description for the data classification rule.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fingerprints

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Fingerprints parameter specifies the byte-encoded files to use as document fingerprints. You can use multiple document fingerprints separated by commas. For instructions on how to import documents to use as templates for fingerprints, see [New-Fingerprint](https://learn.microsoft.com/powershell/module/exchangepowershell/new-fingerprint) or the Examples section.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -Name

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Name parameter specifies a name for the data classification rule. The value must be less than 256 characters.

The value of this parameter is used in the Policy Tip that's presented to users in Outlook on the web.

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

### -ClassificationRuleCollectionIdentity

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

This parameter is reserved for internal Microsoft use.

```yaml
Type: ClassificationRuleCollectionIdParameter
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

### -Locale

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Locale parameter specifies the language that's associated with the data classification rule.

Valid input for this parameter is a supported culture code value from the Microsoft .NET Framework CultureInfo class. For example, da-DK for Danish or ja-JP for Japanese. For more information, see [CultureInfo Class](https://learn.microsoft.com/dotnet/api/system.globalization.cultureinfo).

You can add additional language translations to the data classification rule by using the Set-DataClassification cmdlet.

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
