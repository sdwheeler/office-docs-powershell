---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.RemoteConnections-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/new-webservicesvirtualdirectory
schema: 2.0.0
title: New-WebServicesVirtualDirectory
---

# New-WebServicesVirtualDirectory

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the New-WebServicesVirtualDirectory cmdlet to create Exchange Web Services virtual directories that are used in Internet Information Services (IIS) on Microsoft Exchange servers.

You can create multiple virtual directories by using this cmdlet. However, you can create only one Exchange Web Services virtual directory for each website.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
New-WebServicesVirtualDirectory [-ApplicationRoot <String>]
 [-AppPoolId <String>]
 [-AppPoolIdForManagement <String>]
 [-BasicAuthentication <Boolean>]
 [-Confirm]
 [-DigestAuthentication <Boolean>]
 [-DomainController <Fqdn>]
 [-ExtendedProtectionFlags <MultiValuedProperty>]
 [-ExtendedProtectionSPNList <MultiValuedProperty>]
 [-ExtendedProtectionTokenChecking <ExtendedProtectionTokenCheckingMode>]
 [-ExternalUrl <Uri>]
 [-Force]
 [-GzipLevel <GzipLevel>]
 [-InternalNLBBypassUrl <Uri>]
 [-InternalUrl <Uri>]
 [-MRSProxyEnabled <Boolean>]
 [-MRSProxyMaxConnections <Unlimited>]
 [-OAuthAuthentication <Boolean>]
 [-Path <String>]
 [-Role <VirtualDirectoryRole>]
 [-Server <ServerIdParameter>]
 [-WebSiteName <String>]
 [-WhatIf]
 [-WindowsAuthentication <Boolean>]
 [-WSSecurityAuthentication <Boolean>]
 [<CommonParameters>]
```

## DESCRIPTION
You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
New-WebServicesVirtualDirectory -WebSiteName "www.contoso.com" -ExternalUrl "https://www.contoso.com/webservices.aspx"
```

This example creates a virtual directory under the non-default website www.contoso.com. It also sets the external URL to `https://www.contoso.com/webservices.aspx`.

## PARAMETERS

### -ApplicationRoot

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ApplicationRoot parameter specifies the metabase path of the virtual directory. By default, this path is the same as the website in which the virtual directory is created.

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

### -AppPoolId

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The AppPoolId parameter specifies the IIS application pool in which the virtual directory runs. We recommend that you leave this parameter at its default setting.

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

### -AppPoolIdForManagement

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The AppPoolIdForManagement parameter specifies the pool of programs that manages the virtual directory.

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

### -BasicAuthentication

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The BasicAuthentication parameter specifies whether Basic authentication is enabled on the virtual directory. Valid values are:

- $true: Basic authentication is enabled. This is the default value.
- $false: Basic authentication is disabled.

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

### -DigestAuthentication

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The DigestAuthentication parameter specifies whether Digest authentication is enabled on the virtual directory. Valid values are:

- $true: Digest authentication is enabled.
- $false: Digest authentication is disabled. This is the default value.

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

### -ExtendedProtectionFlags

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ExtendedProtectionFlags parameter specifies custom settings for Extended Protection for Authentication on the virtual directory. Valid values are:

- None: This is the default setting.
- AllowDotlessSPN: Required if you want to use Service Principal Name (SPN) values that don't contain FQDNs (for example, HTTP/ContosoMail instead of HTTP/mail.contoso.com). You specify SPNs with the ExtendedProtectionSPNList parameter. This setting makes Extended Protection for Authentication less secure because dotless certificates aren't unique, so it isn't possible to ensure that the client-to-proxy connection was established over a secure channel.
- NoServiceNameCheck: The SPN list isn't checked to validate a channel binding token. This setting makes Extended Protection for Authentication less secure. We generally don't recommend this setting.
- Proxy: A proxy server is responsible for terminating the SSL channel. To use this setting, you need to register an SPN by using the ExtendedProtectionSPNList parameter.
- ProxyCoHosting: HTTP and HTTPS traffic may be accessing the virtual directory, and a proxy server is located between at least some of the clients and the Client Access services on the Exchange server.

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

### -ExtendedProtectionSPNList

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ExtendedProtectionSPNList parameter specifies a list of valid Service Principal Names (SPNs) if you're using Extended Protection for Authentication on the virtual directory. Valid values are:

- $null: This is the default value.
- Single SPN or comma delimited list of valid SPNs: The SPN value format is `Protocol\FQDN`. For example, HTTP/mail.contoso.com. To add an SPN that's not an FQDN (for example, HTTP/ContosoMail), you also need to use the AllowDotlessSPN value for the ExtendedProtectionFlags parameter.

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

### -ExtendedProtectionTokenChecking

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ExtendedProtectionTokenChecking parameter defines how you want to use Extended Protection for Authentication on the virtual directory. Extended Protection for Authentication isn't enabled by default. Valid values are:

