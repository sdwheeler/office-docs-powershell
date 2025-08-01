---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: tomkau
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: bulenteg
Module Name: SkypeForBusiness
ms.author: tomkau
ms.reviewer: rogupta
online version: https://learn.microsoft.com/powershell/module/skypeforbusiness/set-cspushnotificationconfiguration
schema: 2.0.0
title: Set-CsPushNotificationConfiguration
---

# Set-CsPushNotificationConfiguration

## SYNOPSIS
Modifies an existing collection of push notification configuration settings.
The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) provides a way to send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Skype for Business application on those devices is currently suspended or running in the background.
This cmdlet was introduced in the cumulative update for Lync Server 2010: November 2011.


## SYNTAX

### Identity (Default)
```
Set-CsPushNotificationConfiguration [-Tenant <Guid>] [-EnableApplePushNotificationService <Boolean>]
 [-EnableMicrosoftPushNotificationService <Boolean>] [[-Identity] <XdsIdentity>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Instance
```
Set-CsPushNotificationConfiguration [-Tenant <Guid>] [-EnableApplePushNotificationService <Boolean>]
 [-EnableMicrosoftPushNotificationService <Boolean>] [-Instance <PSObject>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The Apple Push Notification Service and the Microsoft Push Notification Service enable users running Skype for Business on their Apple iPhone or Windows Phone to receive notifications about Skype for Business Server events even when Skype for Business is suspended or running in the background.
For example, users can receive notice for events such as these:

- Invitations to a new instant messaging session or conference
- New instant messages
- New voice mail

Without the push notification service users would receive these notices only when Skype for Business was in the foreground and serving as the active application.

Administrators have the ability to enable or disable push notifications for iPhone users and/or Windows Phone users.
(By default, push notifications are disabled for both iPhone users and Windows Phone users.) Administrators can enable or disable push notifications at the global scope by using the `Set-CsPushNotificationConfiguration` cmdlet.
They can also create custom push notification settings at the site scope by using the `New-CsPushNotificationConfiguration` cmdlet.
These custom settings can also be modified by using the `Set-CsPushNotificationConfiguration` cmdlet.

With the push notification configuration settings there are only two property values for Administrators to manage: EnableApplePushNotificationService, which determines whether push notifications are sent to iPhone users and EnableMicrosoftPushNotificationService, which determines whether push notifications are sent to Windows Phone users.
Note that these property values do not have to be set to the same value.
For example, you could enable push notifications to Windows Phone users (by setting EnableMicrosoftPushNotificationService to True) yet, at the same, disable notifications to iPhone users by setting EnableApplePushNotificationService to False.


## EXAMPLES

### Example 1
```
Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False
```

The command shown in Example 1 disables push notifications from the Apple Push Notification Service for the Redmond site.


### Example 2
```
Get-CsPushNotificationConfiguration -Filter "site:*" | Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $False
```

Example 2 disables push notifications from the Apple Push Notification Service for all the sites currently hosting push notification settings.
To do this, the command first uses the `Get-CsPushNotificationConfiguration` cmdlet and the Filter parameter to return all the push notification settings configured at the site scope; the filter value "site:*" limits the returned settings to those that have an Identity that begins with the string value "site:".
That collection of settings is then piped to the `Set-CsPushNotificationConfiguration` cmdlet, which takes each item in the collection and sets the EnableApplePushNotificationService property to False.


### Example 3
```
Get-CsPushNotificationConfiguration | Where-Object {$_.EnableMicrosoftPushNotificationService -eq $False} | Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $False
```

Example 3 demonstrates how you can locate all the push notification settings where push notifications from the Microsoft Push Notification Service are disabled, and then disable push notifications from the Apple Push Notification Service for each of those settings as well.
To carry out this task, the command first uses the `Get-CsPushNotificationConfiguration` cmdlet to return a collection of all the push notification settings currently in use the organization.
This collection is then piped to the `Where-Object` cmdlet, which selects only those settings where the EnableMicrosoftPushNotificationService property is equal to (-eq) False.
That filtered collection is then piped to the `Set-CsPushNotificationConfiguration` cmdlet, which takes each item in the filtered collection and sets the EnableApplePushNotificationService property to False.


## PARAMETERS

### -EnableApplePushNotificationService

> Applicable: Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, iPhone users will receive push notifications from the Apple Push Notification Service.
When set to False, iPhone users will not receive these notifications.

The default value is False.


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

### -EnableMicrosoftPushNotificationService

> Applicable: Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, Windows Phone users will receive push notifications from the Microsoft Push Notification Service.
When set to False, Windows Phone users will not receive these notifications.

The default value is False.


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

### -Force

> Applicable: Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

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

> Applicable: Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Indicates the Identity of the push notification configuration settings to be modified.
To refer to the global settings, use this syntax:

`-Identity global`

To refer to site settings, use syntax similar to this:

`-Identity site:Redmond`

Note that you cannot use wildcards when specifying an Identity.


```yaml
Type: XdsIdentity
Parameter Sets: Identity
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Instance

> Applicable: Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Tenant

> Applicable: Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Globally unique identifier (GUID) of the Skype for Business Online tenant account for the push notification settings being modified.
For example:

`-Tenant "38aad667-af54-4397-aaa7-e94c79ec2308"`

You can return the tenant ID for each of your tenants by running this command:

`Get-CsTenant | Select-Object DisplayName, TenantID`

If you are using a remote session of Windows PowerShell and are connected only to Skype for Business Online you do not have to include the Tenant parameter.
Instead, the tenant ID will automatically be filled in for you based on your connection information.
The Tenant parameter is primarily for use in a hybrid deployment.


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

### -Confirm

> Applicable: Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

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

> Applicable: Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

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

### Microsoft.Rtc.Management.WriteableConfig.Settings.PushNotificationConfiguration.PushNotificationConfiguration
The `Set-CsPushNotificationConfiguration` cmdlet accepts pipelined instances of the PushNotificationConfiguration object.

## OUTPUTS

### None
Instead, the `Set-CsPushNotificationConfiguration` cmdlet modifies existing instances of the Microsoft.Rtc.Management.WriteableConfig.Settings.PushNotificationConfiguration.PushNotificationConfiguration object.

## NOTES

## RELATED LINKS
