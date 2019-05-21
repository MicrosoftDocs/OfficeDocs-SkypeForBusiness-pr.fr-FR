---
title: Rapport d'utilisation RTC
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
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
description: La nouvelle zone rapports du centre d’administration Skype entreprise vous permet d’afficher les appels et les activités de conférence audio au sein de votre organisation. Elle vous permet d’explorer des rapports pour vous offrir une vue plus granulaire des activités de chaque utilisateur. Le rapport sur les détails d'utilisation PSTN de Skype Entreprise vous permet par exemple d'afficher le nombre de minutes passées pour des appels entrants ou sortants ainsi que les coûts de ces appels. Vous pouvez afficher les détails d’utilisation RTC de l’audioconférence, y compris le coût de l’appel, afin de comprendre l’utilisation et les détails de facturation pour déterminer l’utilisation au sein de votre organisation.
ms.openlocfilehash: e1753915753c110a615edb108b2ff98efe237aa6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287722"
---
# <a name="pstn-usage-report"></a>Rapport d'utilisation RTC

La nouvelle zone **rapports** du centre d’administration Skype entreprise vous permet d’afficher les appels et les activités de conférence audio au sein de votre organisation. Elle vous permet d’explorer des rapports pour vous offrir une vue plus granulaire des activités de chaque utilisateur. Le rapport sur les **détails d'utilisation PSTN de Skype Entreprise** vous permet par exemple d'afficher le nombre de minutes passées pour des appels entrants ou sortants ainsi que les coûts de ces appels. Vous pouvez afficher les détails d’utilisation RTC de l’audioconférence, y compris le coût de l’appel, afin de comprendre l’utilisation et les détails de facturation pour déterminer l’utilisation au sein de votre organisation.
  
Consultez la [vue d’ensemble des rapports](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) pour plus d’informations sur les rapports disponibles.
  
