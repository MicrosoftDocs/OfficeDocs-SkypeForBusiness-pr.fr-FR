---
title: 'Lync Server 2013: haute disponibilité du partage de fichiers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b61a4980c854b6cb79bedbe482bec204a541879f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a>Forte disponibilité du partage de fichiers dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-03-30_

Pour garantir une haute disponibilité du partage de fichiers Lync Server au sein d’un seul centre de données, vous pouvez utiliser le système de fichiers DFS. DFS prend en charge le basculement d’un serveur de fichiers vers un autre dans le même centre de données. Pour un déploiement à grande échelle, il est recommandé d’utiliser des serveurs de fichiers dédiés associés à l’aide de DFS.

En fonction de la taille de votre réseau et de la capacité de résilience souhaitée, vous pouvez utiliser une paire de serveurs pour héberger tous les partages de fichiers dans un site, ou utiliser une paire par pool frontal.

DFS est un mécanisme de réplication de fichiers recommandé, sans engagement d’objectif de temps de récupération (RTO, Recovery Time Objective) ou d’objectif de point de récupération (RPO, Recovery Point Objective) publié. Le basculement entre les serveurs DFS doit être effectué rapidement, mais le délai de réplication des données peut empêcher les utilisateurs de continuer à travailler en cours lorsque le basculement a lieu.

Si vous utilisez le système de fichiers DFS et le magasin de données sur le partage de fichiers est essentiel, il est recommandé de sauvegarder les fichiers partagés, par exemple tous les 4 à 8 heures. Lorsqu’un partage de fichiers ne fonctionne pas et que la réplication n’est pas à jour, vous pouvez utiliser la sauvegarde pour restaurer le contenu du serveur défaillant sur l’autre serveur associé à ce serveur à présent indisponible.

</div>

<span> </span>

</div>

</div>

</div>

