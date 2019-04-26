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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: La nouvelle Skype de zone de rapports du centre d’administration Business affiche vous appeler et audio conférence activité dans votre organisation. Elle vous permet des détails des rapports pour vous donnent plus granulaires sur les activités de chaque utilisateur. Le rapport sur les détails d'utilisation PSTN de Skype Entreprise vous permet par exemple d'afficher le nombre de minutes passées pour des appels entrants ou sortants ainsi que les coûts de ces appels. Vous pouvez afficher les détails d’utilisation PSTN de conférence Audio, y compris le coût de l’appel afin que vous puissiez comprendre l’utilisation et appeler les détails de facturation pour déterminer l’usage au sein de votre organisation.
ms.openlocfilehash: 2a0db39852169cbb4c1dacab178d2f5b3b96dc7e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32239870"
---
# <a name="pstn-usage-report"></a>Rapport d'utilisation RTC

La nouvelle Skype pour la zone Centre d’administration Business **rapports** affiche vous appeler et audio conférence activité dans votre organisation. Elle vous permet des détails des rapports pour vous donnent plus granulaires sur les activités de chaque utilisateur. Le rapport sur les **détails d'utilisation PSTN de Skype Entreprise** vous permet par exemple d'afficher le nombre de minutes passées pour des appels entrants ou sortants ainsi que les coûts de ces appels. Vous pouvez afficher les détails d’utilisation PSTN de conférence Audio, y compris le coût de l’appel afin que vous puissiez comprendre l’utilisation et appeler les détails de facturation pour déterminer l’usage au sein de votre organisation.
  
Consultez la rubrique [vue d’ensemble des rapports](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) pour plusieurs rapports qui sont disponibles.
  
