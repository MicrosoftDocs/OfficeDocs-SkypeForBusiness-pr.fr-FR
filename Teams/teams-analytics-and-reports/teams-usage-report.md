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
ms.openlocfilehash: ef5011ebbfbcbb62332c1fd9a43b19ce2b25b0ff
ms.sourcegitcommit: 00a526c5b9829302f7c4e0631d0c2dac50b7d004
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/16/2022
ms.locfileid: "69436690"
---
# <a name="microsoft-teams-usage-report"></a>Rapport d’utilisation de Microsoft Teams

Le rapport de l’utilisation Teams dans le centre d’administration de Microsoft Teams vous offre une vue d’ensemble de l’activité de l’utilisation dans Teams, y compris le nombre d’utilisateurs et de canaux actifs, pour vous permettre de voir rapidement combien d’utilisateurs utilisent Teams pour communiquer et collaborer au sein de votre organisation. Vous pouvez afficher des informations d’utilisation concernant les équipes, y compris le nombre d’utilisateurs et de canaux actifs, d’invités et de messages dans chaque équipe.

Avec des informations supplémentaires sur les utilisateurs internes et externes, vous pouvez désormais mesurer la collaboration au sein des [canaux partagés](/Teams/shared-channels.md) internes et externes d’une équipe. Par exemple, les métriques telles que les canaux partagés actifs et les utilisateurs actifs externes dans une équipe aideront l’administrateur à mesurer la collaboration entre les canaux partagés au sein d’une équipe.

## <a name="view-the-usage-report"></a>Afficher le rapport d’utilisation

Vous devez être administrateur général, lecteur général et lecteur de rapports, ou administrateur de service Teams pour afficher les rapports dans le Centre d’administration Teams. Voir [Gérer Teams grâce aux rôles d’administrateur Teams](../using-admin-roles.md) afin d’en savoir plus sur l’obtention de rôles et d’autorisations d’administrateur.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Analytique & rapports** > **Rapports d’utilisation**. Sous l’onglet **Afficher les rapports** , sous **Rapport**, sélectionnez **Utilisation de Teams**.
2. Dans **Plage de dates**, sélectionnez une plage puis cliquez sur **Exécuter le rapport**.

    ![Capture d’écran du rapport d’utilisation de Teams dans le Centre d’administration Teams avec légendes.](../media/teams-reports-teams-usage-with-callouts2.png "Capture d’écran du rapport d’utilisation de Teams dans le Centre d’administration Teams avec légendes")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport d’activité d’utilisation de Teams peut être consulté pour connaître les tendances au cours des 7, 30, 90 et 180 derniers jours. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport au moment de l’activité. |
