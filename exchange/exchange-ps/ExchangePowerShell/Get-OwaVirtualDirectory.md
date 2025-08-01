---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.WebClient-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/get-owavirtualdirectory
schema: 2.0.0
title: Get-OwaVirtualDirectory
---

# Get-OwaVirtualDirectory

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the Get-OwaVirtualDirectory cmdlet to view Outlook on the web virtual directories that are used in Internet Information Services (IIS) on Microsoft Exchange servers.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

### Server
```
Get-OwaVirtualDirectory -Server <ServerIdParameter>
 [-ADPropertiesOnly]
 [-DomainController <Fqdn>]
 [-ShowMailboxVirtualDirectories]
 [<CommonParameters>]
```

### Identity
```
Get-OwaVirtualDirectory [[-Identity] <VirtualDirectoryIdParameter>]
 [-ADPropertiesOnly]
 [-DomainController <Fqdn>]
 [-ShowMailboxVirtualDirectories]
 [<CommonParameters>]
```

## DESCRIPTION
The Get-OwaVirtualDirectory cmdlet can be run on a local server or run remotely if the server name is specified in the Identity or Server parameters.

The Get-OwaVirtualDirectory cmdlet can be run on any server that has the Exchange Server administration tools installed.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Get-OwaVirtualDirectory -Server Contoso
```

This example returns a summary list of all Outlook on the web virtual directories on the server named Contoso.

### Example 2
```powershell
Get-OwaVirtualDirectory -Identity "Contoso\owa*" | Format-List
```

This example returns detailed information for the Outlook on the web virtual directory named "owa (Default Web site)" on the server named Contoso.

### Example 3
```powershell
Get-OwaVirtualDirectory
```

This example returns a summary list of all Outlook on the web virtual directories in the client access services on all Mailbox servers in the organization.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Identity parameter specifies the OWA virtual directory that you want to view. You can use any value that uniquely identifies the virtual directory. For example:

- Name or Server\\Name
- Distinguished name (DN)
- GUID

The Name value uses the syntax `"VirtualDirectoryName (WebsiteName)"` from the properties of the virtual directory. You can specify the wildcard character (\*) instead of the default website by using the syntax `VirtualDirectoryName*`.

You can't use the Identity and Server parameters in the same command.

```yaml
Type: VirtualDirectoryIdParameter
Parameter Sets: Identity
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -Server

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Server parameter specifies the Exchange server that hosts the virtual directory. You can use any value that uniquely identifies the server. For example:

- Name
- FQDN
- Distinguished name (DN)
- ExchangeLegacyDN

You can't use the Server and Identity parameters in the same command.

```yaml
Type: ServerIdParameter
Parameter Sets: Server
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -ADPropertiesOnly

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ADPropertiesOnly switch specifies whether to return only the virtual directory properties that are stored in Active Directory. You don't need to specify a value with this switch.

If you don't use this switch, the properties in Active Directory and in the Internet Information Services (IIS) metabase are returned.

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

### -DomainController

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

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

### -ShowMailboxVirtualDirectories

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ShowMailboxVirtualDirectories switch shows information about backend virtual directories on Mailbox servers. You don't need to specify a value with this switch.

By default, this cmdlet shows information about virtual directories in the Client Access services on Mailbox servers. Client connections are proxied from the Client Access services on Mailbox servers to the backend services on Mailbox servers. Clients don't connect directly to the backend services.

We recommend that you use this parameter only under the direction of Microsoft Customer Service and Support.

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
