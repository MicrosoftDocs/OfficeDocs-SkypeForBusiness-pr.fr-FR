---
title: Mise à niveau à partir d’un Skype pour le déploiement local de Business aux équipes - Microsoft Teams
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considérations relatives à la mise à niveau aux équipes un Skype pour Business déploiement local.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: c70ef403754bcf64fe757ea2a5290229e4426513
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887633"
---
![Étapes du voyage mise à niveau, en mettant l’accent sur le déploiement et la phase d’implémentation] (media/upgrade-banner-deployment.png "Étapes du voyage mise à niveau, en mettant l’accent sur le déploiement et la phase d’implémentation")

Cet article fait partie de la phase de déploiement et l’implémentation de votre parcours de mise à niveau. Avant de continuer, vérifiez que vous avez effectué les activités suivantes :

-   [Inscrit les parties prenantes du projet](upgrade-enlist-stakeholders.md)
-   [Définies par l’étendue de votre projet](https://aka.ms/SkypetoTeams-Scope)
-   [Comprendre la coexistence et l’interopérabilité de Skype pour professionnels et les équipes](https://aka.ms/SkypeToTeams-Coexist)
-   [Choisi votre parcours de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Préparer votre environnement](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Préparation de votre organisation](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Mené un projet pilote](https://aka.ms/SkypeToTeams-Pilot)


# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Mise à niveau à partir d’un Skype pour le déploiement local de Business aux équipes

Suivez les instructions de cet article si vous avez déployé Skype pour les entreprises ou Microsoft Lync sur site et votre organisation souhaite mettre à niveau vers les équipes soit sélectivement — à l’aide de plusieurs modes de coexistence, ou tout en. La première étape consiste à configurer la connectivité hybride avec votre client Office 365, puis déplacer les utilisateurs vers Skype pour Business Online et affecter la coexistence appropriée et le mode de mise à niveau.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Étape 1 : Déploiement de connectivité hybride

Les éléments prérequis clés pour la mise à niveau de vos utilisateurs à des équipes consiste à déployer la connectivité hybride. Cela peut impliquer le déploiement de nouvelles connectivité externe pour votre Skype existant pour le déploiement de Lync ou de l’entreprise, ou la configuration simplement une relation hybride avec votre client Office 365.

Pour plus d’informations, voir [déployer la connectivité hybride entre Skype pour Business Server et Skype pour Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-move-users-to-skype-for-business-online"></a>Étape 2 : Déplacer les utilisateurs vers Skype pour Business Online

Une fois que vous avez terminé votre configuration hybride, déplacer des utilisateurs vers Skype pour Business Online. 

Pour plus d’informations, voir [déplacer des utilisateurs à partir de sur site à Skype pour Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a>Étape 3 : Attribuer une coexistence et le mode de mise à niveau

Une fois que vous avez déplacé vos utilisateurs à Skype pour Business Online, vous pouvez affecter le mode de coexistence approprié en fonction de la mise à niveau voyage que votre organisation a choisi. Pour plus d’informations, voir [configuration de votre coexistence et de paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence) et [TeamsUpgradePolicy : gestion de migration et coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

> [!NOTE]
> Avec Skype pour Business Server 2019 et une mise à jour cumulative futur de Skype pour Business Server 2015, vous serez en mesure d’effectuer l’étape 2 (déplacement d’utilisateurs vers Skype pour Business Online) et l’étape 3 (mise à niveau des utilisateurs aux équipes) en une seule étape. Vous trouverez plus d’informations après la sortie de Skype pour Business Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Mise à niveau système téléphonique et les équipes

Si vous passez vos Skype pour le déploiement local de Business de voix entreprise au système téléphonique avec des Plans de l’appel de Microsoft sera votre fournisseur de réseau téléphonique commuté — et en supposant que vous avez terminé le numéro de téléphone portage : mise à niveau de vos utilisateurs à des équipes passera automatiquement aux appels PSTN entrants aux équipes.

Si des Plans de l’appel n’est pas disponible, vous devez effectuer la transition de votre déploiement d’enterprise voice au routage Direct de Microsoft Phone System. Pour mettre à niveau vos utilisateurs à des équipes, voir les [Considérations supplémentaires pour le routage d’un système téléphonique directe](2-envision-make-my-service-decisions-direct-routing.md).