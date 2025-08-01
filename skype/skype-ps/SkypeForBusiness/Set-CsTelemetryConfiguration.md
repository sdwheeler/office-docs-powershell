---
applicable: Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skypeforbusiness/set-cstelemetryconfiguration
schema: 2.0.0
title: Set-CsTelemetryConfiguration
---

# Set-CsTelemetryConfiguration

## SYNOPSIS
Use the `Set-CsTelemetryConfiguration` cmdlet to change the settings on existing telemetry configurations.
UNRESOLVED_TOKEN_VAL(PS_TelemetryDataStatement)

## SYNTAX

### Identity
```
Set-CsTelemetryConfiguration [[-Identity] <XdsIdentity>] [-Confirm] [-EnableClientTelemetry <Boolean>] [-Force]
 [-WhatIf] [<CommonParameters>]
```

### Instance
```
Set-CsTelemetryConfiguration [-Confirm] [-EnableClientTelemetry <Boolean>] [-Force] [-Instance <PSObject>]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
For privacy information, see the Skype for Business Privacy Statement (https://go.microsoft.com/fwlink/?LinkID=517480&clcid=0x409).

## EXAMPLES

### Example 1
```
Set-CsTelemetryConfiguration -Identity site:Redmond -EnableClientTelemetry $True
```

This example enables client telemetry on the configuration scoped to the Redmond site.


## PARAMETERS

### -EnableClientTelemetry

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

When set to true, client telemetry will be enabled.
The default is false.

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

```yaml
Type: XdsIdentity
Parameter Sets: Identity
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Instance

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.

```yaml
Type: PSObject
Parameter Sets: Instance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### System.Management.Automation.PSObject
This cmdlet takes pipeline input of the `Get-CsTelemetryConfiguration` cmdlet.

## OUTPUTS

### None

## NOTES

## RELATED LINKS
