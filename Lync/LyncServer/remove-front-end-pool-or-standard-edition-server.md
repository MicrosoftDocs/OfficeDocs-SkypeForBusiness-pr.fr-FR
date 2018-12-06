---
title: Suppression d’un pool frontal ou un serveur Standard Edition
TOCTitle: Suppression d’un pool frontal ou un serveur Standard Edition
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49891421
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’un pool frontal ou un serveur Standard Edition

 

_**Dernière rubrique modifiée :** 2012-10-04_

Cette rubrique vous guide tout au long du processus de suppression d’un pool de serveurs frontaux ou d’un serveur frontal Standard Edition. Quand vous supprimez un pool de serveurs frontaux, vous supprimez chaque serveur frontal qui appartient à ce pool dans le cadre du processus de suppression du pool. Quand vous supprimez un serveur frontal Standard Edition, vous devez supprimer la définition du magasin SQL du Générateur de topologie.

## Pour supprimer un pool de serveurs frontaux

1.  Ouvrez le Générateur de topologie.

2.  Accédez au nœud Lync Server 2010.

3.  Développez **Pools frontaux Enterprise Edition** , développez le pool de serveurs frontaux, cliquez avec le bouton droit sur le pool de serveurs frontaux à supprimer, puis cliquez sur **Supprimer** .

4.  Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement de Lync Server si besoin.

## Pour supprimer un serveur frontal Standard Edition

1.  Ouvrez le Générateur de topologie.

2.  Accédez au nœud Lync Server 2010.

3.  Développez **Serveurs frontaux Standard Edition** , cliquez avec le bouton droit sur le serveur frontal à supprimer, puis cliquez sur **Supprimer** .

4.  Développez **Magasins SQL** , cliquez avec le bouton droit sur la base de données SQL Server associée au serveur frontal Standard Edition, puis cliquez sur **Supprimer** .
    
    > [!IMPORTANT]  
    > Vous devez supprimer la définition des bases de données SQL Server colocalisées du serveur frontal Standard Edition.

5.  Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement de Lync Server si besoin.

