---
title: Mettre à niveau Skype Entreprise déploiement hybride vers Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Découvrez comment mettre à niveau votre organisation vers Microsoft Teams à partir d’un déploiement hybride Skype Entreprise.
ms.localizationpriority: medium
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
ms.openlocfilehash: 4ea8db9f53b891002cf7fbe1f5282051e7aca7ea
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615600"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Effectuer une mise à niveau à partir d’un déploiement hybride Skype Entreprise vers Teams

![Étapes du parcours de mise à niveau, en mettant l’accent sur la phase de déploiement et d’implémentation.](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, en mettant l’accent sur la phase de déploiement et d’implémentation")

Cet article fait partie de l’étape déploiement et implémentation de votre parcours de mise à niveau. Avant de continuer, vérifiez que vous avez terminé les activités suivantes :

- [Inscription des parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
- [Définition de l’étendue de votre projet](./upgrade-define-project-scope.md)
- [Coexistence et interopérabilité comprises de Skype Entreprise et Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Choix de votre parcours de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Préparer votre environnement](./upgrade-prepare-environment.md)
- [Préparation de votre organisation](./upgrade-prepare-organization.md)
- [Conduite d’un projet pilote](./pilot-essentials.md)

Suivez les instructions de cet article si vous avez déployé Skype Entreprise ou Microsoft Lync en local et que vous l’avez configuré dans un déploiement hybride avec votre organisation Microsoft 365 ou Office 365, et que votre organisation souhaite effectuer une mise à niveau vers Teams de manière sélective (à l’aide de plusieurs modes de coexistence) ou entièrement. Pour un parcours de mise à niveau, vous devez déplacer vos utilisateurs vers Skype Entreprise Online (s’ils ne sont pas déjà hébergés en ligne), puis leur attribuer le mode de coexistence et de mise à niveau approprié.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Étape 1 : Déplacer les utilisateurs vers Skype Entreprise Online

Cette étape s’applique aux utilisateurs qui sont actuellement hébergés localement. Pour plus d’informations sur le déplacement de ces utilisateurs vers Skype Entreprise Online, consultez [Déplacer les utilisateurs d’un site local vers Skype Entreprise Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Étape 2 : Attribuer un mode de coexistence et de mise à niveau

Une fois que vous avez déplacé vos utilisateurs vers Skype Entreprise Online, vous pouvez leur attribuer le mode de coexistence approprié en fonction du parcours de mise à niveau choisi par votre organisation. Pour plus d’informations, consultez [Définir vos paramètres de coexistence et de mise à niveau](./setting-your-coexistence-and-upgrade-settings.md) et [TeamsUpgradePolicy : gestion de la migration et de la coexistence](upgrade-to-teams-on-prem-tools.md).

> [!NOTE]
> Avec Skype Entreprise Server 2019 et une prochaine mise à jour cumulative de Skype Entreprise Server 2015, vous serez en mesure d’effectuer les étapes 1 (déplacement des utilisateurs vers Skype Entreprise Online) et l’étape 2 (mettre à niveau les utilisateurs vers Teams) en une seule étape. Plus d’informations seront fournies après la publication de Skype Entreprise Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Mise à niveau du système téléphonique et de Teams

Si vous effectuez la transition de votre Skype Entreprise déploiement hybride vers le système téléphonique avec forfaits d’appels et que Microsoft sera votre fournisseur de réseau téléphonique commuté (RTC) public , et en supposant que vous avez terminé le portage des numéros de téléphone, la mise à niveau de vos utilisateurs vers Teams passera automatiquement les appels RTC entrants vers Teams.

Si les forfaits d’appels ne sont pas disponibles ou si vous envisagez d’utiliser votre fournisseur de connectivité RTC existant, vous devez passer votre déploiement vocal d’entreprise (ou déploiement vocal hybride qui utilise votre déploiement local existant ou l’édition Cloud Connector) vers le routage direct du système téléphonique Microsoft. Pour mettre à niveau vos utilisateurs vers Teams, consultez [les considérations supplémentaires relatives au routage direct du système téléphonique](./direct-routing-landing-page.md).