---
title: Planifier votre solution vocale dans Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/29/2020
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
description: En savoir plus sur les fonctionnalités voix cloud de Microsoft Teams et les décisions de déploiement que vous allez prendre pour votre organisation.
appliesto:
- Microsoft Teams
ms.openlocfilehash: fcd7ebfd4542c38bd56900c1e414dadec09bf246
ms.sourcegitcommit: 54140f6f8f2279a0eaf2e9c79699d6cff306791c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50408190"
---
# <a name="plan-your-teams-voice-solution"></a>Planifier votre solution vocale Teams 

Cet article vous aide à déterminer la solution Microsoft Voice adaptée à votre organisation. Une fois que vous avez décidé, l’article fournit une feuille de route vers le contenu qui vous permettra d’implémenter la solution que vous avez choisie.

> [!NOTE]
> Pour obtenir des instructions sur la planification d’une solution vocale Teams dans le cadre de votre plan global de mise à niveau vers Teams à partir de Skype Entreprise Server, consultez les [considérations PSTN](upgrade-to-teams-on-prem-pstn-considerations.md)pour la mise à niveau de Skype Entreprise en local vers Teams.

Vous souhaitez peut-être un système téléphonique plus simple &mdash; avec le plan d’appels. Il s’agit de la solution complète dans le cloud de Microsoft qui fournit la fonctionnalité PBX (Private Branch Exchange) et des appels vers le réseau téléphonique commuté (PSTN), comme illustré dans le diagramme suivant. Avec cette solution, Microsoft est votre opérateur PSTN.

![Diagramme 1 montre le système téléphonique avec le plan d’appels](media/voice-solutions-simple.png)

Si vous répondez oui aux questions suivantes, alors Phone System avec Forfait d’appels est la solution adaptée à vos questions :

- Le forfait d’appels est disponible dans votre région.
- Vous n’avez pas besoin de conserver votre opérateur PSTN actuel.
- Vous voulez utiliser l’accès géré par Microsoft au réseau PSTN.

Toutefois, votre situation peut être plus complexe. Par exemple, vous pouvez avoir des bureaux dans des emplacements où le plan d’appels n’est pas disponible. Vous pouvez également avoir besoin d’une solution combinée qui prend en charge un déploiement complexe et multi-national avec des exigences différentes pour différents emplacements géographiques. Microsoft prend en charge une combinaison de solutions : 

- Système téléphonique avec forfait d’appels
- Système téléphonique avec votre propre opérateur PSTN avec un routage direct
- Solution combinée qui utilise à la fois phone system avec le plan d’appels et le système téléphonique avec routage direct

## <a name="what-do-you-need-to-read"></a>Que devez-vous lire ?

**Obligatoire pour tous.** Certaines des sections de cet article concernent toutes les organisations. Par exemple, tout le monde doit en savoir plus sur le système téléphonique et comprendre les options de connexion au réseau téléphonique public commuté (PSTN). 


