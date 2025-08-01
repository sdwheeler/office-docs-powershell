---
applicable: Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skypeforbusiness/new-cstelemetryconfiguration
schema: 2.0.0
title: New-CsTelemetryConfiguration
---

# New-CsTelemetryConfiguration

## SYNOPSIS
Use the `New-CsTelemetryConfiguration` cmdlet to create new configurations for telemetry.
UNRESOLVED_TOKEN_VAL(PS_TelemetryDataStatement)

## SYNTAX

```
New-CsTelemetryConfiguration [-Identity] <XdsIdentity> [-Confirm] [-EnableClientTelemetry <Boolean>] [-Force]
 [-InMemory] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
For privacy information, see the Skype for Business Privacy Statement (https://go.microsoft.com/fwlink/?LinkID=517480&clcid=0x409).

## EXAMPLES

### Example 1
```
New-CsTelemetryConfiguration -Identity Site:Redmond -EnableClientTelemetry $True
```

This example creates a new telemetry configuration with telemetry enabled and scoped for the Redmond site.


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
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InMemory

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Creates an object reference without actually committing the object as a permanent change.
If you assign the output of this cmdlet called with this parameter to a variable, you can make changes to the properties of the object reference and then commit those changes by calling this cmdlet's matching Set-\<cmdlet\>.

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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS
