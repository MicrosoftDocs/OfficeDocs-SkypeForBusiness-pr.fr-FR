---
title: Créer des équipes du gestionnaire de personnes dans Microsoft teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Découvrez comment utiliser un script PowerShell pour créer une équipe pour chaque responsable en tant que membre de l’équipe.
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
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Créer des équipes du gestionnaire de personnes dans Microsoft teams


Lorsque vous déployez Microsoft teams au lieu d’un « ardoise vierge » (sans équipes ou canaux), nous vous recommandons vivement de définir une infrastructure de base des équipes et des canaux. Cela permet d’éviter une « prolifération des équipes », qui permet aux utilisateurs de créer de nombreuses équipes lorsqu’elles doivent créer des canaux dans les équipes existantes. Pour vous aider à prendre en main une structure d’équipes et de canaux bien conçue, nous avons créé un script PowerShell permettant de créer une équipe pour chacun de vos premiers et deuxièmes responsables de personnes, avec les rapports directs de chaque responsable en tant que membres de l’équipe. Il s’agit d’un script « ponctuelle » (il n’est pas mis à jour automatiquement pour les équipes ou les canaux lors de l’ajout ou de la suppression de personnes d’une organisation). C’est un outil précieux qui peut être utilisé pour imposer une commande dans votre structure teams depuis le début. Ce script lit votre Azure AD et obtient la liste des responsables et leurs rapports directs. Il utilise cette liste pour créer une équipe par responsable de personnes. 

## <a name="how-to-use-the-powershell-script"></a>Utiliser le script PowerShell 

Commencez par exécuter les [responsables d’exportation et leurs scripts de direction](scripts/powershell-script-create-teams-from-managers-export-managers.md) (ce qui suppose que vous avez déjà exécuté les modules [AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) et [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell). Les *gestionnaires d’exportation et leurs* scripts de direction créent un fichier délimité par des tabulations (ExportedManagerDirects.txt) qui recense tous les responsables avec leurs rapports directs. 

Ensuite, exécutez le [script créer de nouvelles équipes du gestionnaire de personnes](scripts/powershell-script-create-teams-from-managers-new-teams.md). Ce script lit le fichier ExportedManagerDirects.txt et crée une équipe pour chaque responsable, avec ses rapports directs en tant que membres. Si un responsable ou une direction n’est pas activé pour Teams, le script les ignore et ne crée aucune équipe. (Consultez le rapport, puis relancez le script une fois que vous avez activé les équipes pour toute personne qui en a besoin. Le script ne crée pas de deuxième équipe pour les gestionnaires pour lesquels il a déjà créé une équipe.)

S’il s’agit d’une équipe, le script crée une chaîne générale et « pour plaisir ». 

## <a name="best-practices"></a>Meilleures pratiques

- Demandez à chaque gestionnaire de personnes d’ajouter le site Web de communication de crise de votre organisation en tant qu’onglet au canal général de chaque équipe. 

- Consultez la nouvelle application de communications de crise en lisant ce 8 mars, billet de blog 2020 : [coordonner les communications de crise à l’aide de Microsoft teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).

## <a name="related-topics"></a>Voir aussi

[Recommandations en matière d’organisation des équipes](best-practices-organizing.md)

[Créer une équipe à l’échelle de l’organisation dans Teams](create-an-org-wide-team.md)
