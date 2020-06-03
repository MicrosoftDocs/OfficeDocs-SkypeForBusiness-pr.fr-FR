---
title: Rapport d'activités pair à pair
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: d3b2d569-4ee9-44b8-92bf-d518142f0713
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
- O365E_ReportsS4BPeerActivity
- O365M_ReportsS4BPeerActivity
- O365P_ReportsS4BPeerActivity
description: 'Get a Skype for Business Peer-to-peer activity report, and learn how to interpret and customize it for your needs. '
ms.openlocfilehash: 3708bff31f0034347c23d67d58cf4be7cb3bc956
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2020
ms.locfileid: "44205055"
---
# <a name="peer-to-peer-activity-report"></a>Rapport d'activités pair à pair

Le tableau de bord **rapports** affiche la vue d’ensemble des activités sur les produits Microsoft 365 ou Office 365 au sein de votre organisation. Il vous permet d'explorer les rapports au niveau de chaque produit pour obtenir une vue d'ensemble plus précise des activités qu'ils contiennent. Par exemple, vous pouvez utiliser le rapport **d’activité P2P Skype entreprise** pour visualiser le nombre d’utilisation de la messagerie instantanée, de l’audio, de la vidéo, du partage d’applications et du transfert de fichiers par utilisateur. 

Consultez la [vue d’ensemble des rapports](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).
  
Ce rapport, ainsi que les autres rapports Skype entreprise, vous fournissent des informations sur les activités au sein de votre organisation. Ces informations détaillées sont très utiles pour analyser, planifier et prendre des décisions pour votre entreprise. 
  
> [!NOTE]
> Vous pouvez afficher tous les rapports Skype entreprise lorsque vous vous connectez en tant qu’administrateur au centre d’administration Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-peer-to-peer-activity-report"></a>Comment obtenir le rapport d'activité P2P Skype Entreprise

1. Accédez au centre d’administration > **Reports**  >  **l’utilisation**des rapports.
    
2. Dans la page **utilisation** , sélectionnez activité d' **Skype for Business**  >  **égal à égal** Skype entreprise dans la **liste Sélectionner un rapport** sur la gauche. Vous pouvez cliquer sur le widget **activité Skype entreprise** , puis sur **activité d’égal à égal Skype entreprise** dans la liste **activité Skype entreprise** .

## <a name="interpret-the-skype-for-business-peer-to-peer-activity-report"></a>Interpréter le rapport d'activité P2P Skype Entreprise

Vous pouvez obtenir un aperçu de l'activité P2P Skype Entreprise en consultant les graphiques **Activité**, **Utilisateurs** et **Minutes**.
  
![Rapport d’égal à égal Skype avec légendes.](../images/82dec398-ca05-46c7-b0fe-affcbfc0ddd5.PNG)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>Le **rapport d'activité P2P Skype Entreprise** peut être consulté pour les tendances au cours des 7, 30, 90 ou 180 derniers jours. Toutefois, si vous cliquez sur un jour particulier du rapport, la table (voir le numéro 7) affichera les données pendant 30 jours, jusqu’à la date (voir le numéro 2) pour la date de génération du rapport.

> [!NOTE]
> Si vous cliquez sur les détails d’un jour spécifique, le tableau affiche uniquement les données pour les 30 derniers jours à la date de génération du rapport.

***
![Numéro 2](../images/sfbcallout2.png)<br/>Chaque rapport comporte la date à laquelle il a été généré. Les rapports indiquent généralement une latence de 24 à 48 heures de l’heure d’activité. 
***
![Nombre 3](../images/sfbcallout3.png)<br/>Utilisez les données de graphique du graphique interactif **Activité** pour comprendre les tendances d'utilisation et visualiser le nombre total de sessions par type de sessions qui se tient actuellement dans votre organisation. Il indique le nombre total de sessions de **messagerie instantanée**, **audio**, **vidéo**, de **partage d’application**et de **transferts de fichiers** au sein de votre organisation. 
***
![Numéro 4](../images/sfbcallout4.png)<br/>.Utilisez les données du graphique interactif **Utilisateurs** pour comprendre les tendances d'utilisation et afficher le nombre total d'utilisateurs uniques participant aux activités P2P qui se tiennent dans votre organisation. Le nombre total d’utilisateurs ainsi que les types de **messages instantanés**, **audio**, **vidéo**, de **partage d’application**et de **transferts de fichiers** sont affichés dans les sessions d’égal à égal.
***
!["Nombre 5"](../images/sfbcallout5.png)<br/>Utilisez les données du graphique interactif **Minutes** pour comprendre les tendances d'utilisation et afficher le nombre de minutes utilisées quand des utilisateurs réalisent des activités P2P lors de sessions audio/vidéo. Cela vous indiquera le nombre total de minutes **Audio** et **Vidéo** qui ont été utilisées pendant les sessions P2P. 
***
![Numéro 6](../images/sfbcallout6.png)<br/>Chaque graphique a un axe « X » (horizontal) et « Y » (vertical). 
*    Dans le graphique d'activité **Activité**, l'axe Y correspond au nombre total de sessions de messagerie instantanée, audio, vidéo, de partage d'application et de transferts de fichiers tenues par les utilisateurs dans votre organisation.
*    Dans le graphique d’activité **utilisateurs** , l’axe Y correspond au nombre total d’utilisateurs ayant tenu des sessions de messagerie instantanée, audio, vidéo, de partage d’application et de transfert de fichiers. 
*    Dans le graphique d'activité **Minutes**, l'axe Y correspond à la durée totale en minutes passée par les utilisateurs dans votre organisation lors de sessions audio et vidéo P2P. 

