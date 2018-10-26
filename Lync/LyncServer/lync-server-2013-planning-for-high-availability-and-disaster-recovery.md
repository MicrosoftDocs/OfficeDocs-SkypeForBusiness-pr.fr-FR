---
title: "Lync Server 2013 : Plan. de la haute dispo. et de la récupération d’urgence"
TOCTitle: Planification de la haute disponibilité et de la récupération d’urgence
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204703(v=OCS.15)
ms:contentKeyID: 49296357
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-10-31_

Comme dans Lync Server 2010, le principal schéma de haute disponibilité pour la plupart des rôles serveur dans Lync Server 2013 repose sur la redondance des serveurs via la mise en pool. Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur. Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.

Lync Server 2013 apporte de nouvelles mesures de récupération d’urgence pour les pools frontaux en introduisant la dispersion géographique de vos serveurs dans deux centres de données afin d’assurer la continuité du service si un pool ou un site entier venait à cesser de fonctionner.

Lync Server 2013 optimise par ailleurs la haute disponibilité des serveurs principaux en prenant en charge la mise en miroir SQL synchrone de vos bases de données principales.

Cette section explique ces fonctionnalités majeures de haute disponibilité et de récupération d’urgence et indique comment procéder pour assurer la haute disponibilité et la récupération d’urgence de vos autres rôles serveur.

## Dans cette section

  - [Récupération d’urgence de pool frontal dans Lync Server 2013](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Récupération d’urgence de serveur Edge dans Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

  - [Planification de la résistance Voix Entreprise dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Fonctionnalités de gestion des appels pour la récupération d’urgence dans Lync Server 2013](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [Configuration d’un serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Résistance de sites métropolitains Lync Server 2010](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

