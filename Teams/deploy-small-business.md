---
title: Configurer Microsoft Teams dans votre petite entreprise
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Configurez Teams dans votre petite entreprise pour permettre à vos utilisateurs de collaborer à l’aide de la conversation et du partage de fichiers, configurer à des réunions de petite et grande taille, puis d’y participer, et discuter par vidéo et voix.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7e15a8a327d40ea11412229205fca6e856e9f7b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596318"
---
# <a name="set-up-microsoft-teams-in-your-small-business"></a>Configurer Microsoft Teams dans votre petite entreprise

Il existe de nombreuses façons de personnaliser Teams. Les sections suivantes vous montrent comment configurer chaque charge de travail Teams : **conversations, équipes et canaux** ; **réunions et conférences** ; et **voix cloud**. Vous devez définir l’ordre de configuration de chaque charge de travail. Nous vous recommandons de commencer par définir d’abord les conversations, les équipes et les canaux de charge de travail. Cependant, vous pouvez commencer par des réunions et des conférences, voire la voix cloud. Le choix vous appartient.

> [!NOTE]
> Si vous ne l’avez pas déjà fait, nous vous recommandons vivement de commencer votre déploiement Teams par un pilote. Un pilote vous permettra, ainsi qu'à quelques utilisateurs précoces, de vous familiariser avec Teams et ses fonctionnalités avant votre planification et votre déploiement éventuel. Si vous souhaitez en savoir plus sur le démarrage de votre pilote, veuillez consulter la page [Prise en main de Microsoft Teams](get-started-with-teams-quick-start.md).

