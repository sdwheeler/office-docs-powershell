---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skypeforbusiness/move-csexumcontact
schema: 2.0.0
title: Move-CsExUmContact
---

# Move-CsExUmContact

## SYNOPSIS

Moves one or more Exchange Unified Messaging (UM) contacts to a new Registrar pool.
This cmdlet was introduced in Lync Server 2010.



## SYNTAX

### Identity (Default)
```
Move-CsExUmContact [-Target] <Fqdn> [-Report <String>] [-Force] [-UseLegacyMode] [-IgnoreBackendStoreException]
 [-ProxyPool <Fqdn>] [-DomainController <Fqdn>] [-Identity] <UserIdParameter> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Users
```
Move-CsExUmContact [-Target] <Fqdn> -UserList <String> [-Report <String>] [-Force] [-UseLegacyMode]
 [-IgnoreBackendStoreException] [-ProxyPool <Fqdn>] [-DomainController <Fqdn>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Skype for Business Server works with Exchange UM to provide several voice-related capabilities, including Auto Attendant and Subscriber Access.
The Move-CsExUmContact cmdlet provides a way for you to move an existing Exchange UM contact object to a new Registrar pool.

When an Exchange UM contact object is moved, the AutoAttendant and IsSubscriberAccess properties will be set appropriately based on the value of the OtherIpPhone property of the object.



## EXAMPLES

### EXAMPLE 1
```

Move-CsExUmContact -Identity "sip:exum1@fabrikam.com" -Target atl-cs-001.litwareinc.com
```

Example 1 moves the Exchange UM contact object with the SIP address exum1@fabrikam.com to the Registrar pool with the FQDN atl-cs-001.litwareinc.com.
Note that a confirmation prompt will be displayed when you run this command, even though we didn't include the Confirm parameter.
This prompt will appear even if you include the Force parameter.


### EXAMPLE 2
```

Get-CsExUmContact | Where-Object {$_.AutoAttendant -eq $True} | Move-CsExUmContact -Target atl-cs-001.litwareinc.com

```

This example moves all Exchange UM contact objects that are Auto Attendants to the Registrar pool with the FQDN atl-cs-001.litwareinc.com.
The example begins with a call to the Get-CsExUmContact cmdlet, which retrieves all Exchange UM contacts that have been defined.
This collection of contacts is then piped to the Where-Object cmdlet, which finds all the contacts in the collection that have an AutoAttendant property value of True ($True), meaning the contact is an Auto Attendant.

Finally, the collection of contacts where AutoAttendant is True is piped to the Move-CsExUmContact cmdlet, which moves those contacts to the Registrar pool specified in the Target parameter.

As in Example 1, you will be prompted for confirmation when running this command.

## PARAMETERS

### -DomainController

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Enables you to connect to the specified domain controller.
To connect to a particular domain controller, include the DomainController parameter followed by the computer name (for example, atl-mcs-001) or its FQDN (for example, atl-mcs-001.litwareinc.com).

```yaml
Type: Microsoft.Rtc.Management.Deploy.Fqdn
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Suppresses any confirmation prompts that would otherwise be displayed before making changes.

```yaml
Type: System.Management.Automation.SwitchParameter
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

The unique identifier of the contact object you want to move.
Contact identities can be specified by using one of four formats: 1) the contact's SIP address; 2) the contact's user principal name (UPN); 3) the contact's domain name and logon name, in the form domain\logon (for example, litwareinc\exum1); and, 4) the contact's Active Directory display name (for example, Team Auto Attendant).

```yaml
Type: Microsoft.Rtc.Management.AD.UserIdParameter
Parameter Sets: Identity
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -IgnoreBackendStoreException

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

When present, instructs the computer to ignore any errors that might occur with the backend database and attempt to move the contact despite those errors.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Enables you to pass a contact object through the pipeline that represents the contact account being moved.
By default, the Move-CsExUmContact cmdlet does not pass objects through the pipeline.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyPool

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

This parameter is used only for hosted instances of Skype for Business Server.
It should not be used with an on-premises implementation of Skype for Business Server.



```yaml
Type: Microsoft.Rtc.Management.Deploy.Fqdn
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Report

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

PARAMVALUE: String

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Target

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

The fully qualified domain name (FQDN) of the Registrar pool to which the contact is being moved.

```yaml
Type: Microsoft.Rtc.Management.Deploy.Fqdn
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseLegacyMode
{{ Fill UseLegacyMode Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserList

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

PARAMVALUE: String

```yaml
Type: System.String
Parameter Sets: Users
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Prompts you for confirmation before executing the command.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Describes what would happen if you executed the command without actually executing the command.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
Accepts a pipelined string value representing the Identity of an Exchange UM object to be moved.

## OUTPUTS

### Microsoft.Rtc.Management.ADConnect.Schema.OCSADExUmContact
When called with the PassThru parameter, returns an object of type Microsoft.Rtc.Management.ADConnect.Schema.OCSADExUmContact.

## NOTES

## RELATED LINKS

[New-CsExUmContact](New-CsExUmContact.md)

[Remove-CsExUmContact](Remove-CsExUmContact.md)

[Set-CsExUmContact](Set-CsExUmContact.md)

[Get-CsExUmContact](Get-CsExUmContact.md)
