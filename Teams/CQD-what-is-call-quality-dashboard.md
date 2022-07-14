---
title: Qu’est-ce que le tableau de bord de qualité des appels (CQD) ?
author: CarolynRowe
ms.author: crowe
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
description: Découvrez le tableau de bord de qualité des appels (CQD) et comment l’utiliser pour afficher des rapports sur la qualité des réunions et des appels dans Microsoft Teams.
ms.openlocfilehash: 3bc3c9dcd83e4ff95a07fbffb6f07da39d254cde
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790069"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>Qu’est-ce que le tableau de bord de qualité des appels (CQD) ?

Microsoft Call Quality Dashboard (CQD) : [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) affiche la qualité des appels et des réunions, à **l’échelle de l’organisation**, pour Microsoft Teams, Skype Entreprise Online et Skype Entreprise Server 2019. 

  
La dernière version de CQD comporte un [flux de données en quasi-temps réel (NRT),](CQD-data-and-reports.md) ce qui signifie que les enregistrements d’appel sont disponibles dans CQD dans les 30 minutes suivant la fin d’un appel.

Partout où CQD inclut des [données d’informations d’identification des utilisateurs finaux (EUII),](CQD-data-and-reports.md#euii-data) elle est gérée de la même façon que [l’EUII dans Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

CQD est conçu pour aider les administrateurs Teams, les administrateurs Skype Entreprise et les ingénieurs réseau à surveiller la qualité des appels et des réunions à l’échelle de l’organisation. Vous allez utiliser CQD pour vous aider à **optimiser votre réseau** pour améliorer la qualité des performances. Lorsque vous devez examiner les informations d’appel et de réunion pour un **utilisateur spécifique**, utilisez les données CQD conjointement avec [l’analytique des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md) par utilisateur.

Par exemple, à l’aide de CQD, vous pouvez déterminer que la qualité d’appel médiocre d’un utilisateur (que vous avez observée à l’aide de l’analyse des appels par utilisateur) est due à un problème réseau qui affecte également de nombreux autres utilisateurs. CQD capture à la fois l’expérience des appels individuels et la qualité globale des appels effectués à l’aide de Teams ou de Skype Entreprise. Avec CQD, les modèles globaux peuvent devenir évidents, afin que les ingénieurs réseau puissent effectuer des évaluations éclairées de la qualité des appels. CQD fournit des rapports de métriques de qualité des appels qui vous donnent un aperçu de la qualité globale des appels, des flux serveur-client, des flux client-client et du [contrat SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) de qualité vocale. 
  
![Capture d’écran du tableau de bord qualité des appels.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

Dans CQD, nous vous encourageons à charger des informations sur le bâtiment et le point de terminaison, ce qui vous permet d’utiliser Location-Enhanced Rapports pour analyser la qualité et la fiabilité des appels dans le bâtiment d’un utilisateur. Les données peuvent être évaluées pour déterminer si le problème est isolé pour un seul utilisateur ou affecte un segment plus important d’utilisateurs. Pour activer les affichages spécifiques à la génération ou au point de terminaison dans CQD, un administrateur doit charger des informations sur le [bâtiment ou le point de terminaison](CQD-upload-tenant-building-data.md) sur la page de **chargement des données du locataire** CQD.

![Capture d’écran des rapports Location-Enhanced du tableau de bord qualité des appels.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Ne manquez pas notre article [gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md) , qui fournit des conseils détaillés à l’administrateur teams ou à l’ingénieur de support responsable de la gestion de la qualité des services dans Teams.


## <a name="use-power-bi-to-analyze-cqd-data"></a>Utiliser Power BI pour analyser les données TBQA

Nouveauté de janvier 2020 : [Télécharger Power BI modèles de requête pour les](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)CQD . Modèles de Power BI personnalisables que vous pouvez utiliser pour analyser et signaler vos données CQD.

Lisez [Utilisez Power BI pour analyser les données CQD](CQD-Power-BI-query-templates.md) pour en savoir plus.



## <a name="related-topics"></a>Rubriques connexes

[Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md)

[Configurer le tableau de bord de qualité des appels (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Charger le client et créer des données](CQD-upload-tenant-building-data.md)

[Données et rapports du TBQA](CQD-data-and-reports.md)

[Utiliser le TBQA pour gérer la qualité des appels et des réunions](quality-of-experience-review-guide.md)

[Dimensions et mesures disponibles dans le TBQA](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification de flux de données dans le TBQA](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser les données TBQA](CQD-Power-BI-query-templates.md)


[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)
