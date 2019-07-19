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
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Rapports, le nouveau tableau de bord d'Office 365, vous donne une vue d'ensemble de l'activité de tous les produits Office 365 dans votre organisation. Il vous permet d'explorer les rapports au niveau de chaque produit pour obtenir une vue d'ensemble plus précise des activités qu'ils contiennent.
ms.openlocfilehash: faee3d0a4f2228ddc32121bf85cc2f6b3018f2cc
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/18/2019
ms.locfileid: "35793061"
---
# <a name="session-details-report"></a>Rapport détaillé de session

Le nouveau tableau de bord **Rapports** d'Office 365 vous donne une vue d'ensemble de l'activité de tous les produits Office 365 dans votre organisation. Il vous permet d'explorer les rapports au niveau de chaque produit pour obtenir une vue d'ensemble plus précise des activités qu'ils contiennent. Par exemple, vous pouvez utiliser le rapport Détails de la **session Skype entreprise** pour en savoir plus sur les expériences d’appel des utilisateurs individuels.
  
Consultez la [vue d’ensemble des rapports](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) pour plus d’informations sur les rapports disponibles.
  
Ce rapport, ainsi que les autres rapports Skype entreprise fournissent des informations sur les activités, y compris les détails de la session au sein de votre organisation. Ces informations sont très utiles lorsque vous effectuez des recherches, planifiez et organisez d’autres décisions professionnelles pour votre organisation et que vous configurez des [crédits de communication](/microsoftteams/what-are-communications-credits).
  
> [!NOTE]
> Vous pouvez afficher tous les rapports Skype entreprise lorsque vous vous connectez en tant qu’administrateur au centre d’administration Microsoft 365. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>Comment obtenir le rapport Détails de la session Skype entreprise

1. Accédez au centre d’administration > **rapports**
    
2. Dans le menu de gauche, sélectionnez **rapports** , puis cliquez sur **utilisation**.
    
3. Dans la liste sous **Sélectionner un rapport**, cliquez sur **Détails de la session Skype entreprise**.
    
    > [!TIP]
    > Si ce rapport n’est pas répertorié, reportez-vous à la rubrique**rapports** > **** du >  **Centre d’administration Skype entreprise**. 
  
    > [!IMPORTANT]
    > En fonction de l'abonnement Office 365 que vous avez souscrit, tous les produits et les rapports présentés dans cet article ne seront peut-être pas disponibles. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpréter le rapport Détails de la session Skype entreprise

Vous pouvez afficher les détails de la session Skype entreprise d’un utilisateur en consultant chacune des colonnes qui sont affichées.
  
Voici une illustration du rapport.
  
