---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.RemoteConnections-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/import-exchangecertificate
schema: 2.0.0
title: Import-ExchangeCertificate
---

# Import-ExchangeCertificate

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the Import-ExchangeCertificate cmdlet to import certificates on Exchange servers. You use this cmdlet to install certificates that were exported from other servers, and to complete pending certification requests (also known as certificate signing requests or CSRs) from certification authorities (CAs).

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

### FileData
```
Import-ExchangeCertificate -FileData <Byte[]>
 [-Confirm]
 [-DomainController <Fqdn>]
 [-FriendlyName <String>]
 [-Password <SecureString>]
 [-PrivateKeyExportable <Boolean>]
 [-Server <ServerIdParameter>]
 [-WhatIf]
 [<CommonParameters>]
```

### FileName
```
Import-ExchangeCertificate -Instance <String[]>
 [-Confirm]
 [-DomainController <Fqdn>]
 [-FriendlyName <String>]
 [-Password <SecureString>]
 [-PrivateKeyExportable <Boolean>]
 [-Server <ServerIdParameter>]
 [-WhatIf]
 [<CommonParameters>]
```

### Instance
```
Import-ExchangeCertificate -FileName <String>
 [-Confirm]
 [-DomainController <Fqdn>]
 [-FriendlyName <String>]
 [-Password <SecureString>]
 [-PrivateKeyExportable <Boolean>]
 [-Server <ServerIdParameter>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
You can use the Import-ExchangeCertificate cmdlet to import the following types of certificate files on an Exchange server:

- APKCS #7 certificate or chain of certificates file (.p7b or .p7c) that was issued by a certification authority (CA). PKCS #7 is the Cryptographic Message Syntax Standard, a syntax used for digitally signing or encrypting data using public key cryptography, including certificates. For more information, see [PKCS #7 Cryptographic Messaging Syntax Concepts](https://learn.microsoft.com/windows/win32/seccrypto/pkcs--7-concepts).
- A PKCS #12 certificate file (.cer, .crt, .der, .p12, or .pfx) that contains the private key. PKCS #12 is the Personal Information Exchange Syntax Standard, a file format used to store certificates with corresponding private keys that are protected by a password. For more information, see [PKCS #12: Personal Information Exchange Syntax v1.1](https://tools.ietf.org/html/rfc7292).

After you import a certificate on an Exchange server, you need to assign the certificate to one or more Exchange services by using the Enable-ExchangeCertificate cmdlet.

There are many factors to consider when you configure certificates for Transport Layer Security (TLS) and Secure Sockets Layer (SSL) services. You need to understand how these factors might affect your overall configuration. For more information, see [Digital certificates and encryption in Exchange Server](https://learn.microsoft.com/Exchange/architecture/client-access/certificates).

Secure Sockets Layer (SSL) is being replaced by Transport Layer Security (TLS) as the protocol that's used to encrypt data sent between computer systems. They're so closely related that the terms "SSL" and "TLS" (without versions) are often used interchangeably. Because of this similarity, references to "SSL" in Exchange topics, the Exchange admin center and the Exchange Management Shell have often been used to encompass both the SSL and TLS protocols. Typically, "SSL" refers to the actual SSL protocol only when a version is also provided (for example, SSL 3.0). For more information, see [Exchange Server TLS configuration best practices](https://learn.microsoft.com/Exchange/exchange-tls-configuration).

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Import-ExchangeCertificate -Server Mailbox01 -FileName "\\FileServer01\Data\Exported Fabrikam Cert.pfx" -Password (Get-Credential).password
```

In **Exchange 2013**, this example imports the certificate from the PKCS #12 file from \\\\FileServer01\\Data\\Exported Fabrikam Cert.pfx to the Exchange server named Mailbox01. This file requires the password of the file. This certificate could have been exported from another server or issued by a certification authority.

To export the certificate in Exchange 2016 or Exchange 2019, use the FileData parameter as described in Example 2.

### Example 2
```powershell
Import-ExchangeCertificate -Server Mailbox01 -FileData ([System.IO.File]::ReadAllBytes('\\FileServer01\Data\Exported Fabrikam Cert.pfx')) -Password (Get-Credential).password
```

This example imports the same certificate file from Example 1. This method is required in Exchange 2016 and Exchange 2019 because the FileName parameter is not available.

### Example 3
```powershell
Import-ExchangeCertificate -FileData ([System.IO.File]::ReadAllBytes('C:\Certificates\Fabrikam IssuedCert.p7b'))
```

This example imports a chain of certificates from the PKCS #7 file C:\\Certificates\\Fabrikam IssuedCert.p7b on the local Exchange server.

## PARAMETERS

### -FileData

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The FileData parameter specifies the contents of the certificate file that you want to import.

A valid value for this parameter requires you to read the file to a byte-encoded object using the following syntax: `([System.IO.File]::ReadAllBytes('<Path>\<FileName>'))`. You can use this command as the parameter value, or you can write the output to a variable (`$data = [System.IO.File]::ReadAllBytes('<Path>\<FileName>')`) and use the variable as the parameter value (`$data`).

You can use a local path if the certificate file is located on the Exchange server where you're running the command, and this is the same server where you want to install the certificate. Otherwise, use a UNC path (`\\Server\Share`).

When you use this parameter to import PKCS #7 text certificate files, these files contain contain: -----BEGIN CERTIFICATE----- and -----END CERTIFICATE----- or -----BEGIN PKCS7----- and -----END PKCS7----- and have .p7b or .p7c filename extensions.

If the value contains spaces, enclose the value in quotation marks (").

```yaml
Type: Byte[]
Parameter Sets: FileData
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileName

> Applicable: Exchange Server 2013

**Note**: This parameter was removed from Exchange 2016 and Exchange 2019 by the [2022 H1 Cumulative Updates](https://techcommunity.microsoft.com/t5/exchange-team-blog/released-2022-h1-cumulative-updates-for-exchange-server/ba-p/3285026) because it accepts UNC path values. To import a certificate file without using the FileName parameter, use the FileData parameter.

This parameter is available only in Exchange 2013.

The FileName parameter specifies the certificate file that you want to import. Typically, you use this parameter for PKCS #12 binary certificate files that have .cer, .crt, .der, .p12, or .pfx filename extensions. This type of binary certificate file is protected by a password when the file contains the private key or chain of trust.

You can use a local path if the certificate file is located on the Exchange server where you're running the command, and this is the same server where you want to install the certificate. Otherwise, use a UNC path (`\\Server\Share`).

If the value contains spaces, enclose the value in quotation marks (").

```yaml
Type: String
Parameter Sets: Instance
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Instance

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This parameter has been deprecated and is no longer used.

```yaml
Type: String[]
Parameter Sets: FileName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True
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

### -FriendlyName

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The FriendlyName parameter specifies a friendly name for the certificate. The value must be less than 64 characters.

The friendly name value is descriptive text and doesn't affect the functionality of the certificate.

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

### -Password

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Password parameter specifies the password that's required to import the certificate.

You can use the following methods as a value for this parameter:

- `(ConvertTo-SecureString -String '<password>' -AsPlainText -Force)`.
- Before you run this command, store the password as a variable (for example, `$password = Read-Host "Enter password" -AsSecureString`), and then use the variable (`$password`) for the value.
- `(Get-Credential).password` to be prompted to enter the password securely when you run this command.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivateKeyExportable

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The PrivateKeyExportable parameter specifies whether the certificate has an exportable private key and controls whether you can export the certificate from this server. Valid values are:

- $true: The private key is exportable, so you can export the certificate from this server.
- $false: The private key isn't exportable, so you can't export the certificate from this server. This is the default value.

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
