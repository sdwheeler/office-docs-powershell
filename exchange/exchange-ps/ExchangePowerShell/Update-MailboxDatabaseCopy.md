---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019
author: chrisda
external help file: Microsoft.Exchange.ServerStatus-Help.xml
Locale: en-US
Module Name: ExchangePowerShell
ms.author: chrisda
online version: https://learn.microsoft.com/powershell/module/exchangepowershell/update-mailboxdatabasecopy
schema: 2.0.0
title: Update-MailboxDatabaseCopy
---

# Update-MailboxDatabaseCopy

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the Update-MailboxDatabaseCopy cmdlet to seed or reseed a mailbox database copy.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

### CancelSeed
```
Update-MailboxDatabaseCopy [-Identity] <DatabaseCopyIdParameter>
 [-CancelSeed]
 [-Confirm]
 [-DomainController <Fqdn>]
 [-WhatIf]
 [<CommonParameters>]
```

### Identity
```
Update-MailboxDatabaseCopy [-Identity] <DatabaseCopyIdParameter>
 [-BeginSeed]
 [-Force]
 [-Network <DatabaseAvailabilityGroupNetworkIdParameter>]
 [-SecondaryDatabasePartitionOnly]
 [-SourceServer <ServerIdParameter>]
 [-CatalogOnly]
 [-Confirm]
 [-DatabaseOnly]
 [-DeleteExistingFiles]
 [-DomainController <Fqdn>]
 [-ManualResume]
 [-NetworkCompressionOverride <UseDagDefaultOnOff>]
 [-NetworkEncryptionOverride <UseDagDefaultOnOff>]
 [-NoThrottle]
 [-PrimaryDatabasePartitionOnly]
 [-SafeDeleteExistingFiles]
 [-WhatIf]
 [<CommonParameters>]
```

### ExplicitServer
```
Update-MailboxDatabaseCopy -Server <MailboxServerIdParameter>
 [-MaximumSeedsInParallel <Int32>]
 [-CatalogOnly]
 [-Confirm]
 [-DatabaseOnly]
 [-DeleteExistingFiles]
 [-DomainController <Fqdn>]
 [-ManualResume]
 [-NetworkCompressionOverride <UseDagDefaultOnOff>]
 [-NetworkEncryptionOverride <UseDagDefaultOnOff>]
 [-NoThrottle]
 [-PrimaryDatabasePartitionOnly]
 [-SafeDeleteExistingFiles]
 [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Seeding is the process in which a copy of a mailbox database is added to another Mailbox server. This becomes the database copy into which copied log files and data are replayed.

The Update-MailboxDatabaseCopy cmdlet can also be used to seed a content index catalog for a mailbox database copy. When you do this, the MAPI network is used, regardless of the value you specify with the Network parameter.

You must suspend a database copy before you can update it using the Update-MailboxDatabaseCopy cmdlet. For detailed steps about how to suspend a database copy, see [Suspend or resume a mailbox database copy](https://learn.microsoft.com/Exchange/high-availability/manage-ha/suspend-resume-db-copies).

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Update-MailboxDatabaseCopy -Identity DB1\MBX1
```

This example seeds a copy of the database DB1 on the Mailbox server MBX1.

### Example 2
```powershell
Update-MailboxDatabaseCopy -Identity DB1\MBX1 -SourceServer MBX2
```

This example seeds a copy of the database DB1 on the Mailbox server MBX1 using MBX2 as the source Mailbox server for the seed.

### Example 3
```powershell
Update-MailboxDatabaseCopy -Identity DB1\MBX1 -DatabaseOnly
```

This example seeds a copy of the database DB1 on the Mailbox server MBX1 without seeding the content index catalog.

### Example 4
```powershell
Update-MailboxDatabaseCopy -Identity DB1\MBX1 -CatalogOnly
```

This example seeds the content index catalog for the copy of the database DB1 on the Mailbox server MBX1 without seeding the database file. The content index catalog seeding occurs over the MAPI network.

### Example 5
```powershell
Update-MailboxDatabaseCopy -Server MBX1
```

This example performs a full server reseed of all of the databases on the Mailbox server MBX1.

## PARAMETERS

### -Identity

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Identity parameter specifies the name or GUID of the mailbox database whose copy is being seeded.

