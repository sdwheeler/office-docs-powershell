---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: tomkau
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: bulenteg
Module Name: SkypeForBusiness
ms.author: tomkau
ms.reviewer: rogupta
online version: https://learn.microsoft.com/powershell/module/skypeforbusiness/set-csclientpolicy
schema: 2.0.0
title: Set-CsClientPolicy
---

# Set-CsClientPolicy

## SYNOPSIS
Modifies the property values of an existing client policy.
Among other things, client policies help determine the features of Skype for Business that are available to users; for example, you might give some users the right to transfer files while denying this right to other users.
This cmdlet was introduced in Lync Server 2010.


## SYNTAX

### Identity (Default)
```
Set-CsClientPolicy [-Tenant <Guid>] [-PolicyEntry <PSListModifier>] [-Description <String>]
 [-AddressBookAvailability <AddressBookAvailability>] [-AttendantSafeTransfer <Boolean>]
 [-AutoDiscoveryRetryInterval <TimeSpan>] [-BlockConversationFromFederatedContacts <Boolean>]
 [-CalendarStatePublicationInterval <UInt32>] [-CustomizedHelpUrl <String>]
 [-CustomLinkInErrorMessages <String>] [-CustomStateUrl <String>] [-DGRefreshInterval <TimeSpan>]
 [-DisableCalendarPresence <Boolean>] [-DisableContactCardOrganizationTab <Boolean>]
 [-DisableEmailComparisonCheck <Boolean>] [-DisableEmoticons <Boolean>]
 [-DisableFeedsTab <Boolean>] [-DisableFederatedPromptDisplayName <Boolean>]
 [-DisableFreeBusyInfo <Boolean>] [-DisableHandsetOnLockedMachine <Boolean>]
 [-DisableMeetingSubjectAndLocation <Boolean>] [-DisableHtmlIm <Boolean>]
 [-DisableInkIM <Boolean>] [-DisableOneNote12Integration <Boolean>]
 [-DisableOnlineContextualSearch <Boolean>] [-DisablePhonePresence <Boolean>]
 [-DisablePICPromptDisplayName <Boolean>] [-DisablePoorDeviceWarnings <Boolean>]
 [-DisablePoorNetworkWarnings <Boolean>] [-DisablePresenceNote <Boolean>]
 [-DisableRTFIM <Boolean>] [-DisableSavingIM <Boolean>] [-DisplayPhoto <DisplayPhoto>]
 [-EnableAppearOffline <Boolean>] [-EnableCallLogAutoArchiving <Boolean>]
 [-EnableClientAutoPopulateWithTeam <Boolean>] [-EnableClientMusicOnHold <Boolean>]
 [-EnableConversationWindowTabs <Boolean>] [-EnableEnterpriseCustomizedHelp <Boolean>]
 [-EnableEventLogging <Boolean>] [-EnableExchangeContactSync <Boolean>]
 [-EnableExchangeDelegateSync <Boolean>] [-EnableExchangeContactsFolder <Boolean>]
 [-EnableFullScreenVideo <Boolean>] [-EnableHighPerformanceConferencingAppSharing <Boolean>]
 [-EnableHotdesking <Boolean>] [-EnableIMAutoArchiving <Boolean>]
 [-EnableMediaRedirection <Boolean>] [-EnableMeetingEngagement <Boolean>]
 [-EnableNotificationForNewSubscribers <Boolean>] [-EnableServerConversationHistory <Boolean>]
 [-EnableSkypeUI <Boolean>] [-EnableSQMData <Boolean>] [-EnableTracing <Boolean>]
 [-EnableURL <Boolean>] [-EnableUnencryptedFileTransfer <Boolean>]
 [-EnableVOIPCallDefault <Boolean>] [-ExcludedContactFolders <String>] [-HotdeskingTimeout <TimeSpan>]
 [-IMWarning <String>] [-MAPIPollInterval <TimeSpan>] [-MaximumDGsAllowedInContactList <UInt32>]
 [-MaximumNumberOfContacts <UInt16>] [-MaxPhotoSizeKB <UInt32>] [-MusicOnHoldAudioFile <String>]
 [-P2PAppSharingEncryption <P2PAppSharingEncryption>] [-EnableHighPerformanceP2PAppSharing <Boolean>]
 [-PlayAbbreviatedDialTone <Boolean>] [-RequireContentPin <String>] [-SearchPrefixFlags <UInt16>]
 [-ShowRecentContacts <Boolean>] [-ShowManagePrivacyRelationships <Boolean>]
 [-ShowSharepointPhotoEditLink <Boolean>] [-SPSearchInternalURL <String>] [-SPSearchExternalURL <String>]
 [-SPSearchCenterInternalURL <String>] [-SPSearchCenterExternalURL <String>] [-TabURL <String>]
 [-TracingLevel <TracingLevel>] [-TelemetryTier <String>] [-PublicationBatchDelay <UInt32>]
 [-EnableViewBasedSubscriptionMode <Boolean>] [-WebServicePollInterval <TimeSpan>]
 [-HelpEnvironment <String>] [-RateMyCallDisplayPercentage <UInt16>]
 [-RateMyCallAllowCustomUserFeedback <Boolean>] [-IMLatencySpinnerDelay <UInt32>]
 [-IMLatencyErrorThreshold <UInt32>] [-SupportModernFilePicker <Boolean>] [-EnableOnlineFeedback <Boolean>]
 [-EnableOnlineFeedbackScreenshots <Boolean>] [-ConferenceIMIdleTimeout <TimeSpan>]
 [[-Identity] <XdsIdentity>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Instance
```
Set-CsClientPolicy [-Tenant <Guid>] [-PolicyEntry <PSListModifier>] [-Description <String>]
 [-AddressBookAvailability <AddressBookAvailability>] [-AttendantSafeTransfer <Boolean>]
 [-AutoDiscoveryRetryInterval <TimeSpan>] [-BlockConversationFromFederatedContacts <Boolean>]
 [-CalendarStatePublicationInterval <UInt32>] [-CustomizedHelpUrl <String>]
 [-CustomLinkInErrorMessages <String>] [-CustomStateUrl <String>] [-DGRefreshInterval <TimeSpan>]
 [-DisableCalendarPresence <Boolean>] [-DisableContactCardOrganizationTab <Boolean>]
 [-DisableEmailComparisonCheck <Boolean>] [-DisableEmoticons <Boolean>]
 [-DisableFeedsTab <Boolean>] [-DisableFederatedPromptDisplayName <Boolean>]
 [-DisableFreeBusyInfo <Boolean>] [-DisableHandsetOnLockedMachine <Boolean>]
 [-DisableMeetingSubjectAndLocation <Boolean>] [-DisableHtmlIm <Boolean>]
 [-DisableInkIM <Boolean>] [-DisableOneNote12Integration <Boolean>]
 [-DisableOnlineContextualSearch <Boolean>] [-DisablePhonePresence <Boolean>]
 [-DisablePICPromptDisplayName <Boolean>] [-DisablePoorDeviceWarnings <Boolean>]
 [-DisablePoorNetworkWarnings <Boolean>] [-DisablePresenceNote <Boolean>]
 [-DisableRTFIM <Boolean>] [-DisableSavingIM <Boolean>] [-DisplayPhoto <DisplayPhoto>]
 [-EnableAppearOffline <Boolean>] [-EnableCallLogAutoArchiving <Boolean>]
 [-EnableClientAutoPopulateWithTeam <Boolean>] [-EnableClientMusicOnHold <Boolean>]
 [-EnableConversationWindowTabs <Boolean>] [-EnableEnterpriseCustomizedHelp <Boolean>]
 [-EnableEventLogging <Boolean>] [-EnableExchangeContactSync <Boolean>]
 [-EnableExchangeDelegateSync <Boolean>] [-EnableExchangeContactsFolder <Boolean>]
 [-EnableFullScreenVideo <Boolean>] [-EnableHighPerformanceConferencingAppSharing <Boolean>]
 [-EnableHotdesking <Boolean>] [-EnableIMAutoArchiving <Boolean>]
 [-EnableMediaRedirection <Boolean>] [-EnableMeetingEngagement <Boolean>]
 [-EnableNotificationForNewSubscribers <Boolean>] [-EnableServerConversationHistory <Boolean>]
 [-EnableSkypeUI <Boolean>] [-EnableSQMData <Boolean>] [-EnableTracing <Boolean>]
 [-EnableURL <Boolean>] [-EnableUnencryptedFileTransfer <Boolean>]
 [-EnableVOIPCallDefault <Boolean>] [-ExcludedContactFolders <String>] [-HotdeskingTimeout <TimeSpan>]
 [-IMWarning <String>] [-MAPIPollInterval <TimeSpan>] [-MaximumDGsAllowedInContactList <UInt32>]
 [-MaximumNumberOfContacts <UInt16>] [-MaxPhotoSizeKB <UInt32>] [-MusicOnHoldAudioFile <String>]
 [-P2PAppSharingEncryption <P2PAppSharingEncryption>] [-EnableHighPerformanceP2PAppSharing <Boolean>]
 [-PlayAbbreviatedDialTone <Boolean>] [-RequireContentPin <String>] [-SearchPrefixFlags <UInt16>]
 [-ShowRecentContacts <Boolean>] [-ShowManagePrivacyRelationships <Boolean>]
 [-ShowSharepointPhotoEditLink <Boolean>] [-SPSearchInternalURL <String>] [-SPSearchExternalURL <String>]
 [-SPSearchCenterInternalURL <String>] [-SPSearchCenterExternalURL <String>] [-TabURL <String>]
 [-TracingLevel <TracingLevel>] [-TelemetryTier <String>] [-PublicationBatchDelay <UInt32>]
 [-EnableViewBasedSubscriptionMode <Boolean>] [-WebServicePollInterval <TimeSpan>]
 [-HelpEnvironment <String>] [-RateMyCallDisplayPercentage <UInt16>]
 [-RateMyCallAllowCustomUserFeedback <Boolean>] [-IMLatencySpinnerDelay <UInt32>]
 [-IMLatencyErrorThreshold <UInt32>] [-SupportModernFilePicker <Boolean>] [-EnableOnlineFeedback <Boolean>]
 [-EnableOnlineFeedbackScreenshots <Boolean>] [-ConferenceIMIdleTimeout <TimeSpan>]
 [-Instance <PSObject>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Client policies are applied each time a user accesses the system, regardless of where the user logs on from and regardless of the type of device the user logs on with.
In addition, client policies, like other Skype for Business Server policies, can readily be targeted toward selected groups of users.
You can even create a custom policy that gets assigned to a single user.

Client policies can be configured at the global, site and per-user scopes.
The `Set-CsClientPolicy` cmdlet enables you to modify any (or all) of the client policies that have been configured for use in your organization.

Keep in mind that client policies differ from many other policies in that most of the policy settings do not have default values. When setting is null/none just means that server in band provisioning does not override default client value. Basically, default values are set by client for these cases.

The following parameters are not applicable to Skype for Business Online: AddressBookAvailability, AttendantSafeTransfer, AutoDiscoveryRetryInterval, BlockConversationFromFederatedContacts, CalendarStatePublicationInterval, ConferenceIMIdleTimeout, CustomizedHelpUrl, CustomLinkInErrorMessages, CustomStateUrl, Description, DGRefreshInterval, DisableContactCardOrganizationTab, DisableFederatedPromptDisplayName, DisableFeedsTab, DisableMeetingSubjectAndLocation, DisableOneNote12Integration, DisableOnlineContextualSearch, DisablePhonePresence, DisablePICPromptDisplayName, EnableEventLogging, EnableExchangeContactsFolder, EnableExchangeDelegateSync, EnableFullScreenVideo, EnableHighPerformanceConferencingAppSharing, EnableHighPerformanceP2PAppSharing, EnableMediaRedirection, EnableMeetingEngagement, EnableNotificationForNewSubscribers, EnableOnlineFeedback, EnableOnlineFeedbackScreenshots, EnableSQMData, EnableTracing, EnableViewBasedSubscriptionMode, EnableVOIPCallDefault, Force, HelpEnvironment, Identity, IMLatencyErrorThreshold, IMLatencySpinnerDelay, Instance, MAPIPollInterval, MaximumDGsAllowedInContactList, MaximumNumberOfContacts, MaxPhotoSizeKB, P2PAppSharingEncryption, PipelineVariable, PolicyEntry, PublicationBatchDelay, RateMyCallAllowCustomUserFeedback, RequireContentPin, SearchPrefixFlags, SPSearchCenterExternalURL, SPSearchCenterInternalURL, SPSearchExternalURL, SPSearchInternalURL, SupportModernFilePicker, TabURL, TelemetryTier, Tenant, and WebServicePollInterval

## EXAMPLES

### Example 1
```
Set-CsClientPolicy -Identity RedmondClientPolicy -WebServicePollInterval "00:15:00"
```

The command shown in Example 1 modifies the client policy RedmondClientPolicy.
In this example, the WebServicePollInterval property is set to 15 minutes (00 hours: 15 minutes: 00 seconds).


### Example 2
```
Set-CsClientPolicy -Identity RedmondClientPolicy -DisableEmoticons $True -DisableHtmlIm $True -DisableRTFIm $True
```

In Example 2, three different property values are modified for the client policy RedmondClientPolicy: the properties DisableEmoticons, DisableHtmlIm, and DisableRTFIm are all set to True.


### Example 3
```
Get-CsClientPolicy -Filter "*site:*" | Set-CsClientPolicy -DisableEmoticons $True -DisableHtmlIm $True -DisableRTFIm $True
```

Example 3 also modifies the properties DisableEmoticons, DisableHtmlIm and DisableRTFIm.
In this example, however, the modifications are made to all the client policies that have been configured at the site scope.
To do this, the command first uses the `Get-CsClientPolicy` cmdlet and the Filter property to return all the client policies where the Identity begins with the characters "site:"; by definition, those are policies configured at the site scope.
This filtered collection is then piped to the `Set-CsClientPolicy` cmdlet, which takes each policy in the collection and modifies the values of DisableEmoticons, DisableHtmlIm and DisableRTFIm.


### Example 4
```
Get-CsClientPolicy | Where-Object {$_.MaxPhotoSizeKb -gt 10} | Set-CsClientPolicy -MaxPhotoSizeKb 10
```

In Example 4, all the client policies that allow for photos larger than 10 kilobytes are modified; after the modifications these policies will have a maximum photo size of 10 KB.
To carry out this task, the `Get-CsClientPolicy` cmdlet is first called without any parameters in order to return a collection of all the client policies configured for use in the organization.
This collection is then piped to the `Where-Object` cmdlet, which picks out only those policies where the MaxPhotoSizeKb property is greater than (-gt) 10 KB.
The filtered collection is then piped to the `Set-CsClientPolicy` cmdlet, which sets the value of the MaxPhotoSizeKb property for each policy in the collection to 10 KB.


## PARAMETERS

### -AddressBookAvailability

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Indicates how users are allowed to access information in the Address Book server (that is, by using the Address Book Web Query service and/or by downloading a copy of the Address Book to their local computer).
AddressBookAvailability must be set to one of the following values:

WebSearchAndFileDownload

WebSearchOnly

FileDownloadOnly


```yaml
Type: AddressBookAvailability
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AttendantSafeTransfer

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, Skype for Business Attendant operates in "safe transfer" mode; this means that transferred calls that do not reach the intended recipient will reappear in the incoming area along with a "Failed Transfer" notice.
When set to False, transferred calls that fail to reach the intended recipient will not reappear in the incoming area.


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

### -AutoDiscoveryRetryInterval

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

After a failed connection attempt, specifies the amount of time Skype for Business waits before again trying to connect to Skype for Business Server.
The AutoDiscoveryRetryInterval can be set to value between 1 second and 60 minutes (1 hour), inclusive.

When specifying the AutoDiscoveryRetryInterval you must use the format hours:minutes:seconds.
For example, to set the interval to 25 minutes use this syntax:

`-AutoDiscoveryRetryInterval 00:25:00`


```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BlockConversationFromFederatedContacts

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, contacts from outside your organization will not be allowed to initiate instant message conversations with any user that this policy applies to.
However, outside users will be able to participate in conversations as long the internal user initiates that conversation.
When set to False, outside contacts are allowed to send unsolicited instant messages to users in your organization.


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

### -CalendarStatePublicationInterval

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Specifies the amount of time, in seconds, that Skype for Business waits before retrieving calendar information from Outlook and adding this data to your presence information.

For example, to set the CalendarStatePublicationInterval to 10 minutes (600 seconds) use this syntax:

`-CalendarStatePublicationInterval 600`


```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConferenceIMIdleTimeout

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Indicates the number of minutes that a user can remain in an instant messaging session without either sending or receiving an instant message.

The ConferenceIMIdleTimeout must be less than or equal to 1 hour and must be specified using the format hours:minutes:seconds.
For example, this syntax sets the timeout value to 45 minutes:

`-ConferenceIMIdleTimeout 00:45:00`


```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomizedHelpUrl

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

URL for custom Skype for Business help set up by an organization.
This parameter has been deprecated for use with Skype for Business Server.

Customized help will not be available unless you also set EnableEnterpriseCustomizedHelp to True.


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

### -CustomLinkInErrorMessages

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

URL for the website that can be added to error messages that appear in Skype for Business.
If a URL is specified, that URL will appear at the bottom of any error message that occurs in Skype for Business.
Users can then click that link and be taken to a custom website that contains additional information, troubleshooting tips, etc.


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

### -CustomStateUrl

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Specifies the location of the XML file used to add custom presence states to Skype for Business.
(Skype for Business allows up to four custom presence states in addition to the built-in states such as Available, Busy and Do Not Disturb.) The location of the XML file should be specified using the HTTPS protocol.


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

### -Description

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Allows administrators to provide additional information about a policy.
For example, the Description might indicate the users that the policy should be assigned to.


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

### -DGRefreshInterval

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Indicates the amount of time Skype for Business waits before automatically refreshing the membership list of any distribution group that has been "expanded" in the Contacts list.
(Expanding a distribution group means displaying all the members in that group.) DGRefreshInterval can be set to any integer value between 30 seconds and 28,800 seconds (8 hours), inclusive.
The default value is 28,800 seconds.


```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableCalendarPresence

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, calendar data taken from Outlook will not be included in your presence information.
When set to False, calendar data will be included in your presence information.
For example, free/busy information will be reported in your contact card; likewise, your status will automatically be set to Busy any time Outlook shows that you are in a meeting.


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

### -DisableContactCardOrganizationTab

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, the contact card organization tab is not visible within the Skype for Business user interface.
When set to False, the contact card organization tab is available in Skype for Business.


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

### -DisableEmailComparisonCheck

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, Skype for Business will not attempt to verify that any currently running instance of Outlook belongs to the same user running Skype for Business; for example, the software will not verify that both Outlook and Skype for Business are running under Ken Myer's user account.
Instead, it will be assumed that the two applications are running under the same account and, in turn, will include contact and calendar data in Outlook with Skype for Business.

When set to False, Skype for Business will use SMTP addresses to verify that Outlook and Skype for Business are running under the same account.
If the SMTP addresses do not match then contact and calendar data in Outlook will not be incorporated into Skype for Business.


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

### -DisableEmoticons

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, users will not be able to send or receive emoticons in their instant messages; instead they will be see the text equivalent of those emoticons.
For example, instead of seeing a graphical "smiley face" users will see the text equivalent:

: )

When set to False users will be able to include emoticons in their instant messages and to view emoticons in instant messages they receive.


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

### -DisableFederatedPromptDisplayName

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, any notification dialog generated when you are added to a federated user's Contacts list will use the federated user's SIP address (for example, sip:kenmyer@fabrikam.com).
When set to False, the notification dialog will use the federated user's display name (for example, Ken Myer) instead.


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

### -DisableFeedsTab

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, the activity feeds tab will not be displayed in Skype for Business.
When set to False, the feeds tab will be available within Skype for Business.


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

### -DisableFreeBusyInfo

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, free/busy information retrieved from Microsoft Outlook will not be displayed in your contact card.
When set to False, free/busy information is displayed in your contact card.
For example, your contact card might include a note similar to this:

Calendar: Free until 2:00 PM


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

### -DisableHandsetOnLockedMachine

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, users will not be able to use their Polycom handset if the computer that the handset is connected to is locked.
To use the handset, users will first have to unlock the computer.

When set to False, users will be allowed to use their handset even if the computer the handset is connected to is locked.


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

### -DisableHtmlIm

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, any HTML text copied from a webpage will be converted to plain text when pasted into an instant message.
When set to False, HTML formatting (such as font size and color, drop-down lists and buttons, etc.) will be retained when pasted into an instant message.

Note that, even when set to False, scripts and other potentially malicious items (such as tags that play a sound) will not be copied into an instant message.
You can copy and paste buttons and other controls into a message, but any scripts attached to those controls will automatically be removed.

This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting "Prevent HTML text in instant messages."


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

### -DisableICE

> Applicable: Lync Server 2010

When set to True, Lync 2010 will not use the Interactive Connectivity Establishment (ICE) protocol to traverse firewalls and network address translation (NAT) devices; this effectively prevents users from making Lync 2010 calls across the Internet.
When set to False, Lync 2010 will use the ICE protocol to enable Lync 2010 calls to traverse firewalls and (NAT) devices.

This setting is equivalent to the Office Communications Server 2007 R2 Group Policy setting "Disable Interactive Connectivity Establishment (ICE)."

```yaml
Type: Boolean
Parameter Sets: Identity, Instance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableInkIM

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, users will not be allowed to receive instant messages containing Tablet PC ink.
(Ink is a technology that enables you to insert handwritten notes into a document.) When set to False, users will be allowed to receive messages that contain Table PC ink.


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

### -DisableMeetingSubjectAndLocation

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to False, detailed information about a meeting -- namely, the meeting subject and the location where the meeting is being held -- will be displayed as a tooltip when you view free/busy information in a contact card.
When set to True, this detailed information will not be displayed.
To completely prevent the display of meeting-related information you should also set DisableCalendarPresence to True.


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

### -DisableOneNote12Integration

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, the ability to start OneNote from within Skype for Business (and the ability to automatically link instant message sessions and OneNote notes) is disabled.
When set to False, the option Take Notes Using One Note is enabled in Skype for Business.
In addition, if you locate an instant message transcript in Microsoft Outlook's Conversation History you can retrieve any OneNote notes associated with that conversation just by clicking the Edit conversation notes button.


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

### -DisableOnlineContextualSearch

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, disables the Find Previous Conversations menu option that appears when you right-click a user in your Contacts list.
(This option enables you to search the Outlook Conversation History folder for previous instant messaging sessions involving the user in question.) When set to False, the Find Previous Conversations option will be available when you right-click a user in your Contacts list.

Note that this setting only applies to users who are not running Outlook in cached mode.
That's because any searches conducted by those users must take place on the Exchange Servers and administrators might want to limit the network traffic causes by these searches.
If you are running Outlook in cached mode, searches take place on a user's locally-cached copy of his or her Inbox.
Cached searches are not affected by this setting.


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

### -DisablePhonePresence

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, Skype for Business does not take phone calls into consideration when determining your current status.
When set to False, phone calls are taken into consideration when determining your status.
For example, any time you are on the phone your status will automatically be set to Busy.


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

### -DisablePICPromptDisplayName

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, any notification dialog box generated when you are added to the Contacts list of a user with an account on a public instant messaging service such as MSN will display that person's SIP address (for example, sip:kenmyer@litwareinc.com).
When set to False, the notification dialog box will use the person's display name (for example, Ken Myer) instead.


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

### -DisablePoorDeviceWarnings

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, Skype for Business will not issue warnings (upon startup, in the Tuning Wizard, in the Conversation window, etc.) if an audio or video device is not working correctly.
When set to False, these warnings will be issued.


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

### -DisablePoorNetworkWarnings

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, Skype for Business will not display warnings about poor network quality.


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

### -DisablePresenceNote

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, any Out of Office message you configure in Outlook will not be displayed as part of your presence information.
When set to False, your Out of Office message will be displayed any time a user holds the mouse over your name in their Contacts list.


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

### -DisableRTFIM

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When both this setting and the DisableHtmlIm settings are set to True, prevents rich text formatting (for example, different fonts, font sizes and font colors) from being used in instant messages; instead, all messages sent and received will be converted to plain text format.
When set to False, rich text formatting will be allowed in instant messages.


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

### -DisableSavingIM

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, the options for saving an instant message session are removed from the menu bar in the Skype for Business Conversation window.
When set to False, these options are available in the Conversation window.

Note that setting this value to True removes the menu options that make it easy for users to save instant message transcripts.
However, it does not prevent users from copying all the text in a transcript to the clipboard, pasting that text into another application and then saving the transcript that way.


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

### -DisplayPhoto

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Determines whether or not photos (of both the user and his or her contacts) will be displayed in Skype for Business.
Valid settings are:

NoPhoto - Photos are not displayed in Skype for Business.

PhotosFromADOnly - Only photos that have been published in Active Directory Domain Services can be displayed.

AllPhotos - Either Active Directory photos or custom photos can be displayed.

The default value is AllPhotos.


```yaml
Type: DisplayPhoto
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAppearOffline

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True an additional presence state -- Appear Offline -- is available in Skype for Business.
This state makes it appear as though the user is offline; however, he or she will actually be online and available to answer phone calls, respond to instant messages, etc.
When set to False, the Appear Offline presence state will not be available in Skype for Business.


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

### -EnableCallLogAutoArchiving

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, information about your incoming and outgoing phone calls is automatically saved to the Conversation History folder in Outlook.
(The actual call itself is not recorded.
What is recorded is information such as who took part in the call; the length of the call and whether this was an incoming or an outgoing call.) When set to False, this information is not saved to Outlook.


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

### -EnableClientAutoPopulateWithTeam

> Applicable: Skype for Business Online

When set to true, allows a user's Skype client to be autopopulated with members of his or her immediate team.

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

### -EnableClientMusicOnHold

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, music will be played any time a caller is placed on hold.
When set to False, music will not be played any time a caller is placed on hold.
The default value is False.


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

### -EnableConversationWindowTabs

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, supplemental information related to an instant messaging session will be displayed in a separate browser window.

When set to False, supplemental information will not be displayed in a separate browser window.

This parameter has been deprecated for use with Skype for Business Server.


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

### -EnableEnterpriseCustomizedHelp

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, users who click the Help menu in Skype for Business will be given custom help set up by the organization.
When set to False, users who click the Help menu will be given the default product help.

This parameter has been deprecated for use with Skype for Business Server.


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

### -EnableEventLogging

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, detailed information about Skype for Business will be recorded in the Application event log.
When set to False, only major events (such as the failure to connect to Skype for Business Server) are recorded in the event log.


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

### -EnableExchangeContactsFolder

> Applicable: Skype for Business Online

When set to false, this allows admins to hide Skype for Business contacts from showing up in users' Outlook and Outlook on the Web clients.

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

### -EnableExchangeContactSync

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True (the default value) Skype for Business creates a corresponding personal contact in Outlook for each person on a user's Skype for Business Contacts list.


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

### -EnableExchangeDelegateSync

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, a user that has been configured in Outlook will be allowed to schedule online Lync Calendar meetings for that user (this happens via Lync UCMAPI delegation, without the need of the Enterprise Voice feature).


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

### -EnableFullScreenVideo

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, this parameter does two things: 1) enables full-screen video (with the correct aspect ratio) for Skype for Business calls and 2) disables video preview for Skype for Business calls.
When set to False then full-screen video is not available in Skype for Business, but video preview is available.


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

### -EnableHighPerformanceConferencingAppSharing

> Applicable: Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, enables better performance in applications (such as CAD/CAM applications) that have a high screen refresh rate.
However, this improved performance will reduce the system resources and network bandwidth available to other applications.


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

### -EnableHighPerformanceP2PAppSharing

> Applicable: Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, allows a peer-to-peer application sharing session to exceed the maximum frame rate of 2.5 frames per second.
The default value is False.


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

### -EnableHotdesking

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, enables users to log on to a phone running Skype for Business Phone Edition in a shared workspace by using their Skype for Business Server account.
(Among other things, this provides the user access to his or her contacts.) When set to False, users are not allowed to log on to a phone in a shared workspace by using their own credentials.

Note that this setting applies only to common area (shared workspace) accounts and not to user accounts.
When set to True and applied to a common area account for a phone in a shared workspace, any user will be able to log on to that phone by using his or her credentials.
When set to False, no one will be allowed to log on to that phone.


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

### -EnableIMAutoArchiving

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, a transcript of every instant message session that a user takes part in will be saved to the Conversation History folder in Outlook.
When set to False, these transcripts will not be saved automatically.
(However, users will have the option to manually save instant message transcripts.)


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

### -EnableMediaRedirection

> Applicable: Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True ($True) allows audio and video streams to be separated from other network traffic; in turn, this allows client devices to do encoding and decoding of audio and video locally.
Media redirection typically results in lower bandwidth usage, higher server scalability and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.


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

### -EnableMeetingEngagement

> Applicable: Skype for Business Online

This parameter is reserved for internal Microsoft use.

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

### -EnableNotificationForNewSubscribers

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True you will receive notification any time you are added to someone else's Contacts list.
In addition, the notification dialog box will provide options for you to add that person to your Contacts list, or to block them from viewing your presence information.


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

### -EnableOnlineFeedback

> Applicable: Skype for Business Online

When set to true, allows users to provide feedback through the "help->report a problem" menu options in the client.

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

### -EnableOnlineFeedbackScreenshots

> Applicable: Skype for Business Online

When set to true, allows users to provide screenshots of their clients when reporting problems.

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

### -EnableServerConversationHistory

> Applicable: Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True ($True), allows conversation histories, missed call notifications, and missed IM notifications to be stored on the server instead of in client mailboxes.
This makes it easier for users to retrieve that information from a mobile device.

The default value is False ($False).


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

### -EnableSkypeUI

> Applicable: Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True ($True), this parameter allows administrators to enable the Skype for Business user interface instead of the Lync interface for the Skype for Business client.


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

### -EnableSQMData

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When EnableSQMData is set to True, the user will not automatically be enrolled in the Customer Experience Improvement Program.
However, Skype for Business will provide the user with the option to join the program.

When set to False, the user will not be enrolled in the Customer Experience Improvement Program.
In addition, Skype for Business will not give users the option of joining the program.


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

### -EnableTracing

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, software tracing will be enabled in Skype for Business; when set to False software tracing will be disabled.
Software tracing involves keeping an extremely detailed record of everything that a program does (including tracking API calls).
As such tracing is mostly useful to developers and to application support personnel.


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

### -EnableUnencryptedFileTransfer

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, users will be allowed to exchange files with external users whose instant messaging software does not support encrypted file transfers.
When set to False, users will only be able to exchange files with external users who have software that supports encrypted file transfers.


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

### -EnableURL

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, hyperlinks embedded in an instant message will be "clickable;" that is, users can click that link and their web browser will open to the specified location.
When set to False, hyperlinks appear in instant messages as plain text.
To navigate to the location, users will need to copy the link text and paste it into their web browser.


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

### -EnableViewBasedSubscriptionMode

> Applicable: Skype for Business Online

This parameter is reserved for internal Microsoft use.

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

### -EnableVOIPCallDefault

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, a Skype for Business call will be placed any time a user employs the click-to-call feature.

This policy setting only affects the initial state of the click-to-call feature.
If the user modifies the value of the click-to-call setting then the user-selected value will override this policy setting.
After a user has modified the click-to-call setting that setting will remain in use and will not be affected by the EnableVOIPCallDefault policy.


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

### -ExcludedContactFolders

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Indicates which Outlook contact folders (if any) should not be searched any time Skype for Business searches for new contacts.
Multiple folders can be specified by separating the folder names using semicolons; for example: `-ExcludedContactFolders "SenderPhotoContacts;OtherContacts"`.


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

### -Force

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Suppresses the display of any non-fatal error message that might arise when running the command.


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

### -HelpEnvironment

> Applicable: Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to "Office 365", the Office 365 client help documentation for Skype for Business will be shown to users rather than the on-premises help shown by default.
You can either set HelpEnvironment to "Office 365" or to a null value ($Null).
If set to a null value (the default value) then the on-premises help will be shown to users.


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

### -HotdeskingTimeout

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Timeout interval for a user logged on to a "hot-desk" phone.
(A hot-desk phone is a phone running Skype for Business Phone Edition that is located in a shared workspace and that users can log on to using their Skype for Business Server account.) The hot-desk timeout specifies the number of minutes that can elapse before a user is automatically logged off of a hot-desk phone.
When specifying a hot desking timeout you must use the format hours:minutes:seconds.
For example, this syntax sets the hot desking timeout interval to 45 minutes:

`-HotdeskingTimeout 00:45:00`

Note that this policy setting applies only to common area phones and not to users.
The default value is 5 minutes (00:05:00), and the minimum value is 30 seconds (00:00:30).


```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Unique identifier assigned to the new policy.
To reference the global policy, use this syntax: `-Identity global`.
To reference a site policy, use the prefix "site:" and the name of the site as your Identity; for example: `-Identity site:Redmond`.
To reference a per-user policy, use syntax similar to this: `-Identity SalesClientPolicy`.

```yaml
Type: XdsIdentity
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IMLatencyErrorThreshold

> Applicable: Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

If IM latency is greater than the threshold value (in milliseconds), the client will submit a CER.


```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IMLatencySpinnerDelay

> Applicable: Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Amount of time, in milliseconds, to wait before showing the spinner in the client when IM message delivery is delayed.


```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IMWarning

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When configured, the specified message appears in the Conversation window each time a user takes part in an instant messaging session.
For example, if IMWarning is set to "All information is the property of Litwareinc" then that message will appear in the Conversation window each time a user takes part in an instant messaging session.

Your warning message should be limited to 256 characters, and can only contain plain text.
You cannot use any formatting (such as boldface or italics) and you cannot clickable URLs within the text.

If set to a null value ($Null) then no message appears in the Conversation window.


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

### -Instance

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.


```yaml
Type: PSObject
Parameter Sets: Instance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MAPIPollInterval

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

> [!IMPORTANT]
> This parameter has been deprecated for use with Skype for Business Server.

For users of Microsoft Exchange Server 2003, MAPIPollInterval specifies how often Skype for Business retrieves calendar data from the Exchange public folders.
MAPIPollInterval can be set to any value between 1 second and 1 hour; inclusive.
To configure the MAPI poll interval, use the format hours:minutes:seconds.
For example, this command sets the MAPI poll interval to 45 minutes:

`-MapiPollInterval 00:45:00`


```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumDGsAllowedInContactList

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Indicates the maximum number of distribution groups that a user can configure as a contact.
MaximumDGsAllowedInContactList can be set to any integer value between 0 and 64, inclusive.
The default value is 10.


```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumNumberOfContacts

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Indicates the maximum number of contacts a user is allowed to have.
The maximum contacts can be set to any integer value between 0 and 1000, inclusive.
When set to 0, that prevents the user from having any contacts.


```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxPhotoSizeKB

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Indicates the maximum size (in kilobytes) for photos displayed in Skype for Business.

The default value is 30 kilobytes.


```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MusicOnHoldAudioFile

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Path to the audio file to be played when a caller is placed on hold.
If a value is configured for this property then music on hold will be enabled and users will not be allowed to disable the feature.
If no value is configured for this property then users can specify their own music on hold file, assuming that EnableClientMusicOnHold is set to True.


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

### -P2PAppSharingEncryption

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Indicates whether or not desktop and application sharing data exchanged during a peer-to-peer conversation is encrypted.
Allowed values are:

Supported.
Desktop and application sharing data will be encrypted, if possible.

Enforced.
Desktop and application sharing data must be encrypted.
If the data cannot be encrypted then desktop and application sharing will not be enabled for the conversation.

NotSupported.
Desktop and application sharing data will not be encrypted.


```yaml
Type: P2PAppSharingEncryption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlayAbbreviatedDialTone

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, a 3-second dial tone will be played any time a Skype for Business-compatible handset is taken off the hook.
(A Skype for Business-compatible handset looks like a standard telephone, but plugs into a USB port on your computer and is used to make Skype for Business calls rather than "regular" phone calls.) When set to False, a 30-second dial tone is played any time a Skype for Business-compatible handset is taken off the hook.


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

### -PolicyEntry

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Provides a way to add settings not covered by the default parameters.
For example, when testing pre-release versions Microsoft Lync Server 2010 it was possible to add a Send Feedback option to Microsoft Lync 2010.
That was done by using code similar to this:

`$x = New-CsClientPolicyEntry -Name "OnlineFeedbackURL" -Value "https://www.litwareinc.com/feedback"`

`Set-CsClientPolicy -Identity global -PolicyEntry @{Add=$x}`

For more details and examples, see the `New-CsClientPolicyEntry` cmdlet help topic.


```yaml
Type: PSListModifier
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicationBatchDelay

> Applicable: Skype for Business Online

This parameter is reserved for internal Microsoft use.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RateMyCallAllowCustomUserFeedback

> Applicable: Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True ($True), enables a text box for users to type feedback when prompted.


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

### -RateMyCallDisplayPercentage

> Applicable: Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

The RateMyCallDisplayPercentage setting adjusts how often users are prompted for feedback, ranging from 0 to 100.
The default value is 10, meaning that users will get prompted for feedback 10% of the time after they finish a call.
Setting this to 0 means users will never get prompted.
When set to 100, users will get prompted after every call.


```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequireContentPin

> Applicable: Skype for Business Online

This parameter is reserved for internal Microsoft use.

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

### -SearchPrefixFlags

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Represents the Address Book attributes that should be used any time a user searches for a new contact.
The search prefix flags are constructed as a binary number such as 11101111, in which a 1 indicates that the attribute should be searched and a 0 indicates that the attribute should not be searched.
The attributes in the binary value are (from right to left):

Primary email address

Email alias

All email addresses

Company

Display name

First name

Last name

The binary value 1110111 means that all attributes should be searched except attribute 4: Company.
To search only display name, first name, and last name you would construct this value:

1110000

After the binary value has been constructed it must then be converted to a decimal value before being assigned to SearchPrefixFlags.
To convert a binary number to a decimal number you can use the following Windows PowerShell command:

`[Convert]::ToInt32("1110111", 2)`

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShowManagePrivacyRelationships

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, shows the Relationships option in the Lync Contacts list window.
When set to False, hides the Relationships option.

Note that this setting applies only to Lync 2010.
Skype for Business will not show these relationships even if ShowManagePrivacyRelationships has been set to True.

The default value is False.


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

### -ShowRecentContacts

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

This parameter has no effect on the client.


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

### -ShowSharepointPhotoEditLink

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

If set to True, Skype for Business will include a link that enables users to edit the personal photo stored on SharePoint.
The default value is False, which means that Skype for Business will not include a link to SharePoint.


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

### -SPSearchCenterExternalURL

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

External URL for the SharePoint site used for keyword searches (also known as expert searches).
This URL will appear at the bottom of any keyword search results that appear in Skype for Business.
If the user clicks this URL, his or her web browser will open up to the SharePoint site, giving the user the opportunity to conduct searches using SharePoint's search capabilities.
(SharePoint offers more search options than Skype for Business does.)

SPSearchCenterExternalURL represents the URL for external users; that is, for users logging on from outside the organization's firewall.
The parameter SPSearchCenterInternalURL is for users who log on from inside the firewall.


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

### -SPSearchCenterInternalURL

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Internal URL for the SharePoint site used for keyword searches (also known as expert searches).
This URL will appear at the bottom of any keyword search results that appear in Skype for Business.
If the user clicks this URL, his or her web browser will open up to the SharePoint site, giving the user the opportunity to conduct searches using SharePoint's search capabilities.
(SharePoint offers more search options than Skype for Business does.)

SPSearchCenterInternalURL represents the URL for internal users; that is, for users logging on from inside the organization's firewall.
The parameter SPSearchCenterExternalURL is for users who log on from outside the firewall.


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

### -SPSearchExternalURL

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

External URL for the SharePoint site used for keyword searches (also known as expert searches).
Skype for Business will use the SharePoint site located at this URL any time an external user (that is, a user who has accessed the system from outside the organization's firewall) conducts a keyword search.


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

### -SPSearchInternalURL

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Internal URL for the SharePoint site used for keyword searches (also known as expert searches).
Skype for Business will use the SharePoint site located at this URL any time an internal user (that is, a user who has logged on from inside the organization's firewall) conducts a keyword search.


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

### -SupportModernFilePicker

> Applicable: Skype for Business Online

This parameter is reserved for internal Microsoft use.

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

### -TabURL

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Specifies the location of the XML file used to create custom tabs located at the bottom of the Skype for Business Contacts list window.
This parameter has been deprecated for use with Skype for Business Server.


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

### -TelemetryTier

> Applicable: Skype for Business Online

This parameter is reserved for internal Microsoft use.

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

### -Tenant

> Applicable: Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Globally unique identifier (GUID) of the Skype for Business Online tenant account for whom the client policy is being modified.
For example:

`-Tenant "38aad667-af54-4397-aaa7-e94c79ec2308"`

You can return the tenant ID for each of your Skype for Business Online tenants by running this command:

`Get-CsTenant | Select-Object DisplayName, TenantID`


```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TracingLevel

> Applicable: Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Enables Administrators to manage event tracing and logging in Skype for Business.
Allowed values are:

Off - Tracing is disabled and the user cannot change this setting.

Light - Minimal tracing is performed, and the user cannot change this setting.

Full - Verbose tracing is performed, and the user cannot change this setting.

By default TracingLevel is set to Light.


```yaml
Type: TracingLevel
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebServicePollInterval

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

For users of Microsoft Exchange Server 2007 and later versions of the product, WebServicePollInterval specifies how often Skype for Business retrieves calendar data from Microsoft Exchange Server Web Services.
WebServicePollInterval can be set to any value between 1 second and 1 hour; inclusive.
To configure the Web Service poll interval, use the format hours:minutes:seconds.
For example, this command sets the Web Service poll interval to 45 minutes:

`-WebServicePollInterval 00:45:00`

Note that this setting does not apply to users whose email account is on Exchange 2003.
For those users, calendar retrieval is managed using MAPIPollInterval.


```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Prompts you for confirmation before executing the command.


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

### -WhatIf

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Online, Skype for Business Server 2015, Skype for Business Server 2019

Describes what would happen if you executed the command without actually executing the command.


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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Rtc.Management.WritableConfig.Policy.Client.ClientPolicy

The `Set-CsClientPolicy` cmdlet accepts pipelined instances of the client policy object.

## OUTPUTS

### None
The `Set-CsClientPolicy` cmdlet does not return a value or object.
Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Client.ClientPolicy object.

## NOTES

## RELATED LINKS

[Get-CsClientPolicy](Get-CsClientPolicy.md)

[Grant-CsClientPolicy](Grant-CsClientPolicy.md)

[New-CsClientPolicy](New-CsClientPolicy.md)

[Remove-CsClientPolicy](Remove-CsClientPolicy.md)