|**3**   |<ul><li>L’axe X représente la plage de dates sélectionnée pour ce rapport.</li> <li> L’axe Y indique le nombre d’éléments ou activités actif(ve)s.</li> </ul>Pointez sur le point représentant un élément ou une activité à une date donnée pour voir le nombre d’instances de cet élément ou activité à cette date.|
|**4**   |Vous pouvez filtrer ce qui est affiché dans le tableau en cliquant sur un élément dans la légende. Par exemple, cliquez sur  **Utilisateurs actifs internes**, **Invités actifs**,  **Canaux actifs**, **Publications**, etc. pour afficher uniquement les informations relatives à chacun d’eux. La modification de cette sélection ne modifie pas les informations du tableau lui-même. |
|**5**   |Le tableau présente une répartition de l’utilisation par équipe. <ul><li>**Nom de** l’équipe est le nom complet de l’équipe. Vous pouvez cliquer sur le nom de l’équipe pour accéder à la page des paramètres de l’équipe dans le centre d’administration Microsoft Teams. </li> <li>**L’ID d’équipe** est l’identificateur d’équipe unique. </li> <li>**Le type** indique si l’équipe est une équipe privée ou une équipe publique.</li> <li>**Utilisateurs actifs internes** est le nombre d’utilisateurs actifs, y compris les invités qui effectuent une action dans cette équipe au cours de la période spécifiée. <br/>Les utilisateurs internes et les invités résident dans le même locataire, mais ne sont pas les mêmes.</li><li>**Invités actifs** est le nombre d’invités qui effectuent une action dans cette équipe au cours de la période spécifiée.</li> <li>**Utilisateurs actifs externes** (nouveau) est le nombre d’utilisateurs actifs d’organisations externes qui effectuent une action dans cette équipe dans une ressource, par exemple un canal partagé dans une équipe. <br/> Les utilisateurs externes ont leurs propres identités dans différents locataires et ne sont pas identiques à un compte invité.</li><li>**Les canaux actifs** sont le nombre de canaux dans l’équipe qui a au moins un utilisateur actif au cours de la période spécifiée. Cela inclut les canaux privés, publics et partagés. </li><li>**Canaux partagés actifs** (nouveau) est le nombre de canaux partagés dans une équipe qui a au moins un utilisateur interne ou externe actif dans la période spécifiée. </li> <li>**Le nombre total de réunions organisées** correspond à la somme des réunions planifiées, périodiques, non planifiées et non classifiées organisées par un utilisateur au cours de la période spécifiée. </li><li>**Posts** est le nombre de tous les messages de publication dans les canaux au cours de la période spécifiée.</li> <li>**Réponses** est le nombre de tous les messages de réponse dans les canaux au cours de la période spécifiée.</li> <li>**Mentions** est le nombre de toutes les mentions utilisées dans les messages au cours de la période spécifiée.</li><li>**Réactions** est le nombre de toutes les réactions aux messages au cours de la période spécifiée.</li><li>**Les messages urgents** sont le nombre de tous les messages urgents dans la période spécifiée.</li><li>**Les messages de canal** correspondent au nombre de messages uniques que les utilisateurs de l’équipe ont publiés dans les conversations d’équipe au cours de la période spécifiée.</li> </li> </ul>Notez que si une équipe n’existe plus, le nom est affiché sous la forme « - » dans le tableau. <br><br>Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau. |
|**6**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.|
|**7**   |Exportez le rapport vers un fichier CSV à des fins d’analyse hors connexion. Sélectionnez l’icône **Exporter vers Excel** pour télécharger le rapport dans votre navigateur.|
|**8** |Les données de série chronologique représentées dans le graphique supérieur montrent différentes métriques d’utilisation agrégées pour l’ensemble du locataire|
|**9** |Les données tabulaires représentées dans la moitié inférieure montrent différentes métriques d’utilisation agrégées par équipe|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]


## <a name="make-the-user-specific-data-anonymous"></a>Rendre les données spécifiques de l’utilisateur anonymes

Pour que les données du rapport d’activité utilisateur Teams soient anonymes, vous devez être administrateur général. L’administrateur général peut masquer les informations d’identification (à l’aide de hachages MD5), telles que le nom d’affichage, le nom du groupe, l’adresse e-mail et l’ID AAD dans le rapport et son exportation.

1. Dans Centre d'administration Microsoft 365, accédez à **Paramètres Paramètres** > **De l’organisation**, puis sous l’onglet **Services**, choisissez **Rapports**.
    
2. Sélectionnez **Rapports**, puis **Afficher les noms des utilisateurs, des groupes et des sites masqués dans tous les rapports**. Ce paramètre est appliqué aux rapports d’utilisation dans Centre d'administration Microsoft 365 ainsi qu’au centre d’administration Teams.
  
3. Sélectionnez **Enregistrer les modifications**.

> [!NOTE]
> L’activation de ce paramètre permet d’identifier les informations de nom d’utilisateur, de groupe et de site dans le [rapport d’activité des utilisateurs Teams](user-activity-report.md), le [rapport d’utilisation des appareils Teams](device-usage-report.md) et le [rapport d’utilisation de Teams](teams-usage-report.md). À compter du 1er septembre 2021, ce paramètre est activé par défaut pour tout le monde dans le cadre de notre engagement continu à protéger les informations importantes et à permettre aux entreprises de prendre en charge leurs lois locales sur la protection de la vie privée. 
>
>Ce paramètre s’applique également aux rapports d’utilisation Microsoft 365 dans Centre d'administration Microsoft 365, Microsoft Graph et Power BI.

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)
