---
title: 'Lync Server 2013 : Planification de la haute disponibilité et de la récupération d’urgence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 092e59813f76690233a950cd8ce914df47146d37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-10-31_

Comme dans Lync Server 2010, le principal schéma de haute disponibilité pour la plupart des rôles serveur dans Lync Server 2013 repose sur la redondance du serveur via le regroupement. Si un serveur exécutant un rôle serveur particulier rencontre une défaillance, les autres serveurs du pool qui exécutent le même rôle assument la charge de ce serveur. Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.

Lync Server 2013 ajoute de nouvelles mesures de reprise après sinistre pour les pools front-end en introduisant la dispersion géographique de vos serveurs dans deux centres de données afin de garantir la continuation du service.

Lync Server 2013 améliore également la disponibilité élevée du serveur principal en prenant en charge la mise en miroir SQL synchrone pour vos bases de données principales.

Cette section décrit les principales fonctionnalités de haute disponibilité et de récupération d’urgence, ainsi que les actions que vous pouvez effectuer pour une disponibilité élevée et une reprise après sinistre pour vos autres rôles de serveur.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Récupération d’urgence de pool frontal dans Lync Server 2013](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Récupération d’urgence de serveur Edge dans Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

  - [Planification de la résistance Voix Entreprise dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Fonctionnalités de gestion des appels pour la récupération d’urgence dans Lync Server 2013](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [Configuration d’un serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Résistance de sites métropolitains Lync Server 2010](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

