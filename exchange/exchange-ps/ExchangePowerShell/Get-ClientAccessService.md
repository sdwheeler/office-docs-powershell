---
applicable: Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.WebClient-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/get-clientaccessservice
schema: 2.0.0
title: Get-ClientAccessService
---

# Get-ClientAccessService

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the Get-ClientAccessService cmdlet to view settings that are associated with the Client Access server role.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Get-ClientAccessService [[-Identity] <ClientAccessServerIdParameter>]
 [-DomainController <Fqdn>]
 [-IncludeAlternateServiceAccountCredentialPassword]
 [-IncludeAlternateServiceAccountCredentialStatus]
 [<CommonParameters>]
```

## DESCRIPTION
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Get-ClientAccessService | Format-Table Name
```

This example returns a summary list of all Exchange servers in your organization that have theClient Access server role installed.

### Example 2
```powershell
Get-ClientAccessService -Identity mail.contoso.com | Format-List
```

This example returns detailed information for the server mail.contoso.com.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2016, Exchange Server 2019

The Identity parameter specifies the server with the Client Access server role installed that you want to view.

You can use any value that uniquely identifies the server. For example:

- Name (for example, Exchange01)
- Distinguished name (DN) (for example, CN=Exchange01,CN=Servers,CN=Exchange Administrative Group (FYDIBOHF23SPDLT),CN=Administrative Groups,CN=First Organization,CN=Microsoft Exchange,CN=Services,CN=Configuration,DC=contoso,DC=com)
- Exchange Legacy DN (for example, /o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Configuration/cn=Servers/cn=Exchange01)
- GUID (for example, bc014a0d-1509-4ecc-b569-f077eec54942)

```yaml
Type: ClientAccessServerIdParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -DomainController

> Applicable: Exchange Server 2016, Exchange Server 2019

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

### -IncludeAlternateServiceAccountCredentialPassword

> Applicable: Exchange Server 2016, Exchange Server 2019

The IncludeAlternateServiceAccountCredentialPassword switch specifies whether to include the password of the alternate service account in the results. You don't need to specify a value with this switch.

The password is visible in the AlternateServiceAccountConfiguration property. To see this property, use the Format-List cmdlet. For example, `Get-ClientAccessService <ServerIdentity> | Format-List AlternateServiceAccountConfiguration`.

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

### -IncludeAlternateServiceAccountCredentialStatus

> Applicable: Exchange Server 2016, Exchange Server 2019

The IncludeAlternateServiceAccountCredentialStatus parameter specifies whether to include the status of the alternate service account in the results. You don't need to specify a value with this switch.

The status is visible in the AlternateServiceAccountConfiguration property. To see this property, use the Format-List cmdlet. For example, `Get-ClientAccessService <ServerIdentity> | Format-List AlternateServiceAccountConfiguration`.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/p/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
