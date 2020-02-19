---
title: 'Lync Server 2013 : planification de la haute disponibilité et de la récupération d’urgence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7ba7e58f29bb4e54972804fbe338c2e1345e91e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-31_

Comme dans Lync Server 2010, le principal modèle de haute disponibilité pour la plupart des rôles serveur dans Lync Server 2013 est basé sur la redondance des serveurs via la mise en pool. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur. Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.

Lync Server 2013 ajoute de nouvelles mesures de récupération d’urgence pour les pools frontaux en introduisant la dispersion géographique de vos serveurs dans deux centres de données pour assurer la continuité du service en cas de panne d’un pool ou d’un site.

Lync Server 2013 améliore également la haute disponibilité des serveurs principaux en prenant en charge la mise en miroir SQL synchrone pour vos bases de données principales.

Cette section explique ces fonctionnalités majeures de haute disponibilité et de récupération d’urgence, et explique par ailleurs comment procéder pour assurer la haute disponibilité et la récupération d’urgence de vos autres rôles serveur.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Récupération d’urgence de pool frontal dans Lync Server 2013](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Récupération d’urgence de serveur Edge dans Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

  - [Planification de la résistance voix entreprise dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Fonctionnalités de gestion des appels pour la récupération d’urgence dans Lync Server 2013](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [Configuration du serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Résilience de site métropolitain Lync Server 2010](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

