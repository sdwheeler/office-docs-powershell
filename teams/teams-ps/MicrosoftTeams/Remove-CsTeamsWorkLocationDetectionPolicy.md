---
author: artemiykozlov
external help file: Microsoft.Teams.Policy.Administration.Cmdlets.Core.dll-Help.xml
Locale: en-US
manager: prashibadkur
Module Name: MicrosoftTeams
ms.author: arkozlov
online version: https://learn.microsoft.com/powershell/module/microsoftteams/remove-csteamsworklocationdetectionpolicy
schema: 2.0.0
title: Remove-CsTeamsWorkLocationDetectionPolicy
---

# Remove-CsTeamsWorkLocationDetectionPolicy

## SYNOPSIS
This cmdlet is used to delete an instance of TeamsWorkLocationDetectionPolicy.

## SYNTAX

```
Remove-CsTeamsWorkLocationDetectionPolicy [-Identity] <String> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Deletes an instance of TeamsWorkLocationDetectionPolicy. The `Identity` parameter accepts the identity of the policy instance to delete.

## EXAMPLES

## EXAMPLES

### Example 1
```powershell
PS C:\>Remove-CsTeamsWorkLocationDetectionPolicy -Identity wld-policy
```

Deletes a given policy instance with the Identity wld-policy.

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

### -Force
Suppresses the display of any non-fatal error message that might arise when running the command.

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
Name of the new policy instance to be created.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS
[Get-CsTeamsWorkLocationDetectionPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/get-csteamsworklocationdetectionpolicy)

[New-CsTeamsWorkLocationDetectionPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/new-csteamsworklocationdetectionpolicy)

[Set-CsTeamsWorkLocationDetectionPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/set-csteamsworklocationdetectionpolicy)

[Grant-CsTeamsWorkLocationDetectionPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/grant-csteamsworklocationdetectionpolicy)
