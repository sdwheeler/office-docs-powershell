---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016
author: chrisda
external help file: Microsoft.Exchange.MediaAndDevices-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/get-umcalldatarecord
schema: 2.0.0
title: Get-UMCallDataRecord
---

# Get-UMCallDataRecord

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the Get-UMCallDataRecord cmdlet to display Unified Messaging (UM) call data records for a specific UM-enabled user's mailbox.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Get-UMCallDataRecord -Mailbox <MailboxIdParameter>
 [-DomainController <Fqdn>]
 [<CommonParameters>]
```

## DESCRIPTION
The Get-UMCallDataRecord cmdlet displays UM call data records for the last 90 days for a UM-enabled mailbox that you specify. Each UM call data record provides detailed information about all calls either placed to or received by the specified user. The following list details each of the properties that are returned:

- Date: Date and time of the Mailbox server running the Microsoft Exchange Unified Messaging service that took the call in the Coordinated Universal Time (UTC) format.
- Duration: Total duration of this call. For Find Me calls, this will always be zero because the call is being transferred and won't be handled by Unified Messaging any longer.
- AudioCodec: Audio codec used for the call including G.711 or Group System Mobile (GSM).
- DialPlan: Name of the UM dial plan handling the call.
- CallType: Type of the call (localized in the user's language): Call Answering Voice Message, Call Answering Missed Call, , Auto Attendant, Subscriber Access, Fax, PlayOnPhone, Find Me, None, UnauthenticatedPilotNumber, or PromptProvisioning.
- CallingNumber: Phone number or address of the caller.
- CalledNumber: Phone number or address of the intended recipient of the call.
- Gateway: Fully qualified domain name (FQDN) of the UM IP gateway handling the call.
- Network MOS (NMOS): Mean opinion score for the network performance.
- NMOSDegradation: Total NMOS degradation, which is how far the NMOS reported value was from its top value for the corresponding audio codec.
- PercentagePacketLoss: Percentage that reflects the average network packet loss during the call.
- Jitter: Average jitter of the network.
- RoundTripMilliseconds: Round trip time for Real Time Control Protocol (RTCP) statistics in milliseconds.
- BurstLossDurationMilliseconds: Average duration of packet loss during bursts during the call.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Get-UMCallDataRecord -Mailbox tony@contoso.com
```

This example displays the UM call data records for the UM-enabled user Tony.

## PARAMETERS

### -Mailbox

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The Mailbox parameter specifies the UM-enabled mailbox that UM call data records are displayed for. You can use any value that uniquely identifies the mailbox. For example:

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

```yaml
Type: MailboxIdParameter
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainController

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

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
