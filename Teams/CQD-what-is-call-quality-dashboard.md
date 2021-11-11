---
title: Qu’est-ce que le tableau de bord de qualité des appels ?
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Découvrez le tableau de bord de qualité des appels et comment l’utiliser pour consulter des rapports sur la qualité des réunions et des appels Microsoft Teams.
ms.openlocfilehash: f87f8184b0417d04206d31780392f21dca387d10
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909555"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>Qu’est-ce que le tableau de bord de qualité des appels ?

Tableau de bord de qualité des appels de Microsoft (CQD) - Affiche la qualité des appels et des réunions, au niveau de l’organisation, pour Microsoft Teams, Skype Entreprise Online et [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Skype Entreprise Server 2019.  

  
La dernière version du DQD comprend un flux de données en temps quasi réel [(NRT),](CQD-data-and-reports.md)ce qui signifie que les enregistrements d’appel sont disponibles dans le point de qualité des appels dans les 30 minutes après la fin de l’appel.

Chaque fois que le CQD inclut des informations d’identification des utilisateurs finux [(EUII),](CQD-data-and-reports.md#euii-data)il est géré de la même façon que [euII](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)dans Microsoft 365.

Le CQD est conçu pour aider les Teams, les Skype Entreprise et les ingénieurs réseau à surveiller la qualité des appels et des réunions à l’échelle de l’organisation. Vous utiliserez le CQD pour optimiser **votre réseau afin** d’optimiser la qualité des performances. Lorsque vous avez besoin d’examiner les informations d’appel et de réunion d’un utilisateur **spécifique,** utilisez les données du CQD conjointement avec l’analyse des appels par [utilisateur.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Par exemple, vous pouvez déterminer que la qualité des appels d’un utilisateur (observée à l’aide de l’analyse des appels par utilisateur) est due à un problème de réseau qui affecte également de nombreux autres utilisateurs. Le CQD capture à la fois l’expérience d’appel individuel et la qualité globale des appels effectués à l’aide d Teams ou Skype Entreprise. Grâce au CQD, des modèles globaux peuvent être mis en évidence pour que les ingénieurs réseau puisse évaluer en connaissance de cause la qualité des appels. Le CQD fournit des rapports sur les mesures de qualité des appels, qui fournissent des informations sur la qualité globale des appels, les flux client-serveur, les flux client et le SLA de [qualité vocale.](https://go.microsoft.com/fwlink/p/?linkid=846252) 
  
![Capture d’écran du tableau de bord de qualité des appels.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

Dans le CQD, nous vous encourageons à télécharger les informations de bâtiment et de point de terminaison, qui vous permet d’utiliser des rapports Location-Enhanced pour analyser la qualité et la fiabilité des appels au sein du bâtiment d’un utilisateur. Les données peuvent être évaluées pour déterminer si le problème est isolé pour un seul utilisateur ou affecte un segment plus important d’utilisateurs. Pour activer les affichages spécifiques du point de [](CQD-upload-tenant-building-data.md) terminaison ou du point de terminaison dans le DQD, un administrateur doit télécharger les informations de bâtiment ou de point de terminaison sur la page Données du client du Télécharger du point **de** terminaison.

![Capture d’écran des rapports d’utilisation du tableau de Location-Enhanced qualité des appels.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Ne manquez pas [notre](quality-of-experience-review-guide.md) article Gérer la qualité des appels et des réunions, qui propose des conseils détaillés pour l’administrateur Teams ou l’ingénieur support responsable de la gestion de la qualité du service dans Teams.


## <a name="use-power-bi-to-analyze-cqd-data"></a>Utiliser Power BI pour analyser les données du CQD

Nouveautés de janvier 2020 : télécharger Power BI modèles de [requête pour le CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Modèles Power BI personnalisables que vous pouvez utiliser pour analyser et signaler vos données de CQD.

Lisez Utiliser Power BI pour analyser les données du [CQD](CQD-Power-BI-query-templates.md) et en savoir plus.



## <a name="related-topics"></a>Sujets associés

[Améliorer et surveiller la qualité des appels pour les Teams](monitor-call-quality-qos.md)

[Configurer le tableau de bord de qualité des appels](turning-on-and-using-call-quality-dashboard.md)

[Télécharger données de bâtiment et de client](CQD-upload-tenant-building-data.md)

[Données et rapports du CQD](CQD-data-and-reports.md)

[Utiliser le CQD pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans le DQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification des flux dans le CQD](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser les données du CQD](CQD-Power-BI-query-templates.md)


[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)
