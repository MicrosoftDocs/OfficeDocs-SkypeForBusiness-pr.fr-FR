---
title: Mise à niveau à partir de Skype pour les entreprises en ligne aux équipes - équipes Microsoft
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considérations relatives à la mise à niveau pour les équipes de Skype pour Business Online
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: c910a9a206f93b56e5768498fa9e036132b9c368
ms.sourcegitcommit: b45077dd1b5d366fa9a30698aa66ed4b13264eee
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/25/2018
ms.locfileid: "21148153"
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


# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Mise à niveau à partir de Skype pour les entreprises en ligne aux équipes

Suivez les instructions de cet article si vous avez déployé entièrement Skype pour Business Online et que vous souhaitez mettre à niveau vos utilisateurs à partir de Skype pour les entreprises aux équipes. Vous pouvez mettre à niveau les utilisateurs sélectivement ou tout en, en fonction de la mise à niveau de route que votre organisation a choisi, en affectant le mode de mise à niveau et la coexistence appropriée à vos utilisateurs.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Affecter le mode de mise à niveau et de coexistence

Mise à niveau vers les équipes permettre faire en affectant le mode TeamsOnly de TeamsUpgradePolicy, qui peut être effectuée à l’aide de Microsoft Teams & Skype pour Business Admin Center ou un Skype pour la session Windows Powershell à distance Business.

Pour plus d’informations, voir [configuration de votre coexistence et de paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence) et [TeamsUpgradePolicy : gestion de migration et coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

## <a name="phone-system-and-teams-upgrade"></a>Mise à niveau système téléphonique et les équipes

Si votre Skype pour le déploiement d’entreprise en ligne inclut le système téléphonique avec des Plans de l’appel et Microsoft est votre fournisseur de réseau téléphonique commuté, la mise à niveau de vos utilisateurs à des équipes passera automatiquement PSTN entrant aux équipes de l’appel.

Si votre Skype pour le déploiement d’entreprise en ligne comprend un système téléphonique avec le nuage connecteur Edition, consultez les [Considérations supplémentaires pour le routage d’un système téléphonique directe](2-envision-make-my-service-decisions-direct-routing.md).