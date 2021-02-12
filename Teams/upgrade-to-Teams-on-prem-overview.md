---
title: Mise à niveau vers Teams à partir d’un déploiement local de Skype Entreprise - Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Mise à niveau de Skype Entreprise vers Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fe5bb56979b9b4b430076602e76ece595b8661f
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578397"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Mise à niveau de Skype Entreprise vers Teams &mdash; pour les administrateurs informatiques

## <a name="overview"></a>Présentation

Lors de la mise à niveau de Skype Entreprise vers Teams, certaines organisations nécessitent un déploiement progressif planifié et géré par leurs services informatiques. Les articles de cette section s’appliquent principalement aux administrateurs informatiques des grandes organisations. Ces organisations sont généralement locales, mais il peut également s’agit d’organisations Skype Entreprise Online de grande taille. Avant de lire ces articles, n’oubliez pas de lire les articles [Mise](upgrade-start-here.md) à niveau et À propos de l’infrastructure [de mise à niveau de Teams.](upgrade-framework.md)


Les articles suivants vous guideront tout au long du processus de mise à niveau pour votre organisation : 

- [Méthodes de mise à niveau](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Outils de gestion de votre mise à niveau](upgrade-to-teams-on-prem-tools.md)
- [Autres éléments à prendre en considération pour les organisations avec Skype Entreprise sur site](upgrade-to-teams-on-prem-considerations.md)
- [Implémenter votre mise à niveau](upgrade-to-teams-on-prem-implement.md)
- [Considérations sur le réseau téléphonique commuté (PSTN)](upgrade-to-teams-on-prem-pstn-considerations.md)

Par ailleurs, les articles suivants décrivent les concepts de mise à niveau et les comportements de coexistence importants :

- [Coexistence de Teams et de Skype Entreprise](upgrade-to-teams-on-prem-coexistence.md)
- [Modes de coexistence - Référence](migration-interop-guidance-for-teams-with-skype.md)
- [Expérience client Teams et conformité aux modes coexistence](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
>Les articles suivants utilisent les termes Skype Entreprise Online, Skype Entreprise Server en local et Skype Entreprise. Ce dernier terme fait référence à des versions en ligne et en local.

Avant de commencer, sachez qu’un utilisateur qui a été migré vers Teams n’utilise plus un client Skype Entreprise sauf pour participer à une réunion hébergée dans Skype Entreprise.  Toutes les conversations et appels entrants arrivent dans le client Teams de l’utilisateur, que l’expéditeur utilise Teams ou Skype Entreprise. Les nouvelles réunions organisées par l’utilisateur migré seront organisées en tant que réunions Teams. Si l’utilisateur tente d’utiliser le client Skype Entreprise, le démarrage de conversations et d’appels est bloqué.  Toutefois, l’utilisateur peut (et doit) continuer à utiliser le client Skype Entreprise pour participer aux réunions Skype Entreprise à qui il est invité. (Les anciens clients Skype Entreprise expédiés avant 2017 n’utilisent pas TeamsUpgradePolicy. Assurez-vous d’utiliser le dernier client Skype Entreprise.)
 
Vous gérez la transition de vos utilisateurs vers Teams en utilisant le concept de [mode,](migration-interop-guidance-for-teams-with-skype.md)qui est une propriété de [TeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) Un utilisateur ayant été migré vers Teams comme décrit ci-dessus est en mode « TeamsOnly ».  Pour une organisation qui migre vers Teams, l’objectif ultime est de déplacer tous les utilisateurs en mode TeamsOnly.

>[!NOTE]
>Les utilisateurs qui ont un compte Skype Entreprise sur site ne peuvent pas être TeamsOnly. Bien que ces utilisateurs peuvent utiliser Teams en [mode Îles,](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)cela ne fournit pas l’ensemble complet de la fonctionnalité Teams disponible en mode TeamsOnly. Pour que ces utilisateurs teamsOnly, ils doivent être déplacés vers le cloud à l’aide des `Move-CsUser` outils Skype Entreprise Server locaux.

Bien. Commençons.  La première étape consiste à comprendre les [méthodes de mise à niveau à votre disposition.](upgrade-to-teams-on-prem-upgrade-methods.md)







   

## <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utilisation du service Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

