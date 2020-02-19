---
title: Basculement du magasin central de gestion Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d19b045e23efa39c9f70f70ba7ac0236e77cc13
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="central-management-store-failover-in-lync-server-2013"></a>Basculement du magasin central de gestion dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

Le magasin central de gestion contient des données de configuration sur les serveurs et les services dans votre déploiement Lync 2013. Il fournit un stockage robuste et schématisées des données nécessaires pour définir, configurer, gérer, gérer, décrire et exploiter un déploiement Lync 2013. Il valide également les données afin de garantir la cohérence de la configuration.

Chaque déploiement Lync comprend un magasin central de gestion, hébergé par le serveur principal d’un pool frontal.

Lorsque vous établissez un jumelage de pools qui inclut le pool qui héberge le magasin central de gestion, une base de données du magasin central de gestion de sauvegarde est configurée dans le pool de sauvegarde et les services du magasin central de gestion sont installés dans les deux pools. À tout moment, l’une des deux bases de données du magasin central de gestion est la forme de base active et l’autre est une mise en veille. Le contenu est répliqué par le service de sauvegarde de la forme de base active vers la mise en veille.

Au cours d’un basculement de pool qui implique les pools hébergeant le magasin central de gestion, l’administrateur doit basculer le magasin central de gestion avant de basculer sur le pool frontal.

Une fois le sinistre réparé, il n’est pas nécessaire de restaurer le magasin central de gestion. Après la réparation, le magasin central de gestion dans le pool de sauvegarde d’origine peut demeurer comme la forme de base active.

Les objectifs d’ingénierie du basculement du magasin central de gestion sont de 5 minutes pour l’objectif de temps de récupération (RTO) et de 5 minutes pour l’objectif de point de récupération (RPO).

</div>

<span> </span>

</div>

</div>

</div>

