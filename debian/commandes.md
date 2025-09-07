# 🐧 Guide Complet : Commandes Linux de Base

Le **shell** est une interface en ligne de commande qui permet d’entrer du texte, de l’interpréter et de le transmettre au système. C’est l’outil principal pour interagir avec Linux.

---

## 📑 Table des matières
- [🧹 Nettoyage d’écran](#-nettoyage-décran)
- [📂 Navigation entre répertoires](#-navigation-entre-répertoires)
- [📁 Création et gestion de répertoires](#-création-et-gestion-de-répertoires)
- [📄 Gestion des fichiers](#-gestion-des-fichiers)
- [🔍 Recherche](#-recherche)
- [⚙️ Permissions](#️-permissions)
- [📦 Gestion des paquets](#-gestion-des-paquets)
- [🌐 Réseau](#-réseau)
- [🛠️ Processus](#️-processus)
- [🚪 Quitter et éteindre](#-quitter-et-éteindre)

---

## 🧹 Nettoyage d’écran
```bash
clear
```
👉 Nettoie l’écran du terminal.

---

## 📂 Navigation entre répertoires
```bash
cd /path/
```
👉 `cd` = **Change Directory**, change de dossier courant.

Exemples :
```bash
cd ~            # aller dans le home
cd ..           # remonter d’un répertoire
cd /etc         # aller dans /etc
```

---

## 📁 Création et gestion de répertoires
```bash
mkdir nom
```
👉 Crée un dossier (Make Directory).

```bash
rmdir nom
```
👉 Supprime un dossier vide.

---

## 📄 Gestion des fichiers
```bash
touch fichier.txt
```
👉 Crée un fichier vide.

```bash
cp source.txt dest.txt
```
👉 Copie un fichier.

```bash
mv fichier.txt dossier/
```
👉 Déplace ou renomme un fichier.

```bash
rm fichier.txt
```
👉 Supprime un fichier.

---

## 🔍 Recherche
```bash
ls
```
👉 Liste les fichiers d’un dossier.

```bash
ls -l
```
👉 Liste détaillée (permissions, taille, date).

```bash
find / -name fichier.txt
```
👉 Recherche un fichier dans l’arborescence.

```bash
grep "mot" fichier.txt
```
👉 Recherche un mot dans un fichier.

---

## ⚙️ Permissions
```bash
chmod 755 script.sh
```
👉 Change les permissions.

```bash
chown user:group fichier
```
👉 Change le propriétaire.

---

## 📦 Gestion des paquets
*(selon la distribution)*

Debian/Ubuntu :
```bash
sudo apt update && sudo apt upgrade
sudo apt install package
```

Arch Linux :
```bash
sudo pacman -Syu
sudo pacman -S package
```

Fedora :
```bash
sudo dnf update
sudo dnf install package
```

---

## 🌐 Réseau
```bash
ping google.com
```
👉 Vérifie la connectivité.

```bash
curl ifconfig.me
```
👉 Affiche votre IP publique.

```bash
ss -tulnp
```
👉 Liste les ports en écoute.

---

## 🛠️ Processus
```bash
ps aux
```
👉 Liste les processus.

```bash
top
```
👉 Affiche en temps réel la charge et les processus.

```bash
kill -9 PID
```
👉 Tue un processus avec son PID.

---

## 🚪 Quitter et éteindre
```bash
exit
```
👉 Quitte le terminal.

```bash
shutdown now
```
👉 Éteint immédiatement.

```bash
reboot
```
👉 Redémarre le système.

---

✅ Ce guide couvre les bases essentielles du shell Linux pour la navigation, la gestion des fichiers, des paquets, du réseau et des processus.

