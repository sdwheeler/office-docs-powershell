---
applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skypeforbusiness/new-csreportingconfiguration
schema: 2.0.0
title: New-CsReportingConfiguration
---

# New-CsReportingConfiguration

## SYNOPSIS

Creates a new collection of reporting configuration settings at the service scope.
Reporting configuration settings are used to specify the URL used to access Skype for Business Server 2015 Monitoring Reports.
This cmdlet was introduced in Lync Server 2013.



## SYNTAX

```
New-CsReportingConfiguration [-Identity] <XdsIdentity> [-Confirm] [-Force] [-InMemory] [-ReportingUrl <String>]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION

Reporting configuration settings are used to specify the home page for the Skype for Business Server Monitoring Reports; if you are not using Monitoring Reports then there is no reason for you to modify the reporting configuration settings.

If you do not know the URL for the Monitoring Reports home page you can determine that URL by doing the following:

Open the SQL Server Reporting Services Configuration Manager for the SQL Server instance that contains your monitoring database.

In the Configuration Manager, click Report Manager URL and then click the URL for your Monitoring Reports.
If you see two URLs, click the one that uses the https protocol.

In SQL Server Reporting Services, click LyncServerReports.

On the LyncServerReports page, click Reports Home Page.
That will take you to the home page for the Monitoring Reports.
You can then copy the URL and use that URL in conjunction with the CsReportingConfiguration cmdlets.

Skype for Business Server Control Panel: The functions carried out by the New-CsReportingConfiguration cmdlet are not available in the Skype for Business Server Control Panel.



## EXAMPLES

### Example 1
```

New-CsReportingConfiguration -Identity "service:MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingUrl "https://atl-sql-001.litwareinc.com/lync_reports"

```

The command shown in Example 1 creates a new collection of reporting configuration settings assigned to the monitoring database with the identity service:MonitoringDatabase:atl-sql-001.litwareinc.com.
In this example, the value of the ReportingUrl property is set to `https://atl-sql-001.litwareinc.com/lync_reports`.

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

Service Identity of the monitoring database to be associated with the new reporting configuration settings.
For example:

`-Identity "Service:MonitoringDatabase:atl-sql-001.litwareinc.com"`

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

### -ReportingUrl

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

URL for the Skype for Business Server Monitoring Reports.



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
The New-CsReportingConfiguration cmdlet does not accept pipelined data.

## OUTPUTS


### Microsoft.Rtc.Management.WritableConfig.Settings.Reporting.ReportingConfiguration
The New-CsReportingConfiguration cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Reporting.ReportingConfiguration object.

## NOTES

## RELATED LINKS

[Get-CsReportingConfiguration](Get-CsReportingConfiguration.md)

[Remove-CsReportingConfiguration](Remove-CsReportingConfiguration.md)

[Set-CsReportingConfiguration](Set-CsReportingConfiguration.md)
