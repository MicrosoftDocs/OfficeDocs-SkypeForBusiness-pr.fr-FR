---
title: Appel vocal dans le nuage dans Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
search.appverid: MET150
description: En savoir plus sur la fonctionnalité voix sur le Cloud et comprendre les décisions de déploiement nécessaires.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 851e14e934578b0da8853991e1bc993e8483f818
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814874"
---
# <a name="voice---phone-system-and-pstn-connectivity-options"></a>Options système de téléphonie vocale et connectivité PSTN

Vous avez terminé la [Prise en main](get-started-with-teams-quick-start.md). Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation. Vous avez peut-être déployé des [réunions & des conférences](deploy-meetings-microsoft-teams-landing-page.md). Vous êtes désormais prêt à ajouter des fonctionnalités de voix pour vos utilisateurs. 

Voix fournit des fonctionnalités PBX (Private Branch Exchange) et des options pour la connexion au réseau téléphonique public commuté (RTC).

Cet article vous permet de déterminer si vous avez besoin de modifier des paramètres vocaux par défaut, en fonction du profil de votre organisation et des besoins de votre entreprise, puis de vous guider dans chaque modification. Nous avons fractionné les paramètres en deux groupes, en commençant par l’ensemble de [modifications que vous êtes plus susceptible de apporter](#core-deployment-decisions). Le deuxième groupe inclut les [paramètres supplémentaires](#additional-deployment-decisions) que vous souhaiterez peut-être configurer, en fonction des besoins de votre organisation.

Nous recommandons à toutes les organisations de travailler par le biais des décisions fondamentales puis, si votre organisation a des exigences supplémentaires, de consulter les documents suivants.

 > [!Note]
 > Pour plus d’informations, voir [fonctionnalités d’équipe par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3) .

## <a name="learn-more-about-voice"></a>En savoir plus sur la voix

Les articles suivants fournissent des informations supplémentaires sur le déploiement et l’utilisation des fonctionnalités vocales dans teams :

- [Système téléphonique dans Microsoft 365 ou Office 365](what-is-phone-system-in-office-365.md)
- [Système téléphonique avec forfaits d’appels](calling-plan-landing-page.md)
- [Routage direct via le système téléphonique](direct-routing-landing-page.md)
- [Détails sur les solutions téléphoniques Microsoft Telephony](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)
- Pour en savoir plus sur le système téléphonique, voir la session suivante : [Présentation du système téléphonique dans Microsoft teams](https://aka.ms/teams-phone-system)


## <a name="core-deployment-decisions"></a>Décisions liées au déploiement Core

Voici les paramètres que la plupart des organisations veulent modifier (si les paramètres par défaut de Teams ne fonctionnent pas pour l’organisation).

## <a name="phone-system-office-365"></a>Système téléphonique (Office 365)

Le système téléphonique est la technologie de Microsoft permettant d’activer le contrôle d’appel et les fonctionnalités de branchement privée (PBX) dans le Cloud Microsoft 365 ou Office 365. Le système téléphonique vous permet de remplacer votre système PBX existant par un ensemble de fonctionnalités directement fournies par Microsoft 365 ou Office 365 et intégré étroitement dans l’environnement de productivité Cloud de l’entreprise.


|Posez-vous la question|Action |
|:------------|:-------|
|Pour quels emplacements ou bureaux d’utilisateurs puis-je implémenter un système téléphonique ? |Pour plus d’informations sur le système téléphonique, voir [qu’est-ce que le système téléphonique dans Microsoft 365 ou Office 365](what-is-phone-system-in-office-365.md).</li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a>Connexion au réseau téléphonique public commuté (RTC)

Pour connecter un système téléphonique au réseau téléphonique commuté (PSTN), afin que les utilisateurs puissent passer des appels téléphoniques partout dans le monde, vous disposez d’options selon les besoins de votre entreprise.  Posez-vous les questions suivantes :


|Posez-vous la question|Action |
| :------------|:-------|
| Voulez-vous utiliser le plan d’appel Microsoft comme opérateur de téléphonie ? | Pour plus d’informations, reportez-vous à la rubrique [système téléphonique avec les offres d’appels](calling-plan-landing-page.md).|
| Ai-je besoin d’utiliser mon propre opérateur de téléphonie ? | Pour plus d’informations, reportez-vous [à la rubrique système téléphonique avec routage direct](direct-routing-landing-page.md).
|||


## <a name="additional-deployment-decisions"></a>Options de déploiement supplémentaires

Vous souhaiterez peut-être modifier les paramètres pour les éléments suivants, en fonction des besoins et de la configuration de votre organisation :

- Messagerie vocale
- Identité d’appel
- Numéros de téléphone de Microsoft
- Plan de numérotation
- Files d'attente des appels
- Les standards automatiques

### <a name="voicemail"></a>Messagerie vocale

La messagerie vocale Cloud, optimisée par les services de boîte vocale Azure, prend en charge les dépôts de boîte vocale dans les boîtes aux lettres Exchange et ne prend pas en charge les systèmes de courrier tiers. La messagerie vocale Cloud inclut la transcription de la boîte vocale, qui est activée par défaut pour tous les utilisateurs de votre organisation. Les besoins de votre entreprise peuvent nécessiter la désactivation de la transcription de la boîte vocale pour des utilisateurs spécifiques ou pour tout le monde au sein de l’organisation.

|Posez-vous la question|Action |
|:------------|:-------|
| Ai-je besoin d’activer la messagerie vocale Cloud ? | Pour les procédures de configuration de la messagerie vocale, consultez la rubrique [configurer la messagerie vocale Cloud](set-up-phone-system-voicemail.md).
| Ai-je besoin d’activer la transcription de la messagerie vocale pour tout ou partie de mes utilisateurs ? | Pour désactiver la transcription de la boîte vocale, consultez [la rubrique Configuration des stratégies de messagerie vocale au sein de votre organisation](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</li></ul>|
|||

### <a name="calling-identity"></a>Identité d’appel

Par défaut, tous les appels sortants utilisent le numéro de téléphone attribué en tant qu’identité d’appel (ID d’appelant). Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel.

|Posez-vous la question|Action |
|:------------|:-------|
|Souhaitez-vous masquer ou désactiver l’identification de l’appelant ? | Pour modifier ou bloquer l’ID de l’appelant, voir [définir l’ID d’appelant d’un utilisateur](set-the-caller-id-for-a-user.md). |
|||

### <a name="phone-numbers-from-microsoft"></a>Numéros de téléphone de Microsoft

Microsoft est doté de deux types de numéros de téléphone : les numéros d' *abonnés* (utilisateurs), qui peuvent être attribués à des utilisateurs de votre organisation et des numéros de *service* , disponibles en tant que numéros de service gratuits ou payants, qui ont une plus grande capacité d’appel simultanée que les numéros d’abonnés, et qui peuvent être attribués à des services tels que les conférences audio

|Posez-vous la question|Action |
| :------------|:-------|
| Quels sont les emplacements des utilisateurs qui ont besoin de nouveaux numéros de téléphone de Microsoft ? | Pour plus d’informations sur l’affichage des numéros de téléphone, voir [gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) et [obtenir des numéros de téléphone pour vos utilisateurs](getting-phone-numbers-for-your-users.md). 
| Quel type de numéro de téléphone (abonné ou service) ai-je besoin ? | Pour vous aider à choisir le type de numéro de téléphone dont vous avez besoin, voir [différents types de numéros de téléphone utilisés pour les offres d’appels](different-kinds-of-phone-numbers-used-for-calling-plans.md).
Comment puis-je porter des numéros de téléphone existants vers teams ?|Pour plus d’informations, reportez-vous à la section [transférer des numéros de téléphone vers Microsoft teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
|||

### <a name="dial-plans"></a>Plan de numérotation

Un plan de numérotation dans la fonctionnalité système téléphonique de Microsoft 365 ou d’Office 365 est un ensemble de règles de normalisation qui traduisent les numéros de téléphone numérotés dans un autre format (généralement le format E. 164) pour l’autorisation d’appel et le routage des appels.

Pour plus d'informations sur les plans d'appel, voir [Quels sont les plans de numérotation ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

|Posez-vous la question|Action |
|:------------|:-------|
| Mon organisation a-t-elle besoin d’un plan de numérotation personnalisé ? | Pour savoir si vous avez besoin d’un plan de numérotation personnalisé, voir [planification des plans de numérotation client](what-are-dial-plans.md#planning-for-tenant-dial-plans) .|
Quels sont les utilisateurs qui ont besoin d’un plan d’appel personnalisé et quel plan de numérotation client doit être attribué à chaque utilisateur ? | Pour ajouter des utilisateurs à un plan de numérotation personnalisé dans PowerShell, reportez-vous à la rubrique [création et gestion de plans de numérotation](create-and-manage-dial-plans.md). |
|||

### <a name="call-queues"></a>Files d'attente des appels

Les files d’attente d’appels Cloud incluent des messages d’accueil qui sont utilisés lorsque quelqu’un vous appelle pour appeler un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la possibilité de rechercher le prochain agent d’appel disponible pour gérer l’appel alors que les personnes qui appellent écoutent de la musique pendant l’attente. Vous pouvez créer des files d’attente d’appels uniques ou multiples pour votre organisation. 


|Posez-vous la question|Action |
|:------------|:-------|
| Mon organisation a-t-elle besoin d’une file d’attente d’appels ? | Pour plus d’informations, reportez-vous à la rubrique [création d’une file d’attente d’appels Cloud](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) et [configuration de votre système téléphonique](setting-up-your-phone-system.md). |

### <a name="auto-attendants"></a>Les standards automatiques

Les standards automatiques du Cloud peuvent être utilisés pour créer un système de menus pour votre organisation, qui permet aux appelants externes et internes de se déplacer dans un système de menus afin de localiser et de transférer les appels vers des utilisateurs ou services de la société au sein de votre organisation.

|Posez-vous la question|Action |
|:------------|:-------|
| Mon organisation a-t-elle besoin de standards automatiques ? | Pour plus d’informations, reportez-vous à [définition des standards automatiques Cloud](what-are-phone-system-auto-attendants.md) et [configuration d’un standard automatique Cloud](create-a-phone-system-auto-attendant.md). |

### <a name="devices"></a>Appareils

Pour plus d’informations sur les appareils pris en charge, voir les rubriques suivantes :

- [Gérer vos périphériques dans Microsoft Teams](devices/device-management.md)
- [Téléphones IP](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Périphériques audio et vidéo USB](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Communications intelligentes pour les appareils](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


