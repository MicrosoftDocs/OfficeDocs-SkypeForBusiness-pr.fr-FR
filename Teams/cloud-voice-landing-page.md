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
- highpri
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: En savoir plus sur les fonctionnalités de voix cloud de Microsoft Teams et les décisions de déploiement que vous prendrez pour votre organisation.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba61d1ccbaeda26834b31a321aebfccbe23243
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999349"
---
# <a name="plan-your-teams-voice-solution"></a>Planifier votre solution vocale Teams

Cet article vous aide à déterminer la solution vocale Microsoft adaptée à votre organisation. Une fois que vous avez décidé, l’article fournit une feuille de route pour le contenu qui vous permettra d’implémenter la solution que vous avez choisie.

Vous souhaiterez peut-être le système téléphonique de solution&mdash;le plus simple avec forfait d’appels. Cette option est la solution tout-dans-le-cloud de Microsoft qui fournit des fonctionnalités PbX (Private Branch Exchange) et des appels au réseau téléphonique commuté public (RTC), comme illustré dans le diagramme suivant. Avec cette solution, Microsoft est votre opérateur RTC.

![Le diagramme 1 montre le système téléphonique avec forfait d’appels.](media/voice-solutions-simple.png)

Si vous répondez oui à ce qui suit, le système téléphonique avec forfait d’appels est la solution qui vous convient :

- Le forfait d’appels est disponible dans votre région.
- Vous n’avez pas besoin de conserver votre opérateur RTC actuel.
- Vous souhaitez utiliser l’accès géré par Microsoft au rtc.

Toutefois, votre situation peut être plus complexe. Par exemple, vous pouvez avoir des bureaux dans des emplacements où le forfait d’appels n’est pas disponible. Vous pouvez également avoir besoin d’une solution combinée qui prend en charge un déploiement multi-national complexe, avec des exigences différentes pour différents emplacements géographiques. Microsoft prend en charge une combinaison de solutions :

- Système téléphonique avec forfait d’appels
- Système téléphonique avec votre propre opérateur RTC avec Operator Connect
- Système téléphonique avec votre propre opérateur mobile RTC avec Fournisseur de connectivité mobile (préversion publique)
- Système téléphonique avec votre propre opérateur RTC avec routage direct
- Solution combinée qui utilise le système téléphonique avec forfait d’appels, le système téléphonique avec operator connect et/ou le système téléphonique avec routage direct

Pour obtenir un résumé visuel de toutes les options de solution vocale, consultez l’affiche des solutions vocales.

