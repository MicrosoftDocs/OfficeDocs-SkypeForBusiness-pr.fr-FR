---
title: Résoudre les problèmes liés à l’accès invité dans Microsoft teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Obtenez de l’aide pour résoudre les problèmes liés à l’accès invité dans Microsoft Teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: e0a3530b7a1f9029d9f671d0a02ef58cbb7907bf
ms.sourcegitcommit: 96d98e145ff300833d827a7d43b4e4b0331b7538
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871730"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Résoudre les problèmes liés à l’accès invité dans Microsoft teams
======================================================

> [!IMPORTANT]
> Il est possible que vous deviez attendre 24 heures pour que vos modifications soient prises en compte. 


- Pour vérifier les problèmes de prise en charge de l’accès invité dans Microsoft Teams, voir [résolution des](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)problèmes liés aux équipes.
- Pour savoir si le problème persiste, consultez les [problèmes connus de Microsoft teams](Known-issues.md).
- Les invités sont des utilisateurs extérieurs à votre organisation. Si une personne se trouve au sein de votre organisation (y compris vos employés, prestataires de contenus sur site ou agents sur site), elle ne peut pas être ajoutée en tant qu’invités. Il en va de même pour vos affiliés.
- Apprenez-en davantage sur les nouvelles fonctionnalités de l’accès invité nouveau ou mis à jour dans la [feuilles de route de teams](https://aka.ms/teamsroadmap).
- Dites-nous ce que vous voulez dans [teams UserVoice](https://aka.ms/TeamsUserVoice).

## <a name="if-your-guests-are-seeing-license-errors"></a>Si vos invités voient des erreurs de licence

L’accès invité dans teams utilise Azure Active Directory (Azure AD) Business to Business (B2B) et son modèle de licence. L'accès invité est fourni avec tous les abonnements Office 365 Business Premium, Office 365 Entreprise et Office 365 Education. Aucune licence Office 365 supplémentaire n'est requise.

Si vous rencontrez des erreurs de gestion des licences, veillez à lire les [recommandations d’Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) pour la gestion des licences en fonction de vos besoins en matière d’accès invité au sein de votre organisation.


- Les licences invité sont comptabilisées au niveau de l’organisation d’invitation. Tenez compte de ce qui suit lorsque vous calculez le nombre de licences dont vous avez besoin.
- Les licences sont comptabilisées au niveau de votre organisation, que les invités invités proviennent d’un autre client Office 365 ou utilisent leurs adresses de messagerie personnelles.

## <a name="support-for-b2b-user-types"></a>Prise en charge des types d’utilisateurs B2B
Actuellement Teams ne prend en charge que les types d’utilisateurs invités de l’État 1 et de l’état 2 [, tels qu’ils sont définis par Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Voir aussi

[Accès invité dans Teams](guest-access.md)


