---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.RemoteConnections-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/get-exchangecertificate
schema: 2.0.0
title: Get-ExchangeCertificate
---

# Get-ExchangeCertificate

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the Get-ExchangeCertificate cmdlet to view Exchange certificates that are installed on Exchange servers. This cmdlet returns Exchange self-signed certificates, certificates that were issued by a certification authority and pending certificate requests (also known as certificate signing requests or CSRs).

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

### Identity
```
Get-ExchangeCertificate [[-Identity] <ExchangeCertificateIdParameter>]
 [-DomainController <Fqdn>]
 [-DomainName <MultiValuedProperty>]
 [<CommonParameters>]
```

### Instance
```
Get-ExchangeCertificate [-Instance <X509Certificate2>]
 [-DomainController <Fqdn>]
 [-DomainName <MultiValuedProperty>]
 [-Server <ServerIdParameter>]
 [<CommonParameters>]
```

### Thumbprint
```
Get-ExchangeCertificate [[-Thumbprint] <String>]
 [-DomainController <Fqdn>]
 [-DomainName <MultiValuedProperty>]
 [-Server <ServerIdParameter>]
 [<CommonParameters>]
```

## DESCRIPTION
By default, this cmdlet returns the following certificate properties in the summary list view:

- Thumbprint: The unique digest of the certificate data. An example thumbprint value is 78E1BE82F683EE6D8CB9B9266FC1185AE0890C41.
- Services: The Exchange services that the certificate is assigned to by using the Enable-ExchangeCertificate cmdlet. Values are None, Federation, IIS, IMAP, POP, SMTP, UM, and UMCallRouter. You'll see the value None in certificates that aren't used with Exchange (for example, the `WMSvc-<ServerName>` certificate that's used for the IIS Web Management Service).
- Subject: Contains the X.500 value in the certificate's Subject Name field. The important part is the CN= value.

If you append ` | Format-List` to the command, the cmdlet returns these additional certificate properties:

- AccessRules: Typically, this value is multiple instances of the value System.Security.AccessControl.CryptoKeyAccessRule separated by commas.
- CertificateDomains: The host names or FQDNs in the certificate's Subject Alternative Name field.
- HasPrivateKey: Whether or not the certificate contains a private key.
- IsSelfSigned: Whether or not the certificate is self-signed (not issued by a certification authority).
- Issuer: Who issued the certificate.
- NotAfter: The certificate expiration date.
- NotBefore: The certificate issue date.
- PublicKeySize: The size of the public key in bytes.
- RootCAType: The type of CA that signed the certificate. Values are None (this value is found on the Microsoft Exchange Server Auth Certificate, and also new self-signed certificates that you create), ThirdParty, Enterprise, Registry (this value is found on Exchange self-signed certificates), GroupPolicy, or Unknown (this value is found on pending certificate requests).
- SerialNumber: The unique serial number of the certificate.
- Status: The status of the certificate. Values are DateInvalid, Invalid, PendingRequest, RevocationCheckFailure, Revoked, Unknown, Untrusted or Valid

If you append ` | Format-List *` to the command, the cmdlet returns these additional certificate properties:

- Archived
- CertificateRequest: This property contains the hash value of the certificate request.
- DnsNameList
- EnhancedKeyUsageList: Typically, this value is Server Authentication (1.3.6.1.5.5.7.3.1).
- Extensions
- FriendlyName
- Handle
- Identity: This value uses the syntax ServerFQDN\\Thumbprint.
- IISServices
- IssuerName: Typically, this value is System.Security.Cryptography.X509Certificates.X500DistinguishedName.
- KeyIdentifier
- PrivateKey: Typically, this value is System.Security.Cryptography.RSACryptoServiceProvider.
- PrivateKeyExportable: If this value is True, you can export the certificate from the server.
- PublicKey: Typically, this value is System.Security.Cryptography.RSACryptoServiceProvider.
- RawData
- SendAsTrustedIssuer
- ServicesStringForm
- SignatureAlgorithm: Typically, this value is System.Security.Cryptography.Oid.
- SubjectKeyIdentifier
- SubjectName: Typically, this value is System.Security.Cryptography.X509Certificates.X500DistinguishedName.
- Version: Typically, this value is 3.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Get-ExchangeCertificate -Server Mailbox01
```

This example returns a summary list of all Exchange certificates and pending certificate requests on the server named Mailbox01.

### Example 2
```powershell
Get-ExchangeCertificate -Thumbprint 0271A7F1CA9AD8A27152CCAE044F968F068B14B8 | Format-List
```

This example returns detailed information for the specified certificate.

### Example 3
```powershell
Get-ExchangeCertificate -Thumbprint 0271A7F1CA9AD8A27152CCAE044F968F068B14B8 | Format-List *
```

This example returns all available information for the specified certificate.

### Example 4
```powershell
Get-ExchangeCertificate -DomainName mail.contoso.com
```

This example shows which certificate Exchange will select for the domain name mail.contoso.com. A Send connector or Receive connector selects the certificate to use based on the fully qualified domain name (FQDN) of the connector. If you have multiple certificates with the same FQDN, you can see which certificate Exchange will select by using the DomainName parameter to specify the FQDN. The first certificate returned is the certificate that Exchange will select.

## PARAMETERS

### -Thumbprint

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Thumbprint parameter specifies the thumbprint value of the certificate that you want to view.

The Thumbprint parameter, not the Identity parameter, is the positional parameter for this cmdlet. Therefore, when you specify a thumbprint value by itself, the command uses that value for the Thumbprint parameter.

```yaml
Type: String
Parameter Sets: Thumbprint
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -Identity

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Identity parameter specifies the certificate that you want to view. Valid values are:

- `ServerNameOrFQDN\Thumbprint`
- `Thumbprint`

You can't use this parameter with the Server parameter.

The Thumbprint parameter, not the Identity parameter, is the positional parameter for this cmdlet. Therefore, when you specify a thumbprint value by itself, the command uses that value for the Thumbprint parameter.

```yaml
Type: ExchangeCertificateIdParameter
Parameter Sets: Identity
Aliases:

Required: False
Position: 1
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

### -DomainName

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The DomainName parameter filters the results by the fully qualified domain name (FQDN) or server name values in the Subject Name or the Subject Alternative Name fields. You can specify multiple values separated by commas.

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

### -Instance

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

This parameter has been deprecated and is no longer used.

```yaml
Type: X509Certificate2
Parameter Sets: Instance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True
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

You can't use this parameter with the Identity parameter, but you can use it with the Thumbprint parameter, or by itself.

```yaml
Type: ServerIdParameter
Parameter Sets: Instance, Thumbprint
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
