---
title: Rapport d’utilisation de Microsoft Teams
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
description: Découvrez comment utiliser le rapport utilisation Teams dans le centre d’administration de Microsoft Teams pour obtenir une vue d’ensemble de l’activité des équipes dans votre organisation.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8cc25c5f63bd8645e5bfc540438a77f37abaa164
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904269"
---
# <a name="microsoft-teams-usage-report"></a>Rapport d’utilisation de Microsoft Teams

Le rapport de l’utilisation Teams dans le centre d’administration de Microsoft Teams vous offre une vue d’ensemble de l’activité de l’utilisation dans Teams, y compris le nombre d’utilisateurs et de canaux actifs, pour vous permettre de voir rapidement combien d’utilisateurs utilisent Teams pour communiquer et collaborer au sein de votre organisation. Vous pouvez afficher des informations d’utilisation concernant les équipes, y compris le nombre d’utilisateurs et de canaux actifs, d’invités et de messages dans chaque équipe.

## <a name="view-the-usage-report"></a>Afficher le rapport d’utilisation

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **analyse &** > rapports d'**utilisation**des rapports. Dans l’onglet **afficher les rapports** , sous **rapport**, sélectionnez utilisation des **équipes**.
2. Dans **Plage de dates**, sélectionnez une plage puis cliquez sur **Exécuter le rapport**.

    ![Rapport sur l’utilisation de Microsoft teams dans le centre d’administration teams avec légendes](../media/teams-reports-teams-usage-with-callouts.png "Rapport sur l’utilisation de Microsoft teams dans le centre d’administration teams avec légendes")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport activité d’utilisation des équipes peut être consulté pour les tendances au cours des 7, 28 ou 90 derniers jours. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l’heure de l’activité. |
|**3**   |<ul><li>L’axe X représente la plage de dates sélectionnée pour ce rapport.</li> <li> L’axe Y indique le nombre d’éléments ou activités actif(ve)s.</li> </ul>Pointez sur le point représentant un élément ou une activité à une date donnée pour voir le nombre d’instances de cet élément ou activité à cette date.|
|**4**   |Vous pouvez filtrer ce qui est affiché dans le tableau en cliquant sur un élément dans la légende. Par exemple, cliquez sur **nombre total d’utilisateurs actifs**, **équipes & canaux actifs**, **canaux actifs**ou **messages** pour afficher uniquement les informations relatives à chacun d’eux. La modification de cette sélection ne modifie pas les informations du tableau lui-même. |
|**5**   |Le tableau présente une répartition de l’utilisation par équipe. <ul><li>**Nom** de l’équipe correspond au nom d’affichage de l’équipe. Vous pouvez cliquer sur le nom de l’équipe pour accéder à la page des paramètres de l’équipe dans le centre d’administration Microsoft Teams. </li> <li>**Confidentialité** indique si l’équipe est une équipe privée ou publique.</li> <li>**Utilisateurs actifs** correspond au nombre d’utilisateurs actifs dans l’équipe pour la période spécifiée.</li><li>**Invités** correspond au nombre d’invités dans l’équipe pour la période spécifiée.</li> <li>**Canaux actifs** correspond au nombre de canaux disposant d’au moins un utilisateur actif pendant la période spécifiée.</li> <li>**Publications** est le nombre de tous les messages de publication dans les canaux pendant la période spécifiée.</li> <li>**Messages de réponse** correspond au numéro de tous les messages de réponse dans les canaux pendant la période spécifiée.</li> <li>**Réunions organisées** est le nombre de toutes les réunions planifiées organisées par un utilisateur. Chaque instance d’une réunion périodique est calculée en une seule réunion.</li><li>**Messages urgents** indique le nombre de messages urgents pendant la période spécifiée.</li><li>**Réactions** est le nombre de réponses aux messages pendant la période spécifiée.</li><li>**Mentions** est le nombre de toutes les mentions utilisées dans les messages pendant la période spécifiée.</li><li>**Messages de canal** indique le nombre de messages uniques que les utilisateurs d’une équipe a publié dans une conversation d’équipe pendant la période spécifiée.</li> </li> </ul>Notez que si un compte d’utilisateur n’existe plus dans Azure AD, le nom d’utilisateur est affiché en tant que « -- » dans la table. <br><br>Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau. |
|**6**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.|
|**7**   |Vous pouvez exporter le rapport dans un fichier CSV pour une analyse hors connexion. Cliquez sur **Exporter vers Excel**, puis sous l’onglet **téléchargements** , cliquez sur **Télécharger** pour télécharger le rapport dès qu’il est prêt.<br><br>![Capture d’écran de l’onglet téléchargements montrant les rapports exportés à télécharger](../media/teams-reports-export-to-csv.png)|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)
