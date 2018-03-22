---
title: Utiliser des rapports d’activité pour Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 03/08/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
description: Découvrez comment utiliser les rapports d’activité pour voir comment les utilisateurs de votre organisation utilisent Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 14e2bc5964af6bf37988960c2d4626de17805fba
ms.sourcegitcommit: ccbe086ccb2c0be716984010a1253a4c8c0276b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2018
---
<a name="use-activity-reports-for-microsoft-teams"></a>Utiliser des rapports d’activité pour Microsoft Teams 
========================================

Vous pouvez utiliser les rapports d’activité pour voir comment les utilisateurs de votre organisation utilisent Microsoft Teams. Par exemple, si certains n’utilisent pas encore les équipes, ne peut-être pas savent à commencer ou à comprendre comment ils peuvent utiliser des équipes à être plus productifs et de collaboration. Votre organisation peut utiliser les rapports d’activité pour décider de l’emplacement hiérarchiser les efforts de formation et de communication.

## <a name="how-to-get-to-the-reports-dashboard"></a>Comment faire pour obtenir le tableau de bord des rapports

1. Dans le [Centre d’administration Office 365](https://portal.office.com/adminportal/home), sélectionnez **rapports** > **l’utilisation**.
 
2. Sur la page **d’utilisation** , cliquez sur **Sélectionnez un rapport** à sélectionner dans la liste des rapports disponibles. 

## <a name="teams-activity-reports-that-are-available"></a>Rapports d’activité équipes disponibles

Il existe actuellement deux rapports sur les activités que vous pouvez afficher :

- Rapport d’activité utilisateur Microsoft Teams 
- Rapport d’utilisation du périphérique Microsoft Teams 

### <a name="microsoft-teams-user-activity-report"></a>Rapport d’activité utilisateur Microsoft Teams

Le rapport d’activité utilisateur Microsoft Teams vous donne un aperçu des activités plus courantes que les utilisateurs effectuent dans Teams de Microsoft. Cela inclut le nombre de personnes participer à une conversation sur un canal, combien de communiquer via un message de conversation privée et participe le nombre des appels ou des réunions. Vous pouvez afficher ces informations à la fois au niveau des clients, ainsi que pour chaque utilisateur.

![Capture d’écran de l’état d’activité utilisateur équipes dans le centre d’administration Office 365.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpréter le rapport d’activité utilisateur Microsoft Teams

Vous pouvez obtenir une vue en activité de l’utilisateur Teams de Microsoft en consultant les diagrammes **d’activité** et **les utilisateurs** .

![Capture d’écran de l’état d’activité utilisateur équipes dans le centre d’administration Office 365 avec légendes numérotées.](media/teams-user-activity-report-with-callouts.png)

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport d’activité utilisateur Teams de Microsoft peut être affiché les tendances sur les 7 derniers jours, 30 jours, jours de 90 ou 180 jours. Toutefois, si vous cliquez sur un jour particulier dans le rapport, la table (7) affiche données pendant 30 jours, jusqu'à la date (2) pour lorsque le rapport a été généré. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité. |
|**3**   |L’affichage de **l’activité** vous indique le nombre d’activités de Teams de Microsoft par type d’activité. Les types d’activité sont le nombre de messages de conversation, les messages de conversation privée, les appels ou les réunions des équipes. |
|**4**   |La vue des **utilisateurs** vous indique le nombre d’utilisateurs par type d’activité. Les types d’activité sont le nombre de messages de conversation, les messages de conversation privée, les appels ou les réunions des équipes. |
|**5**   |L’axe des abscisses sur les graphiques est la plage de dates sélectionnée pour le rapport. <ul><li>Sur le graphique de **l’activité** , l’axe Y est le nombre d’activité spécifié.</ul></li> <ul><li>Sur le plan de **fichiers** , l’axe Y est le nombre d’utilisateurs de participer à des conversations des équipes, des conversations privées, les appels ou réunions.</ul></li> |
|**6**   |You can filter the series you see on the chart by clicking on an item in the legend. Par exemple, sur le graphique de **l’activité** , cliquez sur ou cliquez sur **messages de canal**, **Chat des messages**, **appels**ou **réunions** pour afficher uniquement les informations relatives à chacun d’eux. La modification de cette sélection ne change pas les informations contenues dans la table de grille. |
|**7**   |La liste des groupes affichés est déterminée par le jeu de tous les groupes qui existaient (n’ont pas été supprimés) sur l’intervalle de temps de création de rapports (180 jours) plus large.  Le nombre d’activités peut varier en fonction de la sélection de date. <ul><li>**Nom d’utilisateur** est l’adresse de messagerie de l’utilisateur. Vous pouvez afficher l’adresse de messagerie réelle ou rendre ce champ anonyme.</ul></li> <ul><li>**Dernière activité Date (UTC)** fait référence à la dernière date à laquelle l’utilisateur a participé à une activité Teams de Microsoft.</ul></li> <ul><li>**Messages du canal** est le nombre de messages uniques que l’utilisateur est validée dans une discussion d’équipe au cours de la période spécifiée.</ul></li> <ul><li>**Messages de la conversation** est le nombre de messages uniques que l’utilisateur a publiées privé conversation au cours de la période spécifiée.</ul></li> <ul><li>**Appels** est le nombre d’appels qui a participé à l’utilisateur au cours de la période spécifiée.</ul></li> <ul><li>**Réunions** est le nombre de réunions en ligne que l’utilisateur a participé au cours de la période spécifiée.</ul></li> <ul><li>**Toute autre activité** est le nombre d’autres activités d’équipe par l’utilisateur.</ul></li> <ul><li>**Deleted** indique si l’équipe est supprimé. Si l’équipe est supprimé, mais il enregistre l’activité de la période de reporting, il apparaîtra dans la grille avec supprimé a la valeur true.</ul></li> <ul><li>**Deleted date** est la date à laquelle l’équipe a été supprimé.</ul></li> <ul><li>**Le produit affecté** est la liste des produits qui sont affectées à l’utilisateur.</ul></li> <ui>**Remarque :** Vous verrez ne peut-être pas tous les éléments dans la liste ci-dessous dans les colonnes jusqu'à ce que vous les ajoutez. </ul><br><br> <ui>Si les stratégies de votre organisation vous empêche l’affichage des rapports où les informations de l’utilisateur sont identifiables, vous pouvez modifier le paramètre de confidentialité pour tous ces rapports. Extraire le **comment masquer les détails de niveau utilisateur ?** section dans les [Rapports d’activité dans le centre d’administrateur Office 365 Preview](https://support.office.com/en-us/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Cliquez ou appuyez sur **Colonnes** pour ajouter ou supprimer des colonnes du rapport. |
|**9**   |Vous pouvez également exporter les données du rapport dans un fichier .csv Excel, en cliquant sur le lien Exporter. Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez trier et filtrer dans la table dans le rapport lui-même. Si vous avez plus de 2 000 utilisateurs, afin de filtrer et trier, vous devez exporter les données. |

### <a name="microsoft-teams-device-usage-report"></a>Rapport d’utilisation du périphérique Microsoft Teams

Le rapport d’utilisation d’application Teams de Microsoft fournit des informations sur la façon dont vos utilisateurs se connectent à Microsoft Teams, y compris les applications mobiles. Le rapport permet d’identifier les périphériques les plus populaires dans votre organisation et le nombre d’utilisateurs travailler en déplacement.

![Capture d’écran de l’état de l’utilisation du périphérique équipes dans le centre d’administration Office 365.](media/teams-device-usage-report.png)

## <a name="who-can-access-the-teams-activity-reports"></a>Qui peut accéder à le rapports d’activité équipes

Les rapports d’activité sont accessibles par les utilisateurs qui sont attribués :

- Rôle d’administrateur global de Office 365
- Rôle admin de produits spécifiques (Exchange, Skype pour entreprise ou SharePoint)
- Rôle de lecteur de rapports

### <a name="reports-reader-role"></a>Rôle de lecteur de rapports

Vous pouvez attribuer le rôle de *lecteur de rapports* à un personnel non spécialisé qui vous souhaitez avoir accès à ces rapports. En attribuant ce rôle à des responsables de la formation ou aux parties prenantes de l’entreprise, il se peut que vous pouvez vous assurer qu’ils ont accès à répercuter les informations qui sont utiles à l’adoption de lecteur et le suivi des équipes.

## <a name="other-information-on-the-reports-dashboard"></a>Autres informations sur le tableau de bord des rapports

### <a name="at-a-glance-activity-widget"></a>Widget de l’activité d’un coup de œil

Le tableau de bord de rapports inclut les données d’utilisation à partir de Teams de Microsoft dans le widget d’activité d’un coup de œil, ce qui vous donne une vue de produit vectoriel de la façon dont les utilisateurs communiquent et collaborent à l’aide de divers autres services dans Office 365.

![Capture d’écran du widget équipes activité d’un coup de œil sur le tableau de bord des rapports.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Carte d’activité aux équipes

Le tableau de bord des rapports inclut également une nouvelle carte de Teams de Microsoft. La carte vous offre une vue d’ensemble de l’activité dans des équipes, notamment le nombre d’utilisateurs actifs, de sorte que vous pouvez comprendre rapidement le nombre d’utilisateurs utilisent le service.

![Capture d’écran de la carte d’activité équipes sur le tableau de bord des rapports.](media/teams-activity-card.png)
