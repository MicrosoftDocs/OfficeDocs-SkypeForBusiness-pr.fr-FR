---
title: Rapport d'activités
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 8cbe2eb2-1194-4fd7-b1ee-9f9287c82424
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- O365E_ReportsS4BActivity
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: f50b8c03304a308594fd7bd920ee92e8d38a1f43
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2020
ms.locfileid: "44205555"
---
# <a name="activity-report"></a>Rapport d'activités

Le **tableau de** bord Rapports vous offre une vue d’ensemble de l’activité sur les produits Microsoft 365 ou Office 365 au sein de votre organisation. Il vous permet d’aller plus avant dans les rapports individuels au niveau des produits afin d’offrir des informations plus granulaires sur les activités au sein de chaque produit. Par exemple, vous pouvez utiliser le rapport d’activité **Skype** Entreprise pour voir combien de fois vos utilisateurs utilisent des sessions d’égal à égal ou de conférences organisées, ou combien ils participent à des sessions de conférence. 

Pour en savoir [plus, consultez la](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) vue d’ensemble des rapports.
  
Tout comme les autres rapports Skype Entreprise, ce rapport vous fournit les détails des activités au sein de votre organisation. Ces informations détaillées sont très utiles pour analyser, planifier et prendre des décisions pour votre entreprise.
  
> [!NOTE]
> Tous les rapports Skype Entreprise sont consultez lorsque vous vous connectez en tant qu’administrateur dans le Centre d’administration Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>Comment obtenir le rapport d'activité Skype Entreprise

1. Allez au Centre d’administration pour **>'utilisation**  >  **des rapports.**
    
2. Sur la page **Utilisation,** sélectionnez **Activité Skype** Entreprise dans la liste Sélectionner un rapport sur la gauche ou cliquez sur le widget  >   **d’activité Skype** Entreprise. 

  
## <a name="interpret-the-skype-for-business-activity-report"></a>Interpréter le rapport d'activité Skype Entreprise

Vous pouvez visualiser l'activité Skype Entreprise d'un utilisateur à l'aide des graphiques **Activité** et **Utilisateurs**.
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>
Le **rapport Activité de**  la messagerie Skype Entreprise permet d’afficher les tendances des 7, 30, 90 ou 180 derniers jours. Toutefois, si vous cliquez sur un jour en particulier dans le rapport, la table (voir le numéro 7) affiche les données pendant 28 jours au-dessus de la date actuelle (et non la date à laquelle le rapport a été généré).

> [!NOTE]
> Si vous cliquez sur les détails d’un jour spécifique, le tableau affiche uniquement les données des 30 jours jusqu’à la date à laquelle le rapport a été généré.

***
![Numéro 2](../images/sfbcallout2.png)<br/>
Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport à l’heure de l’activité. 
***
![Nombre 3](../images/sfbcallout3.png)<br/>Utilisez les données du graphique interactif **Activité** pour comprendre les tendances d'utilisation et visualiser le nombre total d'activités de conférence actuellement tenues dans votre organisation. Cela vous indiquera le nombre et les types d' **organisations**, de **participations** et de sessions de conférence d' **égal à égal** sein de votre organisation.  
***
![Numéro 4](../images/sfbcallout4.png)<br/>
Use the interactive chart data on the **Users** chart to understand usage trends and to see the number of unique users that are participating in conference activities that are being held in your organization. Cela vous indique le nombre total d’utilisateurs ainsi que les types de  sessions d’égal à **égal,** de participations et de **sessions** d’égal à égal de conférences.
***
!["Nombre 5"](../images/sfbcallout5.png)<br/>
You can filter the series you see on the chart by clicking on an item in the legend. Par exemple,  dans le graphique Activité, cliquez ou appuyez sur  Sessions d’égal à **égal,** Organisées ou **Participations** pour voir uniquement les informations relatives à chacune de ces activités. Changing this selection doesn't change the info in the grid table. 
***
![Numéro 6](../images/sfbcallout6.png)<br/>
Chaque graphique a un axe « X » (horizontal) et « Y » (vertical).
*    Dans le graphique **Activité,** l’axe Y indique le nombre total d’égal à égal, d’organisation et de participations à des sessions de conférence qui se sont tenues.
*    Dans le graphique **d’activité** utilisateurs, l’axe Y indique le nombre d’utilisateurs uniques participant à chaque type d’égal à égal de conférence, organisé et participant à une conférence.

