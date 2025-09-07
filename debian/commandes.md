# Référence des commandes Linux (référence large, travaillée)

> Remarque : il est impossible de lister **toutes** les commandes existantes (dépend de la distribution et des paquets installés). Ci‑dessous : une **référence exhaustive des commandes standards et usuelles** trouvées sur la plupart des systèmes GNU/Linux, organisée et commentée.

---

## Mode d'emploi
- Chaque ligne : `commande [options]` — brève description.
- Pour détails : `man commande` ou `commande --help`.
- Recherche rapide de commandes : `apropos sujet`, `which cmd`, `whereis cmd`.

---

## Navigation & fichiers
- `pwd` — affiche le répertoire courant
- `ls` `ls -l` `ls -a` — lister le contenu
- `cd <chemin>` — changer de répertoire
- `pushd` / `popd` — gérer pile de répertoires
- `mkdir <dir>` — créer dossier
- `rmdir <dir>` — supprimer dossier vide
- `rm -r <dir>` — supprimer dossier récursif
- `cp <src> <dst>` — copier fichier/dossier (`-r` récursif)
- `mv <src> <dst>` — déplacer/renommer
- `ln -s <target> <link>` — lien symbolique
- `touch <file>` — créer fichier vide / mettre à jour la date
- `stat <file>` — informations sur fichier
- `file <file>` — détecter type de fichier
- `tree` — arborescence (si installé)

## Lecture & édition de texte
- `cat file` — affiche fichier
- `tac file` — affiche en sens inverse
- `nl file` — afficher avec numéros de ligne
- `less file` — pagination
- `more file` — pagination basique
- `head -n N file` — premières lignes
- `tail -n N file` / `tail -f file` — dernières lignes / suivi
- `sed` — stream editor (substitutions, etc.)
- `awk` — traitement texte avancé
- `cut` — découper colonnes
- `paste` — coller colonnes
- `sort` — trier
- `uniq` — supprimer doublons consécutifs
- `tr` — translitération / suppression
- `wc` — compte lignes/mots/caractères
- `ed`, `vi`/`vim`, `nano` — éditeurs

## Recherche & filtrage
- `grep pattern file` — chercher motif
- `egrep` / `fgrep` — variantes
- `ripgrep` (`rg`) — grep moderne (si installé)
- `find <path> -name pattern` — trouver fichiers
- `locate name` — rechercher via base de données `mlocate`
- `whereis` — localise binaire, source, man
- `which` — chemin du binaire dans $PATH
- `apropos` — recherche dans les pages man

## Permissions & utilisateurs
- `chmod` — changer permissions (`u/g/o`, `rwx`, ou mode octal)
- `chown user:group file` — changer propriétaire
- `chgrp group file` — changer groupe
- `umask` — masque de création de permissions
- `su - user` — changer d'utilisateur
- `sudo cmd` — exécuter en root
- `sudo -i` / `sudo -s` — shell root
- `id` — identifiants utilisateur
- `whoami` — nom utilisateur courant
- `users` / `who` / `w` — utilisateurs connectés
- `passwd` — changer mot de passe
- `adduser` / `useradd` — ajouter utilisateur
- `deluser` / `userdel` — supprimer utilisateur
- `groupadd` / `groupdel` — gestion des groupes

## Processus & gestion
- `ps aux` — état des processus
- `top` — monitor en temps réel
- `htop` — version interactive (si installé)
- `pgrep pattern` — trouver PID par motif
- `pkill pattern` — tuer par motif
- `kill PID` / `kill -9 PID` — envoyer signaux
- `nice -n N cmd` — démarrer process avec priorité
- `renice` — changer priorité
- `nohup cmd &` — détacher process
- `systemd-cgls` / `systemd-cgtop` — cgroups (systemd)

## Services & systemd
- `systemctl status service` — état
- `systemctl start|stop|restart|reload service` — gérer
- `systemctl enable|disable service` — activer au boot
- `systemctl daemon-reload` — recharger unités
- `journalctl -u service` — logs d’un service
- `journalctl -f` — suivre logs système

## Démarrage, arrêts, pilotes
- `reboot` — redémarrer
- `shutdown -h now` — éteindre
- `poweroff` — éteindre
- `systemctl reboot` / `systemctl poweroff`
- `lsmod` — modules chargés
- `modprobe <module>` — charger module
- `rmmod <module>` — décharger module
- `dmesg` — messages kernel

## Disques et partitions
- `lsblk` — liste block devices
- `blkid` — identifiants/UUID
- `fdisk -l` — partition table (MBR)
- `parted` — partitionnement GPT/MBR
- `mkfs.ext4 /dev/sdXn` — formater (exemple ext4)
- `mount /dev/sdXn /mnt` — monter
- `umount /mnt` — démonter
- `df -h` — espace disque
- `du -sh dir` — taille d’un dossier
- `pv`, `dd` — transfert bas niveau
- `cryptsetup` — LUKS chiffrage