![Tableau de bord de rapport Détails de session Skype entreprise.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>L’option **Rechercher un utilisateur par alias** vous permet de rechercher un utilisateur unique et d’afficher tous les détails de la session de l’utilisateur dans le tableau ci-dessous. 
***
![Numéro 2](../images/sfbcallout2.png)<br/>**Entrée de date** vous permet d’entrer la date de début. Vous pouvez utiliser le calendrier pour sélectionner la date ou entrer la date manuellement. Ce champ doit être rempli.
***
![Nombre 3](../images/sfbcallout3.png)<br/>**Entrée pour date** permet d’entrer la date de fin. Vous pouvez utiliser le calendrier pour sélectionner la date ou entrer la date manuellement. Si aucune date de fin n’est définie, la valeur par défaut est 30 jours à partir de la date de début.
***
![Numéro 4](../images/sfbcallout4.png)<br/>Le tableau suivant présente une répartition des détails relatifs à la session par utilisateur. Cette opération montre tous les utilisateurs qui disposent de Skype entreprise et leurs informations de session. Vous pouvez ajouter ou supprimer des colonnes dans ce tableau. <br/><br/>La table contient les colonnes suivantes pour chaque session:
*    **ID de boîte de dialogue** est l’ID identifiant unique de la session SIP.
*    **Description** du type de média décrit si la session est une conférence téléphonique ou une session P2P et le type de média utilisé (audio/vidéo/partage d’application).
*    **Heure de début** représente l’heure de démarrage de la session.
*    **Heure de fin** correspond à l’heure de fin de la session.
*    L’URI est l’URI de l’utilisateur ou du service **à** l’origine de la session. Est-il possible d’être vide si l’utilisateur a lancé la session à partir d’un téléphone RTC.
*    **To URI** est l’URI de l’utilisateur ou du service qui était la cible de l’initiation de la session. Dans le cas de la Conférence, il s’agit de l’URI de l’organisateur. Est susceptible d’être vide si la cible de la session est un numéro de téléphone PSTN.
*    **À partir de la version du client** indique l’agent utilisateur et la version du client utilisée par l’utilisateur ou le service à l’origine de la session.
*    **Vers la version client** indique l’agent utilisateur et la version du client utilisée par l’utilisateur ou le service qui était la cible de l’initiation de la session.
*    **URL** de la Conférence est l’URL SIP de la Conférence, si celle-ci est une conférence téléphonique. Tous les utilisateurs de la même conférence peuvent utiliser la même URL de conférence. 
*    **Depuis numéro de** téléphone est le numéro de téléphone ciblé dans la session, le cas échéant. Les derniers chiffres du numéro de téléphone sont remplacés par «x» pour protéger la confidentialité de l’utilisateur.
*    **Par numéro de** téléphone est le numéro de téléphone ciblé dans la session, le cas échéant. Les derniers chiffres du numéro de téléphone sont remplacés par «x» pour protéger la confidentialité de l’utilisateur.
*    **From Endpoint ID** est un GUID unique du point de terminaison utilisé par l’utilisateur de. Permet de déterminer si l’utilisateur communique plusieurs sessions à partir du même point de terminaison. Peut être vide si l’utilisateur utilise un téléphone RTC ou s’il a initié une session à partir d’un service.
*    **Pour ID de point de terminaison** , il s’agit d’un GUID unique du point de terminaison utilisé par l’utilisateur à. Permet de déterminer si l’utilisateur communique plusieurs sessions à partir du même point de terminaison. Est peut-être vide si l’utilisateur utilise un téléphone RTC, si elle a été lancée à partir d’un service, ou s’il n’a pas réussi à établir une session.
*    L' **instance de conf** est un GUID unique pour l’instance de la Conférence à l’aide de l’URL de la Conférence. Les réunions périodiques ont la même URL de conférence, mais chaque instance de la réunion est dotée d’une instance de la distinction.
*    **Pour le compte d’URI** figure l’URI de la personne qui a créé le nom de la session. <br/> **URL désignée par URI** est l’URI de l’utilisateur qui a expertisé l’établissement d’une session.
*    **Code de réponse** correspond au code de réponse SIP pour l’établissement de la session qui indique si la session a été correctement établie.

Pour chaque session, il existe une sous-table avec différentes données disponibles selon le scénario. Le tableau suivant répertorie les onglets disponibles dans la sous-table correspondant aux utilisateurs et aux services from et to.
*    L’onglet SESSION affiche des données relatives aux ordinateurs et aux systèmes d’exploitation.
*    L’onglet MEDIALINES affiche les informations de connectivité réseau et les informations sur l’appareil.
*    L’onglet AUDIOSTREAMS affiche les données de performances réseau relatives aux flux audio impliqués dans la session.
*    L’onglet AUDIOCLIENTEVENTS affiche les données sur le client détecté des problèmes affectant l’interface audio.
*    L’onglet AUDIOSIGNALS affiche les données relatives au traitement du signal audio de la session.
*    L’onglet APPSHARINGSTREAMS affiche des données de performances réseau relatives aux flux de partage d’application ou de partage de bureau impliqués dans une session.
*    L’onglet VIDEOCLIENTEVENTS affiche les données relatives aux problèmes détectés dans l’interface vidéo.
*    L’onglet VIDEOSTREAMS affiche des données de performances réseau relatives aux flux vidéo impliqués dans la session.
*    L’onglet TRACEROUTE montre les tronçons du réseau collectés par le biais de traceroute lors de la session. Le chemin d’accès multimédia réel utilisé pour la session peut varier et ces données ne sont disponibles que lorsque la session utilise le son.
*    L’onglet FEEDBACKREPORTS affiche la fin des données d’enquête fournies par les utilisateurs de la session.
***
!["Nombre 5"](../images/sfbcallout5.png)<br/>Cliquez pour déplacer une colonne vers **Pour regrouper les informations autour d'une colonne en particulier, faites glisser et déplacez l'en-tête de la colonne ici** si vous souhaitez visualiser toutes les données regroupées dans une ou plusieurs colonnes. 
***
![Numéro 6](../images/sfbcallout6.png)<br/>Vous pouvez également exporter les données du rapport vers un fichier Excel .csv, en cliquant ou en appuyant sur le bouton **Exporter vers Excel**. <br/><br/> Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez trier et filtrer directement dans le tableau du rapport. Si vous avez plus de 2 000 utilisateurs, vous devrez exporter les données pour pouvoir les trier et les filtrer.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Vous voulez afficher les autres rapports Skype entreprise?

- [Rapport d’activité Skype entreprise](activity-report.md) Vous pouvez visualiser le nombre d’organisations, de participations et de sessions d’égal à égal de conférences par utilisateur.
    
- [Rapport sur l’utilisation des appareils Skype entreprise](device-usage-report.md) Vous pouvez voir les appareils tels que les systèmes d’exploitation Windows et les appareils mobiles sur lesquels l’application Skype entreprise est installée et qui s’en servent pour la messagerie instantanée et les réunions.
    
- [Rapport d’activité d’organisateur de conférences Skype entreprise](conference-organizer-activity-report.md) Vous pouvez visualiser le nombre de conférences de vos utilisateurs à l’aide de la messagerie instantanée, de l’audio/la vidéo, du partage d’applications, du Web, de la Conférence rendez-vous/du tiers et de la Conférence rendez-vous.
    
- [Rapport d’activité de participation à des conférences Skype entreprise](conference-participant-activity-report.md) Vous pouvez voir le nombre de participants à la messagerie instantanée, de l’audio/la vidéo, du partage d’applications, du Web et des conférences rendez-vous et des conférences rendez-vous.
    
- [Rapport d’activité d’égal à égal Skype entreprise](peer-to-peer-activity-report.md) Vous pouvez visualiser le nombre d’utilisation de la messagerie instantanée, de l’audio/la vidéo, du partage d’applications et du transfert de fichiers par utilisateur.
    
- [Rapport d’utilisation de la Conférence RTC Skype entreprise](pstn-usage-report.md) Vous pouvez voir le nombre de minutes passées pour des appels entrants/sortants et le coût de ces appels.

- [Rapport de blocage d’utilisateurs Skype entreprise](users-blocked-report.md) Vous pouvez afficher les utilisateurs de votre organisation qui ont été bloqués et ne peuvent plus passer d’appels RTC.

- [Rapport de pools de minutes RTC Skype entreprise](pstn-minute-pools-report.md) vous pouvez voir le nombre de minutes consommées pendant le mois en cours au sein de votre organisation.
    
## <a name="related-topics"></a>Voir aussi
[Rapports d’activité dans le centre d’administration](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 