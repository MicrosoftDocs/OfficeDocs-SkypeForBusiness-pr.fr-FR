---
title: Rapports d’activité de l’utilisateur Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 04/17/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: chenle
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Découvrez comment utiliser les rapports d’activité pour voir comment les utilisateurs de votre organisation utilisent Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 202e40439c874aec493b96f8707ff218423d2339
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894351"
---
<a name="use-activity-reports-for-microsoft-teams"></a>Rapports d’activité de l’utilisateur Microsoft Teams 
========================================

Vous pouvez utiliser les rapports d’activité dans le centre d’administration Microsoft 365 pour savoir comment les utilisateurs de votre organisation utilisent Microsoft Teams. Par exemple, si certains n’utilisent pas encore Microsoft Teams, ils peuvent sait pas à commencer ou à comprendre comment ils peuvent utiliser des équipes à être plus productifs et collaborative. Votre organisation peut utiliser les rapports d’activité pour choisir où hiérarchiser les efforts de formation et de communication.

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>Comment afficher les rapports d’équipes dans le tableau de bord des rapports

1. Dans le [Centre d’administration Microsoft 365](https://portal.office.com/adminportal/home), sélectionnez **rapports** > **l’utilisation**.
 
2. Dans la page de **l’utilisation** , choisissez **Sélectionner un rapport**, puis sous **Les équipes Microsoft** dans la liste des rapports, le rapport que vous souhaitez afficher.

## <a name="teams-activity-reports-that-are-available"></a>Rapports d’activité équipes disponibles

Il existe actuellement deux rapports d’activité que vous pouvez afficher :

- [Rapport d’activité des utilisateurs de Microsoft Teams](#microsoft-teams-user-activity-report) 
- [Rapport d’utilisation des périphériques de Microsoft Teams](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Rapport d’activité des utilisateurs de Microsoft Teams

Le rapport d’activité utilisateur équipes vous donne un aperçu des activités plus courantes effectuées dans les équipes. Cela inclut le nombre de personnes prendre part à une conversation dans un canal, combien de communiquer via un message de chat privé et combien participer à des appels ou réunions. Vous pouvez consulter ces informations pour toute l’organisation, ainsi que pour chaque utilisateur.

![Capture d’écran de l’état d’activité utilisateur équipes dans le centre d’administration d’Office 365.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpréter le rapport d’activité utilisateur Microsoft Teams

Vous pouvez obtenir une vue dans l’activité utilisateur équipes en examinant les graphiques et **les utilisateurs** de **l’activité** .

![Capture d’écran de l’état d’activité utilisateur équipes dans le centre d’administration Office 365 avec légendes numérotées.](media/teams-user-activity-report-with-callouts.png)

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport d’activité utilisateur équipes peut être affiché pour les tendances sur les 7 derniers jours, 30 jours, de 90 jours ou 180 jours. Toutefois, si vous cliquez sur dans une période donnée dans le rapport, le tableau (7) affiche données pendant 30 jours, jusqu'à la date (2) pour lorsque le rapport a été généré. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l’heure de l’activité. |
|**3**   |L’affichage de **l’activité** vous indique le nombre d’activités Microsoft Teams par type d’activité. Les types d’activité sont un nombres de messages de conversation de l’équipe, les messages de conversation privée, les appels et les réunions. |
|**4**   |La vue des **utilisateurs** vous indique le nombre d’utilisateurs par type d’activité. Les types d’activité sont un nombres de messages de conversation de l’équipe, les messages de conversation privée, les appels et les réunions. |
|**5**   |L’axe des X dans les graphiques sont la plage de dates sélectionnée pour le rapport spécifique. <ul><li>Dans le graphique de **l’activité** , l’axe des Y sont le nombre de l’activité spécifiée.</ul></li> <ul><li>Dans le graphique **d’utilisateurs** , l’axe des Y sont le nombre d’utilisateurs de participer à des conversations d’équipes, salles de conversation privées, appels ou réunions.</ul></li> |
|**6**   |You can filter the series you see on the chart by clicking on an item in the legend. Par exemple, dans le graphique de **l’activité** , cliquez sur ou appuyez sur les **messages de canal**, **messages de conversation**, **les appels**ou **réunions** pour afficher uniquement les informations relatives à chacun d’eux. Modification de cette sélection ne change pas les informations contenues dans la table de grille. |
|**7**   |La liste des équipes actives sur le critère de temps de création de rapports (180 jours) plus large.  Le nombre d’activités varient en fonction de la sélection de date. <br><br> Pour afficher les informations suivantes de la table, veillez à qu'ajouter les colonnes à la table. <ul><li>**Nom d’utilisateur** est l’adresse de messagerie de l’utilisateur. Vous pouvez afficher l’adresse de messagerie réelle ou rendre ce champ anonyme.</ul></li> <ul><li>**Dernière activité Date (UTC)** fait référence à la dernière date à laquelle l’utilisateur a participé à une activité Teams Microsoft.</ul></li> <ul><li>**Messages de canal** est le nombre de messages uniques que l’utilisateur est publié dans une conversation de l’équipe au cours de la période spécifiée.</ul></li> <ul><li>**Messages de conversation** est le nombre de messages uniques que l’utilisateur validées privé conversation au cours de la période spécifiée.</ul></li> <ul><li>**Appels** est le nombre d’appels ayant participé à l’utilisateur pendant la période spécifiée.</ul></li> <ul><li>**Réunions** est le nombre de réunions en ligne que l’utilisateur a participé à la période spécifiée.</ul></li> <ul><li>**Autres activités** est le nombre d’autres activités d’équipe par l’utilisateur dont certains sont et non limité à : messages convenance, travailler sur des fichiers, recherche, suivant les équipes et canal et favoriting les applications.</ul></li> <ul><li>**Deleted** indique si l’équipe est supprimé. Si l’équipe est supprimé, mais effectué dans la période de rapport, il apparaîtra dans la grille avec supprimé défini sur true.</ul></li> <ul><li>**Deleted date** est la date à laquelle l’utilisateur a été supprimé.</ul></li> <ul><li>**Produit affecté** est la liste des produits qui sont affectées à l’utilisateur.</ul></li>Si les stratégies de votre organisation vous empêche l’affichage des rapports où les informations utilisateur sont identifiables, vous pouvez modifier le paramètre de confidentialité pour tous ces rapports. Extraire le **comment masquer les détails de niveau utilisateur ?** section dans les [Rapports d’activité dans le centre d’administration Microsoft 365 Preview](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Cliquez ou appuyez sur les **colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**9**   |Cliquez sur ou cliquez sur **Exporter** pour exporter les données de rapport vers un fichier .csv de Excel. Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez trier et filtrer dans la table dans le rapport lui-même. Si vous avez plus de 2 000 utilisateurs, vous devez exporter les données pour filtrer et trier le rapport. 

### <a name="microsoft-teams-device-usage-report"></a>Rapport d’utilisation des périphériques de Microsoft Teams

Le rapport d’utilisation du périphérique équipes fournit des informations sur la façon dont les utilisateurs se connectent aux équipes, y compris les applications mobiles. Le rapport permet d’identifier les périphériques qui sont courants dans votre organisation et combien d’utilisateurs travailler en déplacement.

![Capture d’écran de l’état de l’utilisation des équipes périphérique dans le centre d’administration d’Office 365.](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>Interprétation du rapport d’utilisation du périphérique Microsoft Teams

Vous pouvez obtenir une vue de l’utilisation du périphérique équipes en examinant les graphiques de **Distribution** et **d’utilisateurs** .

![Capture d’écran de l’état de l’utilisation des équipes périphérique dans le centre d’administration Office 365 avec légendes numérotées.](media/teams-device-usage-report-with-callouts.png)

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport de périphérique équipes peut être affiché pour les tendances sur les 7 derniers jours, 30 jours, de 90 jours ou 180 jours. Toutefois, si vous cliquez sur dans une période donnée dans le rapport, le tableau (7) affiche données pendant 30 jours, jusqu'à la date (2) pour lorsque le rapport a été généré. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l’heure de l’activité. |
|**3**   |La vue des **utilisateurs** vous indique le nombre d’utilisateurs quotidiens par type de périphérique. |
|**4**   |L’affichage de la **Distribution** présente du nombre d’utilisateurs par périphérique pendant la période sélectionnée.  |
|**5**   | <ul><li>Dans le graphique **d’utilisateurs** , l’axe des X sont la plage de dates sélectionnée pour le rapport et l’axe des Y sont le nombre d’utilisateurs par type de périphérique.</ul></li> <ul><li>Sur le graphique de la **Distribution** , l’axe des X indique les différents appareils utilisés pour se connecter à des équipes et de l’axe des Y est le nombre d’utilisateurs à l’aide de l’appareil.</ul></li> |
|**6**   |You can filter the series you see on the chart by clicking on an item in the legend. Par exemple, dans le graphique de la **Distribution** , cliquez sur ou appuyez sur **Windows**, **Mac**, **Web**, **iOS**ou **Android** pour afficher uniquement les informations relatives à chacun d’eux. Modification de cette sélection ne change pas les informations contenues dans la table de grille. |
|**7**   |La liste des équipes actives sur le critère de temps de création de rapports (180 jours) plus large.  Le nombre d’activités varient en fonction de la sélection de date. <br><br> Pour afficher les informations suivantes dans le tableau, veillez à qu'ajouter les colonnes à la table. <ul><li>**Nom d’utilisateur** est l’adresse de messagerie de l’utilisateur. Vous pouvez afficher l’adresse de messagerie réelle ou rendre ce champ anonyme.</ul></li> <ul><li>**Dernière activité Date (UTC)** fait référence à la dernière date à laquelle l’utilisateur a participé à une activité équipes.</ul></li> <ul><li>**Deleted** indique si l’équipe est supprimé. Si l’équipe est supprimé, mais effectué dans la période de rapport, il apparaîtra dans la grille avec supprimé défini sur true.</ul></li><ul><li>**Deleted date** est la date à laquelle l’utilisateur a été supprimé.</ul></li> <ul><li>**Windows** est activée si l’utilisateur a été actif dans le client de bureau équipes sur un ordinateur fonctionnant sous Windows.</ul></li> <ul><li>**Mac** est sélectionnée si l’utilisateur a été actif dans le client de bureau équipes sur un ordinateur Mac OS.</ul></li>  <ul><li>**Web** est sélectionnée si l’utilisateur a été actif sur le client web équipes.</ul></li> <ul><li>**iOS** est activée si l’utilisateur a été actif sur le client mobile équipes pour iOS.</ul></li> <ul><li>**Téléphone Android** est activée si l’utilisateur a été actif sur le client mobile équipes pour Android.</ul></li></li> <ui>Si les stratégies de votre organisation vous empêche l’affichage des rapports où les informations utilisateur sont identifiables, vous pouvez modifier le paramètre de confidentialité pour tous ces rapports. Extraire le **comment masquer les détails de niveau utilisateur ?** section dans les [Rapports d’activité dans le centre d’administration Microsoft 365 Preview](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |Cliquez ou appuyez sur les **colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**9**   |Cliquez sur ou cliquez sur **Exporter** pour exporter les données de rapport vers un fichier .csv de Excel. Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez trier et filtrer dans la table dans le rapport lui-même. Si vous avez plus de 2 000 utilisateurs, vous devez exporter les données pour filtrer et trier le rapport. 

## <a name="who-can-access-the-teams-activity-reports"></a>Personnes autorisées à accéder les rapports d’activité équipes

Les rapports d’activité est accessible par les utilisateurs qui sont affectés :

- Rôle d’administrateur global Office 365
- Rôle d’administration spécifiques au produit (Exchange, Skype pour les professionnels ou SharePoint)
- Rôle de lecteur de rapports

### <a name="reports-reader-role"></a>Rôle de lecteur de rapports

Vous pouvez attribuer le rôle de *lecteur de rapports* au personnel non informatique qui souhaitent avoir accès à ces rapports. En attribuant ce rôle aux responsables de formation ou les parties prenantes métier, il se peut que vous pouvez vous assurer qu’ils ont accès les analyses sont utiles à l’adoption de lecteur et le suivi des équipes.

## <a name="other-information-on-the-reports-dashboard"></a>Autres informations sur le tableau de bord des rapports

### <a name="at-a-glance-activity-widget"></a>Widget d’activité d’un coup de œil

Le tableau de bord rapports comprend les données d’utilisation des équipes dans le widget d’activité d’un coup de œil, qui vous donne une vue entre les produits aux utilisateurs comment communiquent et collaborent à l’aide de divers autres services dans Office 365.

![Capture d’écran du widget équipes activité d’un coup de œil sur le tableau de bord des rapports.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Carte d’activité équipes

La carte d’activité équipes sur le tableau de bord rapports vous donne une vue d’ensemble de l’activité dans les équipes, y compris le nombre d’utilisateurs actifs, afin que vous pouvez comprendre rapidement combien d’utilisateurs d’utilisation du service. Cliquez sur la carte d’activité sur le tableau de bord permet d’atteindre le rapport d’activité utilisateur équipes. 

![Capture d’écran de la carte d’activité équipes sur le tableau de bord des rapports.](media/teams-activity-card.png)
