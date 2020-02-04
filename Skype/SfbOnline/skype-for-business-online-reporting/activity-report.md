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
- O365E_ReportsS4BActivity
ms.custom:
- Reporting
description: 'Learn how to get the Skype for Business Activity reports, what it contains, and how to interpret the data. '
ms.openlocfilehash: 1da7ea7b826d5a8f86691cda8b41b49298114d50
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692449"
---
# <a name="activity-report"></a>Rapport d'activités

Le tableau de bord des **rapports** 365 Office affiche la vue d’ensemble des activités sur les produits Office 365 au sein de votre organisation. Elle vous permet d’explorer les rapports individuels au niveau du produit afin d’améliorer la précision des activités dans chaque produit. Par exemple, le rapport **activité Skype entreprise** vous permet de visualiser le nombre d’utilisateurs qui utilisent des sessions d’égal à égal ou de conférences organisées ou qui participent à des sessions de conférence. 

Pour plus d’informations, consultez la [vue d’ensemble des rapports](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) .
  
Ce rapport, ainsi que les autres rapports Skype entreprise, vous fournissent des informations sur les activités au sein de votre organisation. Ces informations détaillées sont très utiles pour analyser, planifier et prendre des décisions pour votre entreprise.
  
> [!NOTE]
> Vous pouvez afficher tous les rapports Skype entreprise lorsque vous vous connectez en tant qu’administrateur dans le centre d’administration Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-activity-report"></a>Comment obtenir le rapport d'activité Skype Entreprise

1. Accédez au centre d’administration > **** > **l’utilisation**des rapports.
    
2. Sur la **page utilisation** , sélectionnez**activité** **Skype entreprise** > dans la **liste Sélectionner un rapport** située sur la gauche ou cliquez sur le widget **activité Skype entreprise** .

  
## <a name="interpret-the-skype-for-business-activity-report"></a>Interpréter le rapport d'activité Skype Entreprise

Vous pouvez visualiser l'activité Skype Entreprise d'un utilisateur à l'aide des graphiques **Activité** et **Utilisateurs**.
  
