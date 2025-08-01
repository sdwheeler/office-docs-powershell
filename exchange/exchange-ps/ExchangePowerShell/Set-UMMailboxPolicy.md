---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016
author: chrisda
external help file: Microsoft.Exchange.MediaAndDevices-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/set-ummailboxpolicy
schema: 2.0.0
title: Set-UMMailboxPolicy
---

# Set-UMMailboxPolicy

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the Set-UMMailboxPolicy cmdlet to modify a Unified Messaging (UM) mailbox policy.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Set-UMMailboxPolicy [-Identity] <MailboxPolicyIdParameter>
 [-AllowAutomaticSpeechRecognition <Boolean>]
 [-AllowCallAnsweringRules <Boolean>]
 [-AllowCommonPatterns <Boolean>]
 [-AllowDialPlanSubscribers <Boolean>]
 [-AllowedInCountryOrRegionGroups <MultiValuedProperty>]
 [-AllowedInternationalGroups <MultiValuedProperty>]
 [-AllowExtensions <Boolean>]
 [-AllowFax <Boolean>]
 [-AllowMessageWaitingIndicator <Boolean>]
 [-AllowMissedCallNotifications <Boolean>]
 [-AllowPinlessVoiceMailAccess <Boolean>]
 [-AllowPlayOnPhone <Boolean>]
 [-AllowSMSNotification <Boolean>]
 [-AllowSubscriberAccess <Boolean>]
 [-AllowTUIAccessToCalendar <Boolean>]
 [-AllowTUIAccessToDirectory <Boolean>]
 [-AllowTUIAccessToEmail <Boolean>]
 [-AllowTUIAccessToPersonalContacts <Boolean>]
 [-AllowVoiceMailAnalysis <Boolean>]
 [-AllowVoiceMailPreview <Boolean>]
 [-AllowVoiceResponseToOtherMessageTypes <Boolean>]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-FaxMessageText <String>]
 [-FaxServerURI <String>]
 [-ForceUpgrade]
 [-InformCallerOfVoiceMailAnalysis <Boolean>]
 [-LogonFailuresBeforePINReset <Unlimited>]
 [-MaxGreetingDuration <Int32>]
 [-MaxLogonAttempts <Unlimited>]
 [-MinPINLength <Int32>]
 [-Name <String>]
 [-PINHistoryCount <Int32>]
 [-PINLifetime <Unlimited>]
 [-ProtectAuthenticatedVoiceMail <DRMProtectionOptions>]
 [-ProtectedVoiceMailText <String>]
 [-ProtectUnauthenticatedVoiceMail <DRMProtectionOptions>]
 [-RequireProtectedPlayOnPhone <Boolean>]
 [-ResetPINText <String>]
 [-SourceForestPolicyNames <MultiValuedProperty>]
 [-UMDialPlan <UMDialPlanIdParameter>]
 [-UMEnabledText <String>]
 [-VoiceMailPreviewPartnerAddress <SmtpAddress>]
 [-VoiceMailPreviewPartnerAssignedID <String>]
 [-VoiceMailPreviewPartnerMaxDeliveryDelay <Int32>]
 [-VoiceMailPreviewPartnerMaxMessageDuration <Int32>]
 [-VoiceMailText <String>]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
When the Set-UMMailboxPolicy cmdlet is used to modify UM mailbox policy objects, you can change settings such as PIN policies, message text settings, and dialing restrictions for a single UM-enabled recipient or multiple UM-enabled recipients. UM mailbox policies are associated with UM-enabled mailboxes and can be configured to increase the level of security for UM-enabled users.

