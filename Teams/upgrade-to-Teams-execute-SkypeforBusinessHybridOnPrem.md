---
title: Mise à niveau de Skype Entreprise local vers Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Découvrez comment mettre à niveau votre organisation vers Microsoft teams à partir d’un déploiement local de Skype entreprise.
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
ms.openlocfilehash: 1981640ab06d00e7895e11c0e15adf7555577908
ms.sourcegitcommit: b23d3d583910aa21a62ea69b554ab614c1ae8079
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648605"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Mise à niveau de Skype entreprise local vers teams

![Diagramme de parcours de mise à niveau, mise en évidence du déploiement et de l’implémentation](media/upgrade-banner-deployment.png "Étapes du parcours de la mise à niveau, mettant l’accent sur l’étape de déploiement et d’implémentation")

Cet article fait partie de l’étape de déploiement et d’implémentation de votre parcours de mise à niveau. Avant de continuer, confirmez que vous avez terminé les activités suivantes :

-   [Inscription des parties prenantes du projet](upgrade-enlist-stakeholders.md)
-   [Définition de l’objectif de votre projet](https://aka.ms/SkypetoTeams-Scope)
-   [Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes](https://aka.ms/SkypeToTeams-Coexist)
-   [Choix de votre mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Préparé votre environnement](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Préparé votre organisation](https://aka.ms/SkypeToTeams-UserReadiness)
-   [A mené une pilote](https://aka.ms/SkypeToTeams-Pilot)

Si vous avez déployé Skype entreprise Server ou Microsoft Lync local et que votre organisation souhaite procéder à la mise à niveau vers Teams, suivez les recommandations de cet article. Vous devez configurer une connectivité hybride avec votre organisation Microsoft 365 ou Office 365 et définir les exigences de coexistence si vous migrez vos utilisateurs vers équipes par phases. 

> [!IMPORTANT]
> Skype Entreprise Online sera supprimé le 31 juillet 2021. Après cette date, il ne sera plus accessible ni pris en charge. Pour optimiser la réalisation des avantages et garantir que votre organisation dispose du moment approprié pour mettre en œuvre la mise à niveau, nous vous encourageons à commencer votre trajet vers Microsoft teams dès aujourd’hui. Rappelez-vous qu’une mise à niveau réussie aligne les techniques et les capacités de l’utilisateur, veillez donc à tirer parti de ces instructions lorsque vous naviguez dans votre voyage vers Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Étape 1 : configurer la connectivité hybride 

La configuration requise pour la mise à niveau de vos utilisateurs locaux vers teams consiste à configurer une connectivité hybride pour votre déploiement local de Skype entreprise Server. 

Commencez par lire [prévoir une connectivité hybride](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) , puis suivez les étapes décrites dans la rubrique [configurer une connectivité hybride](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Étape 2 : définir le mode de coexistence de la transition (facultatif)

La coexistence et l’interopérabilité entre les clients et les utilisateurs de Skype entreprise et équipes sont définis par les modes de mise à niveau de teams.  Par défaut, les organisations sont en mode îlot, ce qui permet aux utilisateurs d’utiliser des équipes et des clients Skype entreprise côte à côte.

Dans le cas d’une organisation migrant vers Teams, le mode TeamsOnly est la destination finale de chaque utilisateur, mais tous les utilisateurs ne doivent pas avoir besoin d’être TeamsOnly (ou n’importe quel autre mode) en même temps.

Avant d’atteindre le mode TeamsOnly, les organisations peuvent éventuellement utiliser n’importe quel mode de coexistence Skype entreprise pour garantir une communication avec les utilisateurs du mode TeamsOnly et des utilisateurs qui ne sont pas encore connectés.  L’objectif des modes de coexistence Skype entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) est d’offrir une interface simple et prévisible aux utilisateurs finaux lors de la transition de Skype entreprise à Teams. 

Lorsque l’utilisateur se trouve dans l’un des modes Skype entreprise, toutes les conversations et tous les appels entrants sont acheminés vers le client Skype entreprise de l’utilisateur. Afin d’éviter la confusion des utilisateurs finaux et de veiller à ce que le routage, les appels et les discussions appropriés dans le client teams soient désactivés lorsqu’un utilisateur se trouve dans l’un des modes Skype entreprise. De la même façon, la planification de réunions en équipes est désactivée explicitement lorsque les utilisateurs se trouvent dans les modes SfBOnly ou SfBWithTeamsCollab, et activés de manière explicite lorsqu’un utilisateur est en mode SfBWithTeamsCollabAndMeetings.

En fonction de vos besoins, vous pouvez affecter le mode de coexistence approprié en fonction du chemin de mise à niveau choisi par votre organisation. Pour plus d’informations, reportez-vous à la rubrique [Guide de migration et d’interopérabilité pour les organisations qui utilisent des équipes avec Skype entreprise](migration-interop-guidance-for-teams-with-skype.md) et [définissant vos paramètres de coexistence et de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence).


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Étape 3 : migrer des utilisateurs de Skype entreprise local vers équipes uniquement

Pour finir, vous pouvez déplacer vos utilisateurs vers le mode TeamsOnly. Cela peut impliquer une ou deux étapes en fonction de votre environnement local.  

Pour plus d’informations, reportez-vous à [déplacer des utilisateurs entre le Cloud local et le Cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) et [déplacer des utilisateurs de local vers équipes](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams). 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>Étape 4 : désactiver l’environnement hybride pour terminer la migration vers le Cloud

Après avoir déplacé tous les utilisateurs de local vers le Cloud, vous pouvez désaffecter le déploiement Skype entreprise local. Pour plus d’informations, reportez-vous à la rubrique [désactiver l’environnement hybride pour terminer la migration vers le Cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).


## <a name="phone-system-and-pstn-connectivity-options"></a>Options système téléphonique et connectivité PSTN

Le système téléphonique avec teams est pris en charge lorsque l’utilisateur est en mode TeamsOnly. (Si l’utilisateur est en mode îlot, le système téléphonique est uniquement pris en charge par Skype entreprise.) 

### <a name="pstn-connectivity-options"></a>Options de connectivité PSTN

Dans le cadre de la prise en compte des options de connectivité PSTN (réseau téléphonique commuté), il existe deux scénarios possibles lors du passage de Skype entreprise sur site au mode TeamsOnly :

- Un utilisateur de Skype entreprise sur site avec voix entreprise, qui sera déplacé vers en ligne et utilisant un forfait d’appel Microsoft. La migration de cet utilisateur vers teams nécessite le passage du compte Skype entreprise local de l’utilisateur dans le Cloud, et la coordination de la migration à l’aide de l’un des numéros de téléphone de l’utilisateur vers un forfait d’appel Microsoft ou B), en attribuant un nouveau numéro d’abonné à partir des régions disponibles.  Pour plus d’informations, reportez-vous à [Skype entreprise Server en local, avec Enterprise Voice, à l’offre d’appels Microsoft](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).

- Un utilisateur de Skype entreprise sur site avec voix entreprise, qui va basculer vers une connectivité RTC sur site. La migration de cet utilisateur vers teams nécessite le passage du compte Skype entreprise local de l’utilisateur dans le Cloud, et le coordination du déplacement avec la migration de celui-ci pour le routage directe. Pour plus d’informations, reportez-vous [à partir de Skype entreprise Server en local, avec Enterprise Voice, pour le routage direct](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).
