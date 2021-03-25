---
title: Mise à niveau de Skype Entreprise local vers Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Découvrez comment faire passer votre organisation à Microsoft Teams à partir d’un déploiement local de Skype Entreprise.
localization_priority: Normal
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
ms.openlocfilehash: 0585f0ad829f19334d5a970461f1f3248a107e9d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115552"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Mettre à niveau à partir d’un déploiement Skype Entreprise local vers Teams

![Étapes du parcours de mise à niveau, avec l’accentuation sur l’étape déploiement et implémentation](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, avec l’accentuation sur l’étape déploiement et implémentation")

Cet article fait partie de la phase déploiement et implémentation de votre parcours vers la mise à niveau. Avant de poursuivre, confirmez que vous avez effectué les activités suivantes :

- [Demandez aux parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
- [Étendue définie de votre projet](./upgrade-define-project-scope.md)
- [Coexistence et interopérabilité comprises de Skype Entreprise et Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Nous avons choisi votre chemin de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Préparé votre environnement](./upgrade-prepare-environment.md)
- [Préparé votre organisation](./upgrade-prepare-organization.md)
- [Conduite d’un pilote](./pilot-essentials.md)

Si vous avez déployé Skype Entreprise ou Microsoft Lync en local et que votre organisation souhaite mettre à niveau vers Microsoft Teams de manière sélective (à l’aide de plusieurs modes de coexistence), suivez les instructions de cet article. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Étape 1 : déployer la connectivité hybride

La principale condition préalable pour la mise à niveau de vos utilisateurs vers Teams consiste à déployer la connectivité hybride.

Pour plus d’informations, [voir Déployer la connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Étape 2 : mettre en œuvre le chemin de mise à niveau que vous avez choisi pour votre organisation

Une fois que vous avez terminé votre configuration hybride, vous pouvez planifier le déplacement de vos utilisateurs vers Microsoft 365 ou Office 365.

Pour plus d’informations, consultez :

- [TeamsUpgradePolicy : gestion de la migration et de la coexistence.](upgrade-to-teams-on-prem-tools.md)

- [Déplacer les utilisateurs du site vers Skype Entreprise Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="phone-system-and-teams-upgrade"></a>Mise à niveau de Phone System et Teams

La transition des systèmes téléphoniques locaux vers Teams vous permet de tirer parti du routage direct du système téléphonique (« Routage direct ») ou des plans d’appels fournis par Microsoft pour Microsoft 365 ou Office 365.

Si vous n’utilisez pas de forfaits d’appels, vous devez transition votre déploiement vocal d’entreprise vers le routage direct du système téléphonique dans le cadre de votre mise à niveau vers Teams.

Pour plus d’informations, voir [d’autres considérations concernant le routage direct du](./direct-routing-landing-page.md)système téléphonique. Si vous envisagez d’utiliser des forfaits d’appels, consultez nos recommandations pour le transfert de vos numéros [de téléphone vers Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)