---
title: Rapport d’utilisation des applications Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
ms.date: 09/27/2022
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser le rapport d’utilisation des applications Teams dans le Centre d’administration Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c437676df215ead9b588091f2cb58c19d1e136fd
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532264"
---
# <a name="microsoft-teams-app-usage-report"></a>Rapport d’utilisation des applications Microsoft Teams

Le rapport d’utilisation des applications Teams dans le Centre d’administration Microsoft Teams vous fournit des insights sur les applications que les utilisateurs utilisent dans Teams. Vous pouvez obtenir des insights sur l’activité des applications dans votre organisation pour différentes applications Microsoft (Viva Learning, Shifts, etc.), tierces (Polly, Trello, etc.) & applications Teams métier (LOB).   

Vous pouvez utiliser ce rapport pour comprendre où exactement différentes applications sont utilisées et approfondir les données d’utilisation par application.

Les données représentées dans ce rapport fournissent des réponses aux questions suivantes :

-  Combien d’applications installées les utilisateurs de votre environnement ont-ils ?
-  Combien d’applications ont au moins un utilisateur actif dans votre environnement en fonction du type (Microsoft, tiers et métier) ?
-  Combien d’applications sont utilisées par plateforme (Windows, Mac, web ou mobile) ?
-  Combien d’utilisateurs actifs et d’équipes actives utilisent une application ?

> [!NOTE]
> L’utilisation des applications métier **chargées** côté n’est pas incluse dans ce rapport.

Cet article explique comment accéder au rapport et afficher et interpréter les différentes métriques du rapport. 

## <a name="view-the-app-usage-report"></a>Afficher le rapport d’utilisation de l’application

Vous devez être administrateur général, lecteur général ou administrateur du service Teams pour afficher les rapports dans le Centre d’administration Microsoft Teams. Voir [Gérer Teams grâce aux rôles d’administrateur Teams](../using-admin-roles.md) afin d’en savoir plus sur l’obtention de rôles et d’autorisations d’administrateur.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, sélectionnez **Analytics & rapports** > **d’utilisation**. Sous l’onglet **Afficher les rapports** , sous **Rapport**, sélectionnez **Utilisation des applications**.

2. Sous **Plage de dates**, sélectionnez une plage, puis **sélectionnez Exécuter le rapport**.

:::image type="content" alt-text="Capture d’écran du rapport d’utilisation des applications Teams dans le Centre d’administration Teams avec des légendes." source="media/app-usage2-report10.png" lightbox="media/app-usage2-report10.png":::

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport d’utilisation des applications peut être consulté pour les tendances des 7, 30, 90 et 180 derniers jours. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures à partir du moment où une application a été utilisée. Par exemple, les données du 10 janvier doivent apparaître dans le rapport vers le 12 janvier. |
|**3**   |<ul><li>L’axe X représente la plage de dates sélectionnée pour ce rapport.</li> <li> L’axe Y est le nombre d’éléments.</li> </ul>Pointez sur le point représentant un élément à une date donnée pour voir le nombre d’instances de cet élément à cette date donnée.|
|**4**   |Vous pouvez filtrer ce que vous voyez sur le graphique en sélectionnant un élément dans la légende. Par exemple, sélectionnez **Applications Microsoft actives**, **Nombre total d’applications installées** et bien plus encore pour afficher uniquement les informations relatives à chacune d’elles. La modification de cette sélection ne modifie pas les informations du tableau lui-même. <ul><li>**Les applications Microsoft actives** sont le nombre d’applications Microsoft (par exemple, Viva Learning) utilisées au sein de votre organisation. </li> <li>**Les applications tierces actives** sont le nombre d’applications tierces (par exemple Polly) utilisées dans votre organisation.  </li> <li>**Les applications métier actives** sont le nombre d’applications métier utilisées au sein de votre organisation. </li><li>**Le nombre total d’applications actives** correspond au nombre total d’applications utilisées dans votre organisation. </li><li>**Le nombre total d’applications inactives** correspond au nombre d’applications non utilisées dans votre organisation. </li><li>**Le nombre total d’applications installées** correspond au nombre total d’applications installées au sein de votre organisation. La date de début de toutes les métriques d’installation est octobre 2021. Seules les applications installées après cette date sont comptabilisées.</li></ul> Le graphique affiche les métriques agrégées au sein de l’organisation chaque jour au cours d’une période sélectionnée. Par exemple, si vous sélectionnez le 28 janvier et la métrique **Applications tierces actives**, le graphique affiche le nombre total d’applications tierces utilisées le 28 janvier au sein de votre organisation.  |
|**5**   |Le tableau vous donne une répartition de l’utilisation par chaque application. <ul><li>**L’ID d’application** est l’identificateur d’application externe présent dans le manifeste de l’application. <br/>Pour plus d’informations sur l’application, consultez la [section Gérer les applications du Centre d’administration Teams en](/microsoftteams/manage-apps) y faisant référence à l’aide de cet ID d’application externe.</li> <li>**Le nom** de l’application est le nom de cette application tel qu’il est présent dans le manifeste de l’application. </li> <li>**Publisher** est l’éditeur de cette application tel qu’il est présent dans le manifeste de l’application. Cette option est disponible uniquement pour les applications publiées sur le Windows Store global.</li> <li>**Teams utilisant cette application** est le nombre d’équipes Teams distinctes qui ont au moins un utilisateur utilisant cette application. </li><li>**Les utilisateurs qui utilisent cette application** sont le nombre d’utilisateurs distincts de votre organisation qui utilisent cette application.</li> <li>**Utilisé sur Windows** indique si cette application a été utilisée sur Windows par au moins un utilisateur de votre organisation.</li><li>**Utilisé sur Mac** indique si cette application a été utilisée sur MAC par au moins un utilisateur de votre organisation.</li><li>**Utilisé sur le web** indique si cette application a été utilisée sur le web par au moins un utilisateur de votre organisation. </li> <li>**La dernière date utilisée** est la date à laquelle cette application a été utilisée pour la dernière fois par toute personne de votre organisation. </li></ul> |
|**6**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.|
|**7**   |Exportez le rapport vers un fichier CSV pour une analyse hors connexion. Sélectionnez l’icône **Exporter vers Excel** et le rapport sera téléchargé dans votre navigateur.|
|**8** |Les données de série chronologique représentées dans le graphique supérieur montrent différentes métriques d’utilisation agrégées pour l’ensemble du locataire.|
|**9** |Les données tabulaires représentées dans la moitié inférieure affichent différentes métriques d’utilisation agrégées par équipe.|


## <a name="managing-apps-in-the-microsoft-teams-admin-center"></a>Gestion des applications dans le Centre d’administration Microsoft Teams

Pour plus d’informations sur la gestion de vos applications Teams, consultez [À propos des applications dans Microsoft Teams](/microsoftteams/deploy-apps-microsoft-teams-landing-page.md).

Pour lier une application de ce rapport à l’expérience Gérer les applications dans le Centre d’administration Microsoft Teams, vous pouvez utiliser les éléments suivants :

- Nom de l’application
- ID d’application externe

Les ID d’application externes sont équivalents à l’ID de la page Gérer les applications pour les applications du Store. Pour les applications métier, la colonne **ID d’application externe**  peut être activée dans la [section Gérer les applications dans les paramètres de colonne du Centre d’administration Teams](/microsoftteams/manage-apps) . Vous pouvez également l’afficher sur la page des détails de l’application d’une application métier personnalisée.

## <a name="related-articles"></a>Articles connexes

- [Analyses et rapports Teams](teams-reporting-reference.md)
