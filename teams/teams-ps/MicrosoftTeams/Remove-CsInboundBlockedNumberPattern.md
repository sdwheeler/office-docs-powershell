---
applicable: Microsoft Teams
author: serdarsoysal
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml
Locale: en-US
manager: bulenteg
Module Name: MicrosoftTeams
ms.author: serdars
online version: https://learn.microsoft.com/powershell/module/microsoftteams/remove-csinboundblockednumberpattern
schema: 2.0.0
title: Remove-CsInboundBlockedNumberPattern
---

# Remove-CsInboundBlockedNumberPattern

## SYNOPSIS
Removes a blocked number pattern from the tenant list.

## SYNTAX

```
Remove-CsInboundBlockedNumberPattern [-Identity] <string> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet removes a blocked number pattern from the tenant list.

## EXAMPLES

### Example 1
```powershell
PS> Remove-CsInboundBlockedNumberPattern -Identity "BlockAutomatic"
```

This example removes a blocked number pattern identified as "BlockAutomatic".

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

### -Identity
A unique identifier specifying the blocked number pattern to be removed.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## OUTPUTS

## NOTES

## RELATED LINKS

[New-CsInboundBlockedNumberPattern](https://learn.microsoft.com/powershell/module/microsoftteams/new-csinboundblockednumberpattern)

[Set-CsInboundBlockedNumberPattern](https://learn.microsoft.com/powershell/module/microsoftteams/set-csinboundblockednumberpattern)

[Get-CsInboundBlockedNumberPattern](https://learn.microsoft.com/powershell/module/microsoftteams/get-csinboundblockednumberpattern)
