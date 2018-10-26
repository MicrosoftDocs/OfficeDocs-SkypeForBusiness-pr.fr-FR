---
title: 'Lync Server 2013 : Configuration d’Enhanced 9-1-1'
TOCTitle: Configuration d’Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398390(v=OCS.15)
ms:contentKeyID: 49297317
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration d’Enhanced 9-1-1 dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-24_

Enhanced 9-1-1 (E9-1-1) est une fonctionnalité de notification d’urgence qui associe le numéro de téléphone de l’appelant à une adresse géographique ou postale. Au moyen de ces informations, le centre d’appels de la sécurité publique (PSAP) peut immédiatement contacter les services d’urgence et les dépêcher sur place pour porter secours à l’appelant.

Pour prendre en charge E9-1-1, le Lync Server 2013 doit être en mesure de bien associer un emplacement à un client et de vérifier que ces informations permettent d’acheminer l’appel d’urgence vers le PSAP le plus prooche.

Pour plus d’informations sur la planification d’un déploiement de E9-1-1, reportez-vous à [Planification des services d’urgence (E9-1-1) dans Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).

> [!IMPORTANT]  
> Lync Server 2013 prend uniquement en charge E9-1-1 aux États-Unis. Pour déployer E9-1-1, vous devez configurer une connexion SIP à un fournisseur de services E9-1-1 certifié, ou déployer une passerelle ELIN (Emergency Location Identification Number) vers un fournisseur de services E9-1-1 basé sur le réseau téléphonique commuté (RTC). Pour plus d’informations, reportez-vous à <a href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1) et serveur de médiation dans Lync Server 2013</a>. Pour plus d’informations sur la configuration de connexions de jonction, reportez-vous à <a href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013</a>.

## Dans cette section

  - [Configurer un itinéraire des communications vocales E9-1-1 dans Lync Server 2013](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [Créer des stratégies d’emplacement dans Lync Server 2013](lync-server-2013-create-location-policies.md)

  - [Configurer les informations de site pour E9-1-1 dans Lync Server 2013](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [Configurer la base de données d’emplacements dans Lync Server 2013](lync-server-2013-configure-the-location-database.md)

  - [Configurer les fonctionnalités E9-1-1 avancées dans Lync Server 2013](lync-server-2013-configure-advanced-e9-1-1-features.md)

