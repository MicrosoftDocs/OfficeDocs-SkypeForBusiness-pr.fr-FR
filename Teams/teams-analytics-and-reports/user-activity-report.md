---
title: Rapport d’activité des utilisateurs de Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser le rapport d’activité des utilisateurs Teams dans le Centre d’administration Microsoft Teams pour voir comment les utilisateurs de votre organisation utilisent Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 78f1b58dbcddb66e2d8a045d9510a3609bfe4a05
ms.sourcegitcommit: b2692b3f6c60d8df5ba0677c68ff9c90a75a0d72
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68033842"
---
# <a name="microsoft-teams-user-activity-report"></a>Rapport d’activité des utilisateurs de Microsoft Teams

Le rapport d’activité des utilisateurs Teams donne un aperçu des types d’activités que les utilisateurs de votre organisation effectuent dans Teams. Vous pouvez voir combien d’utilisateurs communiquent de façon non planifiée via des réunions non planifiées (appels de groupe et 1:1). Découvrez le nombre de réunions qu’un utilisateur Teams a organisées et les réunions aux quelles un utilisateur Teams a participé. Consultez des détails sur les minutes d’écran, vidéo et audio, ainsi que les statistiques de communication de conversation, telles que le nombre d’utilisateurs qui répondent aux messages de canal et les messages de canal, et le nombre d’utilisateurs qui s’engagent dans des messages de conversation 1:1 ou de groupe.

> [!NOTE]
> La possibilité de planifier un rapport d’activité utilisateur n’est pas disponible pour l’instant.

## <a name="view-the-user-activity-report"></a>Afficher le rapport d’activité de l’utilisateur

Vous devez être un administrateur du service Teams pour apporter ces modifications. Voir [Gérer Teams grâce aux rôles d’administrateur Teams](../using-admin-roles.md) afin d’en savoir plus sur l’obtention de rôles et d’autorisations d’administrateur.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, sélectionnez **Analytics & rapports** > **d’utilisation**. Sous l’onglet **Afficher les rapports** , sous **Rapport**, sélectionnez **l’activité de l’utilisateur Teams**.
2. Sous **Plage de dates**, sélectionnez une plage, puis **sélectionnez Exécuter le rapport**.

    ![Capture d’écran du rapport d’activité des utilisateurs Teams dans le Centre d’administration Teams avec des légendes.](../media/teams-reports-user-activity-with-callouts.png "Capture d’écran du rapport d’activité des utilisateurs Teams dans le Centre d’administration Teams avec légendes")

## <a name="interpret-the-report"></a>Interpréter le rapport