After this task is completed, the parameters and values specified are configured on the UM mailbox policy.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Set-UMMailboxPolicy -Identity MyUMMailboxPolicy -LogonFailuresBeforePINReset 8 -MaxLogonAttempts 12 -MinPINLength 8 -PINHistoryCount 10 -PINLifetime 60 -ResetPINText "The PIN used to allow you access to your mailbox using Outlook Voice Access has been reset."
```

This example sets the PIN settings for users associated with the UM mailbox policy MyUMMailboxPolicy.

### Example 2
```powershell
Set-UMMailboxPolicy -Identity MyUMMailboxPolicy -AllowDialPlanSubscribers $true -AllowedInCountryOrRegionGroups InCountry/RegionGroup1,InCountry/RegionGroup2 -AllowedInternationalGroups InternationalGroup1,InternationalGroup2 -AllowExtensions $true
```

This example selects the in-country or region groups and international groups from those configured on the UM dial plan associated with the UM mailbox policy. UM-enabled users associated with this UM mailbox policy can place outbound calls according to the rules defined on these groups.

### Example 3
```powershell
Set-UMMailboxPolicy -Identity MyUMMailboxPolicy -UMEnabledText "You have been enabled for Unified Messaging." -VoiceMailText "You have received a voice mail message from Microsoft Exchange Unified Messaging."
```

This example configures the text of voice mail messages sent to UM-enabled users and the text included in an email message sent to a user who is UM-enabled.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The Identity parameter specifies the identifier for the UM mailbox policy being modified. This is the directory object ID for the UM mailbox policy.

```yaml
Type: MailboxPolicyIdParameter
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -AllowAutomaticSpeechRecognition

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowAutomaticSpeechRecognition parameter specifies whether users associated with the UM mailbox policy can use Automatic Speech Recognition (ASR). The default value is $true.

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

### -AllowCallAnsweringRules

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowCallAnsweringRules parameter specifies whether users associated with the UM mailbox policy are allowed to configure or set up Call Answering Rules for their accounts. The default value is $true.

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

### -AllowCommonPatterns

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowCommonPatterns parameter specifies whether to allow obvious PINs. Examples of obvious PINs include subsets of the telephone number, sequential numbers, or repeated numbers. If set to $false, sequential and repeated numbers and the suffix of the mailbox extension are rejected. If set to $true, only the suffix of the mailbox extension is rejected.

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

### -AllowDialPlanSubscribers

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowDialPlanSubscribers parameter specifies whether to let subscribers in a dial plan dial a number that resolves to another subscriber within the same dial plan. The default value is $true.

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

### -AllowedInCountryOrRegionGroups

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowedInCountryOrRegionGroups parameter specifies whether to let subscribers dial the list of in-country/region dial group names. The names that subscribers are allowed to dial must match the group names defined in the UM dial plan. The string is limited to 128 characters.

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

### -AllowedInternationalGroups

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowedInternationalGroups parameter specifies whether to let subscribers dial the list of international dial group names. The names that subscribers dial must match the group names defined in the dial plan.

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

### -AllowExtensions

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowExtensions parameter specifies whether to let subscribers dial calls to the number of digits specified on the UM dial plan. The default value is $true.

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

### -AllowFax

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowFax parameter specifies whether users associated with the UM mailbox policy are allowed to receive incoming faxes. The default value is $true.

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

### -AllowMessageWaitingIndicator

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowMessageWaitingIndicator parameter specifies whether users associated with the UM mailbox policy can receive notifications that they've received a new voice mail message. The default value is $true.

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

### -AllowMissedCallNotifications

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowMissedCallNotifications parameter specifies whether missed call notifications are enabled for users associated with the UM mailbox policy. The default value is $true.

When you're integrating Unified Messaging and Lync Server or Skype for Business Server, missed call notifications aren't available to users who have mailboxes located on Exchange 2010 Mailbox servers. A missed call notification is generated when a user disconnects before the call is sent to a Mailbox server.

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

### -AllowPinlessVoiceMailAccess

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowPinlessVoiceMailAccess parameter specifies whether users associated with the UM mailbox policy are required to use a PIN to access their voice mail. A PIN is still required to access their email and calendar. The default value is $false.

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

### -AllowPlayOnPhone

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowPlayOnPhone parameter specifies whether users associated with the UM mailbox policy can use the Play on Phone feature to listen to voice mail messages. The default value is $true.

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

### -AllowSMSNotification

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowSMSNotification parameter specifies whether UM-enabled users associated with the UM mailbox policy are allowed to get SMS or text messages sent to their mobile phones. If this parameter is set to $true, you also want to set the Set-UMMailbox cmdlet UMSMSNotificationOption parameter for the UM-enabled user to either VoiceMail or VoiceMailAndMissedCalls. The default value is $true.

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

