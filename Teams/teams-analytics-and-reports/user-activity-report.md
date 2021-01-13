---
title: Rapport d’activité des utilisateurs de Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser le rapport Activité de l’utilisateur sur Teams dans le Centre d’administration Microsoft Teams pour voir comment les utilisateurs de votre organisation utilisent Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 85d907e527f8b957abf1a5f3b8b9f0d8c5f44443
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809194"
---
# <a name="microsoft-teams-user-activity-report"></a>Rapport d’activité des utilisateurs de Microsoft Teams

Le rapport Activité de l’utilisateur sur Teams donne des informations sur les types d’activités que les utilisateurs de votre organisation effectuent dans Teams. Par exemple, vous pouvez voir le nombre d’utilisateurs qui communiquent ad hoc par le biais de réunions non prévues généralement appelées appels à deux ou de groupe, réunions organisées par un utilisateur de Teams et réunions à qui l’utilisateur a participé. Nous partageons des détails sur les minutes d’écran, vidéo et audio, et les statistiques de communication par conversation, telles que le nombre d’utilisateurs qui répondent à des messages de canal et y publient, et ceux qui participent à des messages de conversation en tête-à-tête ou de groupe.

## <a name="view-the-user-activity-report"></a>Afficher le rapport d’activité de l’utilisateur

Vous devez être un administrateur du service Teams pour apporter ces modifications. Pour en [savoir plus sur l’obtention](https://docs.microsoft.com/microsoftteams/using-admin-roles) de rôles et d’autorisations d’administrateur, voir Utiliser les rôles d’administrateur Teams pour gérer Teams.

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Analyse pour & rapports**  >  **d’utilisation.** Sous **l’onglet Afficher les rapports,** sous **Rapport,** sélectionnez **Activité de l’utilisateur sur Teams.**
2. Dans **Plage de dates**, sélectionnez une plage puis cliquez sur **Exécuter le rapport**.

    ![Rapport d’activité de l’utilisateur sur Teams dans le Centre d’administration Teams avec des callouts](../media/teams-reports-user-activity-with-callouts.png "Rapport d’activité de l’utilisateur sur Teams dans le Centre d’administration Teams avec des callouts")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport Activité de l’utilisateur sur Teams peut être vu pour les tendances au cours des 7, 30 ou 90 derniers jours. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 heures par rapport à l’heure de l’activité. |
|**3**   |<ul><li>L’axe X sur les graphiques est la plage de dates sélectionnée pour le rapport spécifique. </li><li>L’axe Y est le nombre d’utilisateurs participant à l’activité.</li></ul>Pointez sur le point représentant une activité à une date donnée pour voir le nombre d’instances de cette activité à cette date donnée. |
|**4**   |Vous pouvez filtrer ce qui est affiché dans le tableau en cliquant sur un élément dans la légende. Par exemple, cliquez sur **Appels à deux,** **Messages** de canal ou Messages de **conversation** pour voir uniquement les informations relatives à chacun d’eux. La modification de la sélection ne modifie pas les informations du tableau. |
|**5**   |Le tableau offre une répartition de l’utilisation par utilisateur.   <ul><li>**Nom d’utilisateur** est le nom d’affichage de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour afficher la page de paramètres de l’utilisateur dans le Centre d’administration Microsoft Teams.</li><li>**Les messages de** canal sont le nombre de messages uniques que l’utilisateur a publié dans une conversation d’équipe pendant la période spécifiée.</li><li>**Les messages de** réponse sont le nombre de messages de réponse uniques que l’utilisateur a publié dans un canal d’équipe pendant la période spécifiée.</li> <li>**Publier des messages** est le nombre de messages de publication uniques que l’utilisateur a publié dans un canal d’équipe pendant la période spécifiée.</li><li>**Les messages de** conversation sont le nombre de messages uniques que l’utilisateur a publié dans une conversation privée pendant la période spécifiée.</li><li>**Les messages urgents** sont le nombre de messages urgents que l’utilisateur a publié dans une conversation pendant la période spécifiée.</li><li>**Le nombre** total de réunions est le nombre total de réunions programmées et ad hoc à participations de l’utilisateur au cours de la période spécifiée.</li><li>**Les réunions organisées** sont le nombre de réunions programmées et ad hoc organisées par l’utilisateur pendant la période spécifiée.</li><li>**Les réunions organisées sont le** nombre de réunions organisées par l’utilisateur pendant la période spécifiée.</li><li>**Les réunions adhoc** organisées sont le nombre de réunions ad hoc organisées par un utilisateur pendant la période spécifiée.</li><li>**Les réunions ont participé** au nombre de réunions programmées et ad hoc à participation de l’utilisateur pendant la période spécifiée.</li><li>**Les réunions dont la participation a été programmée** sont le nombre de réunions qu’un utilisateur a participé à la période spécifiée.</li><li>**Les réunions ont participé adhoc** est le nombre de réunions ad hoc à qui un utilisateur a participé pendant la période spécifiée.</li><li>**1:1 appels** est le nombre d’appels 1:1 à pris en compte par l’utilisateur pendant la période spécifiée.</li><li>**Le temps audio** est la durée audio totale à qui l’utilisateur a participé pendant la période spécifiée.</li><li>**La durée vidéo** est la durée vidéo totale à qui l’utilisateur a participé pendant la période spécifiée.</li><li>**La durée de partage d’écran** est la durée totale du partage d’écran à quel moment l’utilisateur a participé à la période spécifiée.</li>  <li>**La dernière** activité est la dernière date (UTC) à laquelle l’utilisateur a participé à une activité Teams.</li><li>**Autres** suivis d’activité lorsque l’utilisateur est considéré comme actif mais a une valeur de zéro pour les messages de conversation, les appels 1:1, les messages de canal, le nombre total de réunions et de réunions organisées. Par exemple, il peut s’agir d’un utilisateur qui ouvre une publication de message de canal sans y répondre, ou qui reçoit un message privé et le lit sans y répondre.</li> </ul>Notez  que les appels de groupe ont été remplacés par Réunions adhoc et Réunions ont participé **adhoc,** dans lequel la somme de ces deux **valeurs** est égale à ce qui a été mesuré par les appels de **groupe.**
|**6**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**7**   |Vous pouvez exporter le rapport dans un fichier CSV à des fin d’analyse en mode hors connexion. Cliquez **sur Exporter vers Excel,** puis sous  l’onglet **Téléchargements,** cliquez sur Télécharger pour télécharger le rapport lorsqu’il est prêt.<br><br>![Capture d’écran de l’onglet Téléchargements affichant les rapports exportés à télécharger](../media/teams-reports-export-to-csv.png) <br>Lorsque vous affichez le rapport dans Excel, une colonne ID représentant **l’ID** d’équipe s’affiche également. Un ID d’équipe est généralement une chaîne alphanumérique. Si la **colonne ID** indique **\n,** cela signifie qu’un utilisateur a demandé la suppression de ses informations. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)
