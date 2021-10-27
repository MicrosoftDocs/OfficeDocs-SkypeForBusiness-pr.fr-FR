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
ms.openlocfilehash: 7679652f0cb93e445e72af80307803b1e3197992
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2021
ms.locfileid: "60596211"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams d’utilisation des applications

Le Teams d’utilisation des applications dans le Centre Microsoft Teams d’administration vous fournit des informations sur les applications que les utilisateurs utilisent dans Teams.  

## <a name="view-the-app-usage-report"></a>Afficher le rapport Utilisation des applications

1. Dans le panneau de navigation gauche du Centre d’administration, cliquez sur <https://admin.teams.microsoft.com> **Analyse & rapports**  >  **d’utilisation** des rapports.<br><br>![Capture d’écran de l’élément de menu Rapports d’utilisation.](media/app-usage-report1.png "Capture d’écran de l’élément de menu Rapports d’utilisation.")
2. Sous **l’onglet Afficher les rapports,** sous **Rapport,** sélectionnez **Utilisation des applications.**

3. Dans **Plage de dates**, sélectionnez une plage puis cliquez sur **Exécuter le rapport**. Le Teams utilisation des applications permet d’afficher les tendances des 7, 30 ou 90 derniers jours.<br><br>![Capture d’écran du rapport Utilisation des applications.](media/app-usage-report2.png "Capture d’écran du rapport Utilisation des applications.")


## <a name="interpret-the-report"></a>Interpréter le rapport

:::image type="content" alt-text="Capture d’écran Teams rapport d’utilisation des applications dans le Teams d’administration avec des appels." source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

1. Chaque rapport a une date dans le coin supérieur gauche qui indique quand il a été créé. Les rapports reflètent généralement une latence de 24 heures par rapport à l’ouverture d’une application.

2. L’axe Y du graphique indique le nombre d’utilisateurs qui, pour la date que vous avez sélectionnée en pointant sur le graphique, sont considérés comme utilisateurs actifs, car ils ont ouvert une application au moins une fois.

3. L’axe X du graphique est la plage de dates que vous avez sélectionnée pour le rapport.

4. Pointez sur le point représentant l’utilisation d’une application à une date quelconque pour voir le nombre total d’utilisateurs actifs de cette application à cette date.

5. Pour sélectionner d’autres applications, dans  le coin supérieur droit, cliquez sur l’icône Filtrer, sélectionnez ou tapez de nouveaux critères, puis cliquez sur **Appliquer.**

6. Le tableau en bas du rapport indique les utilisateurs actifs et les équipes par nom d’application.

   - **Le nom de** l’application est le nom d’affichage de l’application utilisée dans Teams.
   - **Le nombre** d’utilisateurs actifs a ouvert l’application au moins une fois au cours de la période spécifiée.
   - **Le type d’application** est une valeur statique de « Microsoft » ou de « Tiers ».
   - **Les équipes** actives sont les équipes qui ont ouvert l’application par au moins un membre de l’équipe et pendant les périodes spécifiées.
   - **Publisher** est l’éditeur du logiciel de l’application.
   - **Version** est la version logicielle de l’application, de l’éditeur de l’application.

   > [!NOTE]
   > **Les utilisateurs actifs** et **les équipes** actives sont calculés pour les applications utilisées dans les canaux uniquement.

7. Pour ajouter ou supprimer des colonnes dans le  tableau, en  haut à droite, cliquez sur l’icône Modifier les colonnes, sous l’onglet Modifier les colonnes, sélectionnez de nouveaux critères, puis cliquez sur **Appliquer.**

8. Pour exporter le rapport dans un fichier CSV à des fin d’analyse en mode hors connexion, dans le coin supérieur droit, sélectionnez l’icône Exporter vers **Excel,** puis sous l’onglet **Téléchargements** sous **État,** cliquez sur **Télécharger.**

   :::image type="content" alt-text="Capture d’écran du volet Téléchargements." source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

9. Lorsque vous affichez le rapport dans Excel, vous voyez également une colonne **ID,** qui représente l’ID d’application, généralement une chaîne alphanumérique. Si **l’ID** est **\n,** cela signifie qu’un utilisateur a demandé la suppression de ses informations.

   ![Capture d’écran du Excel téléchargement.](media/app-usage-report8.png "Capture d’écran du Excel téléchargement.")

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)
