---
title: Réunion en premier - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: francoid
description: Découvrez tout d’abord les réunions dans laquelle les utilisateurs peuvent créer leurs réunions dans Teams, tout en continuant à utiliser Skype Entreprise pour les discussions, les appels et la présence.
localization_priority: Normal
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
ms.openlocfilehash: 34b32a1d421941e4e9c3bd743c5db1026d88a2ac
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809504"
---
# <a name="meetings-first"></a>Commencer par les réunions

La fonction « Réunions en premier » est ciblée et optimisée pour les organisations Skype Entreprise Server ayant des Voix Entreprise locales qui souhaitent commencer à utiliser les réunions Teams aussi rapidement que possible. Pour ces organisations, l’option Réunions en premier est une alternative à l’utilisation du mode **Îles** qui donne la priorité à l’expérience de réunions Teams.

## <a name="what-is-meetings-first"></a>Qu’est-ce que l’étape Réunions en premier ?

Les réunions sont basées sur le mode de coexistence **SfBWithTeamsCollabAndMeetings.** L’option Réunions en premier n’est pas un produit ni une fonctionnalité. Il s’agit d’une configuration qui tire parti des fonctionnalités de Teams et de Skype Entreprise pour offrir une expérience de coexistence personnalisée.

Dans Réunions, les utilisateurs créent d’abord leurs réunions dans Teams, tout en continuant à utiliser Skype Entreprise pour les discussions, les appels et la présence. Il n’existe aucun chevauchement des qualités entre Teams et Skype Entreprise. Les discussions, les appels et la présence sont en cours dans Skype Entreprise et sont en cours dans Teams. Cela permet des scénarios uniques de « meilleur ensemble » entre Skype Entreprise et Teams qui améliorent l’expérience de l’utilisateur lors de la coexistence, ainsi que des scénarios d’interopérabilité avec les utilisateurs de **Teams uniquement.**

