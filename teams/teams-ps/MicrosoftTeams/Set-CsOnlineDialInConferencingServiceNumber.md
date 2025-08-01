---
applicable: Microsoft Teams
author: tomkau
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml
Locale: en-US
manager: bulenteg
Module Name: MicrosoftTeams
ms.author: tomkau
ms.reviewer: williamlooney
online version: https://learn.microsoft.com/powershell/module/microsoftteams/set-csonlinedialinconferencingservicenumber
schema: 2.0.0
title: Set-CsOnlineDialInConferencingServiceNumber
---

# Set-CsOnlineDialInConferencingServiceNumber

## SYNOPSIS
Use the `Set-CsOnlineDialInConferencingServiceNumber` cmdlet to modify the properties of a dial-in or audio conferencing service number that is used by callers when they dial in to a meeting.

## SYNTAX

### UniqueNumberParams (Default)
```
Set-CsOnlineDialInConferencingServiceNumber [-Identity] <String> [-Tenant <Guid>]
 [-PrimaryLanguage <String>] [-SecondaryLanguages <String>] [-RestoreDefaultLanguages] [-DomainController <Fqdn>]
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceParams
```
Set-CsOnlineDialInConferencingServiceNumber [-Instance] <ConferencingServiceNumber> [-Tenant <Guid>]
 [-PrimaryLanguage <String>] [-SecondaryLanguages <String>] [-RestoreDefaultLanguages] [-DomainController <Fqdn>]
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The `Set-CsOnlineDialInConferencingServiceNumber` cmdlet enables you to set the primary and secondary languages or restore the default languages for a given service number.
The primary language will be used for the prompts that callers will listen to when they are entering a meeting.
The secondary languages (up to 4) will be available as options in the case the caller wants the prompts read in a different language.
The following languages are supported for PSTN conferencing:

Arabic

Chinese (Simplified)

Chinese (Traditional)

Danish

Dutch

English (Australia)

English (United Kingdom)

English (United States)

Finnish

French (Canada)

French (France)

German

Hebrew

Italian

Japanese

Korean

Norwegian (Bokmal)

Portuguese

Russian

Spanish (Mexico)

Spanish (Spain)

Swedish

Turkish

Ukrainian

## EXAMPLES

### Example 1
```
Set-CsOnlineDialInConferencingServiceNumber -Identity +14255551234 -PrimaryLanguage de-de -SecondaryLanguages en-us, ja-jp, en-gb
```

This example sets the primary language to German (Germany) and the secondary languages to US English, Japanese, and UK English for the dial-in service number +14255551234.

## PARAMETERS

### -Confirm

> Applicable: Microsoft Teams

The Confirm switch causes the command to pause processing, and requires confirmation to proceed.

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

### -DomainController

> Applicable: Microsoft Teams

Specifies the domain controller that's used by the cmdlet to read or write the specified data.
Valid inputs for this parameter include:

Fully qualified domain name (FQDN): -DomainController atl-cs-001.Contoso.com.

Computer name: -DomainController atl-cs-001

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

### -Identity

> Applicable: Microsoft Teams

Specifies the default dial-in service number string.
The service number can be specified in the following formats: E.164 number, +\<E.164 number\> and tel:\<E.164 number\>.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Instance

> Applicable: Microsoft Teams

Allows you to pass a reference to the Office 365 audio service number object to the cmdlet rather than set individual parameter values.

```yaml
Type: ConferencingServiceNumber
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryLanguage

> Applicable: Microsoft Teams

Specifies the primary language that is used when users call into a meeting.
The culture ID is used.
For example, en-US for US English, ja-JP for Japanese, or es-ES for Spanish.

Use the `Get-CsOnlineDialInConferencingLanguagesSupported` cmdlet to get a list of the available languages.

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

### -RestoreDefaultLanguages

> Applicable: Microsoft Teams

Including this switch restores all of the default languages for the audio conferencing service number.

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

### -SecondaryLanguages

> Applicable: Microsoft Teams

Specifies the secondary languages that can be used when users call into a meeting.
The culture ID is used.
For example, en-US for US English, ja-JP for Japanese, or es-ES for Spanish.
The order you provide will be the order that will be presented to users that are calling into the meeting.
There is a maximum of 4 languages that can be used as secondary languages.

Use the `Get-CsOnlineDialInConferencingLanguagesSupported` cmdlet to get a list of the available languages.

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

### -WhatIf

> Applicable: Microsoft Teams

The WhatIf switch causes the command to simulate its results.
By using this switch, you can view what changes would occur without having to commit those changes.

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

## OUTPUTS

## NOTES

## RELATED LINKS
