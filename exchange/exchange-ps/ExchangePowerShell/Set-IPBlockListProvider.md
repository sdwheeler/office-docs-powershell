---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.TransportMailControl-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/set-ipblocklistprovider
schema: 2.0.0
title: Set-IPBlockListProvider
---

# Set-IPBlockListProvider

## SYNOPSIS
This cmdlet is available or effective only on Edge Transport servers in on-premises Exchange.

Use the Set-IPBlockListProvider cmdlet to modify IP Block list providers that are used by the Connection Filtering agent on Edge Transport servers.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Set-IPBlockListProvider [-Identity] <IPBlockListProviderIdParameter>
 [-AnyMatch <Boolean>]
 [-BitmaskMatch <IPAddress>]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-Enabled <Boolean>]
 [-IPAddressesMatch <MultiValuedProperty>]
 [-LookupDomain <SmtpDomain>]
 [-Name <String>]
 [-Priority <Int32>]
 [-RejectionResponse <AsciiString>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
On Edge Transport servers, you need to be a member of the local Administrators group to run this cmdlet.

## EXAMPLES

### Example 1
```powershell
Set-IPBlockListProvider Contoso.com -AnyMatch $true
```

This example configures connection filtering to block an IP address if any IP address status codes are returned by the IP Block list provider named Contoso.com.

### Example 2
```powershell
Set-IPBlockListProvider Contoso.com -Priority 1
```

This example sets the priority value to 1 for the IP Block list provider named Contoso.com.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Identity parameter specifies the IP Block list provider that you want to modify. You can use any value that uniquely identifies the IP Block list provider. For example:

- Name
- Distinguished name (DN)
- GUID

```yaml
Type: IPBlockListProviderIdParameter
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -AnyMatch

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The AnyMatch parameter specifies whether any response by the block list provider is treated as a match. Valid input for this parameter is $true or $false. The default value is $false. When this parameter is set to $true and connection filtering sends the IP address of the connecting SMTP server to the block list provider, any response code returned by the block list provider causes connection filtering to block messages from that source.

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

### -BitmaskMatch

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The BitmaskMatch parameter specifies the bit mask status code that's returned by the block list provider. Use this parameter if the block list provider returns bitmask responses. Valid input for this parameter is a single IP address in the format 127.0.0.1.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Confirm switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding.

- Destructive cmdlets (for example, Remove-\* cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: `-Confirm:$false`.
- Most other cmdlets (for example, New-\* and Set-\* cmdlets) don't have a built-in pause. For these cmdlets, specifying the Confirm switch without a value introduces a pause that forces you acknowledge the command before proceeding.

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

### -DomainController

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The DomainController parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, dc01.contoso.com.

The DomainController parameter isn't supported on Edge Transport servers. An Edge Transport server uses the local instance of Active Directory Lightweight Directory Services (AD LDS) to read and write data.

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

### -Enabled

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Enabled parameter specifies whether the connection filtering uses this IP Block list provider. Valid input for this parameter is $true or $false. The default value is $true. By default, connection filtering uses new IP Block list providers that you create.

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

### -IPAddressesMatch

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The IPAddressesMatch parameter specifies the IP address status codes that are returned by the block list provider. Use this parameter if the block list provider returns IP address or A record responses. Valid input for this parameter one or more IP addresses in the format 127.0.0.1.

To enter multiple values and overwrite any existing entries, use the following syntax: `Value1,Value2,...ValueN`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

To add or remove one or more values without affecting any existing entries, use the following syntax: `@{Add="Value1","Value2"...; Remove="Value3","Value4"...}`.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LookupDomain

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The LookupDomain parameter specifies the host name that's required to use the block list provider. Connection filtering sends the IP address of the connecting SMTP server to the host name value that you specify. An example value is blocklist.spamservice.com. The actual value you need to use is provided by the block list provider.

```yaml
Type: SmtpDomain
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Name parameter specifies a descriptive name for the IP Block list provider.

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

### -Priority

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Priority parameter specifies the order that the Connection Filtering agent queries the IP Block list providers. A lower priority integer value indicates a higher priority. By default, every time that you add a new IP Block list provider, the entry is assigned a priority of N+1, where N is the number of IP Block list provider services that you have configured.

If you set the Priority parameter to a value that's the same as another IP Block list provider service, the priority of the IP Block list provider that you add first is incremented by 1.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RejectionResponse

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The RejectionResponse parameter specifies the text that you want to include in the SMTP rejection response when messages are blocked by connection filtering. The argument can't exceed 240 characters. If the value contains spaces, enclose the value in quotation marks (").

You should always specify the block list provider in the response so that legitimate senders can contact the block list provider for removal instructions. For example, "Source IP address is listed at the Contoso.com block list provider".

```yaml
Type: AsciiString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The WhatIf switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/p/?LinkID=113216).

## INPUTS

### Input types
To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](https://go.microsoft.com/fwlink/p/?LinkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data.

## OUTPUTS

### Output types
To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](https://go.microsoft.com/fwlink/p/?LinkId=616387). If the Output Type field is blank, the cmdlet doesn't return data.

## NOTES

## RELATED LINKS
