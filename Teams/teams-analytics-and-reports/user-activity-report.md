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
description: Découvrez comment utiliser le rapport d’activité utilisateur équipes dans le centre d’administration Microsoft Teams pour savoir comment les utilisateurs de votre organisation utilisent équipes.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5ad6021f03b200e1f3216238a81cc3b691171fd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225031"
---
# <a name="microsoft-teams-user-activity-report"></a>Rapport d’activité des utilisateurs de Microsoft Teams

Le rapport d’activité utilisateur équipes vous donne un aperçu dans les types d’activités en équipes pour effectuer les utilisateurs de votre organisation. Par exemple, vous pouvez voir combien d’utilisateurs communiquer via des appels de 1:1, combien d’utilisateurs communiquer par le biais de messages de canal et le nombre d’utilisateurs prendre part à des messages de conversation privée.

![Capture d’écran de l’état d’activité utilisateur équipes dans le centre d’administration Microsoft équipes] (../media/teams-reports-user-activity.png "Capture d’écran de l’état d’activité utilisateur équipes dans le centre d’administration Microsoft équipes")

## <a name="view-the-report"></a>Afficher le rapport

1. Accédez au centre d’administration Microsoft Teams, dans la navigation de gauche, cliquez sur **rapports de & Analytique**, puis, sous **état**, sélectionnez **l’activité utilisateur équipes**. 
2. Dans **Plage de dates**, sélectionnez une plage puis cliquez sur **Exécuter le rapport**. 

## <a name="interpret-the-report"></a>Interpréter le rapport

![Capture d’écran de l’état d’activité utilisateur équipes dans le centre d’administration de Microsoft équipes avec légendes numérotées] (../media/teams-reports-user-activity-with-callouts.png "Capture d’écran de l’état d’activité utilisateur équipes dans le centre d’administration de Microsoft équipes avec légendes numérotées")

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport d’activité utilisateur équipes peut être affiché pour les tendances sur la dernière 7 jours ou 28 jours. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l’heure de l’activité. |
|**3**   |<ul><li>L’axe des X dans les graphiques sont la plage de dates sélectionnée pour le rapport spécifique. </li><li>L’axe des Y sont le nombre d’utilisateurs participant à l’activité.</li></ul>Pointez sur le bouton représentant une activité à une date donnée pour afficher le nombre d’instances de cette activité à cette date donnée. |
|**4**   |Vous pouvez filtrer ce qui est affiché dans le tableau en cliquant sur un élément dans la légende. Par exemple, cliquez sur **appels 1:1**, les **messages de canal**ou **les messages de conversation** pour afficher uniquement les informations relatives à chacun d’eux. Modification de la sélection ne change pas les informations contenues dans le tableau. |
|**5**   |Le tableau donne une répartition de l’utilisation par l’utilisateur.   <ul><li>**Nom complet** est le nom complet de l’utilisateur. Vous pouvez cliquer sur le nom complet pour accéder à la page Paramètres de l’utilisateur dans le centre d’administration Microsoft Teams.</li><li>**appels de 1:1** est le nombre d’appels de 1:1 ayant participé à l’utilisateur pendant la période spécifiée.</li><li>**Messages de canal** est le nombre de messages uniques que l’utilisateur est publié dans une conversation de l’équipe au cours de la période spécifiée.</li> <li>**Messages de conversation** est le nombre de messages uniques que l’utilisateur validées privé conversation au cours de la période spécifiée.</li>  <li>**Dernière activité** est la dernière date (UTC) que l’utilisateur a participé à une activité équipes.</li> </ul>Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau.
|**6**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**7**   |Sélectionnez **˙˙˙**, puis **Imprimer le graphique** pour imprimer le graphique. |

## <a name="related-topics"></a>Voir aussi
- [Analyses et rapports Teams](teams-reporting-reference.md)
- [Rapport d’utilisation Teams](teams-usage-report.md)
- [Rapport d’utilisation Teams sur des périphériques](device-usage-report.md)