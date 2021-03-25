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
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser les rapports d’activité pour voir comment les utilisateurs de votre organisation utilisent Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9c975bf4a3f2253dbc99230f85b48a9ae9cd0d65
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107190"
---
<a name="use-activity-reports-for-microsoft-teams"></a>Rapports d’activité de l’utilisateur Microsoft Teams 
========================================

Vous pouvez utiliser les rapports d’activité du Centre d’administration Microsoft 365 pour voir comment les utilisateurs de votre organisation utilisent Microsoft Teams. Par exemple, si certains n’utilisent pas encore Microsoft Teams, ils ne savent pas encore comment démarrer ou comprendre comment ils peuvent utiliser Teams pour être plus productifs et collaboratifs. Votre organisation peut utiliser les rapports d’activité pour choisir où hiérarchiser les efforts de formation et de communication.

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>Afficher les rapports Teams dans le tableau de bord Rapports

1. Dans le [Centre d’administration Microsoft 365,](https://portal.office.com/adminportal/home)sélectionnez **Utilisation des**  >  **rapports.**
 
2. Sur la page **Utilisation,** **sélectionnez** Sélectionner un rapport, puis sous **Microsoft Teams** dans la liste des rapports, sélectionnez le rapport que vous voulez afficher.

## <a name="teams-activity-reports-that-are-available"></a>Rapports d’activité Teams disponibles

Vous pouvez afficher deux rapports d’activité :

- [Rapport d’activité des utilisateurs de Microsoft Teams](#microsoft-teams-user-activity-report) 
- [Rapport d’utilisation des périphériques de Microsoft Teams](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Rapport d’activité des utilisateurs de Microsoft Teams

Le rapport Activité de l’utilisateur sur Teams vous donne un affichage des activités les plus courantes que vos utilisateurs effectuent dans Teams. Cela inclut le nombre de personnes qui participent à une conversation dans un canal, combien communiquent par le biais d’un message de conversation privée et combien participent à des appels ou des réunions. Vous pouvez voir ces informations pour l’ensemble de votre organisation et pour chaque utilisateur individuel.

![Rapport d’activité de l’utilisateur dans le Centre d’administration](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpréter le rapport Activité de l’utilisateur sur Microsoft Teams

Vous pouvez visualiser l’activité des utilisateurs de Teams en regardant les graphiques **Activité** **et Utilisateurs.**

![Capture d’écran du rapport d’activité de l’utilisateur avec des appels numéroés.](media/teams-user-activity-report-with-callouts.png)

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport Activité de l’utilisateur sur Teams permet d’afficher les tendances des 7, 30, 90 ou 180 derniers jours. Toutefois, si vous cliquez sur un plage de temps spécifique dans le rapport, le tableau (7) affiche les données sur 30 jours, jusqu’à la date (2) à laquelle le rapport a été généré. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l’heure de l’activité. |
|**3**   |**L’affichage** Activité indique le nombre d’activités sur Microsoft Teams par type d’activité. Les types d’activités sont le nombre de messages de conversation d’équipe, de messages de conversation privée, d’appels et de réunions. |
|**4**   |**L’affichage** Utilisateurs indique le nombre d’utilisateurs par type d’activité. Les types d’activités sont le nombre de messages de conversation d’équipe, de messages de conversation privée, d’appels et de réunions. |
|**5**   |L’axe X sur les graphiques est la plage de dates sélectionnée pour le rapport spécifique. <ul><li>Dans le **graphique Activité,** l’axe Y indique le nombre d’activités spécifiées.</ul></li> <ul><li>Dans le graphique **Utilisateurs,** l’axe Y indique le nombre d’utilisateurs participant aux conversations d’équipe, aux conversations privées, aux appels ou aux réunions.</ul></li> |
|**6**   |You can filter the series you see on the chart by clicking on an item in the legend. Par exemple,  dans le graphique Activité, cliquez ou appuyez sur **Messages** de canal, **Messages** de conversation, **Appels** ou Réunions pour voir uniquement les informations **liées** à chacun d’eux. La modification de cette sélection ne modifie pas les informations du tableau grille. |
|**7**   |Liste des équipes actives dans l’ensemble de la période de rapport la plus large (180 jours).  Le nombre d’activités varie en fonction de la date de sélection. <br><br> Pour voir les informations suivantes dans le tableau, veillez à y ajouter les colonnes. <ul><li>**Nom d’utilisateur** est l’adresse de courrier de l’utilisateur. Vous pouvez afficher l’adresse de messagerie réelle ou rendre ce champ anonyme.</ul></li> <ul><li>**La date de la dernière activité (UTC)** fait référence à la dernière date à laquelle l’utilisateur a participé à une activité Microsoft Teams.</ul></li> <ul><li>**Les messages de** canal sont le nombre de messages uniques que l’utilisateur a publié dans une conversation d’équipe pendant la période spécifiée.</ul></li> <ul><li>**Les messages de** conversation sont le nombre de messages uniques que l’utilisateur a publié dans une conversation privée pendant la période spécifiée.</ul></li> <ul><li>**Les** appels sont le nombre d’appels que l’utilisateur a participé pendant la période spécifiée.</ul></li> <ul><li>**Les réunions** sont le nombre de réunions en ligne à qui l’utilisateur a participé pendant la période spécifiée.</ul></li> <ul><li>**Une** autre activité est le nombre d’autres activités d’équipe, dont certaines incluent, et non limitées à : aimer des messages, des applications, travailler sur des fichiers, rechercher, suivre des équipes et des canaux et les favoriter.</ul></li> <ul><li>**La suppression** indique si l’équipe est supprimée. Si l’équipe est supprimée mais qu’elle a connu une activité dans la période du rapport, elle s’affiche dans la grille avec la valeur Supprimé définie sur true.</ul></li> <ul><li>**La date de suppression** est la date à laquelle l’utilisateur a été supprimé.</ul></li> <ul><li>**Le produit attribué** est la liste des produits attribués à l’utilisateur.</ul></li>Si la politique de votre organisation vous empêche de consulter les rapports sur lequel sont identifiables les informations des utilisateurs, vous pouvez modifier les paramètres de confidentialité de tous ces rapports. Consultez la section **Comment puis-je** masquer les détails du niveau de l’utilisateur ? dans la prévisualisation des rapports d’activité du [Centre d’administration Microsoft 365.](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)</ui> |
|**8**   |Cliquez ou appuyez **sur Colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**9**   |Cliquez ou **appuyez sur Exporter** pour exporter des données de rapport vers un fichier .csv Excel. Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez trier et filtrer dans le tableau, au sein du rapport proprement dit. Si vous avez plus de 2 000 utilisateurs, vous devez exporter les données pour filtrer et trier le rapport. 

### <a name="microsoft-teams-device-usage-report"></a>Rapport d’utilisation des périphériques de Microsoft Teams

Le rapport Utilisation de Teams sur les appareils vous fournit des informations sur la connexion de vos utilisateurs à Teams, y compris les applications mobiles. Le rapport vous permet de comprendre les appareils les plus utilisés dans votre organisation et le nombre d’utilisateurs qui travaillent en cours.

![Capture d’écran du rapport d’utilisation de Teams sur des appareils.](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>Interpréter le rapport Utilisation de Microsoft Teams sur des appareils

Vous pouvez obtenir un affichage de l’utilisation de Teams sur des appareils en regardant les graphiques **Utilisateurs** **et Distribution.**

![Capture d’écran du rapport d’utilisation de Teams sur les appareils avec des appels numéroés.](media/teams-device-usage-report-with-callouts.png)

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport Teams sur les appareils peut être vu pour les tendances des 7, 30, 90 ou 180 derniers jours. Toutefois, si vous cliquez sur un plage de temps spécifique dans le rapport, le tableau (7) affiche les données sur 30 jours, jusqu’à la date (2) à laquelle le rapport a été généré. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l’heure de l’activité. |
|**3**   |**L’affichage** Utilisateurs indique le nombre d’utilisateurs quotidiens par type d’appareil. |
|**4**   |**L’affichage** Distribution indique le nombre d’utilisateurs par appareil sur la période sélectionnée.  |
|**5**   | <ul><li>Dans le **graphique Utilisateurs,** l’axe X indique la plage de dates sélectionnée pour le rapport, et l’axe Y le nombre d’utilisateurs par type d’appareil.</ul></li> <ul><li>Sur le graphique **de distribution,** l’axe X indique les différents appareils utilisés pour se connecter à Teams, et l’axe Y représente le nombre d’utilisateurs utilisant l’appareil.</ul></li> |
|**6**   |You can filter the series you see on the chart by clicking on an item in the legend. Par exemple, dans le graphique **Distribution,** cliquez ou appuyez sur **Windows,** **Mac,** **Linux,** **Web,** **iOS** ou **Android** pour voir uniquement les informations relatives à chacune de ces séries. La modification de cette sélection ne modifie pas les informations du tableau grille. |
|**7**   |Liste des équipes actives dans l’ensemble de la période de rapport la plus large (180 jours).  Le nombre d’activités varie en fonction de la date de sélection. <br><br> Pour voir les informations suivantes dans le tableau, veillez à y ajouter les colonnes. <ul><li>**Nom d’utilisateur** est l’adresse de courrier de l’utilisateur. Vous pouvez afficher l’adresse de messagerie réelle ou rendre ce champ anonyme.</ul></li> <ul><li>**La date de la dernière activité (UTC)** fait référence à la dernière date à laquelle l’utilisateur a participé à une activité Teams.</ul></li> <ul><li>**La suppression** indique si l’équipe est supprimée. Si l’équipe est supprimée mais qu’elle a connu une activité dans la période du rapport, elle s’affiche dans la grille avec la valeur Supprimé définie sur true.</ul></li><ul><li>**La date de suppression** est la date à laquelle l’utilisateur a été supprimé.</ul></li> <ul><li>**Windows**  est sélectionné si l’utilisateur a été actif dans le client de bureau Teams sur un ordinateur Windows.</ul></li> <ul><li>**Mac** est sélectionné si l’utilisateur a été actif dans le client de bureau Teams sur un ordinateur macOS.</ul></li>  <ul><li>**Linux** est sélectionné si l’utilisateur a été actif dans le client de bureau Teams sur un ordinateur Linux.</ul></li>   <ul><li>**L’application Web** est sélectionnée si l’utilisateur a été actif sur le client web Teams.</ul></li> <ul><li>**iOS** est sélectionné si l’utilisateur était actif sur le client mobile Teams pour iOS.</ul></li> <ul><li>**Le téléphone Android**  est sélectionné si l’utilisateur a été actif sur le client mobile Teams pour Android.</ul></li></li> <ui>Si la politique de votre organisation vous empêche de consulter les rapports sur lequel sont identifiables les informations des utilisateurs, vous pouvez modifier les paramètres de confidentialité de tous ces rapports. Consultez la section **Comment puis-je** masquer les détails du niveau de l’utilisateur ? dans la prévisualisation des rapports d’activité du [Centre d’administration Microsoft 365.](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)</ui> |
|**8**   |Cliquez ou appuyez **sur Colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**9**   |Cliquez ou **appuyez sur Exporter** pour exporter des données de rapport vers un fichier .csv Excel. Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez trier et filtrer dans le tableau, au sein du rapport proprement dit. Si vous avez plus de 2 000 utilisateurs, vous devez exporter les données pour filtrer et trier le rapport. 

## <a name="who-can-access-the-teams-activity-reports"></a>Qui peut accéder aux rapports d’activité De Teams ?

Les rapports d’activité sont accessibles par les utilisateurs affectés :

- Rôle d’administrateur global
- Rôle d’administrateur spécifique au produit (Exchange, Skype Entreprise ou SharePoint)
- Rôle de lecteur de rapports

### <a name="reports-reader-role"></a>Rôle de lecteur de rapports

Vous pouvez attribuer le rôle de lecteur de rapports à des personnes qui n’ont pas les droits d’administrateur mais qui sont responsables de la conduite de l’adoption ou du suivi de l’utilisation des licences teams. Pour savoir comment attribuer des rôles, lisez Attribuer des rôles d’administrateur et non administrateur aux utilisateurs [qui utilisent Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="other-information-on-the-reports-dashboard"></a>Autres informations dans le tableau de bord Rapports

### <a name="at-a-glance-activity-widget"></a>Widget d’activité en un clin d’œil

Le tableau de bord Rapports inclut les données d’utilisation de Teams dans le widget d’activité en un clin d’œil, qui vous donne une vue d’ensemble des produits dont les utilisateurs communiquent et collaborent à l’aide des autres services dans Microsoft 365 ou Office 365.

![Capture d’écran du widget d’activité Teams en un clin d’œil.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Carte d’activité Teams

La carte d’activité Teams sur le tableau de bord Rapports vous donne une vue d’ensemble de l’activité dans Teams, y compris le nombre d’utilisateurs actifs, afin que vous pouvez rapidement comprendre combien d’utilisateurs utilisent le service. Le fait de cliquer sur la carte d’activité sur le tableau de bord vous permet d’aller au rapport d’activité de l’utilisateur sur Teams. 

![Capture d’écran de la carte d’activité Teams.](media/teams-activity-card.png)