---
title: Rapport d’utilisation de Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kojika
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser le rapport utilisation Teams dans le centre d’administration de Microsoft Teams pour obtenir une vue d’ensemble de l’activité des équipes dans votre organisation.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3770d3e45e75808d8dc92e139c1886f6623df922
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825538"
---
# <a name="microsoft-teams-usage-report"></a>Rapport d’utilisation de Microsoft Teams

Le rapport de l’utilisation Teams dans le centre d’administration de Microsoft Teams vous offre une vue d’ensemble de l’activité de l’utilisation dans Teams, y compris le nombre d’utilisateurs et de canaux actifs, pour vous permettre de voir rapidement combien d’utilisateurs utilisent Teams pour communiquer et collaborer au sein de votre organisation. Vous pouvez afficher des informations d’utilisation concernant les équipes, y compris le nombre d’utilisateurs et de canaux actifs, d’invités et de messages dans chaque équipe.

## <a name="view-the-usage-report"></a>Afficher le rapport d’utilisation

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Analyse & rapports** > **d’utilisation**. Sous l’onglet **Afficher les rapports** , sous **Rapport**, sélectionnez **Utilisation de Teams**.
2. Dans **Plage de dates**, sélectionnez une plage puis cliquez sur **Exécuter le rapport**.

    ![Capture d’écran du rapport d’utilisation de Teams dans le Centre d’administration Teams avec des légendes.](../media/teams-reports-teams-usage-with-callouts1.png "Capture d’écran du rapport d’utilisation de Teams dans le Centre d’administration Teams avec des légendes")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport d’activité d’utilisation de Teams peut être consulté pour les tendances des 7 derniers jours, 30 ou 90 jours. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l’heure de l’activité. |
|**3**   |<ul><li>L’axe X représente la plage de dates sélectionnée pour ce rapport.</li> <li> L’axe Y indique le nombre d’éléments ou activités actif(ve)s.</li> </ul>Pointez sur le point représentant un élément ou une activité à une date donnée pour voir le nombre d’instances de cet élément ou activité à cette date.|
|**4**   |Vous pouvez filtrer ce qui est affiché dans le tableau en cliquant sur un élément dans la légende. Par exemple, cliquez sur  **Nombre total d’utilisateurs actifs**, **Teams & Canaux actifs**,  **Canaux actifs** ou **Messages** pour afficher uniquement les informations relatives à chacun d’eux. La modification de cette sélection ne modifie pas les informations du tableau lui-même. |
|**5**   |Le tableau présente une répartition de l’utilisation par équipe. <ul><li>**Le nom** de l’équipe est le nom complet de l’équipe. Vous pouvez cliquer sur le nom de l’équipe pour accéder à la page des paramètres de l’équipe dans le Centre d’administration Microsoft Teams. </li> <li>**Confidentialité** indique si l’équipe est une équipe privée ou publique.</li> <li>**Utilisateurs actifs** correspond au nombre d’utilisateurs actifs dans l’équipe pour la période spécifiée.</li><li>**Invités** correspond au nombre d’invités dans l’équipe pour la période spécifiée.</li> <li>**Les canaux actifs** sont le nombre de canaux qui ont au moins un utilisateur actif pendant la période spécifiée.</li> <li>**Post Messages** est le nombre de tous les messages post dans les canaux de la période spécifiée.</li> <li>**Les messages de réponse** sont le nombre de tous les messages de réponse dans les canaux au cours de la période spécifiée.</li> <li>**Les réunions organisées** sont le nombre de réunions planifiées et ad hoc organisées par un utilisateur pendant la période spécifiée. </li><li>**Les messages urgents** sont le nombre de tous les messages urgents dans la période spécifiée.</li><li>**Les réactions** sont le nombre de toutes les réactions aux messages dans la période spécifiée.</li><li>**Mentions** est le nombre de toutes les mentions utilisées dans les messages dans la période spécifiée.</li><li>**Les messages de canal** sont le nombre de messages uniques que les utilisateurs de l’équipe ont publiés dans une conversation d’équipe pendant la période spécifiée.</li> </li> </ul>Notez que si une équipe n’existe plus, le nom s’affiche sous la forme « - » dans la table. <br><br>Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau. |
|**6**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.|
|**7**   |Vous pouvez exporter le rapport vers un fichier CSV pour une analyse hors connexion. Cliquez sur **Exporter vers Excel**, puis sous l’onglet **Téléchargements** , cliquez sur **Télécharger** pour télécharger le rapport lorsqu’il est prêt.<br><br>![Capture d’écran de l’onglet Téléchargements montrant les rapports exportés à télécharger.](../media/teams-reports-export-to-csv.png)|
|**8** |Les points de données de série chronologique du graphique affichent différentes métriques d’utilisation agrégées au niveau du locataire|
|**9** |Les données tabulaires représentaient différentes métriques d’utilisation agrégées par équipe|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Rubriques connexes

- [Analyses et rapports Teams](teams-reporting-reference.md)
