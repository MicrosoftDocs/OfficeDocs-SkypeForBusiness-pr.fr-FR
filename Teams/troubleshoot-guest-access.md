---
title: Résolution des problèmes liés à l’accès invité dans Microsoft Teams
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
description: Obtenir de l'aide pour résoudre et corriger les problèmes liés à l’accès invité dans Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 32a334f4866c1874f60e85e3b74908f161d45a33
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691550"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Résolution des problèmes liés à l’accès invité dans Microsoft Teams
======================================================

- Pour savoir si le problème persiste, consultez l' [équipe de support au sein de votre organisation](Known-issues.md).
- Pour rechercher les problèmes de prise en charge actuels avec l’accès invité dans Teams, voir [Résolution des problèmes liés à Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).
- Les invités sont des utilisateurs extérieurs à votre organisation. Si une personne se trouve à l'intérieur de votre organisation (y compris vos employés et les fournisseurs et agents sur site), elle ne peut pas être ajoutée en tant qu'invité. La même chose s'applique pour les affiliés.
- Vous trouverez des informations sur les fonctionnalités d'accès invité à venir, nouvelles ou mises à jour, dans la [Feuille de route de Teams](https://aka.ms/teamsroadmap).
- Indiquez-nous ce que vous souhaitez dans [Teams UserVoice](https://aka.ms/TeamsUserVoice).

## <a name="if-your-guests-are-seeing-license-errors"></a>Si vos invités remarquent des erreurs de licence

L’accès invité dans Teams utilise Azure Active Directory (Azure AD) Business to Business (B2B) et son modèle de licence. L’accès invité est inclus dans tous les abonnements Microsoft 365 Business Standard, Office 365 Enterprise et Office 365 Éducation. Aucune licence Microsoft 365 ou Office 365 supplémentaire n'est requise.

> [!NOTE]
> Pour pouvoir se connecter et utiliser les équipes en tant qu’invités sur un autre client (ressource), les équipes doivent être activées sur le client d’origine d’un invité.

Si vous rencontrez des erreurs de gestion des licences, veillez à lire les [recommandations d’Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) pour la gestion des licences en fonction de vos besoins en matière d’accès invité au sein de votre organisation.


- Les licences invité sont décomptées du nombre existant au sein de l’organisation qui invite. Tenez-en compte au moment de calculer le nombre de licences dont vous avez besoin.
- Les licences sont comptabilisées au niveau de votre organisation, que les invités invités proviennent d’une autre organisation 365 ou d’une organisation Office 365 ou utilisent leurs adresses de messagerie personnelles.

## <a name="support-for-b2b-user-types"></a>Prise en charge des types d’utilisateur B2B
Actuellement, Teams prend uniquement en charge les types d’États 1 et 2 des utilisateurs invités [définis par Azure B2B.](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)

## <a name="related-topics"></a>Rubriques connexes

[Accès invité dans Teams](guest-access.md)


