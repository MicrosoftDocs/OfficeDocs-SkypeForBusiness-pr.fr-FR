---
title: Mise à niveau de Skype Entreprise local vers Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Découvrez comment effectuer la transition de votre organisation vers Microsoft Teams à partir d’un déploiement local Skype Entreprise.
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
ms.openlocfilehash: 7b06134a0fe0f72e8dc9c01b4faa85c67a6063f3
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615440"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Effectuer une mise à niveau à partir d’un déploiement local Skype Entreprise vers Teams

![Étapes du parcours de mise à niveau, en mettant l’accent sur la phase de déploiement et d’implémentation.](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, en mettant l’accent sur la phase de déploiement et d’implémentation")

Cet article fait partie de la phase déploiement et implémentation de votre parcours de mise à niveau. Avant de continuer, vérifiez que vous avez terminé les activités suivantes :

- [Inscription des parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
- [Définition de l’étendue de votre projet](./upgrade-define-project-scope.md)
- [Coexistence et interopérabilité comprises de Skype Entreprise et Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Choix de votre parcours de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Préparer votre environnement](./upgrade-prepare-environment.md)
- [Préparation de votre organisation](./upgrade-prepare-organization.md)
- [Conduite d’un projet pilote](./pilot-essentials.md)

Suivez les instructions de cet article si vous avez déployé Skype Entreprise ou Microsoft Lync en local et que votre organisation souhaite effectuer une mise à niveau vers Microsoft Teams de manière sélective (à l’aide de plusieurs modes de coexistence) ou entièrement. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Étape 1 : Déployer une connectivité hybride

La configuration requise pour la mise à niveau de vos utilisateurs vers Teams consiste à déployer une connectivité hybride.

Pour plus d’informations, consultez [Déployer la connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Étape 2 : Implémenter le parcours de mise à niveau choisi pour votre organisation

Une fois votre configuration hybride terminée, vous pouvez planifier le déplacement de vos utilisateurs vers Microsoft 365 ou Office 365.

Pour plus d’informations, consultez :

- [TeamsUpgradePolicy : gestion de la migration et de la coexistence](upgrade-to-teams-on-prem-tools.md).

- [Déplacez les utilisateurs d’un emplacement local vers Skype Entreprise Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="phone-system-and-teams-upgrade"></a>Mise à niveau du système téléphonique et de Teams

La transition des systèmes téléphoniques locaux vers Teams vous permettra de tirer parti du routage direct du système téléphonique (« routage direct ») ou des plans d’appel fournis par Microsoft pour Microsoft 365 ou Office 365.

Si vous n’utilisez pas de forfaits d’appels, vous devez passer votre déploiement vocal d’entreprise au routage direct du système téléphonique dans le cadre de votre mise à niveau vers Teams.

Pour plus d’informations, consultez [les considérations supplémentaires relatives au routage direct du système téléphonique](./direct-routing-landing-page.md). Si vous envisagez d’utiliser des forfaits d’appels, reportez-vous à nos conseils pour [transférer vos numéros de téléphone vers Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).