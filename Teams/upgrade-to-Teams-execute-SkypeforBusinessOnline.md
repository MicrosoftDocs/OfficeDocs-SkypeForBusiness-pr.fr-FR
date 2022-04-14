---
title: Effectuer une mise à niveau de Skype Entreprise Online vers Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Découvrez comment mettre à niveau votre organisation vers Microsoft Teams à partir d’un déploiement Skype Entreprise Online.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 49376910ce9ca0f777533e950600a19bd440c27f
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2022
ms.locfileid: "64846553"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Mise à niveau de Skype Entreprise Online vers Teams

![Diagramme de parcours de mise à niveau, mettant l’accent sur le déploiement et l’implémentation.](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, en mettant l’accent sur la phase de déploiement et d’implémentation")

Cet article fait partie de l’étape déploiement et implémentation de votre parcours de mise à niveau. Avant de continuer, vérifiez que vous avez terminé les activités suivantes :

- [Inscription des parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
- [Définition de l’étendue de votre projet](./upgrade-define-project-scope.md)
- [Compréhension de la coexistence et de l’interopérabilité des Skype Entreprise et des Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Choix de votre parcours de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Préparer votre environnement](./upgrade-prepare-environment.md)
- [Préparation de votre organisation](./upgrade-prepare-organization.md)
- [Conduite d’un projet pilote](./pilot-essentials.md)

Suivez les instructions de cet article si vous avez entièrement déployé Skype Entreprise Online et souhaitez mettre à niveau vos utilisateurs de Skype Entreprise vers Teams. Vous pouvez mettre à niveau les utilisateurs de manière sélective ou intégrale, en fonction du parcours de mise à niveau choisi par votre organisation, en attribuant le mode de coexistence et de mise à niveau approprié à vos utilisateurs.

> [!IMPORTANT]
> Skype Entreprise Online a pris sa retraite le 31 juillet 2021. Pour optimiser la réalisation des avantages et vous assurer que votre organisation dispose du temps nécessaire pour implémenter votre mise à niveau, nous vous encourageons à commencer votre parcours vers Microsoft Teams aujourd’hui. N’oubliez pas qu’une mise à niveau réussie aligne l’état de préparation technique et utilisateur. Veillez donc à tirer parti des conseils qui s’y rapportent lorsque vous naviguez vers Microsoft Teams.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Attribuer le mode de coexistence et de mise à niveau

Vous pouvez mettre à niveau vos utilisateurs vers le mode TeamsOnly en affectant l’instance UpgradeToTeams de TeamsUpgradePolicy, qui peut être effectuée à l’aide du centre d’administration Microsoft Teams ou d’une session Windows PowerShell distante Skype Entreprise. Vous pouvez effectuer cette opération par utilisateur ou à l’échelle du locataire si vous souhaitez mettre à niveau l’intégralité du locataire en une seule étape. 

Pour plus d’informations, consultez [Définir vos paramètres de coexistence et de mise à niveau](./setting-your-coexistence-and-upgrade-settings.md) et [TeamsUpgradePolicy : gestion de la migration et de la coexistence](upgrade-to-teams-on-prem-tools.md).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Mettre à niveau tous les utilisateurs vers Teams en même temps

Suivez ces étapes pour mettre à niveau tous vos utilisateurs vers Teams en même temps.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Étape 1 : Informer les utilisateurs de la modification (facultatif)

1. Dans le centre d’administration Microsoft Teams, sélectionnez **Teams** >  **Teams paramètres de mise à niveau**.
2. En **mode Coexistence**, **modifiez l’option Informer Skype Entreprise utilisateurs qu’une mise à niveau vers Teams est disponible**.

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Étape 2 : Définir le mode de coexistence sur TeamsOnly pour l’organisation

1. Dans le centre d’administration Microsoft Teams, sélectionnez **Teams** >  **Teams paramètres de mise à niveau**.
2. Sélectionnez **Teams mode uniquement** dans la liste déroulante **mode coexistence**.

## <a name="upgrade-users-in-stages"></a>Mettre à niveau les utilisateurs par étapes

Suivez ces étapes si vous souhaitez mettre à niveau progressivement vos utilisateurs vers TeamsOnly.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Étape 1 : Identifier les groupes d’utilisateurs à mettre à niveau

Souvent, les organisations peuvent choisir de mettre à niveau leurs organisations par vagues de réussite d’utilisateurs.  Vous devez d’abord identifier ces utilisateurs pour pouvoir facilement les rechercher dans le centre d’administration Microsoft Teams. Vous pouvez également utiliser PowerShell pour effectuer cette opération plus efficacement. Une fois que vous avez identifié l’ensemble d’utilisateurs pour une vague de mise à niveau donnée, passez aux étapes restantes.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Étape 2 : Définir une notification pour les utilisateurs dans la vague de mise à niveau actuelle (facultatif)

Si vous utilisez le centre d’administration Microsoft Teams, vous pouvez configurer TeamsUpgradePolicy pour jusqu’à 20 utilisateurs à la fois :
1. Dans le centre d’administration Microsoft Teams, sélectionnez **Utilisateurs**, puis recherchez et cochez la case pour jusqu’à 20 utilisateurs qui doivent être mis à niveau. 
2. Sélectionnez **Modifier les paramètres** dans le coin supérieur gauche de l’affichage de liste. 
3. Dans le volet **Modifier les paramètres** à droite, sous **Teams mise à niveau**, **modifiez Notifier le Skype Entreprise commutateur utilisateur** **sur Activé**. Remarque : Si la valeur du mode de coexistence est « Utiliser les paramètres à l’échelle de l’organisation », vous ne verrez pas ce commutateur. Vous devez donc d’abord définir explicitement le mode de coexistence pour ces utilisateurs sur la valeur par défaut de l’organisation.

Vous pouvez également trouver plus facile d’activer des notifications pour des groupes d’utilisateurs à la fois à l’aide de PowerShell. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Étape 3 : Définir le mode de coexistence pour que les utilisateurs Teams uniquement

Lorsque vous êtes prêt à mettre à niveau les utilisateurs de la vague actuelle pour utiliser Teams comme seule application, définissez le mode coexistence pour les utilisateurs sur Teams uniquement.

Si vous utilisez le centre d’administration Microsoft Teams, vous pouvez configurer TeamsUpgradePolicy pour jusqu’à 20 utilisateurs à la fois :
1. Dans le centre d’administration Microsoft Teams, sélectionnez **Utilisateurs**, puis cochez la case pour jusqu’à 20 utilisateurs.
2. Sélectionnez **Modifier les paramètres** dans le coin supérieur gauche de l’affichage de liste.
3. Dans le volet **Modifier les paramètres** à droite, sous **Teams section de mise à niveau**, définissez le mode de coexistence sur **Teams uniquement** dans la liste déroulante.

Vous pouvez également trouver plus facile de mettre à niveau des groupes d’utilisateurs à la fois à l’aide de PowerShell. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Étape 4 : Répétez les étapes 1 à 3 pour les vagues successives d’utilisateurs

Lorsque vous validez votre mise à niveau vers Teams mode Uniquement et que vous êtes prêt à développer, répétez les étapes précédentes pour appliquer TeamsOnly à un plus grand nombre d’utilisateurs.  


## <a name="phone-system-and-pstn-connectivity-options"></a>options de connectivité Système téléphonique et RTC

Système téléphonique avec Teams est pris en charge une fois que l’utilisateur est en mode TeamsOnly. (Si l’utilisateur est en mode Îles, Système téléphonique est uniquement pris en charge avec Skype Entreprise.)  

### <a name="pstn-connectivity-options"></a>Options de connectivité RTC

Lorsque vous envisagez d’utiliser les options de connectivité réseau téléphonique commuté (RTC), il existe deux scénarios possibles lors du passage de Skype Entreprise Online au mode TeamsOnly :

- Un utilisateur dans Skype Entreprise Online, avec un plan d’appel Microsoft. Lors de la mise à niveau, cet utilisateur continuera d’avoir un plan d’appel Microsoft. Il s’agit du scénario le plus simple nécessitant seulement quelques étapes. Pour plus d’informations, consultez [From Skype Entreprise Online with Microsoft Calling Plans](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).

- Un utilisateur dans Skype Entreprise Online, avec des fonctionnalités vocales locales via Skype Entreprise édition locale ou Cloud Connector. La mise à niveau de l’utilisateur vers Teams doit être coordonnée avec la migration de l’utilisateur vers le routage direct pour garantir que l’utilisateur TeamsOnly dispose des fonctionnalités RTC.  Pour plus d’informations, consultez [From Skype Entreprise Online with on-premises voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).
