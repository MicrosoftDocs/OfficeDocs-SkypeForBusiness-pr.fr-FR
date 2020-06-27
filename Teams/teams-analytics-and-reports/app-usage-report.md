---
title: Rapport sur l’utilisation des applications Microsoft teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser le rapport utilisation des applications teams dans le centre d’administration Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1a5d5c1bdb5b5bbe58ecdb90721ce24bd0081a65
ms.sourcegitcommit: a73df97a06ea860bfaf5387e0acbf3c724697e14
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44902331"
---
# <a name="microsoft-teams-app-usage-report"></a>Rapport sur l’utilisation des applications Microsoft teams

Le rapport utilisation des applications teams dans le centre d’administration Microsoft teams vous fournit des informations sur les applications que les utilisateurs utilisent dans Teams.  

## <a name="view-the-app-usage-report"></a>Afficher le rapport utilisation des applications

1.  Dans le volet de navigation de gauche du centre d’administration <https://teams.admin.microsoft.com> , cliquez sur **analyse &** rapports d' \> **utilisation**des rapports. Dans l’onglet **afficher les rapports** , sous **rapport**, sélectionnez utilisation des **applications**.

     :::image type="content" source="media/app-usage-report1.png" alt-text="Capture d’écran de l’élément de menu rapports d’utilisation":::

2.  Dans **Plage de dates**, sélectionnez une plage puis cliquez sur **Exécuter le rapport**.

      :::image type="content" source="media/app-usage-report2.png" alt-text="Capture d’écran du rapport utilisation des applications":::

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport utilisation des applications teams peut être consulté pour les tendances au cours des 7, 30 ou 90 derniers jours. |
|**2**   |Chaque rapport comporte une date à laquelle le rapport a été généré. Les rapports indiquent généralement une latence de 24 heures à partir du moment où l’application a été ouverte. <br><br>![Capture d’écran du rapport utilisation des applications avec des plages de dates](media/app-usage-report3.png)|
|**3**    | <ul><li>L’axe X sur les graphiques représente la plage de dates sélectionnée pour ce rapport particulier.</li><li>L’axe Y indique le nombre d’utilisateurs pour lesquels le jour donné a pointé sur le graphique, ces utilisateurs ont ouvert une application au moins une fois, et par conséquent, ils sont considérés comme des utilisateurs actifs et s’affichent sur le total observé lors du survol de la souris.</li></ul>|
|**4**   |Placez le pointeur de la souris sur le point représentant une utilisation des applications à une date donnée pour afficher le nombre d’instances du total des utilisateurs actifs de cette application à la date donnée.  |
|**5**   |Toutes les applications seront incluses, mais en cliquant sur l’icône de filtre, des filtres supplémentaires sont disponibles.  |
|**6**   |Le tableau fournit une répartition des utilisateurs et équipes actifs par nom d’application.<br><ul><li>**Nom** de l’application correspond au nom complet de l’application utilisée dans Teams.</li><li>**Utilisateurs actifs** correspond au nombre d’utilisateurs qui ont ouvert l’application au moins une fois pendant la période spécifiée.</li><li>**Type d’application** est une valeur statique de « Microsoft » ou de « tiers ».</li><li>**Équipes actives** correspond au nombre d’équipes ayant ouvert l’application par au moins un membre de l’équipe et Pendant la période spécifiée.</li><li>**Publisher** est l’éditeur logiciel de l’application.</li><li>**Version** correspond à la version logicielle de l’application, à partir de l’éditeur de l’application.</li></ul><br>![Capture d’écran d’un rapport sur l’utilisation des applications](media/app-usage-report4.png)  |
|**7**  |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.<br><br>![Capture d’écran de la page modifier les colonnes](media/app-usage-report5.png)  |
|**version8**  |Vous pouvez exporter le rapport dans un fichier CSV pour une analyse hors connexion. Cliquez sur **Exporter vers Excel**, puis sous l’onglet **téléchargements** , cliquez sur **Télécharger** pour télécharger le rapport dès qu’il est prêt.<br>![Capture d’écran de la page téléchargements](media/app-usage-report7.png)  |
|**09**   |Lorsque vous affichez le rapport dans Excel, vous verrez également une colonne **ID** , qui représente l’ID de l’application. Un ID d’équipe est généralement une chaîne alphanumérique. Si la colonne **ID** indique * * \n * * * *, cela signifie qu’un utilisateur a demandé la suppression de ses informations.<br>![Capture d’écran du rapport Excel téléchargé](media/app-usage-report8.png)  |

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)