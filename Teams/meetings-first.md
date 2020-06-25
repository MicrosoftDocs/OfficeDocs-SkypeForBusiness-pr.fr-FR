---
title: Première réunion-Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: francoid
description: Apprenez d’abord sur les réunions, pour permettre aux utilisateurs de créer leur réunion dans Teams, tout en continuant à utiliser Skype entreprise pour la messagerie instantanée, les appels et la présence.
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
ms.openlocfilehash: 58f8424342fa609124a3b658fbde9d7d297d7b44
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868471"
---
# <a name="meetings-first"></a>Commencer par les réunions

« Les réunions d’abord » est ciblée et optimisée pour les organisations de serveurs Skype entreprise sur site qui souhaitent commencer à utiliser les réunions d’équipes le plus rapidement possible. Pour ces organisations, d’abord les réunions sont une alternative à l’utilisation du mode **îlot** qui accorde la priorité à l’utilisation des réunions Teams.

## <a name="what-is-meetings-first"></a>Qu’est-ce que les réunions d’abord ?

Les réunions sont d’abord basées sur le mode de coexistence **SfBWithTeamsCollabAndMeetings** . Les réunions ne sont pas des produits ou des fonctionnalités : il s’agit d’une configuration qui exploite les fonctionnalités d’équipes et de Skype entreprise pour proposer une interface de coexistence unique et personnalisée.

Pour commencer, les utilisateurs créent leur réunion dans Teams, tout en continuant à utiliser Skype entreprise pour la messagerie instantanée, les appels et la présence. Il n’y a pas de chevauchements de modalités entre teams et Skype entreprise. Les discussions, appels et présence sont activés dans Skype entreprise et désactivés dans Teams. Cela permet de mettre en place des scénarios « réunis » uniques entre Skype entreprise et teams qui améliorent l’expérience utilisateur pendant la coexistence, ainsi que des scénarios d’interopérabilité avec les utilisateurs de **teams uniquement** .

