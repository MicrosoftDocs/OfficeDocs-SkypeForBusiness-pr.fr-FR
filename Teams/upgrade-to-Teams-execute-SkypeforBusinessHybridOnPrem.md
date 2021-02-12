---
title: Mettre à niveau Skype Entreprise en local vers Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Découvrez comment mettre à niveau votre organisation vers Microsoft Teams à partir d’un déploiement Skype Entreprise sur site.
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
ms.openlocfilehash: 961ac4f9bcce3c24d62ec1c744d2c9cd15e2ee1b
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578167"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Mise à niveau de Skype Entreprise local vers Teams

![Diagramme de voyage de mise à niveau mettant en relief le déploiement et l’implémentation](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, avec l’accentuation sur l’étape déploiement et implémentation")

Cet article fait partie de la phase déploiement et implémentation de votre voyage de mise à niveau. Avant de poursuivre, confirmez que vous avez effectué les activités suivantes :

-   [Demandez aux parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
-   [Étendue définie de votre projet](https://aka.ms/SkypetoTeams-Scope)
-   [Coexistence et interopérabilité comprises de Skype Entreprise et Teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Nous avons choisi votre chemin de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Préparé votre environnement](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Préparé votre organisation](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Conduite d’un pilote](https://aka.ms/SkypeToTeams-Pilot)

Si vous avez déployé Skype Entreprise Server ou Microsoft Lync en local et que votre organisation souhaite mettre à niveau vers Teams, suivez les instructions de cet article. Vous devez configurer une connectivité hybride avec votre organisation Microsoft 365 ou Office 365, et déterminer les conditions de coexistence si vous déplacez vos utilisateurs vers Teams par phase. 

> [!IMPORTANT]
> Skype Entreprise Online sera supprimé le 31 juillet 2021. Après cette date, il ne sera plus accessible ni pris en charge. Pour optimiser l’avantage et vous assurer que votre organisation a le temps approprié pour implémenter votre mise à niveau, nous vous encourageons à commencer votre voyage vers Microsoft Teams dès aujourd’hui. N’oubliez pas qu’une mise à niveau réussie aligne les niveaux de préparation technique et utilisateur. N’oubliez pas de tirer parti des conseils qui s’offrent à vous au cours de votre voyage vers Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Étape 1 : configurer la connectivité hybride 

La configuration requise pour mettre à niveau vos utilisateurs locaux vers Teams consiste à configurer une connectivité hybride pour votre déploiement Skype Entreprise Server sur site. 

Commencez par lire [Planifier la connectivité hybride,](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) puis suivez les tâches décrites dans [Configurer la connectivité hybride.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Étape 2 : définir le mode de coexistence de transition (facultatif)

La coexistence et l’interopérabilité entre Les clients et utilisateurs de Skype Entreprise et Teams sont définis par les modes de mise à niveau de Teams.  Par défaut, les organisations sont en mode Îles, ce qui permet aux utilisateurs d’utiliser les clients Teams et Skype Entreprise côte à côte.

Pour une organisation passant à Teams, le mode TeamsOnly est la destination finale pour chaque utilisateur, même si tous les utilisateurs ne doivent pas être affectés à TeamsOnly (ou tout autre mode) en même temps.

Avant que les utilisateurs n’atteignent le mode TeamsOnly, les organisations peuvent éventuellement utiliser n’importe quel mode de coexistence Skype Entreprise pour assurer une communication prévisible entre les utilisateurs qui sont en mode TeamsOnly et ceux qui ne le sont pas encore.  L’objectif des modes de coexistence Skype Entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) est d’offrir aux utilisateurs finaux une expérience simple et prévisible au sein de la transition entre Skype Entreprise et Teams au sein des organisations. 

Lorsqu’un utilisateur est dans l’un des modes Skype Entreprise, toutes les conversations et appels entrants sont acheminés vers le client Skype Entreprise de l’utilisateur. Pour éviter la confusion des utilisateurs finaux et assurer un routage approprié, les fonctionnalités d’appel et de conversation dans le client Teams sont désactivées lorsqu’un utilisateur est dans l’un des modes Skype Entreprise. De même, la planification de réunions dans Teams est explicitement désactivée lorsque les utilisateurs sont dans les modes SfBOnly ou SfBWithTeamsCollab et sont explicitement activés quand un utilisateur est en mode SfBWithTeamsCollabAndMeetings.

Selon vos besoins, vous pouvez attribuer le mode de coexistence approprié en fonction du chemin de mise à niveau choisi par votre organisation. Pour plus d’informations, consultez les conseils sur la migration et [l’interopérabilité](migration-interop-guidance-for-teams-with-skype.md) pour les organisations qui utilisent Teams avec Skype Entreprise et définir vos paramètres de coexistence et [de mise à niveau.](https://aka.ms/SkypeToTeams-SetCoexistence)


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Étape 3 : déplacer des utilisateurs de Skype Entreprise en local vers Teams uniquement

Au final, vous souhaiterez déplacer vos utilisateurs vers le mode TeamsOnly. Cela peut impliquer une ou deux étapes en fonction de votre environnement local.  

Pour plus d’informations, voir Déplacer des [utilisateurs](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) entre le cloud local et le cloud et Déplacer des utilisateurs du site [vers Teams.](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>Étape 4 : désactiver le mode hybride pour terminer la migration vers le cloud

Une fois que vous avez déplacé tous les utilisateurs du déploiement local vers le cloud, vous pouvez désaffecter le déploiement Skype Entreprise local. Pour plus d’informations, [voir Désactiver l’hybride pour achever](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)la migration vers le cloud.


## <a name="phone-system-and-pstn-connectivity-options"></a>Options de connectivité système téléphonique et PSTN

Phone System avec Teams est pris en charge lorsque l’utilisateur est en mode TeamsOnly. (Si l’utilisateur est en mode Îles, Phone System n’est pris en charge qu’avec Skype Entreprise.) 

### <a name="pstn-connectivity-options"></a>Options de connectivité PSTN

Lorsque vous considérez des options de connectivité réseau téléphonique commuté (PSTN), deux scénarios peuvent s’offrent à vous lorsque vous basculez de Skype Entreprise en local vers le mode TeamsOnly :

- Un utilisateur de Skype Entreprise sur site avec Voix Entreprise, qui passe au service en ligne et utilise un plan d’appel Microsoft. La migration de cet utilisateur vers Teams nécessite le déplacement du compte Skype Entreprise local de l’utilisateur vers le cloud et la coordination du déplacement avec l’un des A) port du numéro de téléphone de cet utilisateur vers un plan d’appels Microsoft ou B) et l’affectation d’un nouveau numéro d’abonné à partir des régions disponibles.  Pour plus d’informations, voir Skype Entreprise Server sur site, avec [Voix Entreprise, vers le plan d’appels Microsoft.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)

- Un utilisateur de Skype Entreprise sur site avec Voix Entreprise, qui passe à la connexion en ligne et maintient la connectivité RSTN sur site. La migration de cet utilisateur vers Teams nécessite le déplacement du compte Skype Entreprise local de l’utilisateur vers le cloud et la coordination de ce déplacement avec la migration de l’utilisateur vers le routage direct. Pour plus d’informations, voir À partir de Skype Entreprise Server en local, avec [Voix Entreprise, vers Un routage direct.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)
