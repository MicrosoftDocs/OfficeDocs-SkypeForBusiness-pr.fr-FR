---
title: 'Lync Server 2013 : Haute disponibilité du partage de fichiers'
TOCTitle: Haute disponibilité du partage de fichiers
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205203(v=OCS.15)
ms:contentKeyID: 49298655
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Haute disponibilité du partage de fichiers dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-03-30_

Pour garantir la haute disponibilité du partage de fichiers Lync Server dans un centre de données unique, vous pouvez utiliser le système de fichiers DFS. DFS prend en charge le basculement d’un serveur de fichiers vers un autre dans le même centre de données. Pour un déploiement à grande échelle, il est recommandé d’utiliser des serveurs de fichiers dédiés associés à l’aide de DFS.

En fonction de la taille de votre réseau et du niveau de résistance souhaité, vous pouvez utiliser une paire de serveurs pour héberger tous les partages de fichiers d’un site, ou utiliser une paire de serveurs par pool frontal.

DFS est un mécanisme de réplication de fichiers recommandé, sans engagement d’objectif de temps de récupération (RTO, Recovery Time Objective) ou d’objectif de point de récupération (RPO, Recovery Point Objective) publié. Le basculement entre les serveurs DFS doit être effectué rapidement, mais le délai de réplication des données peut empêcher les utilisateurs de poursuivre le travail en cours lorsque le basculement se produit.

Si vous utilisez DFS et que le magasin de données sur le partage de fichiers est crucial, vous devez sauvegarder fréquemment les partages de fichiers, par exemple toutes les 4 à 8 heures. Lorsqu’un partage de fichiers ne fonctionne pas et que la réplication n’est pas à jour, vous pouvez utiliser la sauvegarde pour restaurer le contenu du serveur défaillant sur l’autre serveur associé à ce serveur à présent indisponible.

