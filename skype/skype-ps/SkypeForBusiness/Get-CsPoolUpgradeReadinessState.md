---
applicable: Lync Server 2013, Skype for Business Server 2015
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skypeforbusiness/get-cspoolupgradereadinessstate
schema: 2.0.0
title: Get-CsPoolUpgradeReadinessState
---

# Get-CsPoolUpgradeReadinessState

## SYNOPSIS
Returns information indicating whether or not your Skype for Business Server Registrar pools are ready to be upgraded.
The upgrade readiness state for a pool is based on the upgrade domains that have been configured for that pool.
This cmdlet was introduced in Lync Server 2013.


## SYNTAX

```
Get-CsPoolUpgradeReadinessState [-Confirm] [-Force] [-WhatIf] [-SkipIdleSecondaryVerification]
 [<CommonParameters>]
```

## DESCRIPTION
The Get-CsPoolUpgradeReadinessState cmdlet returns information about the upgrade readiness for a Skype for Business Server pool.
The returned information includes the number of Front End servers assigned to the pool; the number of currently active Front End servers; the name of the upgrade domain; and a True/False value that indicates whether the current state of the pool allows it to be upgraded.
Note that this cmdlet must be run locally on a Front End server in the pool being checked.
There are no options enabling you to run the Get-CsPoolUpgradeReadinessState cmdlet remotely.

The functions carried out by the Get-CsPoolUpgradeReadinessState cmdlet are not available in the Skype for Business Server Control Panel.

In Skype for Business Server 2019, Get-CsPoolUpgradeReadinessState cmdlet was replaced by [Get-CsUpgradeDomainInfo](Get-CsUpgradeDomainInfo.md) cmdlet.


## EXAMPLES

### Example 1
```
Get-CsPoolUpgradeReadinessState
```

The command shown in Example 1 returns the upgrade readiness state for the local Registrar pool.
Note that this command must be executed on a Front End server located within the pool.


## PARAMETERS

### -Force

> Applicable: Lync Server 2013, Skype for Business Server 2015

Suppresses the display of any non-fatal error message that might occur when running the command.

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

### -SkipIdleSecondaryVerification

> Applicable: Skype for Business Server 2015

When included in the command, Get-CsPoolUpgradeReadinessState returns even if replicas are still being built.
By default, Get-CsPoolUpgradeReadinessState waits until the replicas have been built before completing.

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

> Applicable: Lync Server 2013, Skype for Business Server 2015

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

> Applicable: Lync Server 2013, Skype for Business Server 2015

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

### Microsoft.Rtc.Management.Hadr.PoolUpgradeState


## NOTES


## RELATED LINKS