![Capture d’écran illustrant un scénario de meilleure collaboration avec teams et Skype entreprise](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> Les réunions sont d’abord plus adaptées aux organisations qui n’ont pas le plus d’utilisateurs de chat en équipe actif. Discussions d’équipes actives les utilisateurs ne doivent pas être basculés vers le premier mode réunions, car ils perdront la possibilité de discuter en équipe et d’accéder à leur historique des conversations. Ces utilisateurs doivent être précédés du mode **îlot** , et les réunions sont d’abord accordées uniquement aux utilisateurs qui ne sont pas encore actives dans la conversation dans Teams.

## <a name="who-should-consider-meetings-first"></a>Qui doit envisager d’abord les réunions ?

Les réunions d’abord ont été conçues pour des organisations qui utilisent Skype entreprise Server avec voix entreprise qui souhaitent accélérer le passage aux réunions d’équipes, en particulier celles dont le niveau de discipline est important et qui souhaitent un chemin de mise à niveau géré et déterministe vers Teams.

Dans le cas d’organisations complexes ou de grande taille, les migrations vocales sont généralement effectuées en fonction du site et peuvent prendre un certain temps, peut-être quelques années, ce qui peut entraîner des scénarios de coexistence étendus. Si cette coexistence est en mode **îlot** , les utilisateurs auront toujours le choix entre deux solutions de réunion (Skype entreprise et Teams), ce qui peut entraîner des situations confuses ou déconseillées. Contrairement aux migrations vocales, les migrations de réunions peuvent généralement être effectuées au sein de l’ensemble de la société dans une durée courte. Les organisations qui souhaitent basculer totalement vers les réunions teams aussi rapidement que possible (et sans attendre la fin de leur migration vocale) doivent envisager d’abord des réunions.

Les réunions peuvent d’abord ne pas être utiles aux organisations qui n’ont pas d’utilisateurs voix entreprise. Ces organisations doivent être en mesure de procéder à une mise à niveau vers **équipes uniquement** dès qu’elles sont en mesure d’adopter des réunions d’équipe. Ils doivent commencer par ignorer les réunions.

De plus, les réunions sont d’abord utiles pour les organisations dont l’étendue est une solution de réunion à lecture pure, par exemple lorsqu’un appel d’offre « réunions uniquement » est émis.

## <a name="capabilities-in-meetings-first"></a>Fonctionnalités des réunions en premier

La réunion commence par commencer conjointement les fonctionnalités suivantes :

- [Approvisionner un utilisateur Skype entreprise Server (en local)](https://docs.microsoft.com/microsoftteams/tutorial-audio-conferencing?tutorial-step=3) avec l' [audioconférence teams](tutorial-audio-conferencing.yml).
- [Service de migration des réunions](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms): les réunions organisées par l’utilisateur sont déplacées vers le Cloud et converties en réunions Teams, car l’utilisateur est promu d’abord pour les réunions (nécessite Exchange Online).
- Une interface utilisateur rationalisée dans Teams, centrée sur les réunions d’équipe et les équipes et les canaux (qui peuvent éventuellement être masqués à l’aide de la [stratégie d’autorisations des applications](teams-app-permission-policies.md)); La [discussion privée, les appels et la présence automatique d’équipes](teams-client-experience-and-conformance-to-coexistence-modes.md) ne sont pas exposés dans les réunions en premier, ce qui permet à l’effort de déploiement et d’adoption de se concentrer entièrement sur les réunions.
- Amélioration de l' [interaction des réunions teams](tutorial-meetings-in-teams.yml).
- « Collaborez » entre teams et Skype entreprise : 
  - Mise en attente automatique : lorsque vous êtes dans une réunion dans Teams, la mise en place d’un appel dans Skype entreprise met en attente la réunion Teams, et inversement. Cela empêche les utilisateurs d’avoir leurs appels privés préappelé par les participants à la réunion.
    ![Capture d’écran illustrant un scénario de meilleure collaboration avec teams et Skype entreprise](media/meetings-first-better-together-hold.png)
  - Réconciliation de présence : l’activité dans teams est reflétée dans la présence de l’utilisateur, qui est la présence de Skype entreprise dans Skype entreprise. En particulier, lors de la réunion d’équipes d’équipes, leur présence est mise à jour afin de refléter celle-ci. Lorsqu’ils présentent leur écran, leur présence est mise à jour afin de ne pas déranger (en fonction des paramètres de Skype entreprise).
  - Division de contrôle HID de périphérique USB (également disponible sur Mac) : les contrôles HID sont honorés par teams pendant les réunions d’équipes et par Skype entreprise dans les autres circonstances.
  - Sauf indication contraire, de meilleures capacités de regroupement nécessitent des clients de bureau Windows récents pour le moment.

## <a name="prerequisites-for-meetings-first"></a>Prérequis pour les réunions d’abord

Les seules configurations matérielles requises pour les réunions sont les mêmes que celles requises pour les équipes disposant d’Active Directory local et d’un déploiement local de Skype entreprise :

- [Conditions générales d’une équipe](upgrade-plan-journey-prerequisites.md), notamment
- [Identité et authentification dans teams](identify-models-authentication.md) et
- [Configurez Azure Active Directory pour teams et Skype entreprise](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect).

Une [topologie hybride Skype entreprise](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) n’est pas requise, mais nous vous recommandons de le faire. Certaines fonctionnalités telles que le service de migration des réunions et l’interopérabilité s’appuient sur cette topologie.

Les réunions sont d’abord prises en charge avec n’importe quelle version de Skype entreprise Server (et connues de l’utilisation du serveur Lync non pris en charge). Ce service est pris en charge avec n’importe quel client Skype entreprise pris en charge, mais les fonctionnalités de meilleure ensemble nécessitent un client récent.

Une fois ces exigences satisfaites (et non antérieures), les utilisateurs peuvent être [titulaires d’une licence pour Microsoft 365 ou Office 365 et équipes](https://docs.microsoft.com/office365/enterprise/assign-licenses-to-user-accounts).

Pour la première utilisation de réunions, les utilisateurs doivent être activés pour [Exchange Online](exchange-teams-interact.md), [SharePoint Online et OneDrive entreprise](sharepoint-onedrive-interact.md), et la création de groupes Microsoft 365. Les réunions sont tout d’abord prises en charge pour les utilisateurs dont la boîte aux lettres est située en local, ou qui n’ont pas SharePoint Online ou OneDrive entreprise, ou la création de groupes Microsoft 365. Toutefois, leur interface sera moins complète. Par exemple, dans le cas d’organisations utilisant Exchange Server en local, il est possible (en fonction de la version d’Exchange Server) certaines limitations de création et d’affichage de réunions à partir du client Teams, ainsi que des fonctionnalités de conformité.

Pour le moment, les utilisateurs doivent disposer [d’une licence pour teams](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users). De plus, ils peuvent être dotés d’une licence pour les [conférences audio](set-up-audio-conferencing-in-teams.md), si nécessaire.

Nous vous recommandons d' [octroyer le mode **SfBOnly** ou **SfBWithTeamsCollab** ](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) comme client par défaut au moment où vous attribuez une licence aux utilisateurs. Cela permet de garantir que les utilisateurs ne peuvent pas utiliser les équipes par défaut dans le mode par défaut de l' **îlot** avant de pouvoir lancer des réunions en premier.

Les réunions sont d’abord prises en charge sur les clients de bureau complets (Windows et Mac), sur les clients de navigateur et sur les clients mobiles. Il est également compatible avec les [salles de Microsoft teams](https://docs.microsoft.com/microsoftteams/room-systems/). L’utilisation conjointe nécessite le client de bureau complet.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Commencer par organiser des réunions teams

Pour permettre à vos utilisateurs d’avoir la meilleure utilisation possible dans les réunions d’équipe, vous devez :

- Pour plus d’informations, suivez les étapes décrites dans [réunions et conférences pour Microsoft teams](deploy-meetings-microsoft-teams-landing-page.md).
- [Évaluez votre environnement](3-envision-evaluate-my-environment.md).
- [Préparez le réseau de votre organisation à Microsoft teams](prepare-network.md).
- Effectuez la mise à niveau de vos salles de réunion avec les [appareils et les solutions de salle de réunion](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)compatibles avec Teams, ou utilisez la fonction [Cloud Video Interop pour Microsoft teams](cloud-video-interop.md) pour permettre à vos salles et périphériques tiers d’accéder à des réunions d’équipe.
- Équiper vos utilisateurs de [périphériques audio et vidéo USB certifiés](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).
- Préparer la prise en charge de la [sensibilisation et de l’adoption des réunions teams](adopt-microsoft-teams-landing-page.md).
- [Planifiez la gestion de votre service](4-envision-plan-my-service-management.md).
- Familiarisez-vous avec les rapports d’analyse des appels enrichis pour [résoudre les problèmes de mauvaise qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md).

Vous pouvez envisager d’exécuter un pilote de production à échelle modérée à ce stade.

## <a name="configure-users-for-meetings-first"></a>Configurer d’abord les utilisateurs pour les réunions

Une fois que vous avez fourni une licence aux utilisateurs et que vous avez préparé votre organisation pour les réunions Teams, il est temps de commencer par activer vos utilisateurs pour les réunions. C’est facile : un seul paramètre est le tout.

Toutes les fonctionnalités et les expériences utilisateur des réunions d’abord, y compris la configuration du client teams et la [conformité automatique](teams-client-experience-and-conformance-to-coexistence-modes.md) de l’expérience utilisateur, du service de migration des réunions et de l’ensemble des fonctionnalités, sont configurées en accordant l’utilisateur (ou groupe d’utilisateurs, ou par défaut) le [mode de coexistence SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md) dans le [Centre d’administration Microsoft teams](manage-teams-in-modern-portal.md) ou en utilisant [PowerShell](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).

![Capture d’écran des paramètres d’administration permettant d’activer d’abord des réunions](media/teams-meeting-admin-settings.png)

Si vous le souhaitez, vous pouvez également masquer l’application équipes et canaux à partir du volet de navigation gauche du client teams de vos utilisateurs afin de concentrer davantage sur l’utilisation des réunions à l’aide de la [stratégie d’autorisation des applications](teams-app-permission-policies.md).

## <a name="reporting-and-call-analytics"></a>Création de rapports et analyse des appels

La création de rapports et l’analyse des appels pour les réunions teams dans les réunions ne sont pas modifiées par rapport aux autres modes.

## <a name="related-links"></a>Liens connexes

Après avoir examiné cet article, vous souhaiterez peut-être vous reporter à la rubrique choix de votre guide de [mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), de la [migration et de l’interopérabilité](migration-interop-guidance-for-teams-with-skype.md), et de la [coexistence avec Skype entreprise](coexistence-chat-calls-presence.md) pour plus d’informations.


