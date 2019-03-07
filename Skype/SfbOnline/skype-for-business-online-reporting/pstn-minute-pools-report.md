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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: La nouvelle Skype de zone de rapports du centre d’administration Business affiche vous appeler et audio conférence activité dans votre organisation. Elle vous permet des détails des rapports pour vous donnent plus granulaires sur les activités de chaque utilisateur. Par exemple, vous pouvez utiliser la Skype pour rapport de pools minute Business PSTN pour afficher le nombre de minutes consommées au cours du mois au sein de votre organisation.
ms.openlocfilehash: 903ea97fa5cd187e49db89d0e4db32ad7b851a41
ms.sourcegitcommit: d12a9f2d10093e24d4af54ce6044b512e7e3787e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454015"
---
# <a name="pstn-minute-pools-report"></a>Rapport du nombre de minutes RTC

>[!NOTE]
>Ce rapport n’est disponible pour afficher un aperçu des clients.

La nouvelle Skype pour la zone Centre d’administration Business **rapports** affiche vous appeler et audio conférence activité dans votre organisation. Elle vous permet des détails des rapports pour vous donnent plus granulaires sur les activités de chaque utilisateur. Par exemple, vous pouvez utiliser le rapport **Skype pour les pools d’entreprise PSTN minutes** pour afficher le nombre de minutes consommées au cours du mois au sein de votre organisation.
  
Consultez la rubrique [vue d’ensemble des rapports](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) pour plusieurs rapports qui sont disponibles.
  
Ce rapport, ainsi que l’autres Skype pour les rapports d’entreprise, vous donne plus d’informations sur l’activité au sein de votre organisation. Ces informations sont très utiles lors de l’analyse, la planification et les décisions autres pour votre organisation et de configuration [Communications générique](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Vous pouvez afficher tous les rapports Skype Entreprise lorsque vous vous connectez en tant qu'administrateur du centre d'administration Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>Comment obtenir le Skype pour rapport de pools minute Business PSTN

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**

- Accédez au **Centre d’administration Office 365** > **Admin centres** > **Skype pour le centre d’administration Business** > **rapports** > **pools minutes PSTN**.
    
> [!NOTE]
> En fonction de l’abonnement à Office 365 que vous disposez, vous verrez ne peut-être pas les mêmes coordonnées indiquées ici. 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>Interpréter le Skype pour rapport de pools minute Business PSTN

Vous pouvez obtenir une vue dans Skype de l’utilisateur pour les pools d’entreprise minutes en regardant chacune des colonnes qui sont affichés.
  
Voici une illustration du rapport.
  
## 

![Skype pour minute Business PSTN pools de rapport](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>Le tableau présente une répartition des pools minutes par licence (capacité) et l’emplacement de l’utilisation. 
*    **Fonctionnalité** est le plan de licence/service utilisé pour l’appel. Les plans de licence/service que peuvent apparaître dans ce rapport sont les suivantes :
     * MCOPSTN1 - intérieur appelant planifier (3000-minute US/1200-minute UE plans
     * MCOPSTN2 - & nationales International appelant planifier à partir de laquelle vous verrez un pool interne (3000-minute US/Canada/PR, minute-1200 Europe) et un pool international (600-minutes). Cap minute est atteint lorsque cap - ou-international nationale est atteint au cours du mois de calendrier. 
     * MCOPSTN5 - intérieur appelant Plan (plan appelant 120 minutes)
     * MCOPSTN6 - intérieur appelant Plan (plan appelant de 240 minutes)
     * MCOMEETADD - services d’audioconférence
*    **Description de la fonctionnalité** est une description du type de licence utilisé pour l’appel.
*    **Pays Minute Pool** est l’emplacement de l’utilisation de licence l’ou les utilisateurs qui partagent le pool minute. 
*    **Minutes utilisé** est le nombre de minutes utilisée chaque mois.
*    **Nombre total de Minutes** est le nombre total de minutes disponibles pour le mois. 
*    **Pourcentage utilisé** est le pourcentage de temps en minutes pour le mois. 
***
![Numéro 2](../images/sfbcallout2.png)<br/>Cliquez pour déplacer une colonne vers **Pour regrouper les informations autour d'une colonne en particulier, faites glisser et déplacez l'en-tête de la colonne ici** si vous souhaitez visualiser toutes les données regroupées dans une ou plusieurs colonnes. 
***
![Nombre 3](../images/sfbcallout3.png)<br/>Vous pouvez également exporter les données du rapport vers un fichier Excel .csv, en cliquant ou en appuyant sur le bouton **Exporter vers Excel**. <br/><br/> Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez trier et filtrer dans la table dans le rapport lui-même. Si vous avez plus de 2 000 utilisateurs, vous devrez exporter les données pour pouvoir les trier et les filtrer.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Autres rapports d'activité Skype Entreprise

- [Skype pour le rapport des activités](activity-report.md) Vous pouvez voir combien vos utilisateurs sont à l’aide d’égal à égal, organisé et participé à des sessions de conférence.
    
- [Skype pour le rapport d’utilisation des périphériques Business](device-usage-report.md) Vous pouvez pour voir les périphériques, y compris les systèmes d’exploitation Windows et les appareils mobiles qui ont le Skype pour l’application de gestion installés et utilisent pour la messagerie instantanée et réunions.
    
- [Skype Business conférence organisateur rapport d’activité](conference-organizer-activity-report.md) Vous pouvez voir combien vos utilisateurs sont organiser des conférences qui utilisent la messagerie instantanée, audio/vidéo, partage d’applications, Web, /dial out - 3ème partie et /dial out - Microsoft.
    
- [Skype Business conférence participant rapport d’activité](conference-participant-activity-report.md) Vous pouvez voir le partage d’application audio/vidéo, messagerie instantanée, le nombre, Web et accès à des conférences audio sont en cours ont participé.
    
- [Skype pour le rapport des activités d’égal à égal professionnels](peer-to-peer-activity-report.md) Vous pouvez voir combien vos utilisateurs sont à l’aide de messagerie instantanée, audio/vidéo, partage d’application et de transfert de fichiers.
    
- [Skype pour les utilisateurs professionnels bloqués de rapport](users-blocked-report.md) Vous pouvez voir les utilisateurs de votre organisation qui ont été bloqués à partir de l’émission d’appels PSTN.

- [Skype pour le rapport de détails de session Business](session-details-report.md) Vous pouvez voir plus d’informations sur les expériences d’appel d’un utilisateur individuel.
    
## <a name="related-topics"></a>Rubriques connexes
[Rapports d'activité dans le centre d’administration Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
