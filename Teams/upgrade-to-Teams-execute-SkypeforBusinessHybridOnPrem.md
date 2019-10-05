---
title: Effectuer une mise à niveau vers teams à partir d’un déploiement local de Skype entreprise-Microsoft teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Remarques concernant la mise à niveau vers teams à partir d’un déploiement local de Skype entreprise.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b41e716bb115d84b38aa5f2ead25d6347e2e0f1a
ms.sourcegitcommit: 8fb89d6226b02ba8b1f8396eb4d1a37da4608b7c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2019
ms.locfileid: "37396420"
---
![Diagramme de parcours de mise à niveau, mettant en évidence](media/upgrade-banner-deployment.png "les phases de déploiement et d’implémentation du parcours de la mise à niveau, en mettant l’accent sur l’étape de déploiement et d’implémentation")

Cet article fait partie de l’étape de déploiement et d’implémentation de votre parcours de mise à niveau. Avant de continuer, confirmez que vous avez terminé les activités suivantes :

-   [Inscription des parties prenantes du projet](upgrade-enlist-stakeholders.md)
-   [Définition de l’objectif de votre projet](https://aka.ms/SkypetoTeams-Scope)
-   [Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes](https://aka.ms/SkypeToTeams-Coexist)
-   [Choix de votre mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Préparé votre environnement](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Préparé votre organisation](https://aka.ms/SkypeToTeams-UserReadiness)
-   [A mené une pilote](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Mise à niveau de Skype entreprise local vers teams

Si vous avez déployé Skype entreprise Server ou Microsoft Lync local et que votre organisation souhaite procéder à la mise à niveau vers Teams, suivez les recommandations de cet article. Vous devez configurer une connectivité hybride avec votre client Office 365 et définir les exigences de coexistence si vous migrez vos utilisateurs vers équipes par phases. 

> [!IMPORTANT]
> Skype entreprise Online sera supprimé le 31 juillet 2021, mais il ne sera plus accessible ou pris en charge. Pour optimiser la réalisation des avantages et garantir que votre organisation dispose du moment approprié pour mettre en œuvre la mise à niveau, nous vous encourageons à commencer votre trajet vers Microsoft teams dès aujourd’hui. Rappelez-vous qu’une mise à niveau réussie aligne les techniques et les capacités de l’utilisateur, veillez donc à tirer parti de ces instructions lorsque vous naviguez dans votre voyage vers Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Étape 1 : configurer la connectivité hybride 

La configuration requise pour la mise à niveau de vos utilisateurs locaux vers teams consiste à configurer une connectivité hybride pour votre déploiement local de Skype entreprise Server. 

Commencez par lire [prévoir une connectivité hybride](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) , puis suivez les étapes décrites dans la rubrique [configurer une connectivité hybride](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Étape 2 : définir le mode de coexistence de la transition (facultatif)

La coexistence et l’interopérabilité entre les clients et les utilisateurs de Skype entreprise et équipes sont définis par les modes de mise à niveau de teams.  Par défaut, les organisations sont en mode îlot, ce qui permet aux utilisateurs d’utiliser des équipes et des clients Skype entreprise côte à côte.

Dans le cas d’une organisation migrant vers Teams, le mode TeamsOnly est la destination finale de chaque utilisateur, mais tous les utilisateurs ne doivent pas avoir besoin d’être TeamsOnly (ou n’importe quel autre mode) en même temps.

Avant d’atteindre le mode TeamsOnly, les organisations peuvent éventuellement utiliser n’importe quel mode de coexistence Skype entreprise pour garantir une communication avec les utilisateurs du mode TeamsOnly et des utilisateurs qui ne sont pas encore connectés.  L’objectif des modes de coexistence Skype entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) est d’offrir une interface simple et prévisible aux utilisateurs finaux lors de la transition de Skype entreprise à Teams. 

Lorsque l’utilisateur se trouve dans l’un des modes Skype entreprise, toutes les conversations et tous les appels entrants sont acheminés vers le client Skype entreprise de l’utilisateur. Afin d’éviter la confusion des utilisateurs finaux et de veiller à ce que le routage, les appels et les discussions appropriés dans le client teams soient désactivés lorsqu’un utilisateur se trouve dans l’un des modes Skype entreprise. De la même façon, la planification de réunions en équipes est désactivée explicitement lorsque les utilisateurs se trouvent dans les modes SfBOnly ou SfBWithTeamsCollab, et activés de manière explicite lorsqu’un utilisateur est en mode SfBWithTeamsCollabAndMeetings.

En fonction de vos besoins, vous pouvez affecter le mode de coexistence approprié en fonction du chemin de mise à niveau choisi par votre organisation. Pour plus d’informations, reportez-vous à la rubrique [Guide de migration et d’interopérabilité pour les organisations qui utilisent des équipes avec Skype entreprise](migration-interop-guidance-for-teams-with-skype.md) et [définissant vos paramètres de coexistence et de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence).


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Étape 3 : migrer des utilisateurs de Skype entreprise local vers équipes uniquement

Pour finir, vous pouvez déplacer vos utilisateurs vers le mode TeamsOnly. Cela peut impliquer une ou deux étapes en fonction de votre environnement local actuel.  

Pour plus d’informations, reportez-vous à [déplacer des utilisateurs entre le Cloud local et le Cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) et [déplacer des utilisateurs de local vers équipes](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams). 



## <a name="phone-system-and-teams-upgrade"></a>Mise à niveau du système téléphonique et des équipes

Si vous migrez votre déploiement Skype entreprise vers un système téléphonique avec des plans d’appels, Microsoft sera votre fournisseur de réseau téléphonique commuté (PSTN). En supposant que vous avez terminé le portage du numéro de téléphone, la mise à niveau de vos utilisateurs vers teams va automatiquement migrer les appels RTC entrants vers Teams.

Si vous migrez votre déploiement Skype entreprise vers votre système téléphonique sans utiliser d’offres d’appels, vous devez migrer votre déploiement voix entreprise vers le routage direct du système Microsoft Phone. Pour plus d’informations, voir [routage direct du système téléphonique](direct-routing-landing-page.md).
