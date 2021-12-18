---
title: Mettre à niveau Skype Entreprise Online vers Microsoft Teams
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
ms.openlocfilehash: 699f360b8bafb023ad1a477d125d3fc2794e0f67
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563571"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Mise à niveau de Skype Entreprise Online vers Teams

![Diagramme de voyage de mise à niveau mettant en relief le déploiement et l’implémentation.](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, avec l’accentuation sur l’étape déploiement et implémentation")

Cet article fait partie de la phase déploiement et implémentation de votre voyage de mise à niveau. Avant de poursuivre, confirmez que vous avez effectué les activités suivantes :

- [Demandez aux parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
- [Étendue définie de votre projet](./upgrade-define-project-scope.md)
- [Coexistence et interopérabilité comprises entre les systèmes Skype Entreprise et Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Nous avons choisi votre chemin de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Préparé votre environnement](./upgrade-prepare-environment.md)
- [Préparé votre organisation](./upgrade-prepare-organization.md)
- [Conduite d’un pilote](./pilot-essentials.md)

Suivez les instructions de cet article si vous avez déployé Skype Entreprise Online et souhaitez mettre à niveau vos utilisateurs d’Skype Entreprise vers Teams. Vous pouvez mettre à niveau les utilisateurs de manière sélective ou sur la base du parcours de mise à niveau que votre organisation a choisi, en attribuant le mode de coexistence et de mise à niveau approprié à vos utilisateurs.

> [!IMPORTANT]
> Skype Entreprise Online a été retiré le 31 juillet 2021. Pour optimiser l’utilisation des avantages et vous assurer que votre organisation dispose du temps approprié pour implémenter votre mise à niveau, nous vous encourageons à commencer votre chemin vers Microsoft Teams aujourd’hui. N’oubliez pas qu’une mise à niveau réussie aligne les niveaux de préparation technique et utilisateur. N’oubliez pas de tirer parti des recommandations ci-après lorsque vous naviguez vers Microsoft Teams.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Attribuer le mode de coexistence et de mise à niveau

Vous pouvez mettre à niveau vos utilisateurs vers le mode TeamsOnly en attribuant l’instance UpgradeToTeams de TeamsUpgradePolicy, qui peut être effectuée à l’aide du Centre d’administration Microsoft Teams ou d’une session Skype Entreprise remote Windows PowerShell. Vous pouvez le faire soit par utilisateur, soit à l’échelle du client si vous voulez mettre à niveau l’intégralité du client en une seule étape. 

Pour plus d’informations, voir Définir vos paramètres de [coexistence](./setting-your-coexistence-and-upgrade-settings.md) et de mise à niveau et [TeamsUpgradePolicy :](upgrade-to-teams-on-prem-tools.md)gestion de la migration et de la coexistence.

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Mettre à niveau tous les utilisateurs Teams en même temps

Suivez ces étapes pour mettre à niveau tous vos utilisateurs vers Teams une seule fois.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Étape 1 : informer les utilisateurs de la modification (facultatif)

1. Dans le Microsoft Teams d’administration, sélectionnez **paramètres** à l’échelle de  >  **l’Teams mise à niveau.**
2. En **mode coexistence,** modifiez l’Skype Entreprise signaler aux utilisateurs qu’Teams mise à niveau **vers** la version Teams est disponible sur **On.**

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Étape 2 : définir le mode de coexistence sur TeamsOnly pour l’organisation

1. Dans le Microsoft Teams d’administration, sélectionnez **Paramètres à l’échelle de l’organisation.**
2. Sélectionnez **Teams** mode Seul dans la liste du **mode coexistence.**

## <a name="upgrade-users-in-stages"></a>Mettre à niveau les utilisateurs en plusieurs phases

Si vous voulez mettre à niveau progressivement vos utilisateurs vers TeamsOnly, suivez ces étapes.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Étape 1 : identifier les groupes d’utilisateurs à mettre à niveau

Souvent, les organisations peuvent choisir de mettre à niveau leurs organisations par vagues de réussite d’utilisateurs.  Vous devez d’abord identifier ces utilisateurs afin de pouvoir les rechercher facilement dans le Microsoft Teams d’administration. Vous pouvez également utiliser PowerShell pour le faire plus efficacement. Après avoir identifié l’ensemble des utilisateurs pour une vague de mise à niveau donnée, continuez avec les étapes restantes.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Étape 2 : définir une notification pour les utilisateurs dans la vague de mise à niveau actuelle (facultatif)

Si vous utilisez le Microsoft Teams d’administration, vous pouvez configurer TeamsUpgradePolicy pour jusqu’à 20 utilisateurs à la fois :
1. Dans le Microsoft Teams d’administration, sélectionnez Utilisateurs, puis recherchez et sélectionnez plusieurs case à cocher pour jusqu’à 20 utilisateurs qui doivent être mis à niveau. 
2. Sélectionnez **Modifier les paramètres** dans le coin supérieur gauche de l’écran de liste. 
3. Dans le **volet Modifier les paramètres** à droite, sous Teams **mise** à niveau, modifiez Notifier l Skype Entreprise **utilisateur bascule** sur **On.** Remarque : si la valeur du mode de coexistence est « Utiliser les paramètres à l’échelle de l’organisation », vous ne verrez pas ce commutateur. Vous devez donc définir explicitement le mode de coexistence pour ces utilisateurs sur la valeur par défaut de l’organisation.

Vous trouverez également peut-être plus facile d’activer les notifications pour des groupes d’utilisateurs à la fois à l’aide de PowerShell. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Étape 3 : définir le mode de coexistence pour les utilisateurs uniquement Teams

Lorsque vous êtes prêt à mettre à niveau les utilisateurs dans la vague actuelle pour utiliser Teams comme application unique, définissez le mode de coexistence pour ces utilisateurs sur Teams uniquement.

Si vous utilisez le Microsoft Teams d’administration, vous pouvez configurer TeamsUpgradePolicy pour jusqu’à 20 utilisateurs à la fois :
1. Dans le Microsoft Teams d’administration, sélectionnez Utilisateurs, puis cochez la case d’un nombre d’utilisateurs jusqu’à 20.
2. Sélectionnez **Modifier les paramètres** dans le coin supérieur gauche de l’écran de liste.
3. Dans le volet Modifier **les paramètres** à droite, sous la section **Teams** mise à niveau, définissez le mode de coexistence sur **Teams** uniquement dans la liste modifiable.

Vous trouverez également peut-être plus facile de mettre à niveau des groupes d’utilisateurs à la fois à l’aide de PowerShell. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Étape 4 : répéter les étapes 1 à 3 pour les vagues successives d’utilisateurs

Lorsque vous validez votre mise à niveau vers Teams uniquement et que vous êtes prêt à le développer, répétez les étapes précédentes pour appliquer TeamsOnly à davantage d’utilisateurs.  


## <a name="phone-system-and-pstn-connectivity-options"></a>Système téléphonique options de connectivité PSTN et Système téléphonique’autres options

Système téléphonique avec Teams est pris en charge lorsque l’utilisateur est en mode TeamsOnly. (Si l’utilisateur est en mode Îles, Système téléphonique n’est pris en charge qu’avec Skype Entreprise.)  

### <a name="pstn-connectivity-options"></a>Options de connectivité PSTN

Lorsque vous envisagez d’envisager des options de connectivité de réseau téléphonique commuté (PSTN), deux scénarios peuvent s’offrent à vous lorsque vous basculez de Skype Entreprise Online vers le mode TeamsOnly :

- Un utilisateur dans Skype Entreprise Online, avec un plan d’appels Microsoft. Lors de la mise à niveau, cet utilisateur continuera à avoir une offre Microsoft Calling. Il s’agit du scénario le plus simple nécessitant seulement quelques étapes. Pour plus d’informations, voir [À partir Skype Entreprise Online avec les plans d’appel Microsoft.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)

- Un utilisateur dans Skype Entreprise Online, avec des fonctionnalités vocales en local via Skype Entreprise version en local ou Cloud Connector. La mise à niveau de l’utilisateur vers Teams doit être coordonnée avec la migration de l’utilisateur vers le routage direct afin de s’assurer que l’utilisateur TeamsOnly dispose de la fonctionnalité PSTN.  Pour plus d’informations, voir Skype Entreprise Online avec voix [sur site.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)