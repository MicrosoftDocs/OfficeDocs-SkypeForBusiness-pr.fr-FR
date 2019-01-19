---
title: Mise à niveau Skype pour déploiement hybride Business Teams Microsoft | PSTN
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considérations relatives à la mise à niveau aux équipes un Skype pour un déploiement hybride Business.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: c78c5b519997c125dc1902021acabe664ea03047
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349574"
---
![Étapes du voyage mise à niveau, en mettant l’accent sur le déploiement et la phase d’implémentation] (media/upgrade-banner-deployment.png "Étapes du voyage mise à niveau, en mettant l’accent sur le déploiement et la phase d’implémentation")

Cet article fait partie de la phase de déploiement et l’implémentation de votre parcours de mise à niveau. Avant de continuer, vérifiez que vous avez effectué les activités suivantes :

- [Inscrit les parties prenantes du projet](upgrade-enlist-stakeholders.md)
- [Définies par l’étendue de votre projet](https://aka.ms/SkypetoTeams-Scope)
- [Comprendre la coexistence et l’interopérabilité de Skype pour professionnels et les équipes](https://aka.ms/SkypeToTeams-Coexist)
- [Choisi votre parcours de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Préparer votre environnement](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Préparation de votre organisation](https://aka.ms/SkypeToTeams-UserReadiness)
- [Mené un projet pilote](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Mise à niveau à partir d’un Skype pour un déploiement hybride Business aux équipes

Suivez les instructions de cet article si vous avez déployé Skype pour les entreprises ou Microsoft Lync sur site et configuré dans un déploiement hybride avec votre client Office 365 et que votre organisation souhaite mettre à niveau vers les équipes soit sélectivement — en utilisant plusieurs modes de coexistence, ou tout en. Pour un parcours de mise à niveau, vous devez atteindre vos utilisateurs Skype pour Business Online (s’ils ne sont pas déjà hébergés en ligne), puis les affecter le mode de mise à niveau et la coexistence appropriée.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Étape 1 : Déplacer les utilisateurs vers Skype pour Business Online

Cette étape s’applique aux utilisateurs qui sont actuellement hébergés sur un système local. Pour plus d’informations sur le déplacement de ces utilisateurs vers Skype pour Business Online, voir [déplacer des utilisateurs à partir de sur - local à Skype pour Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Étape 2 : Attribuer une coexistence et le mode de mise à niveau

Une fois que vous avez déplacé vos utilisateurs à Skype pour Business Online, vous pouvez affecter le mode de coexistence approprié en fonction de la mise à niveau voyage que votre organisation a choisi. Pour plus d’informations, voir [configuration de votre coexistence et de paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence) et [TeamsUpgradePolicy : gestion de migration et coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

> [!NOTE]
> Avec Skype pour Business Server 2019 et une mise à jour cumulative futur de Skype pour Business Server 2015, vous serez en mesure d’effectuer l’étape 1 (déplacement d’utilisateurs vers Skype pour Business Online) et l’étape 2 (mise à niveau des utilisateurs aux équipes) en une seule étape. Vous trouverez plus d’informations après la sortie de Skype pour Business Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Mise à niveau système téléphonique et les équipes

Si vous passez vos Skype pour un déploiement hybride Business au système téléphonique avec des Plans de l’appel de Microsoft sera votre fournisseur de réseau téléphonique commuté — et en supposant que vous avez terminé le portage numéro de téléphone : mise à niveau de vos utilisateurs Les équipes passera automatiquement PSTN entrant aux équipes de l’appel.

Si des Plans de l’appel n’est pas disponible ou que vous comptez utiliser votre fournisseur de connectivité PSTN existante, vous devez effectuer la transition de votre déploiement d’enterprise voice, ou déploiement de voix hybride qui utilise votre local déploiement ou dans le nuage connecteur Edition — à Routage Direct système téléphonique de Microsoft. Pour mettre à niveau vos utilisateurs à des équipes, voir les [Considérations supplémentaires pour le routage d’un système téléphonique directe](2-envision-make-my-service-decisions-direct-routing.md).
