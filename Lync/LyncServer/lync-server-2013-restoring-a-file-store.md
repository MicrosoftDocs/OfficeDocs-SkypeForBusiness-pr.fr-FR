---
title: Restauration d’un magasin de fichiers
TOCTitle: Restauration d’un magasin de fichiers
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202180(v=OCS.15)
ms:contentKeyID: 53095456
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restauration d’un magasin de fichiers

 

_**Dernière rubrique modifiée :** 2013-02-18_

Les magasins de fichiers pour Standard Edition sont généralement stockés sur le serveur Standard Edition. Les magasins de fichiers pour Enterprise Edition sont généralement stockés sur un serveur de fichiers ou un cluster. La procédure suivante décrit comment restaurer un magasin de fichiers.

## Pour restaurer un magasin de fichiers

1.  En cas de défaillance d’un magasin de fichiers, copiez le magasin de fichiers approprié à partir de $Backup\\ vers l’emplacement du magasin de fichiers sur le serveur de fichiers ou le serveur Standard Edition, puis partagez le dossier.
    
    > [!IMPORTANT]  
    > Le nom et le chemin d’accès au magasin de fichiers restauré doivent être exactement identiques à ceux du magasin de fichiers sauvegardé, afin que les composants qui utilisent les fichiers puissent y accéder.

2.  Si nécessaire, définissez les listes de contrôle d’accès pour le magasin de fichiers. Sur la ligne de commande, tapez :
    
        Enable-CsTopology
    
    > [!NOTE]  
    > Cette étape est obligatoire uniquement si vous n’avez pas exécuté l’Générateur de topologie durant le processus de restauration.
