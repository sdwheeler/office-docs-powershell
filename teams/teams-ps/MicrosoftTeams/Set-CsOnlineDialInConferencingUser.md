---
applicable: Microsoft Teams
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml
Locale: en-US
Module Name: MicrosoftTeams
online version: https://learn.microsoft.com/powershell/module/microsoftteams/set-csonlinedialinconferencinguser
schema: 2.0.0
title: Set-CsOnlineDialInConferencingUser
---

# Set-CsOnlineDialInConferencingUser

## SYNOPSIS

Use the `Set-CsOnlineDialInConferencingUser` cmdlet to modify the properties of a user that has been enabled for Microsoft's audio conferencing service.

## SYNTAX

### TenantIdParams (Default)
```
Set-CsOnlineDialInConferencingUser [-Identity] <UserIdParameter> [-BridgeId <Guid>]
 [-BridgeName <String>] [-Tenant <Guid>] [-ServiceNumber <String>] [-TollFreeServiceNumber <String>] [-AllowPSTNOnlyMeetings <Boolean>] [-Force]
 [-ResetLeaderPin] [-AllowTollFreeDialIn <Boolean>] [-SendEmailToAddress <String>]
 [-SendEmailFromAddress <String>] [-SendEmailFromDisplayName <String>] [-SendEmail] [-DomainController <Fqdn>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TenantDomainParams
```
Set-CsOnlineDialInConferencingUser [-Identity] <UserIdParameter> [-BridgeId <Guid>]
 [-BridgeName <String>] [-TenantDomain <String>] [-ServiceNumber <String>] [-TollFreeServiceNumber <String>] [-AllowPSTNOnlyMeetings <Boolean>] [-Force]
 [-ResetLeaderPin] [-AllowTollFreeDialIn <Boolean>] [-SendEmailToAddress <String>]
 [-SendEmailFromAddress <String>] [-SendEmailFromDisplayName <String>] [-SendEmail] [-DomainController <Fqdn>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The `Set-CsOnlineDialInConferencingUser` cmdlet is used to modify properties for a Microsoft audio conferencing user.
This cmdlet will not work for users with third-party conferencing providers.
The cmdlet will verify that the correct license is assigned to the user.

> [!NOTE]
> The AllowPSTNOnlyMeetings, ResetConferenceId, and ConferenceId parameters will be deprecated on Jan 31, 2022. To allow Teams meeting participants joining via the PSTN to bypass the lobby, use the AllowPSTNUsersToBypassLobby of the [Set-CsTeamsMeetingPolicy cmdlet](https://learn.microsoft.com/powershell/module/microsoftteams/set-csteamsmeetingpolicy). The capabilities associated with the ResetConferenceId and ConferenceId parameters are no longer supported.

## EXAMPLES

### Example 1
```
Set-CsOnlineDialInConferencingUser -Identity "Ken Meyers" -ResetLeaderPin -ServiceNumber 14255037265
```

This example shows how to reset the meeting leader's PIN and set the audio conferencing provider default meeting phone number.

### Example 2
```
Set-CsOnlineDialInConferencingUser -Identity "Ken Meyers" -BridgeName "Conference Bridge"
```

This example sets a user's conference bridge assignment.

## PARAMETERS

### -AllowPSTNOnlyMeetings

> Applicable: Microsoft Teams

If true, non-authenticated users can start meetings.
If false, non-authenticated callers wait in the lobby until an authenticated user joins, thereby starting the meeting.
An authenticated user is a user who joins the meeting using a Skype for Business client, or the organizer that joined the meeting via dial-in conferencing and was authenticated by a PIN number.
The default is false.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowTollFreeDialIn

> Applicable: Microsoft Teams

If toll-free numbers are available in your Microsoft Audio Conferencing bridge, this parameter controls if they can be used to join the meetings of a given user. This setting can ONLY be managed using the TeamsAudioConferencingPolicy. By default, AllowTollFreeDialin is always set to True.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
The parameter is used to run commands as background jobs.
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

### -BridgeId

> Applicable: Microsoft Teams

Specifies the globally-unique identifier (GUID) for the audio conferencing bridge.

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

### -BridgeName

> Applicable: Microsoft Teams

Specifies the name of the audio conferencing bridge.

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

### -Confirm

> Applicable: Microsoft Teams

The Confirm switch causes the command to pause processing and requires confirmation to proceed.

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

Fully qualified domain name (FQDN): `-DomainController atl-cs-001.Contoso.com`

Computer name: `-DomainController atl-cs-001`

This parameter is reserved for internal Microsoft use.

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

Specifies the Identity of the user account to be to be modified.
A user identity can be specified by using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer) and 4) the user's Active Directory display name (for example, Ken Myer).
You can also reference a user account by using the user's Active Directory distinguished name.

```yaml
Type: UserIdParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResetLeaderPin

> Applicable: Microsoft Teams

Specifies whether to reset the meeting organizer or leaders PIN for meetings.

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

### -SendEmail

> Applicable: Microsoft Teams

Send an email to the user containing their Audio Conference information.

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

### -SendEmailFromAddress

> Applicable: Microsoft Teams

You can specify the From Address to send the email that contains the Audio Conference information. This parameter must be used together with -SendEmailFromDisplayName and -SendEmail.

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

### -SendEmailFromDisplayName

> Applicable: Microsoft Teams

You can specify the Display Name to send the email that contains the Audio Conference information. This parameter must be used together with -SendEmailFromAddress and -SendEmail.

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

### -SendEmailToAddress

> Applicable: Microsoft Teams

You can specify the To Address to send the email that contains the Audio Conference information. This parameter must be used together with -SendEmail.

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

### -ServiceNumber

> Applicable: Microsoft Teams

Specifies the default service number for the user.
The default number is used in meeting invitations.
The cmdlet will verify that the service number is assigned to the user's current conference bridge, or the one the user is being assigned to.

The service number can be specified in the following formats: E.164 number, +\<E.164 number\> and tel:\<E.164 number\>.

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

Specifies the globally unique identifier (GUID) of your Skype for Business Online tenant account.
For example: `-Tenant "38aad667-af54-4397-aaa7-e94c79ec2308"`.
You can find your tenant ID by running this command: `Get-CsTenant | Select-Object DisplayName, TenantID`

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

### -TenantDomain

> Applicable: Microsoft Teams

Specifies the domain name for the tenant or organization.

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

### -TollFreeServiceNumber

> Applicable: Microsoft Teams

Specifies a toll-free phone number to be used by the user. This number is then used in meeting invitations. The toll-free number can be specified in the following formats: E.164 number, +\<E.164 number\> and tel:\<E.164 number\>.

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

> Applicable: Microsoft Teams

The WhatIf parameter is not implemented for this cmdlet.

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

[Get-CsTeamsAudioConferencingPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/get-csteamsaudioconferencingpolicy)

[New-CsTeamsAudioConferencingPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/new-csteamsaudioconferencingpolicy)