| Légende |Description  |
|--------|-------------|
|**1**   |Le rapport d’activité des utilisateurs Teams peut être consulté pour les tendances des 7 derniers jours, 30 ou 90 jours. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 heures à partir du moment de l’activité. |
|**3**   |Les points de données de série chronologique du graphique affichent différentes métriques d’utilisation agrégées au niveau du locataire. |
|**4**   |Les données tabulaires représentaient différentes métriques d’utilisation agrégées par utilisateur. |
|**5**   |<ul><li>L’axe X représente la plage de dates sélectionnée pour ce rapport.</li> <li> L’axe Y indique le nombre d’éléments ou activités actif(ve)s.</li> </ul>Pointez sur le point représentant un élément ou une activité à une date donnée pour voir le nombre d’instances de cet élément ou activité à cette date.|
|**6**   | Chacune des métriques représentées dans le graphique au niveau du locataire. Filtrez ce que vous voyez sur le graphique en sélectionnant un élément dans la légende. Sélectionnez **Les messages de canal**, **les messages de réponse**, les  **messages de conversation** ou **les réunions organisées** pour afficher les informations relatives à chacune d’elles. La modification de cette sélection ne modifie pas les informations du tableau lui-même. |
|**7**   |Le tableau vous donne une répartition de l’utilisation par utilisateur.   <ul><li>**Le nom d’utilisateur** est l’adresse e-mail de l’utilisateur. Consultez [la section suivante](#make-the-user-specific-data-anonymous) pour obtenir des conseils sur la façon de l’anonymiser ou sélectionnez le nom d’utilisateur pour accéder à la page de détails de l’utilisateur.</li><li>**Le nom du locataire** est le nom d’un locataire interne ou externe auquel appartient un utilisateur. <br> Si un utilisateur appartient à un locataire externe, les métriques de données correspondantes (telles que les messages postaux et les messages de réponse) sont calculées en fonction de leurs interactions dans les canaux partagés du locataire de l’administrateur. Les interactions effectuées par l’utilisateur dans son propre locataire (en dehors des canaux partagés du locataire donné) ne sont pas prises en compte pour le rapport d’utilisation administrateur du locataire donné.  </li><li>**Les messages de canal** sont le nombre de messages uniques que l’utilisateur a publiés dans un canal d’équipe pendant la période spécifiée.</li><li>**Les messages de réponse** correspondent au nombre de messages de réponse uniques que l’utilisateur a publiés dans un canal d’équipe pendant la période spécifiée.</li> <li>**Les messages** post sont le nombre de messages post uniques que l’utilisateur a publiés dans un canal d’équipe pendant la période spécifiée.</li><li>**Les messages de conversation** correspondent au nombre de messages uniques que l’utilisateur a publiés dans une conversation privée pendant la période spécifiée.</li><li>**Les messages urgents** sont le nombre de messages urgents que l’utilisateur a publiés dans une conversation pendant la période spécifiée.</li><li>**Le nombre total de réunions organisées** correspond à la somme des réunions planifiées, périodiques, non planifiées et <em>non classées</em> qu’un utilisateur a organisées pendant la période spécifiée.</li><li>**Les réunions organisées une seule fois** sont le nombre de réunions planifiées à une seule fois qu’un utilisateur a organisées pendant la période spécifiée.</li><li>**Les réunions planifiées périodiques** sont le nombre de réunions périodiques organisées par un utilisateur pendant la période spécifiée.</li><li>**L’adhoc des réunions organisées** correspond au nombre de réunions non planifiées qu’un utilisateur a organisées pendant la période spécifiée.</li><li>**Le nombre total de réunions participantes** correspond à la somme des réunions planifiées, périodiques, non planifiées et <em>non classées</em> à laquelle un utilisateur a participé pendant la période spécifiée.</li><li>**Les réunions aux réunions planifiées sont** le nombre de réunions planifiées uniques aux cours de la période spécifiée par un utilisateur.</li><li>Le nombre de **réunions périodiques planifiées aux réunions** aux laquelle un utilisateur a participé au cours de la période spécifiée est le nombre de réunions périodiques aux cours de laquelle un utilisateur a participé.</li><li>Le nombre de **réunions aux laquelle un utilisateur a participé** au cours de la période spécifiée est le nombre de réunions non planifiées aux cours des réunions.</li><li>**Les appels 1:1** sont le nombre d’appels 1:1 auxquels l’utilisateur a participé pendant la période spécifiée.</li><li>**La durée audio** est la durée audio totale (minutes) à laquelle l’utilisateur a participé pendant la période spécifiée.</li><li>**Le temps vidéo** est le temps vidéo total (minutes) auquel l’utilisateur a participé pendant la période spécifiée.</li><li>**Le temps de partage** d’écran est le temps total de partage d’écran (minutes) auquel l’utilisateur a participé pendant la période spécifiée.</li>  <li>**La dernière activité** est la dernière date (UTC) à laquelle l’utilisateur a participé à une activité Teams.</li><li>**Les autres activités** s’assurent du suivi lorsque l’utilisateur est considéré comme actif, mais qu’il a la valeur zéro pour les messages de conversation, les appels 1:1, les messages de canal, le nombre total de réunions et les réunions organisées. Des exemples d’actions sont lorsqu’un utilisateur ouvre un message de canal, mais qu’il ne lui répond pas ou lorsqu’un utilisateur reçoit un message privé et le lit, mais qu’il ne répond pas à celui-ci.</li> <li>**Les réunions non classées** sont celles qui ne peuvent pas être identifiées comme planifiées, périodiques ou non planifiées. Ils sont peu nombreux et ne peuvent souvent pas être identifiés en raison d’informations de télémétrie imparfaites.</li> </ul>**Les appels de groupe** ont été **remplacés par les réunions organisées adhoc** et **les réunions ont participé à l’adhoc**. La somme de ces deux valeurs est égale à ce qui a été mesuré par **les appels de groupe**.
|**8**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**9**   |Exportez le rapport vers un fichier CSV pour une analyse hors connexion. Sélectionnez **Exporter vers Excel**, puis l’onglet **Téléchargements** , puis **Télécharger** pour télécharger le rapport lorsqu’il est prêt.<br><br>![Capture d’écran de l’onglet Téléchargements montrant les rapports exportés à télécharger.](../media/teams-reports-export-to-csv.png) <br>Lorsque vous affichez le rapport dans Excel, vous voyez également une colonne **d’ID** , qui représente l’ID utilisateur. Un ID d’utilisateur est généralement une chaîne alphanumérique. |

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Rendre les données spécifiques à l’utilisateur anonymes

Pour rendre les données du rapport d’activité utilisateur Teams anonymes, vous devez être administrateur général. Cela masque les informations d’identification (à l’aide de hachages MD5) telles que le nom d’affichage, l’e-mail et l’ID AAD dans le rapport et leur exportation.

1. Dans Centre d'administration Microsoft 365, accédez aux **paramètres de l’organisation** **Paramètres** \> et, sous l’onglet **Services**, choisissez **Rapports**.
    
2. Sélectionnez **Rapports**, puis choisissez **d’afficher les noms d’utilisateur, de groupe et de site masqués dans tous les rapports**. Ce paramètre est appliqué aux rapports d’utilisation dans Centre d'administration Microsoft 365 et au Centre d’administration Teams.
  
3. Sélectionnez **Enregistrer les modifications**.

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)