```yaml
Type: DatabaseCopyIdParameter
Parameter Sets: CancelSeed, Identity
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -CancelSeed

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The CancelSeed switch specifies whether to cancel an in-progress seeding operation. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: CancelSeed
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Server parameter is used as part of a full server reseed operation. It can be used with the MaximumSeedsInParallel parameter to start reseeds of database copies in parallel across the specified server in batches of up to the value of the MaximumSeedsInParallel parameter copies at a time.

```yaml
Type: MailboxServerIdParameter
Parameter Sets: ExplicitServer
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -BeginSeed

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The BeginSeed switch asynchronously starts the seeding operation and then exits the cmdlet. You don't need to specify a value with this switch.

This switch is useful for scripting reseeds.

```yaml
Type: SwitchParameter
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CatalogOnly

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The CatalogOnly switch specifies that only the content index catalog for the database copy should be seeded. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: Identity, ExplicitServer
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

### -DatabaseOnly

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The DatabaseOnly switch specifies that only the database copy should be seeded. The content index catalog isn't seeded. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: Identity, ExplicitServer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeleteExistingFiles

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The DeleteExistingFiles switch specifies whether to remove the existing log files at the target location. You don't need to specify a value with this switch.

This switch removes only the files that it checks for and fails if other files are present. No action is taken on other files at the target location. Therefore, if database-related files are present, you must manually remove them.

```yaml
Type: SwitchParameter
Parameter Sets: Identity, ExplicitServer
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

### -Force

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Force switch hides warning or confirmation messages. You don't need to specify a value with this switch.

You can use this switch to run tasks programmatically where prompting for administrative input is inappropriate.

```yaml
Type: SwitchParameter
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManualResume

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The ManualResume switch specifies whether to automatically resume replication on the database copy. You don't need to specify a value with this switch.

With this switch, you can manually resume replication to the database copy.

```yaml
Type: SwitchParameter
Parameter Sets: Identity, ExplicitServer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumSeedsInParallel

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The MaximumSeedsInParallel parameter is used with the Server parameter to specify the maximum number of parallel seeding operations that should occur across the specified server during a full server reseed operation. The default value is 10.

```yaml
Type: Int32
Parameter Sets: ExplicitServer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Network

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The Network parameter specifies which DAG network should be used for seeding. Note that content index catalog seeding always occurs over the MAPI network, even if you use this parameter to specify the DAG network.

```yaml
Type: DatabaseAvailabilityGroupNetworkIdParameter
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkCompressionOverride

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The NetworkCompressionOverride parameter specifies whether to override the current DAG network compression settings.

```yaml
Type: UseDagDefaultOnOff
Parameter Sets: Identity, ExplicitServer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkEncryptionOverride

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The NetworkEncryptionOverride parameter specifies whether to override the current DAG encryption settings.

```yaml
Type: UseDagDefaultOnOff
Parameter Sets: Identity, ExplicitServer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoThrottle

> Applicable: Exchange Server 2016, Exchange Server 2019

The NoThrottle switch prevents the seeding operation from being throttled. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: Identity, ExplicitServer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryDatabasePartitionOnly

> Applicable: Exchange Server 2019

This parameter is reserved for internal Microsoft use.

```yaml
Type: SwitchParameter
Parameter Sets: Identity, ExplicitServer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SafeDeleteExistingFiles

> Applicable: Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The SafeDeleteExistingFiles switch specifies a seeding operation with a single copy redundancy pre-check prior to the seed. You don't need to specify a value with this switch.

Because this switch includes the redundancy safety check, it requires a lower level of permissions than the DeleteExistingFiles parameter. Limited permission administrators can perform the seeding operation by using this switch.

```yaml
Type: SwitchParameter
Parameter Sets: Identity, ExplicitServer
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecondaryDatabasePartitionOnly

> Applicable: Exchange Server 2019

This parameter is reserved for internal Microsoft use.

```yaml
Type: SwitchParameter
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceServer

> Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

The SourceServer parameter specifies the Mailbox server with a passive copy of the mailbox database to be used as the source for the seed operation.

 You can use any value that uniquely identifies the server. For example:

- Name
- FQDN
- Distinguished name (DN)
- ExchangeLegacyDN

```yaml
Type: ServerIdParameter
Parameter Sets: Identity
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
