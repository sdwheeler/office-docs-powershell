---
applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online
author: chrisda
external help file: Microsoft.Exchange.RemoteConnections-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/get-dataclassification
schema: 2.0.0
title: Get-DataClassification
---

# Get-DataClassification

## SYNOPSIS
This cmdlet is functional only in on-premises Exchange.

In Exchange Online, this cmdlet has been replaced by the [Get-DlpSensitiveInformationType](https://learn.microsoft.com/powershell/module/exchangepowershell/get-dlpsensitiveinformationtype) cmdlet in Security & Compliance PowerShell.

Use the Get-DataClassification cmdlet to view the data classification rules in your organization. This cmdlet shows built-in data classification rules and rules that you created that use document fingerprints.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

### RuleCollectionIdentity
```
Get-DataClassification [[-ClassificationRuleCollectionIdentity] <ClassificationRuleCollectionIdParameter>]
 [-DomainController <Fqdn>]
 [<CommonParameters>]
```

### Identity
```
Get-DataClassification [[-Identity] <DataClassificationIdParameter>]
 [-DomainController <Fqdn>]
 [<CommonParameters>]
```

## DESCRIPTION
Classification rule packages are used by data loss prevention (DLP) to detect sensitive content in messages.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Get-DataClassification
```

This example returns a summary list of all data classification rules in the organization.

### Example 2
```powershell
Get-DataClassification -ClassificationRuleCollectionIdentity "Fingerprint Classification Collection"
```

This example returns a summary list of all new data classification rules based on document fingerprints that you created.

### Example 3
```powershell
Get-DataClassification "SWIFT Code" | Format-List
```

This example returns details of the built-in data classification rule named SWIFT Code.

## PARAMETERS

### -ClassificationRuleCollectionIdentity

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The ClassificationRuleCollectionIdentity parameter filters the results by the name of the data classification rule collection. The data classification rule collection that contains the built-in data classification rules is named Microsoft Rule Package. The data classification that contains new data classification rules that you create that use document fingerprints is named Fingerprint Classification Collection.

```yaml
Type: ClassificationRuleCollectionIdParameter
Parameter Sets: RuleCollectionIdentity
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Identity parameter specifies the data classification rule that you want to view. You can use any value that uniquely identifies the data classification rule. For example:

- Name
- LocalizedName
- Identity GUID value

```yaml
Type: DataClassificationIdParameter
Parameter Sets: Identity
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True
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
