---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: tomkau
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: bulenteg
Module Name: SkypeForBusiness
ms.author: tomkau
ms.reviewer: rogupta
online version: https://learn.microsoft.com/powershell/module/skypeforbusiness/set-csprivacyconfiguration
schema: 2.0.0
title: Set-CsPrivacyConfiguration
---

# Set-CsPrivacyConfiguration

## SYNOPSIS
Modifies an existing set of privacy configuration settings.
Privacy configuration settings help determine how much information users make available to other users.
This cmdlet was introduced in Lync Server 2010.

## SYNTAX

### Identity (Default)
```
Set-CsPrivacyConfiguration [-EnablePrivacyMode <Boolean>]
 [-AutoInitiateContacts <Boolean>] [-PublishLocationDataDefault <Boolean>]
 [-DisplayPublishedPhotoDefault <Boolean>] [[-Identity] <XdsIdentity>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Instance
```
Set-CsPrivacyConfiguration [-EnablePrivacyMode <Boolean>]
 [-AutoInitiateContacts <Boolean>] [-PublishLocationDataDefault <Boolean>]
 [-DisplayPublishedPhotoDefault <Boolean>] [-Instance <PSObject>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Skype for Business Server gives users the opportunity to share a wealth of presence information with other people: they can publish a photograph of themselves; they can provide detailed location information; they can have presence information automatically made available to everyone in the organization (as opposed to having this information available only to people on their Contacts list).

Some users will welcome the opportunity to make this information available to their colleagues; other users might be more reluctant to share this data.
(For example, many people might be hesitant about having their photo included in their presence data.) As a general rule, users have control over what information they will (or will not) share; for example, users can select or clear a check box in order to control whether or not their location information is shared with others.
In addition, the privacy configuration cmdlets enable administrators to manage privacy settings for their users.
In some cases, administrators can enable or disable settings; for example, if the property AutoInitiateContacts is set to True, then team members will automatically be added to each user's Contacts list; if set to False, team members will not be automatically be added to each user's Contacts list.

In other cases, administrators can configure the default values in Skype for Business while still giving users the right to change these values.
For example, by default location data is published for users, although users do have the right to stop location publication.
By setting the PublishLocationDataByDefault property to False, administrators can change this behavior: in that case, location data will not be published by default, although users will still have the right to publish this data if they choose.

Privacy configuration settings can be applied at the global scope, the site scope, and at the service scope (albeit only for the User Server service).
The `Set-CsPrivacyConfiguration` cmdlet enables you to modify any of the privacy configuration settings currently in use in your organization.


## EXAMPLES

### Example 1
```
Set-CsPrivacyConfiguration -Identity site:Redmond -EnablePrivacyMode $False -AutoInitiateContacts $True -PublishLocationDataDefault $True -DisplayPublishedPhotoDefault $True
```

The command shown in Example 1 modifies three property values for the privacy configuration settings with the Identity site:Redmond.
The three property values modified are AutoInitiateContacts, PublishLocationDataDefault and DisplayPublishedPhotoDefault.


### Example 2
```
Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
```

Example 2 enables privacy mode for all the privacy configuration settings currently in use in the organization.
To do this, the command first calls the `Get-CsPrivacyConfiguration` cmdlet without any parameters; this returns the complete collection of privacy settings.
This collection is then piped to the `Set-CsPrivacyConfiguration` cmdlet, which takes each item in the collection and sets the EnablePrivacyMode property to True.


### Example 3
```
Get-CsPrivacyConfiguration | Where-Object {$_.EnablePrivacyMode -eq $False} | Set-CsPrivacyConfiguration -AutoInitiateContacts $True -PublishLocationDataDefault $True -DisplayPublishedPhotoDefault $True
```

In Example 3, modifications are made to all the privacy configuration settings that are not currently using privacy mode.
To carry out this task, the `Get-CsPrivacyConfiguration` cmdlet is first used in order to return a collection of all the privacy configuration settings.
This collection is piped to the `Where-Object` cmdlet, which selects only those settings where the EnablePrivacyMode property is equal to False.
The filtered collection is then piped to the `Set-CsPrivacyConfiguration` cmdlet, which assigns values to the AutoInitiateContacts, PublishLocationDataDefault, and DisplayPublishedPhotoDefault properties for each item in the collection.


## PARAMETERS

### -AutoInitiateContacts

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

If True, Skype for Business will automatically add your manager and your direct reports to your Contacts list.
The default value is True.


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

### -DisplayPublishedPhotoDefault

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

If True, the user's photo will automatically be published in Skype for Business.
If False, the user's photo will not be available unless he or she explicitly selects the option Let others see my photo.
The default value is True.


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

### -EnablePrivacyMode

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

If True, gives users the opportunity to enable the advanced privacy mode.
In advanced privacy mode, only people on your Contacts list will be allowed to view your presence information.
If False, your presence information will be available to anyone in your organization.
The default value is False.

For information about privacy mode in Microsoft Teams, see [User presence in Teams](/microsoftteams/presence-admins).

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

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

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

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Unique identifier for the privacy configuration settings to be modified.
To modify the global settings, use this syntax:

`-Identity global`

To modify settings configured at the site scope, use syntax similar to this:

`-Identity site:Redmond`

To modify settings at the service level, use syntax like this:

`-Identity service:Redmond-UserServices-1`

Note that privacy settings can only be applied to the User Server service.
An error will occur if you try to apply these settings to any other service.

If this parameter is not specified then the global settings will be updated when you call the `Set-CsPrivacyConfiguration` cmdlet.


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

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.


```yaml
Type: PSObject
Parameter Sets: Instance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PublishLocationDataDefault

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

If True, location data will automatically be published in Skype for Business.
If False, location data will not be available unless the user explicitly selects the option Show Contacts My Location.
The default value is True.


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

### -Confirm

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

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

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

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

### Microsoft.Rtc.Management.WritableConfig.Settings.UserServices.PrivacyConfiguration

The `Set-CsPrivacyConfiguration` cmdlet accepts pipelined input of the privacy configuration object.

## OUTPUTS

### None
The `Set-CsPrivacyConfiguration` cmdlet does not return any objects or values.
Instead, the cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.UserServices.PrivacyConfiguration object.

## NOTES

## RELATED LINKS

[Get-CsPrivacyConfiguration](Get-CsPrivacyConfiguration.md)

[New-CsPrivacyConfiguration](New-CsPrivacyConfiguration.md)

[Remove-CsPrivacyConfiguration](Remove-CsPrivacyConfiguration.md)
