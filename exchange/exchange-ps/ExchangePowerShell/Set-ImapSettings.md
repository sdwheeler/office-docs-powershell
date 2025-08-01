---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.RemoteConnections-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/set-imapsettings
schema: 2.0.0
title: Set-ImapSettings
---

# Set-ImapSettings

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the Set-ImapSettings cmdlet to modify the settings of the Microsoft Exchange IMAP4 service on Exchange servers. This service exists on Exchange servers that have the Client Access server role installed, and is used by IMAP4 clients to connect to Exchange.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Set-ImapSettings [-AuthenticatedConnectionTimeout <EnhancedTimeSpan>]
 [-Banner <String>]
 [-CalendarItemRetrievalOption <CalendarItemRetrievalOptions>]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-EnableExactRFC822Size <Boolean>]
 [-EnableGSSAPIAndNTLMAuth <Boolean>]
 [-EnforceCertificateErrors <Boolean>]
 [-ExtendedProtectionPolicy <ExtendedProtectionTokenCheckingMode>]
 [-ExternalConnectionSettings <MultiValuedProperty>]
 [-InternalConnectionSettings <MultiValuedProperty>]
 [-LogFileLocation <String>]
 [-LogFileRollOverSettings <LogFileRollOver>]
 [-LoginType <LoginOptions>]
 [-LogPerFileSizeQuota <Unlimited>]
 [-MaxCommandSize <Int32>]
 [-MaxConnectionFromSingleIP <Int32>]
 [-MaxConnections <Int32>]
 [-MaxConnectionsPerUser <Int32>]
 [-MessageRetrievalMimeFormat <MimeTextFormat>]
 [-OwaServerUrl <Uri>]
 [-PreAuthenticatedConnectionTimeout <EnhancedTimeSpan>]
 [-ProtocolLogEnabled <Boolean>]
 [-ProxyTargetPort <Int32>]
 [-Server <ServerIdParameter>]
 [-ShowHiddenFoldersEnabled <Boolean>]
 [-SSLBindings <MultiValuedProperty>]
 [-SuppressReadReceipt <Boolean>]
 [-UnencryptedOrTLSBindings <MultiValuedProperty>]
 [-WhatIf]
 [-X509CertificateName <String>]
 [<CommonParameters>]
```

## DESCRIPTION
You can run the Set-ImapSettings cmdlet for a single Exchange server that's running the Microsoft Exchange IMAP4 service, or for all Exchange servers that are running the Microsoft Exchange IMAP4 service.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Set-ImapSettings -Server "MBX01" -UnencryptedOrTLSBindings 10.0.0.0:143
```

This example configures the unencrypted or STARTTLS encrypted IMAP4 connection to the server named MBX01 by using the local IP address 10.0.0.0 on TCP port 143.

### Example 2
```powershell
Set-ImapSettings -ProtocolLogEnabled $true -LogFileLocation "C:\Imap4Logging"
```

This example turns on IMAP4 protocol logging. It also changes the IMAP4 protocol logging directory to C:\\Imap4Logging.

### Example 3
```powershell
Set-ImapSettings -LogPerFileSizeQuota 2MB
```

This example changes the IMAP4 protocol logging to create a new log file when a log file reaches 2 megabytes (MB).

### Example 4
```powershell
Set-ImapSettings -LogPerFileSizeQuota 0 -LogFileRollOverSettings Hourly
```

This example changes the IMAP4 protocol logging to create a new log file every hour.

### Example 5
```powershell
Set-ImapSettings -X509CertificateName mail.contoso.com
```

This example specifies the certificate that contains mail.contoso.com is used to encrypt IMAP4 client connections.

**Note**: For single subject certificates or a SAN certificates, you also need to assign the certificate to the Exchange IMAP service by using the Enable-ExchangeCertificate cmdlet. For wildcard certificates, you don't need to assign the certificate to the Exchange IMAP service (you'll receive an error if you try).

## PARAMETERS

### -AuthenticatedConnectionTimeout

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The AuthenticatedConnectionTimeout parameter specifies the period of time to wait before closing an idle authenticated connection.

To specify a value, enter it as a time span: dd.hh:mm:ss where dd = days, hh = hours, mm = minutes, and ss = seconds.

Valid values are 00:00:30 to 1:00:00. The default setting is 00:30:00 (30 minutes).

```yaml
Type: EnhancedTimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Banner

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Banner parameter specifies the text string that's displayed to connecting IMAP4 clients. The default value is: The Microsoft Exchange IMAP4 service is ready.

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

### -CalendarItemRetrievalOption

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The CalendarItemRetrievalOption parameter specifies how calendar items are presented to IMAP4 clients. Valid values are:

- 0 or iCalendar. This is the default value.
- 1 or IntranetUrl
- 2 or InternetUrl
- 3 or Custom

If you specify 3 or Custom, you need to specify a value for the OwaServerUrl parameter setting.

```yaml
Type: CalendarItemRetrievalOptions
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

### -EnableExactRFC822Size

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The EnableExactRFC822Size parameter specifies how message sizes are presented to IMAP4 clients. Valid values are:

