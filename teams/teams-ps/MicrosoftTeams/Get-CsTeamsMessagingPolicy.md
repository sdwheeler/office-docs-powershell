---
applicable: Microsoft Teams
author: tomkau
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml
Locale: en-US
manager: bulenteg
Module Name: MicrosoftTeams
ms.author: tomkau
ms.reviewer: williamlooney
online version: https://learn.microsoft.com/powershell/module/microsoftteams/get-csteamsmessagingpolicy
schema: 2.0.0
title: Get-CsTeamsMessagingPolicy
---

# Get-CsTeamsMessagingPolicy

## SYNOPSIS
The CsTeamsMessagingPolicy cmdlets enable administrators to control if a user is enabled to exchange messages.

## SYNTAX

### Identity (Default)
```
Get-CsTeamsMessagingPolicy [-Tenant <Guid>] [[-Identity] <XdsIdentity>] [-LocalStore]
 [<CommonParameters>]
```

### Filter
```
Get-CsTeamsMessagingPolicy [-Tenant <Guid>] [-Filter <String>] [-LocalStore] [<CommonParameters>]
```

## DESCRIPTION
The CsTeamsMessagingPolicy cmdlets enable administrators to control if a user is enabled to exchange messages. These also help determine the type of messages users can create and modify.  This cmdlet lets you retrieve messaging policies that are available for use within your organization.

## EXAMPLES

### Example 1
```
powershell
PS C:\> Get-CsTeamsMessagingPolicy
```

In this example all teams messaging policies that have been configured in the organization will be returned.

## PARAMETERS

### -Filter
Enables you to use wildcard characters when specifying the policy (or policies) to be returned.

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
Unique identifier for the policy to be retrieved. To retrieve the global policy, use this syntax: -Identity global. To retrieve a per-user policy use syntax similar to this: -Identity StudentMessagingPolicy.

If this parameter is not included, the Get-CsTeamsMessagingPolicy cmdlet will return a collection of all the teams messaging policies configured for use in your organization.

Note that wildcards are not allowed when specifying an Identity. Use the Filter parameter if you need to use wildcards when specifying a messaging policy.

```yaml
Type: XdsIdentity
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalStore

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS
