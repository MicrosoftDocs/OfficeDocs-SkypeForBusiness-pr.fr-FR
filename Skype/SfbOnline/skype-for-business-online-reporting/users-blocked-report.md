---
title: Rapport d'utilisateurs bloqués
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 0ac844b2-1b08-4e5a-addf-03cde7af7a40
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: 'Tout comme d’autres rapports Skype Entreprise, ce rapport vous fournit les détails des activités, y compris l’utilisation PSTN dans votre organisation. '
ms.openlocfilehash: d5fa69d096f5dc5f2af6f8b5a3c04a3155b8cd9e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692329"
---
# <a name="users-blocked-report"></a>Rapport d'utilisateurs bloqués

Le nouveau tableau de bord rapports Skype **Entreprise** vous offre une vue d’ensemble de l’activité sur les produits Skype Entreprise de votre organisation. Il vous permet d’aller plus avant dans les rapports individuels au niveau des produits afin d’offrir des informations plus granulaires sur les activités au sein de chaque produit. Par exemple, vous pouvez utiliser le rapport de blocage des utilisateurs **Skype** Entreprise pour voir les utilisateurs de votre organisation qui ont été bloqués et ne peuvent plus effectuer d’appels PSTN. Tout comme d’autres rapports Skype Entreprise, ce rapport vous fournit les détails des activités, y compris l’utilisation PSTN dans votre organisation.
  
 Consultez la vue [d’ensemble des](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) rapports pour découvrir d’autres rapports disponibles.
  
> [!NOTE]
> Vous pouvez consulter tous les rapports Skype Entreprise lorsque vous vous connectez en tant qu’administrateur au Centre d’administration Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-users-blocked-report"></a>Comment obtenir le rapport de blocage des utilisateurs Skype Entreprise

![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**

- Go to the admin center > **Admin centers** Skype for Business  >  **admin center**  >  **Reports**  >  **Users blocked.**
    
## <a name="interpret-the-skype-for-business-users-blocked-report"></a>Interpréter le rapport de blocage des utilisateurs Skype Entreprise

Vous pouvez afficher les utilisateurs bloqués en regardant chacune des colonnes affichées.
  
Voici une illustration du rapport. 
  
![Rapport sur les utilisateurs bloqués](../images/df50a413-7a51-4340-a59b-3f83de941762.png)

Le tableau présente une répartition de tous les utilisateurs qui sont bloqués et ne peuvent plus effectuer d’appels. Il vous indique tous les utilisateurs qui sont affectés à un système téléphonique ou à une audioconférence. Vous pouvez ajouter ou supprimer des colonnes dans ce tableau.
***
![Numéro 1](../images/sfbcallout1.png)
*   **L’ID d’utilisateur** est la inscription de l’utilisateur.
*   **Le numéro de** téléphone est le numéro affecté à un utilisateur. 
*   **Le temps d’action** de blocage est l’heure (UTC) à partir de quel moment l’utilisateur a été bloqué.
*   **Une action de** blocage est le type d’action qui a été prise pour bloquer l’utilisateur.
*   **La raison du blocage** est la raison pour laquelle l’utilisateur a été bloqué et ne peut plus effectuer d’appels.
***
![Numéro 2](../images/sfbcallout2.png)<br/>
Cliquez pour déplacer une colonne vers **Pour regrouper les informations autour d'une colonne en particulier, faites glisser et déplacez l'en-tête de la colonne ici** si vous souhaitez visualiser toutes les données regroupées dans une ou plusieurs colonnes.
***
![Nombre 3](../images/sfbcallout3.png)<br/>
Vous pouvez également exporter les données du rapport vers un fichier Excel .csv, en cliquant ou en appuyant sur le bouton **Exporter vers Excel**.

Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez trier et filtrer dans le tableau, au sein du rapport proprement dit. Si vous avez plus de 2 000 utilisateurs, vous devrez exporter les données pour pouvoir les trier et les filtrer.
***

## <a name="want-to-see-other-skype-for-business-reports"></a>Autres rapports d'activité Skype Entreprise

- [Rapport d’activité Skype Entreprise](activity-report.md) Vous pouvez voir le nombre d’utilisations, d’organisation et de participations de vos utilisateurs à des conférences.
    
- [Rapport d’utilisation de Skype Entreprise sur des appareils](device-usage-report.md) Vous pouvez voir les appareils, y compris les systèmes d’exploitation Windows et les appareils mobiles sur lesquels l’application Skype Entreprise est installée et qui l’utilisent pour la messagerie instantanée et les réunions.
    
- [Rapport d’activité d’organisateur de conférences Skype Entreprise](conference-organizer-activity-report.md) Vous pouvez voir combien de fois vos utilisateurs organisent des conférences qui utilisent la messagerie instantanée, l’audio/la vidéo, le partage d’application, le web, la conférence rendez-vous ou la mise en conférence tierce et la mise en conférence/mise en conférence - Microsoft.
    
- [Rapport d’activité de participation à des conférences Skype Entreprise](conference-participant-activity-report.md) Vous pouvez voir le nombre de conférences de messagerie instantanée, audio/vidéo, partage d’application, Web et conférences rendez-vous ou mise en conférence téléphonique pour qui il y a des participants.
    
- [Rapport d’activité P2 P2L Skype Entreprise](peer-to-peer-activity-report.md) Vous pouvez voir le nombre d’utilisation de la messagerie instantanée, de l’audio/la vidéo, du partage d’application et du transfert de fichiers par utilisateur.
    
- [Rapport d’utilisation de la PSTN Skype Entreprise](pstn-usage-report.md) Vous pouvez voir le nombre de minutes passées pour des appels entrants/sortants, ainsi que les coûts de ces appels.

- Le rapport sur les pools de [minutes PSTN Skype](pstn-minute-pools-report.md) Entreprise vous permet de consulter le nombre de minutes consommées au cours du mois en cours au sein de votre organisation.

- [Rapport des détails de la session Skype Entreprise](session-details-report.md) Vous pouvez voir des détails sur les expériences d’appels d’un utilisateur individuel.
   
## <a name="related-topics"></a>Sujets associés
[Rapports d’activité dans le Centre d’administration](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 