- None: Extended Protection for Authentication isn't be used on the virtual directory. This is the default value.
- Allow: Extended Protection for Authentication is used for connections between clients and the virtual directory if both the client and server support it. Connections that don't support Extended Protection for Authentication will work, but may not be as secure as connections that use Extended Protection for Authentication.
- Require: Extended Protection for Authentication is used for all connections between clients and the virtual directory. If either the client or server doesn't support it, the connection will fail. If you use this value, you also need to set an SPN value for the ExtendedProtectionSPNList parameter.

**Note**: If you use the value Allow or Require, and you have a proxy server between the client and the Client Access services on the Mailbox server that's configured to terminate the client-to-proxy SSL channel, you also need to configure one or more Service Principal Names (SPNs) by using the ExtendedProtectionSPNList parameter.

```yaml
Type: ExtendedProtectionTokenCheckingMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalUrl

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ExternalURL parameter specifies the URL that's used to connect to the virtual directory from outside the firewall.

This setting is important when Secure Sockets Layer (SSL) is used.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Force switch hides warning or confirmation messages. You don't need to specify a value with this switch.

You can use this switch to run tasks programmatically where prompting for administrative input is inappropriate.

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

### -GzipLevel

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The GzipLevel parameter sets the Gzip configuration for the Exchange Web Services virtual directory. Valid values are:

- Off: No compression.
- Low: Static compression only. This is the default value. This value has the same result as the Off value, because Exchange Web Services content is dynamic.
- High: Static and dynamic compression. Content from Exchange Web Services is compressed if clients indicate support for Gzip compression in their requests.
- Error: Identifies errors in the Gzip compression configuration.

```yaml
Type: GzipLevel
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InternalNLBBypassUrl

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The InternalNLBBypassUrl parameter specifies the URL of the Exchange server that has the Client Access server role installed, regardless of whether it's behind a Network Load Balancing (NLB) array or not.

When you set the InternalUrl parameter to the URL of the NLB array, you should set the InternalNLBBypassUrl parameter to the URL of the Client Access server itself.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InternalUrl

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The InternalURL parameter specifies the URL that's used to connect to the virtual directory from inside the firewall.

This setting is important when SSL is used.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MRSProxyEnabled

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The MRSProxyEnabled parameter specifies whether to enable MRSProxy for the Mailbox server. MRSProxy is a service that runs on Mailbox servers in a remote forest and helps to proxy a mailbox move. For more information, see [Mailbox moves in Exchange Server](https://learn.microsoft.com/Exchange/recipients/mailbox-moves).

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

### -MRSProxyMaxConnections

> Applicable: Exchange Server 2010

This parameter is available only in Exchange Server 2010.

The MRSProxyMaxConnections parameter specifies the maximum number of simultaneous move sessions that an instance of MRSProxy will accept. This setting accepts values from 0 to unlimited. The default value is 100. For more information about MRSProxy, see [Understanding Move Requests](https://learn.microsoft.com/previous-versions/office/exchange-server-2010/dd298174(v=exchg.141)).

```yaml
Type: Unlimited
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OAuthAuthentication

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The OAuthAuthentication parameter specifies whether OAuth authentication is enabled on the virtual directory. Valid values are:

- $true: OAuth authentication is enabled. This is the default value.
- $false: OAuth authentication is disabled.

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

### -Path

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Path parameter sets the path of the virtual directory in the metabase.

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

### -Role

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Role parameter species the configuration for the virtual directory. Valid values are:

- ClientAccess: Configure the virtual directory for the Client Access (frontend) services on the Mailbox server.
- Mailbox: Configure the virtual directory for the backend services on the Mailbox server.

Client connections are proxied from the Client Access services to the backend services on local or remote Mailbox servers. Clients don't connect directly to the backend services.

```yaml
Type: VirtualDirectoryRole
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Server parameter specifies the Exchange server that hosts the virtual directory. You can use any value that uniquely identifies the server. For example:

- Name
- FQDN
- Distinguished name (DN)
- ExchangeLegacyDN

```yaml
Type: ServerIdParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -WebSiteName

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The WebSiteName parameter specifies the name of the website under which to create the virtual directory. This parameter shouldn't be used when you're creating a virtual directory under the default website.

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

### -WindowsAuthentication

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The WindowsAuthentication parameter specifies whether Integrated Windows authentication is enabled on the virtual directory. Valid values are:

- $true: Integrated Windows authentication is enabled. This is the default value.
- $false: Integrated Windows authentication is disabled.

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

### -WSSecurityAuthentication

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The WSSecurityAuthentication parameter specifies whether WS-Security (Web Services Security) authentication is enabled on the virtual directory. Valid values are:

- $true: WS-Security authentication is enabled. This is the default value.
- $false: WS-Security authentication is disabled.

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
