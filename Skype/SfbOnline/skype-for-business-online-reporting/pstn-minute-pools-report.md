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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: La nouvelle Skype Entreprise rapports du Centre d’administration affiche les activités d’appel et d’audioconférence dans votre organisation. Il vous permet d’drill into reports to give you more granular insight about the activities of each user. Par exemple, vous pouvez utiliser le rapport Skype Entreprise des groupes de minutes PSTN pour consulter le nombre de minutes consommées au cours du mois en cours au sein de votre organisation.
ms.openlocfilehash: d3b75fd81628e4cfcd49b7b120ceed3e3f327bdc
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727993"
---
# <a name="pstn-minute-pools-report"></a>Rapport du nombre de minutes RTC

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

>[!NOTE]
>Ce rapport n’est disponible que pour afficher un aperçu des clients.

La nouvelle Skype Entreprise rapports  du Centre d’administration affiche les activités d’appel et d’audioconférence dans votre organisation. Il vous permet d’drill into reports to give you more granular insight about the activities of each user. Par exemple, vous pouvez utiliser le rapport Skype Entreprise des groupes de **minutes PSTN** pour consulter le nombre de minutes consommées au cours du mois en cours au sein de votre organisation.
  
Consultez la vue [d’ensemble des](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) rapports pour découvrir d’autres rapports disponibles.
  
Tout comme les autres rapports de Skype Entreprise, ce rapport vous fournit des détails sur les activités au sein de votre organisation. Ces informations détaillées sont très utiles pour examiner, planifier et prendre des décisions pour votre entreprise, ainsi que pour définir les [crédits de communication](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Vous pouvez consulter tous les rapports de Skype Entreprise lorsque vous vous connectez en tant qu’administrateur au Centre d’administration Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>Comment obtenir le rapport de Skype Entreprise de minutes PSTN

![Icône représentant le logo Skype Entreprise’affichage.](../images/sfb-logo-30x30.png) **Utilisation du Skype Entreprise d’administration**

- Allez dans le Centre d’administration > **centres d’administration** Skype Entreprise centre d’administration Rapports de groupes de  >    >    >  **minutes PSTN.**
    
> [!NOTE]
> En fonction de Microsoft 365 votre Office 365 abonnement, tous les détails présentés ici peuvent ne pas être affichés. 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>Interpréter le rapport Skype Entreprise des groupes de minutes PSTN

Vous pouvez obtenir un affichage des pools de Skype Entreprise minutes de l’utilisateur en regardant chacune des colonnes affichées.
  
Voici une illustration du rapport.

![Skype Entreprise Rapport sur les pools de minutes PSTN.](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![Numéro 1.](../images/sfbcallout1.png)<br/>Le tableau présente le détail des groupes de minutes par licence (fonctionnalité) et emplacement d’utilisation. 
*    **Il s’agit** de la licence/plan de service utilisé pour l’appel. Les plans de licence/service que vous pouvez voir dans ce rapport sont les suivants :
     * MCOPSTN1 - Forfait d’appels nationaux (plans de 3 000 minutes pour les États-Unis/1 200 minutes pour l’Ue)
     * MCOPSTN2 - Plan d’appels nationaux & internationaux à partir duquel vous verrez un pool national (3 000 minutes US/Canada/PR, pays européens de 1 200 minutes) et un pool international (600 minutes). La limite de minutes est atteinte chaque fois que la limite internationale -OU est atteinte au cours du mois calendaire. 
     * MCOPSTN5 - Forfait d’appels nationaux (forfait d’appels de 120 minutes)
     * MCOPSTN6 - Forfait d’appels nationaux (forfait d’appels de 240 minutes)
     * MCOMEETADD - Audioconférence
*    **La description de** la fonctionnalité est une description du type de licence utilisé pour l’appel.
*    **Country Minute Pool est** l’emplacement d’utilisation sous licence du ou des utilisateurs qui partagent le pool de minutes. 
*    **Le nombre de minutes** utilisées est le nombre de minutes utilisées chaque mois.
*    **Le nombre** total de minutes est le nombre total de minutes disponibles pour le mois. 
*    **Le pourcentage d’utilisation** est le pourcentage de minutes utilisée pour le mois. 
***
![Numéro 2.](../images/sfbcallout2.png)<br/>Cliquez pour déplacer une colonne vers **Pour regrouper les informations autour d'une colonne en particulier, faites glisser et déplacez l'en-tête de la colonne ici** si vous souhaitez visualiser toutes les données regroupées dans une ou plusieurs colonnes. 
***
![Numéro 3.](../images/sfbcallout3.png)<br/>Vous pouvez également exporter les données du rapport vers un fichier Excel .csv, en cliquant ou en appuyant sur le bouton **Exporter vers Excel**. <br/><br/> Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez trier et filtrer dans le tableau, au sein du rapport proprement dit. Si vous avez plus de 2 000 utilisateurs, vous devrez exporter les données pour pouvoir les trier et les filtrer.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Autres rapports d'activité Skype Entreprise

- [Skype Entreprise d’activité de l’entreprise](activity-report.md) Vous pouvez consulter le nombre d’utilisations, d’organisation et de participations de vos utilisateurs à des conférences.
    
- [Skype Entreprise d’utilisation de l’appareil](device-usage-report.md) Vous pouvez voir les appareils, y compris les Windows d’exploitation et les appareils mobiles sur lesquels l’application Skype Entreprise est installée et qui l’utilisent pour la messagerie instantanée et les réunions.
    
- [Skype Entreprise activité de l’organisateur de conférences](conference-organizer-activity-report.md) Vous pouvez voir combien de fois vos utilisateurs organisent des conférences qui utilisent la messagerie instantanée, l’audio/la vidéo, le partage d’application, le web, /dial out - tiers et /dial out - Microsoft.
    
- [Skype Entreprise activité de participant à une conférence](conference-participant-activity-report.md) Vous pouvez voir le nombre de conférences audio/vidéo, de messagerie instantanée, de partage d’applications, de web et de mise en conférence audio en cours de participation.
    
- [Skype Entreprise rapport d’activité P2 P2 P2](peer-to-peer-activity-report.md) Vous pouvez voir le nombre d’utilisation de la messagerie instantanée, de l’audio/la vidéo, du partage d’application et du transfert de fichiers par utilisateur.
    
- [Skype Entreprise les utilisateurs bloqués](users-blocked-report.md) Vous pouvez voir les utilisateurs de votre organisation qui ont été bloqués et ne peuvent plus effectuer d’appels PSTN.

- [Skype Entreprise détails de la session](session-details-report.md) Vous pouvez voir des détails sur les expériences d’appels d’un utilisateur individuel.
    
## <a name="related-topics"></a>Sujets associés
[Rapports d’activité dans le Centre d’administration](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
