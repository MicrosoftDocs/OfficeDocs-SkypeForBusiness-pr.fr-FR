---
title: Créer des équipes de responsables de personnes dans Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Découvrez comment utiliser un script PowerShell pour créer une équipe pour chaque responsable avec ses directs en tant que membres de l’équipe.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe57656eec61747dd0a43d475444e65d8600e222
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583673"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Créer des équipes de responsables de personnes dans Microsoft Teams


Lorsque vous déployer Microsoft Teams, plutôt que de lancer avec une « page de vide » (pas d’équipes ni de canaux), nous vous recommandons vivement de configurer un cadre de base des équipes et des canaux. Cela permet d’empêcher l'« événement d’équipe », car les utilisateurs créent de nombreuses équipes lorsqu’ils doivent créer des canaux dans des équipes existantes. Pour vous aider à commencer avec une structure d’équipes et de canaux bien conçue, nous avons créé un script PowerShell qui crée une équipe pour chacun de vos responsables de première et deuxième ligne, avec les rapports directs de chaque responsable en tant que membres de l’équipe. Il s’agit d’un script « à un moment donné » (il ne met pas à jour vos équipes ou canaux automatiquement lorsque des personnes sont ajoutées ou supprimées d’une organisation). Il s’agit toutefois d’un outil précieux que vous pouvez utiliser dès le départ pour imposer un ordre dans votre structure Teams. Ce script lit votre azure AD, reçoit une liste des responsables et leurs rapports directs. Elle utilise cette liste pour créer une équipe par responsable de personnes. 

## <a name="how-to-use-the-powershell-script"></a>Comment utiliser le script PowerShell 

Commencez par exécuter les responsables de l’exportation et leur script de [directs](scripts/powershell-script-create-teams-from-managers-export-managers.md) (qui suppose que vous avez déjà exécuté les modules [PowerShell Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) et [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell). Les *responsables de* l’exportation et leur script de direction créent un fichier délimité par des tabulations (ExportedManagerDirects.txt) qui répertorie tous les responsables avec leurs rapports directs. 

Ensuite, exécutez le [script Créer de nouvelles équipes de responsables de personnes.](scripts/powershell-script-create-teams-from-managers-new-teams.md) Ce script est lu dans le ExportedManagerDirects.txt et crée une équipe pour chaque responsable, avec les rapports directs de ce responsable en tant que membres. Si un responsable ou un direct n’est pas activé pour Teams, le script les ignore et ne crée pas d’équipe. (Examinez le rapport, puis réexécutez le script après avoir désactivé Teams pour quiconque en a besoin. Le script ne crée pas de deuxième équipe pour un responsable pour qui il a déjà créé une équipe.)

Pour chaque équipe, le script crée un canal Général et « Simplement pour le plaisir ». 

## <a name="best-practices"></a>Meilleures pratiques

- Demandez à chaque responsable d’ajouter le site web des communications de crise de votre organisation en tant qu’onglet au canal Général pour chaque équipe. 

- Consultez la nouvelle application Communications de crise en lisant ce billet de blog du 8 mars 2020 : Coordonnez la communication de crise à l’aide de [Microsoft Teams + Power Platform.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)

## <a name="related-topics"></a>Sujets associés

[Meilleures pratiques pour organiser les équipes](best-practices-organizing.md)

[Créer une équipe à l’échelle de l’organisation dans Teams](create-an-org-wide-team.md)
