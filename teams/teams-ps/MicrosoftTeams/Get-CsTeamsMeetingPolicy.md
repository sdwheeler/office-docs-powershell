---
applicable: Microsoft Teams
author: tomkau
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml
Locale: en-US
manager: bulenteg
Module Name: MicrosoftTeams
ms.author: tomkau
ms.reviewer: williamlooney
online version: https://learn.microsoft.com/powershell/module/microsoftteams/get-csteamsmeetingpolicy
schema: 2.0.0
title: Get-CsTeamsMeetingPolicy
---

# Get-CsTeamsMeetingPolicy

## SYNOPSIS

The CsTeamsMeetingPolicy cmdlets enable administrators to control the type of meetings that users can create or the features that they can access while in a meeting. It also helps determine how meetings deal with anonymous or external users.

## SYNTAX

### Identity (Default)
```
Get-CsTeamsMeetingPolicy [-Tenant <Guid>] [[-Identity] <XdsIdentity>] [-LocalStore] [<CommonParameters>]
```

### Filter
```
Get-CsTeamsMeetingPolicy [-Tenant <Guid>] [-Filter <String>] [-LocalStore] [<CommonParameters>]
```

## DESCRIPTION
The CsTeamsMeetingPolicy cmdlets enable administrators to control the type of meetings that users can create or the features that they can access while in a meeting. It also helps determine how meetings deal with anonymous or external users

Teams Meeting policies can be configured at the global and per-user scopes.
The Get-CsTeamsMeetingPolicy cmdlet enables you to return information about all the meeting policies that have been configured for use in your organization.

## EXAMPLES

### Example 1
```powershell
Get-CsTeamsMeetingPolicy
```

In Example 1, Get-CsTeamsMeetingPolicy is called without any additional parameters; this returns a collection of all the teams meeting policies configured for use in your organization.

### Example 2
```powershell
Get-CsTeamsMeetingPolicy -Identity SalesPolicy
```

In Example 2, Get-CsTeamsMeetingPolicy is used to return the per-user meeting policy that has an Identity SalesPolicy.
Because identities are unique, this command will never return more than one item.

### Example 3
```powershell
Get-CsTeamsMeetingPolicy | Where-Object {$_.AllowMeetNow -eq $True}
```

The preceding command returns a collection of all the meeting policies where the AllowMeetNow property is True.
To do this, Get-CsTeamsMeetingPolicy is first called without any parameters in order to return a collection of all the policies configured for use in the organization.
This collection is then piped to the Where-Object cmdlet, which selects only those policies where the AllowMeetNow property is equal to True.

### Example 4
```powershell
Get-CsTeamsMeetingPolicy -Identity Global | fl NewMeetingRecordingExpirationDays
```

```Output
NewMeetingRecordingExpirationDays : 60
```

The above command returns expiration date setting currently applied on TMR. For more details, see:
[Auto-expiration of Teams meeting recordings](https://learn.microsoft.com/microsoftteams/cloud-recording#auto-expiration-of-teams-meeting-recordings).

## PARAMETERS

### -Filter
Enables you to use wildcard characters when indicating the policy (or policies) to be returned.

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
Unique identifier of the policy to be returned. To refer to the global policy, use this syntax: -Identity global. To refer to a per-user policy, use syntax similar to this: -Identity SalesDepartmentPolicy.
If this parameter is omitted, then all the meeting policies configured for use in your organization will be returned.

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
