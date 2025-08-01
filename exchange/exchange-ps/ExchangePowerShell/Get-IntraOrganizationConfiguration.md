---
applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online
author: chrisda
external help file: Microsoft.Exchange.CalendarsAndGroups-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/get-intraorganizationconfiguration
schema: 2.0.0
title: Get-IntraOrganizationConfiguration
---

# Get-IntraOrganizationConfiguration

## SYNOPSIS
This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

Use the Get-IntraOrganizationConfiguration cmdlet to view the component settings of a hybrid Exchange deployment.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Get-IntraOrganizationConfiguration [[-OrganizationGuid] <OnPremisesOrganizationIdParameter>]
 [<CommonParameters>]
```

## DESCRIPTION
A hybrid Exchange deployment results in one logical organization made up of a number of physical Exchange instances. Hybrid Exchange environments contain more than one Exchange instance and support topologies like two on-premises Microsoft Exchange forests in an organization, an Exchange on-premises organization and an Exchange Online organization or two Exchange Online organizations.

Hybrid environments are enabled by Intra-Organization connectors. The connectors can be created and managed by cmdlets like New-IntraOrganizationConnector, but we strongly recommend that you use the Hybrid Configuration wizard when configuring a hybrid deployment with an Exchange Online organization.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Get-IntraOrganizationConfiguration
```

This example returns the settings of the intra-organization configuration.

## PARAMETERS

### -OrganizationGuid

> Applicable: Exchange Online

This parameter is available only in the cloud-based service.

The OrganizationGuid parameter specifies the on-premises organization in a hybrid deployment that has multiple on-premises organizations defined. If you don't use the OrganizationGuid parameter for these types of hybrid deployments, the Get-IntraOrganizationConfiguration cmdlet will generate errors. To view the on-premises organization GUID values that are required for this parameter, use the Get-OnPremisesOrganization cmdlet.

```yaml
Type: OnPremisesOrganizationIdParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True
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
