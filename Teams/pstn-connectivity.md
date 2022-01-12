---
title: Options de connectivité PSTN
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
description: En savoir plus sur les options Teams d’appel (connectivité PSTN) et les décisions que vous prendrez pour votre organisation.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 994115cdf1dda3b5f938b6816623ead2a4196fdb
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766847"
---
# <a name="pstn-connectivity-options"></a>Options de connectivité PSTN

Microsoft fournit des fonctionnalités complètes de Exchange de branche privée (PBX) pour votre organisation via Teams Téléphone. Toutefois, pour permettre aux utilisateurs de passer des appels en dehors de votre organisation, vous devez vous Teams Téléphone au réseau téléphonique public commuté (PSTN).

Cet article se concentre sur les options de connectivité PSTN. Pour plus d’informations sur les solutions vocales Microsoft, notamment sur les fonctionnalités Teams Téléphone, voir Planifier votre solution vocale Teams [messagerie vocale.](cloud-voice-landing-page.md)

Pour vous Teams Téléphone au réseau PSTN, vous avez le choix entre les options suivantes :

- [**Forfait d’appels.**](#teams-phone-with-calling-plan) Une solution all-in-the-cloud avec Microsoft comme opérateur PSTN.

- [**L’Connecter**](#teams-phone-with-operator-connect),qui est actuellement disponible uniquement en **prévisualisation publique.**  Avec les Connecter opérateurs, si votre opérateur existant participe au programme Microsoft Operator Connecter (Programme d’opérateur Microsoft), il peut gérer les contrôleurs de session et d’appel RTC. 

- [**Routage direct,**](#teams-phone-with-direct-routing)qui vous permet d’utiliser votre propre opérateur PSTN en connectant votre ou vos contrôleurs de session (SBC) à Teams Téléphone.


Vous pouvez également choisir une combinaison d’options qui vous permet de concevoir une solution pour un environnement complexe ou de gérer une migration en plusieurs étapes.

N’ignorez pas que les options que vous choisissez affectent la manière dont certaines Teams Téléphone fonctionnalités sont configurées. Pour plus d’informations, voir [les considérations concernant la configuration](#configuration-considerations) plus loin dans cet article.


## <a name="teams-phone-with-calling-plan"></a>Teams Téléphone’aide du forfait d’appels 

Teams Téléphone’offre d’appels est la solution vocale tout-en-cloud de Microsoft pour les Teams cloud. Il s’agit de l’option la plus simple qui Teams Téléphone au réseau PSTN. Avec cette option, Microsoft agit en tant qu’opérateur PSTN, comme indiqué dans le diagramme suivant :

![Le diagramme 1 montre les Système téléphonique’aide d’un plan d’appels.](media/voice-solutions-simple.png)

Si vous répondez oui aux questions suivantes, l Teams Téléphone’aide du plan d’appels est la solution adaptée à vos questions :

- Forfait d’appels disponible dans votre région.
- Vous n’avez pas besoin de conserver votre opérateur PSTN actuel.
- Vous voulez utiliser l’accès géré par Microsoft au réseau PSTN.

Avec cette option : 

- Vous pouvez Teams Téléphone avec des plans d’appels nationaux ou internationaux qui permettent d’appeler vers des téléphones dans le monde entier (selon le niveau de service sous licence).

- Le déploiement ou la maintenance d’un déploiement local n’est pas nécessaire, car le plan d’appel &mdash; fonctionne Microsoft 365.

- Remarque : si nécessaire, vous pouvez choisir de connecter un contrôleur de session border (SBC) pris en charge via un routage direct pour l’interopérabilité avec des PBX tiers, des appareils analogiques et d’autres équipements téléphoniques tiers pris en charge par le SBC.

Cette option nécessite une connexion ininterrompue à Microsoft 365.

Pour plus d’informations sur le forfait d’appels, consultez les articles suivants :

- [Quelle forfait d’appels vous convient le mieux ?](calling-plan-landing-page.md)
- [Comment acheter un forfait d’appels](calling-plans-for-office-365.md)
- [Disponibilité des forfaits d’appels par pays et par région](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Configurer le forfait d’appels](set-up-calling-plans.md)


## <a name="teams-phone-with-operator-connect"></a>Teams Téléphone’opérateur Connecter

Avec l’Connecter d’opérateur actuellement en prévisualisation publique, si votre opérateur existant participe au programme Connecter de l’opérateur Microsoft, il peut gérer le service pour que les appels RSTN Teams. Votre opérateur gère les services d’appel PSTN et les contrôleurs de session en bordure, ce qui vous permet d’économiser sur l’achat et la gestion du matériel.

L’Connecter peut être la solution appropriée pour votre organisation si :

- Le plan d’appels Microsoft n’est pas disponible dans votre emplacement géographique.
- Votre opérateur préféré est un participant au programme d’Connecter Microsoft.
- Vous souhaitez rechercher un nouvel opérateur pour activer les appels Teams.

Pour plus d’informations sur les avantages et les conditions requises de la Connecter opérateur, et pour obtenir la liste des opérateurs participant à ce programme, consultez la liste des opérateurs [Connecter.](operator-connect-plan.md) Pour plus d’informations sur la configuration de l’Connecter opérateur, voir [Configurer l’Connecter.](operator-connect-configure.md)


## <a name="teams-phone-with-direct-routing"></a>Teams Téléphone le routage direct

Cette option connecte Teams Téléphone réseau téléphonique à l’aide du routage direct, comme illustré dans le diagramme suivant : 

![Le diagramme 5 illustre Système téléphonique routage direct.](media/voice-solution-with-direct-routing.png)

Si vous répondez oui aux questions suivantes, l’Teams Téléphone le routage direct est la solution adaptée à vos questions :

- Vous voulez utiliser Teams avec Teams Téléphone.
- Vous devez conserver votre opérateur PSTN actuel.
- Vous voulez mélanger le routage, certains appels passant par le plan d’appels, d’autres par l’intermédiaire de votre opérateur.
- Vous devez interopérateur avec des PBX tiers et/ou des équipements tels que des pages de surcharge, des dispositifs analogiques, etc.

Avec cette option :

- Vous connectez votre propre contrôleur de session border controller (SBC) pris en charge à Teams Téléphone sans resserr de logiciel local supplémentaire.

- Vous pouvez utiliser pratiquement n’importe quel opérateur téléphonique avec Teams Téléphone.

- Vous pouvez choisir de configurer et de gérer cette option, ou elle peut être configurée et gérée par votre opérateur ou partenaire (demandez-lui si votre opérateur ou partenaire propose cette option).

- Vous pouvez configurer l’interopérabilité entre vos équipements téléphoniques tels qu’un PBX tiers et des appareils &mdash; &mdash; analogiques, et Teams Téléphone.

Cette option nécessite les options suivantes :

- Connexion ininterrompue à Microsoft 365.

- Déploiement et maintenance d’un SBC pris en charge.

- Contrat avec un opérateur tiers.
  (Sauf dans le cadre du déploiement en tant qu’option de connexion au PBX tiers, aux périphériques analogiques ou à d’autres équipements téléphoniques pour les utilisateurs qui utilisent le Teams Téléphone avec le plan d’appel.)

Pour plus d’informations sur le routage direct, voir les articles suivants :

- [Planifier le routage direct](direct-routing-plan.md)
- [Configurer le routage direct](direct-routing-configure.md)
- [Gérer les stratégies de routage vocal pour les utiliser avec le routage direct](manage-voice-routing-policies.md)
- [Planifier le routage géodépendant pour le routage direct](location-based-routing-plan.md)
- [Liste des contrôleurs de frontière de session certifiés pour le routage direct](direct-routing-border-controllers.md)



## <a name="configuration-considerations"></a>Considérations en cas de configuration

La plupart Teams Téléphone fonctionnalités sont identiques quelle que soit l’option de connectivité PSTN que vous choisissez. Par exemple, les paramètres Sans réponse et transfert d’appel, le transfert d’appel, la musique personnalisée mise en attente, le parcage d’appel, la ligne partagée et les applications vocales sont tous disponibles. Pour obtenir la liste complète des Teams Téléphone fonctionnalités, consultez les fonctionnalités de la liste des [Teams Téléphone.](here-s-what-you-get-with-phone-system.md)

Il existe toutefois certaines différences de fonctionnalités qui affectent la façon dont vous configurez Teams Téléphone fonctionnalités. Par exemple, le routage direct nécessite des étapes supplémentaires pour configurer le routage des appels. Autre exemple : le routage direct fournit un routage basé sur l’emplacement (LBR) pour vous permettre de restreindre la dérivation contre les frais dans certains emplacements géographiques où il n’est pas autorisé. 

Le tableau suivant met en évidence les différences de configuration principale. Les sections qui suivent le tableau fournissent des liens vers des informations et des détails supplémentaires.

| Option | Description | Téléphone gestion des nombres | Routage des appels | Disponibilité des appels d’urgence |
| :------------| :-------| :-------| :-------| :-------| 
| Forfaits d’appel | -Microsoft agit en tant qu’opérateur PSTN.<br>-Vous n’avez pas besoin d’acheter ou de gérer des SBCS.| Obtenu auprès de Microsoft.| -Géré par Microsoft. <br> -L’administrateur configure les plans de numérotation utilisateur pour la traduction des numéros. | -Activé par Microsoft. <br> -L’administrateur enregistre les adresses. <br> -Appels dynamiques pris en charge. |
| Connecter | -Carrier gère la connectivité PSTN et les SBCs. <br> -Vous n’avez pas besoin d’acheter ou de gérer des SBCS. | -Obtenu via un opérateur. <br> - Numéros associés à des adresses de secours gérées par un opérateur.  | -Géré par un opérateur. <br>-L’administrateur configure les plans de numérotation utilisateur pour la traduction des numéros. | -Activé par un opérateur. <br> -L’administrateur enregistre les adresses. <br> -Appels dynamiques pris en charge. |
| Routage direct | - Nécessite l’achat de SBC certifié auprès d’un fournisseur tiers.<br>-Connecter votre SBC à Teams Téléphone.<br> -Utilisez votre opérateur PSTN existant. | Obtenu auprès d’un opérateur. | - Nécessite une configuration supplémentaire par l’administrateur.<br>-L’administrateur configure les plans de numérotation de ligne pour la traduction des numéros. <br>-LBR est disponible pour restreindre la dérivation toll. | - Nécessite une configuration supplémentaire par l’administrateur. <br>Adresses enregistrées non prise en charge. <br>-Appels dynamiques pris en charge, mais nécessite une configuration supplémentaire. |
|||||


### <a name="phone-number-management"></a>Téléphone gestion des nombres

Microsoft propose deux types de numéros de téléphone : les numéros d’abonnés (utilisateurs) qui peuvent être affectés à des utilisateurs de votre organisation et les numéros de service disponibles sous forme de numéros de service gratuits et gratuits. Les numéros de service ont une capacité d’appels simultanés supérieure à celle des numéros d’abonné et peuvent être affectés à des services tels que l’Audioconférence, les attendants automatiques ou les files d’attente d’appels.

Vous devrez décider des choix ci-après :

- Quels emplacements utilisateur ont besoin de nouveaux numéros de téléphone de Microsoft ?
- De quel type de numéro de téléphone (abonné ou service) ai-je besoin ?
- Comment faire pour porter des numéros de téléphone existants vers Teams ?

La façon dont vous acquérir et gérer les numéros de téléphone diffère en fonction de l’option de connectivité PSTN.

- Pour plus d’informations sur la gestion des numéros de téléphone pour le plan d’appels, voir [Gérer les numéros de téléphone pour votre organisation.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- Pour plus d’informations sur la gestion des numéros de téléphone avec la Connecter opérateur, voir Configurer des numéros de téléphone avec l’opérateur [Connecter.](operator-connect-configure.md#set-up-phone-numbers)

- Pour plus d’informations sur la gestion des numéros de téléphone pour le routage direct, voir Configurer le numéro de téléphone et activer la messagerie vocale et [vocale d’entreprise.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)


### <a name="call-routing-and-dial-plans"></a>Routage des appels et plans de numérotation

La manière dont vous configurez le routage des appels diffère en fonction de l’option de connectivité RSTN.  

- Pour les forfaits d’appels, la plupart du routage des appels est géré par l’infrastructure du plan d’appels Microsoft. Vous configurez les plans de numérotation utilisateur en vue de la traduction des numéros à des fins d’autorisation et de routage des appels. Pour plus d’informations, voir [Les plans de numérotation.](what-are-dial-plans.md)

- Pour l’Connecter, la plupart du routage des appels est géré par l’opérateur.  Vous configurez les plans de numérotation utilisateur en vue de la traduction des numéros à des fins d’autorisation et de routage des appels. Pour plus d’informations, voir [Les plans de numérotation.](what-are-dial-plans.md)

- Pour le routage direct, vous devez configurer le routage des appels en spécifiant les itinéraires vocaux et en attribuant des stratégies de routage vocal aux utilisateurs. Vous pouvez configurer des plans de numérotation pour la traduction des numéros sur le niveau de ligne afin de garantir l’interopérabilité avec les contrôleurs de session en bordure (SBCs). Pour plus d’informations, voir Configurer le routage vocal pour le [routage](direct-routing-voice-routing.md)direct, Gérer les stratégies de [routage](manage-voice-routing-policies.md) vocal et [Traduire les numéros de téléphone.](direct-routing-translate-numbers.md) 


### <a name="location-based-routing-for-direct-routing"></a>Location-Based routage pour le routage direct

Dans certains pays et certaines régions, il n’est pas illégal de contourner l’opérateur PSTN afin de diminuer les coûts des appels longue distance. Location-Based (LBR) pour le routage direct vous permet de restreindre la dérivation pour les Teams en fonction de leur emplacement géographique. Pour plus d’informations sur la façon de planifier et de configurer LBR, voir les articles suivants :

- [Planifier le routage géodépendant pour le routage direct](location-based-routing-plan.md)
- [Configurer les paramètres de réseau pour le routage géodépendant](location-based-routing-configure-network-settings.md)
- [Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)
- [Étude de cas Contoso : Location-Based routage](voice-case-study-location-based-routing.md)<br>
  Décrit la façon dont Contoso, une entreprise multinationale fictive, a implémenté un Location-Based routage pour leur organisation.


### <a name="emergency-calling"></a>Appel d’urgence

La configuration des appels d’urgence diffère en fonction de l’option de connectivité PSTN.

- Pour le plan d’appels, chaque utilisateur est automatiquement activé pour les appels d’urgence et une adresse d’urgence enregistrée doit être associée à son numéro de téléphone affecté. Les appels d’urgence dynamiques (en fonction de l’emplacement Teams client) sont pris en charge.  

- Pour l’Connecter opérateur, chaque utilisateur est automatiquement activé pour les appels d’urgence et une adresse d’urgence enregistrée doit être associée à son numéro de téléphone affecté, mais ne peut être définie que par le partenaire de l’opérateur. Les appels d’urgence dynamiques (en fonction de l’emplacement Teams client) sont pris en charge.

- Pour le routage direct, vous devez définir des stratégies d’appel d’urgence pour les utilisateurs à l’aide d’une stratégie de routage d’appel d’urgence Teams (TeamsEmergencyCallRoutingPolicy) pour définir les numéros d’urgence et leur destination de routage associée. Les emplacements d’urgence enregistrés ne sont pas pris en charge pour les utilisateurs du routage direct. Pour les appels d’urgence dynamiques, une configuration supplémentaire est requise pour router les appels d’urgence et éventuellement pour la connectivité partenaire.

Pour plus d’informations sur les concepts d’appel d’urgence et la terminologie, ainsi que sur la configuration des appels d’urgence et des appels d’urgence dynamiques, consultez les articles suivants :

- [Gestion des appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planifier et configurer un appel d’urgence dynamique](configure-dynamic-emergency-calling.md)
- [Gérer les stratégies d’appel d’urgence](manage-emergency-calling-policies.md)
- [Gérer les stratégies de routage d’appel d’urgence pour le routage direct](manage-emergency-call-routing-policies.md)
- [Étude de cas Contoso : appels d’urgence](voice-case-study-emergency-calling.md)<br>
  Décrit comment une entreprise multinationale fictive, Contoso, a implémenté des appels d’urgence pour leur organisation.


### <a name="network-topology-for-voice-features"></a>Topologie de réseau pour les fonctionnalités vocales

Si vous déployez des appels d’urgence dynamiques ou un Location-Based de routage direct, vous devez configurer les paramètres réseau pour les utiliser avec ces fonctionnalités dans Microsoft Teams. Pour découvrir comment configurer les paramètres réseau pour les régions réseau, les sites réseau, les sous-réseaux et les adresses IP de confiance, consultez les articles suivants :

- [Paramètres réseau pour les fonctionnalités vocales cloud dans Microsoft Teams - Concepts et terminologie](cloud-voice-network-settings.md)
- [Gérer votre topologie de réseau pour les fonctionnalités vocales cloud dans Microsoft Teams](manage-your-network-topology.md)



