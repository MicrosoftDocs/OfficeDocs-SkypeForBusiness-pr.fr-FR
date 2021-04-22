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
description: Découvrez comment utiliser le rapport Activité de l'utilisateur sur Teams dans le Centre d'administration Microsoft Teams pour voir comment les utilisateurs de votre organisation utilisent Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1a528d92a633e42623772f0f43a85658e4e8aecc
ms.sourcegitcommit: 4cf89ce07184083c8c28892a2acbb85d797c21c4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51938253"
---
# <a name="microsoft-teams-user-activity-report"></a>Rapport d’activité des utilisateurs de Microsoft Teams

Le rapport Activité de l'utilisateur sur Teams donne des informations sur les types d'activités que les utilisateurs de votre organisation font dans Teams. Vous pouvez voir le nombre d'utilisateurs qui communiquent de manière non planifiée par le biais de réunions non planifiées (appels à deux ou de groupe). Découvrez combien de réunions un utilisateur de Teams a organisées et les réunions qu'un utilisateur de Teams a participé. Consultez des détails sur les minutes à l'écran, la vidéo et l'audio, et les statistiques de communication par conversation, telles que le nombre d'utilisateurs qui répondent à des messages de canal et y publient, et combien d'utilisateurs participent à des messages de conversation à deux ou de groupe.

> [!NOTE]
> La possibilité de planifier un rapport d'activité de l'utilisateur n'est pas disponible pour le moment.

## <a name="view-the-user-activity-report"></a>Afficher le rapport d'activité de l'utilisateur

Vous devez être un administrateur du service Teams pour apporter ces modifications. Voir [Gérer Teams grâce aux rôles d’administrateur Teams](../using-admin-roles.md) afin d’en savoir plus sur l’obtention de rôles et d’autorisations d’administrateur.

