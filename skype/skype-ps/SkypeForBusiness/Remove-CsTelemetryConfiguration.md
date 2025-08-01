---
applicable: Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skypeforbusiness/remove-cstelemetryconfiguration
schema: 2.0.0
title: Remove-CsTelemetryConfiguration
---

# Remove-CsTelemetryConfiguration

## SYNOPSIS
Use the `Remove-CsTelemetryConfiguration` cmdlet to remove an existing telemetry configuration.
UNRESOLVED_TOKEN_VAL(PS_TelemetryDataStatement)

## SYNTAX

```
Remove-CsTelemetryConfiguration [-Identity] <XdsIdentity> [-Confirm] [-Force] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
For privacy information, see the Skype for Business Privacy Statement (https://go.microsoft.com/fwlink/?LinkID=517480&clcid=0x409).

## EXAMPLES

### Example 1
```
Remove-CsTelemetryConfiguration -Identity Site:Redmond
```

This example removes the telemetry configuration for the Redmond site.


### Example 2
```
Get-CsTelemetryConfiguration -Filter "Site:*" | Remove-CsTelemetryConfiguration
```

This example uses the `Get-CsTelemetryConfiguration` cmdlet in combination with the Filter parameter to select the telemetry configurations that are configured at the site level and then pipelines them to the `Remove-CsTelemetryConfiguration` cmdlet for removal.
The result is that all "Site" scoped telemetry configurations are removed.


## PARAMETERS

### -Force

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Suppresses the display of any non-fatal error messages and completes the cmdlet operation.

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

### -Identity

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

A unique identifier that includes the scope of the telemetry configuration.
Telemetry configurations can be scoped at the Global, Site, or Service level.
For example, "site:Redmond" (for site).
The format of the service scope is "Service:\<Identity\>", where identity is derived from the topology.
You can use the following commands to identify the relevant services.

`Get-CsService -WebServer | fl Identity`

`Get-CsService -PoolFqdn \<pool\> | fl Identity`

The first command will give you all of the WebServices in the topology, regardless of the pool.
The second will give you all of the services on the pool, regardless of their role.
You can combine the two commands to zero in on a single role in a single pool.

The Global configuration can't be deleted.
Specifying the Global configuration will return it to the default Global settings.

```yaml
Type: XdsIdentity
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Prompts you for confirmation before executing the command.

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

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Describes what would happen if you executed the command without actually executing the command.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### XdsIdentity
This cmdlet takes pipeline input of the `Get-CsTelemetryConfiguration` cmdlet as shown in Example 2.

## OUTPUTS

### None

## NOTES

## RELATED LINKS
