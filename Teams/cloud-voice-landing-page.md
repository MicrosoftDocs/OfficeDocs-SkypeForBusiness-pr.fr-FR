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
description: En savoir plus sur Microsoft Teams fonctionnalités vocales cloud et les décisions de déploiement que vous prendrez pour votre organisation.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f6d857e11545df9c338dd2c75b089d8bef0247e
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518796"
---
# <a name="plan-your-teams-voice-solution"></a>Planifier votre solution Teams voix

Cet article vous aide à déterminer la solution Microsoft Voice adaptée à votre organisation. Une fois que vous avez décidé, l’article fournit une feuille de route vers le contenu qui vous permettra d’implémenter la solution choisie.

Vous souhaitez peut-être trouver la solution la plus simple Système téléphonique’aide&mdash; de forfait d’appels. Cette option est la solution complète dans le cloud de Microsoft qui fournit la fonctionnalité PBX (Private Branch Exchange) et des appels vers le réseau téléphonique commuté (PSTN), comme illustré dans le diagramme suivant. Avec cette solution, Microsoft est votre opérateur PSTN.

![Le diagramme 1 montre les Système téléphonique’aide d’un plan d’appels.](media/voice-solutions-simple.png)

Si vous répondez oui aux questions suivantes, c’est Système téléphonique’aide du plan d’appels est la solution adaptée à vos questions :

- Forfait d’appels disponible dans votre région.
- Vous n’avez pas besoin de conserver votre opérateur PSTN actuel.
- Vous voulez utiliser l’accès géré par Microsoft au réseau PSTN.

Toutefois, votre situation peut être plus complexe. Par exemple, vous pouvez avoir des bureaux dans des emplacements où le plan d’appel n’est pas disponible. Vous pouvez également avoir besoin d’une solution combinée qui prend en charge un déploiement complexe et multi-national, avec des exigences différentes pour différents emplacements géographiques. Microsoft prend en charge une combinaison de solutions :

- Système téléphonique forfait d’appels
- Système téléphonique votre propre opérateur PSTN avec l’opérateur Connecter
- Système téléphonique votre propre opérateur PSTN avec un routage direct
- Solution combinée qui utilise Système téléphonique plan d’appels, une Système téléphonique’opérateur Connecter et/ou une Système téléphonique de routage direct

>[!NOTE]
>Si vous êtes une petite à moyenne entreprise (300 personnes ou moins), Microsoft offre maintenant des offres Système téléphonique un plan d’appels nationaux. Pour plus d’informations, [Système téléphonique conseils](/microsoftteams/business-voice/whats-business-voice) pour les petites et moyennes entreprises pour vous aider à planifier, configurer et gérer votre solution vocale.

## <a name="what-do-you-need-to-read"></a>Que devez-vous lire ?

**Obligatoire pour tous.** Certaines des sections de cet article concernent toutes les organisations. Par exemple, tout le monde doit lire les informations Système téléphonique comprendre les options de connexion au réseau téléphonique public commuté (PSTN).


