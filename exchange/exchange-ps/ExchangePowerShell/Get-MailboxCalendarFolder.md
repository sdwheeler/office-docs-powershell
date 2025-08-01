---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online
author: chrisda
external help file: Microsoft.Exchange.CalendarsAndGroups-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/get-mailboxcalendarfolder
schema: 2.0.0
title: Get-MailboxCalendarFolder
---

# Get-MailboxCalendarFolder

## SYNOPSIS
This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

Use the Get-MailboxCalendarFolder cmdlet to retrieve the publishing or sharing settings for a specified mailbox calendar folder.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Get-MailboxCalendarFolder [-Identity] <MailboxFolderIdParameter>
 [-UseCustomRouting]
 [-DomainController <Fqdn>]
 [<CommonParameters>]
```

## DESCRIPTION
The Get-MailboxCalendarFolder cmdlet retrieves information for the specified calendar folder. This information includes the calendar folder name, whether the folder is currently published or shared, the start and end range of calendar days published, the level of details published for the calendar, whether the published URL of the calendar can be searched on the web and the published URL for the calendar.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Get-MailboxCalendarFolder -Identity kai:\Calendar
```

This example returns all provided publishing information for the specified calendar folder in Kai's mailbox. In this example, the Identity parameter specifies the mailbox with the alias format.

### Example 2
```powershell
Get-MailboxCalendarFolder -Identity kai:\Calendar -DomainController DC1
```

This example returns all provided publishing information for the specified calendar folder in Kai's mailbox. This example also specifies DC1 as the domain controller to retrieve this information from Active Directory.

### Example 3
```powershell
Get-MailboxCalendarFolder -Identity contoso\kai:\Calendar
```

This example returns all provided publishing information for the specified calendar folder in Kai's mailbox. In this example, the Identity parameter specifies the mailbox with the domain\\account format.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019, Exchange Online

The Identity parameter specifies the calendar folder that you want to view. The syntax is `MailboxID:\ParentFolder[\SubFolder]`.

For the value of `MailboxID`, you can use any value that uniquely identifies the mailbox. For example:

- Name
- Alias
- Distinguished name (DN)
- Canonical DN
- Domain\\Username
- Email address
- GUID
- LegacyExchangeDN
- SamAccountName
- User ID or user principal name (UPN)

Example values for this parameter are `john@contoso.com:\Calendar` or `John:\Calendar`.

```yaml
Type: MailboxFolderIdParameter
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -DomainController

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This parameter is available only in on-premises Exchange.

The DomainController parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, dc01.contoso.com.

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

### -UseCustomRouting

> Applicable: Exchange Online

This parameter is available only in the cloud-based service.

{{ Fill UseCustomRouting Description }}

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/p/?LinkID=113216).

## INPUTS

### Input types
To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](https://go.microsoft.com/fwlink/p/?LinkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data.

## OUTPUTS

### Output types
To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](https://go.microsoft.com/fwlink/p/?LinkId=616387). If the Output Type field is blank, the cmdlet doesn't return data.

## NOTES

## RELATED LINKS