Ce rapport, ainsi que l’autres Skype pour les rapports d’entreprise, vous donne plus d’informations sur l’activité, y compris l’appel d’utilisation au sein de votre organisation. Ces informations sont très utiles lorsque vous analyse, la planification et l’émission d’autres activités décisions pour votre organisation et de configuration [Communications générique](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Vous pouvez accéder à tous les rapports Skype Entreprise lorsque vous vous connectez au centre d'administration d'Office 365 en tant qu'administrateur. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Comment obtenir les rapports sur les détails d'utilisation PSTN de Skype Entreprise

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**

- Accédez au **Centre d’administration Office 365** > **Admin centres** > **Skype pour le centre d’administration Business** > **rapports** > **détails d’utilisation PSTN**.
    
    > [!NOTE]
    > En fonction de l'abonnement Office 365 que vous avez souscrit, tous les produits et les rapports présentés dans cet article ne seront peut-être pas disponibles. 
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpréter le rapport d'utilisation PSTN de Skype Entreprise

Vous pouvez vous connaître l'utilisation PSTN Skype Entreprise d'un utilisateur en consultant chacune des colonnes qui sont affichées.
  
Voici une illustration du rapport.
  
![Rapport d'utilisation de la conférence RTC Skype Entreprise](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)

***
![Numéro 1](../images/sfbcallout1.png)<br/>Le tableau présente une répartition par utilisateur de toutes les utilisations PSTN. Affiche tous les utilisateurs qui ont Skype pour les entreprises affecté et leur utilisation PSTN. Vous pouvez ajouter ou supprimer des colonnes dans ce tableau.
*    **ID d’appel** est l’ID de l’appel à un appel. Il est un identificateur unique de l’appel est utilisé lors de l’appel de prise en charge du service Microsoft.
*    **ID de l'utilisateur** est le nom de connexion de l'utilisateur.
*    **Numéro de téléphone** est le Skype pour le numéro de téléphone professionnel qui a reçu l’appel pour les appels entrants ou le numéro composé pour les appels sortants.
*    **Emplacement de l’utilisateur** est la pays/la région où se trouve l’utilisateur.
*    **ID de l’appelant** est le numéro de téléphone de l’appelant (ID de l’appelant) pour les appels entrants, le numéro à partir de laquelle l’appel provient ou le Skype pour numéro Professionnel d'où provient l’appel pour les appels sortants.
*    **Type d’appel** est si l’appel a été appeler un numéro PSTN entrant ou sortant et le type d’appel, par exemple un appel placé par un utilisateur ou une conférence audio. Les types d’appels que vous pouvez voir sont les suivants : 

     **Types d’appels Plan d’appel** 
     *    **user_in** (l’utilisateur a reçu un appel RTC entrant) 
     *    **user_out** (l’utilisateur a placé un appel RTC sortant) 
     *    **user_out_conf** (l’utilisateur a ajouté 2 ou plusieurs participants PSTN à l’appel, par exemple une téléconférence 3 voies) 
     *    **user_out_transfer** (l’utilisateur transféré l’appel vers un numéro RTC) 
     *    **user_out_forwarding** (l’utilisateur transféré l’appel vers un numéro RTC)

     **Types d’appels de conférence audio**
     *    **conf_in** (un appel entrant vers le pont de conférence Audio) 
     *    **conf_out** (un appel sortant à partir du pont d’audioconférence généralement pour ajouter un numéro RTC à la conférence)

     **Applications de communications unifiées (UCAP)** 
     *    **ucap_in** (un appel RTC entrant à l’application de communications unifiées telles que de la file d’attente standard ou un appel automatique) 
     *    **ucap_out** (un appel RTC sortant de l’application de communications unifiées telles que de la file d’attente standard ou un appel automatique)
     *    **Remarque :** Les appels qui ont été transférés à un utilisateur de l’application de communications unifiées comme une file d’attente standard ou un appel automatique n’apparaît pas dans le rapport d’utilisation PSTN que les branches d’appel sont les appels audio d’égal à égal (P2P). Vous pouvez accéder aux appels P2P dans le Skype pour le centre d’administration de Business sous « Outils > Skype pour Business appel Analytique » et rechercher par nom d’utilisateur ou SIP adresse corrélation l’appel par date/heure et/ou d’origine CLID (ID de ligne de l’appel). 
*     
     **Internes et internationaux** indique si l’appel a été placé a été pris en compte interne (au sein d’une pays/région) ou international (en dehors d’une pays/région) basée sur l’emplacement de l’utilisateur. 
*    **Destination composée** est le nom de la destination de pays/région est composé comme France, Allemagne ou États-Unis (États-Unis). 
*    **Type de numéro** est le type de numéro de téléphone d’un numéro de téléphone d’un utilisateur, un service ou le numéro d’appel gratuit.  
*    **Heure de début (UTC)** est l'heure à laquelle l'appel a commencé. 
*    **Durée** indique le temps de connexion de l'appel.  
*    **ConfID** est l’ID de conférence de la conférence audio. 
*    **Frais** est le montant ou le coût de l’appel est en cours débité de votre compte. 
*    **Devise** est le type de devise est utilisé pour calculer le coût de l’appel. 
*    **Fonctionnalité** est la licence utilisée pour l’appel. Vous pouvez voir les types de licences sont les suivants : 
     *    **MCOPSTNPP** - crédits Communications <br/> **MCOPSTN1** - planifier l’appel nationales (3000 min US / min 1200 UE plans) 
     *    **MCOPSTN2** - Plan appels internationaux 
     *    **MCOPSTN5** - intérieur appelant Plan (plan appelant 120 min) 
     *    **MCOPSTN6** - nationales appelant Plan (plan appelant de 240 minutes) Remarque : disponibilité limitée
     *    **MCOMEETADD** - services d’audioconférence
     *    **MCOMEETACPEA** - salaire par Minute services d’audioconférence
> [!NOTE]
> Si vous souhaitez exécuter un rapport pour inclure la paie uniquement par minutes appels qui ne sont pas inclus dans votre abonnement de conférence ou un appel, filtrer le rapport avec la fonctionnalité « MCOPSTNPP ». Cela fournit une liste détaillée des tous les salaires par minutes appels.  Paie par minute audioconférence, filtrer par « MCOMEETACPEA » au lieu de « MCOPSTNPP ».  
***
> [!NOTE]
> Vous ne pouvez également voir « aucune donnée » dans certains champs. « Aucune donnée » signifie que le champ n’est pas applicable au type d’appel ou fonctionnalité. 
***
> [!NOTE]
> Si vous disposez d’un plan d’appel Telstra, vous ne verrez pas les enregistrements des détails des appels dans le rapport d’utilisation PSTN. Veuillez contacter Telstra pour vos besoins en matière de création de rapports. 
***
![Numéro 2](../images/sfbcallout2.png)<br/>Cliquez pour déplacer une colonne vers **Pour regrouper les informations autour d'une colonne en particulier, faites glisser et déplacez l'en-tête de la colonne ici** si vous souhaitez visualiser toutes les données regroupées dans une ou plusieurs colonnes.
 ***
![Nombre 3](../images/sfbcallout3.png)<br/>Vous pouvez également exporter le rapport de données dans un onglet délimité par des fichiers Excel, en cliquant sur le bouton **Exporter vers Excel** . <br/><br/> Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez trier et filtrer directement dans le tableau du rapport. 
    > [!Note] 
    > Despite the export file named as .CSV (which implies a comma delimited export), as there may be commas in the data set, the file is actually delimited with **TABS** and not **COMMAS**.

## <a name="want-to-see-other-skype-for-business-reports"></a>Autres rapports d'activité Skype Entreprise

- [Skype pour le rapport des activités](activity-report.md) Vous pouvez voir combien vos utilisateurs sont à l’aide d’égal à égal, organisé et participé à des sessions de conférence.
    
- [Skype pour le rapport d’utilisation des périphériques Business](device-usage-report.md) Vous pouvez pour voir les périphériques, y compris les systèmes d’exploitation Windows et les appareils mobiles qui ont le Skype pour l’application de gestion installés et utilisent pour la messagerie instantanée et réunions.
    
- [Skype Business conférence organisateur rapport d’activité](conference-organizer-activity-report.md) Vous pouvez voir combien vos utilisateurs sont organiser des conférences qui utilisent la messagerie instantanée, audio/vidéo, partage d’applications, Web, /dial out - 3ème partie et /dial out - Microsoft.
    
- [Skype Business conférence participant rapport d’activité](conference-participant-activity-report.md) Vous pouvez voir le partage d’application audio/vidéo, messagerie instantanée, le nombre, Web et accès à des conférences audio sont en cours ont participé.
    
- [Skype pour le rapport des activités d’égal à égal professionnels](peer-to-peer-activity-report.md) Vous pouvez voir combien vos utilisateurs sont à l’aide de messagerie instantanée, audio/vidéo, partage d’application et de transfert de fichiers.
    
- [Skype pour les utilisateurs professionnels bloqués de rapport](users-blocked-report.md) Vous pouvez voir les utilisateurs de votre organisation qui ont été bloqués à partir de l’émission d’appels PSTN.

- [Skype pour rapport de pools minute Business PSTN](pstn-minute-pools-report.md) , vous pouvez voir le nombre de minutes consommées au cours du mois au sein de votre organisation.

- [Skype pour le rapport de détails de session Business](session-details-report.md) Vous pouvez voir plus d’informations sur les expériences d’appel d’un utilisateur individuel.
    
## <a name="related-topics"></a>Voir aussi
[Rapports d'activité dans le centre d’administration Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
