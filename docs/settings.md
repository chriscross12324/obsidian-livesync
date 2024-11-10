**NOTE:** This document is not complete. I'll be improving it soon, but your contributions are always welcome.

# Settings of Self-hosted LiveSync

There are many settings in Self-hosted LiveSync. This document describes each setting in detail (not the setup process). The configuration and settings are divided into several categories, each indicated by an icon. The icons are as follows:

| Icon | Description                                                        |
| :--: | ------------------------------------------------------------------ |
| 💬  | [0. Update Information](#0-update-information)                     |
| 🧙‍♂️  | [1. Setup](#1-setup)                                               |
| ⚙️  | [2. General Settings](#2-general-settings)                         |
| 🛰️  | [3. Remote Configuration](#3-remote-configuration)                 |
| 🔄  | [4. Sync Settings](#4-sync-settings)                               |
| 🚦  | [5. Selector (Advanced)](#5-selector-advanced)                     |
| 🔌  | [6. Customization Sync (Advanced)](#6-customization-sync-advanced) |
| 🧰  | [7. Hatch](#7-hatch)                                               |
| 🔧  | [8. Advanced (Advanced)](#8-advanced-advanced)                     |
| 💪  | [9. Power Users (Power User)](#9-power-users-power-user)           |
| 🩹  | [10. Patches (Edge Case)](#10-patches-edge-case)                   |
| 🎛️  | [11. Maintenance](#11-maintenance)                                 |

## 0. Update Information

This pane shows version update information. You can check what has changed in recent versions.

## 1. Setup

This section is for setting up Self-hosted LiveSync. There are several methods to complete the setup.

### 1. Quick Setup

The easiest and fastest way to set up Self-hosted LiveSync. You can complete the setup with just a few clicks.

#### Use the Copied Setup URI

Set up Self-hosted LiveSync by using the `setup URI` that was [copied from another device](#copy-current-settings-as-a-new-setup-uri) or from the setup script.

#### Minimal Setup

A step-by-step guide to manually set up Self-hosted LiveSync with only the essential settings.

#### Enable LiveSync on This Device (After Manual Setup)

This option appears only if the setup was not completed. After manually completing the setup, you can enable LiveSync on this device by clicking this button.

### 2. To Set Up Other Devices

#### Copy Current Settings as a New Setup URI

You can copy the current settings as a new setup URI. This URI can then be used to set up other devices, similar to the [Use the Copied Setup URI](#use-the-copied-setup-uri) option.

### 3. Reset

#### Discard Existing Settings and Databases

Reset the Self-hosted LiveSync settings and databases to their default state.  
**Warning:** This is a risky operation. Please use it with caution.

### 4. Enable Extra and Advanced Features

To keep the setup interface simple, some panes are hidden by default. You can enable them here.

#### Enable Advanced Features

**Setting Key:** `useAdvancedMode`

The following panes will be shown when you enable this setting:

| Icon | Description                                                         |
| :--: | ------------------------------------------------------------------- |
| 🚦  | [5. Selector (Advanced)](#5-selector-advanced)                      |
| 🔌  | [6. Customization Sync (Advanced)](#6-customization-sync-advanced)  |
| 🔧  | [8. Advanced (Advanced)](#8-advanced-advanced)                      |

#### Enable Power User Features

**Setting Key:** `usePowerUserMode`

The following pane will be shown when you enable this setting:

| Icon | Description                                                         |
| :--: | ------------------------------------------------------------------- |
| 💪  | [9. Power Users (Power User)](#9-power-users-power-user)            |

#### Enable Edge Case Treatment Features

**Setting Key:** `useEdgeCaseMode`

The following pane will be shown when you enable this setting:

| Icon | Description                                                         |
| :--: | ------------------------------------------------------------------- |
| 🩹  | [10. Patches (Edge Case)](#10-patches-edge-case)                    |


## 2. General Settings

### 1. Appearance

#### Display Language

**Setting Key:** `displayLanguage`

You can change the display language, which is independent of the system language and/or Obsidian's language.  
**Note:** Not all messages are translated. Please revert to "Default" when reporting errors. Contributions to translations are always welcome!

#### Show Status Inside the Editor

**Setting Key:** `showStatusOnEditor`

Displays the synchronization status inside the editor.  
**Note:** Changes will be reflected after rebooting.

#### Show Status as Icons Only

**Setting Key:** `showOnlyIconsOnEditor`

Displays the synchronization status as icons only. This is useful if you want to save space on the status bar.

#### Show Status on the Status Bar

**Setting Key:** `showStatusOnStatusbar`

Displays the synchronization status on the status bar.  
**Default:** On.

### 2. Logging

#### Show Only Notifications

**Setting Key:** `lessInformationInLog`

Prevents detailed logging and shows only notifications. Please disable this option when reporting logs.

#### Verbose Log

**Setting Key:** `showVerboseLog`

Shows detailed logs. Please enable this option when reporting logs.


## 3. Remote Configuration

### 1. Remote Server

#### Remote Type

**Setting Key:** `remoteType`

Select the type of remote server.

### 2. Notification

#### Notify When Estimated Remote Storage Size Exceeds on Startup

**Setting Key:** `notifyThresholdOfRemoteStorageSize`

Set the threshold (in MB) for receiving a notification when the estimated remote storage size exceeds this value.  
**Note:** Set to 0 to disable this notification.

### 3. Confidentiality

#### End-to-End Encryption

**Setting Key:** `encrypt`

Enable end-to-end encryption. It is recommended to keep this enabled.  
**Note:** If you change the passphrase, you will need to rebuild the databases. You will be notified if this happens.

#### Passphrase

**Setting Key:** `passphrase`

Set the encryption passphrase.  
**Note:** Changing the passphrase will require rebuilding the databases. You will be notified if this happens.

#### Path Obfuscation

**Setting Key:** `usePathObfuscation`

By default, file paths are not obfuscated to improve performance. Enabling this will obfuscate file paths, which is useful if you want to hide the paths.

#### Use Dynamic Iteration Count (Experimental)

**Setting Key:** `useDynamicIterationCount`

This experimental feature is not recommended for general use. Enabling it will dynamically adjust the iteration count for encryption, which may improve performance.

---

### 4. Minio, S3, R2

#### Endpoint URL

**Setting Key:** `endpoint`

Set the endpoint URL for the object storage service.

#### Access Key

**Setting Key:** `accessKey`

Set the access key for the object storage service.

#### Secret Key

**Setting Key:** `secretKey`

Set the secret key for the object storage service.

#### Region

**Setting Key:** `region`

Set the region for the object storage service.

#### Bucket Name

**Setting Key:** `bucket`

Set the bucket name for the object storage service.

#### Use Custom HTTP Handler

**Setting Key:** `useCustomRequestHandler`

Enable this if your object storage service does not support CORS configuration.

#### Test Connection

Test the connection to the remote server.

#### Apply Settings

Apply the current settings.

---

### 5. CouchDB

#### URI

**Setting Key:** `couchDB_URI`

Set the URI for the CouchDB server.

#### Username

**Setting Key:** `couchDB_USER`

Set the username for CouchDB authentication.

#### Password

**Setting Key:** `couchDB_PASSWORD`

Set the password for CouchDB authentication.

#### Database Name

**Setting Key:** `couchDB_DBNAME`

Set the name of the database.

#### Test Database Connection

Test the connection to the CouchDB database. If the remote database is not found and you have the privileges to create a database, it will be created automatically.

#### Check and Fix Database Configuration

Check the database configuration for issues and automatically fix any problems found.

#### Apply Settings

Apply the current settings.


## 4. Sync Settings

### 1. Synchronization Preset

#### Presets

**Setting Key:** `preset`  
Apply a preset configuration for synchronization.

### 2. Synchronization Methods

#### Sync Mode

**Setting Key:** `syncMode`  
Choose the synchronization mode.

#### Periodic Sync Interval

**Setting Key:** `periodicReplicationInterval`  
Set the interval (in seconds) for periodic synchronization.

#### Sync on Save

**Setting Key:** `syncOnSave`  
Enable synchronization automatically whenever a file is saved.

#### Sync on Editor Save

**Setting Key:** `syncOnEditorSave`  
Enable synchronization automatically when a file is saved within the editor.

#### Sync on File Open

**Setting Key:** `syncOnFileOpen`  
Enable synchronization automatically when a file is opened.

#### Sync on Start

**Setting Key:** `syncOnStart`  
Enable synchronization to start automatically when Obsidian is launched.

#### Sync After Merging Files

**Setting Key:** `syncAfterMerge`  
Enable synchronization automatically after merging files.

### 3. Update Thinning

#### Batch Database Update

**Setting Key:** `batchSave`  
Reduce the frequency at which on-disk changes are reflected in the database.

#### Minimum Delay for Batch Database Updates

**Setting Key:** `batchSaveMinimumDelay`  
Set the minimum delay (in seconds) for saving to the local database after you stop typing or saving.

#### Maximum Delay for Batch Database Updates

**Setting Key:** `batchSaveMaximumDelay`  
Set the maximum delay (in seconds) before saving is performed forcefully.

### 4. Deletion Propagation (Advanced)

#### Use the Trash Bin

**Setting Key:** `trashInsteadDelete`  
Prevent files deleted in remote locations from being permanently deleted; they will be moved to the trash instead.

#### Keep Empty Folders

**Setting Key:** `doNotDeleteFolder`  
Normally, a folder is deleted if it becomes empty after synchronization. Enabling this setting will prevent the folder from being deleted.

### 5. Conflict Resolution (Advanced)

#### Always Overwrite with a Newer File (Beta)

**Setting Key:** `resolveConflictsByNewerFile`  
Automatically resolve conflicts by overwriting with the newer file. (Default: Off)

#### Postpone Resolution of Inactive Files

**Setting Key:** `checkConflictOnlyOnOpen`  
Postpone conflict resolution for inactive files until they are opened.

#### Postpone Manual Resolution of Inactive Files

**Setting Key:** `showMergeDialogOnlyOnActive`  
Postpone the manual resolution of conflicts for inactive files until they are active.

### 6. Sync Settings via Markdown (Advanced)

#### Filename

**Setting Key:** `settingSyncFile`  
Specify the markdown file where all settings will be saved. You will be notified when new settings are available. Different files can be set based on the platform.

#### Write Credentials in the File

**Setting Key:** `writeCredentialsForSettingSync`  
(Not recommended) Store credentials within the sync settings file.

#### Notify All Setting Files

**Setting Key:** `notifyAllSettingSyncFile`  
Enable notifications for all setting files.

### 7. Hidden Files (Advanced)

#### Hidden File Synchronization

Enable synchronization for hidden files.

#### Enable Hidden Files Sync

Enable or disable synchronization for hidden files.

#### Scan for Hidden Files Before Replication

**Setting Key:** `syncInternalFilesBeforeReplication`  
Enable or disable scanning for hidden files before replication starts.

#### Scan Hidden Files Periodically

**Setting Key:** `syncInternalFilesInterval`  
Set the interval (in seconds) to periodically scan for hidden files. Set to 0 to disable periodic scanning.


## 5. Selector (Advanced)

### 1. Normal Files

#### Synchronizing Files

Use a regular expression (RegExp) to filter files for synchronization. Leave empty to sync all files.

#### Non-Synchronizing Files

Use a regular expression (RegExp) to specify files that should not be synchronized. Any changes to local and remote files matching this pattern will be skipped.

#### Maximum File Size

**Setting Key:** `syncMaxSizeInMB`  
Set a maximum file size (in MB). Files larger than this size will be skipped during synchronization. If the file becomes smaller than the set size, it will be synchronized again.

#### (Beta) Use Ignore Files

**Setting Key:** `useIgnoreFiles`  
If enabled, changes to local files matching ignore file patterns will be skipped. Remote changes are determined using local ignore files.

#### Ignore Files

**Setting Key:** `ignoreFiles`  
Specify one or more ignore files (e.g., `.gitignore`, `.dockerignore`). Files matching patterns in these ignore files will not be synchronized.

### 2. Hidden Files (Advanced)

#### Ignore Patterns

Use ignore patterns to filter hidden files. These patterns define which files should be excluded from synchronization based on their characteristics (e.g., name, extension, etc.).

#### Add Default Patterns

Add default ignore patterns for hidden files to ensure they are excluded from synchronization.


## 6. Customization Sync (Advanced)

### 1. Customization Sync

#### Device Name

**Setting Key:** `deviceAndVaultName`  
Assign a unique name to each device in the synchronization network. This name must be unique across all synchronized devices. To edit this setting, disable customization sync first.

#### Per-File-Saved Customization Sync

**Setting Key:** `usePluginSyncV2`  
Enable this option to use per-file, efficient customization sync. This requires a small migration to enable and all devices should be updated to version 0.23.18. Once enabled, older versions will no longer be compatible.

#### Enable Customization Sync

**Setting Key:** `usePluginSync`  
Enable this setting to activate synchronization for customizations across devices.

#### Scan Customization Automatically

**Setting Key:** `autoSweepPlugins`  
Automatically scan for customization changes before replicating files.

#### Scan Customization Periodically

**Setting Key:** `autoSweepPluginsPeriodic`  
Set to scan for customization changes every 1 minute.

#### Notify Customization Updates

**Setting Key:** `notifyPluginOrSettingUpdated`  
Receive notifications when another device has made a new customization.

#### Open Dialog  
Open the customization sync dialog for manual adjustments.


## 7. Hatch

### 1. Reporting Issues

#### Report an Issue

Provide a report to inform about any issues encountered.

#### Write Logs to a File

**Setting Key:** `writeLogToTheFile`  
**Warning:** Enabling this will significantly impact performance. Logs will not be synchronized under the default name. Be cautious with logs, as they often contain sensitive information.

### 2. Scram Switches

#### Suspend File Watching

**Setting Key:** `suspendFileWatching`  
Temporarily stop monitoring file changes.

#### Suspend Database Reflection

**Setting Key:** `suspendParseReplicationResult`  
Temporarily stop reflecting database changes into storage files.

### 3. Recovery and Repair

#### Recreate Missing Chunks for All Files  
This will attempt to recreate missing chunks for all files. If there were any missing chunks, this may resolve errors.

#### Verify and Repair All Files  
Compare the content of files between the local database and storage. If discrepancies are found, you will be prompted to choose which version to keep.

#### Check and Convert Non-Path-Obfuscated Files  
Verify and convert files that are not path-obfuscated.

### 4. Reset

#### Reset to Non-Configured State  
Revert all settings back to the default, non-configured state.

#### Delete All Customization Sync Data  
Remove all customization synchronization data.


## 8. Advanced (Advanced)

### 1. Memory Cache

#### Memory Cache Size (Total Items)  
**Setting Key:** `hashCacheMaxCount`  
Limit the total number of items stored in the memory cache.

#### Memory Cache Size (Total Characters)  
**Setting Key:** `hashCacheMaxAmount`  
Limit the total number of characters stored in the memory cache (in megacharacters).

### 2. Local Database Tweak

#### Enhance Chunk Size  
**Setting Key:** `customChunkSize`  
Adjust the size of data chunks stored locally.

#### Use Splitting-Limit-Capped Chunk Splitter  
**Setting Key:** `enableChunkSplitterV2`  
If enabled, chunks will be split into no more than 100 items, though deduplication may be slightly weaker.

#### Use Segmented-Splitter  
**Setting Key:** `useSegmenter`  
If enabled, chunks will be split into semantically meaningful segments. Not all platforms support this feature.

### 3. Transfer Tweak

#### Fetch Chunks on Demand  
**Setting Key:** `readChunksOnline`  
If enabled, LiveSync will read chunks directly online instead of replicating them locally. Increasing the custom chunk size is recommended.

#### Batch Size of On-Demand Fetching  
**Setting Key:** `concurrencyOfReadChunksOnline`  
Control the batch size when fetching chunks online.

#### Delay for Consecutive On-Demand Fetches  
**Setting Key:** `minimumIntervalOfReadChunksOnline`  
Set a delay between consecutive online chunk fetches.

#### Send Chunks in Bulk  
**Setting Key:** `sendChunksBulk`  
If enabled, chunks will be sent in bulk, which can help in high-latency environments.

#### Maximum Size of Chunks to Send in One Request  
**Setting Key:** `sendChunksBulkMaxSize`  
Set the maximum size (in MB) for chunks sent in a single request.


## 9. Power Users (Power User)

### 1. Remote Database Tweak

#### Incubate Chunks in Document (Beta)  
**Setting Key:** `useEden`  
If enabled, newly created chunks are temporarily stored within the document and later promoted to independent chunks once stable.

#### Maximum Incubating Chunks  
**Setting Key:** `maxChunksInEden`  
The maximum number of chunks that can be incubated within the document. Excess chunks will immediately become independent.

#### Maximum Incubating Chunk Size  
**Setting Key:** `maxTotalLengthInEden`  
The maximum total size of chunks allowed in incubation. Chunks exceeding this size will be graduated to independent chunks.

#### Maximum Incubation Period  
**Setting Key:** `maxAgeInEden`  
The maximum time chunks can remain incubated within the document before being graduated to independent chunks.

#### Data Compression (Experimental)  
**Setting Key:** `enableCompression`  
Enable experimental data compression for chunks.

### 2. CouchDB Connection Tweak

#### Batch Size  
**Setting Key:** `batch_size`  
Set the number of change feed items to process at once (default: 50). Minimum value: 2.

#### Batch Limit  
**Setting Key:** `batches_limit`  
Define the number of batches to process simultaneously (default: 40). Minimum value: 2. This, along with batch size, controls how many documents are stored in memory at a time.

#### Use Timeouts Instead of Heartbeats  
**Setting Key:** `useTimeouts`  
If enabled, the connection will remain open for 60 seconds. If no change occurs, it will close and reopen the socket instead of staying open indefinitely. Useful for situations where proxies limit request durations.

### 3. Configuration Encryption

#### Encrypt Sensitive Configuration Items  
**Setting Key:** `configPassphraseStore`  
Enable encryption for sensitive configuration items.

#### Passphrase for Sensitive Configuration Items  
**Setting Key:** `configPassphrase`  
This passphrase will not sync across devices. It will reset to `Default` until manually configured again.


## 10. Patches (Edge Case)

### 1. Compatibility (Metadata)

#### Do Not Keep Metadata of Deleted Files  
**Setting Key:** `deleteMetadataOfDeletedFiles`  
Prevent retention of metadata for files that are deleted.

#### Delete Old Metadata of Deleted Files on Start-Up  
**Setting Key:** `automaticallyDeleteMetadataOfDeletedFiles`  
Automatically delete metadata for deleted files after a specified number of days (set to 0 to disable).

### 2. Compatibility (Conflict Behaviour)

#### Always Resolve Conflicts Manually  
**Setting Key:** `disableMarkdownAutoMerge`  
When enabled, a merge dialog will always appear, even if a sensible merge is possible.

#### Always Reflect Synchronized Changes Even if the Note Has a Conflict  
**Setting Key:** `writeDocumentsIfConflicted`  
Ensure synchronized changes are written, even if there’s a conflict.

### 3. Compatibility (Database Structure)

#### (Obsolete) Use an Old Adapter for Compatibility  
**Setting Key:** `useIndexedDBAdapter`  
Enables the older local database adapter for compatibility. This is obsolete after v0.17.16 and requires local database rebuilding.

#### Compute Revisions for Chunks (Previous Behaviour)  
**Setting Key:** `doNotUseFixedRevisionForChunks`  
Restores the previous behaviour of storing chunks with revisions based on their content.

#### Handle Files as Case-Sensitive  
**Setting Key:** `handleFilenameCaseSensitive`  
Treat file names as case-sensitive (previous behaviour).

### 4. Compatibility (Internal API Usage)

#### Scan Changes on Customization Sync  
**Setting Key:** `watchInternalFileChanges`  
Disables the use of internal API during synchronization.

### 5. Edge Case Addressing (Database)

#### Database Suffix  
**Setting Key:** `additionalSuffixOfDatabaseName`  
Automatically configures a suffix for databases to handle multiple vaults with the same name.

#### The Hash Algorithm for Chunk IDs (Experimental)  
**Setting Key:** `hashAlg`  
Select the hash algorithm used for chunk IDs.

### 6. Edge Case Addressing (Behaviour)

#### Fetch Database with Previous Behaviour  
**Setting Key:** `doNotSuspendOnFetching`  
Restores the previous behaviour for fetching databases.

#### Keep Empty Folder  
**Setting Key:** `doNotDeleteFolder`  
Prevents the deletion of empty folders after synchronization.

### 7. Edge Case Addressing (Processing)

#### Do Not Split Chunks in the Background  
**Setting Key:** `disableWorkerForGeneratingChunks`  
Disables background chunk splitting, reverting to UI thread processing.

#### Process Small Files in the Foreground  
**Setting Key:** `processSmallFilesInUIThread`  
Process files smaller than 1 KB on the UI thread.

### 8. Compatibility (Troubleshooting)

#### Do Not Check Configuration Mismatch Before Replication  
**Setting Key:** `disableCheckingConfigMismatch`  
Disables checks for configuration mismatches before replication.


## 11. Maintenance

### 1. Scram!

#### Lock Remote  
**Prevents synchronization** with other devices by locking the remote.

#### Emergency Restart  
**Flag file** to halt all operations and trigger a restart.

### 2. Data-Complementary Operations

#### Resend  
Resend all chunks to the remote.

#### Reset Journal Received History  
Resets the received history; items will be downloaded again, except those already synced from this device.

#### Reset Journal Sent History  
Resets the sent history; items will be sent again, except those already received by this device.

### 3. Rebuilding Operations (Local)

#### Fetch from Remote  
Restore or rebuild the local database using data from the remote.

#### Fetch Rebuilt DB (Save Local Documents Before)  
Restore the local database from the remote but use local chunks.

### 4. Total Overhaul

#### Rebuild Everything  
Rebuild both local and remote databases using local files.

### 5. Rebuilding Operations (Remote Only)

#### Perform Compaction  
**Discards non-latest Eden revisions** to reduce remote storage usage. Requires equivalent free space.

#### Overwrite Remote  
Overwrite the remote with the local database and passphrase.

#### Reset All Journal Counter  
Reset all journal histories; next sync will receive and send all items.

#### Purge All Journal Counter  
Clear all sending and receiving caches.

#### Make Empty the Bucket  
Delete all remote data.

### 6. Niches

#### (Obsolete) Clean Up Databases  
Remove unused chunks to shrink the database. Not always effective—use "Rebuild Everything" instead.

### 7. Reset

#### Discard Local Database to Reset or Uninstall Self-Hosted LiveSync  
Reset or uninstall the self-hosted LiveSync by discarding the local database.
