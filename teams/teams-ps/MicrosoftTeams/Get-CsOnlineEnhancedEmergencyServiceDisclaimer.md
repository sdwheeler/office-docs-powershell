---
applicable: Microsoft Teams
author: tomkau
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml
Locale: en-US
manager: bulenteg
Module Name: MicrosoftTeams
ms.author: tomkau
ms.reviewer: williamlooney
online version: https://learn.microsoft.com/powershell/module/microsoftteams/get-csonlineenhancedemergencyservicedisclaimer
schema: 2.0.0
title: Get-CsOnlineEnhancedEmergencyServiceDisclaimer
---

# Get-CsOnlineEnhancedEmergencyServiceDisclaimer

## SYNOPSIS
Use the Get-CsOnlineEnhancedEmergencyServiceDisclaimer cmdlet to determine whether your organization has accepted the terms and conditions of enhanced emergency service.

## SYNTAX

```
Get-CsOnlineEnhancedEmergencyServiceDisclaimer [-CountryOrRegion <CountryInfo>] [-DomainController <Fqdn>] [-Force] [-Tenant <Guid>] [-Version <String>] [<CommonParameters>]
```

## DESCRIPTION
You can use this cmdlet to determine whether your organization has accepted the terms and conditions of enhanced emergency service. The United States is currently the only country supported.

## EXAMPLES

### Example 1
```
Get-CsOnlineEnhancedEmergencyServiceDisclaimer -CountryOrRegion "US"
```

This example returns your organization's enhanced emergency service terms and conditions acceptance status.

## PARAMETERS

### -CountryOrRegion

> Applicable: Microsoft Teams

Specifies the region or country whose terms and conditions you wish to verify.
The United States is currently the only country supported, but it must be specified as "US".

```yaml
Type: CountryInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainController

> Applicable: Microsoft Teams

This parameter is reserved for internal Microsoft use.

```yaml
Type: Fqdn
Parameter Sets: (All)
Aliases: DC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

> Applicable: Microsoft Teams

The Force switch specifies whether to suppress warning and confirmation messages.
It can be useful in scripting to suppress interactive prompts.
If the Force switch isn't provided in the command, you're prompted for administrative input if required.

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

### -Tenant

> Applicable: Microsoft Teams

This parameter is reserved for internal Microsoft use.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version

> Applicable: Microsoft Teams

This parameter is reserved for internal Microsoft use.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS
[Set-CsOnlineEnhancedEmergencyServiceDisclaimer](https://learn.microsoft.com/powershell/module/microsoftteams/set-csonlineenhancedemergencyservicedisclaimer)
