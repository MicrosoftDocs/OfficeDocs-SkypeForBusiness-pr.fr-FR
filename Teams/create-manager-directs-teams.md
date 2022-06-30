---
title: Créer des équipes de responsables de personnes dans Microsoft Teams
ms.reviewer: pbethi
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Découvrez comment utiliser un script PowerShell pour créer une équipe pour chaque responsable avec ses directs en tant que membres de l’équipe.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd880e58b2c6818b8738afd5fb4e5efaf78642d4
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562583"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Créer des équipes de responsables de personnes dans Microsoft Teams


Lorsque vous déployez Microsoft Teams, plutôt que de lancer avec une « tablette vide » (aucune équipe ou aucun canal), nous vous recommandons vivement de configurer une infrastructure de base d’équipes et de canaux. Cela permet d’éviter la « prolifération des équipes », où les utilisateurs créent de nombreuses équipes lorsqu’ils doivent créer des canaux dans des équipes existantes. Pour vous aider à bien démarrer avec une structure d’équipes et de canaux bien conçue, nous avons créé un script PowerShell qui crée une équipe pour chacun de vos responsables de première et deuxième ligne, avec les rapports directs de chaque responsable en tant que membres de l’équipe. Il s’agit d’un script « ponctuel » (il ne met pas à jour vos équipes ou canaux automatiquement lorsque des personnes sont ajoutées ou retirées d'une organisation). Mais il s'agit d'un outil précieux que vous pouvez utiliser pour imposer un certain ordre à la structure de vos équipes dès le départ. Ce script lit votre Azure AD, obtient une liste des responsables et leurs rapports directs. Elle utilise cette liste pour créer une équipe par responsable de personnes. 

## <a name="how-to-use-the-powershell-script"></a>Comment utiliser le script PowerShell 

Commencez par exécuter les [Gestionnaires d’exportation et leurs de script directs](scripts/powershell-script-create-teams-from-managers-export-managers.md) (ce qui suppose que vous avez déjà exécuté les modules PowerShell [Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) et [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps)). Le script *Gestionnaires d’exportation et leur de directs* crée un fichier délimité par des tabulations (ExportedManagerDirects.txt) qui répertorie tous les responsables avec leurs rapports directs. 

Ensuite, exécutez le script [Créer des équipes de gestionnaire de personnes](scripts/powershell-script-create-teams-from-managers-new-teams.md). Ce script lit le fichier ExportedManagerDirects.txt et crée une équipe pour chaque responsable, avec les rapports directs de ce responsable en tant que membres. Si aucun responsable ou direct n’est activé pour Teams, le script les ignore et ne crée pas d’équipe. (Passez en revue le rapport, puis réexécutez le script une fois que vous avez activé Teams pour toute personne qui en a besoin. Le script ne crée pas de deuxième équipe pour un responsable pour lequel il a déjà créé une équipe.)

Pour chaque équipe, le script crée un canal Général et « Juste pour le plaisir ». 

## <a name="best-practices"></a>Meilleures pratiques

- Demandez à chaque responsable de personnes d’ajouter le site web de communication de crise de votre organisation sous forme d’onglet au canal Général pour chaque équipe. 

- Découvrez la nouvelle application Communications en cas de crise en lisant ce billet de blog du 8 mars 2020 : [Coordonner les communications de crise à l’aide de Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).

## <a name="related-topics"></a>Voir aussi

[Meilleurs pratiques d’organisation d’équipe](best-practices-organizing.md)

[Créer une équipe à l’échelle de l’organisation dans Teams](create-an-org-wide-team.md)