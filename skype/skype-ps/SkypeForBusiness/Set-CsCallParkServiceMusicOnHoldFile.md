---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skypeforbusiness/set-cscallparkservicemusiconholdfile
schema: 2.0.0
title: Set-CsCallParkServiceMusicOnHoldFile
---

# Set-CsCallParkServiceMusicOnHoldFile

## SYNOPSIS
Changes the audio file that will be played to callers who are on hold in a parked call.
This cmdlet was introduced in Lync Server 2010.


## SYNTAX

```
Set-CsCallParkServiceMusicOnHoldFile [-Service] <String> -Content <Byte[]> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Call parking is a service that allows a user to "park" an incoming phone call.
Parking a call transfers it to a number in a specified range and immediately places it on hold.
Based on configuration settings for the Call Park service, music on hold can be played to the caller while the call is parked.
Use this cmdlet to change the audio file (music on hold) that is played to a parked caller who is on hold.

Music on hold is played only if the EnableMusicOnHold property of the Call Park service has been set to True.
You can check this property by calling the `Get-CsCpsConfiguration` cmdlet.
You can set the property either when the Call Park configuration is created with the `New-CsCpsConfiguration` cmdlet or after the Call Park configuration exists by calling the `Set-CsCpsConfiguration` cmdlet.
This property is True by default.

Skype for Business Server ships with a default Call Park service music on hold file.
If you don't assign an audio file, the default file will be used.

Audio files must be in the following format: Windows Media Audio 9, 44 kHz, 16 bits, Mono, CBR, or 32 kbps.


## EXAMPLES

### Example 1
```
$a = [System.IO.File]::ReadAllBytes('C:\MoHFiles\soothingmusic.wma')

Set-CsCallParkServiceMusicOnHoldFile -Service ApplicationServer:pool0.litwareinc.com -Content $a
```

This example sets the file SoothingMusic.wma to be the audio file that is played to callers whose calls are parked.
The first line of this example uses the `[System.IO.File]::ReadAllBytes` command to read the contents of a file in byte format and assign them, in this case, to the variable $a.

Line 2 in this example is where we actually assign the audio file.
We call the `Set-CsCallParkServiceMusicOnHoldFile` cmdlet and specify the service ID where the Call Park service is running.
We then pass the audio file contents that we read into variable $a to the Content parameter.
(Remember that these contents must be in byte format.)


## PARAMETERS

### -Content

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

The contents of the audio file in byte format.

A valid value for this parameter requires you to read the file to a byte-encoded object using the following syntax: `([System.IO.File]::ReadAllBytes('<Path>\<FileName>'))`. You can use this command as the parameter value, or you can write the output to a variable (`$data = [System.IO.File]::ReadAllBytes('<Path>\<FileName>')`) and use the variable as the parameter value (`$data`).

```yaml
Type: Byte[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -Service

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

The ID of the service where the Call Park service resides; for example, ApplicationServer:pool0.litwareinc.com.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Sysetm.Byte[]
Accepts pipelined input of a byte array containing the music on hold file.

## OUTPUTS

### None
This cmdlet does not return a value.

## NOTES

## RELATED LINKS

[New-CsCpsConfiguration](New-CsCpsConfiguration.md)

[Remove-CsCpsConfiguration](Remove-CsCpsConfiguration.md)

[Set-CsCpsConfiguration](Set-CsCpsConfiguration.md)

[Get-CsCpsConfiguration](Get-CsCpsConfiguration.md)