## Réseau
- `ip addr` / `ip a` — adresses
- `ip link` — interfaces
- `ip route` — table de routage
- `ifconfig` — (legacy) interfaces
- `ss -tulnp` — sockets / ports écoutés
- `netstat -tulnp` — (legacy)
- `ping host` — test ICMP
- `traceroute host` — traceroute
- `tracepath` — traceroute sans root
- `curl` — requêtes HTTP et autres
- `wget` — téléchargement
- `nc` / `ncat` — netcat pour tests TCP/UDP
- `dig` / `nslookup` — DNS
- `iptables` / `nft` — firewall
- `ufw` — frontend iptables (Ubuntu)
- `nmcli` / `nmtui` — NetworkManager control

## Paquets & mise à jour
- Debian/Ubuntu: `apt update`, `apt upgrade`, `apt install pkg`, `apt remove pkg`
- Debian low-level: `dpkg -i package.deb`, `dpkg -l`
- Arch: `pacman -Syu`, `pacman -S pkg`, `pacman -R pkg`
- Fedora: `dnf update`, `dnf install pkg`
- openSUSE: `zypper refresh`, `zypper install pkg`
- RPM: `rpm -i package.rpm`, `rpm -qa`
- Snap: `snap install pkg`
- Flatpak: `flatpak install repo pkg`

## Compression / Archivage
- `tar -cf archive.tar files...` — créer tar
- `tar -xvf archive.tar` — extraire tar
- `tar -czf archive.tar.gz` / `-xzf` — gzip
- `tar -cjf archive.tar.bz2` / `-xjf` — bzip2
- `zip` / `unzip`
- `gzip` / `gunzip`
- `7z` — si p7zip installé

## Sauvegarde & transfert
- `rsync -avz src dst` — synchronisation
- `scp src user@host:dst` — copie sécurisée
- `sftp` — ftp over SSH
- `ssh user@host` — shell distant
- `ssh-keygen` — clés SSH
- `ssh-copy-id user@host` — installer clé

## Debug & diagnostic
- `strace -p PID` / `strace cmd` — appels système
- `ltrace` — appels de bibliothèques
- `perf` — profilage
- `valgrind` — détecter fuites mémoire
- `tcpdump` — capture paquets
- `wireshark` — analyse réseau (GUI)

## Développement & compilation
- `make` / `make install`
- `gcc` / `g++` — compilateurs
- `ldd bin` — bibliothèques partagées
- `objdump`, `nm`, `readelf` — inspecter binaires
- `git` — gestion de version
- `docker` / `podman` — conteneurs
- `systemtap`, `bcc`, `bpftrace` — tracing avancé

## Cryptographie & sécurité
- `openssl` — commandes SSL/TLS
- `gpg` — chiffrement/signature
- `fail2ban-client` — gestion fail2ban
- `selinux` tools: `sestatus`, `setenforce`

## Locales, date & heure
- `date` — afficher/format date
- `timedatectl` — configurer time/date/ntp
- `hwclock` — horloge matérielle
- `locale` — infos locales

## Journalisation et logs
- `journalctl` — logs systemd
- `tail -f /var/log/syslog` ou `/var/log/messages`
- `logrotate` — rotation logs

## Scripting & automatisation
- `bash`, `sh`, `dash`, `zsh` — shells
- `crontab -e` — planifier tâches (cron)
- `systemd timers` — timers systemd
- Variables, redirections (`>`, `>>`), pipes (`|`), substitution (`$()`)

## Outils courants supplémentaires
- `bash`, `zsh`, `fish` — shells interactifs
- `screen`, `tmux` — multiplexeurs de terminal
- `rsync`, `nc`, `socat`
- `sed`, `awk`, `perl`, `python3` — traitement
- `jq` — JSON CLI
- `xargs` — construire commandes à partir d’entrée
- `env`, `printenv` — variables d’environnement
- `export` — exporter variable

## Commandes d’aide & documentation
- `man <commande>` — page man
- `--help` option souvent disponible
- `info <commande>` — documentation info
- `whatis <commande>` — brève description
- `apropos mot` — recherche man pages

---

## Organisation recommandée pour ton repo
- `commands/` → fichiers par catégorie (`navigation.md`, `fichiers.md`, `réseau.md`, ...)
- `cheatsheets/` → fichiers courts avec commandes fréquentes
- `examples/` → snippets réels et scripts
- `tools-list.md` → liste d’outils installés et utilité

---

## Clause finale
Ce document couvre des **centaines** de commandes courantes. Si tu veux un export formaté (Markdown) prêt à placer dans ton repo, je peux générer :
- un jeu de fichiers catégorisés (installation rapide),
- ou un seul `COMMANDS.md` complet.

Pas de emojis, format pro, direct.

