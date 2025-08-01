---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Rgs.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skypeforbusiness/import-csrgsaudiofile
schema: 2.0.0
title: Import-CsRgsAudioFile
---

# Import-CsRgsAudioFile

## SYNOPSIS

Imports a new audio file for use with the Response Group application.
This cmdlet was introduced in Lync Server 2010.

## SYNTAX

```
Import-CsRgsAudioFile [-Identity] <RgsIdentity> -Content <Byte[]> -FileName <String> [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The Response Group application can use audio files (.WAV or .WMA formats only) in at least two different ways.
For one, the service can play music (or an announcement of some type) any time callers are placed on hold.
Alternatively, the Response Group application occasionally "talks" to callers; for example, with interactive voice response (IVR) the service might ask callers a question such as "Are you calling about an existing order?" You can have the service read these questions using text-to-speech technology or you can play an audio recording of an actual person asking the question.

Regardless of how you choose to use audio files, the files themselves must be imported into the Response Group application by using the Import-CsRgsAudioFile cmdlet.
Note that you must run Import-CsRgsAudioFile each time you want to use an audio file, even if that file is already being used elsewhere in the Response Group application.
For example, suppose Workflow A uses a given audio file as its custom music on hold file and you now want to use that same audio file as the custom music on hold for Workflow B.
Even though the audio file is already used by the Response Group application you will still need to import the file in order to use it with Workflow B.

## EXAMPLES

### EXAMPLE 1
```

$x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" -FileName "WhileYouWait.wav" -Content ([System.IO.File]::ReadAllBytes('C:\Media\WhileYouWait.wav'))

$y = Get-CsRgsWorkflow -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" -Name "Help Desk Workflow"

$y.CustomMusicOnHoldFile = $x

Set-CsRgsWorkflow $y
```

The commands shown in Example 1 import an audio file (C:\Media\WhileYouWait.wav) and then assign that file to the CustomMusicOnHold property of a workflow.
To perform this task, the first command uses Import-CsRgsAudioFile to import the audio file to the Response Group application found on ApplicationServer:atl-cs-001.litwareinc.com.
In addition to the Identity parameter (which specifies the service location) the FileName parameter is used to specify the file name of the file being imported.

At the same time, the Content parameter is used to import the audio file.
File importing is carried out by calling the `[System.IO.File]::ReadAllBytes` command with the path to the file being imported.
The imported file is then stored in a variable named $x.

In the second command, Get-CsRgsWorkflow is used to create an object reference ($y) to the workflow Help Desk Workflow.
After this object reference has been created, command 3 sets the value of the CustomMusicOnHoldFile property to $x, the variable containing the imported audio file.
Finally, the last command in the example uses Set-CsRgsWorkflow to write these changes to the actual workflow Help Desk Workflow.
If you do not call Set-CsRgsWorkflow, your modifications will exist only in memory, and will disappear as soon as you close Windows PowerShell or delete the variables $x or $y.

## PARAMETERS

### -Content

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Actual content of the audio file being imported.

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

### -FileName

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

File name for the audio file being imported.
For example, the file name for the file C:\Media\Welcome.wav is this: Welcome.wav.

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

### -Force

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

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

### -Identity

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Identity of the service where the audio file is to be imported.
(This must be the same service that hosts the Response Group application.) For example: `-Identity "service:ApplicationServer:atl-cs-001.litwareinc.com".`

```yaml
Type: RgsIdentity
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
This cmdlet supports the common parameters: `-Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).`

## INPUTS

### None
Import-CsRgsAudioFile does not accept pipelined input.

## OUTPUTS

### Microsoft.Rtc.Rgs.Management.WritableSettings.AudioFile
Creates new instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.AudioFile object.

## NOTES

## RELATED LINKS

[New-CsRgsWorkflow](New-CsRgsWorkflow.md)

[Set-CsRgsWorkflow](Set-CsRgsWorkflow.md)
