# Elektor DVD 1990-1999 (FR)

Correctifs pour accès WWW du DVDROM Elektor 1990-1999. Ce dépôt contient les liens des fichiers ayant un probleme de casse.
Il ne contient aucune donnée présente sur [le DVD de l'éditeur](https://www.elektor.fr/dvd-elektor-1990-1999-fr).

## Installation

Clonez ce dépôt à la racine de votre serveur HTTP (DocumentRoot)
```
  cd ${DocumentRoot}
  git clone https://github.com/lhondareyte/dvd-elektor-1990.git Elektor-1990
```

Copiez le contenu du DVD dans le dossier:

Sous FreeBSD:
```
  mount -t cd9660 /dev/cd0 /mnt ; cd /mnt
  find . -print | cpio -pdvmu ${DocumentRoot}/Elektor-1990
  cd - && umount /mnt
  camcontrol eject cd0
```

Sous Linux:
```
  mount -t iso9660 /dev/scd0 /mnt ; cd /mnt
  find . -print | cpio -pdvmu ${DocumentRoot}/Elektor-1990
  cd - && umount /mnt
  eject /dev/scd0
```

Vous pouvez supprimer tous les programmes obsolètes ou inutiles avec la commande:
```
  cd ${DocumentRoot}/Elektor-1990 && make clean
```
