---
title: Rapport du nombre de minutes RTC
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 51c2f7ac-2b72-488d-b1ea-f00e1e88ee7a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: La nouvelle zone rapports du centre d’administration Skype entreprise vous permet d’afficher les appels et les activités de conférence audio au sein de votre organisation. Elle vous permet d’explorer des rapports pour vous offrir une vue plus granulaire des activités de chaque utilisateur. Par exemple, vous pouvez utiliser le rapport de pools de minutes RTC Skype entreprise pour connaître le nombre de minutes consommées lors du mois en cours au sein de votre organisation.
ms.openlocfilehash: bfbc21453732d338c4d0cf6355903df344c826f4
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494014"
---
# <a name="pstn-minute-pools-report"></a>Rapport du nombre de minutes RTC

>[!NOTE]
>Ce rapport est disponible uniquement pour la version bêta des clients.

La nouvelle zone **rapports** du centre d’administration Skype entreprise vous permet d’afficher les appels et les activités de conférence audio au sein de votre organisation. Elle vous permet d’explorer des rapports pour vous offrir une vue plus granulaire des activités de chaque utilisateur. Par exemple, vous pouvez utiliser le rapport de pools de **minutes RTC Skype entreprise** pour connaître le nombre de minutes consommées lors du mois en cours au sein de votre organisation.
  
Consultez la [vue d’ensemble des rapports](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) pour plus d’informations sur les rapports disponibles.
  
Ce rapport, ainsi que les autres rapports Skype entreprise, vous fournissent des informations sur les activités au sein de votre organisation. Ces informations sont très utiles lors de l’examen, de la planification et de la création d’autres décisions commerciales pour votre organisation, ainsi que pour la configuration de [crédits de communication](/microsoftteams/what-are-communications-credits) .
  
> [!NOTE]
> Vous pouvez accéder à tous les rapports Skype Entreprise lorsque vous vous connectez au centre d'administration d'Office 365 en tant qu'administrateur. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>Comment obtenir le rapport de pools de minutes RTC Skype entreprise

![Icône illustrant le logo](../images/sfb-logo-30x30.png) Skype entreprise **dans le centre d’administration Skype entreprise**

-  > Accédez au centre d’administration du centre d' **administration Office 365****centres** > **d’administration Skype entreprise** > -**rapports sur** > les pools de**minutes RTC**.
    
> [!NOTE]
> En fonction de l’abonnement Office 365 que vous avez, vous ne verrez peut-être pas les mêmes détails. 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>Interpréter le rapport de pools de minutes RTC Skype entreprise

Vous pouvez afficher les listes de minutes Skype entreprise d’un utilisateur en consultant chacune des colonnes qui sont affichées.
  
Voici une illustration du rapport.
  
## 

![Rapport de pools de minutes RTC Skype entreprise](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>Le tableau montre une répartition des regroupements de minutes par licence (fonctionnalité) et d’emplacement d’utilisation. 
*    **Capability** est le plan de licence/service utilisé pour l’appel. Les offres de licence/service qui peuvent figurer dans ce rapport sont les suivantes:
     * MCOPSTN1-forfait d’appels nationaux (plans 3000-minutes d’Europe/1200 minutes
     * MCOPSTN2-national & international Calling, à partir duquel vous verrez un forfait local (3000-minute-américaine/Canada/PR, 1200-minutes Europe) et un pool international (600 minutes). Le capuchon est atteint chaque fois que la PAC nationale ou internationale est atteinte dans le cadre du mois civil. 
     * MCOPSTN5-forfait d’appels nationaux (forfait d’appels de 120 minutes)
     * MCOPSTN6-forfait d’appels nationaux (forfait d’appels de 240 minutes)
     * MCOMEETADD-audioconférence
*    La description de la **fonctionnalité** est une description du type de licence utilisé pour l’appel.
*    Le **pool de minutes** est l’emplacement d’utilisation des licences du ou des utilisateurs qui partagent le pool de minutes. 
*    **Minutes utilisées** indique le nombre de minutes d’utilisation par mois.
*    Nombre **total de minutes** est le nombre total de minutes disponibles pour le mois. 
*    **Pourcentage utilisé** correspond au pourcentage de minutes d’utilisation du mois. 
***
![Numéro 2](../images/sfbcallout2.png)<br/>Cliquez pour déplacer une colonne vers **Pour regrouper les informations autour d'une colonne en particulier, faites glisser et déplacez l'en-tête de la colonne ici** si vous souhaitez visualiser toutes les données regroupées dans une ou plusieurs colonnes. 
***
![Nombre 3](../images/sfbcallout3.png)<br/>Vous pouvez également exporter les données du rapport vers un fichier Excel .csv, en cliquant ou en appuyant sur le bouton **Exporter vers Excel**. <br/><br/> Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2000 utilisateurs, vous pouvez les trier et les filtrer dans le tableau. Si vous avez plus de 2 000 utilisateurs, vous devrez exporter les données pour pouvoir les trier et les filtrer.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Autres rapports d'activité Skype Entreprise

- [Rapport d’activité Skype entreprise](activity-report.md) Vous pouvez visualiser le nombre d’organisations, de participations et de sessions d’égal à égal de conférences par utilisateur.
    
- [Rapport sur l’utilisation des appareils Skype entreprise](device-usage-report.md) Vous pouvez voir les appareils tels que les systèmes d’exploitation Windows et les appareils mobiles sur lesquels l’application Skype entreprise est installée et qui s’en servent pour la messagerie instantanée et les réunions.
    
- [Rapport d’activité d’organisateur de conférences Skype entreprise](conference-organizer-activity-report.md) Vous pouvez visualiser le nombre de conférences de vos utilisateurs à l’aide de la messagerie instantanée, de l’audio/la vidéo, du partage d’applications, du Web, de/Dial tiers et/Dial de Microsoft.
    
- [Rapport d’activité de participation à des conférences Skype entreprise](conference-participant-activity-report.md) Vous pouvez voir le nombre de messages instantanés, audio/vidéo, du partage d’applications, du Web et de la numérotation des conférences audio.
    
- [Rapport d’activité d’égal à égal Skype entreprise](peer-to-peer-activity-report.md) Vous pouvez visualiser le nombre d’utilisation de la messagerie instantanée, de l’audio/la vidéo, du partage d’applications et du transfert de fichiers par utilisateur.
    
- [Rapport de blocage d’utilisateurs Skype entreprise](users-blocked-report.md) Vous pouvez afficher les utilisateurs de votre organisation qui ont été bloqués et ne peuvent plus passer d’appels RTC.

- [Rapport Détails de la session Skype entreprise](session-details-report.md) Vous pouvez afficher des détails sur les expériences d’appel des utilisateurs individuels.
    
## <a name="related-topics"></a>Voir aussi
[Rapports d'activité dans le centre d’administration Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
