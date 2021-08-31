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
description: En savoir plus sur les Microsoft Teams fonctionnalités vocales cloud et les décisions de déploiement que vous prendrez pour votre organisation.
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb6796dff27cf078c2f8f1d2d2f1ffc00fddc5e0
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730513"
---
# <a name="plan-your-teams-voice-solution"></a>Planifier votre solution Teams voix 

Cet article vous aide à déterminer la solution Microsoft Voice adaptée à votre organisation. Une fois que vous avez décidé, l’article fournit une feuille de route vers le contenu qui vous permettra d’implémenter la solution que vous avez choisie.

Vous souhaitez peut-être une solution plus simple &mdash; Système téléphonique’aide de Forfait d’appels. Il s’agit de la solution dans le cloud de Microsoft qui fournit des fonctionnalités de Exchange de branche privée (PBX) et des appels vers le réseau téléphonique commuté (PSTN), comme illustré dans le diagramme suivant. Avec cette solution, Microsoft est votre opérateur PSTN.

![Le diagramme 1 montre les Système téléphonique’aide d’un plan d’appels.](media/voice-solutions-simple.png)

Si vous répondez oui aux questions suivantes, alors Système téléphonique’aide du plan d’appels est la solution adaptée à vos questions :

- Le forfait d’appels est disponible dans votre région.
- Vous n’avez pas besoin de conserver votre opérateur PSTN actuel.
- Vous voulez utiliser l’accès géré par Microsoft au réseau PSTN.

Toutefois, votre situation peut être plus complexe. Par exemple, vous pouvez avoir des bureaux dans des emplacements où le plan d’appels n’est pas disponible. Vous pouvez également avoir besoin d’une solution combinée qui prend en charge un déploiement complexe et multi-national avec des exigences différentes pour différents emplacements géographiques. Microsoft prend en charge une combinaison de solutions : 

- Système téléphonique forfait d’appels
- Système téléphonique votre propre opérateur PSTN avec l’opérateur Connecter (actuellement disponible uniquement en **prévisualisation publique)**
- Système téléphonique votre propre opérateur PSTN avec un routage direct
- Solution combinée qui utilise Système téléphonique plan d’appels, une Système téléphonique’opérateur Connecter et/ou une Système téléphonique de routage direct


## <a name="what-do-you-need-to-read"></a>Que devez-vous lire ?

**Obligatoire pour tous.** Certaines des sections de cet article concernent toutes les organisations. Par exemple, tout le monde doit lire les informations Système téléphonique comprendre les options de connexion au réseau téléphonique public commuté (PSTN). 