Avant de déployer Teams à grande échelle, pour vérifier que votre organisation est prête, veuillez consulter la section [Vérifiez que vous êtes prêt](get-started-with-teams-quick-start.md#make-sure-youre-ready).

Passez à la section qui vous intéresse :

- [Charges de travail](#workloads)
  - [Conversation, équipes et canaux](#chat-teams-and-channels)
  - [Réunions et conférences](#meetings-and-conferencing)
  - [Business Voice](#business-voice)
- [Déploiement des clients](#deploy-clients)
- [Formation](#training)

## <a name="workloads"></a>Charges de travail
### <a name="chat-teams-and-channels"></a>Conversation, équipes et canaux

La conversation, les équipes et les canaux sont la clé de l’utilisation de Teams. La **conversation** permet à un ou plusieurs utilisateurs de discuter, de partager des fichiers, puis de se réunir en privé. Les **équipes**, visibles par tous les membres de votre organisation ou seulement par les membres de l’équipe, permettent aux bonnes personnes collaborer quelle que soit la tâche ou l’occasion, qu’il s’agisse d’un projet de longue durée ou d’une fête d’anniversaire. Les **canaux** au sein des équipes peuvent segmenter des sujets, des projets, des services ou toute autre chose qui a du sens pour votre équipe. Si vous souhaitez en savoir plus sur les conversations, les équipes et les canaux, veuillez consulter la rubrique [Vue d’ensemble des équipes et canaux](teams-channels-overview.md).

> [!TIP]
> Découvrez comment gérer les rôles d’équipe, l’accès et les stratégies de messagerie en complétant le module [Gérer Microsoft Teams](/learn/modules/m365-teams-collab-manage-teams/) dans Microsoft Learn.

Lorsque vous pensez à déployer des équipes et des canaux, vous devez décider qui doit pouvoir les créer, si des invités extérieurs à votre organisation peuvent y accéder, et bien plus encore. L’article [Conversation, équipes, canaux et applications dans Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md) propose de nombreuses informations sur la planification des conversations, des équipes et des canaux. Toutefois, voici quelques éléments clés de cet article à prendre en compte. Sélectionnez une décision si vous souhaitez en savoir plus à son sujet.

| Decision | Description |
|--|--|
| [Qui doit être administrateur Teams ?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-administrators) | Les rôles d'administrateur vous permettent d’accorder des autorisations spécifiques aux personnes qui doivent, selon vous, administrer Teams. Les petites entreprises n’ont pas besoin de ces rôles supplémentaires, car la même personne peut être responsable de tous les aspects de Teams. Vous pouvez toujours ajouter ou supprimer des administrateurs ultérieurement.<br><br>[Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams](using-admin-roles.md) |
| [Qui doit être propriétaire et membre d’une équipe ?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-owners-and-members) | Les propriétaires d’équipe contrôlent qui peut accéder à une équipe et à ses canaux. Ils peuvent décider si une équipe ou un canal est public (pour l’organisation) ou privé, puis définir des stratégies telles que la modération d’un canal. Les membres peuvent accéder à l’équipe et à ses canaux (sauf si un canal est donné comme privé et qu’ils ne sont pas membres de ce canal) et peuvent être désignés comme modérateurs.<br><br>[Affecter des propriétaires d’équipe et des membres dans Microsoft Teams](assign-roles-permissions.md) |
| [Dois-je activer l’accès invité ?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#guest-access) |L’accès invité permet aux contacts de votre organisation d’inviter des contacts externes à votre organisation à accéder à vos équipes et canaux. L’accès invité sert souvent à collaborer avec des contacts extérieurs à votre organisation qui n’ont pas de relation officielle avec la vôtre. Par exemple, vous pouvez inviter un planificateur de projet à travailler temporairement sur un projet.<br>L’accès invité est différent de l’accès externe. L'accès invité permet d’inviter des personnes spécifiques à interagir avec les contacts de votre organisation.  <br>L’accès invité est **désactivé** par défaut. <br><br>[Activer ou désactiver l'accès invité dans Microsoft Teams](set-up-guests.md)  |

Vous n’avez rien d’autre à faire pour que vos utilisateurs commencent à utiliser la conversation, les équipes et les canaux. Toutefois, de nombreuses options vous permettent de contrôler l’utilisation de Teams. Vous pouvez apporter des modifications maintenant ou attendre de voir comment les personnes utilisent Teams. Si vous souhaitez en savoir plus veuillez, consulter les articles suivants :

- [Gérer les stratégies de messagerie dans Teams](messaging-policies-in-teams.md)
- [Paramètres de Teams](enable-features-office-365.md#teams-settings)

### <a name="meetings-and-conferencing"></a>Réunions et conférences

Les réunions et les conférences permettent aux contacts de votre organisation de se réunir, puis de rencontrer les personnes extérieures à votre organisation. Toute personne possédant un client Teams ou Skype Entreprise peut participer aux **réunions** auxquelles elle a été invitée. L’utilisation du microphone, de la caméra et de l’écran de leur appareil permet aux participants de rejoindre la conversation sans avoir besoin d’un téléphone. Les participants peuvent converser, passer des appels vocaux et partager des vidéos et applications avec d’autres participants à l’aide d’un PC ou d’un appareil mobile.

Le **système d’audioconférence** permet aux participants de rejoindre les réunions par téléphone normal en appelant un numéro de téléphone de conférence, puis en entrant un ID de réunion. L’audioconférence est utile lorsqu’un participant n’a pas une bonne connexion Internet, que la réunion est à voix seule ou qu’une autre circonstance ne lui permet pas de rejoindre la réunion via le client Teams.

> [!TIP]
> Familiarisez-vous avec les réunions et événements en exécutant le module [Gérer les réunions, les conférences et les événements avec Microsoft Teams](/learn/modules/m365-teams-collab-manage-meetings) sur Microsoft Learn.

Les réunions sont activées par défaut dans Teams. Toutefois, vous pouvez contrôler l’expérience des organisateurs et des participants en matière de réunions. Vous pouvez également définir des stratégies sur ce que les personnes peuvent et ne peuvent pas faire avant et pendant les réunions. Si vous souhaitez en savoir plus veuillez, consulter les articles suivants :

- [Démarrage rapide pour les administrateurs : réunions et événements en direct dans Microsoft Teams](quick-start-meetings-live-events.md)
- [Configurer l’audioconférence pour les petites et moyennes entreprises](audio-conferencing-smb.md)

### <a name="business-voice"></a>Business Voice

[Microsoft 365 Business Voice](business-voice/whats-business-voice.md) est une solution idéale pour les entreprises de moins de 300 utilisateurs. Elle offre toutes les fonctionnalités d’un système de téléphonie de bureau. Business Voice inclut la messagerie vocale, l’identification de l'appelant, des menus de système téléphonique, des numéros gratuits, et bien plus encore, sans devoir gérer un système téléphonique local complexe et coûteux.

Basé sur le Système téléphonique Microsoft 365, Business Voice simplifie l’ajout de voix à votre organisation en regroupant les fonctionnalités et les modules supplémentaires du système téléphonique, puis en fournissant un assistant facile à suivre pour vous aider à configurer votre système téléphonique. Si votre organisation se trouve dans un pays ou une région [qui prend en charge Business Voice](business-voice/country-region-availability.md), vous pouvez transférer vos numéros de téléphone vers Microsoft 365 et nous laisser gérer votre système téléphonique à votre place.

Avec Microsoft 365 comme système téléphonique, vous pouvez transformer n’importe quel appareil en téléphone en y installant le client Teams. Sinon, si vous préférez un téléphone classique de bureau ou de conférence, vous pouvez le choisir parmi un grand nombre d’appareils certifiés Teams. Dans les deux cas, les appels parviennent toujours à l’endroit où vous vous trouvez, et votre numéro de téléphone de bureau s’affiche toujours lorsque vous passez des appels.

Si vous souhaitez essayer Business Voice, veuillez consulter la rubrique [Que dois-je me procurer pour utiliser Microsoft 365 Business Voice ?](business-voice/what-to-buy.md).

## <a name="deploy-clients"></a>Déployer les clients

Lorsque vous êtes prêt à aider vos utilisateurs à utiliser Teams, ils peuvent installer le client Teams sur leurs PC Windows, Mac ou Linux, ou sur leurs appareils Android ou iOS. Les utilisateurs peuvent télécharger le client Teams directement depuis <https://teams.microsoft.com/downloads>.

Vérifiez que toute personne souhaitant utiliser Teams possède une licence Teams. Si vous souhaitez en savoir plus sur l’attribution d’une licence Teams, veuillez consulter la rubrique [Gérer l’accès des utilisateurs à Teams](user-access.md#using-the-microsoft-365-admin-center).

> [!TIP]
> Obtenez des recommandations sur la façon de planifier le déploiement de votre client Teams en complétant le module [Déployer les clients Microsoft Teams](/learn/modules/m365-teams-collab-deploy-clients/) sur Microsoft Learn.

Si votre organisation utilise Microsoft Endpoint Configuration Manager, une stratégie de groupe ou un mécanisme de distribution tiers, pour déployer des logiciels sur les ordinateurs de vos utilisateurs, veuillez consulter la rubrique [Installer Microsoft Teams à l’aide de Microsoft Endpoint Configuration Manager](msi-deployment.md).

Si vous souhaitez en savoir plus sur le déploiement des clients Teams, veuillez consulter la rubrique [Obtenir les clients pour Microsoft Teams](get-clients.md).

## <a name="training"></a>Formation

Si vous souhaitez en savoir plus sur la formation de vos utilisateurs et administrateurs à l’utilisation de Teams, veuillez consulter la rubrique [Formation Microsoft Teams](training-microsoft-teams-landing-page.md).