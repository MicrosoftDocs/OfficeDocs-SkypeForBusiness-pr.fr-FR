---
title: Rapport d’activité des utilisateurs de Microsoft Teams
author: LanaChin
ms.author: v-lanac
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
description: Découvrez comment utiliser le rapport activité de l’utilisateur sur teams dans le centre d’administration de Microsoft teams pour voir comment les utilisateurs de votre organisation utilisent Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 907491aab660bacd0b619b385aaef3a9309cc121
ms.sourcegitcommit: 9d60f403b42d2fdef91cdfa3caf50179a49561df
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2020
ms.locfileid: "46536836"
---
# <a name="microsoft-teams-user-activity-report"></a>Rapport d’activité des utilisateurs de Microsoft Teams

Le rapport activité de l’utilisateur sur teams permet de visualiser les types d’activités exécutées par les utilisateurs de votre organisation dans Teams. Par exemple, l’un peut voir le nombre d’utilisateurs qui communiquent sur une base ad hoc par le biais de réunions non planifiées fréquemment appelées 1:1 et appels de groupe, réunions qu’un utilisateur d’équipe a organisé et rendez-vous à un utilisateur de teams. Nous partageons des détails sur les minutes de l’écran, de la vidéo et de l’audio, ainsi que des statistiques de communication de chat, comme le nombre d’utilisateurs qui répondent à des messages de canal, ainsi que le nombre d’utilisateurs qui se connectent à 1:1 ou aux messages de discussion de groupe.

## <a name="view-the-user-activity-report"></a>Afficher le rapport d’activité de l’utilisateur

Pour effectuer ces modifications, vous devez être un administrateur de service Teams. Pour plus d’informations sur l’accès aux rôles d’administrateur et aux autorisations, voir [utiliser les rôles d’administrateur d’équipes pour gérer teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) .

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **analyse &** rapports d'  >  **utilisation**des rapports. Dans l’onglet **afficher les rapports** , sous **rapport**, sélectionnez activité de l' **utilisateur sur teams**.
2. Dans **Plage de dates**, sélectionnez une plage puis cliquez sur **Exécuter le rapport**.

    ![Capture d’écran du rapport activité de l’utilisateur sur teams dans le centre d’administration teams avec légendes](../media/teams-reports-user-activity-with-callouts.png "Capture d’écran du rapport activité de l’utilisateur sur teams dans le centre d’administration teams avec légendes")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport activité de l’utilisateur sur teams peut être consulté pour les tendances au cours des 7, 30 ou 90 derniers jours. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports indiquent généralement une latence de 24 heures. |
|**3**   |<ul><li>L’axe X sur les graphiques représente la plage de dates sélectionnée pour ce rapport particulier. </li><li>L’axe Y indique le nombre d’utilisateurs participant à l’activité.</li></ul>Placez le pointeur de la souris sur le point représentant une activité à une date donnée pour afficher le nombre d’instances de cette activité à cette date donnée. |
|**4**   |Vous pouvez filtrer ce qui est affiché dans le tableau en cliquant sur un élément dans la légende. Par exemple, cliquez sur **appels 1:1**, **messages de canal**ou messages de **conversation** pour afficher uniquement les informations relatives à chacune d’elles. La modification de la sélection ne modifie pas les informations du tableau. |
|**5**   |Le tableau présente une répartition de l’utilisation par utilisateur.   <ul><li>**Nom d’utilisateur indique le** nom d’affichage de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour accéder à la page de paramètres de l’utilisateur dans le centre d’administration Microsoft Teams.</li><li>**Messages de canal** indique le nombre de messages uniques que l’utilisateur a publié dans une conversation d’équipe pendant la période spécifiée.</li><li>**Messages de réponse** indique le nombre de messages de réponse uniques que l’utilisateur a publiés dans un canal d’équipe pendant la période spécifiée.</li> <li>**Billets de messages** indique le nombre de messages de publication uniques que l’utilisateur a publiés dans un canal d’équipe pendant la période spécifiée.</li><li>**Messages de conversation** indique le nombre de messages uniques que l’utilisateur a publié dans une conversation privée pendant la période spécifiée.</li><li>**Messages urgents** indique le nombre de messages urgents que l’utilisateur a publié dans une conversation pendant la période spécifiée.</li><li>**Réunions totales** est le nombre total de réunions planifiées et ad hoc auxquelles un utilisateur a participé pendant la période spécifiée.</li><li>**Réunions organisées** indique le nombre de réunions planifiées et ad hoc qu’un utilisateur a organisées pendant la période spécifiée.</li><li>**Réunions organisées planifiées** indique le nombre de réunions planifiées organisées par un utilisateur pendant la période spécifiée.</li><li>**Réunions organisées** pour les réunions ad hoc indique le nombre de réunions ad hoc qu’un utilisateur a organisées pendant la période spécifiée.</li><li>**Réunions participé** est le nombre d’heures prévues et de réunions ad hoc auxquelles un utilisateur a participé pendant la période spécifiée.</li><li>**Réunions ayant participé** à la planification est le nombre de réunions planifiées auxquelles un utilisateur a participé pendant la période spécifiée.</li><li>Le nombre de réunions ad hoc auxquelles un utilisateur a participé pendant la période spécifiée a été **participé aux réunions** ad hoc.</li><li>**1:1 appels** est le nombre d’appels 1:1 auxquels l’utilisateur a participé pendant la période spécifiée.</li><li>**Temps audio** correspond au nombre total d’heures audio auxquelles l’utilisateur a participé pendant la période spécifiée.</li><li>La **durée vidéo** est le nombre total d’heures vidéo auxquelles l’utilisateur a participé pendant la période spécifiée.</li><li>Le **temps de partage d’écran** correspond à la durée totale du partage d’écran à laquelle l’utilisateur a participé pendant la période spécifiée.</li>  <li>**Dernière activité** correspond à la dernière date (UTC) à laquelle l’utilisateur a participé à une activité d’équipe.</li><li>Les **autres activités** effectuent le suivi lorsque l’utilisateur est considéré comme actif mais dont la valeur est zéro pour les messages de conversation, les appels 1:1, les messages de canal, les réunions totales et les réunions organisées. Par exemple, une action permet à un utilisateur d’ouvrir un message de canal, mais ne lui répond pas ou lorsqu’un utilisateur reçoit un message privé et le lit sans y répondre.</li> </ul>Notez que les **appels de groupe** ont été remplacés par des **réunions organisées** par le biais des **réunions ad hoc, et que**la somme de ces deux valeurs est égale à celles mesurées par les **appels de groupe**.
|**6**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**7**   |Vous pouvez exporter le rapport dans un fichier CSV pour une analyse hors connexion. Cliquez sur **Exporter vers Excel**, puis sous l’onglet **téléchargements** , cliquez sur **Télécharger** pour télécharger le rapport dès qu’il est prêt.<br><br>![Capture d’écran de l’onglet téléchargements montrant les rapports exportés à télécharger](../media/teams-reports-export-to-csv.png) <br>Lorsque vous affichez le rapport dans Excel, vous verrez également une colonne **ID** , qui représente l’ID d’équipe. Un ID d’équipe est généralement une chaîne alphanumérique. Si la colonne **ID** indique **\n**, cela signifie qu’un utilisateur a demandé les informations à supprimer. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)
