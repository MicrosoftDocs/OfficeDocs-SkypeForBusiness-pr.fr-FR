---
title: Effectuer une mise à niveau vers teams à partir d’un déploiement local de Skype entreprise-Microsoft teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
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
ms.openlocfilehash: e146394b5f000ce984d7bfaff5e6674c2c091b98
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955885"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Mise à niveau de Skype entreprise vers teams &mdash; pour les administrateurs informatiques

## <a name="overview"></a>Vue d’ensemble

Lorsque vous procédez à la mise à niveau de Skype entreprise vers équipes, certaines organisations requièrent un lancement progressif qui est planifié et géré par leurs services informatiques. Les Articles de cette section s’appliquent principalement aux administrateurs informatiques au sein d’organisations de grande envergure. Ces organisations sont généralement locales, mais peuvent également être des organisations Skype entreprise Online de grande envergure. Avant de lire cet article, assurez-vous de lire la [mise à niveau de votre équipe](upgrade-start-here.md) et de [l’infrastructure de mise à niveau](upgrade-framework.md).


Les articles suivants vous guident tout au long du processus de mise à niveau de votre organisation : 

- [Méthodes de mise à niveau](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Outils de gestion de votre mise à niveau](upgrade-to-teams-on-prem-tools.md)
- [Autres considérations concernant les organisations avec Skype entreprise en local](upgrade-to-teams-on-prem-considerations.md)
- [Implémenter votre mise à niveau](upgrade-to-teams-on-prem-implement.md)
- [Considérations relatives au réseau téléphonique public commuté (RTC)](upgrade-to-teams-on-prem-pstn-considerations.md)

De plus, les articles suivants décrivent des concepts importants de mise à niveau et des comportements de coexistence :

- [Coexistence des équipes et de Skype entreprise](upgrade-to-teams-on-prem-coexistence.md)
- [Modes de coexistence-référence](migration-interop-guidance-for-teams-with-skype.md)
- [Expérience client Teams et conformité aux modes coexistence](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
>Les articles suivants utilisent les termes Skype entreprise Online, Skype entreprise Server en local et Skype entreprise. Ce terme fait référence à des versions en ligne et locales.

Avant de commencer, sachez qu’un utilisateur qui a migré vers teams n’utilise plus un client Skype entreprise, à l’exception de la participation à une réunion hébergée dans Skype entreprise.  Toutes les conversations et les appels entrants dans le client teams de l’utilisateur, que l’expéditeur utilise teams ou Skype entreprise. Toutes les nouvelles réunions organisées par l’utilisateur migré seront planifiées en tant que réunions d’équipes. Si l’utilisateur tente d’utiliser le client Skype entreprise, l’ouverture de conversations et d’appels est bloquée.  Toutefois, l’utilisateur peut (et doit) toujours utiliser le client Skype entreprise pour participer aux réunions Skype entreprise auxquelles il est invité. (Les anciens clients Skype entreprise livrés avant 2017 ne respectent pas TeamsUpgradePolicy. Vérifiez que vous utilisez la dernière version du client Skype entreprise.)
 
Vous gérez la transition de votre utilisateur vers teams à l’aide du concept de [mode](migration-interop-guidance-for-teams-with-skype.md), qui est une propriété de [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). Un utilisateur qui a été migré vers teams comme décrit ci-dessus est en mode « TeamsOnly ».  Dans le cas d’une organisation migrant vers Teams, l’objectif ultime consiste à déplacer tous les utilisateurs vers le mode TeamsOnly.

Bien. Commençons.  La première étape consiste à comprendre les [méthodes de mise à niveau disponibles](upgrade-to-teams-on-prem-upgrade-methods.md).







   

## <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer une connectivité hybride entre Skype entreprise Server et Microsoft 365 ou Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utiliser le service de migration de réunion (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

