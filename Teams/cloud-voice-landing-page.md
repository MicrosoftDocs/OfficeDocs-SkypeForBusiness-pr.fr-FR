---
title: Planifier votre solution vocale dans Microsoft teams
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
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: En savoir plus sur les fonctionnalités de voix sur le Cloud de Microsoft teams et les décisions de déploiement que vous allez apporter à votre organisation.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 213950b808d781e8566e1ffae6f6075bb7b3371b
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686450"
---
# <a name="plan-your-teams-voice-solution"></a>Planifier votre solution vocale teams 

Cet article vous aide à déterminer la solution Microsoft Voice adaptée à votre organisation. Après avoir décidé, l’article fournit une introduction au contenu qui vous permettra d’implémenter la solution que vous avez choisie.

> [!NOTE]
> Pour obtenir des instructions sur la planification d’une solution vocale d’équipes dans le cadre de la mise à niveau vers teams depuis Skype entreprise Server, voir [considérations RTC pour la mise à niveau vers teams depuis Skype entreprise local](upgrade-to-Teams-on-prem-pstn-considerations.md).

Vous voudrez peut-être utiliser le système téléphonique de la solution la plus simple &mdash; avec le plan d’appels. Il s’agit de la solution tout-en-Cloud de Microsoft qui fournit les fonctionnalités de PBX et les appels au réseau téléphonique public commuté (RTC), comme indiqué dans le schéma suivant. Avec cette solution, Microsoft est votre opérateur PSTN.

![Le diagramme 1 montre un système téléphonique avec un plan d’appels](media/voice-solutions-simple.png)

Si vous répondez oui à ce qui suit, le système téléphonique avec la formule d’appel est la solution adaptée à votre cas :

- Le plan d’appels est disponible dans votre région.
- Vous n’avez pas besoin de conserver votre opérateur PSTN actuel.
- Vous voulez utiliser l’accès géré par Microsoft au RTC.

Toutefois, votre situation peut être plus complexe. Par exemple, il est possible que vous disposiez de bureaux où le plan d’appels n’est pas disponible. Par ailleurs, vous aurez peut-être besoin d’une solution combinée qui prend en charge un déploiement à plusieurs niveaux, avec des exigences différentes pour différents emplacements géographiques. Microsoft prend en charge un ensemble de solutions : 

- Système téléphonique avec un plan d’appels
- Système téléphonique avec votre propre opérateur PSTN avec routage direct
- Solution combinée qui utilise à la fois un système téléphonique et un plan d’appel et un système téléphonique avec le routage direct

## <a name="what-do-you-need-to-read"></a>Que devez-vous lire ?

**Obligatoire pour tous.** Certaines des sections de cet article s’appliquent à toutes les organisations. Par exemple, tout le monde doit en savoir plus sur le système téléphonique et comprendre les options de connexion au réseau téléphonique public commuté (RTC). 


