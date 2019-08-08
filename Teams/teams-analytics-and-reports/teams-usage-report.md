---
title: Rapport d’utilisation de Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 06/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Découvrez comment utiliser le rapport utilisation Teams dans le centre d’administration de Microsoft Teams pour obtenir une vue d’ensemble de l’activité des équipes dans votre organisation.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a5fdee65771f2ac23e2cea78e54752786357405
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234769"
---
# <a name="microsoft-teams-usage-report"></a>Rapport d’utilisation de Microsoft Teams

Le rapport de l’utilisation Teams dans le centre d’administration de Microsoft Teams vous offre une vue d’ensemble de l’activité de l’utilisation dans Teams, y compris le nombre d’utilisateurs et de canaux actifs, pour vous permettre de voir rapidement combien d’utilisateurs utilisent Teams pour communiquer et collaborer au sein de votre organisation. Vous pouvez afficher des informations d’utilisation concernant les équipes, y compris le nombre d’utilisateurs et de canaux actifs, d’invités et de messages dans chaque équipe.

![Capture d’écran du rapport utilisation de Microsoft teams dans le centre d’administration] (../media/teams-reports-teams-usage.png "Capture d’écran du rapport utilisation de Microsoft teams dans le centre d’administration Microsoft teams")

## <a name="view-the-report"></a>Afficher le rapport

1.In le centre d’administration de Microsoft Teams, dans le volet de navigation de gauche, cliquez sur **analyse & rapports**, puis sous **rapport**, sélectionnez **utilisation des équipes**.
2. Dans **Plage de dates**, sélectionnez une plage puis cliquez sur **Exécuter le rapport**.

## <a name="interpret-the-report"></a>Interpréter le rapport

![Capture d’écran du rapport utilisation de Microsoft teams dans le centre d’administration] (../media/teams-reports-teams-usage-with-callouts.png "Capture d’écran du rapport utilisation de Microsoft teams dans le centre d’administration Microsoft teams avec des légendes numérotées")

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport d’activité Teams permet d’observer des tendances sur les 7 ou 28 derniers jours. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l’heure de l’activité. |
|**3**   |<ul><li>L’axe X représente la plage de dates sélectionnée pour ce rapport.</li> <li> L’axe Y indique le nombre d’éléments ou activités actif(ve)s.</li> </ul>Pointez sur le point représentant un élément ou une activité à une date donnée pour voir le nombre d’instances de cet élément ou activité à cette date.|
|**4**   |Vous pouvez filtrer ce qui est affiché dans le tableau en cliquant sur un élément dans la légende. Par exemple, cliquez sur **nombre total d’utilisateurs actifs**, **équipes & canaux actifs**, **canaux actifs**ou **messages** pour afficher uniquement les informations relatives à chacun d’eux. La modification de cette sélection ne modifie pas les informations du tableau lui-même. |
|**5**   |Le tableau présente une répartition de l’utilisation par équipe. <ul><li>**Nom** de l’équipe correspond au nom d’affichage de l’équipe. Vous pouvez cliquer sur le nom de l’équipe pour accéder à la page des paramètres de l’équipe dans le centre d’administration Microsoft Teams. </li> <li>**Confidentialité** indique si l’équipe est une équipe privée ou publique.</li> <li>**Utilisateurs actifs** correspond au nombre d’utilisateurs actifs dans l’équipe pour la période spécifiée.</li><li>**Invités** correspond au nombre d’invités dans l’équipe pour la période spécifiée.</li> </li> </ul>Notez que si un compte d’utilisateur n’existe plus dans Azure AD, le nom d’utilisateur est affiché en tant que «--» dans la table. <br><br>Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau. |
|**6**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.|
|**7**   |Vous pouvez exporter le rapport dans un fichier CSV pour une analyse hors connexion. Cliquez sur **Exporter vers Excel**, puis sous l’onglet **téléchargements** , cliquez sur **Télécharger** pour télécharger le rapport dès qu’il est prêt.<br>![Capture d’écran de l’onglet téléchargements indiquant les rapports exportés à télécharger](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>Voir aussi
- [Analyses et rapports Teams](teams-reporting-reference.md)
