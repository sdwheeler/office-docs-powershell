---
applicable: Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skypeforbusiness/test-csmanagementserver
schema: 2.0.0
title: Test-CsManagementServer
---

# Test-CsManagementServer

## SYNOPSIS
Verifies that the Central Management service is working correctly.
The Central Management service is responsible for replicating data between the Central Management store and computers running Skype for Business Server.


## SYNTAX

```
Test-CsManagementServer [-Report <String>] [<CommonParameters>]
```


## DESCRIPTION
The Central Management service is responsible for replicating data between the Central Management store and computers running Skype for Business Server.
The Central Management service runs on a single Front End pool (or a single Standard Edition server) and facilitates replication throughout the Skype for Business Server infrastructure.
The `Test-CsManagementServer` cmdlet enables you verify that the Management service is working correctly.


## EXAMPLES

### Example 1
```
Test-CsManagementServer
```

The command shown in Example 1 tests the Central Management service.
Because there can only be a single instance of this service, no additional parameters are required.


## PARAMETERS

### -Report

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Enables you to specify a file path for the log file created when the cmdlet runs.
For example:

`-Report "C:\Logs\ManagementServerTestTest.html"`

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
The `test-CsManagementServer` cmdlet does not accept pipelined input.

## OUTPUTS

### Microsoft.Rtc.SyntheticTransactions.TaskOutput
The `Test-CsManagementServer` cmdlet returns an instance of the Microsoft.Rtc.SyntheticTransactions.TaskOutput object.

## NOTES

## RELATED LINKS

[Set-CsManagementServer](Set-CsManagementServer.md)
