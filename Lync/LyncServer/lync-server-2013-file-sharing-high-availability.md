---
title: 'Lync Server 2013 : haute disponibilité du partage de fichiers'
description: 'Lync Server 2013 : haute disponibilité du partage de fichiers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29b0a77d2d03460c640c66b8e8ce2a551edf2d73
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543360"
---
# <a name="file-sharing-high-availability-in-lync-server-2013"></a>Haute disponibilité du partage de fichiers dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-03-30_

Pour garantir la haute disponibilité du partage de fichiers Lync Server au sein d’un centre de données unique, vous pouvez utiliser le système de fichiers DFS. DFS prend en charge le basculement d’un serveur de fichiers vers un autre dans le même centre de données. Pour un déploiement à grande échelle, il est recommandé d’utiliser des serveurs de fichiers dédiés qui sont associés à l’aide de DFS.

En fonction de la taille de votre réseau et du niveau de résistance souhaité, vous pouvez utiliser une paire de serveurs pour héberger tous les partages de fichiers d’un site, ou utiliser une paire de serveurs par pool frontal.

DFS est un mécanisme de réplication de fichiers recommandé, sans engagement d’objectif de temps de récupération (RTO, Recovery Time Objective) ou d’objectif de point de récupération (RPO, Recovery Point Objective) publié. Le basculement entre les serveurs DFS doit être effectué rapidement, mais le délai de réplication des données peut empêcher les utilisateurs de poursuivre le travail en cours lorsque le basculement se produit.

Si vous utilisez DFS et que le magasin de données sur le partage de fichiers est crucial, vous devez sauvegarder fréquemment les partages de fichiers, par exemple toutes les 4 à 8 heures. Lorsqu’un partage de fichiers tombe en panne et que la réplication n’est pas à jour, vous pouvez utiliser la sauvegarde pour restaurer le contenu du serveur défaillant sur l’autre serveur qui est associé à ce serveur à présent indisponible.

</div>

<span> </span>

</div>

</div>

</div>

