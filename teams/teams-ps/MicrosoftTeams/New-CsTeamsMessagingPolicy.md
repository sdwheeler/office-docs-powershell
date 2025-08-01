---
applicable: Microsoft Teams
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml
Locale: en-US
Module Name: MicrosoftTeams
online version: https://learn.microsoft.com/powershell/module/microsoftteams/new-csteamsmessagingpolicy
schema: 2.0.0
title: New-CsTeamsMessagingPolicy
---

# New-CsTeamsMessagingPolicy

## SYNOPSIS
The CsTeamsMessagingPolicy cmdlets enable administrators to control if a user is enabled to exchange messages. These also help determine the type of messages users can create and modify.

## SYNTAX

```powershell
New-CsTeamsMessagingPolicy [[-Identity] <XdsIdentity>]
 [-AllowChatWithGroup <Boolean>]
 [-AllowCommunicationComplianceEndUserReporting <Boolean>]
 [-AllowCustomGroupChatAvatars <Boolean>]
 [-AllowExtendedWorkInfoInSearch <Boolean>]
 [-AllowFluidCollaborate <Boolean>]
 [-AllowFullChatPermissionUserToDeleteAnyMessage <Boolean>]
 [-AllowGiphy <Boolean>]
 [-AllowGiphyDisplay <Boolean>]
 [-AllowGroupChatJoinLinks <Boolean>]
 [-AllowImmersiveReader <Boolean>]
 [-AllowMemes <Boolean>]
 [-AllowOwnerDeleteMessage <Boolean>]
 [-AllowPasteInternetImage <Boolean>]
 [-AllowPriorityMessages <Boolean>]
 [-AllowRemoveUser <Boolean>]
 [-AllowSecurityEndUserReporting <Boolean>]
 [-AllowSmartCompose] <Boolean>]
 [-AllowSmartReply <Boolean>]
 [-AllowStickers <Boolean>]
 [-AllowUrlPreviews <Boolean>]
 [-AllowUserChat <Boolean>]
 [-AllowUserDeleteChat <Boolean>]
 [-AllowUserDeleteMessage <Boolean>]
 [-AllowUserEditMessage <Boolean>]
 [-AllowUserTranslation <Boolean>]
 [-AllowVideoMessages <Boolean>]
 [-AudioMessageEnabledType <AudioMessageEnabledTypeEnum>]
 [-ChannelsInChatListEnabledType <ChannelsInChatListEnabledTypeEnum>]
 [-ChatPermissionRole <String>]
 [-Confirm]
 [-CreateCustomEmojis <Boolean>]
 [-DeleteCustomEmojis <Boolean>]
 [-Description <String>]
 [-DesignerForBackgroundsAndImages <String>]
 [-Force]
 [-GiphyRatingType <String>]
 [-InMemory]
 [-InOrganizationChatControl <String>]
 [-ReadReceiptsEnabledType <String>]
 [-Tenant <Guid>]
 [-UsersCanDeleteBotMessages <Boolean>]
 [<CommonParameters>]
 [-WhatIf]
 ```

## DESCRIPTION
The CsTeamsMessagingPolicy cmdlets enable administrators to control if a user is enabled to exchange messages. These also help determine the type of messages users can create and modify.  This cmdlet creates a new Teams messaging policy.  Custom policies can then be assigned to users using the Grant-CsTeamsMessagingPolicy cmdlet.

## EXAMPLES

### Example 1
```powershell
PS C:\> New-CsTeamsMessagingPolicy -Identity StudentMessagingPolicy -AllowGiphy $false -AllowMemes $false
```

In this example two different property values are configured: AllowGiphy is set to false and AllowMemes is set to False.
All other policy properties will use the default values.

## PARAMETERS

### -AllowChatWithGroup

This setting determines if users can chat with groups (Distribution, M365 and Security groups). Possible values: True, False

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

### -AllowCommunicationComplianceEndUserReporting

This setting determines if users can report offensive messages to their admin for Communication Compliance. Possible Values: True, False

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

### -AllowCustomGroupChatAvatars

These settings enables, disables updating or fetching custom group chat avatars for the users included in the messaging policy. Possible values: True, False

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

### -AllowExtendedWorkInfoInSearch
This setting enables/disables showing company name and department name in search results for MTO users.

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

### -AllowFluidCollaborate

This field enables or disables Fluid Collaborate feature for users. Possible values: True, False

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

### -AllowFullChatPermissionUserToDeleteAnyMessage

This setting determines if users with the 'Full permissions' role can delete any group or meeting chat message within their tenant. Possible values: True, False

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

### -AllowGiphy
Determines whether a user is allowed to access and post Giphys. Set this to TRUE to allow. Set this FALSE to prohibit.

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

### -AllowGiphyDisplay

Determines if Giphy images should be displayed that had been already sent or received in chat. Possible values: True, False

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

### -AllowGroupChatJoinLinks

This setting determines if users in a group chat can create and share join links for other users within the organization to join that chat. Possible values: True, False

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

### -AllowImmersiveReader
Determines whether a user is allowed to use Immersive Reader for reading conversation messages. Set this to TRUE to allow. Set this FALSE to prohibit.

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

### -AllowMemes
Determines whether a user is allowed to access and post memes. Set this to TRUE to allow. Set this FALSE to prohibit.

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

### -AllowOwnerDeleteMessage
Determines whether owners are allowed to delete all the messages in their team. Set this to TRUE to allow. Set this to FALSE to prohibit.

