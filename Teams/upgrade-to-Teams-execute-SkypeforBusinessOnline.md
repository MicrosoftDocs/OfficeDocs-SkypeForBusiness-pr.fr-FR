---
title: Mise à niveau de Skype entreprise Online vers Microsoft teams | Deploy
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Remarques concernant la mise à niveau vers teams à partir de Skype entreprise Online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4f4a7076a5911798664ea1b7668e7dee8c820ff1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235860"
---
![Diagramme de parcours de mise à niveau, mise en évidence du déploiement et de l’implémentation] (media/upgrade-banner-deployment.png "Étapes du parcours de la mise à niveau, mettant l’accent sur l’étape de déploiement et d’implémentation")

Cet article fait partie de l’étape de déploiement et d’implémentation de votre parcours de mise à niveau. Avant de continuer, confirmez que vous avez terminé les activités suivantes:

- [Inscription des parties prenantes du projet](upgrade-enlist-stakeholders.md)
- [Définition de l’objectif de votre projet](https://aka.ms/SkypetoTeams-Scope)
- [Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes](https://aka.ms/SkypeToTeams-Coexist)
- [Choix de votre mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Préparé votre environnement](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Préparé votre organisation](https://aka.ms/SkypeToTeams-UserReadiness)
- [A mené une pilote](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Mise à niveau de Skype Entreprise Online vers Teams

Suivez les recommandations de cet article si vous avez entièrement déployé Skype entreprise Online et voulez mettre à niveau vos utilisateurs de Skype entreprise vers Teams. Vous pouvez mettre à niveau les utilisateurs de manière sélective ou sélective, en fonction du parcours de mise à niveau choisi par votre organisation, en attribuant la coexistence et le mode de mise à niveau appropriés à vos utilisateurs.

> [!IMPORTANT]
> Skype entreprise Online sera supprimé le 31 juillet 2021, mais il ne sera plus accessible ou pris en charge. Pour optimiser la réalisation des avantages et garantir que votre organisation dispose du moment approprié pour mettre en œuvre la mise à niveau, nous vous encourageons à commencer votre trajet vers Microsoft teams dès aujourd’hui. Rappelez-vous qu’une mise à niveau réussie aligne les techniques et les capacités de l’utilisateur, veillez donc à tirer parti de ces instructions lorsque vous naviguez dans votre voyage vers Microsoft Teams.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Attribuer le mode de coexistence et de mise à niveau

Vous pouvez mettre à niveau vos utilisateurs vers le mode TeamsOnly en assignant l’instance UpgradeToTeams de TeamsUpgradePolicy, qui peut être effectuée à l’aide du centre d’administration Microsoft teams ou d’une session Windows PowerShell Skype entreprise distante. Vous pouvez effectuer cette opération sur une base par utilisateur ou sur une base d’un client si vous souhaitez mettre à niveau tout le client en une seule étape. 

Pour plus d’informations, reportez-vous à [définition de votre coexistence et de vos paramètres de mise à](https://aka.ms/SkypeToTeams-SetCoexistence) [TeamsUpgradePolicy: gestion de la migration et de](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)la coexistence.

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Mettre à niveau tous les utilisateurs en équipes en même temps

Suivez ces étapes pour mettre à niveau tous vos utilisateurs vers teams en même temps.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Étape 1: informer les utilisateurs de la modification (facultatif)

1. Dans le centre d’administration de Microsoft Teams, sélectionnez**mise à niveau des équipes** **des paramètres** > à l’échelle de l’organisation.
2. Sous **mode**de coexistence, changez le paramètre **informer les utilisateurs de Skype entreprise qu’une mise à niveau vers teams est disponible** . ****

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Étape 2: définir le mode de coexistence sur TeamsOnly pour l’Organisation

1. Dans le centre d’administration de Microsoft Teams, sélectionnez **paramètres à l’échelle**de l’organisation.
2. Sélectionner le mode **équipes uniquement** dans la liste déroulante du **mode coexistence** .

## <a name="upgrade-users-in-stages"></a>Mettre à niveau les utilisateurs par étapes

Suivez ces étapes si vous souhaitez mettre à niveau progressivement vos utilisateurs vers TeamsOnly.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Étape 1: identifier les groupes d’utilisateurs pour la mise à niveau

Il arrive souvent que les organisations choisissent de mettre à niveau leurs organisations en cas d’onde de réussite.  Vous souhaiterez peut-être identifier ces utilisateurs d’abord pour pouvoir les Rechercher dans le centre d’administration Microsoft Teams. Par ailleurs, il est possible que vous souhaitiez utiliser PowerShell pour plus efficacement. Une fois que vous avez identifié le jeu d’utilisateurs pour une vague de mise à niveau donnée, poursuivez les étapes restantes.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Étape 2: définir une notification pour les utilisateurs de l’onde de mise à niveau actuelle (facultatif)

Si vous utilisez le centre d’administration de Microsoft Teams, vous pouvez configurer TeamsUpgradePolicy pour 20 utilisateurs à la fois:
1. Dans le centre d’administration de Microsoft Teams, sélectionnez **utilisateurs**, puis recherchez et activez la case à cocher pour 20 utilisateurs maximum qui doivent être mis à niveau. 
2. Dans le coin supérieur gauche de ListView, sélectionnez **modifier les paramètres** . 
3. Dans le **volet modifier les paramètres** à droite, sous **mise à niveau**de Microsoft Teams, modifiez l’option demander **** à **l’utilisateur de Skype entreprise** de changer. Remarque: si la valeur du mode de coexistence est «utiliser les paramètres à l’échelle de l’organisation», vous ne verrez pas ce commutateur, vous devez commencer par définir explicitement le mode de coexistence pour ces utilisateurs à la valeur par défaut de l’organisation.

Par ailleurs, il est possible que vous puissiez facilement activer les notifications pour les groupes d’utilisateurs à la fois à l’aide de PowerShell. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Étape 3: définir le mode de coexistence pour les utilisateurs uniquement dans teams

Lorsque vous êtes prêt à mettre à niveau les utilisateurs de l’onde actuelle pour utiliser teams comme seule application, définissez le mode de coexistence pour les utilisateurs sur équipes uniquement.

Si vous utilisez le centre d’administration de Microsoft Teams, vous pouvez configurer TeamsUpgradePolicy pour 20 utilisateurs à la fois:
1. Dans le centre d’administration de Microsoft Teams, sélectionnez **utilisateurs**, puis cochez la case jusqu’à 20 utilisateurs.
2. Dans le coin supérieur gauche de ListView, sélectionnez **modifier les paramètres** .
3. Dans le volet **modifier les paramètres** sur la droite, sous la section **mise à niveau** de Microsoft Teams, définissez le mode de coexistence sur **équipes uniquement** dans la liste déroulante.

Par ailleurs, il est possible que vous puissiez constater qu’il est plus facile de mettre à niveau des groupes d’utilisateurs à la fois avec PowerShell. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Étape 4: répéter les étapes 1-3 pour les vagues successives d’utilisateurs

Lorsque vous validez le mode de mise à niveau en équipes uniquement et que vous êtes prêt à développer, répétez les étapes précédentes pour ajouter TeamsOnly à d’autres utilisateurs.  


## <a name="phone-system-and-teams-upgrade"></a>Mise à niveau du système téléphonique et des équipes

Si votre déploiement de Skype entreprise Online inclut un système téléphonique avec des plans d’appels et que Microsoft est votre fournisseur de réseau téléphonique commuté (PSTN), la mise à niveau de vos utilisateurs vers teams fera automatiquement basculer les appels RTC entrants vers Teams.

Si votre déploiement de Skype entreprise Online inclut un système téléphonique avec la version Cloud Connector, voir [Considérations supplémentaires relatives au routage direct du système téléphonique](2-envision-make-my-service-decisions-direct-routing.md).