- $true: Calculate the exact message size. Because this setting can negatively affect performance, you should configure it only if it's required by your IMAP4 clients.
- $false: Use an estimated message size. This is the default value.

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

### -EnableGSSAPIAndNTLMAuth

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The EnableGSSAPIAndNTLMAuth parameter specifies whether connections can use Integrated Windows authentication (NTLM) using the Generic Security Services application programming interface (GSSAPI). This setting applies to connections where Transport Layer Security (TLS) is disabled. Valid values are:

- $true: NTLM for IMAP4 connections is enabled. This is the default value.
- $false: NTLM for IMAP4 connections is disabled.

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

### -EnforceCertificateErrors

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The EnforceCertificateErrors parameter specifies whether to enforce valid Secure Sockets Layer (SSL) certificate validation failures. Valid values are:

The default setting is $false.

- $true: If the certificate isn't valid or doesn't match the target IMAP4 server's FQDN, the connection attempt fails.
- $false: The server doesn't deny IMAP4 connections based on certificate errors. This is the default value.

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

### -ExtendedProtectionPolicy

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ExtendedProtectionPolicy parameter specifies how Extended Protection for Authentication is used. Valid values are:

- None: Extended Protection for Authentication isn't used. This is the default value.
- Allow: Extended Protection for Authentication is used only if it's supported by the incoming IMAP4 connection. If it's not, Extended Protection for Authentication isn't used.
- Require: Extended Protection for Authentication is required for all IMAP4 connections. If the incoming IMAP4 connection doesn't support it, the connection is rejected.

Extended Protection for Authentication enhances the protection and handling of credentials by Integrated Windows authentication (also known as NTLM), so we strongly recommend that you use it if it's supported by your clients (default installations of Windows 7 or later and Windows Server 2008 R2 or later support it).

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

### -ExternalConnectionSettings

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ExternalConnectionSettings parameter specifies the host name, port, and encryption method that's used by external IMAP4 clients (IMAP4 connections from outside your corporate network).

This parameter uses the syntax `HostName:Port:[<TLS | SSL>]`. The encryption method value is optional (blank indicates unencrypted connections).

The default value is blank ($null), which means no external IMAP4 connection settings are configured.

To enter multiple values and overwrite any existing entries, use the following syntax: `Value1,Value2,...ValueN`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

To add or remove one or more values without affecting any existing entries, use the following syntax: `@{Add="Value1","Value2"...; Remove="Value3","Value4"...}`.

The combination of encryption methods and ports that are specified for this parameter need to match the corresponding encryption methods and ports that are specified by the SSLBindings and UnencryptedOrTLSBindings parameters.

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

### -InternalConnectionSettings

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The InternalConnectionSettings parameter specifies the host name, port, and encryption method that's used by internal IMAP4 clients (IMAP4 connections from inside your corporate network). This setting is also used when a IMAP4 connection is forwarded to another Exchange server that's running the Microsoft Exchange IMAP4 service.

This parameter uses the syntax `HostName:Port:[<TLS | SSL>]`. The encryption method value is optional (blank indicates unencrypted connections).

The default value is `<ServerFQDN>:993:SSL,<ServerFQDN>:143:TLS`.

To enter multiple values and overwrite any existing entries, use the following syntax: `Value1,Value2,...ValueN`. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

To add or remove one or more values without affecting any existing entries, use the following syntax: `@{Add="Value1","Value2"...; Remove="Value3","Value4"...}`.

The combination of encryption methods and ports that are specified for this parameter need to match the corresponding encryption methods and ports that are specified by the SSLBindings and UnencryptedOrTLSBindings parameters.

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

### -LogFileLocation

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The LogFileLocation parameter specifies the location for the IMAP4 protocol log files. The default location is %ExchangeInstallPath%Logging\\Imap4.

This parameter is only meaningful when the ProtocolLogEnabled parameter value is $true.

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

### -LogFileRollOverSettings

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The LogFileRollOverSettings parameter specifies how frequently IMAP4 protocol logging creates a new log file. Valid values are:

- 1 or Hourly. This is the default value in Exchange 2019 and Exchange 2016.
- 2 or Daily. This is the default value in Exchange 2013 and Exchange 2010.
- 3 or Weekly.
- 4 or Monthly.

This parameter is only meaningful when the LogPerFileSizeQuota parameter value is 0, and the ProtocolLogEnabled parameter value is $true.

```yaml
Type: LogFileRollOver
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoginType

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The LoginType parameter specifies the authentication method for IMAP4 connections. Valid values are:

- 1 or PlainTextLogin.
- 2 or PlainTextAuthentication.
- 3 or SecureLogin. This is the default value.

```yaml
Type: LoginOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogPerFileSizeQuota

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The LogPerFileSizeQuota parameter specifies the maximum size of a IMAP4 protocol log file.

When you enter a value, qualify the value with one of the following units:

- B (bytes)
- KB (kilobytes)
- MB (megabytes)
- GB (gigabytes)
- TB (terabytes)

Unqualified values are typically treated as bytes, but small values may be rounded up to the nearest kilobyte.

The default value is 0, which means a new IMAP4 protocol log file is created at the frequency that's specified by the LogFileRollOverSettings parameter.

