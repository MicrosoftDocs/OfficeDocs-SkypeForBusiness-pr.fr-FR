---
title: Rapport d’activité des utilisateurs de Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/22/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Découvrez comment utiliser le rapport activité de l’utilisateur sur teams dans le centre d’administration de Microsoft teams pour voir comment les utilisateurs de votre organisation utilisent Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c217ae2d1344c8998e9dd8035f8c96d48a110a6d
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433007"
---
# <a name="microsoft-teams-user-activity-report"></a>Rapport d’activité des utilisateurs de Microsoft Teams

Le rapport activité de l’utilisateur sur teams vous permet de mieux comprendre les types d’activités que les utilisateurs de votre organisation effectuent dans Teams. Par exemple, vous pouvez voir le nombre d’utilisateurs qui communiquent par le biais d’appels 1:1, le nombre d’utilisateurs qui communiquent par le biais de messages de canal, et le nombre d’utilisateurs qui entreprennent des messages de conversation privée.

![Capture d’écran du rapport activité de l’utilisateur sur teams] (../media/teams-reports-user-activity.png "Capture d’écran du rapport activité de l’utilisateur sur teams dans le centre d’administration Microsoft teams")

## <a name="view-the-report"></a>Afficher le rapport

1. Accédez au centre d’administration de Microsoft Teams, dans le volet de navigation de gauche, cliquez sur **analyse & rapports**, puis sous **rapport**, sélectionnez activité de l' **utilisateur**sur Teams. 
2. Dans **Plage de dates**, sélectionnez une plage puis cliquez sur **Exécuter le rapport**. 

## <a name="interpret-the-report"></a>Interpréter le rapport

![Capture d’écran du rapport activité de l’utilisateur sur Microsoft teams avec des légendes numérotées] (../media/teams-reports-user-activity-with-callouts.png "Capture d’écran du rapport activité de l’utilisateur sur teams dans le centre d’administration Microsoft teams avec des légendes numérotées")

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport activité de l’utilisateur sur teams peut être consulté pour les tendances au cours des 7, ou 28 derniers jours. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l’heure de l’activité. |
|**3**   |<ul><li>L’axe X sur les graphiques représente la plage de dates sélectionnée pour ce rapport particulier. </li><li>L’axe Y indique le nombre d’utilisateurs participant à l’activité.</li></ul>Placez le pointeur de la souris sur le point représentant une activité à une date donnée pour afficher le nombre d’instances de cette activité à cette date donnée. |
|**4**   |Vous pouvez filtrer ce qui est affiché dans le tableau en cliquant sur un élément dans la légende. Par exemple, cliquez sur **appels 1:1**, **messages de canal**ou messages de **conversation** pour afficher uniquement les informations relatives à chacune d’elles. La modification de la sélection ne modifie pas les informations du tableau. |
|**5**   |Le tableau présente une répartition de l’utilisation par utilisateur.   <ul><li>**Nom complet** est le nom d’affichage de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour accéder à la page de paramètres de l’utilisateur dans le centre d’administration Microsoft Teams.</li><li>**1:1 appels** est le nombre d’appels 1:1 auxquels l’utilisateur a participé pendant la période spécifiée.</li><li>**Messages de canal** indique le nombre de messages uniques que l’utilisateur a publié dans une conversation d’équipe pendant la période spécifiée.</li> <li>**Messages de conversation** indique le nombre de messages uniques que l’utilisateur a publié dans une conversation privée pendant la période spécifiée.</li>  <li>**Dernière activité** correspond à la dernière date (UTC) à laquelle l’utilisateur a participé à une activité d’équipe.</li> </ul>Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.
|**6**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**7**   |Vous pouvez exporter le rapport dans un fichier CSV pour une analyse hors connexion. Cliquez sur **Exporter vers Excel**, puis sous l’onglet **téléchargements** , cliquez sur **Télécharger** pour télécharger le rapport dès qu’il est prêt.<br>![Capture d’écran de l’onglet téléchargements indiquant les rapports exportés à télécharger](../media/teams-reports-export-to-csv.png)||

## <a name="related-topics"></a>Voir aussi
- [Analyses et rapports Teams](teams-reporting-reference.md)
- [Rapport d’utilisation Teams](teams-usage-report.md)
- [Rapport d’utilisation Teams sur des périphériques](device-usage-report.md)