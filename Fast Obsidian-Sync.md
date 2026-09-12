
Данный документ необходим для быстрой синхронизации всех заметок при работе на чистом устройстве.

```
mkdir C:\Users\ustimenko.viktor\Documents\Obsidian Vault
mkdir C:\Users\ustimenko.viktor\Documents\Obsidian Vault\Obsidian-Sync
cd /d C:\Users\ustimenko.viktor\Documents\Obsidian Vault\Obsidian-Sync
git init
git config --global user.name "Viktor.Work"
git config --global user.email "Viktor@Work"
git checkout -b main origin/main
git remote add origin https://github.com/depotion2586/Obsidian-Sync
git pull 
```