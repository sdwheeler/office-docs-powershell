---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.TransportMailControl-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/add-contentfilterphrase
schema: 2.0.0
title: Add-ContentFilterPhrase
---

# Add-ContentFilterPhrase

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the Add-ContentFilterPhrase cmdlet to define custom words for the Content Filter agent. A custom word is a word or phrase that the administrator sets for the Content Filter agent to evaluate the content of an message and apply appropriate filter processing.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Add-ContentFilterPhrase [-Phrase] <String> -Influence <Influence>
 [-Confirm]
 [-DomainController <Fqdn>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
The Add-ContentFilterPhrase cmdlet adds phrases to the Allow or Block phrases list.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Add-ContentFilterPhrase -Phrase "Free credit report" -Influence BadWord
```

This example adds the phrase Free credit report to the Block phrase list. Any messages that contain this phrase will be marked as spam by the Content Filtering agent.

## PARAMETERS

### -Phrase

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Phrase parameter specifies a custom word or phrase for the Content Filter agent. When you pass an argument, you must enclose the Phrase parameter in quotation marks (") if the phrase contains spaces, for example: "This is a bad phrase". Custom phrases must be less than 257 characters in length.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -Influence

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Influence parameter specifies whether the phrase being added will cause the messages that contain the phrase to be allowed or blocked. Valid values are GoodWord and BadWord.

A message that contains a custom word or phrase that has an Influence value of GoodWord is automatically assigned a spam confidence level (SCL) rating of 0 and therefore bypasses downstream spam processing. A message that contains a custom word or phrase that has an Influence value of BadWord is automatically assigned an SCL rating of 9 and therefore is treated as spam.

```yaml
Type: Influence
Parameter Sets: (All)
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