### -AllowSubscriberAccess

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowSubscriberAccess parameter specifies whether users associated with the UM mailbox policy are allowed subscriber access to their individual mailboxes. If this parameter is set to $true, after users are authenticated, they're able to retrieve voice mail over the telephone. The default value is $true.

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

### -AllowTUIAccessToCalendar

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowTUIAccessToCalendar parameter specifies whether users associated with the UM mailbox policy can access their individual calendars over the telephone. The default value is $true.

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

### -AllowTUIAccessToDirectory

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowTUIAccessToDirectory parameter specifies whether users associated with the UM mailbox policy can access the directory over the telephone. The default value is $true.

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

### -AllowTUIAccessToEmail

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowTUIAccessToEmail parameter specifies whether users associated with the UM mailbox policy can access their individual email messages over the telephone. The default value is $true.

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

### -AllowTUIAccessToPersonalContacts

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowTUIAccessToPersonalContacts parameter specifies whether users associated with the UM mailbox policy can access their personal contacts over the telephone. The default value is $true.

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

### -AllowVoiceMailAnalysis

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowVoiceMailAnalysis parameter specifies whether a copy of each voice mail left for the users associated with the UM mailbox policy will be forwarded to Microsoft for analysis and improvement of our speech recognition features.

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

### -AllowVoiceMailPreview

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowVoiceMailPreview parameter specifies whether users associated with the UM mailbox policy are able to receive Voice Mail Previews for call-answered messages, or have Voice Mail Previews provided for voice mail messages that they send to other users in their mailbox. The default value is $true.

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

### -AllowVoiceResponseToOtherMessageTypes

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The AllowVoiceResponseToOtherMessageTypes parameter specifies whether UM-enabled users associated with the UM mailbox policy can record and attach a voice mail message when replying to email messages and calendar items.

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

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

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

### -FaxMessageText

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The FaxMessageText parameter specifies the text included in the body part of fax messages. This text is limited to 512 characters.

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

### -FaxServerURI

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The FaxServerURI parameter specifies the Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) for the fax solution that serves the UM-enabled users associated with the UM mailbox policy. This fax product or fax service accepts incoming fax calls that were redirected from Exchange Unified Messaging servers and creates inbound fax messages for the UM-enabled users associated with the UM mailbox policy. Although you can enter more than one fax server URI, only one URI will be used by the Unified Messaging server.

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

### -ForceUpgrade

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The ForceUpgrade switch suppresses the confirmation message that appears if the object was created in a previous version of Exchange. You don't need to specify a value with this switch.

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

### -InformCallerOfVoiceMailAnalysis

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The InformCallerOfVoiceMailAnalysis parameter specifies whether the callers leaving the voice mails will be informed about the possibility of their voice mails being forwarded to Microsoft for analysis.

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

### -LogonFailuresBeforePINReset

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The LogonFailuresBeforePINReset parameter specifies the number of sequential unsuccessful logon attempts before the mailbox PIN is automatically reset. To disable this feature, set this parameter to Unlimited. If this parameter isn't set to Unlimited, it must be set to less than the value of the MaxLogonAttempts parameter. The range is from 0 through 999. The default setting is 5.

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

### -MaxGreetingDuration

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The MaxGreetingDuration parameter specifies the maximum greeting length. The range is from 1 through 10 minutes. The default value is 5 minutes.

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

### -MaxLogonAttempts

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The MaxLogonAttempts parameter specifies the number of times users can try unsuccessfully to log on, in sequence, before the UM mailboxes are locked. The range is from 1 through 999. The default value is 15.

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

### -MinPINLength

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The MinPINLength parameter specifies the minimum number of digits required in a PIN for UM-enabled users. The range is from 4 through 24. The default value is 6.

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

### -Name

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The Name parameter specifies the display name for the UM mailbox policy. This setting is limited to 64 characters.

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

### -PINHistoryCount

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The PINHistoryCount parameter specifies the number of previous PINs that are remembered and aren't allowed during a PIN reset. This number includes the first time that the PIN was set. The range is from 1 through 20. The default value is 5.

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