| Obligatoire pour tous | Description |
| :------------|:-------|
| [**Système téléphonique**](#phone-system) | La technologie microsoft permettant d’activer le contrôle des appels et les fonctionnalités de Exchange de branche privée (PBX) dans le cloud Microsoft 365'Microsoft Teams. |
| [**Options de connectivité de réseau téléphonique commuté (PSTN)**](#public-switched-telephone-network-connectivity-options) | Choisissez Microsoft comme opérateur de téléphonie ou connectez votre propre opérateur de téléphonie à Microsoft Teams à l’aide de l’opérateur Connecter ou du routage direct. Combinées aux Système téléphonique, les options de connectivité PSTN permettent à vos utilisateurs de effectuer des appels téléphoniques dans le monde entier.|

**En fonction de vos besoins.** Certaines des sections de cet article et des articles connexes sont pertinentes en fonction de votre déploiement et des exigences existantes. Par exemple, un Location-Based routage n’est nécessaire que pour les clients de routage direct dans des emplacements géographiques qui n’autorisent pas la dérivation contre les frais.

Parmi ces autres configurations, pensez à celles dont vous pourriez avoir besoin :

![Le diagramme 2 présente d’autres composants vocaux, tels que les numéros Téléphone De Microsoft, les plans de numérotation et le routage des appels, etc.](media/voice-consider-additional-components.png)

| Selon vos besoins | Description |
| :------------|:-------|
| [**Téléphone gestion des nombres**](pstn-connectivity.md#phone-number-management) | La façon d’obtenir et de gérer les numéros de téléphone diffère en fonction de l’option de connectivité PSTN. Lisez cette section si vous avez besoin d’obtenir des numéros de téléphone, de transférer des numéros existants, de vous procurer des numéros de service, etc. |
| [**Routage des appels et plans de numérotation**](pstn-connectivity.md#call-routing-and-dial-plans) | Comment configurer et gérer des plans de numérotation qui traduisent les numéros de téléphone composés dans un autre format (généralement E.164) pour l’autorisation et le routage des appels. Lisez cette section si vous voulez connaître les plans de numérotation et si vous devez spécifier des plans de numérotation pour votre organisation.|
| [**Appels d’urgence**](pstn-connectivity.md#emergency-calling) | La gestion et la configuration des appels d’urgence diffèrent en fonction de l’option de connectivité PSTN. Pour comprendre comment gérer les appels d’urgence pour votre organisation, lisez cette section. |
| [**Routage basé sur l’emplacement pour le routage direct**](pstn-connectivity.md#location-based-routing-for-direct-routing) |Comment utiliser Location-Based routage des réseaux de distribution de données (LBR) pour restreindre le contournement Microsoft Teams utilisateurs en fonction de leur emplacement géographique. Lisez cette section si votre organisation utilise le routage direct à un emplacement qui n’autorise pas la dérivation contre les frais.
| [**Topologie de réseau pour les fonctionnalités vocales dans le cloud**](pstn-connectivity.md#network-topology-for-voice-features) | Si votre organisation déploie le Location-Based routage des appels d’urgence dynamiques ou le routage direct, vous devez configurer les paramètres réseau pour ces fonctionnalités dans Microsoft Teams. Lisez cette section si vous implémentez LBR pour le routage direct, ou si vous implémentez des appels d’urgence dynamiques avec le plan d’appel ou le routage direct. |
| [**Migrer votre solution vocale existante**](#migrate-your-existing-voice-solution-to-teams) | Ce à quoi vous devez penser lors de la migration de votre solution vocale vers Teams.  Lisez cette section si vous migrez d’une solution vocale existante vers Teams. 

> [!Important]
> Cet article se concentre sur les solutions vocales avec Microsoft Teams. Suite à l’retrait de Skype Entreprise Online le 31 juillet 2021, la connectivité PSTN&mdash; entre votre environnement local via Skype Entreprise Server ou Cloud Connector Edition&mdash; et Skype Entreprise Online n’est plus prise en charge. Cet article présente Teams solutions vocales et vous explique comment connecter votre réseau téléphonique local, le cas échéant, à Teams à l’aide de l’Connecter d’opérateur ou du routage direct.


## <a name="phone-system"></a>Système téléphonique

Système téléphonique est la technologie de Microsoft qui permet d’activer le contrôle d’appel et les fonctionnalités de Exchange de branche privée (PBX) dans le cloud Microsoft 365 avec Microsoft Teams.

Système téléphonique fonctionne avec des clients Teams et des périphériques certifiés. Système téléphonique vous permet de remplacer votre système PBX existant par un ensemble de fonctionnalités directement Microsoft 365. 

Les appels entre utilisateurs de votre organisation, quelle que soit leur zone géographique, sont gérés en interne au sein Système téléphonique. Ces appels internes n’ont jamais été passés vers le réseau téléphonique public commuté (PSTN), aussi votre entreprise évite-t-elle de payer des frais d’appel longue distance.

Cet article présente les éléments clés Système téléphonique fonctionnalités principales, ainsi que les décisions de déploiement que vous devrez prendre en compte :

- [Standards automatiques et files d’attente d’appels](#auto-attendants-and-call-queues)
- [Messagerie vocale cloud](#cloud-voicemail)
- [Identité d’appel](#calling-identity)

![Le diagramme 3 indique Téléphone automatique, les requêtes d’appel, la messagerie vocale cloud et l’identité d’appel.](media/phone-system-contains.png)

Pour plus d’informations sur Système téléphonique fonctionnalités et la façon de configurer Système téléphonique, consultez les articles suivants :

- [Les avantages du système téléphonique](here-s-what-you-get-with-phone-system.md)
- [La configuration système téléphonique de votre organisation](setting-up-your-phone-system.md)<br>
  Décrit comment acheter et attribuer Système téléphonique licences, gérer les numéros de téléphone et configurer des crédits de communication pour les numéros gratuits. 

Pour plus d’informations sur la gestion des appareils pris en charge, voir Gérer vos appareils [dans Microsoft Teams](devices/device-management.md) [et Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).


### <a name="auto-attendants-and-call-queues"></a>Automatiquement et files d’attente d’appels

Les attendants automatiques vous permettent de configurer des options de menu pour router les appels en fonction de la saisie de l’appelant. Les files d’attente sont des zones d’attente pour les appelants. Utilisées ensemble, les files d’attente automatiques et les files d’attente d’appels peuvent facilement router les appelants vers la personne ou le service approprié dans votre organisation.

Pour plus d’informations sur les files d’attente et les files d’attente automatiques, consultez les articles suivants :

- [Planifier les appels Teams automatiques et les files d’attente d’appels](plan-auto-attendant-call-queue.md)
- [Configurer un attendant automatique](create-a-phone-system-auto-attendant.md)
- [Créer une file d’attente d’appel](create-a-phone-system-call-queue.md) 
- [Étude de cas Contoso : attendants automatiques et files d’attente d’appels](voice-case-study-call-queues.md)<br>
  Décrit comment une entreprise multinationale fictive, Contoso, a implémenté des files d’attente et des files d’attente automatiques pour leur solution vocale.

### <a name="cloud-voicemail"></a>Messagerie vocale cloud

Messagerie vocale infonuagique, optimisé par les services de messagerie vocale Azure, prend en charge les dépôts de messages vocaux Exchange boîtes aux lettres uniquement. Il ne prend pas en charge les systèmes de courrier tiers. 

La messagerie vocale cloud inclut la transcription des messages vocaux. Elle est activée par défaut pour tous les utilisateurs de votre organisation. Les besoins de votre entreprise peuvent nécessiter la désactivation de la transcription des messages vocaux pour des utilisateurs spécifiques ou pour tous les membres de l’organisation.

Messagerie vocale infonuagique est automatiquement installé et mis en service pour Teams utilisateurs.  

Pour plus d’informations sur Messagerie vocale infonuagique sa configuration, voir les articles suivants :

- [Configurer la Messagerie vocale cloud](set-up-phone-system-voicemail.md)
- [Définir les stratégies de messagerie vocale dans votre organisation](manage-voicemail-policies.md)


### <a name="calling-identity"></a>Identité d’appel

Par défaut, tous les appels sortants utilisent le numéro de téléphone affecté comme identité d’appel (ID de l’appelant). Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel. Pour plus d’informations sur la configuration de l’ID de l’appelant, ou sur la modification ou le blocage de cet ID, voir Définir l’ID d’appelant [d’un utilisateur](set-the-caller-id-for-a-user.md). 

## <a name="public-switched-telephone-network-connectivity-options"></a>Options de connectivité réseau téléphonique public commuté

Système téléphonique fournit des fonctionnalités PBX complètes pour votre organisation. Toutefois, pour permettre aux utilisateurs de passer des appels en dehors de votre organisation, vous devez vous Système téléphonique au réseau téléphonique public commuté (PSTN). Pour vous Système téléphonique au réseau PSTN, vous pouvez choisir l’une des options suivantes :

- [**Système téléphonique’aide d’un forfait d’appels**](pstn-connectivity.md#phone-system-with-calling-plan). Une solution all-in-the-cloud avec Microsoft comme opérateur PSTN.

- [**Système téléphonique votre propre opérateur PSTN à l’aide**](operator-connect-plan.md) de l’opérateur Connecter. Avec l’Connecter opérateur, si votre opérateur existant participe au programme Connecter de l’opérateur Microsoft, il peut gérer le service de mise à niveau des appels R TEAMS. Pour plus d’informations sur les avantages et les exigences de la Connecter opérateur, voir la [Connecter.](operator-connect-plan.md)

- [**Système téléphonique avec votre propre opérateur PSTN en utilisant le routage**](pstn-connectivity.md#phone-system-with-direct-routing) direct pour connecter votre environnement local à Teams.

Vous pouvez choisir une combinaison d’options qui vous permet de concevoir une solution pour un environnement complexe ou de gérer une migration en plusieurs étapes. Vous en savoir plus sur la migration dans la suite de ce processus.

La plupart Système téléphonique fonctionnalités sont identiques quelle que soit l’option de connectivité PSTN que vous choisissez. Il existe toutefois certaines différences de fonctionnalités qui affectent la manière dont vous configurez certaines Système téléphonique, telles que le routage des appels et les appels d’urgence. Pour plus d’informations sur les options de connectivité PSTN et les considérations en matière de configuration, voir [Les options de connectivité PSTN](pstn-connectivity.md).


## <a name="migrate-your-existing-voice-solution-to-teams"></a>Migrer votre solution vocale existante vers Teams

> [!NOTE]
> Pour obtenir des instructions sur la planification d’une solution vocale Teams dans le cadre de votre plan global de mise à niveau vers Teams à partir d’Skype Entreprise Server, consultez les [considérations PSTN](upgrade-to-teams-on-prem-pstn-considerations.md) pour la mise à niveau vers Teams à partir d’Skype Entreprise local.

Pour une organisation qui fait la mise à niveau vers Teams, l’objectif ultime est de déplacer tous les utilisateurs vers le mode TeamsOnly. L’Système téléphonique n’est prise en charge que lorsque l’utilisateur est en mode TeamsOnly. Si vous avez besoin d’informations de base sur la mise à niveau vers Teams, commencez ici :

- [Prise en main de votre mise à niveau de Microsoft Teams](upgrade-start-here.md)
- [À propos du cadre de mise à niveau](upgrade-framework.md)
- [Stratégies de mise à niveau pour les administrateurs informatiques](upgrade-to-teams-on-prem-implement.md)

Lors de la migration de votre solution vocale, quatre scénarios d’appel sont possibles lors du passage en mode TeamsOnly :

- [**Un utilisateur dans Skype Entreprise Online, avec un plan d’appels Microsoft**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans). Lors de la mise à niveau, cet utilisateur continuera à avoir un plan d’appel Microsoft.

- **[Un utilisateur dans Skype Entreprise Online, avec des fonctionnalités vocales](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** en local par le biais de Skype Entreprise version en local ou Cloud Connector. La mise à niveau de l’utilisateur vers Teams doit être coordonnée avec la migration de l’utilisateur vers le routage direct afin de s’assurer que l’utilisateur TeamsOnly dispose de la fonctionnalité PSTN.

- **[Un utilisateur sur Skype Entreprise](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** sur site avec Voix Entreprise, qui passe à la connexion en ligne et maintient la connectivité RSTN sur site. La migration de cet utilisateur vers Teams nécessite le déplacement du compte Skype Entreprise local de l’utilisateur vers le cloud, et la coordination de ce déplacement avec la migration de l’utilisateur vers le routage direct. 

- **[Un utilisateur sur Skype Entreprise site](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** avec Voix Entreprise, qui passe au service en ligne et utilise un plan d’appel Microsoft.  La migration de cet utilisateur vers Teams nécessite le déplacement du compte Skype Entreprise local de l’utilisateur vers le cloud et la coordination du déplacement avec l’un des A) du port du numéro de téléphone de cet utilisateur vers un plan d’appels Microsoft ou B) et l’affectation d’un nouveau numéro d’abonné à partir des régions disponibles.

Pour plus d’informations sur l’implémenter la migration vocale pour chacun de ces scénarios, consultez les articles suivants :

- [Considérations PSTN lors de la mise à niveau vers Teams pour les administrateurs informatiques](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Étude de cas de migration vocale dans Contoso](voice-case-study-overview.md)<br>
  Cette étude de cas décrit la façon dont contoso, une entreprise multinationale fictive, a implémenté une solution vocale Teams pour leur organisation. Il contient les articles suivants :

  - [Teams de mise à niveau](voice-case-study-migration-plan.md)
  - [Système téléphonique options de connectivité PSTN et Système téléphonique’autres options](voice-case-study-phone-system.md)
  - [Implémentation d’un routage basé sur l’emplacement](voice-case-study-location-based-routing.md)
  - [Appels d’urgence](voice-case-study-emergency-calling.md)
  - [Standards automatiques et files d’attente d’appels](voice-case-study-call-queues.md)
  - [Audioconférence](voice-case-study-audio-conferencing.md)
