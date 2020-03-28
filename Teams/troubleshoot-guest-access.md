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
ms.openlocfilehash: 0c0f65f7026e6c083d9230551d689f0dd19d6b0d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837634"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Résolution des problèmes liés à l’accès invité dans Microsoft Teams
======================================================

> [!IMPORTANT]
> Il est possible que les modifications ne prennent effet qu'après 24 heures. 


- Pour rechercher les problèmes de prise en charge actuels avec l’accès invité dans Teams, voir [Résolution des problèmes liés à Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).
- Pour vérifier que votre problème est connu, consultez les [Problèmes connus pour Microsoft Teams](Known-issues.md).
- Les invités sont des utilisateurs extérieurs à votre organisation. Si une personne se trouve à l'intérieur de votre organisation (y compris vos employés et les fournisseurs et agents sur site), elle ne peut pas être ajoutée en tant qu'invité. La même chose s'applique pour les affiliés.
- Vous trouverez des informations sur les fonctionnalités d'accès invité à venir, nouvelles ou mises à jour, dans la [Feuille de route de Teams](https://aka.ms/teamsroadmap).
- Indiquez-nous ce que vous souhaitez dans [Teams UserVoice](https://aka.ms/TeamsUserVoice).

## <a name="if-your-guests-are-seeing-license-errors"></a>Si vos invités remarquent des erreurs de licence

L’accès invité dans Teams utilise Azure Active Directory (Azure AD) Business to Business (B2B) et son modèle de licence. L'accès invité est fourni avec tous les abonnements Office 365 Business Premium, Office 365 Entreprise et Office 365 Education. Aucune licence Office 365 supplémentaire n'est requise.

Si vous voyez des erreurs liées aux licences, assurez-vous de lire le [Guide d'attribution de licences pour Azure Active Directory B2B Collaboration](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) pour déterminer si les critères de licences répondent à vos besoins pour l’accès invité au sein de votre organisation.


- Les licences invité sont décomptées du nombre existant au sein de l’organisation qui invite. Tenez-en compte au moment de calculer le nombre de licences dont vous avez besoin.
- Les licences sont décomptées du nombre existant au sein de votre organisation si les invités proviennent d’un autre client Office 365 ou utilisent leur adresse de courrier personnelle.

## <a name="support-for-b2b-user-types"></a>Prise en charge des types d’utilisateur B2B
Actuellement, Teams prend uniquement en charge les types d’États 1 et 2 des utilisateurs invités [définis par Azure B2B.](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)

## <a name="related-topics"></a>Rubriques connexes

[Accès invité dans Teams](guest-access.md)


