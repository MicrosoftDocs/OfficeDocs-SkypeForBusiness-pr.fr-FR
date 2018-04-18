---
title: Rapport d’utilisation de TLS
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Le nouveau Skype pour zone de rapports d’entreprise Admin Center affiche vous appelant et audio conférence activité dans votre organisation. Il vous permet de vous y plonger le rapports pour vous fournir des informations plus précises sur les activités de chaque utilisateur. Le rapport sur les détails d'utilisation PSTN de Skype Entreprise vous permet par exemple d'afficher le nombre de minutes passées pour des appels entrants ou sortants ainsi que les coûts de ces appels. Vous pouvez afficher les détails de l’utilisation d’Audio conférence PSTN, y compris le coût de l’appel afin que vous pouvez comprendre votre utilisation et appeler les détails de facturation pour déterminer l’utilisation au sein de votre organisation.
ms.openlocfilehash: 6ee6606ae37e02d07e3c3e57ca9fee529b150626
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="pstn-usage-report"></a>Rapport d’utilisation de TLS

Le nouveau Skype pour la zone Centre d’administration Business **rapports** affiche vous appelant et audio conférence activité dans votre organisation. Il vous permet de vous y plonger le rapports pour vous fournir des informations plus précises sur les activités de chaque utilisateur. Le rapport sur les **détails d'utilisation PSTN de Skype Entreprise** vous permet par exemple d'afficher le nombre de minutes passées pour des appels entrants ou sortants ainsi que les coûts de ces appels. Vous pouvez afficher les détails de l’utilisation d’Audio conférence PSTN, y compris le coût de l’appel afin que vous pouvez comprendre votre utilisation et appeler les détails de facturation pour déterminer l’utilisation au sein de votre organisation.
  
Consultez la [vue d’ensemble des rapports](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) pour les rapports supplémentaires qui sont disponibles.
  
Ce rapport, ainsi que l’autre Skype pour les rapports d’entreprise, vous donne des détails sur l’activité, y compris l’utilisation de l’appel au sein de votre organisation. Ces informations sont très utiles lorsque vous étudie, de planification et effectuer d’autres activités des décisions pour votre entreprise et pour configurer les [crédits de Communications](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)
  
> [!NOTE]
> Vous pouvez afficher tous les rapports Skype Entreprise lorsque vous vous connectez en tant qu'administrateur du centre d'administration Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Comment obtenir les rapports sur les détails d'utilisation PSTN de Skype Entreprise

- Accédez au **Centre d’administration Office 365** > **Admin centres** > **Skype pour le centre d’administration Business** > **rapports** > **les détails de l’utilisation de TLS**.
    
    > [!NOTE]
    > En fonction de l'abonnement Office 365 que vous avez souscrit, tous les produits et les rapports présentés dans cet article ne seront peut-être pas disponibles. 
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpréter le rapport d'utilisation PSTN de Skype Entreprise

Vous pouvez vous connaître l'utilisation PSTN Skype Entreprise d'un utilisateur en consultant chacune des colonnes qui sont affichées.
  
Voici une illustration du rapport.
  
