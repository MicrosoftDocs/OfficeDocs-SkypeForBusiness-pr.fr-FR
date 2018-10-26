---
title: Vérification des paramètres de configuration
TOCTitle: Vérification des paramètres de configuration
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204885(v=OCS.15)
ms:contentKeyID: 49297205
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification des paramètres de configuration

 

_**Dernière rubrique modifiée :** 2012-09-06_

Vous pouvez valider la réplication des informations de configuration sur le serveur Edge en exécutant l’applet de commande Lync Server 2013**Get-CsManagementStoreReplicationStatus** sur l’ordinateur interne où se trouve le magasin central de gestion ou sur tout autre ordinateur lié au domaine sur lequel les composants principaux de Lync Server 2013 (OcsCore.msi) sont installés.

Les résultats initiaux peuvent indiquer le statut de réplication « False » au lieu de « True ». Si tel est le cas, exécutez l’applet de commande **Invoke-CsManagementStoreReplication** pour donner à la réplication le temps nécessaire de se terminer avant de réexécuter **Get-CsManagementStoreReplicationStatus**.

