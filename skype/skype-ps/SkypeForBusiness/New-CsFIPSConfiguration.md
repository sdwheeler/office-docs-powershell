---
applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skypeforbusiness/new-csfipsconfiguration
schema: 2.0.0
title: New-CsFIPSConfiguration
---

# New-CsFIPSConfiguration

## SYNOPSIS

Creates a new collection of Federal Information Processing Standards (FIPS) configuration settings.
The FIPS standards are a set of United States government security standards required for use in computers maintained by non-military government agencies and by government contractors.
This cmdlet was introduced in Lync Server 2013.



## SYNTAX

```
New-CsFIPSConfiguration [-Identity] <XdsIdentity> [-Confirm] [-Force] [-InMemory]
 [-RequireFIPSCompliantMedia <Boolean>] [-Tenant <Guid>] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION

The Federal Information Processing Standards (FIPS) are a series of standards and guidelines used by computers engaged in work for the United States government; for example, there are FIPS standards that govern the use of such things as cryptography, encryption, and digital signatures.
(See httpss://www.itl.nist.gov/fipspubs/by-num.htm (https://www.itl.nist.gov/fipspubs/by-num.htm) for more information.) Skype for Business Server provides an option that enables the software to use only algorithms that meet the FIPS standards.
If you need to work with the United States government (or with other entities that follow FIPS) then you can enable FIPS compliance in Skype for Business Server.

Keep in mind, however, that, for the on-premises version of Skype for Business Server, you have only a single, global collection of FIPS configuration settings: FIPS compliance can only be enabled or disabled for your entire Skype for Business Server implementation.
You cannot selectively enable or disable FIPS compliance on, say, an individual site or an individual Registrar pool.
If you do enable FIPS compliance, you could potentially encounter problems when trying to communicate with organizations that do not fully adhere to the FIPS standards.
That means that the New-CsFIPSConfiguration cmdlet is primarily used to manage FIPS compliance for Skype for Business Online.

By default, FIPS compliance is disabled in Skype for Business Server.

Skype for Business Server Control Panel: The functions carried out by the New-CsFIPSConfiguration cmdlet are not available in the Skype for Business Server Control Panel.



## EXAMPLES


### Example 1
```
$x = New-CsFIPSConfiguration -Identity "global" -RequireFIPSCompliantMedia $False -InMemory

Set-CsFIPSConfiguration -Instance $x
```

The commands shown in Example 1 create a new, in-memory-only set of FIPS configuration settings and then later use these settings to update the global collection of FIPS configuration settings.
In order to do this, the first command in the example uses the New-CsFIPSConfiguration cmdlet and the InMemory parameter to create a new collection of FIPS configurations settings with the Identity "global"; the resulting settings object is stored in a variable named $x.

In the second command, the Set-CsFIPSConfiguration cmdlet and the Instance parameter are then used to replace the existing global collection of FIPS settings with the new collection stored in $x.

Although this example works, it is easier to modify FIPS configuration settings by using the Set-CsFIPSConfiguration cmdlet.



## PARAMETERS

### -Force

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

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

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Unique identifier for the new collection of FIPS configuration settings.
Because Skype for Business Server only supports a single, global collection of FIPS settings, the only way you can use this parameter is to create a "new" global collection that exists only in memory.
You will also need to use the InMemory parameter in order to do that.



```yaml
Type: XdsIdentity
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InMemory

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Creates an object reference without actually committing the object as a permanent change.
If you assign the output of this cmdlet called with this parameter to a variable, you can make changes to the properties of the object reference and then commit those changes by calling this cmdlet's matching Set- cmdlet.

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

### -RequireFIPSCompliantMedia

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, Skype for Business Server will only allow media sessions with entities that use FIPS compliant algorithms for authentication and authorization.

Note that, if you require FIPS compliance, then your users will no longer be able to connect to your system by using a Microsoft Lync Server 2010 A/V Edge server.
Instead, you will need to upgrade all your Edge servers to Skype for Business Server.

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

### -Tenant

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Globally unique identifier (GUID) of the Skype for Business Online tenant account for which the new FIPS configuration settings are being created.
For example:

`-Tenant "38aad667-af54-4397-aaa7-e94c79ec2308"`

You can return the tenant ID for each of your tenants by running this command:

`Get-CsTenant | Select-Object DisplayName, TenantID`



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

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

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

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

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
This cmdlet supports the common parameters: `-Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).`

## INPUTS

### None
The New-CsFIPSConfiguration cmdlet does not accept pipelined input.

## OUTPUTS

### Microsoft.Rtc.Management.WritableConfig.Settings.FIPSConfiguration.FIPSConfiguration
The New-CsFIPSConfiguration cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.FIPSConfiguration.FIPSConfiguration object.

## NOTES

## RELATED LINKS

[Get-CsFIPSConfiguration](Get-CsFIPSConfiguration.md)

[Remove-CsFIPSConfiguration](Remove-CsFIPSConfiguration.md)

[Set-CsFIPSConfiguration](Set-CsFIPSConfiguration.md)
