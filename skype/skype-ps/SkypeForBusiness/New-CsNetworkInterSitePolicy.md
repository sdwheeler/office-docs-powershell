---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skypeforbusiness/new-csnetworkintersitepolicy
schema: 2.0.0
title: New-CsNetworkInterSitePolicy
---

# New-CsNetworkInterSitePolicy

## SYNOPSIS

Creates a new network inter-site policy that defines bandwidth limitations between sites that are directly linked within a call admission control (CAC) configuration.
This cmdlet was introduced in Lync Server 2010.



## SYNTAX

### Identity
```
New-CsNetworkInterSitePolicy [-Identity] <XdsGlobalRelativeIdentity> -NetworkSiteID1 <String>
 -NetworkSiteID2 <String> [-BWPolicyProfileID <String>] [-Force] [-InMemory] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ParentAndRelativeKey
```
New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID <String> -NetworkSiteID1 <String>
 -NetworkSiteID2 <String> [-BWPolicyProfileID <String>] [-Force] [-InMemory] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.
This cmdlet creates a network site policy that associates a bandwidth limitation policy with two directly connected sites.



## EXAMPLES

### EXAMPLE 1
```

New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits

```

This example creates a new network inter-site policy that limits bandwidth between the connected sites Reno and Portland.
The bandwidth limitations for audio and video connections between these sites are limited based on the setting configured for the bandwidth policy profile LowBWLimits.


## PARAMETERS

### -BWPolicyProfileID

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

The Identity of the bandwidth policy profile that will define the limitations for this site policy.
You can retrieve a list of available profiles by calling the Get-CsNetworkBandwidthPolicyProfile cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Suppresses any confirmation prompts that would otherwise be displayed before making changes.

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

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

A unique identifier for the newly created network inter-site policy.
Network inter-site policies are created only at the global scope, so this identifier does not need to specify a scope.
Instead, it contains a string that is a unique name that identifies that site policy.

```yaml
Type: XdsGlobalRelativeIdentity
Parameter Sets: Identity
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InMemory

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

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

### -InterNetworkSitePolicyID

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

This value is the same as the Identity.
You cannot specify both an Identity and an InterNetworkSitePolicyID; a value entered for one will be automatically used for both.

```yaml
Type: String
Parameter Sets: ParentAndRelativeKey
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkSiteID1

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

The Identity (NetworkSiteID) of one of the two sites associated with this policy.
The combination of NetworkSiteID1 and NetworkSiteID2 must be unique (for example, you can't have two site policies defined that connect Reno and Portland).

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

### -NetworkSiteID2

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

The Identity (NetworkSiteID) of one of the two sites associated with this policy.
The combination of NetworkSiteID1 and NetworkSiteID2 must be unique (for example, you can't have two site policies defined that connect Reno and Portland).

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

### -Confirm

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

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

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

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
This cmdlet supports the common parameters: `-Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).`

## INPUTS

### None

## OUTPUTS

### Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkSitePolicyType
Creates an object of type Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkSitePolicyType.

## NOTES

## RELATED LINKS

[Remove-CsNetworkInterSitePolicy](Remove-CsNetworkInterSitePolicy.md)

[Set-CsNetworkInterSitePolicy](Set-CsNetworkInterSitePolicy.md)

[Get-CsNetworkInterSitePolicy](Get-CsNetworkInterSitePolicy.md)
