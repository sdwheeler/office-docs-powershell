---
applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online
author: chrisda
external help file: Microsoft.Exchange.CalendarsAndGroups-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/new-intraorganizationconnector
schema: 2.0.0
title: New-IntraOrganizationConnector
---

# New-IntraOrganizationConnector

## SYNOPSIS
This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

Use the New-IntraOrganizationConnector cmdlet to create an Intra-Organization connector between two on-premises Exchange forests in an organization, between an Exchange on-premises organization and an Exchange Online organization, or between two Exchange Online organizations. This connector enables feature availability and service connectivity across the organizations using a common connector and connection endpoints.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
New-IntraOrganizationConnector [-Name] <String> -DiscoveryEndpoint <Uri> -TargetAddressDomains <MultiValuedProperty>
 [-Confirm]
 [-DomainController <Fqdn>]
 [-Enabled <Boolean>]
 [-TargetSharingEpr <Uri>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
The New-IntraOrganizationConnector cmdlet is used to create a connection for features and services between divisions in your Exchange organization. It allows for the expansion of organizational boundaries for features and services across different hosts and network boundaries, such as between Active Directory forests, between on-premises and cloud-based organizations, or between tenants hosted in the same or different datacenters.

For hybrid deployments between on-premises Exchange and Exchange Online organizations, the New-IntraOrganizationConnector cmdlet is used by the Hybrid Configuration wizard. Typically, the Intra-Organization connector is configured when the hybrid deployment is initially created by the wizard. We strongly recommend that you use the Hybrid Configuration wizard to create the Intra-Organization connector when configuring a hybrid deployment with an Exchange Online organization.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
New-IntraOrganizationConnector -DiscoveryEndpoint https://ExternalDiscovery.Contoso.com -Name MainCloudConnector -TargetAddressDomains Cloud1.contoso.com,Cloud2.contoso.com
```

This example creates an Intra-Organization connector named "MainCloudConnector" between an on-premises Exchange organization and an Exchange Online organization containing two domains, Cloud1.contoso.com and Cloud2.contoso.com.

## PARAMETERS

### -Name

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Name parameter specifies a friendly name for the Intra-Organization connector. If the value contains spaces, enclose the value in double quotation marks.

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

### -DiscoveryEndpoint

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The DiscoveryEndpoint parameter specifies the externally-accessible URL that's used for the Autodiscover service for the domain that's configured in the Intra-Organization connector.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetAddressDomains

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The TargetAddressDomains parameter specifies the domain namespaces that will be used in the Intra-organization connector. These domains must have valid Autodiscover endpoints defined in their organizations. The domains and their associated Autodiscover endpoints are used by the Intra-Organization connector for feature and service connectivity.

You specify multiple domain values separated by commas.

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

### -Enabled

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Enabled parameter enables or disabled the Intra-organization connector. The valid values for this parameter are $true or $false. The default value is $true.

When you set the value to $false, you completely stop connectivity for the specific connection.

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

### -TargetSharingEpr

> Applicable: Exchange Online

This parameter is available only in the cloud-based service.

The TargetSharingEpr parameter specifies the URL of the target Exchange Web Services that will be used in the Intra-Organization connector.

```yaml
Type: Uri
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
