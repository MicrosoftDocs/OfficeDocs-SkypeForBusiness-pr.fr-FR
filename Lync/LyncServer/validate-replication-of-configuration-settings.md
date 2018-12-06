---
title: Validation de la réplication des paramètres de configuration
TOCTitle: Validation de la réplication des paramètres de configuration
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205042(v=OCS.15)
ms:contentKeyID: 49297907
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Validation de la réplication des paramètres de configuration

 

_**Dernière rubrique modifiée :** 2012-10-19_

Vous pouvez valider la réplication des informations de configuration sur le serveur Edge en exécutant l’applet de commande Lync Server 2013**Get-CsManagementStoreReplicationStatus** sur l’ordinateur interne sur lequel se trouve le magasin central de gestion ou sur un ordinateur joint au domaine sur lequel les composants principaux de Lync Server 2013 sont installés.

Les résultats initiaux peuvent indiquer le statut de réplication « False » au lieu de « True ». Si tel est le cas, exécutez l’applet de commande **Invoke-CsManagementStoreReplication** et patientez le temps nécessaire pour que la réplication ait lieu avant de réexécuter l’applet de commande **Get-CsManagementStoreReplicationStatus**.