![Capture d’écran du scénario Meilleur ensemble avec Teams et Skype Entreprise](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> Réunions Constitue un meilleur point de départ pour les organisations qui n’ont pas ou peu d’utilisateurs actifs de la conversation Teams. Les utilisateurs d’une conversation Teams actives ne doivent pas passer en mode Réunions en premier, car ils perdraient la possibilité de discuter dans Teams et d’accéder à leur historique des discussions. Ces utilisateurs doivent être en **mode** Îles et les réunions ne doivent être accordées qu’aux utilisateurs qui ne sont pas encore actifs dans la conversation dans Teams.

## <a name="who-should-consider-meetings-first"></a>Qui doit d’abord envisager les réunions ?

L’application Réunions d’abord a été conçue pour les organisations qui utilisent Skype Entreprise Server avec Voix Entreprise et qui souhaitent accélérer leur déplacement vers les réunions Teams, en particulier celles qui ont besoin d’une discipline informatique robuste, qui souhaitent obtenir un chemin de mise à niveau géré et déterminant pour Teams.

Pour les organisations complexes ou de grande taille, les migrations voix sont généralement réalisées site par site et peuvent prendre beaucoup de temps( plusieurs années), ce qui entraîne des scénarios de coexistence étendus. Si cette coexistence est en **mode** îles, les utilisateurs auront toujours la choix entre deux solutions de réunion (Skype Entreprise et Teams), ce qui peut se résultatr à des situations déroutantes ou sous-optimales. Contrairement aux migrations vocales, les migrations de réunions peuvent généralement être effectuées dans l’ensemble de l’entreprise dans un délai court. Les organisations qui souhaitent basculer complètement vers les réunions Teams le plus rapidement possible (sans attendre la fin de leur migration vocale) doivent d’abord envisager de tenir compte des réunions.

Les réunions peuvent d’abord ne pas être utiles aux organisations qui n’ont pas d’Voix Entreprise utilisateurs. Ces organisations ne doivent pouvoir mettre à niveau **vers Teams que** dès qu’elles sont en mesure d’adopter les réunions Teams. Il doit d’abord envisager d’ignorer l’étape Réunions.

De plus, l’outil Réunions en premier s’avère utile pour les organisations dont l’étendue est une solution de réunion en lecture seule, par exemple lors de l’émission d’un appel d’offres « réunions uniquement ».

## <a name="capabilities-in-meetings-first"></a>Fonctionnalités de Réunions en premier

La réunion rassemble tout d’abord les fonctionnalités suivantes :

- Mettre en service un utilisateur [Skype Entreprise Server (sur site)](https://docs.microsoft.com/microsoftteams/tutorial-audio-conferencing?tutorial-step=3) avec [l’audioconférence Teams.](tutorial-audio-conferencing.yml)
- [Service de migration](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)de réunions : les réunions organisées par l’utilisateur sont migrées vers le cloud et converties en réunions Teams au cours de la promotion de l’utilisateur en Réunions d’abord (nécessite Exchange Online).
- Expérience utilisateur rationalisée dans Teams, centrée sur les réunions et équipes et canaux Teams (qui peuvent éventuellement être masqués à l’aide de la stratégie [Autorisations d’application)](teams-app-permission-policies.md); [Les discussions privées, les](teams-client-experience-and-conformance-to-coexistence-modes.md) appels et la présence autonome d’Équipes ne sont pas exposés dans Les réunions en premier, ce qui permet aux efforts de déploiement et d’adoption de se concentrer entièrement sur les réunions.
- Expérience [de réunion Teams supérieure.](tutorial-meetings-in-teams.yml)
- « Better Together » entre Teams et Skype Entreprise : 
  - Mise en attente automatique : lors d’une réunion dans Teams, la prise d’un appel dans Skype Entreprise place la réunion Teams en attente, et inversement. Cela empêche les utilisateurs de faire entendre leurs appels privés entendus par les participants à la réunion.
    ![Capture d’écran du scénario Meilleur ensemble avec Teams et Skype Entreprise](media/meetings-first-better-together-hold.png)
  - Rapprochement des informations de présence : l’activité dans Teams est reflétée dans la présence de l’utilisateur, qui est la présence de Skype Entreprise étant donné que les appels et les discussions sont dans Skype Entreprise. Plus précisément, lorsque les premiers utilisateurs de Réunions se retrouvent dans une réunion Teams, leur présence est mise à jour pour refléter cela. Lorsqu’il présente son écran, sa présence est mise à jour pour afficher ne pas déranger (d’après les paramètres de Skype Entreprise).
  - Rapprochement des contrôles HID d’appareil USB (également disponible sur Mac) : les contrôles HID sont honorés par Teams pendant les réunions Teams et par Skype Entreprise dans toutes les autres circonstances.
  - Sauf mention contraire, les fonctionnalités Better Together nécessitent actuellement des clients de bureau Windows récents.

## <a name="prerequisites-for-meetings-first"></a>Conditions préalables pour les réunions en premier

Les seules conditions difficiles à utiliser pour les réunions En premier sont les mêmes que pour Teams avec Active Directory local et un déploiement local de Skype Entreprise :

- [Conditions préalables générales pour Teams,](upgrade-plan-journey-prerequisites.md)notamment
- [Identité et authentification dans Teams](identify-models-authentication.md) et
- [Configurez Azure Active Directory pour Teams et Skype Entreprise.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect)

Une [topologie Skype Entreprise hybride](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) n’est pas nécessaire, mais elle est recommandée. Certaines fonctionnalités, telles que le service de migration de réunions et l’interopérabilité, dépendent de cette topologie.

Meetings First est pris en charge avec n’importe quelle version de Skype Entreprise Server (et est connu pour fonctionner avec le serveur Lync non pris en charge). Il est pris en charge avec n’importe quel client Skype Entreprise, mais les fonctionnalités Better Together nécessitent un client récent.

Une fois ces conditions remplies (et non antérieures), les utilisateurs peuvent être titulaires d’une licence [pour Microsoft 365 ou Office 365 et Teams.](https://docs.microsoft.com/office365/enterprise/assign-licenses-to-user-accounts)

Pour une première expérience de réunion la meilleure possible, les utilisateurs doivent être activés pour créer des groupes [Exchange Online,](exchange-teams-interact.md) [SharePoint Online, OneDrive](sharepoint-onedrive-interact.md)Entreprise et Microsoft 365. Meetings First est pris en charge pour les utilisateurs dont la boîte aux lettres se trouve sur Exchange en local, qui n’ont pas SharePoint Online, OneDrive Entreprise ou la création de groupes Microsoft 365. Leur expérience sera toutefois moins complète. En particulier, pour les organisations qui utilisent Exchange Server localement, il peut y avoir (selon la version d’Exchange Server) certaines limitations à la création et à l’affichage des réunions à partir du client Teams, ainsi qu’au niveau des fonctionnalités de conformité.

Au minimum, les utilisateurs doivent être [titulaires d’une licence pour Teams.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) En outre, elles peuvent être titulaires d’une licence [d’audioconférence,](set-up-audio-conferencing-in-teams.md)si nécessaire.

Nous vous recommandons [d’accorder le mode **client SfBOnly** ou **SfBWithTeamsCollab**](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) par défaut au moment où vous accordez une licence aux utilisateurs. Cela garantit que les utilisateurs ne commenceraient pas à utiliser Teams par eux-mêmes en **mode** Îles par défaut avant que vous ne soyez prêt à lancer les réunions tout d’abord.

Meetings First est pris en charge sur les clients de bureau complets (Windows et Mac), sur les clients de navigateur et sur les clients mobiles. Il est également compatible avec [les salles Microsoft Teams.](https://docs.microsoft.com/microsoftteams/room-systems/) Better Together nécessite le client de bureau complet.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Préparer les réunions Teams dans Réunions tout d’abord

Pour que vos utilisateurs ont la meilleure expérience possible dans les réunions Teams, vous devez :

- Suivez notamment les étapes des réunions et [conférences pour Microsoft Teams.](deploy-meetings-microsoft-teams-landing-page.md)
- [Évaluez votre environnement.](3-envision-evaluate-my-environment.md)
- [Préparez le réseau de votre organisation pour Microsoft Teams.](prepare-network.md)
- Mettre à niveau vos salles de réunion avec des [solutions](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)et des appareils de salle de réunion capables de Teams, ou utiliser [Cloud Video Interop](cloud-video-interop.md) pour Microsoft Teams pour permettre à vos salles et appareils tiers existants de participer à des réunions Teams.
- Équipez vos utilisateurs [de périphériques audio et vidéo USB certifiés.](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- Préparer les [réunions Teams pour les sensibilisations et l’adoption.](adopt-microsoft-teams-landing-page.md)
- [Planifiez votre gestion des services.](4-envision-plan-my-service-management.md)
- Familiarisez-vous avec les rapports d’analyse des appels [enrichis pour résoudre les problèmes de qualité des appels.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

À ce stade, vous pouvez envisager d’exécutez un pilote prêt pour la production d’échelle modérée.

## <a name="configure-users-for-meetings-first"></a>Configurer d’abord les utilisateurs pour les réunions

Une fois que vous avez autorisé vos utilisateurs et préparé votre organisation pour les réunions Teams, il est temps d’activer d’abord vos utilisateurs pour les réunions. Nous avons fait en sorte que tout soit facile : un seul paramètre vous permettra d’y voir plus facilement.

Toutes les fonctionnalités et expériences utilisateur dans Les réunions en premier, y compris la configuration du client Teams et la [conformité](teams-client-experience-and-conformance-to-coexistence-modes.md) automatique de l’expérience utilisateur, le service de migration de réunions et les fonctionnalités Better Together, sont configurées en octroyant à l’utilisateur (ou au groupe d’utilisateurs ou au client par défaut) le mode de [coexistence SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md) dans le Centre d’administration [Microsoft Teams](manage-teams-in-modern-portal.md) ou à l’aide [de PowerShell.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

![Capture d’écran des paramètres d’administration permettant d’activer d’abord les réunions](media/teams-meeting-admin-settings.png)

Si vous le souhaitez, si vous souhaitez masquer l’application Équipes et canaux dans le navigation gauche du [](teams-app-permission-policies.md)client Teams de vos utilisateurs, afin de concentrer leur expérience sur les réunions, qui peuvent être obtenues à l’aide de la stratégie d’autorisation d’application.

## <a name="reporting-and-call-analytics"></a>Rapports et analyse des appels

Les rapports et les données d’analyse des appels pour les réunions Teams dans les réunions sont tout d’abord inchangées par rapport à ce qu’elles sont dans les autres modes.

## <a name="related-links"></a>Liens connexes

Après avoir consulté cet article, vous souhaiterez peut-être consulter les recommandations de mise à [niveau,](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)de migration et [d’interopérabilité,](migration-interop-guidance-for-teams-with-skype.md)et de [coexistence](coexistence-chat-calls-presence.md) avec Skype Entreprise pour plus d’informations.