1. Dans le panneau de navigation gauche du Centre d'administration Microsoft Teams, sélectionnez **Analyse & rapports**  >  **d'utilisation des rapports.** Sous **l'onglet Afficher les rapports,** sous **Rapport,** sélectionnez **Activité de l'utilisateur sur Teams.**
2. Sous **Plage de dates,** sélectionnez une plage, puis **sélectionnez Exécuter le rapport.**

    ![Rapport d'activité de l'utilisateur sur Teams dans le Centre d'administration Teams avec des appels](../media/teams-reports-user-activity-with-callouts.png "Rapport d'activité de l'utilisateur sur Teams dans le Centre d'administration Teams avec des appels")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport Activité de l'utilisateur sur Teams peut être vu pour les tendances au cours des 7, 30 ou 90 derniers jours. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 heures par rapport à l'heure de l'activité. |
|**3**   |Les points de données de série de temps dans le graphique montrent différentes mesures d'utilisation agrégées au client. |
|**4**   |Les données tabulaires représentent différentes mesures d'utilisation agrégées par utilisateur. |
|**5**   |<ul><li>L’axe X représente la plage de dates sélectionnée pour ce rapport.</li> <li> L’axe Y indique le nombre d’éléments ou activités actif(ve)s.</li> </ul>Pointez sur le point représentant un élément ou une activité à une date donnée pour voir le nombre d’instances de cet élément ou activité à cette date.|
|**6**   | Chacune des mesures représentées dans le graphique au niveau du client. Filtrez ce que vous voyez sur le graphique en sélectionnant un élément dans la légende. Sélectionnez **Messages de canal,** **Messages de réponse,**  **Messages de** conversation ou Réunions organisées pour voir les informations **liées** à chacun d'eux. La modification de cette sélection ne modifie pas les informations du tableau lui-même. |
|**7**   |Le tableau vous offre une répartition de l'utilisation par utilisateur.   <ul><li>**Le nom d'affichage** est le nom d'affichage de l'utilisateur. Sélectionnez le nom complet pour afficher la page des détails de l'utilisateur dans le Centre d'administration Microsoft Teams.</li><li>**Les messages de** canal sont le nombre de messages uniques que l'utilisateur a publié dans un canal d'équipe pendant la période spécifiée.</li><li>**Les messages de** réponse sont le nombre de messages de réponse uniques que l'utilisateur a publié dans un canal d'équipe pendant la période spécifiée.</li> <li>**Publier des messages** est le nombre de messages de publication uniques que l'utilisateur a publié dans un canal d'équipe pendant la période spécifiée.</li><li>**Les messages de** conversation sont le nombre de messages uniques que l'utilisateur a publié dans une conversation privée pendant la période spécifiée.</li><li>**Les messages urgents** sont le nombre de messages urgents que l'utilisateur a publié dans une conversation pendant la période spécifiée.</li><li>Le nombre total de réunions organisées est la somme des réunions planifiées une seule fois, périodiques, non planifiées et <em>non</em> **classées** qu'un utilisateur a organisées pendant la période spécifiée.</li><li>**Les réunions organisées** en une fois sont le nombre de réunions prévues de manière précise qu'un utilisateur a organisées pendant la période spécifiée.</li><li>**Les réunions organisées périodiquement organisées** sont le nombre de réunions périodiques organisées par un utilisateur pendant la période spécifiée.</li><li>**Les réunions adhoc** organisées sont le nombre de réunions non planifiées organisées par un utilisateur pendant la période spécifiée.</li><li>**Le nombre total** de réunions a participé à la somme des réunions planifiées, récurrentes, non planifiées et <em>non</em> classées qu'un utilisateur a participé pendant la période spécifiée.</li><li>**Les réunions prévues** une fois sont le nombre de réunions prévues de la même heure à participer à l'utilisateur pendant la période spécifiée.</li><li>**Les réunions dont la participation a été programmée** sont le nombre de réunions périodiques à qui l'utilisateur a participé pendant la période spécifiée.</li><li>**Les réunions ont participé adhoc** est le nombre de réunions non planifiées à qui un utilisateur a participé pendant la période spécifiée.</li><li>**Les appels 1:1** sont le nombre d'appels 1:1 que l'utilisateur a participé à la période spécifiée.</li><li>**Le temps** audio est la durée audio totale (minutes) à qui l'utilisateur a participé pendant la période spécifiée.</li><li>**La durée vidéo** est la durée vidéo totale (minutes) à qui l'utilisateur a participé pendant la période spécifiée.</li><li>**La durée de partage d'écran** est la durée totale du partage d'écran (minutes) à à quel moment l'utilisateur a participé à la période spécifiée.</li>  <li>**La dernière** activité est la dernière date (UTC) à laquelle l'utilisateur a participé à une activité Teams.</li><li>**Autres** suivis d'activité lorsque l'utilisateur est considéré comme actif mais a une valeur de zéro pour les messages de conversation, les appels 1:1, les messages de canal, le nombre total de réunions et de réunions organisées. Par exemple, il peut s'agir d'un utilisateur qui ouvre une publication de message de canal sans y répondre, ou qui reçoit un message privé et le lit sans y répondre.</li> <li>**Les réunions non classées** sont les réunions qui ne peuvent pas être classées comme étant planifiées, récurrentes ou non planifiées. Leur nombre est court et ne peut principalement pas être identifié en raison d'informations de télémétrie falsifiées</li> </ul>**Les appels** de groupe ont été **remplacés par les réunions adhoc** et **meetings participated adhoc.** La somme de ces deux valeurs est égale à ce qui a été mesuré par les **appels de groupe.**
|**8**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**9**   |Exportez le rapport dans un fichier CSV à des fin d'analyse en mode hors connexion. Sélectionnez **Exporter vers Excel,** puis sous  l'onglet **Téléchargements,** sélectionnez Télécharger pour télécharger le rapport lorsqu'il est prêt.<br><br>![Capture d'écran de l'onglet Téléchargements affichant les rapports exportés à télécharger](../media/teams-reports-export-to-csv.png) <br>Lorsque vous affichez le rapport dans Excel, une colonne ID représentant **l'ID** d'utilisateur s'affiche également. Un ID utilisateur est généralement une chaîne alphanumérique. ||

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Rendre les données spécifiques de l'utilisateur anonymes

Pour anonymisation des données du rapport d'activité de l'utilisateur sur Teams, vous devez être administrateur général. Cela a pour effet de masquer les informations identifiables telles que le nom d'affichage, le courrier électronique et l'ID AAD dans le rapport et leur exportation.

1. Dans le Centre d'administration Microsoft 365, sélectionnez **Paramètres** de l'organisation, puis sous l'onglet \>  **Services,** sélectionnez **Rapports.**
    
2. Sélectionnez **Rapports,** puis choisissez **d'afficher les identificateurs anonymes.** Ce paramètre est appliqué aux rapports d'utilisation dans le Centre d'administration Microsoft 365 et le Centre d'administration Teams.
  
3. Sélectionnez **Enregistrer les modifications.**

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)
