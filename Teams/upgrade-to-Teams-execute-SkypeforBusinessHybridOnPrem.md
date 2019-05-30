---
title: Effectuer la mise à niveau vers Teams à partir d’un déploiement hybride ou local de Skype Entreprise - Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Remarques concernant la mise à niveau vers teams à partir d’une version hybride ou d’un déploiement local de Skype entreprise.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 118bae776f4bb3709d62dea1f384ccaa0707397b
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493978"
---
![Diagramme de parcours de mise à niveau, mise en évidence du déploiement et de l’implémentation] (media/upgrade-banner-deployment.png "Étapes du parcours de la mise à niveau, mettant l’accent sur l’étape de déploiement et d’implémentation")

Cet article fait partie de l’étape de déploiement et d’implémentation de votre parcours de mise à niveau. Avant de continuer, confirmez que vous avez terminé les activités suivantes:

-   [Inscription des parties prenantes du projet](upgrade-enlist-stakeholders.md)
-   [Définition de l’objectif de votre projet](https://aka.ms/SkypetoTeams-Scope)
-   [Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes](https://aka.ms/SkypeToTeams-Coexist)
-   [Choix de votre mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Préparé votre environnement](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Préparé votre organisation](https://aka.ms/SkypeToTeams-UserReadiness)
-   [A mené une pilote](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a>Effectuer une mise à niveau vers teams depuis un déploiement hybride ou local Skype entreprise

Suivez les recommandations de cet article si vous avez déployé Skype entreprise ou Microsoft Lync en local et que votre organisation souhaite effectuer une mise à niveau vers des équipes de manière sélective, en utilisant plusieurs modes de coexistence, ou tout le tout. La première étape consiste à configurer la connectivité hybride avec votre client Office 365, puis à déplacer vos utilisateurs vers Skype entreprise Online et à leur affecter le mode de coexistence et de mise à niveau appropriés. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Étape 1: déployer une connectivité hybride 

La configuration minimale requise pour la mise à niveau de vos utilisateurs vers teams consiste à déployer une connectivité hybride. Cela peut impliquer le déploiement de nouvelles connexions externes pour votre déploiement Skype entreprise ou Lync, ou la configuration d’une relation hybride avec votre client Office 365. 

Pour plus d’informations, reportez-vous à la section déploiement d’une [connectivité hybride entre Skype entreprise Server et Skype entreprise Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).

## <a name="step-2-move-users-to-skype-for-business-online"></a>Étape 2: déplacer des utilisateurs vers Skype entreprise Online 

Lorsque vous avez terminé la configuration hybride, déplacez les utilisateurs vers Skype entreprise online. 

Pour plus d’informations, reportez-vous à la rubrique [déplacer des utilisateurs de local vers Skype entreprise Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online). 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a>Étape 3: affecter une coexistence et un mode de mise à niveau

Après avoir déplacé vos utilisateurs vers Skype entreprise Online, vous pouvez leur affecter le mode de coexistence approprié en fonction du parcours de mise à niveau choisi par votre organisation. Pour plus d’informations, reportez-vous à [définition de votre coexistence et de vos paramètres de mise à](https://aka.ms/SkypeToTeams-SetCoexistence) [TeamsUpgradePolicy: gestion de la migration et de](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)la coexistence.

> [!NOTE]
> Avec Skype entreprise Server 2019 et une prochaine mise à jour cumulative de Skype entreprise Server 2015, vous serez en mesure de passer à l’étape 2 (déplacer les utilisateurs vers Skype entreprise Online) et à l’étape 3 (mettre à niveau les utilisateurs vers les équipes) en une seule étape. Des informations supplémentaires seront fournies après le lancement de Skype entreprise Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Mise à niveau du système téléphonique et des équipes

Si vous migrez votre déploiement hybride Skype entreprise vers votre système téléphonique avec des plans d’appels, Microsoft sera votre fournisseur de réseau téléphonique commuté (PSTN), et en supposant que vous avez terminé le transfert du numéro de téléphone, la mise à niveau de vos utilisateurs vers Teams va automatiquement migrer les appels RTC entrants vers Teams.

Si les plans d’appel ne sont pas disponibles, vous devez migrer votre déploiement voix entreprise vers le routage direct du système Microsoft Phone. Pour mettre à niveau vos utilisateurs vers Teams, reportez-vous à la rubrique [Considérations supplémentaires sur le routage direct du système téléphonique](2-envision-make-my-service-decisions-direct-routing.md).
