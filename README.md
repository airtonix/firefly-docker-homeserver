# firefly-docker-homeserver

Run Firefly 3 on your homeserver with a simple bulletproof approach to backup and restore.

```console
$ ./op help

🧑‍💻 Usage

$ ./op [command]

❓ Commands

new     ID           - Creates a new instance <ID>
run     ID           - Run an instance <ID>
backup  ID [NAME]    - Backup an existing instance <ID> with [NAME] defaults to a timestamp
restore ID NAME      - Restore backups <NAME> for an instance <ID>
```


## Create

Create a new firefly instance per financial year

```console
$ ./op new 2022
```

- creates a bunch of infrastructure files in `instances/2022/`
- backups are scheduled and stored in `instances/2022/backups/`


## Manual Backup

Backup running instances by peforming a msql dump of the DB and volume archive of the uploads

```console
$ ./op backup 2022
```

- creates a timestamped backup in `instances/2022/backups/`


## Restore

Restore available backups into an instance

```console
$ ./op restore 2022
```

- Restores backups from `instances/2022/backups/`