This parameter is only meaningful when the ProtocolLogEnabled parameter value is $true.

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

### -MaxCommandSize

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The MaxCommandSize parameter specifies the maximum size in bytes of a single IMAP4 command. Valid values are from 1024 through 16384. The default value is 10240.

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

### -MaxConnectionFromSingleIP

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The MaxConnectionFromSingleIP parameter specifies the maximum number of IMAP4 connections that are accepted by the Exchange server from a single IP address. Valid values are from 1 through 2147483647. The default value is 2147483647.

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

### -MaxConnections

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The MaxConnections parameter specifies the maximum number of IMAP4 connections that are accepted by the Exchange server. Valid values are from 1 through 2147483647. The default value is 2147483647.

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

### -MaxConnectionsPerUser

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The MaxConnectionsPerUser parameter specifies the maximum number of IMAP4 connections that are allowed for each user. Valid values are from 1 through 2147483647. The default value is 16.

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

### -MessageRetrievalMimeFormat

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The MessageRetrievalMimeFormat parameter specifies the MIME encoding of messages. Valid values are:

- 0 or TextOnly.
- 1 or HtmlOnly.
- 2 or HtmlAndTextAlternative.
- 3 or TextEnrichedOnly.
- 4 or TextEnrichedAndTextAlternative.
- 5 or BestBodyFormat. This is the default value.
- 6 or Tnef.

```yaml
Type: MimeTextFormat
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OwaServerUrl

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The OwaServerUrl parameter specifies the URL that's used to retrieve calendar information for instances of custom Outlook on the web calendar items.

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

### -PreAuthenticatedConnectionTimeout

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The PreAuthenticatedConnectionTimeout parameter specifies the period of time to wait before closing an idle IMAP4 connection that isn't authenticated.

To specify a value, enter it as a time span: dd.hh:mm:ss where dd = days, hh = hours, mm = minutes, and ss = seconds.

Valid values are00:00:30 to 1:00:00. The default value is 00:01:00 (one minute).

```yaml
Type: EnhancedTimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtocolLogEnabled

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ProtocolLogEnabled parameter specifies whether to enable protocol logging for IMAP4. Valid values are:

- $true: IMAP4 protocol logging is enabled.
- $false: IMAP4 protocol logging is disabled. This is the default value.

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

### -ProxyTargetPort

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ProxyTargetPort parameter specifies the port on the Microsoft Exchange IMAP4 Backend service that listens for client connections that are proxied from the Microsoft Exchange IMAP4 service. The default value is 1993.

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

### -Server

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Server parameter specifies the Exchange server where you want to run this command. You can use any value that uniquely identifies the server. For example:

- Name
- FQDN
- Distinguished name (DN)
- Exchange Legacy DN

If you don't use this parameter, the command is run on the local server.

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

### -ShowHiddenFoldersEnabled

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ShowHiddenFoldersEnabled parameter specifies whether hidden mailbox folders are visible. Valid values are:

- $true: Hidden folders are visible.
- $false: Hidden folders aren't visible. This is the default value.

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

### -SSLBindings

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The SSLBindings parameter specifies the IP address and TCP port that's used for IMAP4 connection that's always encrypted by SSL/TLS. This parameter uses the syntax `IPv4OrIPv6Address:Port`.

The default value is `[::]:993,0.0.0.0:993`.

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

### -SuppressReadReceipt

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The SuppressReadReceipt parameter specifies whether to stop duplicate read receipts from being sent to IMAP4 clients that have the Send read receipts for messages I send setting configured in their IMAP4 email program. Valid values are:

- $true: The sender receives a read receipt only when the recipient opens the message.
- $false: The sender receives a read receipt when the recipient downloads the message, and when the recipient opens the message. This is the default value.

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

### -UnencryptedOrTLSBindings

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The UnencryptedOrTLSBindings parameter specifies the IP address and TCP port that's used for unencrypted IMAP4 connections, or IMAP4 connections that are encrypted by using opportunistic TLS (STARTTLS) after the initial unencrypted protocol handshake. This parameter uses the syntax `IPv4OrIPv6Address:Port`.

The default value is `[::]:143,0.0.0.0:143`.

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

### -X509CertificateName

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The X509CertificateName parameter specifies the certificate that's used for encrypting IMAP4 client connections.

A valid value for this parameter is the FQDN from the ExternalConnectionSettings or InternalConnectionSettings parameters (for example, mail.contoso.com or mailbox01.contoso.com).

If you use a single subject certificate or a subject alternative name (SAN) certificate, you also need to assign the certificate to the Exchange IMAP service by using the Enable-ExchangeCertificate cmdlet.

If you use a wildcard certificate, you don't need to assign the certificate to the Exchange IMAP service.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/p/?LinkID=113216).

## INPUTS

### Input types
To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](https://go.microsoft.com/fwlink/p/?LinkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data.

## OUTPUTS

### Output types
To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](https://go.microsoft.com/fwlink/p/?LinkId=616387). If the Output Type field is blank, the cmdlet doesn't return data.

## NOTES

## RELATED LINKS
