---
title: Qu’est-ce que le tableau de bord de qualité des appels (bord) ?
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: En savoir plus sur le tableau de bord de qualité des appels (bord) et sur son utilisation pour afficher des rapports sur la réunion et la qualité d’appel dans Microsoft Teams.
ms.openlocfilehash: 9ba1956533887314a9ffa7ad994cbb4c81ffe103
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583483"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>Qu’est-ce que le tableau de bord de qualité des appels (bord) ?

Le tableau de bord de qualité des appels Microsoft (bord) : [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) affiche la qualité des appels et des réunions, au **niveau**de l’organisation, pour Microsoft Teams, Skype entreprise Online et Skype entreprise Server 2019. 

  
La version la plus récente de bord comprend un [flux de données en temps réel (NRT)](CQD-data-and-reports.md), ce qui signifie que les enregistrements d’appels sont disponibles dans bord dans les 30 minutes de la fin d’un appel.

Partout où bord inclut les données d’identification de l' [utilisateur final (EUII)](CQD-data-and-reports.md#euii-data), il est géré de la même manière que [EUII dans Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

BORD est conçu pour permettre aux administrateurs d’équipe, aux administrateurs Skype entreprise et aux ingénieurs réseau de surveiller la qualité des appels et des réunions à l’échelle de l’organisation. Vous pouvez utiliser bord pour **optimiser votre réseau** et renforcer la qualité des performances. Lorsque vous recherchez des informations sur les appels et les réunions pour un **utilisateur spécifique**, utilisez les données bord conjointement avec l' [analyse](use-call-analytics-to-troubleshoot-poor-call-quality.md)par utilisateur.

Par exemple, en utilisant bord, vous pouvez déterminer si la qualité d’appel d’un utilisateur (que vous avez observé lors d’une analyse d’appel par utilisateur) est due à un problème de réseau qui affecte également de nombreux autres utilisateurs. BORD capture les appels individuels et la qualité générale des appels passés à l’aide d’équipes ou de Skype entreprise. Avec bord, les modèles globaux peuvent devenir évidents, afin que les ingénieurs du réseau puissent effectuer des analyses éclairées de la qualité des appels. BORD fournit des rapports sur les métriques de la qualité d’appel qui vous permettent d’avoir une vue d’ensemble de la qualité des appels, des flux client-client, des flux client-client et du [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)de qualité vocale. 
  
![Capture d’écran du tableau de bord de qualité des appels.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

Dans bord, nous vous encourageons à télécharger des informations sur la création et le point de terminaison, qui vous permet d’utiliser des rapports d’emplacement pour analyser la qualité et la fiabilité des appels au sein d’un immeuble. Les données peuvent être évaluées pour déterminer si le problème est limité à un utilisateur unique ou s’il concerne un plus grand nombre d’utilisateurs. Pour activer le bâtiment ou les vues spécifiques aux points de terminaison dans bord, un administrateur doit [Télécharger les informations de construction ou de point de terminaison](CQD-upload-tenant-building-data.md) sur la page de téléchargement de données du **client** bord.

![Capture d’écran des rapports d’emplacement du tableau de bord de qualité des appels.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Ne manquez pas notre article [gérer l’appel et la qualité](quality-of-experience-review-guide.md) de la réunion, qui offre des instructions détaillées au sein de l’administrateur teams ou du technicien de support responsable de la gestion de la qualité du service dans Teams.

## <a name="older-version-of-cqd-cqdlynccom"></a>Version antérieure de bord (CQD.lync.com)

La version actuelle de bord ( https://CQD.Teams.microsoft.com) remplace l’ancienne version d’bord ( https://CQD.lync.com) . Vous pouvez toujours utiliser CQD.lync.com (disponible dans le centre d’administration Skype entreprise), mais à partir du 1er juillet 2020, il utilise les données de bord. Teams.microsoft.com. Nous désactivons l’accès à CQD.lync.com bientôt, donc vous devez accéder à bord. Teams.microsoft.com si vous ne l’avez pas déjà fait.

> [!IMPORTANT]
> À compter du 1er juillet 2020, vous ne pouvez plus afficher ni modifier vos données de bâtiment ou de requête à partir de l’ancien bord (CQD.lync.com). Si vous n’avez pas déjà migré ces données à partir de CQD.lync.com et que vous en avez encore besoin, consignez un ticket de support.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Utiliser Power BI pour analyser des données de bord

Nouveauté de janvier 2020 : [Télécharger les modèles de requête Power bi pour bord](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modèles Power BI personnalisables que vous pouvez utiliser pour analyser et enregistrer vos données bord.

Pour en savoir plus, voir [utiliser Power bi pour analyser les données de bord](CQD-Power-BI-query-templates.md) .



## <a name="related-topics"></a>Voir aussi

[Améliorer et surveiller la qualité des appels pour teams](monitor-call-quality-qos.md)

[Configurer le tableau de bord de qualité des appels (bord)](turning-on-and-using-call-quality-dashboard.md)

[Télécharger le client et générer des données](CQD-upload-tenant-building-data.md)

[Rapports et données bord](CQD-data-and-reports.md)

[Utiliser bord pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans bord](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification des flux dans bord](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser des données de bord](CQD-Power-BI-query-templates.md)


[Résolution des problèmes de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)