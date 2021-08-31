---
title: Rapport détaillé de session
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: e62ac09f-dfdc-4306-8e06-31349a3b27f0
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
description: Le tableau de bord Rapports vous offre une vue d’ensemble de l’activité Microsoft 365 ou Office 365 des produits au sein de votre organisation. Il vous permet d'explorer les rapports au niveau de chaque produit pour obtenir une vue d'ensemble plus précise des activités qu'ils contiennent.
ms.openlocfilehash: 30d6f28c193f303d4cbc21467fb05e260e75a595
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726683"
---
# <a name="session-details-report"></a>Rapport détaillé de session

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Le **tableau de** bord Rapports vous offre une vue d’ensemble de l’activité Microsoft 365 ou Office 365 de votre organisation. Il vous permet d'explorer les rapports au niveau de chaque produit pour obtenir une vue d'ensemble plus précise des activités qu'ils contiennent. Par exemple, vous pouvez utiliser le rapport Skype Entreprise **détails** de la session pour voir des détails sur les expériences d’appels d’un utilisateur individuel.
  
Consultez [la vue d’ensemble](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) des rapports pour découvrir d’autres rapports disponibles.
  
Tout comme les autres rapports de Skype Entreprise vous donnent des détails sur l’activité, y compris les détails des sessions dans votre organisation. Ces informations détaillées sont très utiles pour examiner, planifier et prendre des décisions pour votre entreprise, ainsi que pour définir les [crédits de communication.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Vous pouvez consulter tous les rapports de Skype Entreprise lorsque vous vous connectez en tant qu’administrateur au Centre d’administration Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>Comment obtenir le rapport Skype Entreprise détails de la session

1. Go to the admin center > **Reports**
    
2. Sélectionnez **Rapports** dans le menu de gauche, puis cliquez sur **Utilisation.**
    
3. Dans la liste sous **Sélectionner un rapport,** cliquez Skype Entreprise **détails de la session.**
    
    > [!TIP]
    > Si ce rapport n’est pas répertorié, consultez les Skype Entreprise de la session rapports   >    >  **du Centre d’administration.** 
  
    > [!IMPORTANT]
    > En fonction du Microsoft 365 ou Office 365 votre abonnement, vous ne verrez peut-être pas tous les produits et rapports affichés ici. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpréter le rapport Skype Entreprise détails de la session de travail

Vous pouvez obtenir un affichage des détails de la session de l’Skype Entreprise en regardant chacune des colonnes qui sont affichées.
  
Voici une illustration du rapport.
  
![Skype Entreprise Tableau de bord du rapport Détails de la session.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Numéro 1.](../images/sfbcallout1.png)<br/>**Rechercher un utilisateur par alias** vous permet de rechercher un seul utilisateur et affiche tous les détails de la session de l’utilisateur dans le tableau ci-dessous. 
***
![Numéro 2.](../images/sfbcallout2.png)<br/>**Entrer à partir de l’heure** de début vous permet d’entrer la date de début. Vous pouvez utiliser le calendrier pour sélectionner la date ou entrer la date manuellement. Ce champ doit être rempli.
***
![Numéro 3.](../images/sfbcallout3.png)<br/>**Entrer l’heure de** fin vous permet de mettre la date de fin. Vous pouvez utiliser le calendrier pour sélectionner la date ou entrer la date manuellement. Si aucune date de fin n’est définie, la valeur par défaut est 30 jours à partir de la date de début.
***
![Numéro 4.](../images/sfbcallout4.png)<br/>Le tableau présente une répartition par utilisateur de toutes les détails de la session. Il vous indique tous les utilisateurs Skype Entreprise qui leur ont été affectés ainsi que leurs informations de session. Vous pouvez ajouter ou supprimer des colonnes dans ce tableau. <br/><br/>Le tableau présente les colonnes suivantes pour chaque session :
*    **ID de boîte** de dialogue est l’ID de l’identificateur unique de la session SIP.
*    **La description des types** de médias indique si la session est une conférence téléphonique ou une session P2P et le type de média utilisé (audio/vidéo/partage d’application).
*    **L’heure de** début est l’heure à partir de la session commencée.
*    **L’heure de** fin est la période à l’issue de la session terminée.
*    **L’URI est** l’URI de l’utilisateur ou du service à l’origine de la session. Peut-être vide si l’utilisateur a commencé la session à partir d’un téléphone PSTN.
*    **L’URI est** l’URI de l’utilisateur ou du service qui a été la cible de l’initiation de la session. En cas de conférence, il s’agit de l’URI de l’organisateur. Peut être vide si la cible de la session était un numéro de téléphone PSTN.
*    **À partir de la version du client** vous indique l’Agent utilisateur et la version du client utilisé par l’utilisateur ou le service à l’origine de la session.
*    **La version du client** vous indique l’Agent utilisateur et la version du client utilisé par l’utilisateur ou le service qui a été la cible de l’initiation de la session.
*    **L’URL de** conférence est l’URL SIP de la conférence, s’il s’agit d’une conférence téléphonique. Tous les utilisateurs d’une même conférence auront la même URL de conférence. 
*    **À partir du numéro** de téléphone est le numéro de téléphone qui a été la cible de la session, le cas échéant. Les derniers chiffres du numéro de téléphone peuvent être remplacés par « x » pour protéger la confidentialité de l’utilisateur.
*    **Pour numéro de téléphone** est le numéro de téléphone qui a été la cible de la session, le cas échéant. Les derniers chiffres du numéro de téléphone peuvent être remplacés par « x » pour protéger la confidentialité de l’utilisateur.
*    **À partir de l’ID du point** de terminaison est un GUID unique du point de terminaison utilisé par l’utilisateur De. Permet d’identifier si l’utilisateur communique plusieurs sessions à partir du même point de terminaison. Peut être vide si l’utilisateur utilise un téléphone PSTN ou si la session a été lancée à partir d’un service.
*    **L’ID du point de terminaison** est un GUID unique du point de terminaison utilisé par l’utilisateur À. Permet d’identifier si l’utilisateur communique plusieurs sessions à partir du même point de terminaison. Peut être vide si l’utilisateur utilise un téléphone PSTN, si la session a été initiée à partir d’un service ou si une session n’a pas réussi à établir.
*    **L’instance de** conférence est un GUID unique pour l’instance de la conférence à l’aide de l’URL de la conférence. Les réunions périodiques auront la même URL de conférence, mais chaque instance de la réunion aura une instance de conférence spécifique.
*    **Au nom de URI est** l’URI du délégant pour le compte de la session en cours d’établis. <br/> **Référence par URI est** l’URI de l’utilisateur qui a référent l’établissement d’une session.
*    **Le Code de** réponse est le code de réponse SIP pour l’établissement de la session, qui indique si la session a été établie correctement.

Pour chaque session, il existe une sous-table avec des données différentes disponibles selon le scénario. L’exemple suivant répertorie les onglets disponibles dans le sous-tableau pour les services ou utilisateurs De et À.
*    L’onglet SESSION affiche des données sur les ordinateurs et les systèmes d’exploitation.
*    L’onglet MEDIALINES affiche des informations sur la connectivité réseau et des informations sur l’appareil.
*    L’onglet AUDIOSTREAMS affiche les données de performances réseau relatives aux flux audio impliqués dans la session.
*    L’onglet AUDIOCLIENTEVENTS affiche des données sur les problèmes détectés par le client et impactant l’expérience audio.
*    L’onglet AUDIOSIGNALS affiche des données sur le traitement des signaux audio pour la session.
*    L’onglet APPSHARINGSTREAMS affiche les données de performances réseau relatives au partage d’application ou aux flux de partage de bureau impliqués dans une session.
*    L’onglet VIDEOCLIENTEVENTS affiche des données sur les problèmes détectés par le client et impactant l’expérience vidéo.
*    L’onglet VIDEOSTREAMS affiche les données de performances réseau relatives aux flux vidéo impliqués dans une session.
*    L’onglet TRACEROUTES affiche les sauts de réseau collectés via traceroute pendant la session. Le chemin multimédia réel utilisé pour la session peut varier et ces données ne sont disponibles qu’en cas d’audio dans la session.
*    L’onglet FEEDBACKREPORTS affiche les données d’enquête de fin d’appel fournies par les utilisateurs au cours de la session.
***
![Numéro 5.](../images/sfbcallout5.png)<br/>Cliquez pour déplacer une colonne vers **Pour regrouper les informations autour d'une colonne en particulier, faites glisser et déplacez l'en-tête de la colonne ici** si vous souhaitez visualiser toutes les données regroupées dans une ou plusieurs colonnes. 
***
![Numéro 6.](../images/sfbcallout6.png)<br/>Vous pouvez également exporter les données du rapport vers un fichier Excel .csv, en cliquant ou en appuyant sur le bouton **Exporter vers Excel**. <br/><br/> Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez trier et filtrer directement dans le tableau du rapport. Si vous avez plus de 2 000 utilisateurs, vous devrez exporter les données pour pouvoir les trier et les filtrer.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Vous souhaitez voir d’autres Skype Entreprise rapports d’état ?

- [Skype Entreprise d’activité de l’entreprise](activity-report.md) Vous pouvez consulter le nombre d’utilisations, d’organisation et de participations de vos utilisateurs à des conférences.
    
- [Skype Entreprise d’utilisation de l’appareil](device-usage-report.md) Vous pouvez voir les appareils, y compris les Windows d’exploitation et les appareils mobiles sur lesquels l’application Skype Entreprise est installée et qui l’utilisent pour la messagerie instantanée et les réunions.
    
- [Skype Entreprise activité de l’organisateur de conférences](conference-organizer-activity-report.md) Vous pouvez voir combien de fois vos utilisateurs organisent des conférences qui utilisent la messagerie instantanée, l’audio/la vidéo, le partage d’application, le web, la conférence rendez-vous ou la mise en conférence tierce et la mise en conférence/mise en conférence - Microsoft.
    
- [Skype Entreprise activité de participant à une conférence](conference-participant-activity-report.md) Vous pouvez voir le nombre de conférences de messagerie instantanée, audio/vidéo, partage d’application, Web et conférences rendez-vous ou mise en conférence téléphonique pour qui il y a des participants.
    
- [Skype Entreprise rapport d’activité P2 P2 P2](peer-to-peer-activity-report.md) Vous pouvez voir le nombre d’utilisation de la messagerie instantanée, de l’audio/la vidéo, du partage d’application et du transfert de fichiers par utilisateur.
    
- [Skype Entreprise d’utilisation PSTN](pstn-usage-report.md) Vous pouvez voir le nombre de minutes passées pour des appels entrants/sortants, ainsi que les coûts de ces appels.

- [Skype Entreprise les utilisateurs bloqués](users-blocked-report.md) Vous pouvez voir les utilisateurs de votre organisation qui ont été bloqués et ne peuvent plus effectuer d’appels PSTN.

- Skype Entreprise des pools de [minutes PSTN](pstn-minute-pools-report.md) vous indiquent le nombre de minutes consommées au cours du mois en cours au sein de votre organisation.
    
## <a name="related-topics"></a>Sujets associés
[Rapports d’activité dans le Centre d’administration](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
