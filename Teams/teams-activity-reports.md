---
title: Utiliser des rapports d’activité pour Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: lolaj
ms.date: 04/17/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: chenle
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
description: Découvrez comment utiliser les rapports d’activité pour voir comment les utilisateurs de votre organisation utilisent Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5262795147853c6587853365eed589e65dbd81ff
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2018
ms.locfileid: "19000118"
---
<a name="use-activity-reports-for-microsoft-teams"></a>Utiliser des rapports d’activité pour Microsoft Teams 
========================================

Vous pouvez utiliser les rapports d’activité pour voir comment les utilisateurs de votre organisation utilisent Microsoft Teams. Par exemple, si certains n’utilisent pas encore les équipes, ils peuvent sait pas à commencer ou à comprendre comment ils peuvent utiliser des équipes à être plus productifs et collaborative. Votre organisation peut utiliser les rapports d’activité pour déterminer où hiérarchiser les efforts de formation et de communication.

## <a name="how-to-get-to-the-reports-dashboard"></a>Comment obtenir au tableau de bord de rapports

1. Dans le [Centre d’administration Office 365](https://portal.office.com/adminportal/home), sélectionnez **rapports** > **l’utilisation**.
 
2. Dans la page de **l’utilisation** , choisissez **Sélectionner un rapport** de sélectionner à partir d’une liste des rapports disponibles. 

## <a name="teams-activity-reports-that-are-available"></a>Rapports d’activité équipes disponibles

Il existe actuellement deux rapports d’activité que vous pouvez afficher :

- Rapport d’activité utilisateur Microsoft Teams 
- Rapport d’utilisation des périphériques Microsoft Teams 

### <a name="microsoft-teams-user-activity-report"></a>Rapport d’activité utilisateur Microsoft Teams

Le rapport d’activité utilisateur Teams Microsoft vous donne un aperçu des activités plus courantes effectuées dans Microsoft Teams. Cela inclut le nombre de personnes prendre part à une conversation dans un canal, combien de communiquer via un message de chat privé et combien participer à des appels ou réunions. Vous pouvez consulter ces informations à la fois au niveau du client, ainsi que pour chaque utilisateur.

![Capture d’écran de l’état d’activité utilisateur équipes dans le centre d’administration d’Office 365.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpréter le rapport d’activité utilisateur Microsoft Teams

Vous pouvez obtenir une vue dans l’activité de l’utilisateur Microsoft Teams en examinant les graphiques et **les utilisateurs** de **l’activité** .

![Capture d’écran de l’état d’activité utilisateur équipes dans le centre d’administration Office 365 avec légendes numérotées.](media/teams-user-activity-report-with-callouts.png)

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport d’activité utilisateur Teams Microsoft peut être affiché pour les tendances sur les 7 derniers jours, 30 jours, de 90 jours ou 180 jours. Toutefois, si vous cliquez sur dans un jour donné dans le rapport, le tableau (7) affiche données pendant 30 jours, jusqu'à la date (2) pour lorsque le rapport a été généré. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l'heure de l'activité. |
|**3**   |L’affichage de **l’activité** vous indique le nombre d’activités Microsoft Teams par type d’activité. Les types d’activité sont le nombre de messages de conversation, les messages de conversation privée, les appels ou des réunions des équipes. |
|**4**   |La vue des **utilisateurs** vous indique le nombre d’utilisateurs par type d’activité. Les types d’activité sont le nombre de messages de conversation, les messages de conversation privée, les appels ou des réunions des équipes. |
|**5**   |L’axe des X dans les graphiques sont la plage de dates sélectionnée pour le rapport spécifique. <ul><li>Dans le graphique de **l’activité** , l’axe des Y sont le nombre d’activité spécifié.</ul></li> <ul><li>Dans le graphique de **fichiers** , l’axe des Y sont le nombre d’utilisateurs de participer à des conversations d’équipes, salles de conversation privées, appels ou réunions.</ul></li> |
|**6**   |You can filter the series you see on the chart by clicking on an item in the legend. Par exemple, dans le graphique de **l’activité** , cliquez sur ou appuyez sur les **messages de canal**, **messages de conversation**, **les appels**ou **réunions** pour afficher uniquement les informations relatives à chacun d’eux. Modification de cette sélection ne change pas les informations contenues dans la table de grille. |
|**7**   |La liste des groupes affichés est déterminée par l’ensemble de tous les groupes qui existaient (n’ont pas été supprimés) sur le critère de temps de création de rapports (180 jours) plus large.  Le nombre d’activités varient en fonction de la sélection de date. <ul><li>**Nom d’utilisateur** est l’adresse de messagerie de l’utilisateur. Vous pouvez afficher l’adresse de messagerie réelle ou rendre ce champ anonyme.</ul></li> <ul><li>**Dernière activité Date (UTC)** fait référence à la dernière date à laquelle l’utilisateur a participé à une activité Teams Microsoft.</ul></li> <ul><li>**Messages de canal** est le nombre de messages uniques que l’utilisateur est publié dans une conversation de l’équipe au cours de la période spécifiée.</ul></li> <ul><li>**Messages de conversation** est le nombre de messages uniques que l’utilisateur validées privé conversation au cours de la période spécifiée.</ul></li> <ul><li>**Appels** est le nombre d’appels ayant participé à l’utilisateur pendant la période spécifiée.</ul></li> <ul><li>**Réunions** est le nombre de réunions en ligne que l’utilisateur a participé à la période spécifiée.</ul></li> <ul><li>**Autres activités** est le nombre d’autres activités d’équipe par l’utilisateur.</ul></li> <ul><li>**Deleted** indique si l’équipe est supprimé. Si l’équipe est supprimé, mais effectué dans la période de rapport, il apparaîtra dans la grille avec supprimé défini sur true.</ul></li> <ul><li>**Deleted date** est la date à laquelle l’équipe a été supprimé.</ul></li> <ul><li>**Produit affecté** est la liste des produits qui sont affectées à l’utilisateur.</ul></li> <ui>**Remarque :** Vous ne pouvez pas voir tous les éléments dans la liste ci-dessous dans les colonnes jusqu'à ce que vous les ajoutez. </ul><br><br> <ui>Si les stratégies de votre organisation vous empêche l’affichage des rapports où les informations utilisateur sont identifiables, vous pouvez modifier le paramètre de confidentialité pour tous ces rapports. Extraire le **comment masquer les détails de niveau utilisateur ?** section dans les [Rapports d’activité dans le centre d’administration Office 365 Preview](https://support.office.com/en-us/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Cliquez ou appuyez sur **Colonnes** pour ajouter ou supprimer des colonnes du rapport. |
|**9**   |Vous pouvez également exporter les données du rapport dans un fichier .csv Excel, en cliquant sur le lien Exporter. Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez trier et filtrer dans la table dans le rapport lui-même. Si vous avez plus de 2 000 utilisateurs, afin de filtrer et trier, vous devez exporter les données. |

### <a name="microsoft-teams-device-usage-report"></a>Rapport d’utilisation des périphériques Microsoft Teams

Le rapport d’utilisation Teams Microsoft application fournit des informations sur la façon dont vos utilisateurs se connectent à Microsoft Teams, y compris les applications mobiles. Le rapport permet d’identifier les périphériques qui sont courants dans votre organisation et combien d’utilisateurs travailler en déplacement.

![Capture d’écran de l’état de l’utilisation des équipes périphérique dans le centre d’administration d’Office 365.](media/teams-device-usage-report.png)

## <a name="who-can-access-the-teams-activity-reports"></a>Personnes autorisées à accéder les rapports d’activité équipes

Les rapports d’activité est accessible par les utilisateurs qui sont affectés :

- Rôle d’administrateur global Office 365
- Rôle d’administration spécifiques au produit (Exchange, Skype pour les professionnels ou SharePoint)
- Rôle de lecteur de rapports

### <a name="reports-reader-role"></a>Rôle de lecteur de rapports

Vous pouvez attribuer le rôle de *lecteur de rapports* au personnel non informatique qui souhaitent avoir accès à ces rapports. En attribuant ce rôle aux responsables de formation ou les parties prenantes métier, il se peut que vous pouvez vous assurer qu’ils ont accès les analyses sont utiles à l’adoption de lecteur et le suivi des équipes.

## <a name="other-information-on-the-reports-dashboard"></a>Autres informations sur le tableau de bord des rapports

### <a name="at-a-glance-activity-widget"></a>Widget d’activité d’un coup de œil

Le tableau de bord rapports comprend les données d’utilisation de Microsoft Teams dans le widget d’activité d’un coup de œil, qui vous donne une vue entre les produits aux utilisateurs comment communiquent et collaborent à l’aide de divers autres services dans Office 365.

![Capture d’écran du widget équipes activité d’un coup de œil sur le tableau de bord des rapports.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Carte d’activité équipes

Le tableau de bord rapports inclut également une nouvelle carte pour Microsoft Teams. La carte vous donne une vue d’ensemble de l’activité dans les équipes, y compris le nombre d’utilisateurs actifs, afin que vous pouvez comprendre rapidement combien d’utilisateurs d’utilisation du service.

![Capture d’écran de la carte d’activité équipes sur le tableau de bord des rapports.](media/teams-activity-card.png)
