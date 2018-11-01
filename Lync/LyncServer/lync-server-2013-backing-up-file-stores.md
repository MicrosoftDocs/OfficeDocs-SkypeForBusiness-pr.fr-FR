---
title: Sauvegarde des magasins de fichiers
TOCTitle: Sauvegarde des magasins de fichiers
ms:assetid: 1a7f4e93-aa3d-461e-878e-2c572baa1293
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202167(v=OCS.15)
ms:contentKeyID: 53095368
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sauvegarde des magasins de fichiers

 

_**Dernière rubrique modifiée :** 2013-02-17_

La sauvegarde des magasins de fichiers Lync Server comprend tous les fichiers et dossiers utilisés par les composants Lync Server :

## Pour sauvegarder des magasins de fichiers

1.  Pour rechercher les emplacements spécifiques de vos magasins de fichiers Lync Server, ouvrez le Générateur de topologie et recherchez le nœud **Magasins de fichiers**.

2.  Utilisez Robocopy ou un autre outil de gestion de système de fichiers pour copier chaque magasin de fichiers dans $Backup\\filestore.