L'axe X sur les deux graphiques représente la plage de dates sélectionnée pour ce rapport particulier.
***
![Nombre 7](../images/sfbcallout7.png)<br/>You can filter the series you see on the chart by clicking on an item in the legend. Par exemple, dans le graphique **activité** , cliquez ou appuyez **sur messagerie instantanée**, **audio**, **vidéo**, **partage d’application**et transferts de **fichiers** pour afficher uniquement les informations relatives à chacune d’elles. Changing this selection doesn't change the info in the grid table. 
***
![Nombre 8](../images/sfbcallout8.png)<br/>Le tableau présente une répartition par utilisateur des activités P2P. Il vous indique tous les utilisateurs auxquels Skype Entreprise a été affecté ainsi que leurs activités P2P. Vous pouvez ajouter des colonnes supplémentaires dans ce tableau.
*    **Nom d'utilisateur** est le nom de l'utilisateur.
*    **Supprimé** indique que la licence de l'utilisateur a été supprimée. <br/> <br/> **Remarque :**  Le rapport activité d’un utilisateur supprimé reste affiché tant qu’il a été concédé sous licence à un certain moment au cours de la période sélectionnée. La colonne **Supprimé** vous permet d'observer que l'utilisateur n'est peut-être plus actif, mais a contribué aux données du rapport.  <br/><br/>
*    La **date de suppression** correspond à la date à laquelle la licence de l'utilisateur a été supprimée. 
*    **Dernière date d'activité (UTC)** est la dernière date d'activité (UTC) pour cet utilisateur.
*    **Messagerie instantanée** indique le nombre total de sessions P2P utilisées par l'utilisateur.
*    **Audio** indique le nombre total de sessions P2P audio.
*    **Vidéo** indique le nombre total de sessions P2P vidéo.
*    **Partage d'application** indique le nombre total de sessions P2P de partage d'application.
*    **Transferts de fichiers** indique le nombre total de sessions P2P de transferts de fichiers.
*    **Minutes audio** indique le nombre total de minutes audio utilisées dans votre organisation. 
*    **Minutes vidéo** indique le nombre total de minutes vidéo utilisées dans votre organisation. 

Si les stratégies de votre organisation vous empêchent d’afficher des rapports dans lesquels les informations utilisateur sont identifiables, vous pouvez modifier le paramètre de confidentialité pour tous ces rapports. Consultez la section **« Comment puis-je masquer les détails au niveau utilisateur ?** » dans les [rapports d’activité du centre d’administration](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263). 
***
![Numéro 9](../images/sfbcallout9.png)<br/>Vous pouvez également exporter les données du rapport vers un fichier Excel .csv, en cliquant ou en appuyant sur **Exporter**.           <br/> ![Bouton d’exportation des rapports de Skype entreprise.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/>Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez trier et filtrer directement dans le tableau du rapport. Si vous avez plus de 2 000 utilisateurs, vous devrez exporter les données pour pouvoir les trier et les filtrer.
***
![Nombre 10](../images/sfbcallout10.png)<br/>![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)<br/>Cliquez ou appuyez sur l’icône **colonnes** dans une des colonnes pour ajouter ou supprimer des colonnes dans le rapport.         
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Autres rapports d'activité Skype Entreprise

- [Rapport d’activité Skype entreprise](activity-report.md) Vous pouvez visualiser le nombre d’organisations, de participations et de sessions d’égal à égal de conférences par utilisateur.
    
- [Rapport sur l’utilisation des appareils Skype entreprise](device-usage-report.md) Vous pouvez voir les appareils tels que les systèmes d’exploitation Windows et les appareils mobiles sur lesquels l’application Skype entreprise est installée et qui s’en servent pour la messagerie instantanée et les réunions.
    
- [Rapport d’activité d’organisateur de conférences Skype entreprise](conference-organizer-activity-report.md) Vous pouvez visualiser le nombre de conférences de vos utilisateurs à l’aide de la messagerie instantanée, de l’audio/la vidéo, du partage d’applications, du Web, de la Conférence rendez-vous/du tiers et de la Conférence rendez-vous.
    
- [Rapport d’activité de participation à des conférences Skype entreprise](conference-participant-activity-report.md) Vous pouvez voir le nombre de participants à la messagerie instantanée, de l’audio/la vidéo, du partage d’applications, du Web et des conférences rendez-vous et des conférences rendez-vous.
    
- [Rapport de blocage d’utilisateurs Skype entreprise](users-blocked-report.md) Vous pouvez afficher les utilisateurs de votre organisation qui ont été bloqués et ne peuvent plus passer d’appels RTC.
    
- [Rapport d’utilisation de la Conférence RTC Skype entreprise](pstn-usage-report.md) Vous pouvez voir le nombre de minutes passées pour des appels entrants/sortants et le coût de ces appels.
    
- [Rapport de pools de minutes RTC Skype entreprise](pstn-minute-pools-report.md) vous pouvez voir le nombre de minutes consommées pendant le mois en cours au sein de votre organisation.

- [Rapport Détails de la session Skype entreprise](session-details-report.md) Vous pouvez afficher des détails sur les expériences d’appel des utilisateurs individuels.
    
## <a name="related-topics"></a>Voir aussi
[Rapports d’activité dans le centre d’administration](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 