![Rapport d'utilisation de la conférence RTC Skype Entreprise](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)

***
![Numéro 1](../images/sfbcallout1.png)<br/>Le tableau présente une répartition par utilisateur de toutes les utilisations PSTN. Affiche tous les utilisateurs qui ont Skype pour entreprise affectée ainsi que leur utilisation RTPC. Vous pouvez ajouter ou supprimer des colonnes dans ce tableau.
*    **ID d’appel** est l’identifiant d’appel pour un appel. Il s’agit d’un identificateur unique pour l’appel qui est utilisé lors de l’appel du service de support de Microsoft.
*    **ID de l'utilisateur** est le nom de connexion de l'utilisateur.
*    **Numéro de téléphone** est le Skype pour le numéro de téléphone professionnel qui a reçu l’appel pour les appels entrants ou le numéro composé pour les appels sortants.
*    **Emplacement de l’utilisateur** est le pays ou la région où se trouve l’utilisateur.
*    **ID de l’appelant** est un numéro de téléphone de l’appelant (ID de l’appelant) pour les appels entrants, le numéro à partir duquel provient l’appel ou le Skype pour le numéro d’entreprise d'où provient l’appel pour les appels sortants.
*    **Type d’appel** est si l’appel a été appeler d’un RTPC entrant ou sortant et le type de l’appel comme un appel placé par un utilisateur ou une conférence audio. Les types d’appels que vous pouvez voir sont : 

     **Types de Plan d’appel d’appel** 
     *    **user_in** (l’utilisateur a reçu un appel entrant de RTPC) 
     *    **user_out** (l’utilisateur a placé un appel RTC sortant) 
     *    **user_out_conf** (l’utilisateur ajouté 2 ou plusieurs participants de RTC de l’appel comme un appel de conférence 3 voies) 
     *    **user_out_transfer** (l’utilisateur transféré l’appel à un numéro RTC) 
     *    **user_out_forwarding** (l’utilisateur transmis à l’appel d’un numéro RTC)

     **Types d’appel de conférence audio**
     *    **conf_in** (c’est un appel entrant vers le pont de conférence de données Audio) 
     *    **conf_out** (un appel sortant à partir de la passerelle audioconférence généralement à ajouter un numéro RTC à la conférence)

     **Applications de Communication unifiée (UCAP)** 
     *    **ucap_in** (un appel entrant à l’application de communications unifiées comme file d’attente de surveillance ou d’appel automatique) 
     *    **ucap_out** (un appel sortant à partir de l’application de communications unifiées comme file d’attente de surveillance ou d’appel automatique)
*     
     **Internes et internationaux** vous indique si l’appel qui a été placé a été considérée comme intérieurs (au sein d’un pays/une région) ou internationaux (en dehors d’un pays/une région) basée sur l’emplacement de l’utilisateur. 
*    **Composé de destination** est le nom de la destination de pays/région est composé par exemple de la France, en Allemagne ou les États-Unis (US). 
*    **Type de numéro** est le type de numéro de téléphone d’un numéro de téléphone d’un utilisateur, un service ou un numéro d’appel gratuit.  
*    **Heure de début (UTC)** est l'heure à laquelle l'appel a commencé. 
*    **Durée** indique le temps de connexion de l'appel.  
*    **ConfID** est l’ID de la conférence audio de la conférence. 
*    **Les frais** sont le montant d’argent ou de coût de l’appel est facturé à votre compte. 
*    **La devise** est le type de devise utilisé pour calculer le coût de l’appel. 
*    **Fonction** est la licence utilisée pour l’appel. Les types de licences que vous pouvez voir sont les suivantes : 
     *    **MCOPSTNPP** - crédits de Communications <br/> **MCOPSTN1** - intérieur appelant Plan (3000 min US / 1200 min de l’Union européenne envisage) 
     *    **MCOPSTN2** - Plan d’appel International 
     *    **MCOPSTN5** - intérieur appelant Plan (plan d’appel 120 min) 
     *    **MCOMEETADD** - conférence Audio
     *    **MCOMEETACPEA** - paie par Minute audioconférence 
***
![Numéro 2](../images/sfbcallout2.png)<br/>Cliquez pour déplacer une colonne vers **Pour regrouper les informations autour d'une colonne en particulier, faites glisser et déplacez l'en-tête de la colonne ici** si vous souhaitez visualiser toutes les données regroupées dans une ou plusieurs colonnes.
 ***
![Numéro 3](../images/sfbcallout3.png)<br/>Vous pouvez également exporter des données dans un onglet séparé par des fichier Excel, en cliquant sur le bouton **Exporter vers Excel** . <br/><br/> Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez trier et filtrer directement dans le tableau du rapport. 
    > [!Note] 
    > Despite the export file named as .CSV (which implies a comma delimited export), as there may be commas in the data set, the file is actually delimited with **TABS** and not **COMMAS**.

## <a name="want-to-see-other-skype-for-business-reports"></a>Autres rapports d'activité Skype Entreprise

- [Skype pour le rapport d’activité commerciale](activity-report.md) Vous pouvez voir combien vos utilisateurs sont à l’aide de peer-to-peer, d’organisation et participé aux sessions de conférence.
    
- [Skype pour le rapport d’utilisation du périphérique Business](device-usage-report.md) Vous pouvez pour voir les périphériques, y compris les systèmes d’exploitation basés sur Windows et les périphériques mobiles qui ont le Skype pour application métier installé et sont en servent pour la messagerie instantanée et des réunions.
    
- [Skype pour le rapport d’activité commerciale conférence organisateur](conference-organizer-activity-report.md) Vous pouvez voir combien vos utilisateurs sont organiser des conférences qui utilisent la messagerie instantanée, audio/vidéo, partage d’applications, Web, /dial out - 3ème partie et /dial, Microsoft.
    
- [Skype Business conférence participant rapport d’activité](conference-participant-activity-report.md) Vous pouvez voir le partage d’applications audio/vidéo, messagerie instantanée, le nombre, le Web et l’accès à des conférences audio sont en cours participés.
    
- [Skype Business - to-peer rapport d’activité](peer-to-peer-activity-report.md) Vous pouvez voir combien vos utilisateurs sont à l’aide de messagerie instantanée, audio/vidéo, partage d’applications et le transfert de fichiers.
    
- [Skype pour les utilisateurs professionnels bloqué rapport](users-blocked-report.md) Vous pouvez voir les utilisateurs de votre organisation qui ont été bloqués d’effectuer les appels RTPC.

- [Skype pour rapport de pools minute RTC de l’entreprise](pstn-minute-pools-report.md) , vous pouvez voir le nombre de minutes consommées au cours du mois en cours au sein de votre organisation.

- [Skype pour le rapport de détails de session de Business](session-details-report.md) Vous pouvez afficher des détails sur les expériences d’appel de l’utilisateur.
    
## <a name="related-topics"></a>Rubriques connexes
[Rapports d'activité dans le centre d’administration Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
