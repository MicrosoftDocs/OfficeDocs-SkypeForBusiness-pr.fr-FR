---
title: Résolution des problèmes liés à l’accès invité dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: c8d54e236583211c2a8169987bf03ceba756facf
ms.sourcegitcommit: 1957a06d4bae3d42b4e3b6d4bd8ff2752a19d377
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60641214"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Résolution des problèmes liés à l’accès invité dans Microsoft Teams

- Pour savoir si nous sommes au courant de votre problème, consultez le [support Teams dans votre organisation.](/MicrosoftTeams/troubleshoot/teams-welcome)
- Pour rechercher les problèmes de prise en charge actuels avec l’accès invité dans Teams, voir [Résolution des problèmes liés à Teams](/MicrosoftTeams/troubleshoot/).
- Les invités sont des personnes extérieures à votre organisation. Si une personne se trouve à l'intérieur de votre organisation (y compris vos employés et les fournisseurs et agents sur site), elle ne peut pas être ajoutée en tant qu'invité. La même chose s'applique pour les affiliés.
- Vous trouverez des informations sur les fonctionnalités d'accès invité à venir, nouvelles ou mises à jour, dans la [Feuille de route de Teams](https://aka.ms/teamsroadmap).
- Indiquez-nous ce que vous souhaitez dans [Teams UserVoice](https://aka.ms/TeamsUserVoice).

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a>Si vos invités remarquent des erreurs de licence

L’accès invité dans Teams utilise Azure Active Directory (Azure AD) Business to Business (B2B) et son modèle de licence. L’accès invité est inclus dans tous les abonnements Microsoft 365 Business Standard, Office 365 Enterprise et Office 365 Éducation. Aucune licence Microsoft 365 ou Office 365 supplémentaire n'est requise.

> [!NOTE]
> Teams clients doivent être activés sur le client d’un invité pour que les invités puissent se connecter et utiliser Teams en tant qu’invité sur un autre client (ressource).

Si vous voyez des erreurs de licence, veillez à lire le modèle de facturation pour [les identités externes Azure AD](/azure/active-directory/external-identities/external-identities-pricing) afin de déterminer les conditions de licence requises pour répondre à vos besoins en matière d’accès invité dans votre organisation.

- Les licences invité sont décomptées du nombre existant au sein de l’organisation qui invite. Tenez-en compte au moment de calculer le nombre de licences dont vous avez besoin.
- Les licences sont comptabilisées dans votre organisation, que les invités proviennent d’une autre Microsoft 365 organisation ou utilisent leur adresse de messagerie personnelle.

## <a name="related-topics"></a>Rubriques connexes

[Accès invité dans Teams](guest-access.md)

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)
