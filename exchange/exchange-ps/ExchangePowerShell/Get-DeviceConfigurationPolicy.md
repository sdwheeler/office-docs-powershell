---
applicable: Exchange Online, Security & Compliance
author: chrisda
external help file: Microsoft.Exchange.TransportMailflow-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/get-deviceconfigurationpolicy
schema: 2.0.0
title: Get-DeviceConfigurationPolicy
---

# Get-DeviceConfigurationPolicy

## SYNOPSIS
This cmdlet is functional only in Security & Compliance PowerShell. For more information, see [Security & Compliance PowerShell](https://learn.microsoft.com/powershell/exchange/scc-powershell).

Use the Get-DeviceConfigurationPolicy cmdlet to view mobile device configuration policies in Basic Mobility and Security in Microsoft 365.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Get-DeviceConfigurationPolicy [[-Identity] <PolicyIdParameter>]
 [<CommonParameters>]
```

## DESCRIPTION
The cmdlets in Basic Mobility and Security are described in the following list:

- DeviceTenantPolicy and DeviceTenantRule cmdlets: A policy that defines whether to block or allow mobile device access to Exchange Online email by unsupported devices that use Exchange ActiveSync only. This setting applies to all users in your organization. Both allow and block scenarios allow reporting for unsupported devices, and you can specify exceptions to the policy based on security groups.
- DeviceConditionalAccessPolicy and DeviceConditionalAccessRule cmdlets: Policies that control mobile device access to Microsoft 365 for supported devices. These policies are applied to security groups. Unsupported devices are not allowed to enroll in Basic Mobility and Security.
- DeviceConfigurationPolicy and DeviceConfigurationRule cmdlets: Policies that control mobile device settings for supported devices. These policies are applied to security groups.
- Get-DevicePolicy: Returns all Basic Mobility and Security policies regardless of type (DeviceTenantPolicy, DeviceConditionalAccessPolicy or DeviceConfigurationPolicy).

For more information about Basic Mobility and Security, see [Overview of Basic Mobility and Security for Microsoft 365](https://learn.microsoft.com/microsoft-365/admin/basic-mobility-security/overview).

To use this cmdlet in Security & Compliance PowerShell, you need to be assigned permissions. For more information, see [Permissions in the Microsoft Defender portal](https://learn.microsoft.com/defender-office-365/mdo-portal-permissions) or [Permissions in the Microsoft Purview compliance portal](https://learn.microsoft.com/purview/microsoft-365-compliance-center-permissions).

## EXAMPLES

### Example 1
```powershell
Get-DeviceConfigurationPolicy | Format-Table Name,Enabled,Priority
```

This example shows summary information for all mobile device configuration policies.

### Example 2
```powershell
Get-DeviceConfigurationPolicy -Identity "Engineering Group"
```

This example shows details about the mobile device configuration policy named Engineering Group.

## PARAMETERS

### -Identity

> Applicable: Exchange Online, Security & Compliance

The Identity parameter specifies the mobile device configuration policy that you want to view. You can use any value that uniquely identifies the policy. For example:

- Name
- Distinguished name (DN)
- GUID

```yaml
Type: PolicyIdParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/p/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
