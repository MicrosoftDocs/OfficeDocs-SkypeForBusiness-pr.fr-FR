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
description: En savoir plus sur Teams options d’appel (connectivité PSTN) et les décisions que vous prendrez pour votre organisation.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c53b553a83349c3d4fd20a926f29b4c727175c73aba5ba0f5e352cf19a53f9e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54285939"
---
# <a name="pstn-connectivity-options"></a>Options de connectivité RTC

Microsoft fournit des fonctionnalités PBX (Private Branch Exchange) complètes à votre organisation via Système téléphonique. Toutefois, pour permettre aux utilisateurs de passer des appels à l’extérieur de votre organisation, vous devez vous Système téléphonique au réseau téléphonique commuté (PSTN).

Cet article se concentre sur les options de connectivité PSTN. Pour plus d’informations sur les solutions vocales Microsoft, en inséant des détails sur les fonctionnalités Système téléphonique, voir [Planifier Teams solution vocale.](cloud-voice-landing-page.md)

Pour vous connecter Système téléphonique au réseau PSTN, vous pouvez choisir parmi les options suivantes :

- [**Forfait d’appels**](#phone-system-with-calling-plan). Une solution tout-dans-le-cloud avec Microsoft comme opérateur PSTN.

- [**Opérateur Connecter**](#phone-system-with-operator-connect), actuellement disponible uniquement en **prévisualisation publique.**  Avec l’opérateur Connecter, si votre opérateur existant participe au programme Microsoft Operator Connecter, il peut gérer les appels RTC et les contrôleurs de frontière de session (SCS). 

- [**Routage direct,**](#phone-system-with-direct-routing)qui vous permet d’utiliser votre propre opérateur PSTN en connectant vos contrôleurs de frontière de session (SBC) à Système téléphonique.


Vous pouvez également choisir une combinaison d’options, ce qui vous permet de concevoir une solution pour un environnement complexe ou de gérer une migration en plusieurs étapes.

N’ignorez pas que l’option ou les options que vous choisissez affectent la façon dont certaines Système téléphonique sont configurées. Pour plus d’informations, voir [considérations sur la configuration](#configuration-considerations) plus loin dans cet article.


## <a name="phone-system-with-calling-plan"></a>Système téléphonique avec forfaits d’appels 

Système téléphonique forfait d’appels est la solution vocale tout-en-cloud de Microsoft pour les Teams utilisateurs. Il s’agit de l’option la plus simple qui connecte Système téléphonique au réseau PSTN. Avec cette option, Microsoft agit comme votre opérateur PSTN, comme illustré dans le diagramme suivant :

![Le diagramme 1 montre les Système téléphonique forfait d’appels](media/voice-solutions-simple.png)

Si vous répondez oui aux questions suivantes, Système téléphonique forfait d’appels est la solution appropriée pour vous :

- Le forfait d’appels est disponible dans votre région.
- Vous n’avez pas besoin de conserver votre opérateur PSTN actuel.
- Vous souhaitez utiliser l’accès géré par Microsoft au réseau PSTN.

Avec cette option : 

- Vous avez accès au Système téléphonique Microsoft avec des Forfaits d’appels nationaux ou internationaux qui permettent d’appeler vers des téléphones dans le monde entier (selon le niveau de service faisant l’objet d’une licence).

- Vous n’avez pas besoin de déploiement ou de maintenance d’un déploiement local, car le plan d’appel fonctionne &mdash; hors Microsoft 365.

- Remarque : si nécessaire, vous pouvez choisir de connecter un contrôleur SBC (Session Border Controller) pris en charge via le routage direct pour l’interopérabilité avec des PBX tiers, des périphériques analogiques et d’autres équipements téléphoniques tiers pris en charge par le SBC.

Cette option nécessite une connexion ininterrompue à Microsoft 365.

Pour plus d’informations sur forfait d’appels, consultez les articles suivants :

- [Quelle forfait d’appels vous convient le mieux ?](calling-plan-landing-page.md)
- [Comment acheter un forfait d’appels](calling-plans-for-office-365.md)
- [Disponibilité des forfaits d’appels dans les pays et régions](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Configurer le forfait d’appels](set-up-calling-plans.md)


## <a name="phone-system-with-operator-connect"></a>Système téléphonique avec opérateur Connecter

Avec l’opérateur Connecter, actuellement en prévisualisation publique, si votre opérateur existant participe au programme Connecter de l’opérateur Microsoft, il peut gérer le service d’appels PSTN vers Teams. Votre opérateur gère les services d’appel PSTN et les contrôleurs SCS (Session Border Controller), ce qui vous permet d’économiser sur l’achat et la gestion du matériel.

L Connecter opérateur peut être la solution appropriée pour votre organisation si :

- Le forfait d’appels Microsoft n’est pas disponible dans votre emplacement géographique.
- Votre opérateur préféré est un participant au programme d’Connecter Microsoft.
- Vous souhaitez trouver un nouvel opérateur pour activer les appels dans Teams.

Pour plus d’informations sur les avantages et les exigences de l’opérateur Connecter et pour obtenir la liste des opérateurs participant à ce programme, consultez l’opérateur [de plan Connecter](operator-connect-plan.md). Pour plus d’informations sur la configuration de l’opérateur Connecter, voir [Configure Operator Connecter](operator-connect-configure.md).


## <a name="phone-system-with-direct-routing"></a>Système téléphonique avec routage direct

Cette option connecte Système téléphonique réseau téléphonique à l’aide du routage direct, comme illustré dans le diagramme suivant : 

![Le diagramme 5 montre Système téléphonique avec le routage direct](media/voice-solution-with-direct-routing.png)

Si vous répondez oui aux questions suivantes, la solution Système téléphonique avec routage direct est adaptée :

- Vous voulez utiliser Teams avec le système téléphonique.
- Vous devez conserver votre opérateur PSTN actuel.
- Vous voulez mélanger les routages, certains appels passant par le forfait d'appels, d’autres via votre opérateur.
- Vous devez interopérer avec des PBX tiers et/ou des équipements tels que les pageurs de surcharge, les périphériques analogiques, etc.

Avec cette option :

- Vous connectez votre propre contrôleur SBC (Session Border Controller) à Système téléphonique sans avoir besoin de logiciels locaux supplémentaires.

- Vous pouvez utiliser pratiquement n’importe quel opérateur téléphonique avec Système téléphonique.

- Vous pouvez choisir de configurer et de gérer cette option, ou elle peut être configurée et gérée par votre opérateur ou partenaire (demandez-lui si votre opérateur ou partenaire propose cette option).

- Vous pouvez configurer l’interopérabilité entre vos équipements téléphoniques tels qu’un PBX tiers et des périphériques &mdash; analogiques &mdash; et des Système téléphonique.

Cette possibilité nécessite ce qui suit :

- Une connexion ininterrompue à Microsoft 365.

- Déploiement et maintenance d’un SBC pris en charge.

- Contrat avec un opérateur tiers. (Sauf dans le cadre d’un déploiement en vue de fournir une connexion à un système PBX tiers, à des périphériques similaires ou à d’autres équipements de téléphonie pour les utilisateurs qui utilisent le système téléphonique avec le forfait d’appel.)

Pour plus d’informations sur le routage direct, consultez les articles suivants :

- [Planifier le routage direct](direct-routing-plan.md)
- [Configurer le routage direct](direct-routing-configure.md)
- [Gérer les stratégies de routage des voix à utiliser avec le routage direct](manage-voice-routing-policies.md)
- [Planifier le routage géodépendant pour le routage direct](location-based-routing-plan.md)
- [Liste des Contrôleurs de frontière de session (SBC) certifiés pour le routage direct](direct-routing-border-controllers.md)



## <a name="configuration-considerations"></a>Considérations sur la configuration

La Système téléphonique fonctionnalités sont les mêmes quelle que soit l’option de connectivité PSTN que vous choisissez. Par exemple, les paramètres de transfert, de transfert d’appel, d’attente musicale personnalisée, de parcage d’appel, de ligne partagée et d’applications vocales sont tous disponibles. Pour obtenir la liste complète des fonctionnalités Système téléphonique, voir Voici ce que vous obtenez [avec Système téléphonique](here-s-what-you-get-with-phone-system.md).

Toutefois, certaines différences de fonctionnalités affectent la configuration de Système téléphonique fonctionnalités. Par exemple, le routage direct nécessite des étapes supplémentaires pour configurer le routage des appels. Autre exemple, le routage direct fournit le routage basé sur l’emplacement (LBR) afin que vous pouvez restreindre le contournement de frais à certains emplacements géographiques où il n’est pas autorisé. 

Le tableau suivant met en évidence les principales différences de configuration. Les sections qui suivent le tableau fournissent des liens vers plus d’informations et de détails.

| Option | Description | Téléphone gestion des nombres | Routage des appels | Disponibilité des appels d’urgence |
| :------------| :-------| :-------| :-------| :-------| 
| Forfaits d’appel | -Microsoft agit en tant qu’opérateur PSTN.<br>-Vous n’avez pas besoin d’acheter ou de gérer des SBCs.| Obtenu par le biais de Microsoft.| -Géré par Microsoft. <br> -Admin configure les plans de numérotation utilisateur pour la traduction de numéros. | -Activé par Microsoft. <br> -Admin inscrit les adresses. <br> -Appel dynamique pris en charge. |
| Operator Connect | -Carrier gère la connectivité PSTN et les SCS. <br> -Vous n’avez pas besoin d’acheter ou de gérer des SBCs. | -Obtenu par le biais de l’opérateur. <br> - Numéros associés aux adresses d’urgence gérées par l’opérateur.  | -Géré par l’opérateur. <br>-Admin configure les plans de numérotation utilisateur pour la traduction de numéros. | -Activé par l’opérateur. <br> -Admin inscrit les adresses. <br> -Appel dynamique pris en charge. |
| Routage direct | -Nécessite un SBC certifié acheté auprès d’un fournisseur tiers.<br>-Connecter votre SBC pour Système téléphonique.<br> -Utiliser votre opérateur PSTN existant. | Obtenu par le biais de l’opérateur. | -Nécessite une configuration supplémentaire par l’administrateur.<br>-Admin configure les plans de numérotation de la ligne pour la traduction de numéros. <br>-LBR disponible pour limiter le contournement de frais. | -Nécessite une configuration supplémentaire par l’administrateur. <br>-Les adresses inscrites ne sont pas pris en charge. <br>-Appel dynamique pris en charge, mais nécessite une configuration supplémentaire. |
|||||


### <a name="phone-number-management"></a>Téléphone gestion des nombres

Microsoft dispose de deux types de numéros de téléphone disponibles : les numéros d’abonné (utilisateur), qui peuvent être affectés à des utilisateurs de votre organisation, et les numéros de service disponibles sous forme de numéros de service gratuits et gratuits. Les numéros de service ont une capacité d’appel simultanée plus élevée que les numéros d’abonné et peuvent être affectés à des services tels que l’audioconférence, les attendants automatiques ou les files d’attente d’appels.

Vous devrez décider :

- Quels emplacements d’utilisateurs ont besoin de nouveaux numéros de téléphone de Microsoft ?
- De quel type de numéro de téléphone (abonné ou service) ai-je besoin ?
- Comment porte-t-on des numéros de téléphone existants vers Teams ?

L’acquisition et la gestion des numéros de téléphone varient en fonction de votre option de connectivité PSTN.

- Pour plus d’informations sur la gestion des numéros de téléphone pour le forfait d’appels, voir [Gérer les numéros de téléphone de votre organisation.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- Pour plus d’informations sur la gestion des numéros de téléphone avec Connecter opérateur, voir Configurer des numéros de téléphone [avec l’opérateur Connecter](operator-connect-configure.md#set-up-phone-numbers).

- Pour plus d’informations sur la gestion des numéros de téléphone pour le routage direct, voir Configurer le numéro de téléphone et activer la messagerie vocale et vocale [d’entreprise.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)


### <a name="call-routing-and-dial-plans"></a>Routage des appels et plans de numérotation

La façon dont vous configurez le routage des appels diffère en fonction de votre option de connectivité PSTN.  

- Pour les forfaits d’appels, la plupart du routage des appels est géré par l’infrastructure du plan d’appel Microsoft. Vous configurez des plans de numérotation utilisateur à des fins de traduction de numéros pour l’autorisation d’appel et le routage des appels. Pour plus d’informations, [voir Que sont les plans de numérotation ?](what-are-dial-plans.md)

- Pour les Connecter, la majeure partie du routage des appels est gérée par l’opérateur.  Vous configurez des plans de numérotation utilisateur à des fins de traduction de numéros pour l’autorisation d’appel et le routage des appels. Pour plus d’informations, [voir Que sont les plans de numérotation ?](what-are-dial-plans.md)

- Pour le routage direct, vous devez configurer le routage des appels en spécifiant les itinéraires de voix et en attribuant des stratégies de routage des appels aux utilisateurs. Vous pouvez configurer des plans de numérotation pour la traduction de numéros au niveau de la ligne pour garantir l’interopérabilité avec les contrôleurs de frontière de session (SCS). Pour plus d’informations, voir [Configure voice routing for Direct Routing](direct-routing-voice-routing.md), [Manage voice routing policies](manage-voice-routing-policies.md) and Translate phone [numbers](direct-routing-translate-numbers.md). 


### <a name="location-based-routing-for-direct-routing"></a>Routage basé sur l’emplacement pour le routage direct

Dans certains pays et régions, il est interdit de contourner l’opérateur PSTN pour réduire les coûts d’appels longue distance. Location-Based routage LBR (Routage direct) vous permet de restreindre le contournement de frais pour les utilisateurs Teams en fonction de leur emplacement géographique. Pour plus d’informations sur la façon de planifier et de configurer le LBR, consultez les articles suivants :

- [Planifier le routage géodépendant pour le routage direct](location-based-routing-plan.md)
- [Configurer les paramètres de réseau pour le routage géodépendant](location-based-routing-configure-network-settings.md)
- [Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)
- [Étude de cas Contoso : Location-Based routage](voice-case-study-location-based-routing.md)<br>
  Décrit comment une entreprise multinationale fictive, Contoso, a implémenté Location-Based routage pour son organisation.


### <a name="emergency-calling"></a>Appel d’urgence

La configuration des appels d’urgence diffère en fonction de votre option de connectivité PSTN.

- Pour le forfait d’appels, chaque utilisateur est automatiquement activé pour les appels d’urgence et doit avoir une adresse de secours inscrite associée à son numéro de téléphone affecté. Les appels d’urgence dynamiques (en fonction de l’emplacement Teams client) sont pris en charge.  

- Pour l’opérateur Connecter, chaque utilisateur est automatiquement activé pour les appels d’urgence et doit avoir une adresse de secours inscrite associée à son numéro de téléphone affecté, mais ne peut être définie que par le partenaire opérateur. Les appels d’urgence dynamiques (en fonction de l’emplacement Teams client) sont pris en charge.

- Pour le routage direct, vous devez définir des stratégies d’appel d’urgence pour les utilisateurs à l’aide d’une stratégie de routage des appels d’urgence Teams (TeamsEmergencyCallRoutingPolicy) pour définir les numéros d’urgence et leur destination de routage associée. Les emplacements d’urgence enregistrés ne sont pas pris en charge pour les utilisateurs du routage direct. Pour les appels d’urgence dynamiques, une configuration supplémentaire est requise pour le routage des appels d’urgence et éventuellement pour la connectivité des partenaires.

Pour plus d’informations sur les concepts et la terminologie des appels d’urgence, ainsi que sur la configuration des appels d’urgence et des appels d’urgence dynamiques, consultez les articles suivants :

- [Gérer les appels d'urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planifier et configurer un appel d’urgence dynamique](configure-dynamic-emergency-calling.md)
- [Gérer les stratégies d'appel d'urgence](manage-emergency-calling-policies.md)
- [Gérer les stratégies de routage d’appel d’urgence pour du routage direct](manage-emergency-call-routing-policies.md)
- [Étude de cas Contoso : appels d’urgence](voice-case-study-emergency-calling.md)<br>
  Décrit comment une entreprise multinationale fictive, Contoso, a implémenté les appels d’urgence pour son organisation.


### <a name="network-topology-for-voice-features"></a>Topologie réseau pour les fonctionnalités vocales

Si vous déployez un appel d’urgence dynamique ou un routage Location-Based pour le routage direct, vous devez configurer les paramètres réseau à utiliser avec ces fonctionnalités dans Microsoft Teams. Pour savoir comment configurer les paramètres réseau pour les régions réseau, les sites réseau, les sous-réseaux et les adresses IP de confiance, consultez les articles suivants :

- [Paramètres réseau pour les fonctionnalités vocales cloud dans Microsoft Teams : concepts et terminologie](cloud-voice-network-settings.md)
- [Gérez la topologie de votre réseau pour les fonctions de voix en cloud dans Microsoft Teams.](manage-your-network-topology.md)