L'axe X sur les deux graphiques représente la plage de dates sélectionnée pour ce rapport particulier. 
***
![Numéro 7](../images/sfbcallout7.png)<br/>
Le tableau présente une répartition par utilisateur de toutes les activités de conférence. Il vous indique tous les utilisateurs à qui Skype Entreprise a été affecté ainsi que leurs activités de conférence. Vous pouvez ajouter des colonnes supplémentaires au tableau.
* **Nom d’utilisateur** est le nom de l’utilisateur.
* **Supprimé** indique que la licence de l'utilisateur a été supprimée.<br/><br/>
  > [!NOTE]
  > L’activité d’un utilisateur supprimé continue à s’afficher dans un rapport si cet utilisateur a été titulaire d’une licence à un moment ou à un autre pendant la période sélectionnée. La colonne **Supprimé** vous permet d'observer que l'utilisateur n'est peut-être plus actif, mais a contribué aux données du rapport.
     
* La **date de suppression** correspond à la date à laquelle la licence de l'utilisateur a été supprimée.
* **Dernière date d'activité (UTC)** représente la dernière fois que l'utilisateur a participé à une session d'égal à égal, a organisé une conférence ou a participé à une conférence.
* **Une session d’égal** à égal indique le nombre total de sessions de conférence d’égal à égal utilisées par l’utilisateur.
* **Conférences organisées** indique le nombre total de conférences organisées par cet utilisateur.
* **Participations-à des conférences** indique le nombre total de conférences auxquelles l'utilisateur a participé.
* **Le produit affecté** est celui des produits Microsoft 365 ou Office 365 attribués à cet utilisateur.<br/>

Si la politique de votre organisation vous empêche de consulter les rapports sur lequel sont identifiables les informations des utilisateurs, vous pouvez modifier les paramètres de confidentialité de tous ces rapports. Consultez la **section Masquer les détails de l’utilisateur dans** la section Rapports du Centre [d’administration.](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
***
![Numéro 8](../images/sfbcallout8.png)<br/>
Cliquez ou appuyez sur **l’icône** Colonnes dans l’une des colonnes pour ajouter ou supprimer des colonnes dans le rapport.           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![Numéro 9](../images/sfbcallout9.png)<br/>
Vous pouvez également exporter les données du rapport vers un fichier Excel .csv, en cliquant ou en appuyant sur **Exporter**.           <br/> ![Bouton d’exportation des rapports Skype Entreprise.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez trier et filtrer dans le tableau, au sein du rapport proprement dit. Si vous avez plus de 2 000 utilisateurs, vous devrez exporter les données pour pouvoir les trier et les filtrer. 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Autres rapports d'activité Skype Entreprise

- [Rapport d’utilisation de Skype Entreprise sur des appareils](device-usage-report.md) Vous pouvez voir les appareils, y compris les systèmes d’exploitation Windows et les appareils mobiles, sur lesquels l’application Skype Entreprise est installée et qui l’utilisent pour la messagerie instantanée et les réunions.
    
- [Rapport d’activité d’organisateur de conférences Skype Entreprise](conference-organizer-activity-report.md) Vous pouvez voir combien de fois vos utilisateurs organisent des conférences qui utilisent la messagerie instantanée, l’audio/la vidéo, le partage d’application, le web, la conférence rendez-vous ou la mise en conférence tierce et la mise en conférence/mise en conférence - Microsoft.
    
- [Rapport d’activité P2 P2L Skype Entreprise](peer-to-peer-activity-report.md) Vous pouvez voir le nombre d’utilisation de la messagerie instantanée, de l’audio/la vidéo, du partage d’application et du transfert de fichiers par utilisateur.
    
- [Rapport de blocage d’utilisateurs Skype Entreprise](users-blocked-report.md) Vous pouvez voir les utilisateurs de votre organisation qui ont été bloqués et ne peuvent plus effectuer d’appels PSTN.
    
- [Rapport d’utilisation PSTN de Skype Entreprise](pstn-usage-report.md) Vous pouvez voir le nombre de minutes passées pour des appels entrants/sortants, ainsi que les coûts de ces appels.

- Le rapport sur les pools de [minutes PSTN Skype](pstn-minute-pools-report.md) Entreprise vous permet de consulter le nombre de minutes consommées au cours du mois en cours au sein de votre organisation.

- [Rapport des détails de la session Skype Entreprise](session-details-report.md) Vous pouvez voir des détails sur les expériences d’appels d’un utilisateur individuel.

    
## <a name="related-topics"></a>Sujets associés
[Rapports d’activité dans le Centre d’administration](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
