---
title: Mise à niveau Skype pour les entreprises en ligne pour les équipes Microsoft | Déployer
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considérations relatives à la mise à niveau pour les équipes de Skype pour Business Online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 82577b8e8102baca9ea9681bb94d4a0c73f8b01e
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30465155"
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

# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Mise à niveau à partir de Skype pour les entreprises en ligne aux équipes

Suivez les instructions de cet article si vous avez déployé entièrement Skype pour Business Online et que vous souhaitez mettre à niveau vos utilisateurs à partir de Skype pour les entreprises aux équipes. Vous pouvez mettre à niveau les utilisateurs sélectivement ou tout en, en fonction de la mise à niveau de route que votre organisation a choisi, en affectant le mode de mise à niveau et la coexistence appropriée à vos utilisateurs.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Affecter le mode de mise à niveau et de coexistence

Vous pouvez mettre à niveau vos utilisateurs par les équipes en affectant le mode TeamsOnly de TeamsUpgradePolicy, qui peut être effectuée à l’aide du centre d’administration Microsoft Teams ou un Skype pour la session Windows Powershell à distance Business.

Pour plus d’informations, voir [configuration de votre coexistence et de paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence) et [TeamsUpgradePolicy : gestion de migration et coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Mettre à niveau simultanément tous les utilisateurs à des équipes

Suivez ces étapes pour mettre à niveau tous les utilisateurs à des équipes en même temps.

### <a name="step-1-notify-the-users-of-the-change"></a>Étape 1 : Avertir les utilisateurs de la modification

1. Dans le centre d’administration Microsoft Teams, sélectionnez **paramètres à l’échelle de la société** > **équipes de mise à niveau**.
2. Sous **mode de Coexistence**, remplacez le commutateur **Skype de notification pour les utilisateurs qu’une mise à niveau pour les équipes est disponible** **sur**.

### <a name="step-2-set-the-coexistence-mode-for-the-users"></a>Étape 2 : Définir le mode de coexistence pour les utilisateurs

1. Dans le centre d’administration Microsoft Teams, sélectionnez **paramètres de l’organisation**.
2. Sélectionnez mode **d’Équipes uniquement** à partir de la liste déroulante **mode de Coexistence** .

## <a name="upgrade-users-in-stages"></a>Mise à niveau par étapes

Si vous souhaitez mise à niveau progressive de vos utilisateurs à des équipes, procédez comme suit.

### <a name="step-1-create-your-user-cohorts-for-the-upgrade"></a>Étape 1 : Créer votre cohortes utilisateur pour la mise à niveau

Cohortes utilisateur sont des groupes d’utilisateurs qui seront déplacées vers le mode équipes uniquement en même temps.

Pour créer votre cohortes utilisateur (ajouter un lien vers la page de sélection de l’utilisateur)

### <a name="step-2-set-the-user-mode-to-islands"></a>Étape 2 : Définir le mode utilisateur pour (îles)

1. Dans le centre d’administration Microsoft Teams, sélectionnez **utilisateurs**, puis sélectionnez un cohorte utilisateur.
2. En regard de **mise à niveau des équipes**, sélectionnez **Modifier**.
3. Dans le volet de **Mise à niveau des équipes** , sous **mode de Coexistence**, sélectionnez **(îles)** dans la liste déroulante.

### <a name="step-3-set-notification-for-the-user-optional"></a>Étape 3 : Configurer la notification de l’utilisateur (facultatif)

1. Dans le centre d’administration Microsoft Teams, sélectionnez **les utilisateurs**et sélectionnez un cohorte utilisateur.
2. En regard de **mise à niveau des équipes**, sélectionnez **Modifier**.
3. Dans le volet de **Mise à niveau des équipes** , sous **mode de Coexistence**, modifier commutateur **notifier le Skype pour utilisateur professionnel** **activé**.

### <a name="step-4-set-the-user-mode-to-teams-only"></a>Étape 4 : Définissez le mode utilisateur pour les équipes uniquement

Lorsque vous êtes prêt à mettre à niveau des utilisateurs afin d’utiliser des équipes comme leur application uniquement, définissez le mode de Coexistence pour l’utilisateur d’équipes uniquement.

1. Dans le centre d’administration Microsoft Teams, sélectionnez **utilisateurs**, puis sélectionnez un cohorte utilisateur.
2. En regard de **mise à niveau des équipes**, sélectionnez **Modifier**.
3. Dans le volet de **Mise à niveau des équipes** , sous **mode de Coexistence**, sélectionnez **Équipes uniquement** dans la liste déroulante.

## <a name="phone-system-and-teams-upgrade"></a>Mise à niveau système téléphonique et les équipes

Si votre Skype pour le déploiement d’entreprise en ligne inclut le système téléphonique avec des Plans de l’appel et Microsoft est votre fournisseur de réseau téléphonique commuté, la mise à niveau de vos utilisateurs à des équipes passera automatiquement PSTN entrant aux équipes de l’appel.

Si votre Skype pour le déploiement d’entreprise en ligne comprend un système téléphonique avec le nuage connecteur Edition, consultez les [Considérations supplémentaires pour le routage d’un système téléphonique directe](2-envision-make-my-service-decisions-direct-routing.md).