### -PINLifetime

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The PINLifetime parameter specifies the number of days until a new password is required. The range is from 1 through 999. The default value is 60. If you specify Unlimited, the users' PINs won't expire.

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

### -ProtectAuthenticatedVoiceMail

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The ProtectAuthenticatedVoiceMail parameter specifies whether Mailbox servers that answer Outlook Voice Access calls for UM-enabled users associated with the UM mailbox policy create protected voice mail messages. The default setting is None. This means that no protection is applied to voice mail messages. If the value is set to Private, only messages marked as private are protected. If the value is set to All, every voice mail message is protected.

```yaml
Type: DRMProtectionOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectedVoiceMailText

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The ProtectedVoiceMailText parameter specifies the text included in the body part of the protected voice mail messages for UM-enabled users associated with the UM mailbox policy. This text can contain up to 512 characters.

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

### -ProtectUnauthenticatedVoiceMail

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The ProtectUnauthenticatedVoiceMail parameter specifies whether the Mailbox servers that answer calls for UM-enabled users associated with the UM mailbox policy create protected voice mail messages. This also applies when a message is sent from a UM auto attendant to a UM-enabled user associated with the UM mailbox policy. The default setting is None. This means that no protection is applied to voice mail messages. If the value is set to Private, only messages marked as private are protected. If the value is set to All, every voice mail message is protected.

```yaml
Type: DRMProtectionOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequireProtectedPlayOnPhone

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The RequireProtectedPlayOnPhone parameter specifies whether users associated with the UM mailbox policy can only use Play on Phone for protected voice mail messages or whether users can use multimedia software to play the protected message. The default value is $false. When set to $false, users are able to use both methods to listen to protected voice mail messages.

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

### -ResetPINText

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The ResetPINText parameter specifies the text to be included in the PIN reset email message. This text is limited to 512 characters.

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

### -SourceForestPolicyNames

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The SourceForestPolicyNames parameter specifies the name or names of the corresponding UM mailbox policy objects located in the source forest during a cross-forest migration.

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

### -UMDialPlan

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The UMDialPlan parameter specifies the UM dial plan associated with the UM mailbox policy.

```yaml
Type: UMDialPlanIdParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UMEnabledText

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The UMEnabledText parameter specifies the text to be included when a user is enabled for Unified Messaging. This text is limited to 512 characters.

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

### -VoiceMailPreviewPartnerAddress

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The VoiceMailPreviewPartnerAddress parameter specifies the SMTP address of a Voice Mail Preview partner that's contracted to provide transcription services for UM-enabled users in this UM mailbox policy. The default value is $null.

```yaml
Type: SmtpAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VoiceMailPreviewPartnerAssignedID

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The VoiceMailPreviewPartnerAssignedID parameter specifies the identification string, if any, provided to the organization by the Voice Mail Preview partner that's contracted to provide transcription services for UM-enabled users in this UM mailbox policy. The default value is $null.

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

### -VoiceMailPreviewPartnerMaxDeliveryDelay

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The VoiceMailPreviewPartnerMaxDeliveryDelay parameter specifies the number of seconds that a Mailbox server waits for a Voice Mail Preview partner system to return a message with a Voice Mail Preview. If this time is exceeded, the Mailbox server delivers the voice mail message without a preview. The default value is 1200. The minimum value for this parameter is 300.

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

### -VoiceMailPreviewPartnerMaxMessageDuration

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The VoiceMailPreviewPartnerMaxMessageDuration parameter specifies the maximum duration, in seconds, of voice mail messages sent to the Voice Mail Preview partner that's contracted to provide transcription services for UM-enabled users in this UM mailbox policy. The default value is 180. The minimum number for this parameter is 60. This setting should be set equal to the maximum value allowed by the Voice Mail Preview partner.

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

### -VoiceMailText

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

The VoiceMailText parameter specifies the text to be included in the body part of voice mail messages. The parameter applies to call answering messages in addition to messages originated by an authenticated subscriber. This text is limited to 512 characters.

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

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

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
