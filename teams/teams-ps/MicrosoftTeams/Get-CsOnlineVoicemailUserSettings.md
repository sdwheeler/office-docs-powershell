---
applicable: Microsoft Teams
author: serdarsoysal
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml
Locale: en-US
manager: bulenteg
Module Name: MicrosoftTeams
ms.author: serdars
online version: https://learn.microsoft.com/powershell/module/microsoftteams/get-csonlinevoicemailusersettings
schema: 2.0.0
title: Get-CsOnlineVoicemailUserSettings
---

# Get-CsOnlineVoicemailUserSettings

## SYNOPSIS
Use the Get-CsOnlineVoicemailUserSettings cmdlet to get information about online voicemail user settings of a specific user.

## SYNTAX

```
Get-CsOnlineVoicemailUserSettings [-Identity] <string> [-Force] [<CommonParameters>]
```

## DESCRIPTION
The Get-CsOnlineVoicemailUserSettings cmdlet returns information about online voicemail user settings of a specific user in your organization.

## EXAMPLES

### Example 1
```
Get-CsOnlineVoicemailUserSettings -Identity sip:user@contoso.com
```

This example gets the online voicemail user settings of user with SIP URI sip:user@contoso.com.

## PARAMETERS

### -Force
Specifies whether to suppress warning and confirmation messages. It can be useful in scripting to suppress interactive prompts. If the Force switch isn't provided in the command, you're prompted for administrative input if required.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity

> Applicable: Microsoft Teams

The Identity parameter represents the ID of the specific user in your organization; this can be either a SIP URI or an Object ID.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
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

### Microsoft.Rtc.Management.Hosted.Voicemail.Models.VoicemailUserSettings

## NOTES

## RELATED LINKS

[Set-CsOnlineVoicemailUserSettings](https://learn.microsoft.com/powershell/module/microsoftteams/set-csonlinevoicemailusersettings)
