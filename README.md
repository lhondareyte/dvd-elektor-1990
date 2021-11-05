# Elektor DVD 1990-1999 (FR)

Correctifs pour accès WWW du DVDROM Elektor 1990-1999. Ce dépôt contient les liens des fichiers ayant un probleme de casse.
Il ne contient aucune donnée présente sur le DVD de l'éditeur.

## Installation

Copiez le contenu du DVD dans un dossier de votre serveur web:

Sous FreeBSD:
```
  mount -t cd9660 /dev/cd0 /mnt
  mkdir ${RootDocument}/Elektor-90
  find . -print | cpio -pdvmu ${RootDocument}/Elektor-90
  cd - && umount /mnt
  camcontrol eject cd0
```

Sous Linux 
```
  mount -t iso9660 /dev/scd0 /mnt
  mkdir ${RootDocument}/Elektor-90
  find . -print | cpio -pdvmu ${RootDocument}/Elektor-90
  cd - && umount /mnt
  eject /dev/scd0
```


Puis 
```
  cd ${RootDocument}/Elektor-90
  git clone https://github.com/lhondareyte/dvd-elektor-90.git
```

Vous pouvez supprimer tous les programmes obosolètes/inutiles avec la commande:
```
  make clean
```
