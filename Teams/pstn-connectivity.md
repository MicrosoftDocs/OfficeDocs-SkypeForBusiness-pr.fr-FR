---
title: Options de connectivité RTC
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 07/08/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: En savoir plus sur Teams options d’appel (connectivité RTC) et les décisions que vous prendrez pour votre organisation.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f37265a445a4b7361cdda8e6729944bb5250b029
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675806"
---
# <a name="pstn-connectivity-options"></a>Options de connectivité RTC

Microsoft fournit des fonctionnalités complètes de Exchange de branche privée (PBX) pour votre organisation via Système téléphonique. Toutefois, pour permettre aux utilisateurs de passer des appels en dehors de votre organisation, vous devez vous connecter Système téléphonique au réseau téléphonique commuté (RTC).

Cet article se concentre sur les options de connectivité RTC. Pour plus d’informations sur les solutions vocales Microsoft, y compris des détails sur Système téléphonique fonctionnalités, consultez [Planifier votre solution vocale Teams](cloud-voice-landing-page.md).

Pour connecter Système téléphonique au rtc, vous pouvez choisir parmi les options suivantes :

- [**Forfait d’appels**](#phone-system-with-calling-plan). Une solution tout-dans-le-cloud avec Microsoft comme opérateur RTC.

- [**Operator Connect**](#phone-system-with-operator-connect). Avec Operator Connect, si votre opérateur existant participe au programme Microsoft Operator Connect, il peut gérer les contrôleurs de frontière de session et les appels RTC.

- [**Le routage direct**](#phone-system-with-direct-routing), qui vous permet d’utiliser votre propre opérateur RTC en connectant vos contrôleurs de frontière de session (SBC) à Système téléphonique.

Vous pouvez également choisir une combinaison d’options, ce qui vous permet de concevoir une solution pour un environnement complexe ou de gérer une migration en plusieurs étapes.

L’option ou les options que vous choisissez affectent la façon dont certaines fonctionnalités Système téléphonique sont configurées. Pour plus d’informations, consultez [les considérations relatives à la configuration](#configuration-considerations) plus loin dans cet article.

## <a name="phone-system-with-calling-plan"></a>Système téléphonique avec forfait d’appels

Système téléphonique avec forfait d’appels est la solution vocale tout-en-cloud de Microsoft pour les utilisateurs Teams. Cette solution est l’option la plus simple qui connecte Système téléphonique au rtc. Avec cette option, Microsoft agit comme votre opérateur RTC, comme illustré dans le diagramme suivant :

![Le diagramme 1 montre Système téléphonique avec plan d’appel.](media/voice-solutions-simple.png)

Si vous répondez oui à ce qui suit, Système téléphonique avec forfait d’appels est la solution qui vous convient :

- Le forfait d’appels est disponible dans votre région.
- Vous n’avez pas besoin de conserver votre opérateur RTC actuel.
- Vous souhaitez utiliser l’accès géré par Microsoft au rtc.

Avec cette option :

- Vous obtenez Système téléphonique avec des forfaits d’appels nationaux ou internationaux ajoutés qui permettent d’appeler des téléphones dans le monde entier (en fonction du niveau de service sous licence).

- Vous n’avez pas besoin de déploiement ou de maintenance d’un déploiement&mdash;local, car le plan d’appel fonctionne hors de Microsoft 365.

- Remarque : vous pouvez connecter un contrôleur de frontière de session (SBC) pris en charge via le routage direct pour l’interopérabilité avec des PBX tiers, des périphériques analogiques et d’autres équipements de téléphonie pris en charge par le SBC.

Cette option nécessite une connexion ininterrompue à Microsoft 365.

Pour plus d’informations sur le forfait d’appels, consultez les articles suivants :

- [Quelle forfait d’appels vous convient le mieux ?](calling-plan-landing-page.md)
- [Comment acheter un forfait d’appels](calling-plans-for-office-365.md)
- [Disponibilité des forfaits d’appels par pays et par région](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Configurer le plan d’appel](set-up-calling-plans.md)

## <a name="phone-system-with-operator-connect"></a>Système téléphonique avec Operator Connect

Avec Operator Connect, si votre opérateur existant participe au programme Microsoft Operator Connect, il peut gérer le service d’appel RTC à Teams. Votre opérateur gère les services d’appel RTC et les contrôleurs de frontière de session , ce qui vous permet d’économiser sur l’achat et la gestion du matériel.

Operator Connect peut être la solution appropriée pour votre organisation si :

- Le plan d’appel Microsoft n’est pas disponible dans votre emplacement géographique.
- Votre opérateur préféré participe au programme Microsoft Operator Connect.
- Vous souhaitez trouver un nouveau transporteur pour activer l’appel dans Teams.

Pour plus d’informations sur les avantages et les exigences de Operator Connect et pour obtenir la liste des transporteurs participant à ce programme, voir [Plan Operator Connect](operator-connect-plan.md). Pour plus d’informations sur la configuration de Operator Connect, consultez [Configurer Operator Connect](operator-connect-configure.md).

## <a name="phone-system-with-direct-routing"></a>Système téléphonique avec routage direct

Cette option connecte Système téléphonique à votre réseau téléphonique à l’aide du routage direct, comme illustré dans le diagramme suivant : 

![Le diagramme 5 montre Système téléphonique avec routage direct.](media/voice-solution-with-direct-routing.png)

Si vous répondez oui aux questions suivantes, Système téléphonique avec le routage direct est la solution qui vous convient :

- Vous souhaitez utiliser Teams avec Système téléphonique.
- Vous devez conserver votre opérateur RTC actuel.
- Vous souhaitez combiner le routage, avec certains appels qui passent par forfait d’appels, d’autres par le biais de votre opérateur.
- Vous devez interagir avec des PBX tiers et/ou des équipements tels que des pagaeurs de surcharge, des périphériques analogiques, etc.

Avec cette option :

- Vous connectez votre propre contrôleur de frontière de session (SBC) pris en charge à Système téléphonique sans avoir besoin de logiciels locaux supplémentaires.

- Vous pouvez utiliser pratiquement n’importe quel opérateur téléphonique avec Système téléphonique.

- Vous pouvez configurer et gérer cette option, ou elle peut être configurée et gérée par votre opérateur ou partenaire (demandez si votre opérateur ou partenaire fournit cette option).

- Vous pouvez configurer l’interopérabilité entre vos équipements&mdash;de téléphonie tels qu’un PBX tiers et des appareils analogiques&mdash;et Système téléphonique.

Cette option nécessite les éléments suivants :

- Connexion ininterrompue à Microsoft 365.

- Déploiement et maintenance d’un SBC pris en charge.

- Un contrat avec un transporteur tiers.
  (Sauf si elle est déployée en tant qu’option permettant de fournir une connexion à pbX tiers, à des périphériques analogiques ou à d’autres équipements de téléphonie pour les utilisateurs qui sont en Système téléphonique avec forfait d’appels.)

Pour plus d’informations sur le routage direct, consultez les articles suivants :

- [Planifier le routage direct](direct-routing-plan.md)
- [Configurer le routage direct](direct-routing-configure.md)
- [Gérer les stratégies de routage vocal à utiliser avec le routage direct](manage-voice-routing-policies.md)
- [Planifier le routage géodépendant pour le routage direct](location-based-routing-plan.md)
- [Liste des contrôleurs de frontière de session certifiés pour le routage direct](direct-routing-border-controllers.md)

## <a name="configuration-considerations"></a>Considérations relatives à la configuration

La plupart des fonctionnalités Système téléphonique sont les mêmes, quelle que soit l’option de connectivité RTC que vous choisissez. Par exemple, les paramètres d’appel sans réponse et de transfert, le transfert d’appel, la musique personnalisée en attente, le parc d’appels, la ligne partagée et les applications vocales sont tous disponibles. Pour obtenir la liste complète des fonctionnalités de Système téléphonique, consultez [ce que vous obtenez avec Système téléphonique](here-s-what-you-get-with-phone-system.md).

Toutefois, certaines différences de fonctionnalités affectent la façon dont vous configurez certaines fonctionnalités Système téléphonique. Par exemple, le routage direct nécessite des étapes supplémentaires pour configurer le routage des appels. Comme autre exemple, le routage direct fournit le routage basé sur l’emplacement (LBR). LBR vous permet de limiter le contournement des péages dans certains emplacements géographiques où il n’est pas autorisé. 

Le tableau suivant met en évidence les principales différences de configuration. Les sections qui suivent le tableau fournissent des liens vers plus d’informations et de détails.

| Option | Description | gestion des nombres Téléphone | Routage des appels | Disponibilité des appels d’urgence |
| :------------| :-------| :-------| :-------| :-------| 
| Forfaits d’appel | -Microsoft agit comme opérateur RTC.<br>-Vous n’avez pas besoin d’acheter ou de gérer des SBC.| Obtenu par le biais de Microsoft.| -Géré par Microsoft. <br> -Administration configure les plans de numérotation utilisateur pour la traduction de numéros. | -Activé par Microsoft. <br> -Administration inscrit des adresses. <br> -Appels dynamiques pris en charge. |
| Operator Connect | -Carrier gère la connectivité RTC et les SBC. <br> -Vous n’avez pas besoin d’acheter ou de gérer des SBC. | -Obtenu par le biais du transporteur. <br> - Numéros associés aux adresses d’urgence gérées par le transporteur. | -Géré par le transporteur. <br>-Administration configure les plans de numérotation utilisateur pour la traduction de numéros. | -Activé par le transporteur. <br> -Administration inscrit des adresses. <br> -Appels dynamiques pris en charge. |
| Routage direct | - Nécessite un SBC certifié acheté auprès d’un fournisseur tiers.<br>-Connecter votre SBC à Système téléphonique.<br> -Utilisez votre opérateur RTC existant. | Obtenu par l’intermédiaire du transporteur. | - Nécessite une configuration supplémentaire par l’administrateur.<br>-Administration configure les plans de numérotation de jonction pour la traduction de numéros. <br>-LBR disponible pour restreindre le contournement des péages. | - Nécessite une configuration supplémentaire par l’administrateur. <br>-Adresses inscrites non prises en charge. <br>-Appels dynamiques pris en charge, mais nécessite une configuration supplémentaire. |

### <a name="phone-number-management"></a>gestion des nombres Téléphone

Microsoft dispose de deux types de numéros de téléphone disponibles : les numéros d’abonné (utilisateur), qui peuvent être affectés aux utilisateurs de votre organisation, et les numéros de service, disponibles en tant que numéros de service payants et gratuits. Les numéros de service ont une capacité d’appel simultanée supérieure à celle des numéros d’abonné et peuvent être affectés à des services tels que les Audioconférence, les standards automatiques ou les files d’attente d’appels.

Vous devez décider :

- Quels sont les emplacements d’utilisateur qui ont besoin de nouveaux numéros de téléphone de Microsoft ?
- De quel type de numéro de téléphone (abonné ou service) ai-je besoin ?
- Comment faire port des numéros de téléphone existants vers Teams ?

La façon dont vous acquérez et gérez des numéros de téléphone diffère en fonction de votre option de connectivité RTC.

- Pour plus d’informations sur la gestion des numéros de téléphone pour le forfait d’appels, consultez [Gérer les numéros de téléphone de votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Pour plus d’informations sur la gestion des numéros de téléphone avec Operator Connect, consultez [Configurer des numéros de téléphone avec Operator Connect](operator-connect-configure.md#set-up-phone-numbers).

- Pour plus d’informations sur la gestion des numéros de téléphone pour le routage direct, consultez [Configurer le numéro de téléphone et activer la voix d’entreprise](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice).

### <a name="call-routing-and-dial-plans"></a>Plans de routage et de numérotation des appels

La façon dont vous configurez le routage des appels varie en fonction de votre option de connectivité RTC.  

- Pour les forfaits d’appels, la plupart du routage des appels est géré par l’infrastructure du plan d’appel Microsoft. Vous configurez des plans de numérotation utilisateur à des fins de traduction de numéros pour l’autorisation d’appel et le routage des appels. Pour plus d’informations, consultez [Que sont les plans de numérotation ?](what-are-dial-plans.md)

- Pour Operator Connect, la plupart du routage des appels est géré par le transporteur.  Vous configurez des plans de numérotation utilisateur à des fins de traduction de numéros pour l’autorisation d’appel et le routage des appels. Pour plus d’informations, consultez [Que sont les plans de numérotation ?](what-are-dial-plans.md)

- Pour le routage direct, vous devez configurer le routage des appels en spécifiant les itinéraires vocaux et en attribuant des stratégies de routage vocal aux utilisateurs. Vous pouvez configurer des plans de numérotation pour la traduction de numéros au niveau du tronçon pour garantir l’interopérabilité avec les contrôleurs de frontière de session (SBC). Pour plus d’informations, consultez [Configurer le routage vocal pour le routage direct](direct-routing-voice-routing.md), [Gérer les stratégies de routage vocal](manage-voice-routing-policies.md) et [Traduire les numéros de téléphone](direct-routing-translate-numbers.md). 

### <a name="location-based-routing-for-direct-routing"></a>Location-Based routage pour le routage direct

Dans certains pays et régions, il est illégal de contourner le transporteur RTC pour réduire les coûts d’appels longue distance. Location-Based Routage (LBR) pour le routage direct vous permet de limiter le contournement des péages pour les utilisateurs Teams en fonction de leur emplacement géographique. Pour plus d’informations sur la planification et la configuration de LBR, consultez les articles suivants :

- [Planifier le routage géodépendant pour le routage direct](location-based-routing-plan.md)
- [Configurer les paramètres de réseau pour le routage géodépendant](location-based-routing-configure-network-settings.md)
- [Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)
- [Étude de cas Contoso : routage Location-Based](voice-case-study-location-based-routing.md)<br>
  Décrit comment une société multinationale fictive, Contoso, a implémenté Location-Based routage pour son organisation.

### <a name="emergency-calling"></a>Appel d’urgence

La façon dont vous configurez les appels d’urgence diffère en fonction de votre option de connectivité RTC.

- Pour le plan d’appel, chaque utilisateur est automatiquement activé pour les appels d’urgence. L’utilisateur doit disposer d’une adresse d’urgence inscrite associée à son numéro de téléphone affecté. Les appels d’urgence dynamiques (en fonction de l’emplacement du client Teams) sont pris en charge.  

- Pour Operator Connect, chaque utilisateur est automatiquement activé pour les appels d’urgence. L’utilisateur doit disposer d’une adresse d’urgence inscrite associée à l’engourdissement de son téléphone affecté, mais l’adresse ne peut être définie que par le partenaire du transporteur. Les appels d’urgence dynamiques (en fonction de l’emplacement du client Teams) sont pris en charge.

- Pour le routage direct, vous devez définir des stratégies d’appel d’urgence pour les utilisateurs à l’aide d’une Teams stratégie de routage des appels d’urgence (TeamsEmergencyCallRoutingPolicy). La stratégie définit les numéros d’urgence et leur destination de routage associée. Les emplacements d’urgence inscrits ne sont pas pris en charge pour les utilisateurs de routage direct. Pour les appels d’urgence dynamiques, une configuration supplémentaire est requise pour le routage des appels d’urgence et éventuellement pour la connectivité des partenaires.

Pour plus d’informations sur les concepts et la terminologie relatifs aux appels d’urgence, et sur la configuration des appels d’urgence et des appels d’urgence dynamiques, consultez les articles suivants :

- [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planifier et configurer un appel d’urgence dynamique](configure-dynamic-emergency-calling.md)
- [Gérer les stratégies d’appel d’urgence](manage-emergency-calling-policies.md)
- [Gérer les stratégies de routage des appels d’urgence pour le routage direct](manage-emergency-call-routing-policies.md)
- [Étude de cas Contoso : Appel d’urgence](voice-case-study-emergency-calling.md)<br>
  Décrit comment une société multinationale fictive, Contoso, a implémenté des appels d’urgence pour son organisation.

### <a name="network-topology-for-voice-features"></a>Topologie réseau pour les fonctionnalités vocales

Si vous déployez des appels d’urgence dynamiques ou Location-Based routage pour le routage direct, vous devez configurer les paramètres réseau de ces fonctionnalités dans Microsoft Teams. Pour savoir comment configurer les paramètres réseau pour les régions réseau, les sites réseau, les sous-réseaux réseau et les adresses IP approuvées, consultez les articles suivants :

- [Paramètres réseau pour les fonctionnalités de voix cloud dans Microsoft Teams - Concepts et terminologie](cloud-voice-network-settings.md)
- [Gérer la topologie de votre réseau pour les fonctionnalités de voix cloud dans Microsoft Teams](manage-your-network-topology.md)