[![Affiche Microsoft Voice Solutions.](media/microsoft-voice-solutions-thumb.png)](https://download.microsoft.com/download/4/3/5/435cd4e9-ca56-4fd1-acb6-d1fda7952320/microsoft-voice-solutions.pdf) <br> [fichier PDF ;](https://download.microsoft.com/download/4/3/5/435cd4e9-ca56-4fd1-acb6-d1fda7952320/microsoft-voice-solutions.pdf) <br>[Visio](https://download.microsoft.com/download/7/5/c/75c13012-e20c-48bd-a6dd-ea49d1a3420d/microsoft-voice-solutions.vsdx) 
<br>

>[!NOTE]
>Si vous êtes une petite ou moyenne entreprise (300 personnes ou moins), Microsoft regroupe désormais le système téléphonique avec un forfait d’appels nationaux. Pour plus d’informations, consultez les [conseils du système téléphonique pour les petites et moyennes entreprises](/microsoftteams/business-voice/whats-business-voice) afin de vous aider à planifier, configurer et gérer votre solution vocale.

## <a name="what-do-you-need-to-read"></a>Que devez-vous lire ?

**Obligatoire pour tous.** Certaines des sections de cet article concernent toutes les organisations. Par exemple, tout le monde doit en savoir plus sur le système téléphonique et comprendre les options de connexion au réseau téléphonique commuté (RTC).


| Obligatoire pour tous | Description |
| :------------|:-------|
| [**Système téléphonique**](#phone-system) | Technologie de Microsoft permettant d’activer le contrôle des appels et les fonctionnalités PbX (Private Branch Exchange) dans le cloud Microsoft 365 avec Microsoft Teams. |
| [**Options de connectivité RTC (Public Switched Telephone Network)**](#public-switched-telephone-network-connectivity-options) | Choisissez Microsoft comme opérateur de téléphonie ou connectez votre propre opérateur de téléphonie à Microsoft Teams à l’aide de l’opérateur Connect ou du routage direct. Combinées au système téléphonique, les options de connectivité RTC permettent à vos utilisateurs d’effectuer des appels téléphoniques dans le monde entier.|

**En fonction de vos besoins.** Certaines des sections de cet article et des articles connexes sont pertinentes en fonction de votre déploiement et de vos besoins existants. Par exemple, Location-Based routage n’est requis que pour les clients de routage direct dans des emplacements géographiques qui n’autorisent pas le contournement des péages.

Tenez compte des autres configurations dont vous pourriez avoir besoin :

![Le diagramme 2 montre d’autres composants vocaux, tels que les numéros de téléphone de Microsoft, les plans de numérotation et le routage des appels, etc.](media/voice-consider-additional-components.png)

| En fonction de vos besoins | Description |
| :------------|:-------|
| [**Gestion des numéros de téléphone**](pstn-connectivity.md#phone-number-management) | L’obtention et la gestion des numéros de téléphone diffèrent en fonction de votre option de connectivité RTC. Lisez cette section si vous avez besoin d’obtenir des numéros de téléphone, de transférer des numéros existants, d’obtenir des numéros de service, et ainsi de suite. |
| [**Plans de routage et de numérotation des appels**](pstn-connectivity.md#call-routing-and-dial-plans) | Comment configurer et gérer des plans de numérotation qui traduisent les numéros de téléphone composés dans un autre format (généralement le format E.164) pour l’autorisation d’appel et le routage des appels. Lisez cette section si vous devez comprendre ce que sont les plans de numérotation et si vous devez spécifier des plans de numérotation pour votre organisation.|
| [**Appel d’urgence**](pstn-connectivity.md#emergency-calling) | La gestion et la configuration des appels d’urgence diffèrent en fonction de votre option de connectivité RTC. Lisez cette section si vous devez comprendre comment gérer les appels d’urgence pour votre organisation. |
| [**Routage basé sur l’emplacement pour le routage direct**](pstn-connectivity.md#location-based-routing-for-direct-routing) |Comment utiliser Location-Based Routage (LBR) pour limiter le contournement des péages pour les utilisateurs de Microsoft Teams en fonction de leur emplacement géographique. Lisez cette section si votre organisation utilise le routage direct à un emplacement qui n’autorise pas le contournement des péages.
| [**Topologie de réseau pour les fonctionnalités de voix cloud**](pstn-connectivity.md#network-topology-for-voice-features) | Si votre organisation déploie Location-Based Routage (LBR) pour le routage direct ou les appels d’urgence dynamiques, vous devez configurer les paramètres réseau de ces fonctionnalités dans Microsoft Teams. Lisez cette section si vous implémentez LBR pour le routage direct, ou si vous implémentez des appels d’urgence dynamiques avec le plan d’appel ou le routage direct. |
| [**Migrer votre solution vocale existante**](#migrate-your-existing-voice-solution-to-teams) | Ce à quoi vous devez penser lors de la migration de votre solution vocale vers Teams.  Lisez cette section si vous migrez d’une solution vocale existante vers Teams. 

> [!Important]
> Cet article se concentre sur les solutions vocales avec Microsoft Teams. En raison de la mise hors service de Skype Entreprise Online le 31 juillet 2021, la connectivité RTC entre votre environnement&mdash;local via Skype Entreprise Server ou Cloud Connector Edition&mdash;et Skype Entreprise Online n’est plus prise en charge. Cet article présente les solutions vocales Teams et la façon dont vous pouvez connecter votre réseau de téléphonie local, si nécessaire, à Teams à l’aide de l’opérateur Connect ou du routage direct.


## <a name="phone-system"></a>Système téléphonique

Le système téléphonique est la technologie de Microsoft permettant d’activer le contrôle des appels et les fonctionnalités PBX (Private Branch Exchange) dans le cloud Microsoft 365 avec Microsoft Teams.

Le système téléphonique fonctionne avec les clients Teams et les appareils certifiés. Le système téléphonique vous permet de remplacer votre système PBX existant par un ensemble de fonctionnalités directement fournies à partir de Microsoft 365. 

Les appels entre les utilisateurs de votre organisation, quelle que soit la zone géographique, sont gérés en interne dans le système téléphonique. Ces appels internes n’accédant jamais au réseau téléphonique commuté (RTC), votre entreprise évite donc les frais de longue distance.

Cet article présente les fonctionnalités et fonctionnalités clés du système téléphonique suivantes, ainsi que les décisions de déploiement à prendre en compte :

- [Standards automatiques et files d’attente d’appels](#auto-attendants-and-call-queues)
- [Messagerie vocale cloud](#cloud-voicemail)
- [Identité d’appel](#calling-identity)

![Le diagramme 3 montre que le système téléphonique contient les standards automatiques et les requêtes d’appel, la messagerie vocale cloud et l’identité d’appel.](media/phone-system-contains.png)

Pour plus d’informations sur toutes les fonctionnalités du système téléphonique et sur la configuration du système téléphonique, consultez les articles suivants :

- [Les avantages du système téléphonique](here-s-what-you-get-with-phone-system.md)
- [La configuration système téléphonique de votre organisation](setting-up-your-phone-system.md)<br>
  Décrit comment acheter et attribuer des licences système téléphonique, gérer les numéros de téléphone et configurer des crédits de communication pour les numéros gratuits. 

Pour plus d’informations sur la gestion des appareils pris en charge, consultez [Gérer vos appareils dans Microsoft Teams](devices/device-management.md) et [la Place de marché Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).


### <a name="auto-attendants-and-call-queues"></a>Standards automatiques et files d’attente d’appels

Les standards automatiques vous permettent de configurer des options de menu pour router les appels en fonction de l’entrée de l’appelant. Les files d’attente d’appels sont des zones d’attente pour les appelants. Utilisés ensemble, les standards automatiques et les files d’attente d’appels peuvent facilement acheminer les appelants vers la personne ou le service approprié dans votre organisation.

Pour plus d’informations sur les standards automatiques et les files d’attente d’appels, consultez les articles suivants :

- [Planifier les standards automatiques teams et les files d’attente d’appels](plan-auto-attendant-call-queue.md)
- [Configurer un standard automatique](create-a-phone-system-auto-attendant.md)
- [Créer une file d’attente d’appel](create-a-phone-system-call-queue.md) 
- [Étude de cas Contoso : Standards automatiques et files d’attente d’appels](voice-case-study-call-queues.md)<br>
  Décrit comment une société multinationale fictive, Contoso, a implémenté des standards automatiques et des files d’attente d’appels pour leur solution vocale.

### <a name="cloud-voicemail"></a>Messagerie vocale cloud

Messagerie vocale infonuagique, optimisée par les services de messagerie vocale Azure, prend uniquement en charge les dépôts de messagerie vocale dans les boîtes aux lettres Exchange. Il ne prend pas en charge les systèmes de messagerie tiers. 

La messagerie vocale cloud inclut la transcription des messages vocaux. Elle est activée par défaut pour tous les utilisateurs de votre organisation. Vos besoins professionnels peuvent nécessiter la désactivation de la transcription de messages vocaux pour des utilisateurs spécifiques ou pour tous les membres de l’organisation.

Messagerie vocale infonuagique est automatiquement configuré et configuré pour les utilisateurs Teams.  

Pour plus d’informations sur Messagerie vocale infonuagique et sa configuration, consultez les articles suivants :

- [Configurer la Messagerie vocale cloud](set-up-phone-system-voicemail.md)
- [Définir des stratégies de messagerie vocale dans votre organisation](manage-voicemail-policies.md)


### <a name="calling-identity"></a>Identité d’appel

Par défaut, tous les appels sortants utilisent le numéro de téléphone affecté comme identité d’appel (ID d’appelant). Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel. Pour plus d’informations sur la configuration de l’ID d’appelant ou pour modifier ou bloquer l’ID de l’appelant, consultez [Définir l’ID de l’appelant pour un utilisateur](set-the-caller-id-for-a-user.md). 

## <a name="public-switched-telephone-network-connectivity-options"></a>Options de connectivité réseau téléphonique commutée publique

Le système téléphonique fournit des fonctionnalités PBX complètes pour votre organisation. Toutefois, pour permettre aux utilisateurs de passer des appels en dehors de votre organisation, vous devez connecter le système téléphonique au réseau téléphonique commuté (RTC). Pour connecter le système téléphonique au rtc, vous pouvez choisir l’une des options suivantes :

- [**Système téléphonique avec forfait d’appels**](pstn-connectivity.md#phone-system-with-calling-plan). Une solution tout-dans-le-cloud avec Microsoft comme opérateur RTC.

- [**Système téléphonique avec votre propre opérateur RTC à l’aide de Operator Connect**](operator-connect-plan.md). Avec Operator Connect, si votre opérateur existant participe au programme Microsoft Operator Connect, il peut gérer le service pour l’appel RTC à Teams. 

- [**Système téléphonique avec votre propre opérateur mobile RTC à l’aide de Fournisseur de connectivité mobile**](operator-connect-mobile-plan.md) **version d’évaluation publique**. Avec Fournisseur de connectivité mobile, si votre opérateur existant participe au programme Microsoft Fournisseur de connectivité mobile, il peut gérer le service pour l’utilisation de numéros de téléphone mobile compatibles SIM avec Teams. 

- [**Système téléphonique avec votre propre opérateur RTC à l’aide du routage direct**](pstn-connectivity.md#phone-system-with-direct-routing) pour connecter votre environnement local à Teams.


Vous pouvez choisir une combinaison d’options, ce qui vous permet de concevoir une solution pour un environnement complexe ou de gérer une migration en plusieurs étapes. Vous en apprendrez plus sur la migration ultérieurement.

La plupart des fonctionnalités du système téléphonique sont les mêmes, quelle que soit l’option de connectivité RTC que vous choisissez. Toutefois, certaines différences de fonctionnalités affectent la façon dont vous configurez certaines fonctionnalités du système téléphonique, telles que le routage des appels et les appels d’urgence. Pour plus d’informations sur les options de connectivité RTC et les considérations de configuration, consultez les [options de connectivité RTC](pstn-connectivity.md).


## <a name="migrate-your-existing-voice-solution-to-teams"></a>Migrer votre solution vocale existante vers Teams

> [!NOTE]
> Pour obtenir des conseils sur la planification d’une solution vocale Teams dans le cadre de votre plan global de mise à niveau vers Teams à partir de Skype Entreprise Server, consultez [les considérations RTC relatives à la mise à niveau vers Teams à partir de Skype Entreprise localement](upgrade-to-teams-on-prem-pstn-considerations.md).

Pour une organisation qui effectue une mise à niveau vers Teams, l’objectif ultime est de déplacer tous les utilisateurs vers le mode TeamsOnly. L’utilisation du système téléphonique est prise en charge uniquement lorsque l’utilisateur est en mode TeamsOnly. Si vous avez besoin d’informations de base sur la mise à niveau vers Teams, commencez ici :

- [Prise en main de votre mise à niveau de Microsoft Teams](upgrade-start-here.md)
- [À propos du cadre de mise à niveau](upgrade-framework.md)
- [Stratégies de mise à niveau pour les administrateurs informatiques](upgrade-to-teams-on-prem-implement.md)

Lors de la migration de votre solution vocale, il existe quatre scénarios d’appel possibles lors du passage en mode TeamsOnly :

- [**Un utilisateur dans Skype Entreprise Online, avec un plan d’appel Microsoft**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans). Lors de la mise à niveau, cet utilisateur continuera d’avoir un plan d’appel Microsoft.

- **[Un utilisateur dans Skype Entreprise Online, avec des fonctionnalités vocales locales](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) via Skype Entreprise édition locale ou Cloud Connector**. La mise à niveau de l’utilisateur vers Teams doit être coordonnée avec la migration de l’utilisateur vers le routage direct pour garantir que l’utilisateur TeamsOnly dispose des fonctionnalités RTC.

- **[Utilisateur en Skype Entreprise local avec Téléphonie –  Grandes entreprises](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), qui passera en ligne et conservera la connectivité RTC locale**. La migration de cet utilisateur vers Teams nécessite le déplacement du compte Skype Entreprise local de l’utilisateur vers le cloud et la coordination de ce déplacement avec la migration de l’utilisateur vers le routage direct. 

- **[Un utilisateur dans Skype Entreprise local avec Téléphonie –  Grandes entreprises](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), qui passera en ligne et utilisera un plan d’appel Microsoft**.  La migration de cet utilisateur vers Teams nécessite le déplacement du compte Skype Entreprise local de l’utilisateur vers le cloud, et la coordination de ce déplacement avec le port du numéro de téléphone de cet utilisateur vers un plan d’appel Microsoft ou B) en affectant un nouveau numéro d’abonné à partir des régions disponibles.

Pour plus d’informations sur la façon d’implémenter votre migration vocale pour chacun de ces scénarios, consultez les articles suivants :

- [Considérations relatives au RTC lors de la mise à niveau vers Teams , pour les administrateurs informatiques](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Étude de cas de migration vocale Contoso](voice-case-study-overview.md)<br>
  L’étude de cas décrit comment une société multinationale fictive, Contoso, a implémenté une solution de voix Teams pour son organisation. Il contient les articles suivants :

  - [Plan de mise à niveau teams](voice-case-study-migration-plan.md)
  - [Options de connectivité système téléphonique et RTC](voice-case-study-phone-system.md)
  - [Implémentation du routage basé sur l’emplacement](voice-case-study-location-based-routing.md)
  - [Appel d’urgence](voice-case-study-emergency-calling.md)
  - [Standards automatiques et files d’attente d’appels](voice-case-study-call-queues.md)
  - [Audioconférence](voice-case-study-audio-conferencing.md)
