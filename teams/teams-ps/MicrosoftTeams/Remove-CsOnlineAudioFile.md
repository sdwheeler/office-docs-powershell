---
applicable: Microsoft Teams
author: serdarsoysal
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml
Locale: en-US
Module Name: MicrosoftTeams
ms.author: serdars
online version: https://learn.microsoft.com/powershell/module/microsoftteams/remove-csonlineaudiofile
schema: 2.0.0
title: Remove-CsOnlineAudioFile
---

# Remove-CsOnlineAudioFile

## SYNOPSIS
Marks an audio file of application type TenantGlobal for deletion and later removal (within 24 hours).

## SYNTAX

```
Remove-CsOnlineAudioFile -Identity <String> [-HttpPipelinePrepend <SendAsyncStep[]>] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet marks an audio file of application type TenantGlobal for deletion and later removal.

## EXAMPLES

### Example 1
```powershell
Remove-CsOnlineAudioFile -Identity dcfcc31daa9246f29d94d0a715ef877e
```
This cmdlet marks the audio file with Id dcfcc31daa9246f29d94d0a715ef877e for deletion and later removal.

## PARAMETERS

### -HttpPipelinePrepend
{{ Fill HttpPipelinePrepend Description }}

```yaml
Type: Microsoft.Teams.ConfigAPI.Cmdlets.Generated.Runtime.SendAsyncStep[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
The Id of the specific audio file that you would like to mark for deletion.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES
Please note that using this cmdlet on other application types like OrgAutoAttendant and HuntGroup does not mark the audio file for deletion. These kinds of audio files will automatically be deleted, when

the corresponding Auto Attendant or Call Queue is deleted.

The cmdlet is available in Teams PS module 2.4.0-preview or later.

## RELATED LINKS

[Export-CsOnlineAudioFile](https://learn.microsoft.com/powershell/module/microsoftteams/export-csonlineaudiofile)

[Get-CsOnlineAudioFile](https://learn.microsoft.com/powershell/module/microsoftteams/get-csonlineaudiofile)

[Import-CsOnlineAudioFile](https://learn.microsoft.com/powershell/module/microsoftteams/import-csonlineaudiofile)
