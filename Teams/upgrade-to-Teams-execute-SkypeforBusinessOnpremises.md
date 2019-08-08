---
title: Mise à niveau de Skype entreprise sur site vers Microsoft teams | Déployer | Lync
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Remarques concernant la mise à niveau vers teams à partir d’un déploiement local de Skype entreprise.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f234c6fe959d35d2f92e117e28af8d15f0a02819
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235897"
---
![Étapes du parcours de la mise à niveau, mettant l’accent sur l’étape de déploiement et d’implémentation] (media/upgrade-banner-deployment.png "Étapes du parcours de la mise à niveau, mettant l’accent sur l’étape de déploiement et d’implémentation")

Cet article fait partie de l’étape de déploiement et d’implémentation de votre parcours de mise à niveau. Avant de continuer, confirmez que vous avez terminé les activités suivantes:

- [Inscription des parties prenantes du projet](upgrade-enlist-stakeholders.md)
- [Définition de l’objectif de votre projet](https://aka.ms/SkypetoTeams-Scope)
- [Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes](https://aka.ms/SkypeToTeams-Coexist)
- [Choix de votre mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Préparé votre environnement](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Préparé votre organisation](https://aka.ms/SkypeToTeams-UserReadiness)
- [A mené une pilote](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Effectuer une mise à niveau d’un déploiement local de Skype entreprise vers teams

Suivez les recommandations de cet article si vous avez déployé Skype entreprise ou Microsoft Lync en local et que votre organisation souhaite effectuer une mise à niveau vers Microsoft teams de manière sélective, à l’aide de plusieurs modes de coexistence (ou tout le tout). 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Étape 1: déployer une connectivité hybride

La configuration minimale requise pour la mise à niveau de vos utilisateurs vers teams consiste à déployer une connectivité hybride.

Pour plus d’informations, reportez-vous à la section déploiement d’une [connectivité hybride entre Skype entreprise Server et Skype entreprise Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Étape 2: implémenter le voyage de mise à niveau choisi pour votre organisation

Une fois que vous avez terminé la configuration hybride, vous pouvez planifier la migration de vos utilisateurs vers Office 365.

Pour plus d’informations, consultez:

- [TeamsUpgradePolicy: gestion de la migration et de](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)la coexistence.

- [Déplacez les utilisateurs de local vers Skype entreprise Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="phone-system-and-teams-upgrade"></a>Mise à niveau du système téléphonique et des équipes

Le passage des systèmes téléphoniques locaux à teams vous permet de tirer parti du routage direct du système téléphonique («routage directe») ou des offres d’appels fournies par Microsoft pour Office 365.

Si vous n’utilisez pas les forfaits d’appels dans Office 365, vous devez faire basculer votre déploiement de voix entreprise vers le routage direct du système téléphonique dans le cadre de la mise à niveau vers Teams.

Pour plus d’informations, reportez-vous [à considérations supplémentaires sur le routage direct du système téléphonique](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing). Si vous envisagez d’utiliser des plans d’appel dans Office 365, consultez nos recommandations pour [le transfert de vos numéros de téléphone vers office 365](https://docs.microsoft.com/microsoftteams/transfer-phone-numbers-to-office-365).