![Skype for Business Online Activity Report](../images/670c8bc6-d29c-4033-87fc-a20d324c9aae.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>
Le rapport activité de la messagerie électronique sur l' **activité Skype entreprise** peut être consulté pour les tendances au cours des 7, 30, 90 ou 180 jours qui suivent. Toutefois, si vous cliquez sur un jour particulier du rapport, la table (voir le numéro 7) affichera les données pour un maximum de 28 jours à partir de la date actuelle (et non la date de génération du rapport).

> [!NOTE]
> Si vous cliquez sur les détails d’un jour spécifique, le tableau affiche uniquement les données pour les 30 derniers jours à la date de génération du rapport.

***
![Numéro 2](../images/sfbcallout2.png)<br/>
Chaque rapport comporte la date à laquelle il a été généré. Les rapports indiquent généralement une latence de 24 à 48 heures de l’heure d’activité. 
***
![Nombre 3](../images/sfbcallout3.png)<br/>Utilisez les données du graphique interactif **Activité** pour comprendre les tendances d'utilisation et visualiser le nombre total d'activités de conférence actuellement tenues dans votre organisation. Cela vous indiquera le nombre et les types d' **organisations**, de **participations** et de sessions de conférence d' **égal à égal** sein de votre organisation.  
***
![Numéro 4](../images/sfbcallout4.png)<br/>
Use the interactive chart data on the **Users** chart to understand usage trends and to see the number of unique users that are participating in conference activities that are being held in your organization. Il indique le nombre total d’utilisateurs, ainsi que les types de **sessions d’égal à égal**, d' **organisation**et de participation **** à des conférences.
***
!["Nombre 5"](../images/sfbcallout5.png)<br/>
You can filter the series you see on the chart by clicking on an item in the legend. Par exemple, dans le graphique **activité** , cliquez ou appuyez sur **sessions d’égal à égal**, **organisées**ou ayant **participé** pour afficher uniquement les informations relatives à chacune d’elles. Changing this selection doesn't change the info in the grid table. 
***
![Numéro 6](../images/sfbcallout6.png)<br/>
Chaque graphique a un axe « X » (horizontal) et « Y » (vertical).
*    Sur le graphique **activité** , l’axe Y représente le nombre total d’organisations, de participations et de sessions d’égal à égal de conférences organisées.
*    Sur le graphique d’activité **utilisateurs** , l’axe Y indique le nombre d’utilisateurs uniques participant à chaque type d’organisations, de participations et de participations à des conférences.

L'axe X sur les deux graphiques représente la plage de dates sélectionnée pour ce rapport particulier. 
***
![Nombre 7](../images/sfbcallout7.png)<br/>
Le tableau montre une répartition de toutes les activités de conférences par utilisateur. Ce contrôle montre tous les utilisateurs qui disposent de Skype entreprise et leurs activités de conférence. Vous pouvez ajouter des colonnes supplémentaires au tableau.
* **Nom d’utilisateur est le** nom de l’utilisateur.
* **Supprimé** indique que la licence de l'utilisateur a été supprimée.<br/><br/>
  > [!NOTE]
  > Le rapport activité d’un utilisateur supprimé reste affiché tant qu’il a été concédé sous licence à un certain moment au cours de la période sélectionnée. La colonne **Supprimé** vous permet d'observer que l'utilisateur n'est peut-être plus actif, mais a contribué aux données du rapport.
     
* La **date de suppression** correspond à la date à laquelle la licence de l'utilisateur a été supprimée.
* **Dernière date d'activité (UTC)** représente la dernière fois que l'utilisateur a participé à une session d'égal à égal, a organisé une conférence ou a participé à une conférence.
* D' **égal à égal** indique le nombre total de sessions de conférence d’égal à égal utilisées par l’utilisateur.
* **Conférences organisées** indique le nombre total de conférences organisées par cet utilisateur.
* **Participations-à des conférences** indique le nombre total de conférences auxquelles l'utilisateur a participé.
* **Produit affecté** indique les produits Office 365 affectés à cet utilisateur.<br/>

Si les stratégies de votre organisation vous empêchent d’afficher des rapports dans lesquels les informations utilisateur sont identifiables, vous pouvez modifier le paramètre de confidentialité pour tous ces rapports. Pour plus d' **informations, voir masquer les détails des utilisateurs dans la section rapports** des rapports d’activité du [Centre d’administration](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).
***
![Nombre 8](../images/sfbcallout8.png)<br/>
Cliquez ou appuyez sur l’icône **colonnes** dans une des colonnes pour ajouter ou supprimer des colonnes dans le rapport.           <br/> ![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)
***
![Numéro 9](../images/sfbcallout9.png)<br/>
Vous pouvez également exporter les données du rapport vers un fichier Excel .csv, en cliquant ou en appuyant sur **Exporter**.           <br/> ![Bouton d’exportation des rapports de Skype entreprise.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/> Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2000 utilisateurs, vous pouvez les trier et les filtrer dans le tableau. Si vous avez plus de 2 000 utilisateurs, vous devrez exporter les données pour pouvoir les trier et les filtrer. 
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Autres rapports d'activité Skype Entreprise

- [Rapport sur l’utilisation des appareils Skype entreprise](device-usage-report.md) Vous pouvez voir les appareils, y compris les systèmes d’exploitation Windows et les appareils mobiles, sur lesquels l’application Skype entreprise est installée et qui l’utilisent pour la messagerie instantanée et les réunions.
    
- [Rapport d’activité d’organisateur de conférences Skype entreprise](conference-organizer-activity-report.md) Vous pouvez visualiser le nombre de conférences de vos utilisateurs à l’aide de la messagerie instantanée, de l’audio/la vidéo, du partage d’applications, du Web, de la Conférence rendez-vous/du tiers et de la Conférence rendez-vous.
    
- [Rapport d’activité d’égal à égal Skype entreprise](peer-to-peer-activity-report.md) Vous pouvez visualiser le nombre d’utilisation de la messagerie instantanée, de l’audio/la vidéo, du partage d’applications et du transfert de fichiers par utilisateur.
    
- [Rapport de blocage d’utilisateurs Skype entreprise](users-blocked-report.md) Vous pouvez afficher les utilisateurs de votre organisation qui ont été bloqués et ne peuvent plus passer d’appels RTC.
    
- [Rapport d’utilisation de la Conférence RTC Skype entreprise](pstn-usage-report.md) Vous pouvez voir le nombre de minutes passées pour des appels entrants/sortants et le coût de ces appels.

- [Rapport de pools de minutes RTC Skype entreprise](pstn-minute-pools-report.md) vous pouvez voir le nombre de minutes consommées pendant le mois en cours au sein de votre organisation.

- [Rapport Détails de la session Skype entreprise](session-details-report.md) Vous pouvez afficher des détails sur les expériences d’appel des utilisateurs individuels.

    
## <a name="related-topics"></a>Rubriques connexes
[Rapports d’activité dans le centre d’administration](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
