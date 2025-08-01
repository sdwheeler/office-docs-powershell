---
applicable: Microsoft Teams
author: serdarsoysal
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml
Locale: en-US
manager: bulenteg
Module Name: MicrosoftTeams
ms.author: serdars
online version: https://learn.microsoft.com/powershell/module/microsoftteams/get-csonlinevoiceroute
schema: 2.0.0
title: Get-CsOnlineVoiceRoute
---

# Get-CsOnlineVoiceRoute

## SYNOPSIS
Returns information about the online voice routes configured for use in your tenant.

## SYNTAX

### Identity (Default)
```
Get-CsOnlineVoiceRoute [[-Identity] <string>] [<CommonParameters>]
```

### Filter
```
Get-CsOnlineVoiceRoute [-Filter <string>] [<CommonParameters>]
```

## DESCRIPTION
Use this cmdlet to retrieve one or more existing online voice routes in your tenant. Online voice routes contain instructions that tell Skype for Business Online how to route calls from Office 365 users to phone numbers on the public switched telephone network (PSTN) or a private branch exchange (PBX).

This cmdlet can be used to retrieve voice route information such as which online PSTN gateways the route is associated with (if any), which online PSTN usages are associated with the route, the pattern (in the form of a regular expression) that identifies the phone numbers to which the route applies, and caller ID settings. The PSTN usage associates the voice route to an online voice policy.

This cmdlet is used when configuring Microsoft Phone System Direct Routing.

## EXAMPLES

### Example 1
```
PS C:\> Get-CsOnlineVoiceRoute
```

Retrieves the properties for all voice routes defined within the tenant.

### Example 2
```
PS C:\> Get-CsOnlineVoiceRoute -Identity Route1
```

Retrieves the properties for the Route1 voice route.

### Example 3
```
PS C:\> Get-CsOnlineVoiceRoute -Filter *test*
```

This command displays voice route settings where the Identity contains the string "test" anywhere within the value. To find the string test only at the end of the Identity, use the value \*test. Similarly, to find the string test only if it occurs at the beginning of the Identity, specify the value test\*.

### Example 4
```
PS C:\> Get-CsOnlineVoiceRoute | Where-Object {$_.OnlinePstnGatewayList.Count -eq 0}
```

This command retrieves all voice routes that have not had any PSTN gateways assigned. First all voice routes are retrieved using the Get-CsOnlineVoiceRoute cmdlet. These voice routes are then piped to the Where-Object cmdlet. The Where-Object cmdlet narrows down the results of the Get operation. In this case we look at each voice route (that's what the $_ represents) and check the Count property of the PstnGatewayList property. If the count of PSTN gateways is 0, the list is empty and no gateways have been defined for the route.

## PARAMETERS

### -Filter
This parameter filters the results of the Get operation based on the wildcard value passed to this parameter.

```yaml
Type: String
Parameter Sets: Filter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
A string that uniquely identifies the voice route. If no identity is provided, all voice routes for the organization are returned.

```yaml
Type: String
Parameter Sets: Identity
Aliases:

Required: False
Position: 1
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
[New-CsOnlineVoiceRoute](https://learn.microsoft.com/powershell/module/microsoftteams/new-csonlinevoiceroute)

[Set-CsOnlineVoiceRoute](https://learn.microsoft.com/powershell/module/microsoftteams/set-csonlinevoiceroute)

[Remove-CsOnlineVoiceRoute](https://learn.microsoft.com/powershell/module/microsoftteams/remove-csonlinevoiceroute)
