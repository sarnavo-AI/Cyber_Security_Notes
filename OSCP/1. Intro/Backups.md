A _backup_ is a copy of data made at a certain point in time. Backups enable us to _restore_ data if it has been deleted or corrupted. Data can be deleted or corrupted in several different ways, for example, because of an attack (ransomware, wiper malware, etc.), human error, or natural disasters (electrical surges, fire, etc.), among other possibilities.

Since a backup is a copy of data at a specific point in time, restoring data using a backup only returns data to the state that it was in when the backup was taken. If that data does not change over time, this effectively allows us to ensure its availability and integrity. If it does change over time, restoration allows us to mitigate potential data loss.

	If files are actively being changed or updated - referred to as "hot" files - there is an inherent risk of data loss when restoring from a backup. This is because backups capture the state of data at a specific point in time.

## Types of backups

There are a few different types of backups: full, incremental, and differential:-
The table below summarizes these backup types:

| **Type**         | **Backs up**                         | **Backup Speed** | **Recovery Complexity** | **Cost**        |
| ---------------- | ------------------------------------ | ---------------- | ----------------------- | --------------- |
| **Full**         | All files                            | Slowest          | Simple                  | Most expensive  |
| **Differential** | Files changed since last full backup | Slower over time | Moderate complexity     | Moderate cost   |
| **Incremental**  | Files changed since last backup      | Fastest          | Most complex            | Least expensive |

## Types of backups based on state
There are two other types of backups that refer to the state of the system when the backup is made: hot and cold. A _hot backup_ is taken from a running, online system. We can create these backups without shutting down the system or service. The backup can be stored on the same computer as the original files or on a different designated computer. Hot backups can be performed periodically, on a scheduled basis, or as triggered by changes or specific conditions. Either way, this creates a backup of the current state of the system or files.

_Cold backups_, alternatively, are taken when the system or service is offline. Cold backups are safer in terms of data consistency, but require system downtime, which can be a significant drawback for systems that require full-time availability.


# How to store those backups
A hybrid approach using redundant backups is the safest approach. We can combine hot and cold backup strategies, as well as online and offline storage solutions. We should consider a strategy that makes the most sense given our business needs and level of accepted risk.

Specifically, we should focus on redundancy. We should adopt several different backup techniques so that if one backup system fails, we have another at our disposal. This creates _defense in depth_, a strategy that layers multiple security controls and measures to protect against a variety of different threats. The idea is that no single security measure is foolproof, so multiple layers of defense can help mitigate the risks of an attack.

### 3-2-1 Rule for storing backups
Backups must also be stored securely. One of the ways that we can do this is by encrypting them. We'll discuss encryption in the next section.

An effective backup strategy often follows the [3-2-1 rule](https://www.cisa.gov/sites/default/files/publications/data_backup_options.pdf), which is a best practice guideline for data redundancy and recovery. According to this rule, we should:

Keep at least _three copies of our data_: This includes the original data and at least two backups. Having multiple copies reduces the risk of data loss due to corruption or failure of a single copy.

Store copies on _two different types of media_: By using different storage media (such as internal hard drives, external drives, tapes, or cloud storage), we mitigate the risk associated with a specific medium failing.

Keep one copy offsite: Storing at least _one backup offsite_ protects our data from local disasters like fires, floods, or theft. This could be in a physical location or in a cloud-based storage service.

