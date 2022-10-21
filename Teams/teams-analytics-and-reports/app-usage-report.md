---
title: Rapport d’utilisation de l’application Microsoft Teams
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
description: Découvrez comment utiliser le rapport d’utilisation de l’application Teams dans le Centre d’administration Teams pour connaître les équipes et les utilisateurs actifs d’une application.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c907dc44ff7b76b3df94843d6e33f4a711b37721
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68655880"
---
# <a name="microsoft-teams-app-usage-report"></a>Rapport d’utilisation de l’application Microsoft Teams

Le rapport d’utilisation des applications Teams dans le Centre d’administration Microsoft Teams vous fournit des informations sur les applications que les utilisateurs utilisent dans Teams. Vous pouvez obtenir des insights sur l’activité des applications dans votre organisation pour différentes applications Microsoft (Viva Learning, Shifts, etc.), tierces (Polly, Trello, etc.) & métier Teams.   

Vous pouvez utiliser ce rapport pour comprendre où exactement différentes applications sont utilisées et pour approfondir les données d’utilisation par application.

Les données représentées dans ce rapport fournissent des réponses aux questions suivantes :

-  Combien d’applications installées les utilisateurs de votre environnement ont-ils ?
-  Combien d’applications ont au moins un utilisateur actif dans votre environnement en fonction du type (Microsoft, tiers et métier) ?
-  Combien d’applications sont utilisées par plateforme (Windows, Mac, web ou mobile) ?
-  Combien d’utilisateurs actifs et d’équipes actives utilisent une application ?

> [!NOTE]
> L’utilisation des applications métier chargées de manière **latérale** n’est pas incluse dans ce rapport.

Cet article explique comment accéder au rapport, afficher et interpréter les différentes métriques dans le rapport. 

## <a name="view-the-app-usage-report"></a>Afficher le rapport d’utilisation de l’application

Vous devez être administrateur général, lecteur général ou administrateur de service Teams pour afficher les rapports dans le Centre d’administration Microsoft Teams. Voir [Gérer Teams grâce aux rôles d’administrateur Teams](../using-admin-roles.md) afin d’en savoir plus sur l’obtention de rôles et d’autorisations d’administrateur.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, sélectionnez **Analytique & rapports** > **Rapports d’utilisation**. Sous l’onglet **Afficher les rapports** , sous **Rapport**, sélectionnez **Utilisation des applications**.

2. Sous **Plage de dates**, sélectionnez une plage, puis **sélectionnez Exécuter le rapport**.