| Obligatoire pour tous | Description |
| :------------|:-------|
| [**Système téléphonique**](#phone-system) | Technologie microsoft permettant d’activer le contrôle des appels et les fonctionnalités PBX (Private Branch Exchange) dans le cloud Microsoft 365 avec Microsoft Teams. |
| [**Options de connectivité de réseau téléphonique commuté (PSTN)**](#public-switched-telephone-network-connectivity-options) | Choix entre l’utilisation de Microsoft comme opérateur de téléphonie ou la connexion de votre propre opérateur téléphonique à Microsoft Teams à l’aide du routage direct. Combinées avec le système téléphonique, les options de connectivité PSTN permettent à vos utilisateurs de effectuer des appels téléphoniques dans le monde entier.|

**En fonction de vos besoins.** Certaines des sections de cet article sont pertinentes en fonction de votre déploiement et des exigences existantes. Par exemple, un Location-Based routage n’est nécessaire que pour les clients de routage direct dans des emplacements géographiques qui n’autorisent pas la dérivation contre les frais.

Prenez en compte les configurations supplémentaires qui peuvent vous être nécessaires :

![Le diagramme 2 présente d’autres composants vocaux, tels que les numéros de téléphone de Microsoft, les plans de numérotation et le routage des appels, etc.](media/voice-consider-additional-components.png)

| Selon vos besoins | Description |
| :------------|:-------|
| [**Numéros de téléphone de Microsoft**](#phone-numbers-from-microsoft) | Comment obtenir et gérer des numéros de téléphone de Microsoft et comment transférer des numéros existants vers Microsoft. Lisez ceci si vous devez obtenir des numéros de téléphone pour le plan d’appels Microsoft, transférer des numéros existants, obtenir des numéros de service, etc. |
| [**Plans de numérotation et routage des appels**](#dial-plans-and-call-routing) | Comment configurer et gérer des plans de numérotation qui traduisent les numéros de téléphone composés dans un autre format (généralement E.164) pour l’autorisation et le routage des appels. Lisez ceci si vous devez comprendre ce que sont les plans de numérotation et si vous devez spécifier des plans de numérotation pour votre organisation.|
| [**Appels d’urgence**](#emergency-calling) | Comment gérer et configurer les appels d’urgence &mdash; en fonction de votre option de connectivité PSTN. Lisez cette section si vous utilisez un plan d’appel Microsoft ou un routage direct et souhaitez comprendre comment gérer les appels d’urgence pour votre organisation. |
| [**Routage basé sur l’emplacement pour le routage direct**](#location-based-routing-for-direct-routing) |Comment utiliser Location-Based routage de réseau (LBR) pour restreindre le contournement gratuit pour les utilisateurs de Microsoft Teams en fonction de leur emplacement géographique. Lisez cette section si votre organisation utilise le routage direct à un emplacement qui n’autorise pas la dérivation contre les frais.
| [**Topologie de réseau pour les fonctionnalités vocales cloud**](#network-topology-for-voice-features) | Si votre organisation déploie Location-Based routage de réseau (LBR) pour le routage direct ou les appels d’urgence dynamiques, vous devez configurer les paramètres réseau pour les utiliser avec ces fonctionnalités dans Microsoft Teams. Lisez cette section si vous implémentez LBR pour le routage direct, ou si vous implémentez des appels d’urgence dynamiques avec le plan d’appel ou le routage direct. |
| [**Migrer votre solution vocale existante**](#migrate-your-existing-voice-solution-to-teams) | Ce à quoi vous devez penser lors de la migration de votre solution vocale vers Teams.  Lisez cette section si vous migrez d’une solution vocale existante vers Teams. 



> [!Important]
> Cet article traite des solutions vocales avec Microsoft Teams. Bien que les solutions avec Skype Entreprise Online soient toujours disponibles (comme décrit dans les solutions téléphoniques [Microsoft),](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)il est important de comprendre que Skype Entreprise Online sera retiré le 31 juillet 2021.  Après cette date, le service Skype Entreprise Online ne sera plus accessible. Par ailleurs, la connectivité PSTN entre votre environnement local, que ce soit par le biais de Skype Entreprise Server ou de la version Cloud Connector et de Skype Entreprise Online ne sera plus prise en &mdash; &mdash; charge. Cet article présente les solutions vocales Teams et la façon dont vous pouvez connecter votre réseau téléphonique local, le cas échéant, à Teams à l’aide du routage direct.


## <a name="phone-system"></a>Système téléphonique

Phone System est la technologie de Microsoft qui permet d’activer le contrôle des appels et les fonctionnalités PBX (Private Branch Exchange) dans le cloud Microsoft 365 ou Office 365 avec Microsoft Teams.

Phone System fonctionne avec les clients Et périphériques certifiés Teams ou Skype Entreprise. Phone System vous permet de remplacer votre système PBX existant par un ensemble de fonctionnalités directement depuis Microsoft 365 ou Office 365. 

Les appels entre utilisateurs de votre organisation sont gérés en interne au sein du système téléphonique et ne sont jamais passés au réseau téléphonique public commuté (PSTN). Cela s’applique aux appels entre utilisateurs de votre organisation situés dans différentes zones géographiques, en supprimant les coûts longue distance sur ces appels internes.

Cet article présente les fonctionnalités et fonctionnalités clés suivantes du système téléphonique, ainsi que les décisions de déploiement que vous devrez prendre en compte :

- [Standards automatiques et files d’attente d’appels](#auto-attendants-and-call-queues)
- [Messagerie vocale cloud](#cloud-voicemail)
- [Identité d’appel](#calling-identity)

![Diagramme 3 montre que le système téléphonique contient les attendants automatiques et les requêtes d’appel, la messagerie vocale cloud et l’identité d’appel](media/phone-system-contains.png)

Pour plus d’informations sur toutes les fonctionnalités du système téléphonique et sur la façon de configurer Phone System, consultez les articles suivants :

- [Voici les avantages du système téléphonique](here-s-what-you-get-with-phone-system.md)
- [Configurer le système téléphonique dans votre organisation](setting-up-your-phone-system.md)<br>
  Décrit comment acheter et attribuer des licences Phone System, gérer les numéros de téléphone et configurer des crédits de communication pour les numéros gratuits. 

Pour plus d’informations sur la gestion des appareils pris en charge, voir [Gérer vos appareils dans Microsoft Teams](devices/device-management.md) et Teams [Marketplace.](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


### <a name="auto-attendants-and-call-queues"></a>Automatiquement et files d’attente d’appels

Les attendants automatiques vous permettent de configurer des options de menu pour router les appels en fonction de la saisie de l’appelant. Les files d’attente sont des zones d’attente pour les appelants. Utilisées ensemble, les files d’attente automatiques et les files d’attente d’appels peuvent facilement router les appelants vers la personne ou le service approprié dans votre organisation.

Pour plus d’informations sur les files d’attente et les files d’attente automatiques, consultez les articles suivants :

- [Planifier les files d’attente et les files d’attente automatiques de Teams](plan-auto-attendant-call-queue.md)
- [Configurer un attendant automatique](create-a-phone-system-auto-attendant.md)
- [Créer une file d’attente d’appel](create-a-phone-system-call-queue.md) 
- [Étude de cas Contoso : attendants automatiques et files d’attente d’appels](voice-case-study-call-queues.md)<br>
  Décrit comment une entreprise multinationale fictive, Contoso, a implémenté des files d’attente et des files d’attente automatiques pour leur solution vocale.

### <a name="cloud-voicemail"></a>Messagerie vocale cloud

La messagerie vocale cloud, optimisée par les services de messagerie vocale Azure, prend en charge les dépôts de messages vocaux sur les boîtes aux lettres Exchange uniquement. Il ne prend pas en charge les systèmes de courrier tiers. 

La messagerie vocale cloud inclut la transcription des messages vocaux. Elle est activée par défaut pour tous les utilisateurs de votre organisation. Les besoins de votre entreprise peuvent nécessiter la désactivation de la transcription des messages vocaux pour des utilisateurs spécifiques ou pour tous les membres de l’organisation.

Pour les utilisateurs en ligne uniquement, la messagerie vocale cloud est automatiquement mise en service pour les utilisateurs une fois qu’une licence Phone System leur a été attribuée. Pour les utilisateurs de phone system qui ont une boîte aux lettres Exchange, vous devez effectuer des étapes de configuration supplémentaires. 

Pour plus d’informations sur la messagerie vocale cloud et sa configuration, consultez les articles suivants :

- [Configurer la Messagerie vocale cloud](set-up-phone-system-voicemail.md)
- [Définir les stratégies de messagerie vocale dans votre organisation](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a>Identité d’appel

Par défaut, tous les appels sortants utilisent le numéro de téléphone affecté comme identité d’appel (ID de l’appelant). Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel. Pour plus d’informations sur la configuration de l’ID de l’appelant, ou sur la modification ou le blocage de cet ID, voir Définir l’ID d’appelant [d’un utilisateur.](set-the-caller-id-for-a-user.md) 

## <a name="public-switched-telephone-network-connectivity-options"></a>Options de connectivité réseau téléphonique public commuté

Phone System fournit des fonctionnalités PBX complètes pour votre organisation. Toutefois, pour permettre aux utilisateurs de passer des appels en dehors de votre organisation, vous devez connecter le système téléphonique au réseau téléphonique commuté (PSTN). Pour connecter le système téléphonique au réseau PSTN, vous pouvez choisir l’une des options suivantes :

- [**Phone System avec forfait d’appels.**](#phone-system-with-calling-plan) Une solution all-in-the-cloud avec Microsoft comme opérateur PSTN.

- [**Système téléphonique avec votre propre opérateur PSTN en**](#phone-system-with-own-pstn-carrier-with-direct-routing) utilisant le routage direct pour connecter votre environnement local à Teams.

Vous pouvez également choisir une combinaison d’options qui vous permet de concevoir une solution pour un environnement complexe ou de gérer une migration en plusieurs étapes (en savoir plus sur la migration ultérieure).

### <a name="phone-system-with-calling-plan"></a>Système téléphonique avec forfait d’appels 

Comme décrit plus tôt dans cet article, Phone System avec Forfait d’appels est la solution vocale tout-dans-le-cloud de Microsoft pour les utilisateurs de Teams. Il s’agit de l’option la plus simple qui connecte Microsoft Phone System au réseau téléphonique commuté (PSTN) pour activer les appels vers des téléphones fixes et mobiles dans le monde entier. Avec cette option, Microsoft fournit la fonctionnalité PBX (Private Branch Exchange) pour votre organisation et agit en tant qu’opérateur PSTN, comme indiqué dans le diagramme suivant :

![Diagramme 4 montre le système téléphonique avec des serveurs automatiques, des files d’attente d’appels, un ID d’appelant, et Microsoft comme opérateur PSTN](media/voice-solution-microsoft-complete.png)

Si vous répondez oui aux questions suivantes, alors Phone System avec Forfait d’appels est la solution adaptée à vos questions :

- Le forfait d’appels est disponible dans votre région.
- Vous n’avez pas besoin de conserver votre opérateur PSTN actuel.
- Vous voulez utiliser l’accès géré par Microsoft au réseau PSTN.

Avec cette option : 

- Vous obtenez Microsoft Phone System avec des plans d’appels nationaux ou internationaux qui permettent d’appeler vers des téléphones dans le monde entier (selon le niveau de service sous licence).

- Le déploiement ou la maintenance d’un déploiement local n’est pas nécessaire, car le plan d’appel fonctionne avec &mdash; Microsoft 365 ou Office 365.

- Remarque : si nécessaire, vous pouvez choisir de connecter un contrôleur de session border (SBC) pris en charge via un routage direct pour l’interopérabilité avec des PBX tiers, des appareils analogiques et d’autres équipements téléphoniques tiers pris en charge par le SBC.

Cette option nécessite une connexion ininterrompue à Microsoft 365 ou Office 365.

Pour plus d’informations sur le forfait d’appels, consultez les articles suivants :

- [Quelle forfait d’appels vous convient le mieux ?](calling-plan-landing-page.md)
- [Comment acheter un forfait d’appels](calling-plans-for-office-365.md)
- [Disponibilité des forfaits d’appels par pays et par région](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [Configurer le forfait d’appels](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>Système téléphonique avec son propre opérateur PSTN avec un routage direct

Cette option connecte Microsoft Phone System à votre réseau téléphonique à l’aide du routage direct, comme illustré dans le diagramme suivant : 

![Diagramme 5 montre le système téléphonique avec routage direct](media/voice-solution-with-direct-routing.png)

Si vous répondez oui aux questions suivantes, Phone System avec routage direct est la solution adaptée à vos questions :

- Vous voulez utiliser Teams avec Phone System.
- Vous devez conserver votre opérateur PSTN actuel.
- Vous voulez mélanger le routage, certains appels passant par le plan d’appels, d’autres par l’intermédiaire de votre opérateur.
- Vous devez interopérateur avec des SYSTÈMES PBX tiers et/ou des équipements tels que des pageurs généraux, des dispositifs analogiques, etc.

Avec cette option :

- Vous connectez votre propre SBC pris en charge à Microsoft Phone System sans re besoin de logiciel local supplémentaire.

- Vous pouvez utiliser pratiquement n’importe quel opérateur téléphonique avec Microsoft Phone System.

- Vous pouvez choisir de configurer et de gérer cette option, ou elle peut être configurée et gérée par votre opérateur ou partenaire (demandez-lui si votre opérateur ou partenaire propose cette option).

- Vous pouvez configurer l’interopérabilité entre votre équipement téléphonique, tel qu’un PBX tiers, des appareils &mdash; analogiques &mdash; et un système téléphonique Microsoft.


Cette option nécessite les options suivantes :

- Connexion ininterrompue à Microsoft 365 ou Office 365.

- Déploiement et maintenance d’un SBC pris en charge.

- Contrat avec un opérateur tiers.
  (Sauf dans le cadre du déploiement en tant qu’option de connexion au PBX tiers, aux périphériques analogiques ou à d’autres équipements téléphoniques pour les utilisateurs qui utilisent phone system avec le plan d’appel.)

Pour plus d’informations sur le routage direct, voir les articles suivants :

- [Routage direct via le système téléphonique](direct-routing-landing-page.md)
- [Planifier le routage direct](direct-routing-plan.md)
- [Configurer le routage direct](direct-routing-configure.md)
- [Gérer les stratégies de routage vocal pour les utiliser avec le routage direct](manage-voice-routing-policies.md)
- [Planifier le routage géodépendant pour le routage direct](location-based-routing-plan.md)
- [Liste des contrôleurs de frontière de session certifiés pour le routage direct](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a>Numéros de téléphone de Microsoft

Microsoft propose deux types de  numéros de téléphone : les numéros d’abonnés (utilisateurs) qui peuvent être attribués à des utilisateurs de votre organisation et les numéros de *service* disponibles sous forme de numéros de service gratuits et gratuits. Les numéros de service ont une capacité d’appels simultanés supérieure à celle des numéros d’abonné et peuvent être affectés à des services tels que l’Audioconférence, les attendants automatiques ou les files d’attente d’appels.

Vous devrez décider des choix ci-après :

- Quels emplacements utilisateur ont besoin de nouveaux numéros de téléphone de Microsoft ?
- De quel type de numéro de téléphone (abonné ou service) ai-je besoin ? 
- Comment puis-je porter des numéros de téléphone existants vers Teams ?

Pour plus d’informations sur la gestion des numéros de téléphone dans votre organisation, y compris l’obtention de nouveaux numéros ou le transfert de numéros de sortie, consultez les articles suivants :

- [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [Différents types de numéros de téléphone utilisés pour les forfaits d’appels](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Obtention de numéros de téléphone pour vos utilisateurs](getting-phone-numbers-for-your-users.md)
- [Transférer des numéros de téléphone dans Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>Plans de numérotation et routage des appels

Un plan de numérotation est un ensemble de règles de normalisation qui traduisent les numéros de téléphone composés dans un autre format (généralement E.164) pour l’autorisation et le routage des appels.

Vous devrez décider des choses suivantes : 

- Mon organisation a-t-elle besoin d’un plan de numérotation personnalisé ?
- Quels utilisateurs ont besoin d’un plan de numérotation personnalisé ?
- Quel plan de numérotation client doit être attribué à chaque utilisateur ?

Pour plus d’informations, voir les articles suivants : 

- [Qu’est-ce que les plans de numérotation ?](what-are-dial-plans.md)
- [Planifier les plans de numérotation client](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [Créer et gérer les plans de numérotation](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>Appel d’urgence

La configuration des appels d’urgence diffère en fonction de l’option de connectivité RSTN : Plan d’appel Microsoft ou Routage direct. Les appels d’urgence dynamiques pour le plan d’appels Microsoft et le routage direct du système téléphonique offrent la possibilité de configurer et de router des appels d’urgence et de notifier le personnel de sécurité en fonction de l’emplacement actuel du client Teams. Pour plus d’informations sur les concepts d’appel d’urgence et la terminologie, et sur la configuration des appels d’urgence dynamiques, consultez les articles suivants :

- [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planifier et configurer un appel d’urgence dynamique](configure-dynamic-emergency-calling.md)
- [Étude de cas Contoso : appels d’urgence](voice-case-study-emergency-calling.md)<br>
  Décrit comment une entreprise multinationale fictive, Contoso, a implémenté des appels d’urgence pour leur organisation.

## <a name="location-based-routing-for-direct-routing"></a>Location-Based routage pour le routage direct

Dans certains pays et certaines régions, il n’est pas illégal de contourner le fournisseur de réseau téléphonique commuté (PSTN) afin de diminuer les coûts des appels longue distance. Location-Based routage pour le routage direct vous permet de restreindre le contournement gratuit pour les utilisateurs de Microsoft Teams en fonction de leur emplacement géographique. Pour plus d’informations sur la façon de planifier et de configurer Location-Based routage des détails, consultez les articles suivants :

- [Planifier le routage géodépendant pour le routage direct](location-based-routing-plan.md)
- [Configurer les paramètres de réseau pour le routage géodépendant](location-based-routing-configure-network-settings.md)
- [Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)
- [Étude de cas Contoso : Location-Based routage](voice-case-study-location-based-routing.md)<br>
  Décrit la façon dont Contoso, une entreprise multinationale fictive, a implémenté un Location-Based routage pour leur organisation.

## <a name="network-topology-for-voice-features"></a>Topologie de réseau pour les fonctionnalités vocales

Si vous déployez des appels d’urgence dynamiques ou un Location-Based de routage direct, vous devez configurer les paramètres réseau pour les utiliser avec ces fonctionnalités dans Microsoft Teams. Pour découvrir comment configurer les paramètres réseau pour les régions réseau, les sites réseau, les sous-réseaux et les adresses IP de confiance, consultez les articles suivants :

- [Paramètres réseau pour les fonctionnalités vocales cloud dans Microsoft Teams - Concepts et terminologie](cloud-voice-network-settings.md)
- [Gérer votre topologie de réseau pour les fonctionnalités vocales cloud dans Microsoft Teams](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>Migrer votre solution vocale existante vers Teams

Pour une organisation qui fait la mise à niveau vers Teams, l’objectif ultime est de déplacer tous les utilisateurs vers le mode TeamsOnly. L’utilisation du système téléphonique avec Teams n’est prise en charge que lorsque l’utilisateur est en mode TeamsOnly. Si vous avez besoin d’informations de base sur la mise à niveau vers Teams, commencez ici :

- [Prise en main de votre mise à niveau de Microsoft Teams](upgrade-start-here.md)
- [À propos du cadre de mise à niveau](upgrade-framework.md)
- [Stratégies de mise à niveau pour les administrateurs informatiques](upgrade-to-teams-on-prem-implement.md)

Lors de la migration de votre solution vocale, quatre scénarios d’appel sont possibles lors du passage en mode TeamsOnly :

- [**Un utilisateur dans Skype Entreprise Online, avec un plan d’appel Microsoft.**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans) Lors de la mise à niveau, cet utilisateur continuera à avoir un plan d’appel Microsoft.

- Un utilisateur dans Skype Entreprise Online, avec des **[fonctionnalités vocales](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** en local par le biais de Skype Entreprise en local ou édition Cloud Connector. La mise à niveau de l’utilisateur vers Teams doit être coordonnée avec la migration de l’utilisateur vers le routage direct pour s’assurer que l’utilisateur TeamsOnly dispose de la fonctionnalité PSTN.

- Un utilisateur de Skype Entreprise sur site avec Voix Entreprise, qui passe à la connexion en ligne et maintient la connectivité **[](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)RSTN sur site.** La migration de cet utilisateur vers Teams nécessite le déplacement du compte Skype Entreprise local de l’utilisateur vers le cloud et la coordination de ce déplacement avec la migration de l’utilisateur vers le routage direct. 

- Un utilisateur de Skype Entreprise sur site avec Voix Entreprise, qui passe au service en ligne et utilise un **[](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)plan d’appel Microsoft.**  La migration de cet utilisateur vers Teams nécessite le déplacement du compte Skype Entreprise local de l’utilisateur vers le cloud et la coordination du déplacement avec l’un des A) port du numéro de téléphone de cet utilisateur vers un plan d’appels Microsoft ou B) et l’affectation d’un nouveau numéro d’abonné à partir des régions disponibles.

Pour plus d’informations sur l’implémentation de la migration vocale pour chacun de ces scénarios, notamment sur la nécessité de configurer une connectivité hybride et la migration des utilisateurs avec la fonctionnalité vocale sur site vers le routage direct, voir les &mdash; articles suivants &mdash; :

- [Considérations PSTN lors de la mise à niveau vers Teams — pour les administrateurs informatiques](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Étude de cas de migration vocale dans Contoso](voice-case-study-overview.md)<br>
  Cette étude de cas décrit la façon dont contoso, une entreprise multinationale fictive, a implémenté une solution vocale Teams pour leur organisation. Il contient les articles suivants :

  - [Plan de mise à niveau de Teams](voice-case-study-migration-plan.md)
  - [Options de connectivité système téléphonique et PSTN](voice-case-study-phone-system.md)
  - [Implémentation d’un routage basé sur l’emplacement](voice-case-study-location-based-routing.md)
  - [Appels d’urgence](voice-case-study-emergency-calling.md)
  - [Standards automatiques et files d’attente d’appels](voice-case-study-call-queues.md)
  - [Audioconférence](voice-case-study-audio-conferencing.md)












