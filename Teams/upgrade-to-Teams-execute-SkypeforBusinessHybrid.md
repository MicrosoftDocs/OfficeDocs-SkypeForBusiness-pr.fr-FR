---
title: Mettre à Skype Entreprise niveau vers un déploiement hybride Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Découvrez comment mettre à niveau votre organisation vers un déploiement Microsoft Teams un déploiement Skype Entreprise hybride.
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
ms.openlocfilehash: cc79cb570a92ac59bc820b8e10d750d9d926f287
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615130"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Mettre à niveau à partir d Skype Entreprise déploiement hybride vers un déploiement Teams

![Étapes du parcours de mise à niveau, avec l’accentuation sur l’étape déploiement et implémentation](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, avec l’accent sur l’étape déploiement et implémentation")

Cet article fait partie de la phase déploiement et implémentation de votre voyage de mise à niveau. Avant de poursuivre, confirmez que vous avez effectué les activités suivantes :

- [Demandez aux parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
- [Étendue définie de votre projet](./upgrade-define-project-scope.md)
- [Coexistence et interopérabilité comprises entre les systèmes Skype Entreprise et Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Nous avons choisi votre chemin de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Préparé votre environnement](./upgrade-prepare-environment.md)
- [Préparé votre organisation](./upgrade-prepare-organization.md)
- [Conduite d’un pilote](./pilot-essentials.md)

Suivez les instructions de cet article si vous avez déployé Skype Entreprise ou Microsoft Lync en local et que vous l’avez configuré dans un déploiement hybride avec votre organisation Microsoft 365 ou Office 365 et que votre organisation souhaite mettre à niveau vers Teams de manière sélective (en utilisant plusieurs modes de coexistence) ou tous les membres. Pour une mise à niveau, vous devez déplacer vos utilisateurs vers Skype Entreprise Online (s’ils ne sont pas encore domicile domicile) et leur attribuer le mode de coexistence et de mise à niveau approprié.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Étape 1 : déplacer des utilisateurs vers Skype Entreprise Online

Cette étape s’applique aux utilisateurs actuellement domiciles sur site. Pour plus d’informations sur le déplacement de ces utilisateurs vers Skype Entreprise Online, voir Déplacer les utilisateurs d’un site [local vers Skype Entreprise Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Étape 2 : attribuer une coexistence et un mode de mise à niveau

Une fois que vous avez déplacé vos utilisateurs vers Skype Entreprise Online, vous pouvez leur attribuer le mode de coexistence approprié, en fonction du parcours de mise à niveau que votre organisation a choisi. Pour plus d’informations, voir Définir vos paramètres de [coexistence](./setting-your-coexistence-and-upgrade-settings.md) et de mise à niveau et [TeamsUpgradePolicy :](upgrade-to-teams-on-prem-tools.md)gestion de la migration et de la coexistence.

> [!NOTE]
> Avec Skype Entreprise Server 2019 et une prochaine mise à jour cumulative de Skype Entreprise Server 2015, vous serez en mesure d’effectuer les étapes 1 (déplacement des utilisateurs vers Skype Entreprise Online) et étape 2 (mise à niveau des utilisateurs vers Teams) en une seule étape. Des informations supplémentaires seront fournies après Skype Entreprise Server publication de 2019.

## <a name="phone-system-and-teams-upgrade"></a>Système téléphonique mise à Teams niveau

Si vous effectuez la transition de votre déploiement hybride Skype Entreprise vers Système téléphonique avec les forfaits d’appels, Microsoft sera votre fournisseur de réseau téléphonique commuté (PSTN) et, en supposant que vous avez effectué le transfert de numéro de téléphone, la mise à niveau de vos utilisateurs vers Teams fera automatiquement passer les appels PSTN entrants vers Teams.

Si les forfaits d’appels ne sont pas disponibles ou si vous avez l’intention d’utiliser votre fournisseur de connectivité PSTN existant, vous devez transition votre déploiement voix d’entreprise, ou déploiement vocal hybride qui utilise votre déploiement local existant ou la version Cloud Connector, vers le routage direct du système Téléphone Microsoft. Pour mettre à niveau vos utilisateurs vers Teams, consultez les autres éléments à prendre en [compte pour Système téléphonique routage direct.](./direct-routing-landing-page.md)