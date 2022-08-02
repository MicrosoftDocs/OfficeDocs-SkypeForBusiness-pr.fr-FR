---
title: Rapport d’utilisation des applications Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Découvrez comment utiliser le rapport d’utilisation des applications Teams dans le Centre d’administration Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f9dadab5ee29a15e939a120cddcd3e889d524d88
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156722"
---
# <a name="microsoft-teams-app-usage-report"></a>Rapport d’utilisation des applications Microsoft Teams

Le rapport d’utilisation des applications Teams dans le Centre d’administration Microsoft Teams vous fournit des informations sur les applications que les utilisateurs utilisent dans Teams.  

## <a name="view-the-app-usage-report"></a>Afficher le rapport d’utilisation des applications

1. Dans le volet de navigation gauche du Centre d’administration Teams, sélectionnez **Analyse & rapports** > **[d’utilisation](https://admin.teams.microsoft.com/analytics/reports)**.

   :::image type="content" source="media/app-usage-report1.png" alt-text="Capture d’écran de l’élément de menu Rapports d’utilisation.":::

1. Sous l’onglet **Afficher les rapports** , sous **Rapport**, sélectionnez **Utilisation des applications**.

1. Sous **Plage de dates**, sélectionnez une plage, puis **sélectionnez Exécuter le rapport**. Vous pouvez afficher le rapport d’utilisation des applications Teams pour les tendances des 7, 30 ou 90 derniers jours.

   :::image type="content" source="media/app-usage-report2-trimmed.png" alt-text="Capture d’écran de l’interface du rapport Utilisation des applications." lightbox="media/app-usage-report2.png":::

## <a name="interpret-the-report"></a>Interpréter le rapport

:::image type="content" alt-text="Capture d’écran du rapport d’utilisation des applications Teams dans le Centre d’administration Teams avec des légendes." source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

Chaque rapport a une date en haut à gauche qui indique quand le rapport a été créé. Les rapports reflètent généralement une latence de 24 heures à partir du moment où une application a été ouverte.

L’axe Y du graphique est le nombre d’utilisateurs qui, pour la date que vous avez sélectionnée en pointant sur le graphique, sont considérés comme des utilisateurs actifs. Les utilisateurs qui ouvrent une application au moins une fois sont considérés comme des utilisateurs actifs.

L’axe X du graphique correspond à la plage de dates que vous avez sélectionnée pour le rapport.

Pointez sur le point (4) représentant l’utilisation d’une application à n’importe quelle date pour voir le nombre total d’utilisateurs actifs de cette application à cette date.

Pour sélectionner d’autres applications, en haut à droite, sélectionnez l’icône **Filtre** (5), sélectionnez ou tapez de nouveaux critères, puis **sélectionnez Appliquer**.

Le tableau en bas du rapport (6) affiche les utilisateurs actifs et les équipes par nom d’application.

   - **Le nom** de l’application est le nom complet de l’application utilisée dans Teams.
   - **Les utilisateurs actifs** sont le nombre d’utilisateurs qui ont ouvert l’application au moins une fois pendant la période spécifiée.
   - **Le type d’application** est une valeur statique de « Microsoft » ou « Tiers ».
   - **Les équipes actives** sont le nombre d’équipes qui ont ouvert l’application par au moins un membre de l’équipe et pendant les périodes spécifiées.
   - **Publisher** est le développeur de logiciels de l’application.
   - **La version** est la version logicielle de l’application, du développeur de l’application.

   > [!NOTE]
   > **Les utilisateurs actifs et les** **équipes actives** sont calculés uniquement pour les applications utilisées dans les canaux.

Pour ajouter ou supprimer des colonnes dans le tableau, en haut à droite, sélectionnez l’icône **Modifier les colonnes** (7), sous l’onglet **Modifier les colonnes** , sélectionnez de nouveaux critères, puis **sélectionnez Appliquer**.

Pour exporter le rapport vers un fichier CSV à des fins d’analyse hors connexion, en haut à droite, sélectionnez l’icône **Exporter vers Excel** (8), puis sous l’onglet **Téléchargements** sous **État**, **sélectionnez Télécharger**.

   :::image type="content" alt-text="Capture d’écran du volet Téléchargements." source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

Lorsque vous affichez le rapport dans Microsoft Excel, vous voyez également une `Id` colonne, qui représente l’ID d’application, généralement une chaîne alphanumérique. Si la valeur de l’objet `Id` est **\n**, cela signifie qu’un utilisateur a demandé la suppression de ses informations.

   :::image type="content" source="media/app-usage-report8.png" alt-text="Capture d’écran du rapport Excel téléchargé.":::

## <a name="related-articles"></a>Articles connexes

- [Analyses et rapports Teams](teams-reporting-reference.md)
