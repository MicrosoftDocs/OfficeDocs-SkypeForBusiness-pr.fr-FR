---
title: Microsoft Teams d’utilisation des applications
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser le rapport d Teams’utilisation des applications dans le Microsoft Teams d’administration.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f58634bea7a2846e35ddc4dbc8da0be13396e616
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046010"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams d’utilisation des applications

Le Teams d’utilisation des applications dans le Centre Microsoft Teams d’administration vous fournit des informations sur les applications que les utilisateurs utilisent dans Teams.  

## <a name="view-the-app-usage-report"></a>Afficher le rapport Utilisation des applications

1.  Dans le panneau de navigation gauche du Centre d’administration, cliquez sur <https://admin.teams.microsoft.com> **Analyse & rapports** \> **d’utilisation** des rapports. Sous **l’onglet Afficher les rapports,** sous **Rapport,** sélectionnez **Utilisation des applications.**

     :::image type="content" source="media/app-usage-report1.png" alt-text="Capture d’écran de l’élément de menu Rapports d’utilisation.":::

2.  Dans **Plage de dates**, sélectionnez une plage puis cliquez sur **Exécuter le rapport**.

      :::image type="content" source="media/app-usage-report2.png" alt-text="Capture d’écran du rapport Utilisation des applications.":::

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le Teams utilisation des applications permet d’afficher les tendances des 7, 30 ou 90 derniers jours. |
|**2**   |Chaque rapport indique la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 heures par rapport à l’ouverture d’une application. <br><br>![Capture d’écran du rapport Utilisation des applications affichant des plages de dates.](media/app-usage-report3.png)|
|**3**    | <ul><li>L’axe X sur les graphiques est la plage de dates sélectionnée pour le rapport spécifique.</li><li>L’axe Y indique le nombre d’utilisateurs qui, pour un jour donné, ont survolé le graphique, ces utilisateurs ont ouvert une application au moins une fois et sont considérés comme des utilisateurs actifs, ce qui leur permet d’atteindre le total vu au survol avec la souris.</li></ul>|
|**4**   |Pointez sur le point représentant une utilisation des applications à une date donnée pour voir le nombre d’instances du nombre total d’utilisateurs actifs de cette application à cette date donnée.  |
|**5**   |Toutes les applications seront incluses, mais en choisissant l’icône Filtrer, des filtres supplémentaires sont disponibles.  |
|**6**   |Le tableau vous offre une répartition par nom d’application des utilisateurs et équipes actifs.<br><ul><li>**Le nom d’application** est le nom d’affichage de l’application utilisée dans Teams.</li><li>**Le nombre** d’utilisateurs actifs a ouvert l’application au moins une fois au cours de la période spécifiée.</li><li>**Le type d’application** est une valeur statique de « Microsoft » ou de « Tiers ».</li><li>**Les équipes** actives sont le nombre d’équipes qui ont ouvert l’application par au moins un membre de l’équipe et pendant les périodes spécifiées.</li><li>**Publisher** est l’éditeur du logiciel de l’application.</li><li>**Version** est la version logicielle de l’application, de l’éditeur de l’application.</li></ul><b> Remarque :</b> Pour l’instant, les applications « Utilisateurs actifs » et « Équipes actives » sont calculées pour les applications utilisées uniquement dans les canaux.     
<br>![Capture d’écran d’un rapport Utilisation des applications.](media/app-usage-report4.png)|
|**7**  |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.<br><br>![Capture d’écran de la page Modifier les colonnes.](media/app-usage-report5.png)  |
|**8**  |Vous pouvez exporter le rapport dans un fichier CSV à des fin d’analyse en mode hors connexion. Cliquez **sur Exporter vers Excel,** puis sous l’onglet **Téléchargements,** cliquez sur Télécharger pour télécharger le rapport lorsqu’il est prêt. <br>![Capture d’écran de la page Téléchargements.](media/app-usage-report7.png)  |
|**9**   |Lorsque vous affichez le rapport dans Excel, vous voyez également une colonne **ID** qui représente l’ID d’application. Un ID d’équipe est généralement une chaîne alphanumérique. Si la **colonne ID** indique **\n*****, cela signifie qu’un utilisateur a demandé la suppression de ses informations.<br>![Capture d’écran du Excel téléchargement.](media/app-usage-report8.png)  |

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)