---
title: Mise à niveau Skype pour les entreprises en ligne pour les équipes Microsoft | Déployer
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: 6748397c354f9238282f9646388993fc0e9f7b88
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902718"
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

# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Mise à niveau de Skype Entreprise Online vers Teams

Suivez les instructions de cet article si vous avez déployé entièrement Skype pour Business Online et que vous souhaitez mettre à niveau vos utilisateurs à partir de Skype pour les entreprises aux équipes. Vous pouvez mettre à niveau les utilisateurs sélectivement ou tout en, en fonction de la mise à niveau de route que votre organisation a choisi, en affectant le mode de mise à niveau et la coexistence appropriée à vos utilisateurs.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Affecter le mode de mise à niveau et de coexistence

Vous pouvez mettre à niveau vos utilisateurs en mode TeamsOnly en affectant l’instance UpgradeToTeams de TeamsUpgradePolicy, qui peut être effectuée à l’aide du centre d’administration Microsoft Teams ou un Skype pour la session Windows Powershell à distance Business. Vous pouvez le faire par utilisateur, soit sur un client à l’échelle si vous souhaitez de mise à niveau du client entier en une seule étape. 

Pour plus d’informations, voir [configuration de votre coexistence et de paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence) et [TeamsUpgradePolicy : gestion de migration et coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Mettre à niveau simultanément tous les utilisateurs à des équipes

Suivez ces étapes pour mettre à niveau tous les utilisateurs à des équipes en même temps.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Étape 1 : Avertir les utilisateurs de la modification (facultative)

1. Dans le centre d’administration Microsoft Teams, sélectionnez **paramètres à l’échelle de la société** > **équipes de mise à niveau**.
2. Sous **mode de Coexistence**, remplacez le commutateur **Skype de notification pour les utilisateurs qu’une mise à niveau pour les équipes est disponible** **sur**.

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Étape 2 : Définir le mode de coexistence pour TeamsOnly pour l’organisation

1. Dans le centre d’administration Microsoft Teams, sélectionnez **paramètres de l’organisation**.
2. Sélectionnez mode **d’Équipes uniquement** à partir de la liste déroulante **mode de Coexistence** .

## <a name="upgrade-users-in-stages"></a>Mise à niveau par étapes

Si vous souhaitez mettre à niveau progressive vos utilisateurs vers TeamsOnly, procédez comme suit.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Étape 1 : Identifier les groupes d’utilisateurs pour la mise à niveau

Souvent, les organisations peuvent choisir de mettre à niveau leurs organisations vagues de réussite des utilisateurs.  Vous souhaiterez identifier ces utilisateurs en premier afin que vous pouvez facilement les rechercher dans le centre d’administration Microsoft Teams. Vous pouvez également utiliser PowerShell pour effectuer cette opération plus efficacement. Une fois que vous avez identifié l’ensemble des utilisateurs d’une vague de mise à niveau donnée, continuez avec les étapes restantes.

### <a name="step-2-set-notification-for-the-users-in-the-current-ugprade-wave-optional"></a>Étape 2 : Configurer la notification pour les utilisateurs de la vague de mise à niveau en cours (facultatif)

Si vous utilisez le centre d’administration Microsoft Teams, vous pouvez configurer pour l’utilisateur jusqu'à 20 des TeamsUpgradePolicy :
1. Dans le centre d’administration Microsoft Teams, sélectionnez **les utilisateurs**et de rechercher et de sélectionner plusieurs la case à cocher pour jusqu'à 20 utilisateurs qui doivent être mis à niveau. 
2. Dans le coin supérieur gauche de la liste affichée, sélectionnez **Modifier les paramètres** . 
3. Dans le volet de droite, sous **mise à niveau des équipes**, **Modifier les paramètres** modifier commutateur **notifier le Skype pour utilisateur professionnel** **activé**. Remarque : Si la valeur du mode de coexistence est « paramètres d’utilisation à l’échelle de l’organisation », vous ne verrez pas ce commutateur, il vous faudra donc tout d’abord définir explicitement le mode de Coexistence pour les utilisateurs à tout ce qui est la valeur par défaut pour l’organigramme.

Autrement, il peut plus facile activer les notifications pour les groupes d’utilisateurs à la fois à l’aide de PowerShell. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Étape 3 : Définir le mode de coexistence pour les utilisateurs à des équipes uniquement

Lorsque vous êtes prêt à mettre à niveau les utilisateurs de la génération actuelle pour utiliser des équipes comme leur application uniquement, définissez le mode de Coexistence pour les utilisateurs à des équipes uniquement.

Si vous utilisez le centre d’administration Microsoft Teams, vous pouvez configurer pour l’utilisateur jusqu'à 20 des TeamsUpgradePolicy :
1. Dans le centre d’administration Microsoft Teams, sélectionnez **les utilisateurs**, puis activez la case à cocher pour jusqu'à 20 utilisateurs.
2. Dans le coin supérieur gauche de la liste affichée, sélectionnez **Modifier les paramètres** .
3. Dans le volet **Modifier les paramètres** sur la droite, sous la section **mise à niveau des équipes** , définissez le mode de coexistence pour **Les équipes uniquement** dans la liste déroulante.

Sinon, vous souhaiterez plus faciles à mettre à niveau des groupes d’utilisateurs à la fois à l’aide de PowerShell. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Étape 4 : Répétez les étapes 1 à 3 pour par vagues successives d’utilisateurs

Lorsque vous validez votre mise à niveau vers le mode équipes uniquement et que vous êtes prêt à développer, répétez les étapes précédentes pour appliquer TeamsOnly à d’autres utilisateurs.  


## <a name="phone-system-and-teams-upgrade"></a>Mise à niveau système téléphonique et les équipes

Si votre Skype pour le déploiement d’entreprise en ligne inclut le système téléphonique avec des Plans de l’appel et Microsoft est votre fournisseur de réseau téléphonique commuté, la mise à niveau de vos utilisateurs à des équipes passera automatiquement PSTN entrant aux équipes de l’appel.

Si votre Skype pour le déploiement d’entreprise en ligne comprend un système téléphonique avec le nuage connecteur Edition, consultez les [Considérations supplémentaires pour le routage d’un système téléphonique directe](2-envision-make-my-service-decisions-direct-routing.md).
