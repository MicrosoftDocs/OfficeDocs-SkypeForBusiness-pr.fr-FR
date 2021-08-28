---
title: Rapport d’utilisation de Microsoft Teams
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: e2913093cfa45bb7e242dbe5452657cd74f9e187
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627246"
---
# <a name="microsoft-teams-usage-report"></a>Rapport d’utilisation de Microsoft Teams

Le rapport de l’utilisation Teams dans le centre d’administration de Microsoft Teams vous offre une vue d’ensemble de l’activité de l’utilisation dans Teams, y compris le nombre d’utilisateurs et de canaux actifs, pour vous permettre de voir rapidement combien d’utilisateurs utilisent Teams pour communiquer et collaborer au sein de votre organisation. Vous pouvez afficher des informations d’utilisation concernant les équipes, y compris le nombre d’utilisateurs et de canaux actifs, d’invités et de messages dans chaque équipe.

## <a name="view-the-usage-report"></a>Afficher le rapport d’utilisation

1. Dans le panneau de navigation gauche du Centre Microsoft Teams’administration, cliquez sur **Analyse & rapports**  >  **d’utilisation.** Sous **l’onglet Afficher les** rapports, sous **Rapport,** sélectionnez **Teams’utilisation.**
2. Dans **Plage de dates**, sélectionnez une plage puis cliquez sur **Exécuter le rapport**.

    ![Capture d’écran du Teams d’utilisation de l’Teams dans le Centre d’administration Teams des appels](../media/teams-reports-teams-usage-with-callouts1.png "Capture d’écran du Teams d’utilisation de l’Teams dans le Centre d’administration Teams des appels")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le Teams de l’activité sur l’utilisation peut être pris en compte pour les tendances des 7, 30 ou 90 derniers jours. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l’heure de l’activité. |
|**3**   |<ul><li>L’axe X représente la plage de dates sélectionnée pour ce rapport.</li> <li> L’axe Y indique le nombre d’éléments ou activités actif(ve)s.</li> </ul>Pointez sur le point représentant un élément ou une activité à une date donnée pour voir le nombre d’instances de cet élément ou activité à cette date.|
|**4**   |Vous pouvez filtrer ce qui est affiché dans le tableau en cliquant sur un élément dans la légende. Par exemple, cliquez sur **Nombre total** d’utilisateurs **actifs,** Teams & canaux **actifs,** canaux actifs ou **messages** pour voir uniquement les informations liées à chacun d’eux. La modification de cette sélection ne modifie pas les informations du tableau lui-même. |
|**5**   |Le tableau présente une répartition de l’utilisation par équipe. <ul><li>**Le nom d’équipe** est le nom complet de l’équipe. Vous pouvez cliquer sur le nom de l’équipe pour aller à la page des paramètres de l’équipe dans le Microsoft Teams d’administration. </li> <li>**Confidentialité** indique si l’équipe est une équipe privée ou publique.</li> <li>**Utilisateurs actifs** correspond au nombre d’utilisateurs actifs dans l’équipe pour la période spécifiée.</li><li>**Invités** correspond au nombre d’invités dans l’équipe pour la période spécifiée.</li> <li>**Les canaux actifs** sont le nombre de canaux qui comptent au moins un utilisateur actif au cours de la période spécifiée.</li> <li>**Publier des messages** est le nombre de messages publiés dans les canaux pour la période spécifiée.</li> <li>**Les messages de** réponse sont le nombre de messages de réponse dans les canaux pour la période spécifiée.</li> <li>**Les réunions organisées** sont le nombre de réunions programmées et ad hoc organisées par l’utilisateur pendant la période spécifiée. </li><li>**Les messages urgents** sont le nombre de messages urgents pour la période spécifiée.</li><li>**Les réactions** sont le nombre de réactions aux messages au cours de la période spécifiée.</li><li>**Mentions** indique le nombre de mentions utilisées dans les messages au cours de la période spécifiée.</li><li>**Les messages de** canal sont le nombre de messages uniques que les utilisateurs de l’équipe ont publiés dans les conversations d’équipe pendant la période spécifiée.</li> </li> </ul>Notez que si un compte d’utilisateur n’existe plus dans Azure AD, le nom d’utilisateur s’affiche sous la forme « - » dans le tableau. <br><br>Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau. |
|**6**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.|
|**7**   |Vous pouvez exporter le rapport dans un fichier CSV à des fin d’analyse en mode hors connexion. Cliquez **sur Exporter vers Excel,** puis sous l’onglet **Téléchargements,** cliquez sur Télécharger pour télécharger le rapport lorsqu’il est prêt. <br><br>![Capture d’écran de l’onglet Téléchargements affichant les rapports exportés à télécharger](../media/teams-reports-export-to-csv.png)|
|**8** |Les points de données de série de temps dans le graphique montrent différentes mesures d’utilisation agrégées au client|
|**9** |Données tabulaires représentant différentes mesures d’utilisation agrégées par équipe|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)
