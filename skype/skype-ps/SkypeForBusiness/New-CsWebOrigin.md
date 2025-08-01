---
applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skypeforbusiness/new-csweborigin
schema: 2.0.0
title: New-CsWebOrigin
---

# New-CsWebOrigin

## SYNOPSIS
Creates a new domain object that can be added to the collection of domains allowed to send cross-domain scripting requests to the Skype for Business Server deployment.

## SYNTAX

```
New-CsWebOrigin -Url <String> [<CommonParameters>]
```

## DESCRIPTION
The `New-CsWebOrigin` cmdlet is used to specify domains that are authorized to host web applications which, in turn, are permitted to send cross-domain scripting requests to your deployment of Skype for Business Server.
This cmdlet is primarily used for applications created on top of the Unified Communications Web API.

To add a domain to a collection of web service configuration settings, you must first create a domain object by using the `New-CsWebOrigin` cmdlet.
This domain object, which will exist only in memory, must be stored in a variable.
After the object has been created, it can then be added to a collection of web service configuration settings by using either the `New-CsWebServiceConfiguration` cmdlet or the `Set-CsWebServiceConfiguration` cmdlet.

Skype for Business Server Control Panel: The functions carried out by the `New-CsWebOrigin` cmdlet are not available in the Skype for Business Server Control Panel.

## EXAMPLES

### Example 1
```
$x = New-CsWebOrigin -Url "http://fabrikam.com"

New-CsWebServiceConfiguration -Identity "site:Redmond" - CrossDomainAuthorizationList $x
```

The commands shown in Example 1 add the domain http://fabrikam.com to a new collection of web service configuration settings being created for the Redmond site.
To do this, the first command in the example uses the `New-CsWebOrigin` cmdlet to create a domain object for fabrikam.com.
The resulting domain object is stored in a variable named $x.

The second command in the example uses the `New-CsWebServiceConfiguration` cmdlet to create the web service configuration settings for the Redmond site.
The syntax "`- CrossDomainAuthorizationList $x`" adds http://fabrikam.com to the collection of domains authorized for cross-domain scripting.


### Example 2
```
$x = New-CsWebOrigin -Url "http://fabrikam.com"

Set-CsWebServiceConfiguration -Identity "site:Redmond" - CrossDomainAuthorizationList @{Add=$x}
```

The commands shown in Example 2 add the domain http://fabrikam.com to an existing collection of web service configuration settings.
To carry out this task, the first command in the example uses the `New-CsWebOrigin` cmdlet to create a domain object for fabrikam.com.
The resulting domain object is stored in a variable named $x.

The second command in the example uses the `Set-CsWebServiceConfiguration` cmdlet to add http://fabrikam.com to the web service configuration settings applied to the Redmond site.
The syntax `@{Add=$x}` adds the domain to any domains already in the collection of domains authorized for cross-domain scripting.
To replace the existing collection with just http://fabrikam.com use the syntax `@{Replace=$x}`.


## PARAMETERS

### -Url

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

URL of the domain authorized to send cross-domain scripting requests.
URLs must be prefaced using either the http: or the https: prefix.
For example:

`-Url "http://contoso.com"`

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
The `New-CsWebOrigin` cmdlet does not accept pipelined input.

## OUTPUTS

### Microsoft.Rtc.Management.WritableConfig.Settings.Web.Origin
The `New-CsWebOrigin` cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Web.Origin object.

## NOTES

## RELATED LINKS

[New-CsWebServiceConfiguration](New-CsWebServiceConfiguration.md)

[Set-CsWebServiceConfiguration](Set-CsWebServiceConfiguration.md)