:::image type="content" alt-text="Capture d’écran du rapport d’utilisation de l’application Teams dans le Centre d’administration Teams avec légendes." source="media/app-usage2-report10.png" lightbox="media/app-usage2-report10.png":::

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport d’utilisation de l’application peut être consulté pour connaître les tendances au cours des 7, 30, 90 et 180 derniers jours. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures entre le moment où une application a été utilisée. Par exemple, les données du 10 janvier doivent apparaître dans le rapport vers le 12 janvier. |
|**3**   |<ul><li>L’axe X représente la plage de dates sélectionnée pour ce rapport.</li> <li> L’axe Y est le nombre d’éléments.</li> </ul>Pointez sur le point représentant un élément à une date donnée pour voir le nombre d’instances de cet élément à cette date donnée.|
|**4**   |Vous pouvez filtrer ce que vous voyez sur le graphique en sélectionnant un élément dans la légende. Par exemple, sélectionnez **Applications Microsoft actives**, **Nombre total d’applications installées**, etc. pour afficher uniquement les informations relatives à chacune d’elles. La modification de cette sélection ne modifie pas les informations du tableau lui-même. <ul><li>**Les applications Microsoft actives** correspondent au nombre d’applications Microsoft (par exemple, Viva Learning) utilisées dans votre organisation. </li> <li>**Les applications tierces actives** correspondent au nombre d’applications tierces (par exemple, Polly) utilisées dans votre organisation.  </li> <li>**Les applications métier actives** sont le nombre d’applications métier utilisées dans votre organisation. </li><li>**Le nombre total d’applications actives** est le nombre total d’applications utilisées au sein de votre organisation. </li><li>**Le nombre total d’applications inactives** correspond au nombre d’applications non utilisées dans votre organisation. </li><li>**Le nombre total d’applications installées** correspond au nombre total d’applications installées au sein de votre organisation. La date de début de toutes les métriques d’installation est octobre 2021. Seules les applications installées après cette date seront comptabilisées.</li></ul> Le graphique montre les métriques agrégées au sein de l’organisation chaque jour au cours d’une période sélectionnée. Par exemple, si vous sélectionnez 28 janvier et que vous métrique **Applications tierces actives**, le graphique vous indique le nombre total d’applications tierces utilisées le 28 janvier au sein de votre organisation.  |
|**5**   |Le tableau vous donne une répartition de l’utilisation par application. <ul><li>**L’ID d’application** est l’identificateur d’application externe présent dans le manifeste de l’application. <br/>Vous trouverez plus d’informations sur l’application dans la [section Gérer les applications du Centre d’administration Teams en](/microsoftteams/manage-apps) y faisant référence à l’aide de cet ID d’application externe.</li> <li>**Nom de** l’application est le nom de cette application tel qu’il figure dans le manifeste de l’application. </li> <li>**Publisher** est l’éditeur de cette application tel qu’il figure dans le manifeste de l’application. Cette option est uniquement disponible pour les applications publiées sur le Store global.</li> <li>**Teams utilisant cette application** correspond au nombre d’équipes Teams distinctes qui ont au moins un utilisateur utilisant cette application. </li><li>**Utilisateurs utilisant cette application** correspond au nombre d’utilisateurs distincts de votre organisation qui utilisent cette application.</li> <li>**Utilisé sur Windows** indique si cette application a été utilisée sur Windows par au moins un utilisateur de votre organisation.</li><li>**Utilisé sur Mac** indique si cette application a été utilisée sur MAC par au moins un utilisateur de votre organisation.</li><li>**Utilisé sur le web** indique si cette application a été utilisée sur le web par au moins un utilisateur de votre organisation. </li> <li>**La date de la dernière utilisation** est la date à laquelle cette application a été utilisée pour la dernière fois par un membre de votre organisation. </li></ul> |
|**6**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.|
|**7**   |Exportez le rapport vers un fichier CSV à des fins d’analyse hors connexion. Sélectionnez l’icône **Exporter vers Excel** pour télécharger le rapport dans votre navigateur.|
|**8** |Les données de série chronologique représentées dans le graphique supérieur montrent différentes métriques d’utilisation agrégées pour l’ensemble du locataire.|
|**9** |Les données tabulaires représentées dans la moitié inférieure montrent différentes métriques d’utilisation agrégées par équipe.|


## <a name="managing-apps-in-the-microsoft-teams-admin-center"></a>Gestion des applications dans le Centre d’administration Microsoft Teams

Pour plus d’informations sur la gestion de vos applications Teams, consultez [À propos des applications dans Microsoft Teams](/microsoftteams/deploy-apps-microsoft-teams-landing-page.md).

Pour lier une application de ce rapport à l’expérience Gérer les applications dans le Centre d’administration Microsoft Teams, vous pouvez utiliser les éléments suivants :

- Nom de l’application
- ID d’application externe

Les ID d’application externes sont équivalents à l’ID dans la page Gérer les applications pour les applications du Windows Store. Pour les applications métier, la colonne **ID d’application externe**  peut être activée dans la [section Gérer les applications des paramètres de colonne du Centre d’administration Teams](/microsoftteams/manage-apps) . Vous pouvez également l’afficher sur la page des détails de l’application d’une application métier personnalisée.

## <a name="related-articles"></a>Articles connexes

- [Analyses et rapports Teams](teams-reporting-reference.md)