| Obligatoire pour tous | Description |
| :------------|:-------|
| [**Système téléphonique**](#phone-system) | Technologie de Microsoft pour l’activation du contrôle des appels et des fonctionnalités de branchement privée (PBX) dans le Cloud Microsoft 365 et Microsoft Teams. |
| [**Options de connectivité du réseau téléphonique public commuté (RTC)**](#public-switched-telephone-network-connectivity-options) | Choix entre Microsoft en tant qu’opérateur de téléphonie ou de connexion de votre opérateur de téléphonie à Microsoft teams via le routage direct. Combiné au système téléphonique, les options de connectivité PSTN permettent aux utilisateurs de passer des appels téléphoniques partout dans le monde.|

**Selon vos besoins.** Certaines des sections de cet article sont pertinentes en fonction de votre déploiement actuel et de vos exigences. Par exemple, le routage Location-Based est requis uniquement pour les clients de routage direct situés dans des emplacements géographiques qui n’autorisent pas le contournement du numéro.

Déterminez les configurations supplémentaires dont vous aurez besoin :

![Le diagramme 2 indique les composants vocaux supplémentaires, tels que les numéros de téléphone de Microsoft, les plans de numérotation et le routage des appels, etc.](media/voice-consider-additional-components.png)

| Selon vos besoins | Description |
| :------------|:-------|
| [**Numéros de téléphone de Microsoft**](#phone-numbers-from-microsoft) | Découvrez comment obtenir et gérer des numéros de téléphone de Microsoft et comment transférer des numéros existants vers Microsoft. Prenez connaissance de cette offre si vous avez besoin d’obtenir des numéros de téléphone pour votre forfait d’appel Microsoft, de transférer des numéros existants, d’obtenir des numéros de service, etc. |
| [**Plans de numérotation et routage des appels**](#dial-plans-and-call-routing) | Comment configurer et gérer les plans de numérotation qui convertissent les numéros de téléphone numérotés dans un autre format (généralement le format E. 164) pour l’autorisation et le routage des appels. Lisez cet élément si vous devez comprendre ce que sont les plans de numérotation et si vous devez spécifier des plans de numérotation pour votre organisation.|
| [**Appels d’urgence**](#emergency-calling) | Comment gérer et configurer les appels &mdash; d’urgence en fonction de votre option de connectivité PSTN. Lisez cette section si vous utilisez un plan d’appel Microsoft ou le routage direct et que vous avez besoin de comprendre comment gérer les appels d’urgence pour votre organisation. |
| [**Routage en fonction de l’emplacement pour le routage direct**](#location-based-routing-for-direct-routing) |Comment utiliser le routage de Location-Based (LBR) pour limiter le contournement de péage pour les utilisateurs de Microsoft teams en fonction de leur emplacement géographique. Prenez connaissance de cette section si votre organisation utilise le routage direct à un emplacement qui ne permet pas un contournement payant.
| [**Topologie réseau pour les fonctionnalités vocales de Cloud**](#network-topology-for-voice-features) | Si votre organisation déploie le routage de Location-Based (LBR) pour le routage direct ou les appels d’urgence dynamiques, vous devez configurer les paramètres réseau pour utiliser ces fonctionnalités dans Microsoft Teams. Lisez cette section si vous implémentez LBR pour le routage direct ou si vous implémentez des appels d’urgence dynamiques avec un plan d’appels ou un routage direct. |
| [**Migrer votre solution vocale existante**](#migrate-your-existing-voice-solution-to-teams) | Ce que vous devez savoir lors de la migration de votre solution vocale vers Teams.  Lisez cette section si vous effectuez une migration à partir d’une solution vocale existante vers Teams. 



> [!Important]
> Cet article se concentre sur les solutions vocales avec Microsoft Teams. Si les solutions avec Skype entreprise Online sont toujours disponibles (comme décrit dans la rubrique [solutions de téléphonie Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)), il est important de comprendre que Skype entreprise Online sera supprimé le 31 juillet 2021.  Après cette date, le service Skype entreprise Online ne sera plus accessible. Par ailleurs, la connectivité PSTN entre votre environnement local, &mdash; que ce soit par le biais de Skype entreprise Server ou de la version Cloud Connector &mdash; et de Skype entreprise Online ne sera plus prise en charge. Cet article présente les solutions vocales teams et la façon de vous connecter à votre réseau téléphonique local, si nécessaire, aux équipes à l’aide du routage direct.


## <a name="phone-system"></a>Système téléphonique

Le système téléphonique est la technologie de Microsoft permettant d’activer le contrôle d’appel et les fonctionnalités de branchement privée (PBX) dans le Cloud Microsoft 365 ou Office 365 avec Microsoft Teams.

Le système téléphonique fonctionne avec les équipes ou les clients Skype entreprise et les appareils certifiés. Le système téléphonique vous permet de remplacer votre système PBX existant par un ensemble de fonctionnalités directement fournies par Microsoft 365 ou Office 365. 

Les appels entre les utilisateurs de votre organisation sont gérés en interne au sein du système téléphonique et ne sont jamais dirigés vers le réseau téléphonique public commuté (RTC). Cela concerne les appels entre les utilisateurs de votre organisation qui se trouvent dans des zones géographiques différentes, en supprimant les coûts de grande distance de ces appels internes.

Cet article présente les fonctionnalités clés du système téléphonique et ses fonctionnalités, ainsi que les décisions de déploiement que vous devez prendre en compte :

- [Standards automatiques et files d’attente d’appels](#auto-attendants-and-call-queues)
- [Messagerie vocale cloud](#cloud-voicemail)
- [Identité d’appel](#calling-identity)

![Le diagramme 3 indique que le système téléphonique contient des standards automatiques, des requêtes d’appel, la boîte vocale Cloud et l’identité des appels](media/phone-system-contains.png)

Pour plus d’informations sur l’ensemble des fonctionnalités du système téléphonique et sur la configuration du système téléphonique, voir les articles suivants :

- [Voici les avantages du système téléphonique](here-s-what-you-get-with-phone-system.md)
- [Configurer le système téléphonique au sein de votre organisation](setting-up-your-phone-system.md)<br>
  Décrit comment acheter et affecter des licences de système téléphonique, gérer des numéros de téléphone et configurer des crédits de communication pour les numéros sans frais. 

Pour plus d’informations sur la gestion des appareils pris en charge, voir [gérer vos appareils dans Microsoft teams](devices/device-management.md) et [teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).


### <a name="auto-attendants-and-call-queues"></a>Standards automatiques et files d’attente d’appels

Les standards automatiques vous permettent de configurer des options de menu pour acheminer les appels en fonction de l’entrée de l’appelant. Les files d’attente d’appels sont des zones d’attente pour les appelants. Utilisées ensemble, les standards automatiques et les files d’attente d’appels peuvent facilement router les appelants vers la personne ou le service approprié au sein de votre organisation.

Pour plus d’informations sur les standards automatiques et les files d’attente d’appels, voir les articles suivants :

- [Plan pour les standards automatiques d’équipe et les files d’attente d’appels](plan-auto-attendant-call-queue.md)
- [Configurer un standard automatique](create-a-phone-system-auto-attendant.md)
- [Créer une file d’attente d’appel](create-a-phone-system-call-queue.md) 
- [Étude de cas contoso : standards automatiques et files d’attente d’appels](voice-case-study-call-queues.md)<br>
  Décrit comment une entreprise fictive multinationale fictive, contoso, a implémenté des standards automatiques et des files d’attente pour leur solution vocale.

### <a name="cloud-voicemail"></a>Messagerie vocale cloud

La messagerie vocale Cloud, optimisée par les services de boîte vocale Azure, ne prend en charge que les dépôts vocaux dans les boîtes aux lettres Exchange. Les systèmes de courrier tiers ne sont pas pris en charge. 

La messagerie vocale Cloud inclut la transcription de la boîte vocale, qui est activée par défaut pour tous les utilisateurs de votre organisation. Les besoins de votre entreprise peuvent nécessiter la désactivation de la transcription de la boîte vocale pour des utilisateurs spécifiques ou pour tout le monde au sein de l’organisation.

Pour les utilisateurs uniquement en ligne, la boîte vocale Cloud est configurée et approvisionnée automatiquement pour les utilisateurs après leur attribution d’une licence de système téléphonique. Pour les utilisateurs du système téléphonique disposant d’une boîte aux lettres Exchange, vous devez effectuer des étapes de configuration supplémentaires. 

Pour plus d’informations sur la boîte vocale Cloud et sa configuration, consultez les articles suivants :

- [Configurer la Messagerie vocale cloud](set-up-phone-system-voicemail.md)
- [Définir des stratégies de messagerie vocale au sein de votre organisation](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a>Identité d’appel

Par défaut, tous les appels sortants utilisent le numéro de téléphone attribué en tant qu’identité d’appel (ID d’appelant). Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel. Pour plus d’informations sur la configuration de l’identification de l’appelant ou pour modifier ou bloquer l’ID de l’appelant, voir [définir l’ID d’appelant d’un utilisateur](set-the-caller-id-for-a-user.md). 

## <a name="public-switched-telephone-network-connectivity-options"></a>Options de connectivité du réseau téléphonique commuté public

Le système téléphonique fournit des fonctionnalités PBX complètes pour votre organisation. Toutefois, pour permettre aux utilisateurs d’effectuer des appels hors de votre organisation, vous devez connecter le système téléphonique au réseau téléphonique public commuté (RTC). Pour connecter un système téléphonique au RTC, vous pouvez choisir l’une des options suivantes :

- [**Système téléphonique avec un plan d’appels**](#phone-system-with-calling-plan). Une solution tout-en-un-Cloud avec Microsoft comme opérateur PSTN.

- [**Système téléphonique avec votre propre opérateur PSTN**](#phone-system-with-own-pstn-carrier-with-direct-routing) en utilisant le routage direct pour connecter votre environnement local à Teams.

Vous pouvez également choisir une combinaison d’options vous permettant de concevoir une solution pour un environnement complexe ou de gérer une migration en plusieurs étapes (en savoir plus sur la migration plus tard).

### <a name="phone-system-with-calling-plan"></a>Système téléphonique avec un plan d’appels 

Comme décrit précédemment dans cet article, le système téléphonique avec un plan d’appels est le système de gestion vocale tout-en-le Cloud de Microsoft pour les utilisateurs de teams. Il s’agit de l’option la plus simple qui connecte le système Microsoft Phone au réseau téléphonique public commuté (RTC) pour permettre les appels vers des téléphones fixes et mobiles dans le monde entier. Avec cette option, Microsoft fournit des fonctionnalités PBX (Private Branch Exchange) pour votre organisation et agit comme votre opérateur PSTN, comme illustré dans le schéma suivant :

![Le diagramme 4 illustre le système téléphonique avec les standards automatiques, les files d’attente d’appels, l’identification de l’appelant, etc., et Microsoft comme opérateur PSTN](media/voice-solution-microsoft-complete.png)

Si vous répondez oui à ce qui suit, le système téléphonique avec la formule d’appel est la solution adaptée à votre cas :

- Le plan d’appels est disponible dans votre région.
- Vous n’avez pas besoin de conserver votre opérateur PSTN actuel.
- Vous voulez utiliser l’accès géré par Microsoft au RTC.

Avec cette option : 

- Vous obtenez un système Microsoft Phone avec des plans d’appels nationaux ou internationaux qui permettent d’appeler des téléphones dans le monde entier (en fonction du niveau de service sous licence).

- Vous n’avez pas besoin de déploiement ou de maintenance d’un déploiement local &mdash; , car le plan d’appel ne fonctionne pas sur Microsoft 365 ou Office 365.

- Remarque : si nécessaire, vous pouvez choisir de connecter un contrôleur de bordure de session (SBC) pris en charge par le routage direct pour l’interopérabilité avec des PBX tiers, des appareils analogiques et d’autres équipements de téléphonie tiers pris en charge par l’SBC.

Cette option nécessite une connexion sans interruption à Microsoft 365 ou Office 365.

Pour plus d’informations sur la planification des appels, voir les articles suivants :

- [Quelle forfait d’appels vous convient le mieux ?](calling-plan-landing-page.md)
- [Comment acheter un forfait d’appels](calling-plans-for-office-365.md)
- [Disponibilité des forfaits d’appels par pays et par région](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [Configurer un plan d’appels](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>Système téléphonique avec son propre opérateur PSTN avec routage direct

Cette option connecte le système Microsoft Phone à votre réseau téléphonique en utilisant le routage direct, comme indiqué dans le schéma suivant : 

![Diagramme 5 montrant le système téléphonique avec le routage direct](media/voice-solution-with-direct-routing.png)

Si vous répondez oui aux questions suivantes, le système téléphonique avec le routage direct est la solution adaptée à votre cas :

- Vous voulez utiliser teams avec un système téléphonique.
- Vous devez conserver votre opérateur PSTN actuel.
- Vous voulez combiner le routage, avec certains appels passant par la formule d’appel, par le biais de votre opérateur.
- Vous devez interopérer avec des PBX et/ou des équipements tiers tels que les recharges informatiques des États-Unis, les appareils analogiques, etc.

Avec cette option :

- Vous connectez votre propre SBC au système Microsoft Phone compatible sans avoir besoin d’un logiciel local supplémentaire.

- Vous pouvez utiliser quasiment n’importe quel opérateur de téléphonie doté du système Microsoft Phone.

- Vous pouvez choisir de configurer et de gérer cette option, ou être configuré et géré par votre opérateur ou partenaire (demander si votre opérateur ou partenaire fournit cette option).

- Vous pouvez configurer l’interopérabilité entre votre équipement de téléphonie, &mdash; tel qu’un système PBX tiers et des appareils analogiques &mdash; et Microsoft Phone.


Pour cela, vous devez disposer des éléments suivants :

- Connexion sans interruption à Microsoft 365 ou Office 365.

- Déploiement et mise à jour d’un SBC pris en charge.

- Contrat avec un opérateur tiers.
  (Sauf s’il est déployé en tant qu’option pour fournir une connexion à un système PBX tiers, des appareils analogiques ou un autre équipement de téléphonie pour les utilisateurs qui utilisent un plan d’appels.)

Pour plus d’informations sur le routage direct, voir les articles suivants :

- [Routage direct via le système téléphonique](direct-routing-landing-page.md)
- [Planifier le routage direct](direct-routing-plan.md)
- [Configurer le routage direct](direct-routing-configure.md)
- [Gérer les stratégies de routage téléphonique pour une utilisation avec le routage direct](manage-voice-routing-policies.md)
- [Planifier le routage géodépendant pour le routage direct](location-based-routing-plan.md)
- [Liste des contrôleurs de frontière de session certifiés pour le routage direct](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a>Numéros de téléphone de Microsoft

Microsoft est doté de deux types de numéros de téléphone disponibles : les numéros d' *abonnés* (utilisateurs), qui peuvent être attribués à des utilisateurs de votre organisation et des numéros de *service* , disponibles en tant que numéros de service gratuits ou payants. Les numéros de service disposent d’une capacité d’appels simultanée supérieure à celle des numéros d’abonnés et peuvent être attribués à des services, tels que les téléconférences, les standards automatiques ou les files d’attente d’appels.

Vous devez choisir :

- Quels sont les emplacements des utilisateurs qui ont besoin de nouveaux numéros de téléphone de Microsoft ?
- Quel type de numéro de téléphone (abonné ou service) ai-je besoin ? 
- Comment puis-je porter des numéros de téléphone existants vers teams ?

Pour plus d’informations sur la gestion des numéros de téléphone au sein de votre organisation, notamment la réception de nouveaux numéros ou le transfert de numéros en sortie, reportez-vous aux articles suivants :

- [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [Différents types de numéros de téléphone utilisés pour les offres d’appels](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Obtention de numéros de téléphone pour vos utilisateurs](getting-phone-numbers-for-your-users.md)
- [Transfert de numéros de téléphone dans Microsoft teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>Plans de numérotation et routage des appels

Un plan de numérotation est un ensemble de règles de normalisation qui permettent de traduire des numéros de téléphone dans un autre format (généralement le format E. 164) pour l’autorisation et le routage des appels.

Vous devez prendre les décisions suivantes : 

- Mon organisation a-t-elle besoin d’un plan de numérotation personnalisé ?
- Quels sont les utilisateurs qui ont besoin d’un plan de numérotation personnalisé ?
- Quel plan de numérotation client doit être attribué à chaque utilisateur ?

Pour plus d’informations, consultez les articles suivants : 

- [Qu’est-ce que les plans de numérotation ?](what-are-dial-plans.md)
- [Planifier les plans de numérotation client](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [Créer et gérer les plans de numérotation](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>Appel d’urgence

Le mode de configuration des appels d’urgence varie en fonction de votre option de connectivité PSTN : forfait d’appel Microsoft ou routage direct. Les appels d’urgence dynamiques pour le plan d’appel Microsoft et le routage direct du système téléphonique permettent de configurer et d’acheminer les appels d’urgence et de notifier le personnel de sécurité en fonction de l’emplacement actuel du client Teams. Pour plus d’informations sur les concepts et la terminologie des appels d’urgence, et sur la configuration des appels d’urgence dynamiques, voir les articles suivants :

- [Gérer les appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planifier et configurer un appel d’urgence dynamique](configure-dynamic-emergency-calling.md)
- [Étude de cas contoso : appels d’urgence](voice-case-study-emergency-calling.md)<br>
  Décrit le fonctionnement des appels d’urgence d’une entreprise fictive par le biais de la fonction contoso.

## <a name="location-based-routing-for-direct-routing"></a>Routage de Location-Based pour le routage direct

Dans certains pays et certaines régions, il est illégal d’ignorer le fournisseur de réseau téléphonique commuté (PSTN) pour réduire les frais d’appel longue distance. Location-Based le routage pour le routage direct permet de limiter le contournement payant pour les utilisateurs de Microsoft teams en fonction de leur emplacement géographique. Pour plus d’informations sur la planification et la configuration de l’acheminement des Location-Based (LBR), consultez les articles suivants :

- [Planifier le routage géodépendant pour le routage direct](location-based-routing-plan.md)
- [Configurer les paramètres de réseau pour le routage géodépendant](location-based-routing-configure-network-settings.md)
- [Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)
- [Étude de cas contoso : routage de Location-Based](voice-case-study-location-based-routing.md)<br>
  Décrit la façon dont une entreprise mutualisée fictive, contoso, implémentée Location-Based routage pour son organisation.

## <a name="network-topology-for-voice-features"></a>Topologie réseau pour les fonctionnalités vocales

Si vous déployez des appels d’urgence dynamiques ou des Location-Based le routage pour le routage direct, vous devez configurer les paramètres réseau pour les utiliser avec ces fonctionnalités de Microsoft Teams. Pour plus d’informations sur la configuration des paramètres réseau pour les régions réseau, les sites réseau, les sous-réseaux et les adresses IP approuvées, consultez les articles suivants :

- [Paramètres réseau pour les fonctionnalités vocales de Microsoft teams-concepts et terminologie](cloud-voice-network-settings.md)
- [Gérer la topologie de votre réseau pour les fonctionnalités vocales de Microsoft teams](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>Migrer votre solution vocale actuelle vers teams

Pour une organisation qui effectue une mise à niveau vers Teams, l’objectif ultime consiste à déplacer tous les utilisateurs vers le mode TeamsOnly. L’utilisation du système téléphonique avec teams est uniquement prise en charge lorsque l’utilisateur est en mode TeamsOnly. Si vous avez besoin d’informations de base sur la mise à niveau vers Teams, commencez ici :

- [Prise en main de votre mise à niveau de Microsoft Teams](upgrade-start-here.md)
- [À propos du cadre de mise à niveau](upgrade-framework.md)
- [Mise à niveau de Skype entreprise vers équipes : pour les administrateurs informatiques](upgrade-to-teams-on-prem-overview.md)

Lors de la migration de votre solution vocale, il existe quatre scénarios d’appel possibles lors du passage au mode TeamsOnly :

- [**Un utilisateur de Skype entreprise Online avec un plan d’appels Microsoft**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans). Suite à la mise à niveau, cet utilisateur aura besoin d’un plan d’appels Microsoft.

- **[Un utilisateur de Skype entreprise Online avec la fonction vocale locale](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) via Skype entreprise local ou la version Cloud Connector**. La mise à niveau de l’utilisateur vers teams doit être coordonnée avec la migration de l’utilisateur pour diriger le routage afin de garantir que l’utilisateur TeamsOnly dispose de la fonctionnalité RTC.

- **[Un utilisateur de Skype entreprise sur site avec voix entreprise](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), qui va basculer vers une connectivité RTC sur site**. La migration de cet utilisateur vers teams nécessite le passage du compte Skype entreprise local de l’utilisateur dans le Cloud, et le coordination du déplacement avec la migration de celui-ci pour le routage directe. 

- **[Un utilisateur de Skype entreprise sur site avec voix entreprise](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), qui sera déplacé vers en ligne et utilisant un forfait d’appel Microsoft**.  La migration de cet utilisateur vers teams nécessite le passage du compte Skype entreprise local de l’utilisateur dans le Cloud, et la coordination de la migration à l’aide de l’un des numéros de téléphone de l’utilisateur vers un forfait d’appel Microsoft ou B), en attribuant un nouveau numéro d’abonné à partir des régions disponibles.

Pour plus d’informations sur la manière d’implémenter la migration vocale pour chacun de ces scénarios &mdash; , y compris des informations sur la configuration de la connectivité hybride et la migration des utilisateurs disposant d’une fonctionnalité vocale locale vers le routage direct, &mdash; voir les articles suivants :

- [Considérations RTC lors de la mise à niveau vers teams : pour les administrateurs informatiques](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Étude de cas de migration vocale contoso](voice-case-study-overview.md)<br>
  L’étude de cas décrit la façon dont une entreprise mutualisée fictive Contoso a implémenté une solution vocale teams pour son organisation. Il contient les articles suivants :

  - [Plan de mise à niveau de teams](voice-case-study-migration-plan.md)
  - [Options système téléphonique et connectivité PSTN](voice-case-study-phone-system.md)
  - [Implémentation du routage basée sur l’emplacement](voice-case-study-location-based-routing.md)
  - [Appels d’urgence](voice-case-study-emergency-calling.md)
  - [Standards automatiques et files d’attente d’appels](voice-case-study-call-queues.md)
  - [Audioconférence](voice-case-study-audio-conferencing.md)












