---
applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.RemoteConnections-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/dump-provisioningcache
schema: 2.0.0
title: Dump-ProvisioningCache
---

# Dump-ProvisioningCache

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the Dump-ProvisioningCache cmdlet to return a list of the cached keys and values for the specified server and Windows PowerShell application.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

### GlobalCache
```
Dump-ProvisioningCache [-Server] <Fqdn> -Application <String>
 [-GlobalCache]
 [-CacheKeys <MultiValuedProperty>]
 [-Confirm]
 [-WhatIf]
 [<CommonParameters>]
```

### OrganizationCache
```
Dump-ProvisioningCache [-Server] <Fqdn> -Application <String>
 [-CurrentOrganization]
 [-Organizations <MultiValuedProperty>]
 [-CacheKeys <MultiValuedProperty>]
 [-Confirm]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
The Dump-ProvisioningCache cmdlet is for diagnostic purposes only and is rarely used. Exchange administrators or Microsoft support personnel may need to run this cmdlet to troubleshoot problems resulting from incorrect links or properties stamped on newly provisioned recipients, which can be caused by stale data in the provisioning cache.

The Dump-ProvisioningCache cmdlet displays a list of the Windows PowerShell provisioning cache keys. Use the value of these cache keys with the Reset-ProvisioningCache cmdlet to reset provisioning cache data.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Dump-ProvisioningCache -Server EXSRV1.contoso.com -Application Powershell-Proxy -GlobalCache
```

This example displays all cache keys for the specified server and Windows PowerShell application.

## PARAMETERS

### -Server

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Server parameter specifies the fully qualified domain name (FQDN) of the server that the application you want to reset is running on.

```yaml
Type: Fqdn
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -Application

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Application parameter specifies the specific administrative application to reset the provisioning cache for. You can use the following values:

- Powershell
- Powershell-LiveId
- Powershell-Proxy
- PowershellLiveId-Proxy
- Ecp
- Psws

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

### -GlobalCache

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The GlobalCache switch specifies that all cache keys are cleared. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: GlobalCache
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CacheKeys

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The CacheKeys parameter specifies the value for the cache key that you want to clear. The format for the values should contain 32 digits separated by four dashes: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx

Use the Dump-ProvisioningCache cmdlet to return a list of cache keys.

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

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

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

### -CurrentOrganization

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The CurrentOrganization switch specifies that the provision cache is reset for this organization. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: OrganizationCache
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Organizations

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Organizations parameter specifies the organizations that the provisioning cache will be reset. This parameter is used in multi-tenant deployments.

```yaml
Type: MultiValuedProperty
Parameter Sets: OrganizationCache
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

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
