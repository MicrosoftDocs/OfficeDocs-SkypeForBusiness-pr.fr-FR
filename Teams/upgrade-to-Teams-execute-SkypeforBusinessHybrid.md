---
title: Mettre à niveau le déploiement hybride de Skype entreprise vers teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Remarques sur la mise à niveau vers teams à partir d’un déploiement hybride Skype entreprise.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa72c0d6a03ef89d0c04b0a70a0bbc918a508243
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136974"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Mise à niveau d’un déploiement hybride Skype entreprise vers teams

![Étapes du parcours de la mise à niveau, mettant l’accent sur l’étape de déploiement et d’implémentation](media/upgrade-banner-deployment.png "Étapes du parcours de la mise à niveau, mettant l’accent sur l’étape de déploiement et d’implémentation")

Cet article fait partie de l’étape de déploiement et d’implémentation de votre parcours de mise à niveau. Avant de continuer, confirmez que vous avez terminé les activités suivantes :

- [Inscription des parties prenantes du projet](upgrade-enlist-stakeholders.md)
- [Définition de l’objectif de votre projet](https://aka.ms/SkypetoTeams-Scope)
- [Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes](https://aka.ms/SkypeToTeams-Coexist)
- [Choix de votre mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Préparé votre environnement](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Préparé votre organisation](https://aka.ms/SkypeToTeams-UserReadiness)
- [A mené une pilote](https://aka.ms/SkypeToTeams-Pilot)

Suivez les recommandations de cet article si vous avez déployé Skype entreprise ou Microsoft Lync en local et l’avez configuré dans un déploiement hybride avec votre client Office 365 et que votre organisation souhaite effectuer une mise à niveau vers des équipes de manière sélective, à l’aide de plusieurs modes de coexistence, ou tout-en-un. Pour chaque mise à niveau, vous devez déplacer vos utilisateurs vers Skype entreprise Online (s’ils ne sont pas encore hébergés en ligne), puis leur affecter le mode de coexistence et de mise à niveau appropriés.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Étape 1 : déplacer des utilisateurs vers Skype entreprise Online

Cette étape s’applique aux utilisateurs actuellement hébergés sur site. Pour plus d’informations sur le déplacement de ces utilisateurs dans Skype entreprise Online, reportez-vous à la rubrique [déplacer des utilisateurs de local vers Skype entreprise Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Étape 2 : affecter une coexistence et un mode de mise à niveau

Après avoir déplacé vos utilisateurs vers Skype entreprise Online, vous pouvez leur affecter le mode de coexistence approprié en fonction du parcours de mise à niveau choisi par votre organisation. Pour plus d’informations, reportez-vous à [définition de votre coexistence et de vos paramètres de mise à](https://aka.ms/SkypeToTeams-SetCoexistence) [TeamsUpgradePolicy : gestion de la migration et de la coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

> [!NOTE]
> Avec Skype entreprise Server 2019 et une prochaine mise à jour cumulative de Skype entreprise Server 2015, vous serez en mesure de passer à l’étape 1 (déplacer les utilisateurs vers Skype entreprise Online) et étape 2 (mettre à niveau les utilisateurs vers Teams) en une seule étape. Des informations supplémentaires seront fournies après le lancement de Skype entreprise Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Mise à niveau du système téléphonique et des équipes

Si vous migrez votre déploiement hybride Skype entreprise vers votre système téléphonique avec des plans d’appels et que Microsoft sera votre fournisseur de réseaux téléphoniques commutés (RTC), et en supposant que vous avez terminé le transfert du numéro de téléphone, la mise à niveau de vos utilisateurs vers teams transmettra automatiquement les appels RTC entrants vers Teams.

Si les offres d’appels ne sont pas disponibles ou si vous envisagez d’utiliser votre fournisseur de connectivité RTC, vous devez migrer votre déploiement voix entreprise (ou un déploiement VoIP hybride qui utilise votre déploiement local ou édition Cloud Connector) vers le routage direct du système Microsoft Phone. Pour mettre à niveau vos utilisateurs vers Teams, reportez-vous à la rubrique [Considérations supplémentaires sur le routage direct du système téléphonique](2-envision-make-my-service-decisions-direct-routing.md).
