---
title: Appel vocal dans le nuage dans Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: Page d’accueil pour le déploiement de voix dans le nuage dans les équipes
appliesto:
- Microsoft Teams
ms.openlocfilehash: 47c534eba93c6f5af21a75fa20b5015fac00c674
ms.sourcegitcommit: 6949c957224949ccc6f5958d3c84294d382ee405
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2019
ms.locfileid: "31914611"
---
# <a name="cloud-voice-in-microsoft-teams"></a>Appel vocal dans le nuage dans Microsoft Teams

Vous avez terminé la [Prise en main](get-started-with-teams-quick-start.md). Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation. Peut-être que vous avez déployé la [conférence & de réunions](deploy-meetings-microsoft-teams-landing-page.md). Vous êtes maintenant prêt à ajouter des fonctionnalités de voix dans le nuage pour vos utilisateurs. 

Nuage voix fournit des fonctionnalités d’autocommutateur privé (PBX) et des options pour la connexion à la Public téléphone réseau commuté (RTC).

Cet article vous aide à déterminer si vous devez modifier les paramètres par défaut dans le nuage voix, basé sur le profil de votre organisation et des besoins de l’entreprise, il vous guide dans chaque modification. Nous avons divisé en deux groupes, en commençant par l’ensemble de [modifications que vous êtes susceptible de rendre](#core-deployment-decisions)les paramètres. Le deuxième groupe inclut les [paramètres supplémentaires](#additional-deployment-decisions) que vous souhaiterez peut-être configurer, en fonction des besoins de votre organisation.

Nous vous recommandons de toutes les organisations fonctionnent par le biais de décisions clés puis, si votre organisation a des exigences supplémentaires, passez en revue le contenu suivant.



## <a name="learn-more-about-cloud-voice"></a>En savoir plus sur la voix dans le nuage

Les articles suivants fournissent plus d’informations sur le déploiement et l’utilisation des fonctionnalités de voix dans le nuage dans les équipes :

- [Système téléphonique dans Office 365](what-is-phone-system-in-office-365.md)
- [Système téléphonique avec les Plans d’appel](calling-plan-landing-page.md)
- [Routage direct via le système téléphonique](direct-routing-landing-page.md)
- [Déploiement de la fonctionnalité vocale cloud](cloud-voice-deployment.md)
- [Détails sur les solutions téléphoniques Microsoft Telephony](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- Regarder la session suivante pour en savoir plus sur le système téléphonique : [Introduction au système téléphonique dans les équipes Microsoft](https://aka.ms/teams-phone-system)


## <a name="core-deployment-decisions"></a>Décisions liées au déploiement Core

Voici les paramètres que la plupart des organisations veulent modifier (si les paramètres par défaut de Teams ne fonctionnent pas pour l’organisation).

## <a name="phone-system-office-365"></a>Système téléphonique (Office 365)

Système téléphonique est la technologie de Microsoft pour activer le contrôle d’appel et les fonctionnalités d’autocommutateur privé (PBX) dans le nuage Office 365. Système téléphonique vous permet de remplacer votre système autocommutateur privé (PBX) existant avec un ensemble de fonctionnalités remis directement à partir d’Office 365 et étroitement intégré à l’expérience de productivité de l’entreprise dans le nuage.


|Posez-vous la question|Action |
|:------------|:-------|
|Dans les emplacements de l’utilisateur ou les bureaux allez implémenter système téléphonique ? |Pour plus d’informations sur le système téléphonique, voir [What ' s système téléphonique dans Office 365](what-is-phone-system-in-office-365.md).</li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a>Connexion au Public commuté Switched Telephone Network (PSTN)

Pour connecter le système téléphonique pour le Public téléphone réseau commuté (RTC) afin que les utilisateurs peuvent effectuer des appels téléphoniques dans le monde entier, vous disposez des options en fonction des besoins de votre entreprise.  Posez-vous les éléments suivants :


|Posez-vous la question|Action |
| :------------|:-------|
| Je veux utiliser l’appel de Plan de Microsoft en tant que mon opérateur de téléphonie | Pour plus d’informations, consultez la rubrique [Système téléphonique avec des Plans de l’appel](calling-plan-landing-page.md).|
| Dois-je utiliser mes propres opérateur de téléphonie ? | Pour plus d’informations, voir le [Système téléphonique avec le routage Direct](direct-routing-landing-page.md).
|||


## <a name="additional-deployment-decisions"></a>Options de déploiement supplémentaires

Vous souhaiterez peut-être modifier les paramètres pour les éléments suivants, selon les besoins de votre organisation et la configuration :

- Messagerie vocale
- Identité de l’appelant
- Numéros de téléphone à partir de Microsoft
- Plan de numérotation
- Files d'attente des appels
- Standards automatiques

### <a name="voicemail"></a>Messagerie vocale

Messagerie vocale dans le nuage, grâce aux services de messagerie vocale Azure, prend en charge les dépôts de messagerie vocale pour les boîtes aux lettres Exchange et ne prend pas en charge les systèmes de messagerie tiers. Messagerie vocale dans le nuage inclut la transcription de la messagerie vocale, qui est activée par défaut pour tous les utilisateurs de votre organisation. Besoins de votre entreprise peuvent nécessiter que vous désactivez la transcription de la messagerie vocale pour des utilisateurs spécifiques ou tout le monde dans toute l’organisation.

|Posez-vous la question|Action |
|:------------|:-------|
| Je souhaite activer la messagerie vocale dans le nuage ? | Pour les procédures de configuration de la messagerie vocale, voir [configurer la messagerie vocale dans le nuage](set-up-phone-system-voicemail.md).
| Je souhaite activer la transcription de la messagerie vocale pour certains ou tous les utilisateurs ? | Pour désactiver la transcription de la messagerie vocale, consultez [définition des stratégies de messagerie vocale dans votre organisation](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</li></ul>|
|||

### <a name="calling-identity"></a>Identité de l’appelant

Par défaut, tous les appels sortants utilisent le numéro de téléphone affecté comme identité de l’appelante (ID de l’appelant). Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel.

|Posez-vous la question|Action |
|:------------|:-------|
|Je veux masquer ou désactiver l’ID de l’appelant | Pour modifier ou bloquer l’ID d’appelant, voir [définir l’ID d’appelant pour un utilisateur](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user). |
|||

### <a name="phone-numbers-from-microsoft"></a>Numéros de téléphone à partir de Microsoft

Microsoft dispose de deux types de numéros de téléphone disponibles : *abonné* (utilisateur), qui peuvent être affectés aux utilisateurs de votre organisation, des numéros *service* , disponible en tant que payants et les numéros de service gratuit, dont les appels simultanés supérieur la capacité de numéros abonné et peuvent être affectés aux services tels que la conférence Audio, les standards automatiques ou files d’attente des appels.

|Posez-vous la question|Action |
| :------------|:-------|
| Les emplacements utilisateur besoin de nouveaux numéros de téléphone à partir de Microsoft ? | Pour plus d’informations sur l’obtention des numéros de téléphone, voir [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) et [l’obtention des numéros de téléphone pour vos utilisateurs](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users). 
| Le type de numéro de téléphone (abonné ou service) besoin ? | Pour vous aider à choisir le type de numéro de téléphone que vous avez besoin, voir [différents types de numéros de téléphone utilisés pour les Plans de l’appel](different-kinds-of-phone-numbers-used-for-calling-plans.md).
Comment puis-je port existant numéros de téléphone à Office 365 ?|Pour plus d’informations, voir [transférer des numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md).
|||

### <a name="dial-plans"></a>Plan de numérotation

Un plan de numérotation dans la fonctionnalité de système téléphonique d’Office 365 est un ensemble de règles de normalisation qui traduisent composé des numéros de téléphone dans un autre format (généralement le format E.164) pour l’autorisation d’appel et le routage des appels.

Pour plus d'informations sur les plans d'appel, voir [Quels sont les plans de numérotation ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

|Posez-vous la question|Action |
|:------------|:-------|
| Mon organisation a-t-elle besoin d’un plan de numérotation personnalisé ? | Pour vous aider à déterminer si vous avez besoin d’un plan de numérotation personnalisé, consultez [planification des clients plans de numérotation](what-are-dial-plans.md#planning-for-tenant-dial-plans)|
Quels sont les utilisateurs qui ont besoin d’un plan d’appel personnalisé et quel plan de numérotation client doit être attribué à chaque utilisateur ? | Pour ajouter des utilisateurs à un plan de numérotation personnalisé dans PowerShell, voir [créer et gérer des plans de numérotation](create-and-manage-dial-plans.md). |
|||

### <a name="call-queues"></a>Files d'attente des appels

Le message d’accueil qui est utilisés lorsqu’une personne appelle un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la capacité de recherche pour l’agent disponible appel suivant gérer l’appel pendant les personnes qui sont des appels sont les files d’attente des appels dans le nuage écoute musicale. Vous pouvez créer une seule ligne ou plusieurs files d’attente d’appel pour votre organisation. 


|Posez-vous la question|Action |
|:------------|:-------|
| Mon organisation devez appelle les files d’attente ? | Pour plus d’informations, voir [créer une file d’attente des appels dans le nuage](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) et [la configuration de votre système téléphonique](setting-up-your-phone-system.md). |

### <a name="auto-attendants"></a>Standards automatiques

Standards automatiques de nuage peuvent être utilisées pour créer un système de menus pour votre organisation qui vous permet d’externe et internes appelants déplacement dans un système de menus pour localiser et placer ou transférer des appels vers les utilisateurs de la société ou département au sein de votre organisation.

|Posez-vous la question|Action |
|:------------|:-------|
| Mon organisation a-t-elle besoin de standards automatiques ? | Pour plus d’informations, voir [les standards automatiques de nuage](what-are-phone-system-auto-attendants.md) et [configurer un standard automatique de nuage](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json). |

### <a name="devices"></a>Appareils

Pour plus d’informations sur les appareils pris en charge, voir :

- [Gérer vos périphériques dans Microsoft Teams](device-management.md)
- [Téléphones IP](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Périphériques audio et vidéo USB](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Communications intelligentes pour les périphériques](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


