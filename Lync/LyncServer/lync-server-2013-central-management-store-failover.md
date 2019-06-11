---
title: Basculement du magasin central de gestion dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b320b3313f37a1912b909d018bbe37de5a997be
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-failover-in-lync-server-2013"></a>Basculement du magasin central de gestion dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-18_

Le magasin de gestion central contient des données de configuration relatives aux serveurs et services dans votre déploiement Lync 2013. Il fournit un stockage fiable schematized des données nécessaires pour définir, configurer, gérer, gérer, décrire et utiliser un déploiement Lync 2013. Il valide également les données afin de garantir la cohérence de la configuration.

Chaque déploiement Lync inclut un magasin de gestion central, hébergé par le serveur principal d’un pool frontal.

Lorsque vous établissez une jumelage de réserve qui inclut le pool hébergeant le magasin central de gestion, une base de données de magasin de gestion centrale de sauvegarde est configurée dans le pool de sauvegarde, et les services du magasin de gestion centrale sont installés dans les deux pools. À tout moment, l’une des deux bases de données de la Banque centrale de gestion est la forme de base active et l’autre est une réserve. Le contenu est répliqué par le service de sauvegarde de la forme de base active vers la veille.

Au cours d’un basculement de pool qui implique les pools hébergeant la Banque centrale de gestion, l’administrateur doit basculer sur le magasin de gestion central avant d’avoir basculé sur le pool frontal.

Une fois la récupération d’urgence effectuée, il n’est pas nécessaire de rebasculer le magasin central de gestion. Après la réparation, le magasin de gestion central dans le pool de sauvegarde d’origine peut rester le maître actif.

Les objectifs d’ingénierie du basculement du magasin central de gestion sont les suivants : un objectif de durée de reprise (RTO) de 5 minutes et 5 minutes pour chaque objectif de point de reprise (RPO).

</div>

<span> </span>

</div>

</div>

</div>