Ce rapport, ainsi que les autres rapports Skype entreprise, vous fournissent des informations sur les activités, y compris l’utilisation des appels au sein de votre organisation. Ces informations sont très utiles lorsque vous effectuez des recherches, planifiez et organisez d’autres décisions d’entreprise pour votre organisation et que vous configurez des [crédits de communication](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Vous pouvez accéder à tous les rapports Skype Entreprise lorsque vous vous connectez au centre d'administration d'Office 365 en tant qu'administrateur. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Comment obtenir les rapports sur les détails d'utilisation PSTN de Skype Entreprise

![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **à l’aide du centre d’administration Skype entreprise**

-  > Accédez au centre d’administration du centre d' **administration Office 365****centres** > **d’administration Skype entreprise** > -**rapports** > **Détails d’utilisation PSTN**.
    
    > [!NOTE]
    > En fonction de l'abonnement Office 365 que vous avez souscrit, tous les produits et les rapports présentés dans cet article ne seront peut-être pas disponibles. 
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpréter le rapport d'utilisation PSTN de Skype Entreprise

Vous pouvez vous connaître l'utilisation PSTN Skype Entreprise d'un utilisateur en consultant chacune des colonnes qui sont affichées.
  
Voici une illustration du rapport.
  
![Rapport d'utilisation de la conférence RTC Skype Entreprise](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)

***
![Numéro 1](../images/sfbcallout1.png)<br/>Le tableau présente une répartition par utilisateur de toutes les utilisations PSTN. Cette opération montre tous les utilisateurs pour lesquels Skype entreprise est associé et leur utilisation PSTN. Vous pouvez ajouter ou supprimer des colonnes dans ce tableau.
*    **ID d’appel** est l’ID d’appel d’un appel. Il s’agit d’un identificateur unique de l’appel qui est utilisé lors de l’appel du service de support technique Microsoft.
*    **ID de l'utilisateur** est le nom de connexion de l'utilisateur.
*    **Numéro de téléphone** correspond au numéro de téléphone skype entreprise qui a reçu l’appel d’appels entrants ou du numéro numéroté pour les appels sortants.
*    **Emplacement** de l’utilisateur est le pays ou la région où se trouve l’utilisateur.
*    **ID** de l’appelant correspond au numéro de téléphone (ID d’appelant) de l’appelant pour les appels entrants, le numéro à partir duquel provient l’appel ou le numéro Skype entreprise à partir duquel il a été émis pour les appels sortants.
*    **Type d’appel** indique si l’appel était un appel RTC entrant ou sortant ainsi que le type d’appel passé par un utilisateur ou une conférence audio. Les types d’appels que vous pouvez voir: 

     **Types d’appels de plan d’appels** 
     *    **user_in** (l’utilisateur a reçu un appel RTC entrant) 
     *    **user_out** (l’utilisateur a placé un appel RTC sortant) 
     *    **user_out_conf** (l’utilisateur a ajouté 2 personnes ou plus de participants PSTN à l’appel, par exemple une conférence téléphonique à trois directions) 
     *    **user_out_transfer** (l’utilisateur a transféré l’appel vers un numéro PSTN) 
     *    **user_out_forwarding** (l’utilisateur a transféré l’appel vers un numéro PSTN)

     **Types d’appels de conférence audio**
     *    **conf_in** (appel entrant vers le pont de conférence audio) 
     *    **conf_out** (un appel sortant provenant généralement de l’audioconférence pour ajouter un numéro PSTN à la Conférence)

     **Applications de communication unifiée (UCAP)** 
     *    **ucap_in** (un appel RTC entrant vers l’application de communications unifiées, tel que le standard automatique ou la file d’attente d’appels); 
     *    **ucap_out** (un appel RTC sortant depuis l’application de communications unifiées, tel que le standard automatique ou la file d’attente d’appels)
     *    **Remarque:** Les appels transférés vers un utilisateur à partir de l’application de communications unifiées, tels qu’un standard automatique ou une file d’attente d’appels, n’apparaissent pas dans le rapport d’utilisation RTC, car ces appels sont des appels audio d’égal à égal (P2P). Vous pouvez accéder aux appels P2P dans le centre d’administration de Skype entreprise, sous la section «outils > d’analyse des appels Skype entreprise» et effectuer une recherche par nom d’utilisateur ou adresse SIP mettant en corrélation l’appel par date/heure et/ou CLID d’origine (ID de ligne d’appel). 
*     
     **National/international** vous indique si l’appel qui a été placé était considéré comme national (dans un pays ou une région) ou international (à l’extérieur d’un pays ou d’une région) en fonction de l’emplacement de l’utilisateur. 
*    **Composé composé** est le nom de la destination du pays/de la région qui est numérotée comme France, Allemagne ou les États-Unis. 
*    **Type de numéro** est le type de numéro de téléphone qui provient du numéro de téléphone d’un utilisateur, d’un service ou d’un numéro sans frais.  
*    **Heure de début (UTC)** est l'heure à laquelle l'appel a commencé. 
*    **Durée** indique le temps de connexion de l'appel.  
*    **ConfID** est l’ID de conférence de la conférence audio. 
*    **Débit** est le montant d’argent ou le coût de l’appel débité sur votre compte. 
*    **Devise** correspond au type de devise utilisé pour calculer le coût de l’appel. 
*    **Capability** est la licence utilisée pour l’appel. Les types de licence qui peuvent s’afficher sont les suivants: 
     *    **MCOPSTNPP** -crédits de communication <br/> **MCOPSTN1** -forfait d’appels nationaux (3000 min US/1200 min Europe) 
     *    **MCOPSTN2** -forfait d’appels internationaux 
     *    **MCOPSTN5** -forfait d’appels nationaux (forfait d’appels min 120) 
     *    **MCOPSTN6** -forfait d’appels nationaux (forfait d’appels min 240) Remarque: disponibilité limitée
     *    **MCOMEETADD** -audioconférence
     *    **MCOMEETACPEA** -audioconférence à la minute
> [!NOTE]
> Pour inclure uniquement les appels payants à la minute qui ne sont pas inclus dans votre abonnement d’appel ou de conférence, filtrez le rapport avec la fonctionnalité «MCOPSTNPP». Cette opération permet de fournir un élément de tous les appels à la minute.  Pour les conférences audio à la minute, filtrez en fonction de «MCOMEETACPEA» au lieu de «MCOPSTNPP».  
***
> [!NOTE]
> Vous pouvez également voir «aucune donnée» dans certains champs. «Aucune donnée» signifie que le champ n’est pas applicable au type d’appel ou à la fonctionnalité. 
***
> [!NOTE]
> Si vous avez un plan d’appels Telstra, vous ne verrez pas les enregistrements des détails des appels dans le rapport d’utilisation PSTN. Veuillez contacter Telstra pour obtenir les exigences de votre rapport. 
***
![Numéro 2](../images/sfbcallout2.png)<br/>Cliquez pour déplacer une colonne vers **Pour regrouper les informations autour d'une colonne en particulier, faites glisser et déplacez l'en-tête de la colonne ici** si vous souhaitez visualiser toutes les données regroupées dans une ou plusieurs colonnes.
 ***
![Nombre 3](../images/sfbcallout3.png)<br/>Vous pouvez également exporter les données du rapport vers un fichier Excel délimité par des TABULATIONs en cliquant ou en appuyant sur le bouton **Exporter vers Excel** . <br/><br/> Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez trier et filtrer directement dans le tableau du rapport. 
    > [!Note] 
    > Despite the export file named as .CSV (which implies a comma delimited export), as there may be commas in the data set, the file is actually delimited with **TABS** and not **COMMAS**.

## <a name="want-to-see-other-skype-for-business-reports"></a>Autres rapports d'activité Skype Entreprise

- [Rapport d’activité Skype entreprise](activity-report.md) Vous pouvez visualiser le nombre d’organisations, de participations et de sessions d’égal à égal de conférences par utilisateur.
    
- [Rapport sur l’utilisation des appareils Skype entreprise](device-usage-report.md) Vous pouvez voir les appareils tels que les systèmes d’exploitation Windows et les appareils mobiles sur lesquels l’application Skype entreprise est installée et qui s’en servent pour la messagerie instantanée et les réunions.
    
- [Rapport d’activité d’organisateur de conférences Skype entreprise](conference-organizer-activity-report.md) Vous pouvez visualiser le nombre de conférences de vos utilisateurs à l’aide de la messagerie instantanée, de l’audio/la vidéo, du partage d’applications, du Web, de/Dial tiers et/Dial de Microsoft.
    
- [Rapport d’activité de participation à des conférences Skype entreprise](conference-participant-activity-report.md) Vous pouvez voir le nombre de messages instantanés, audio/vidéo, du partage d’applications, du Web et de la numérotation des conférences audio.
    
- [Rapport d’activité d’égal à égal Skype entreprise](peer-to-peer-activity-report.md) Vous pouvez visualiser le nombre d’utilisation de la messagerie instantanée, de l’audio/la vidéo, du partage d’applications et du transfert de fichiers par utilisateur.
    
- [Rapport de blocage d’utilisateurs Skype entreprise](users-blocked-report.md) Vous pouvez afficher les utilisateurs de votre organisation qui ont été bloqués et ne peuvent plus passer d’appels RTC.

- [Rapport de pools de minutes RTC Skype entreprise](pstn-minute-pools-report.md) vous pouvez voir le nombre de minutes consommées pendant le mois en cours au sein de votre organisation.

- [Rapport Détails de la session Skype entreprise](session-details-report.md) Vous pouvez afficher des détails sur les expériences d’appel des utilisateurs individuels.
    
## <a name="related-topics"></a>Voir aussi
[Rapports d'activité dans le centre d’administration Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
