---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skypeforbusiness/remove-csdeviceupdateconfiguration
schema: 2.0.0
title: Remove-CsDeviceUpdateConfiguration
---

# Remove-CsDeviceUpdateConfiguration

## SYNOPSIS
Removes the specified device update configuration settings.
These settings help manage the Device Update Web service, a Skype for Business Server component that enables administrators to distribute firmware updates to telephones and other devices running Skype for Business Phone Edition.
This cmdlet was introduced in Lync Server 2010.


## SYNTAX

```
Remove-CsDeviceUpdateConfiguration [-Identity] <XdsIdentity> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Device Update Web service provides a way for administrators to distribute firmware updates to devices that run Skype for Business Phone Edition.
Periodically, administrators upload a set of device update rules to Skype for Business Server.
After those rules have been tested and approved, they can then be applied to the appropriate devices as those devices connect to the system.
Devices check for updates when they are first powered on, then check again when a user logs on.
After that, devices check for updates every 24 hours.

Skype for Business Server uses device update configuration settings to manage the Device Update Web service; these configuration settings can be applied at the global scope or at the site scope.
By default, settings are found only at the global scope; however, you can use the `New-CsDeviceUpdateConfiguration` cmdlet to assign customized settings at the site scope as well.

In addition, you can use the `Remove-CsDeviceUpdateConfiguration` cmdlet to delete settings that have been assigned at the site scope.
When you run this cmdlet against a site, the device update configuration settings assigned to that site are removed.
You can also run the `Remove-CsDeviceUpdateConfiguration` cmdlet against the global settings.
In that case, however, the global settings will not be removed; that's because you cannot remove the global device update configuration settings.
Instead, the global properties will be reset to their default values.
For example, suppose you have changed the global property MaxLogCacheLimit to 1,024,000 bytes.
If you run the `Remove-CsDeviceUpdateConfiguration` cmdlet against the global settings, the global settings will not be removed; however, any properties that have been modified will be reset to their default values.
That means that MaxLogCacheLimit will be reset to 512,000 bytes.


## EXAMPLES

### Example 1
```
Remove-CsDeviceUpdateConfiguration -Identity global
```

In Example 1, the `Remove-CsDeviceUpdateConfiguration` cmdlet is used to "remove" the global device update configuration settings.
Because the global settings cannot actually be removed, the command will not delete anything; however, all the properties in the global device update configuration settings will be reset to their default values.


### Example 2
```
Remove-CsDeviceUpdateConfiguration -Identity site:Redmond
```

The command shown in Example 2 removes the device update configuration settings with the Identity site:Redmond.
Because these settings were configured at the site scope, they will be deleted and the Redmond site will no longer have its own set of device update configuration settings.


### Example 3
```
Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration
```

In Example 3, all the device update configuration settings that have been configured at the site scope are removed.
To do this, the `Get-CsDeviceUpdateConfiguration` cmdlet and the Filter parameter are used to return all the settings that have an Identity that begins with the string value "site:"; by definition, these will all be settings that were configured at the site scope.
That collection is then piped to the `Remove-CsDeviceUpdateConfiguration` cmdlet, which removes each of the items in the collection.


### Example 4
```
Get-CsDeviceUpdateConfiguration | Where-Object {$_.MaxLogFileSize -lt 1024000} | Remove-CsDeviceUpdateConfiguration
```

In Example 4, all the device update configuration settings that have a MaxLogFileSize property greater than 1024000 bytes are deleted.
To accomplish this task, the `Get-CsDeviceUpdateConfiguration` cmdlet is first called in order to return a collection of all the device update configuration settings.
This collection is piped to the `Where-Object` cmdlet, which selects only those configuration settings where the MaxLogFileSize property is greater than 1024000 bytes.
That filtered collection is then piped to the `Remove-CsDeviceUpdateConfiguration` cmdlet, which deletes each item in the collection.


## PARAMETERS

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

Indicates the Identity of the device update configuration settings to be removed.
To refer to the global settings, use this syntax: `-Identity global`.
To refer to site settings, use syntax similar to this: `-Identity site:Redmond`.
Note that you cannot use wildcards when specifying an Identity.

```yaml
Type: XdsIdentity
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Rtc.Management.WritableConfig.Settings.DeviceUpdate.DeviceUpdateConfiguration

The `Remove-CsDeviceUpdateConfiguration` cmdlet accepts pipelined instances of the device update configuration object.

## OUTPUTS

### None
Instead, the `Remove-CsDeviceUpdateConfiguration` cmdlet deletes instances of the Microsoft.Rtc.Management.WritableConfig.Settings.DeviceUpdate.DeviceUpdateConfiguration object.

## NOTES

## RELATED LINKS

[Get-CsDeviceUpdateConfiguration](Get-CsDeviceUpdateConfiguration.md)

[New-CsDeviceUpdateConfiguration](New-CsDeviceUpdateConfiguration.md)

[Set-CsDeviceUpdateConfiguration](Set-CsDeviceUpdateConfiguration.md)
