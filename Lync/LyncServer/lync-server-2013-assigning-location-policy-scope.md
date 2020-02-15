---
title: 'Lync Server 2013 : affectation de l’étendue de la stratégie d’emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69218c3f5399b62fc67fe0d538a98f1bdadd3cf4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a>Affectation de l’étendue de la stratégie d’emplacement dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-06_

Comme pour les autres stratégies Lync Server, les stratégies d’emplacement peuvent être attribuées à plusieurs niveaux d’étendue : global, site et User. Toutefois, l’étendue des stratégies d’emplacement au niveau de l’utilisateur se comporte de manière légèrement différente de celle des autres stratégies Lync Server. Non seulement les stratégies d’emplacement par utilisateur peuvent être appliquées à des objets de point de terminaison (par exemple, les objets de contact des utilisateurs et du téléphone de partie commune), mais elles peuvent également être appliquées aux sites réseau Lync Server. Les sites réseau sont des regroupements de sous-réseaux clients associés à un emplacement géographique (mais pas nécessairement tous les sous-réseaux dans un site central ou un site de succursale). Tous les clients connectés aux sous-réseaux dans un site réseau utilisent automatiquement la stratégie d’emplacement affectée à ce site réseau. Dans les cas où une stratégie d’emplacement de niveau utilisateur est affectée à un utilisateur et à un site réseau, la stratégie d’emplacement de site réseau remplace les paramètres de stratégie par utilisateur.

Une stratégie d’emplacement est affectée à chaque site réseau. Différentes valeurs d’utilisations PSTN, d’URI de notification et d’URI de conférence sont affectées à chaque stratégie.

<div>


> [!NOTE]  
> La raison associée à ce comportement d’étendue de stratégie particulière est que lorsqu’un utilisateur hébergé sur un pool dans un site de bureau visite un autre site et doit passer un appel d’urgence, les paramètres de routage d’appels E9-1-1 adaptés à ce réseau sont appliqués, indépendamment du pool ou du site auquel l’utilisateur est affecté.



</div>

</div>

<span> </span>

</div>

</div>

</div>