| Obligatoire pour tous | Description |
| :------------|:-------|
| [**Système téléphonique**](#phone-system) | La technologie de Microsoft qui permet d’activer le contrôle des appels et les fonctionnalités Exchange de branche privée (PBX) dans le cloud Microsoft 365'Microsoft Teams. |
| [**Options de connectivité de réseau téléphonique commuté (PSTN)**](#public-switched-telephone-network-connectivity-options) | Choix entre l’utilisation de Microsoft comme opérateur de téléphonie ou la connexion de votre propre opérateur téléphonique à Microsoft Teams à l’aide de l’opérateur Connecter ou du routage direct. Combinées avec Système téléphonique, les options de connectivité PSTN permettent à vos utilisateurs de effectuer des appels téléphoniques dans le monde entier.|

**En fonction de vos besoins.** Certaines des sections de cet article et des articles connexes sont pertinentes en fonction de votre déploiement et des exigences existantes. Par exemple, un Location-Based routage n’est nécessaire que pour les clients de routage direct dans des emplacements géographiques qui n’autorisent pas la dérivation contre les frais.

Prenez en compte les configurations supplémentaires qui peuvent vous être nécessaires :

![Le diagramme 2 présente d’autres composants vocaux, tels que Téléphone de Microsoft, les plans de numérotation et le routage des appels, etc.](media/voice-consider-additional-components.png)

| Selon vos besoins | Description |
| :------------|:-------|
| [**Téléphone gestion des nombres**](pstn-connectivity.md#phone-number-management) | La façon d’obtenir et de gérer les numéros de téléphone diffère selon votre option de connectivité PSTN. Lisez cette section si vous avez besoin d’obtenir des numéros de téléphone, de transférer des numéros existants, de vous procurer des numéros de service, etc. |
| [**Routage des appels et plans de numérotation**](pstn-connectivity.md#call-routing-and-dial-plans) | Comment configurer et gérer des plans de numérotation qui traduisent les numéros de téléphone composés dans un autre format (généralement E.164) pour l’autorisation et le routage des appels. Lisez cette section si vous avez besoin de comprendre ce que sont les plans de numérotation et si vous devez spécifier des plans de numérotation pour votre organisation.|
| [**Appels d’urgence**](pstn-connectivity.md#emergency-calling) | La gestion et la configuration des appels d’urgence diffèrent en fonction de l’option de connectivité PSTN. Pour comprendre comment gérer les appels d’urgence pour votre organisation, lisez cette section. |
| [**Routage basé sur l’emplacement pour le routage direct**](pstn-connectivity.md#location-based-routing-for-direct-routing) |Comment utiliser Location-Based routage des réseaux de distribution de données (LBR) pour restreindre la dérivation contre les Microsoft Teams en fonction de leur emplacement géographique. Lisez cette section si votre organisation utilise le routage direct à un emplacement qui n’autorise pas la dérivation contre les frais.
| [**Topologie de réseau pour les fonctionnalités vocales cloud**](pstn-connectivity.md#network-topology-for-voice-features) | Si votre organisation déploie Location-Based routage des appels d’urgence dynamiques ou le routage direct, vous devez configurer des paramètres réseau pour les utiliser avec ces fonctionnalités dans Microsoft Teams. Lisez cette section si vous implémentez LBR pour le routage direct, ou si vous implémentez des appels d’urgence dynamiques avec le plan d’appel ou le routage direct. |
| [**Migrer votre solution vocale existante**](#migrate-your-existing-voice-solution-to-teams) | Ce à quoi vous devez penser lors de la migration de votre solution vocale vers Teams.  Lisez cette section si vous migrez d’une solution vocale existante vers Teams. 

> [!Important]
> Cet article se concentre sur les solutions vocales avec Microsoft Teams. Bien que les solutions avec Skype Entreprise Online soient toujours disponibles, il est important de comprendre que Skype Entreprise Online sera retiré le 31 juillet 2021.  Après cette date, le service Skype Entreprise Online ne sera plus accessible. Par ailleurs, la connectivité PSTN entre votre environnement local, que ce soit via Skype Entreprise Server ou la version Cloud Connector et Skype Entreprise Online ne sera plus prise en &mdash; &mdash; charge. Cet article présente Teams solutions vocales et vous explique comment connecter votre réseau téléphonique local, le cas échéant, à Teams à l’aide d’un routage direct ou d’un opérateur Connecter.


## <a name="phone-system"></a>Système téléphonique

Système téléphonique est la technologie de Microsoft qui permet d’activer le contrôle d’appel et les fonctionnalités de Exchange de branche privée (PBX) dans le cloud Microsoft 365 avec Microsoft Teams.

Système téléphonique fonctionne avec des Teams ou Skype Entreprise clients et appareils certifiés. Système téléphonique vous permet de remplacer votre système PBX existant par un ensemble de fonctionnalités directement Microsoft 365. 

Les appels entre utilisateurs de votre organisation sont gérés en interne au sein Système téléphonique et ne sont jamais passés au réseau téléphonique public commuté (PSTN). Cela s’applique aux appels entre utilisateurs de votre organisation situés dans différentes zones géographiques, en supprimant les coûts longue distance sur ces appels internes.

Cet article présente les éléments clés Système téléphonique fonctionnalités principales, ainsi que les décisions de déploiement que vous devrez prendre en compte :

- [Standards automatiques et files d’attente d’appels](#auto-attendants-and-call-queues)
- [Messagerie vocale cloud](#cloud-voicemail)
- [Identité d’appel](#calling-identity)

![Le diagramme 3 indique Téléphone automatique, les requêtes d’appel, la messagerie vocale cloud et l’identité d’appel.](media/phone-system-contains.png)

Pour plus d’informations sur Système téléphonique fonctionnalités de contrôle et la manière de configurer Système téléphonique, consultez les articles suivants :

- [Les avantages du système téléphonique](here-s-what-you-get-with-phone-system.md)
- [La configuration système téléphonique de votre organisation](setting-up-your-phone-system.md)<br>
  Décrit comment acheter et attribuer Système téléphonique licences, gérer les numéros de téléphone et configurer des crédits de communication pour les numéros gratuits. 

Pour plus d’informations sur la gestion des appareils pris en charge, voir Gérer vos appareils [dans Microsoft Teams](devices/device-management.md) et [Teams Marketplace.](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


### <a name="auto-attendants-and-call-queues"></a>Attendants automatiques et files d’attente d’appels

Les attendants automatiques vous permettent de configurer des options de menu pour router les appels en fonction de la saisie de l’appelant. Les files d’attente sont des zones d’attente pour les appelants. Utilisées ensemble, les files d’attente automatiques et les files d’attente d’appels peuvent facilement router les appelants vers la personne ou le service approprié dans votre organisation.

Pour plus d’informations sur les files d’attente et les files d’attente automatiques, consultez les articles suivants :

- [Planifier la mise Teams automatiques et des files d’attente d’appels](plan-auto-attendant-call-queue.md)
- [Configurer un attendant automatique](create-a-phone-system-auto-attendant.md)
- [Créer une file d’attente d’appel](create-a-phone-system-call-queue.md) 
- [Étude de cas Contoso : attendants automatiques et files d’attente d’appels](voice-case-study-call-queues.md)<br>
  Décrit comment une entreprise multinationale fictive, Contoso, a implémenté des files d’attente automatiques et des files d’attente pour leur solution vocale.

### <a name="cloud-voicemail"></a>Messagerie vocale cloud

Messagerie vocale infonuagique, optimisé par les services de messagerie vocale Azure, prend en charge les dépôts de messages vocaux Exchange boîtes aux lettres uniquement. Il ne prend pas en charge les systèmes de courrier tiers. 

La messagerie vocale cloud inclut la transcription des messages vocaux. Elle est activée par défaut pour tous les utilisateurs de votre organisation. Les besoins de votre entreprise peuvent nécessiter la désactivation de la transcription des messages vocaux pour des utilisateurs spécifiques ou pour tous les membres de l’organisation.

Pour les utilisateurs en ligne uniquement, Messagerie vocale infonuagique est automatiquement installé et mis en service pour les utilisateurs une fois qu’une licence Système téléphonique leur est attribuée. Pour Système téléphonique utilisateurs qui ont Exchange boîte aux lettres, vous devez effectuer des étapes de configuration supplémentaires. 

Pour plus d’informations sur Messagerie vocale infonuagique sa configuration, voir les articles suivants :

- [Configurer la Messagerie vocale cloud](set-up-phone-system-voicemail.md)
- [Définir les stratégies de messagerie vocale dans votre organisation](manage-voicemail-policies.md)


### <a name="calling-identity"></a>Identité d’appel

Par défaut, tous les appels sortants utilisent le numéro de téléphone affecté comme identité d’appel (ID de l’appelant). Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel. Pour plus d’informations sur la configuration de l’ID de l’appelant, ou sur la modification ou le blocage de cet ID, voir Définir l’ID d’appelant [d’un utilisateur.](set-the-caller-id-for-a-user.md) 

## <a name="public-switched-telephone-network-connectivity-options"></a>Options de connectivité réseau téléphonique public commuté

Système téléphonique fournit des fonctionnalités PBX complètes pour votre organisation. Toutefois, pour permettre aux utilisateurs de passer des appels en dehors de votre organisation, vous devez vous Système téléphonique au réseau téléphonique public commuté (PSTN). Pour vous Système téléphonique au réseau PSTN, vous pouvez choisir l’une des options suivantes :

- [**Système téléphonique’aide d’un forfait d’appels.**](pstn-connectivity.md#phone-system-with-calling-plan) Une solution all-in-the-cloud avec Microsoft comme opérateur PSTN.

- [**Système téléphonique votre propre opérateur PSTN à**](operator-connect-plan.md)l’aide de l’opérateur Connecter, actuellement disponible uniquement en **prévisualisation publique.**  Avec la Connecter opérateur, si votre opérateur existant participe au programme Connecter de l’opérateur Microsoft, il peut gérer le service de mise à niveau des appels R TEAMS. Pour plus d’informations sur les avantages et les exigences de la Connecter opérateur, et pour obtenir la liste des opérateurs participant à ce programme, consultez la liste des opérateurs [Connecter.](operator-connect-plan.md)

- Système téléphonique avec votre propre opérateur [**PSTN en**](pstn-connectivity.md#phone-system-with-direct-routing) utilisant le routage direct pour connecter votre environnement local à Teams.

Vous pouvez également choisir une combinaison d’options qui vous permet de concevoir une solution pour un environnement complexe ou de gérer une migration en plusieurs étapes (en savoir plus sur la migration ultérieure).

La plupart Système téléphonique fonctionnalités sont identiques quelle que soit l’option de connectivité PSTN que vous choisissez. Il existe toutefois certaines différences de fonctionnalités qui affectent la manière dont vous configurez certaines Système téléphonique, telles que le routage des appels et les appels d’urgence. Pour plus d’informations sur les options de connectivité PSTN et sur ces considérations concernant la configuration, voir les options de [connectivité PSTN.](pstn-connectivity.md)


## <a name="migrate-your-existing-voice-solution-to-teams"></a>Migrer votre solution vocale existante vers Teams

> [!NOTE]
> Pour obtenir des instructions sur la planification d’une solution vocale Teams dans le cadre de votre plan global de mise à niveau vers Teams Skype Entreprise Server à partir d’Skype Entreprise Server, consultez les [considérations PSTN](upgrade-to-teams-on-prem-pstn-considerations.md)pour la mise à niveau vers Teams à partir d’Skype Entreprise local.

Pour une organisation qui fait la mise à niveau vers Teams, l’objectif ultime est de déplacer tous les utilisateurs vers le mode TeamsOnly. L’Système téléphonique avec Teams n’est prise en charge que lorsque l’utilisateur est en mode TeamsOnly. Si vous avez besoin d’informations de base sur la mise à niveau vers Teams, commencez ici :

- [Prise en main de votre mise à niveau de Microsoft Teams](upgrade-start-here.md)
- [À propos du cadre de mise à niveau](upgrade-framework.md)
- [Stratégies de mise à niveau pour les administrateurs informatiques](upgrade-to-teams-on-prem-implement.md)

Lors de la migration de votre solution vocale, quatre scénarios d’appel sont possibles lors du passage en mode TeamsOnly :

- [**Un utilisateur dans Skype Entreprise Online, avec un plan d’appels Microsoft.**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans) Lors de la mise à niveau, cet utilisateur continuera à avoir un plan d’appel Microsoft.

- Un utilisateur dans Skype Entreprise Online, avec des **[fonctionnalités vocales](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** en local via Skype Entreprise version Skype Entreprise version cloud connector. La mise à niveau de l’utilisateur vers Teams doit être coordonnée avec la migration de l’utilisateur vers le routage direct afin de s’assurer que l’utilisateur TeamsOnly dispose des fonctionnalités PSTN.

- Un utilisateur sur Skype Entreprise sur site avec Voix Entreprise, qui passe à la connexion en ligne et maintient la connectivité **[](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)RSTN sur site.** La migration de cet utilisateur vers Teams nécessite le déplacement du compte Skype Entreprise local de l’utilisateur vers le cloud, et la coordination de ce déplacement avec la migration de l’utilisateur vers le routage direct. 

- Un utilisateur sur Skype Entreprise site avec Voix Entreprise, qui passe au service en ligne et utilise un **[](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)plan d’appel Microsoft.**  La migration de cet utilisateur vers Teams nécessite le déplacement du compte Skype Entreprise local de l’utilisateur vers le cloud et la coordination du déplacement avec l’un des A) du port de ce numéro de téléphone vers un plan d’appels Microsoft ou B) et l’affectation d’un nouveau numéro d’abonné à partir des régions disponibles.

Pour plus d’informations sur l’implémentation de votre migration vocale pour chacun de ces scénarios, notamment sur la nécessité de configurer une connectivité hybride et la migration des utilisateurs avec la fonctionnalité vocale sur site vers le routage direct, voir les &mdash; articles suivants &mdash; :

- [Considérations concernant les réseaux PSTN lors de la mise à niveau vers Teams pour les administrateurs informatiques](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Étude de cas de migration vocale dans Contoso](voice-case-study-overview.md)<br>
  Cette étude de cas décrit la façon dont contoso, une entreprise multinationale fictive, a implémenté une solution vocale Teams pour leur organisation. Il contient les articles suivants :

  - [Teams de mise à niveau](voice-case-study-migration-plan.md)
  - [Système téléphonique options de connectivité PSTN](voice-case-study-phone-system.md)
  - [Implémentation d’un routage basé sur l’emplacement](voice-case-study-location-based-routing.md)
  - [Appels d’urgence](voice-case-study-emergency-calling.md)
  - [Standards automatiques et files d’attente d’appels](voice-case-study-call-queues.md)
  - [Audioconférence](voice-case-study-audio-conferencing.md)
