---
applicable: Microsoft Teams
author: serdarsoysal
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml
Locale: en-US
manager: bulenteg
Module Name: MicrosoftTeams
ms.author: serdars
online version: https://learn.microsoft.com/powershell/module/microsoftteams/new-csonlinevoiceroutingpolicy
schema: 2.0.0
title: New-CsOnlineVoiceRoutingPolicy
---

# New-CsOnlineVoiceRoutingPolicy

## SYNOPSIS
Creates a new online voice routing policy. Online voice routing policies manage online PSTN usages for Phone System users.

## SYNTAX

### Identity
```
New-CsOnlineVoiceRoutingPolicy [-Identity] <string> [-Description <string>] [-OnlinePstnUsages <Object>] [-RouteType <string>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Online voice routing policies are used in Microsoft Phone System Direct Routing scenarios. Assigning your Teams users an online voice routing policy enables those users to receive and to place phone calls to the public switched telephone network by using your on-premises SIP trunks.

Note that simply assigning a user an online voice routing policy will not enable them to make PSTN calls via  Teams. Among other things, you will also need to enable those users for Phone System and will need to assign them an appropriate online voice policy.

## EXAMPLES

### Example 1
```
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "RedmondOnlineVoiceRoutingPolicy" -OnlinePstnUsages "Long Distance"
```

The command shown in Example 1 creates a new online per-user voice routing policy with the Identity RedmondOnlineVoiceRoutingPolicy. This policy is assigned a single online PSTN usage: Long Distance.

### Example 2
```
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "RedmondOnlineVoiceRoutingPolicy" -OnlinePstnUsages "Long Distance", "Local", "Internal"
```

Example 2 is a variation of the command shown in Example 1; in this case, however, the new policy is assigned three online PSTN usages: Long Distance; Local; Internal. Multiple usages can be assigned simply by separating each usage using a comma.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

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

### -Description
Enables administrators to provide explanatory text to accompany an online voice routing policy. For example, the Description might include information about the users the policy should be assigned to.

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

### -Identity
Unique identifier assigned to the policy when it was created.

```yaml
Type: String
Parameter Sets: Identity
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnlinePstnUsages
A list of online PSTN usages (such as Local or Long Distance) that can be applied to this online voice routing policy. The online PSTN usage must be an existing usage (PSTN usages can be retrieved by calling the `Get-CsOnlinePstnUsage` cmdlet).

```yaml
Type: Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouteType
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS
[Get-CsOnlineVoiceRoutingPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/get-csonlinevoiceroutingpolicy)

[Set-CsOnlineVoiceRoutingPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/set-csonlinevoiceroutingpolicy)

[Grant-CsOnlineVoiceRoutingPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/grant-csonlinevoiceroutingpolicy)

[Remove-CsOnlineVoiceRoutingPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/remove-csonlinevoiceroutingpolicy)
