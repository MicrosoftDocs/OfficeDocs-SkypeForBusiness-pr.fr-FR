---
title: Première réunion - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: Découvrez les réunions d’abord, où les utilisateurs peuvent créer leur réunion dans Teams, tout en continuant à utiliser Skype Entreprise pour la conversation, l’appel et la présence.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 149a5a3e22a633ec4c889b68a91ac9c6db8e9f4b
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789779"
---
# <a name="meetings-first"></a>Commencer par les réunions

« Réunions d’abord » est ciblé et optimisé pour les organisations Skype Entreprise Server avec des Voix Entreprise locales qui souhaitent commencer à utiliser les réunions Teams aussi rapidement que possible. Pour ces organisations, Meetings First est une alternative à l’utilisation du mode **Îles** qui hiérarchise l’expérience des réunions Teams.

## <a name="what-is-meetings-first"></a>Qu’est-ce que Les réunions d’abord ?

Meetings First est basé sur le mode **de coexistence SfBWithTeamsCollabAndMeetings** . Meetings First n’est pas un produit ou une fonctionnalité , il s’agit d’une configuration qui utilise les fonctionnalités et fonctionnalités de Teams et Skype Entreprise pour fournir une expérience de coexistence personnalisée de manière unique.

Dans Réunions d’abord, les utilisateurs créent leur réunion dans Teams, tout en continuant à utiliser Skype Entreprise pour la conversation, l’appel et la présence. Il n’y a pas de chevauchement des modalités entre Teams et Skype Entreprise. La conversation, l’appel et la présence sont activés dans Skype Entreprise et désactivés dans Teams. Cela permet des scénarios uniques « mieux ensemble » entre Skype Entreprise et Teams qui améliorent l’expérience de l’utilisateur pendant la coexistence, ainsi que des scénarios d’interopérabilité avec les utilisateurs **Teams uniquement**.