If the `-AllowUserDeleteMessage` parameter is set to FALSE, the team owner will not be able to delete their own messages.

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

### -AllowPasteInternetImage

Determines if a user is allowed to paste internet-based images in compose. Possible values: True, False

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

### -AllowPriorityMessages
Determines whether a user is allowed to send priorities messages. Set this to TRUE to allow. Set this FALSE to prohibit.

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

### -AllowRemoveUser
Determines whether a user is allowed to remove a user from a conversation. Set this to TRUE to allow. Set this FALSE to prohibit.

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

### -AllowSecurityEndUserReporting

This setting determines if users can report any security concern posted in messages to their admin. Possible values: True, False

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

### -AllowSmartCompose
Turn on this setting to let a user get text predictions for chat messages.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Con nombre
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowSmartReply
Turn this setting on to enable suggested replies for chat messages.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowStickers
Determines whether a user is allowed to access and post stickers. Set this to TRUE to allow. Set this FALSE to prohibit.

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

### -AllowUrlPreviews
Use this setting to turn automatic URL previewing on or off in messages. Set this to TRUE to turn on. Set this to FALSE to turn off.
Note: [Optional Connected Experiences](https://learn.microsoft.com/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) must be also enabled for URL previews to be allowed.

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

### -AllowUserChat
Determines whether a user is allowed to chat. Set this to TRUE to allow a user to chat across private chat, group chat and in meetings. Set this to FALSE to prohibit all chat.

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

### -AllowUserDeleteChat

Determines whether a user is allowed to chat. Set this to TRUE to allow a user to chat across private chat, group chat and in meetings. Set this to FALSE to prohibit all chat.

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

### -AllowUserDeleteMessage
Determines whether a user is allowed to delete their own messages. Set this to TRUE to allow. Set this to FALSE to prohibit.

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

### -AllowUserEditMessage
Determines whether a user is allowed to edit their own messages. Set this to TRUE to allow. Set this to FALSE to prohibit.

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

### -AllowUserTranslation
Determines whether a user is allowed to translate messages to their client languages. Set this to TRUE to allow. Set this to FALSE to prohibit.

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

### -AllowVideoMessages

This setting determines if users can create and send video messages. Possible values: True, False

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

### -AudioMessageEnabledType
Determines whether a user is allowed to send audio messages. Possible values are: ChatsAndChannels,ChatsOnly,Disabled.

```yaml
Type: AudioMessageEnabledTypeEnum
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ChannelsInChatListEnabledType
On mobile devices, enable to display favorite channels above recent chats.

Possible values are: DisabledUserOverride,EnabledUserOverride.

```yaml
Type: ChannelsInChatListEnabledTypeEnum
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ChatPermissionRole
Determines the Supervised Chat role of the user.  Set this to Full to allow the user to supervise chats.  Supervisors have the ability to initiate chats with and invite any user within the environment.  Set this to Limited to allow the user to initiate conversations with Full and Limited permissioned users, but not Restricted.  Set this to Restricted to block chat creation with anyone other than Full permissioned users.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Restricted
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

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

### -CreateCustomEmojis
This setting enables the creation of custom emojis and reactions within an organization for the specified policy users.

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

### -DeleteCustomEmojis
These settings enable and disable the editing and deletion of custom emojis and reactions for the users included in the messaging policy.

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

### -Description
Allows you to provide a description of your policy to note the purpose of creating it.

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

### -DesignerForBackgroundsAndImages

This setting determines whether a user is allowed to create custom AI-powered backgrounds and images with MS Designer.

Possible values are: Enabled, Disabled.

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
The Force switch specifies whether to suppress warning and confirmation messages. It can be useful in scripting to suppress interactive prompts. If the Force switch isn't provided in the command, you're prompted for administrative input if required.

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

### -GiphyRatingType
Determines the Giphy content restrictions applicable to a user. Set this to STRICT, MODERATE or NORESTRICTION.

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

### -Identity
Unique identifier for the teams messaging policy to be created.

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
### -InMemory
Creates an object reference without actually committing the object as a permanent change. If you assign the output of this cmdlet called with this parameter to a variable, you can make changes to the properties of the object reference and then commit those changes by calling this cmdlet's matching Set-.

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

### -InOrganizationChatControl

This setting determines if chat regulation for internal communication in the tenant is allowed.

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

### -ReadReceiptsEnabledType

Use this setting to specify whether read receipts are user controlled, enabled for everyone, or disabled. Set this to UserPreference, Everyone or None.

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
Globally unique identifier (GUID) of the tenant account whose external user communication policy are being created. For example:

-Tenant "38aad667-af54-4397-aaa7-e94c79ec2308"

You can return your tenant ID by running this command:

Get-CsTenant | Select-Object DisplayName, TenantID

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

### -UsersCanDeleteBotMessages

Determines whether a user is allowed to delete messages sent by bots. Set this to TRUE to allow. Set this to FALSE to prohibit.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS
[Set-CsTeamsMessagingPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/set-csteamsmessagingpolicy)

[Get-CsTeamsMessagingPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/get-csteamsmessagingpolicy)

[Grant-CsTeamsMessagingPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/grant-csteamsmessagingpolicy)

[Remove-CsTeamsMessagingPolicy](https://learn.microsoft.com/powershell/module/microsoftteams/remove-csteamsmessagingpolicy)
