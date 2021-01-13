---
title: Mettre à niveau un déploiement Skype Entreprise hybride vers Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Découvrez comment mettre à niveau votre organisation vers Microsoft Teams à partir d’un déploiement hybride Skype Entreprise.
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
ms.openlocfilehash: 67bb6c10bb8cc5f37d332459d8e147f4f626497d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802344"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Mettre à niveau à partir d’un déploiement Skype Entreprise hybride vers Teams

![Étapes du parcours de mise à niveau, avec l’accent sur l’étape déploiement et implémentation](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, avec l’accent sur l’étape déploiement et implémentation")

Cet article fait partie de la phase déploiement et implémentation de votre voyage de mise à niveau. Avant de poursuivre, confirmez que vous avez effectué les activités suivantes :

- [Demandez aux parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
- [Étendue définie de votre projet](https://aka.ms/SkypetoTeams-Scope)
- [Coexistence et interopérabilité comprises de Skype Entreprise et Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Nous avons choisi votre chemin de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Préparé votre environnement](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Préparé votre organisation](https://aka.ms/SkypeToTeams-UserReadiness)
- [Conduite d’un pilote](https://aka.ms/SkypeToTeams-Pilot)

Suivez les instructions de cet article si vous avez déployé Skype Entreprise ou Microsoft Lync sur site et que vous l’avez configuré dans un déploiement hybride avec votre organisation Microsoft 365 ou Office 365, et que votre organisation souhaite mettre à niveau vers Teams de manière sélective (en utilisant plusieurs modes de coexistence) ou tous les membres. Pour une mise à niveau, vous devez déplacer vos utilisateurs vers Skype Entreprise Online (s’ils ne sont pas encore domicile domicile) et leur attribuer le mode de coexistence et de mise à niveau approprié.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Étape 1 : déplacer des utilisateurs vers Skype Entreprise Online

Cette étape s’applique aux utilisateurs actuellement domiciles sur site. Pour plus d’informations sur la déplacement de ces utilisateurs vers Skype Entreprise Online, consultez Déplacer les utilisateurs du site [vers Skype Entreprise Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Étape 2 : attribuer une coexistence et un mode de mise à niveau

Une fois que vous avez déplacé vos utilisateurs vers Skype Entreprise Online, vous pouvez leur attribuer le mode de coexistence approprié, en fonction du parcours de mise à niveau que votre organisation a choisi. Pour plus d’informations, voir Définir vos paramètres de [coexistence](https://aka.ms/SkypeToTeams-SetCoexistence) et de mise à niveau et [TeamsUpgradePolicy :](upgrade-to-teams-on-prem-tools.md)gestion de la migration et de la coexistence.

> [!NOTE]
> Avec Skype Entreprise Server 2019 et une prochaine mise à jour cumulative de Skype Entreprise Server 2015, vous serez en mesure d’effectuer les étapes 1 (déplacement des utilisateurs vers Skype Entreprise Online) et étape 2 (mise à niveau des utilisateurs vers Teams) en une seule étape. Des informations supplémentaires seront fournies après la publication de Skype Entreprise Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Mise à niveau de Phone System et Teams

Si vous effectuez la transition de votre déploiement skype entreprise hybride vers Phone System avec des forfaits d’appels et que Microsoft sera votre fournisseur de réseau téléphonique commuté (PSTN) public (et en supposant que vous avez effectué le transfert de numéro de téléphone), la mise à niveau de vos utilisateurs vers Teams fera automatiquement la transition des appels PSTN entrants vers Teams.

Si les forfaits d’appels ne sont pas disponibles ou si vous avez l’intention d’utiliser votre fournisseur de connectivité RST existant, vous devez transition votre déploiement voix d’entreprise, ou déploiement vocal hybride qui utilise votre déploiement local existant ou la version Cloud Connector, vers le routage direct du système Microsoft Phone. Pour mettre à niveau vos utilisateurs vers Teams, consultez les autres considérations en relation avec [le routage direct du](2-envision-make-my-service-decisions-direct-routing.md)système téléphonique.
