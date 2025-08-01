---
applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skypeforbusiness/import-csuserdata
schema: 2.0.0
title: Import-CsUserData
---

# Import-CsUserData

## SYNOPSIS

Imports user data previously exported by using the Export-CsUserData cmdlet.
This cmdlet was introduced in Lync Server 2013.



## SYNTAX

### Identity
```
Import-CsUserData -FileName <String> -Identity <String> [-ConfDirectoryFilter <String>]
 [-DomainController <Fqdn>] [-Force] [-LegacyFormat] [-RoutingGroupFilter <String>] [-UserFilter <String>]
 [<CommonParameters>]
```

### PoolFqdn
```
Import-CsUserData -FileName <String> -PoolFqdn <Fqdn> [-ConfDirectoryFilter <String>]
 [-DomainController <Fqdn>] [-Force] [-LegacyFormat] [-RoutingGroupFilter <String>] [-UserFilter <String>]
 [<CommonParameters>]
```

## DESCRIPTION

The Import-CsUserData cmdlet is used to import previously-saved user data and/or conference directory data to Skype for Business Server.
Note that this data must have been exported by using the Export-CsUserData cmdlet.

To make sure changes happen after this cmdlet, FE services need to be stopped in all FE servers in the pool firstly then be restarted at the same time after executing Import-CsUserdata cmdlet.

Skype for Business Server Control Panel: The functions carried out by the Import-CsUserData cmdlet are not available in the Skype for Business Server Control Panel.



## EXAMPLES

### Example 1
```

Import-CsUserData -PoolFqdn "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"
```

The command shown in Example 1 imports user data from a file named C:\Logs\ExportedUserData.zip to the pool atl-cs-001.litwareinc.com.


## PARAMETERS

### -ConfDirectoryFilter

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

When specified, allows you to import conference directory information for the specified conference directory.
For example, to import data from the conference directory with the ID 13 use this syntax:

`-ConfDirectoryFilter 13`

You can return conference directory IDs by using this command:

`Get-CsConferenceDirectory`

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

### -DomainController

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Enables administrators to specify the FQDN of the domain controller to be used when running the Import-CsUserData cmdlet.
If not specified, the cmdlet will use the first available domain controller.



```yaml
Type: Fqdn
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileName

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Full path to the input file containing the exported user data.
For example:

`-InputFile "C:\Data\ExportedUsers.xml"`

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

### -Force

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

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

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Service Identity of the user database where the data should be imported.
For example:

`-Identity "UserDatabase:atl-sql-001.litwareinc.com"`

You cannot use both the Identity and the PoolFqdn parameters in the same command.

```yaml
Type: String
Parameter Sets: Identity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LegacyFormat

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Indicates that the data to be imported was exported from a previous version of Lync Server or Office Communications Server.

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

### -PoolFqdn

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Fully qualified domain name of the Registrar pool for the user data being imported.
For example:

`-PoolFqdn "atl-cs-001.litwareinc.com"`

```yaml
Type: Fqdn
Parameter Sets: PoolFqdn
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoutingGroupFilter

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Enables you to limit the imported data to users who belong to the same routing group.
Routing groups are used by Skype for Business Server to determine the Front End server that users register with.



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

### -UserFilter

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Enables you to import user data for a single user.
To convert data for a specified user (and only for that user), set the UserFilter parameter to the SIP address of that user, being sure to omit the sip: prefix.
For example:

`-UserFilter "kenmyer@litwareinc.com"`

This parameter allows you to import data one user at a time.

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

### CommonParameters
This cmdlet supports the common parameters: `-Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).`

## INPUTS

### None
The Import-CsUserData cmdlet does not accept pipelined input.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Convert-CsUserData](Convert-CsUserData.md)

[Export-CsUserData](Export-CsUserData.md)

[Sync-CsUserData](Sync-CsUserData.md)

[Update-CsUserData](Update-CsUserData.md)