![Capture d’écran du meilleur scénario avec Teams et Skype Entreprise.](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> Meetings First est une meilleure correspondance pour les organisations qui n’ont pas ou peu d’utilisateurs de conversation Teams actifs. Les utilisateurs de conversation Active Teams ne doivent pas être basculés vers le mode Réunions en premier, car ils perdraient la possibilité de discuter dans Teams et d’accéder à leur historique de conversation. Ces utilisateurs doivent être acquis en mode **Îles** à la place, et Les réunions d’abord ne doivent être accordées qu’aux utilisateurs qui ne sont pas encore actifs dans la conversation dans Teams.

## <a name="who-should-consider-meetings-first"></a>Qui doit d’abord envisager les réunions ?

Meetings First a été conçu pour les organisations qui utilisent Skype Entreprise Server avec des Voix Entreprise qui souhaitent accélérer leur passage aux réunions Teams, en particulier ceux qui ont une discipline informatique forte qui souhaitent un chemin de mise à niveau managé et déterministe vers Teams.

Pour les organisations complexes ou de grande taille, les migrations vocales sont généralement effectuées site par site et peuvent prendre beaucoup de temps, voire plusieurs années, ce qui entraîne des scénarios de coexistence étendus. Si cette coexistence est en mode **Îles**, les utilisateurs auront toujours le choix entre deux solutions de réunion (Skype Entreprise et Teams), ce qui peut entraîner des situations déroutantes ou non optimales. Contrairement aux migrations vocales, les migrations de réunions peuvent généralement être effectuées dans toute l’entreprise en peu de temps. Les organisations qui souhaitent basculer complètement vers les réunions Teams le plus rapidement possible (et sans attendre la fin de leur migration vocale) doivent d’abord envisager les réunions.

Les réunions d’abord peuvent ne pas être utiles pour les organisations qui n’ont pas d’utilisateurs Voix Entreprise. Ces organisations doivent pouvoir effectuer une mise à niveau vers **Teams uniquement** dès qu’elles sont en mesure d’adopter des réunions Teams. Ils doivent d’abord envisager d’ignorer les réunions.

En outre, Meetings First est utile pour les organisations dont l’étendue est une solution de réunion pure lecture, par exemple lorsqu’une DFP « réunions uniquement » est émise.

## <a name="capabilities-in-meetings-first"></a>Fonctionnalités des réunions d’abord

Meeting First réunit les fonctionnalités suivantes :

- [Provisionnez un utilisateur Skype Entreprise Server (local)](./tutorial-audio-conferencing.yml?tutorial-step=3) avec [l’audioconférence Teams](tutorial-audio-conferencing.yml).
- [Service de migration de réunions](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms) : les réunions organisées par l’utilisateur sont migrées vers le cloud et converties en réunions Teams lorsque l’utilisateur est promu en Réunions d’abord (nécessite Exchange Online).
- Simplification de l’expérience utilisateur dans Teams, centrée sur les réunions teams et les équipes et les canaux (qui peuvent éventuellement être masqués à l’aide de la [stratégie d’autorisations](teams-app-permission-policies.md) d’application); [Les conversations privées Teams, les appels et la présence autonome](teams-client-experience-and-conformance-to-coexistence-modes.md) ne sont pas exposés dans Meetings First, ce qui permet au déploiement et à l’adoption de se concentrer pleinement sur les réunions.
- Expérience de [réunion Teams](tutorial-meetings-in-teams.yml) supérieure.
- « Better Together » entre Teams et Skype Entreprise : 
  - Conservation automatique : lors d’une réunion dans Teams, l’obtention d’un appel dans Skype Entreprise met la réunion Teams en attente, et vice versa. Cela empêche les utilisateurs d’entendre leurs appels privés par les participants aux réunions.
    ![Capture d’écran du meilleur scénario avec Teams et Skype Entreprise.](media/meetings-first-better-together-hold.png)
  - Rapprochement de présence : l’activité dans Teams se reflète dans la présence de l’utilisateur, qui est la présence Skype Entreprise puisque la conversation et l’appel sont en Skype Entreprise. Plus précisément, lorsque les utilisateurs de Meetings First participent à une réunion Teams, leur présence est mise à jour pour refléter cela. Lorsqu’ils présentent leur écran, leur présence est mise à jour pour afficher Ne pas déranger (en fonction de leurs paramètres dans Skype Entreprise).
  - Rapprochement des contrôles HID d’appareil USB (également disponibles sur Mac) : les contrôles HID sont respectés par Teams lors des réunions Teams et par Skype Entreprise dans toutes les autres circonstances.
  - Sauf indication contraire, les fonctionnalités Better Together nécessitent des clients de bureau Windows récents pour l’instant.

## <a name="prerequisites-for-meetings-first"></a>Prérequis pour les réunions en premier

Les seules exigences matérielles pour Meetings First sont les mêmes que celles de Teams avec Active Directory local et un déploiement local Skype Entreprise :

- [Conditions préalables générales pour Teams](upgrade-plan-journey-prerequisites.md), notamment
- [Identité et authentification dans Teams](identify-models-authentication.md) et
- [Configurez Azure Active Directory pour Teams et Skype Entreprise](/skypeforbusiness/hybrid/configure-azure-ad-connect).

Une [topologie hybride Skype Entreprise](/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) n’est pas nécessaire, mais elle est recommandée. Certaines fonctionnalités telles que Meetings Migration Service et l’interopérabilité reposent sur cette topologie.

Meetings First est pris en charge avec n’importe quelle version du Skype Entreprise Server (et connu pour fonctionner avec le serveur Lync qui n’est plus pris en charge). Il est pris en charge avec n’importe quel client Skype Entreprise pris en charge, mais les fonctionnalités Better Together nécessitent un client récent.

Une fois ces exigences remplies (et non antérieures), les utilisateurs peuvent obtenir une [licence microsoft 365 ou Office 365 et Teams](/office365/enterprise/assign-licenses-to-user-accounts).

Pour bénéficier de la meilleure expérience Réunions d’abord, les utilisateurs doivent être activés pour [la création de groupes Exchange Online](exchange-teams-interact.md)[, SharePoint Online et OneDrive Entreprise](sharepoint-onedrive-interact.md) et Microsoft 365. Meetings First est pris en charge pour les utilisateurs dont la boîte aux lettres se trouve sur Exchange en local, ou qui n’ont pas de création de groupe SharePoint Online, OneDrive Entreprise ou Microsoft 365. Toutefois, leur expérience sera moins complète. En particulier, pour les organisations qui utilisent Exchange Server localement, il peut y avoir (selon la version de Exchange Server) certaines limitations à la création et à l’affichage de réunions à partir du client Teams, ainsi qu’en ce qui concerne les fonctionnalités de conformité.

Au minimum, les utilisateurs doivent disposer [d’une licence pour Teams](/microsoft-365/admin/manage/assign-licenses-to-users). En outre, elles peuvent être concédées sous licence pour [l’audioconférence](set-up-audio-conferencing-in-teams.md), si nécessaire.

Nous vous recommandons [**d’accorder le mode SfBOnly** ou **SfBWithTeamsCollab**](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) en tant que mode client par défaut au moment où vous concédez une licence aux utilisateurs. Cela permet de s’assurer que les utilisateurs ne commencent pas à utiliser Teams par leurs propres moyens en mode **Îles** par défaut avant d’être prêts à lancer Meetings First.

Meetings First est pris en charge sur les clients de bureau complets (Windows et Mac), sur les clients de navigateur et sur les clients mobiles. Il est également compatible avec [Salles Microsoft Teams](/microsoftteams/room-systems/). Better Together nécessite le client de bureau complet.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Préparer d’abord les réunions Teams dans les réunions

Pour que vos utilisateurs bénéficient de la meilleure expérience possible dans les réunions Teams, vous devez :

- Suivez les [étapes des réunions et conférences pour Microsoft Teams](deploy-meetings-microsoft-teams-landing-page.md), en particulier.
- [Évaluez votre environnement](3-envision-evaluate-my-environment.md).
- [Préparez le réseau de votre organisation pour Microsoft Teams](prepare-network.md).
- Mettez à niveau vos salles de réunion avec [des solutions et des appareils de salle de réunion](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) compatibles Teams, ou utilisez [Cloud Video Interop pour Microsoft Teams pour](cloud-video-interop.md) permettre à vos salles et appareils tiers existants de rejoindre des réunions Teams.
- Équipez vos utilisateurs [d’appareils audio et vidéo USB certifiés](/skypeforbusiness/certification/devices-usb-devices?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json).
- Préparez-vous à [favoriser la sensibilisation et l’adoption des réunions Teams](adopt-microsoft-teams-landing-page.md).
- [Planifiez votre gestion des services](4-envision-plan-my-service-management.md).
- Familiarisez-vous avec les rapports d’analyse des appels complets pour [résoudre les problèmes de mauvaise qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md).

Vous pouvez envisager d’exécuter un pilote prêt pour la production à l’échelle modérée à ce stade.

## <a name="configure-users-for-meetings-first"></a>Configurer les utilisateurs pour les réunions d’abord

Une fois que vous avez concédé une licence à vos utilisateurs et préparé votre organisation pour les réunions Teams, il est temps d’activer vos utilisateurs pour les réunions d’abord. Nous avons facilité la tâche : un seul paramètre va tout faire !

Toutes les fonctionnalités et expériences utilisateur dans Meetings First, y compris la configuration du client Teams et la [conformité automatique](teams-client-experience-and-conformance-to-coexistence-modes.md) de l’expérience utilisateur, Meetings Migration Service et Better Together, sont configurées en accordant à l’utilisateur (ou au groupe d’utilisateurs ou au locataire par défaut) le [mode de coexistence SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md) dans le [Centre d’administration Microsoft Teams](manage-teams-in-modern-portal.md) ou à l’aide de [PowerShell](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).

![Capture d’écran des paramètres d’administration pour activer Les réunions d’abord.](media/teams-meeting-admin-settings.png)

Si vous le souhaitez, si vous souhaitez masquer l’application Teams et Canaux dans la navigation gauche du client Teams de vos utilisateurs pour concentrer davantage leur expérience sur les réunions, cela peut être réalisé à l’aide de la [stratégie d’installation](teams-app-setup-policies.md) de l’application.

## <a name="reporting-and-call-analytics"></a>Analyse des rapports et des appels

Les réunions Reporting et Call Analytics for Teams dans Meetings First sont inchangées par rapport à ce qu’elles sont dans d’autres modes.

## <a name="related-links"></a>Liens connexes

Après avoir examiné cet article, vous pouvez consulter [choisir votre parcours de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), les [conseils sur la migration et l’interopérabilité](migration-interop-guidance-for-teams-with-skype.md), ainsi que [la coexistence avec Skype Entreprise](coexistence-chat-calls-presence.md) pour plus d’informations.
