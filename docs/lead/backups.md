# Backing up Lead
Making Backups for Lead is really easy.
1. Locate the `plugins/Lead/teams.yml` file. 
2. Download the `teams.yml` file.
3. All set! Save that file somewhere safe.

# Loading Backups
To loading backups is still really easy. There are 1 of 2 ways you can load a backup.
- Stop the server.
  - Delete `plugins/Lead/teams.yml`
  - Import or upload your backed up `teams.yml` file.
  - Start the server.
- Delete `plugins/Lead/teams.yml`
  - Import or upload your backed up `teams.yml` file.
  - Run `/team reload -t`. (The `-t` flag is to force reload teams.)