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
description: Découvrez comment utiliser les rapports d’activité pour déterminer la façon dont les utilisateurs de votre organisation utilisent Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 85184f1de59338282ddd676009f000794b1b4b07
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548676"
---
<a name="use-activity-reports-for-microsoft-teams"></a>Rapports d’activité de l’utilisateur Microsoft Teams 
========================================

Vous pouvez utiliser des rapports d’activité dans le centre d’administration Microsoft 365 pour déterminer la façon dont les utilisateurs de votre organisation utilisent Microsoft Teams. Par exemple, si vous n’êtes pas encore en mesure d’utiliser Microsoft Teams, il est possible qu’il n’ait pas pu commencer ou comprendre la manière dont ils peuvent utiliser teams pour être plus productifs et collaborer. Votre organisation peut utiliser les rapports d’activité pour choisir où hiérarchiser les efforts de formation et de communication.

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>Comment afficher les rapports d’équipes dans le tableau de bord rapports?

1. Dans le [Centre d’administration Microsoft 365](https://portal.office.com/adminportal/home), sélectionnez**utilisation**des **rapports** > .
 
2. Sur la page **utilisation** , sélectionnez **Sélectionner un rapport**, puis sous **Microsoft teams** dans la liste des États, sélectionnez le rapport que vous souhaitez consulter.

## <a name="teams-activity-reports-that-are-available"></a>Rapports d’activité d’équipes disponibles

Deux rapports d’activité peuvent actuellement s’afficher:

- [Rapport d’activité des utilisateurs de Microsoft Teams](#microsoft-teams-user-activity-report) 
- [Rapport d’utilisation des périphériques de Microsoft Teams](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Rapport d’activité des utilisateurs de Microsoft Teams

Le rapport activité de l’utilisateur sur teams vous permet d’afficher les activités les plus fréquemment effectuées par les utilisateurs dans Teams. Cela comprend le nombre de personnes qui participent à une conversation dans un canal, le nombre de communications par message privé et le nombre de participants à des appels ou des réunions. Vous pouvez consulter ces informations pour l’ensemble de votre organisation, ainsi que pour chaque utilisateur individuel.

![Capture d’écran du rapport activité de l’utilisateur dans le centre d’administration Office 365.](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpréter le rapport activité de l’utilisateur sur Microsoft teams

Vous pouvez obtenir un aperçu de l’activité des utilisateurs dans teams en consultant les graphiques **activité** et **utilisateurs** .

![Capture d’écran du rapport d’activité de l’utilisateur avec des légendes numérotées.](media/teams-user-activity-report-with-callouts.png)

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport activité de l’utilisateur sur teams peut être consulté pour les tendances au cours des 7, 30, 90 ou 180 jours qui suivent. Toutefois, si vous cliquez sur une plage de dates spécifique dans le rapport, le tableau (7) affiche les données pendant 30 jours, jusqu’à la date (2) pour le moment de la génération de l’État. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l’heure de l’activité. |
|**3**   |La vue **activité** indique le nombre d’activités de Microsoft teams par type d’activité. Les types d’activité sont le nombre de messages de discussion d’équipe, de messages de conversation privée, d’appels et de réunions. |
|**4**   |L’affichage **utilisateurs** indique le nombre d’utilisateurs par type d’activité. Les types d’activité sont le nombre de messages de discussion d’équipe, de messages de conversation privée, d’appels et de réunions. |
|**5**   |L’axe X sur les graphiques représente la plage de dates sélectionnée pour ce rapport particulier. <ul><li>Sur le graphique **activité** , l’axe Y indique le nombre d’activités spécifiées.</ul></li> <ul><li>Sur le graphique **utilisateurs** , l’axe Y indique le nombre d’utilisateurs participant aux conversations d’équipe, aux conversations privées, aux appels ou aux réunions.</ul></li> |
|**6**   |You can filter the series you see on the chart by clicking on an item in the legend. Par exemple, dans le graphique **activité** , cliquez ou appuyez sur **messages de canal**, messages de **conversation**, **appels**ou **réunions** pour afficher uniquement les informations relatives à chacune d’elles. La modification de cette sélection ne modifie pas les informations du tableau grille. |
|**7**   |La liste des équipes actives dans le cadre de la création de rapports dans le monde (180-jour).  Le nombre d’activités varie en fonction de la date de sélection. <br><br> Pour afficher les informations suivantes dans le tableau, assurez-vous d’ajouter les colonnes à la table. <ul><li>**Nom** d’utilisateur est l’adresse de messagerie de l’utilisateur. Vous pouvez afficher l’adresse de messagerie réelle ou rendre ce champ anonyme.</ul></li> <ul><li>**Date de la dernière activité (UTC)** indique la dernière date à laquelle l’utilisateur a participé à une activité sur Microsoft Teams.</ul></li> <ul><li>**Messages de canal** indique le nombre de messages uniques que l’utilisateur a publié dans une conversation d’équipe pendant la période spécifiée.</ul></li> <ul><li>**Messages de conversation** indique le nombre de messages uniques que l’utilisateur a publié dans une conversation privée pendant la période spécifiée.</ul></li> <ul><li>**Appels** indique le nombre d’appels auxquels l’utilisateur a participé pendant la période spécifiée.</ul></li> <ul><li>**Réunions** indique le nombre de réunions en ligne auxquelles l’utilisateur a participé pendant la période spécifiée.</ul></li> <ul><li>**Autres activités** indique le nombre d’autres activités d’équipe effectuées par l’utilisateur, dont certaines sont notamment les suivantes: les messages, les applications, les fichiers, les recherches, les équipes et les ajouter aux favoris.</ul></li> <ul><li>**Supprimé** indique que l’équipe est supprimée. Si l’équipe a été supprimée, mais qu’il y avait une activité au cours de la période du rapport, elle apparaîtra dans la grille avec suppression définie sur true.</ul></li> <ul><li>La **Date de suppression** correspond à la date à laquelle l’utilisateur a été supprimé.</ul></li> <ul><li>**Produit attribué** indique la liste des produits attribués à l’utilisateur.</ul></li>Si les stratégies de votre organisation vous empêchent d’afficher des rapports dans lesquels les informations utilisateur sont identifiables, vous pouvez modifier le paramètre de confidentialité pour tous ces rapports. Consultez la section **comment masquer les détails au niveau utilisateur?** dans les [rapports d’activité dans la version preview du centre d’administration Microsoft 365](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**version8**   |Cliquez ou appuyez sur **colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**09**   |Pour exporter les données du rapport vers un fichier Excel. csv, cliquez ou appuyez sur **Exporter** . Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez les trier et les filtrer dans le tableau. Si vous avez plus d’utilisateurs 2 000, vous devrez exporter les données pour filtrer et trier le rapport. 

### <a name="microsoft-teams-device-usage-report"></a>Rapport d’utilisation des périphériques de Microsoft Teams

Le rapport utilisation des appareils teams fournit des informations sur la façon dont vos utilisateurs se connectent à Teams, y compris les applications mobiles. Ce rapport vous aide à comprendre quels appareils sont populaires au sein de votre organisation et combien d’utilisateurs travaillent lors de vos tâches.

![Capture d’écran du rapport d’utilisation de l’appareil Teams.](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>Interpréter le rapport utilisation de Microsoft teams sur les appareils

Vous pouvez obtenir un aperçu de l’utilisation des appareils teams en consultant les graphiques **utilisateurs** et **distribution** .

![Capture d’écran du rapport sur l’utilisation d’un appareil teams avec des légendes numérotées.](media/teams-device-usage-report-with-callouts.png)

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport sur les appareils teams peut être consulté pour les tendances au cours des 7, 30, 90 ou 180 jours qui suivent. Toutefois, si vous cliquez sur une plage de dates spécifique dans le rapport, le tableau (7) affiche les données pendant 30 jours, jusqu’à la date (2) pour le moment de la génération de l’État. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l’heure de l’activité. |
|**3**   |L’affichage **utilisateurs** indique le nombre d’utilisateurs quotidiens par type d’appareil. |
|**4**   |L’affichage **distribution** indique le nombre d’utilisateurs par appareil sur la période sélectionnée.  |
|**5**   | <ul><li>Sur le graphique **utilisateurs** , l’axe X représente la plage de dates sélectionnée pour le rapport et l’axe Y représente le nombre d’utilisateurs par type d’appareil.</ul></li> <ul><li>Sur le graphique **distribution** , l’axe X montre les différents appareils utilisés pour se connecter aux équipes et l’axe Y indique le nombre d’utilisateurs de l’appareil.</ul></li> |
|**6**   |You can filter the series you see on the chart by clicking on an item in the legend. Par exemple, dans le **graphique distribution** , cliquez ou appuyez sur **Windows**, **Mac**, **Web**, **iOS**ou **Android** pour afficher uniquement les informations relatives à chacun d’eux. La modification de cette sélection ne modifie pas les informations du tableau grille. |
|**7**   |La liste des équipes actives dans le cadre de la création de rapports dans le monde (180-jour).  Le nombre d’activités varie en fonction de la date de sélection. <br><br> Pour afficher les informations suivantes dans le tableau, assurez-vous d’ajouter les colonnes à la table. <ul><li>**Nom** d’utilisateur est l’adresse de messagerie de l’utilisateur. Vous pouvez afficher l’adresse de messagerie réelle ou rendre ce champ anonyme.</ul></li> <ul><li>**Date de la dernière activité (UTC)** indique la dernière date à laquelle l’utilisateur a participé à une activité d’équipe.</ul></li> <ul><li>**Supprimé** indique que l’équipe est supprimée. Si l’équipe a été supprimée, mais qu’il y avait une activité au cours de la période du rapport, elle apparaîtra dans la grille avec suppression définie sur true.</ul></li><ul><li>La **Date de suppression** correspond à la date à laquelle l’utilisateur a été supprimé.</ul></li> <ul><li>**Windows** est sélectionné si l’utilisateur a été actif dans le client de bureau teams sur un ordinateur exécutant Windows.</ul></li> <ul><li>L’option **Mac** est activée si l’utilisateur a été actif dans le client de bureau teams sur un ordinateur MacOS.</ul></li>  <ul><li>L’option **Web** est activée si l’utilisateur a été actif sur le client Web Teams.</ul></li> <ul><li>**iOS** est sélectionné si l’utilisateur a été actif dans le client mobile teams pour iOS.</ul></li> <ul><li>Le **téléphone Android** est sélectionné si l’utilisateur a été actif sur le client mobile teams pour Android.</ul></li></li> <ui>Si les stratégies de votre organisation vous empêchent d’afficher des rapports dans lesquels les informations utilisateur sont identifiables, vous pouvez modifier le paramètre de confidentialité pour tous ces rapports. Consultez la section **comment masquer les détails au niveau utilisateur?** dans les [rapports d’activité dans la version preview du centre d’administration Microsoft 365](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**version8**   |Cliquez ou appuyez sur **colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**09**   |Pour exporter les données du rapport vers un fichier Excel. csv, cliquez ou appuyez sur **Exporter** . Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez les trier et les filtrer dans le tableau. Si vous avez plus d’utilisateurs 2 000, vous devrez exporter les données pour filtrer et trier le rapport. 

## <a name="who-can-access-the-teams-activity-reports"></a>Qui peut accéder aux rapports d’activité de teams?

Les rapports d’activité sont accessibles aux utilisateurs assignés:

- Rôle d’administrateur général Office 365
- Rôle d’administrateur spécifique au produit (Exchange, Skype entreprise ou SharePoint)
- Rôle du lecteur de rapports

### <a name="reports-reader-role"></a>Rôle du lecteur de rapports

Vous pouvez affecter le rôle de *lecteur rapports* aux personnes qui ne sont pas du personnel informatique pour lesquelles vous souhaitez avoir accès à ces rapports. En attribuant ce rôle aux responsables de formations ou aux parties prenantes de l’entreprise, vous pouvez veiller à ce qu’ils aient accès aux informations utiles pour piloter et effectuer le suivi de l’adoption d’équipes.

## <a name="other-information-on-the-reports-dashboard"></a>Autres informations dans le tableau de bord rapports

### <a name="at-a-glance-activity-widget"></a>Widget d’activité en un clin d’œil

Le tableau de bord rapports inclut les données d’utilisation d’équipes dans le widget activité d’un coup d’œil, qui vous permettent d’obtenir une vue d’ensemble illustrant la manière dont les utilisateurs communiquent et collaborent à l’aide des autres services dans Office 365.

![Capture d’écran du widget activités d’une équipe en un clin d’œil.](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Carte d’activité de teams

La carte d’activité équipes dans le tableau de bord rapports vous donne un aperçu de l’activité dans Teams, y compris le nombre d’utilisateurs actifs, afin que vous puissiez rapidement comprendre le nombre d’utilisateurs actifs par le service. Le fait de cliquer sur la carte d’activité dans le tableau de bord vous permet d’accéder au rapport d’activité de l’utilisateur sur Teams. 

![Capture d’écran de la carte d’activité de teams.](media/teams-activity-card.png)
