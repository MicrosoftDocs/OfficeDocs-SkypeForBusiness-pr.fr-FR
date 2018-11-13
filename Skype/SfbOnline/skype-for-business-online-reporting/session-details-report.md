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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Rapports, le nouveau tableau de bord d'Office 365, vous donne une vue d'ensemble de l'activité de tous les produits Office 365 dans votre organisation. Il vous permet d'explorer les rapports au niveau de chaque produit pour obtenir une vue d'ensemble plus précise des activités qu'ils contiennent.
ms.openlocfilehash: 46a44a61777cdd4d52b9899429b4a17ffe6ad7cb
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293721"
---
# <a name="session-details-report"></a>Rapport détaillé de session

**Rapports**, le nouveau tableau de bord d'Office 365, vous donne une vue d'ensemble de l'activité de tous les produits Office 365 dans votre organisation. Il vous permet d'explorer les rapports au niveau de chaque produit pour obtenir une vue d'ensemble plus précise des activités qu'ils contiennent. Par exemple, vous pouvez utiliser le rapport **Skype pour plus d’informations de Session Business** pour afficher plus d’informations sur des expériences utilisateur appel.
  
Consultez la rubrique [vue d’ensemble des rapports](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) pour plusieurs rapports qui sont disponibles.
  
Ce rapport, ainsi que l’autres Skype pour les rapports d’entreprise vous donnent plus d’informations sur l’activité, notamment des informations de session au sein de votre organisation. Ces informations sont très utiles lorsque vous analyse, la planification et l’émission d’autres activités décisions pour votre organisation et de configuration [Communications générique](/microsoftteams/what-are-communications-credits).
  
> [!NOTE]
> Vous pouvez afficher tous les rapports Skype Entreprise lorsque vous vous connectez en tant qu'administrateur du centre d'administration Office 365. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>Comment obtenir le Skype pour le rapport de détails de Session de l’entreprise

1. Accéder au **Centre d’administration Office 365** > **rapports**
    
2. Sélectionnez les **rapports** dans le menu de gauche, puis cliquez sur **l’utilisation**.
    
3. Dans la liste sous **Sélectionnez un rapport**, cliquez sur **Skype pour plus d’informations de Session de l’entreprise**.
    
    > [!TIP]
    > Si vous ne voyez pas ce rapport répertorié, accédez à **Skype pour le centre d’administration de Business** > **rapports** > **Détails de la Session**. 
  
    > [!IMPORTANT]
    > En fonction de l'abonnement Office 365 que vous avez souscrit, tous les produits et les rapports présentés dans cet article ne seront peut-être pas disponibles. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpréter le Skype pour le rapport de détails de Session de l’entreprise

Vous pouvez obtenir une vue dans Skype de l’utilisateur pour les détails de la session en regardant chacune des colonnes qui sont affichés.
  
Voici une illustration du rapport.
  
![Skype pour le tableau de bord de rapport de détails de Session Business.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**Utilisateur de recherche par alias** vous permet de rechercher un utilisateur unique et affiche tous les détails de la session de l’utilisateur dans le tableau ci-dessous. 
***
![Numéro 2](../images/sfbcallout2.png)<br/>**Entrée de date heure** vous permet de que vous placer dans la date de début. Vous pouvez utiliser le calendrier pour sélectionner la date ou entrez la date manuellement. Ce champ doit être rempli.
***
![Nombre 3](../images/sfbcallout3.png)<br/>Permet **d’entrée pour date heure** que vous placer dans la date de fin. Vous pouvez utiliser le calendrier pour sélectionner la date ou entrez la date manuellement. Si aucune date de fin n’est définie, la valeur par défaut est 30 jours à partir de la date de début.
***
![Numéro 4](../images/sfbcallout4.png)<br/>Le tableau présente une répartition des tous les détails de session par utilisateur. Affiche tous les utilisateurs qui ont Skype pour les entreprises affecté et leurs informations de session. Vous pouvez ajouter ou supprimer des colonnes dans ce tableau. <br/><br/>Le tableau comporte les colonnes suivantes pour chaque session :
*    **ID de la boîte de dialogue** est l’ID de l’identificateur unique de la session SIP.
*    **Description des types de médias** indique si la session est une téléconférence ou une session P2P et le type de média utilisé (partage Audio/vidéo/Application).
*    **Heure de début** est l’heure de début de la session.
*    **Heure de fin** est l’heure de fin de la session.
*    **À partir de l’URI** est l’URI de l’utilisateur ou le service qui a initié la session. Peut être vide si l’utilisateur a démarré la session à partir d’un téléphone RTC.
*    **Pour l’URI** est l’URI de l’utilisateur ou le service qui a été la cible de l’ouverture de session. Dans le cas de la conférence, il s’agit de l’URI de l’organisateur. Peut être vide si la cible de la session a été un numéro de téléphone PSTN.
*    **À partir de la version du client** vous indique l’Agent utilisateur et la version du client utilisé par l’utilisateur ou le service qui a initié la session.
*    **Pour la version du client** vous indique l’Agent utilisateur et la version du client utilisé par l’utilisateur ou le service qui a été la cible de l’ouverture de session.
*    **URL de la conférence** est l’URL SIP de la conférence, si la session a été une téléconférence. Tous les utilisateurs dans le même appel de conférence aura la même URL de conférence. 
*    **À partir d’un Tel numéro** est le numéro de téléphone qui était la cible de la session, le cas échéant. Les derniers chiffres du numéro de téléphone peuvent être remplacés par « x » pour protéger la confidentialité des utilisateurs.
*    **Nombre à Tel** est le numéro de téléphone qui était la cible de la session, le cas échéant. Les derniers chiffres du numéro de téléphone peuvent être remplacés par « x » pour protéger la confidentialité des utilisateurs.
*    **À partir du point de terminaison Id** est un GUID unique du point de terminaison utilisé par l’utilisateur. Utilisé pour déterminer si l’utilisateur communique plusieurs sessions à partir du même point de terminaison. Peut être vide si l’utilisateur a recours à un téléphone RTC ou si la session a été lancée à partir d’un service.
*    **Id du point de terminaison** est un GUID unique du point de terminaison utilisé par l’utilisateur à. Utilisé pour déterminer si l’utilisateur communique plusieurs sessions à partir du même point de terminaison. Peut être vide si l’utilisateur a recours à un téléphone RTC, si la session a été lancée à partir d’un service ou Impossible d’établir une session.
*    **Instance de conférence** est un GUID unique pour l’instance de la conférence à l’aide de l’URL de conférence. Les réunions périodiques aura la même URL de conférence, mais chaque instance de la réunion aura une différence Instance Conf.
*    **URI de la part** d’est l’URI de la personne au nom duquel la session est établie. <br/> **Référencé par l’URI** est l’URI de l’utilisateur ayant référencé l’établissement d’une session.
*    **Code de réponse** est le code de réponse SIP pour l’établissement de la session qui indique si la session a été établie.

Pour chaque session, une table sub avec des données différentes est disponible en fonction du scénario. Suit répertorie les onglets disponibles dans le tableau sub pour le champ d’et à l’utilisateur ou les services.
*    Onglet SESSION affiche les données sur les ordinateurs et les systèmes d’exploitation.
*    Onglet MEDIALINES affiche les informations de connectivité réseau et de périphérique.
*    Onglet AUDIOSTREAMS présente les données de performances réseau sur les flux audio impliquées dans la session.
*    Onglet AUDIOCLIENTEVENTS affiche les données sur les problèmes de détection de client ayant un impact sur l’expérience audio.
*    Onglet AUDIOSIGNALS affiche les données sur le traitement de la session du signal audio.
*    Onglet APPSHARINGSTREAMS indique les données de performances sur le partage d’application ou le flux de partage du bureau impliquées dans la session.
*    Onglet VIDEOCLIENTEVENTS affiche les données sur les problèmes de détection de client ayant un impact sur l’expérience vidéo.
*    Onglet VIDEOSTREAMS présente les données de performances réseau sur les flux vidéo impliquées dans la session.
*    Onglet de détermination d’itinéraire affiche les tronçons réseau collectées via traceroute pendant la session. Le chemin d’accès réel media utilisé pour la session peut varier et ces données ne sont disponibles que lorsqu’il est audio dans la session.
*    Onglet FEEDBACKREPORTS affiche toute fin de données d’enquête appel fournies par les utilisateurs dans la session.
***
!["Nombre 5"](../images/sfbcallout5.png)<br/>Cliquez pour déplacer une colonne vers **Pour regrouper les informations autour d'une colonne en particulier, faites glisser et déplacez l'en-tête de la colonne ici** si vous souhaitez visualiser toutes les données regroupées dans une ou plusieurs colonnes. 
***
![Numéro 6](../images/sfbcallout6.png)<br/>Vous pouvez également exporter les données du rapport vers un fichier Excel .csv, en cliquant ou en appuyant sur le bouton **Exporter vers Excel**. <br/><br/> Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez trier et filtrer directement dans le tableau du rapport. Si vous avez plus de 2 000 utilisateurs, vous devrez exporter les données pour pouvoir les trier et les filtrer.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Autres rapports d'activité Skype Entreprise

- [Skype pour le rapport des activités](activity-report.md) Vous pouvez voir combien vos utilisateurs sont à l’aide d’égal à égal, organisé et participé à des sessions de conférence.
    
- [Skype pour le rapport d’utilisation des périphériques Business](device-usage-report.md) Vous pouvez pour voir les périphériques, y compris les systèmes d’exploitation Windows et les appareils mobiles qui ont le Skype pour l’application de gestion installés et utilisent pour la messagerie instantanée et réunions.
    
- [Skype Business conférence organisateur rapport d’activité](conference-organizer-activity-report.md) Vous pouvez voir combien vos utilisateurs sont organiser des conférences qui utilisent la messagerie instantanée, audio/vidéo, partage d’applications, le site Web, dial-in/out - 3ème partie et dial-in/out - Microsoft.
    
- [Skype Business conférence participant rapport d’activité](conference-participant-activity-report.md) Vous pouvez voir combien par messagerie instantanée, audio/vidéo, partage d’applications, Web et et les conférences rendez-vous dans/conférence sont participés.
    
- [Skype pour le rapport des activités d’égal à égal professionnels](peer-to-peer-activity-report.md) Vous pouvez voir combien vos utilisateurs sont à l’aide de messagerie instantanée, audio/vidéo, partage d’application et de transfert de fichiers.
    
- [Skype pour le rapport d’utilisation PSTN Business](pstn-usage-report.md) Vous pouvez voir le nombre de minutes passé dans les appels entrants et sortants et le coût de ces appels.

- [Skype pour les utilisateurs professionnels bloqués de rapport](users-blocked-report.md) Vous pouvez voir les utilisateurs de votre organisation qui ont été bloqués à partir de l’émission d’appels PSTN.

- [Skype pour rapport de pools minute Business PSTN](pstn-minute-pools-report.md) , vous pouvez voir le nombre de minutes consommées au cours du mois au sein de votre organisation.
    
## <a name="related-topics"></a>Rubriques connexes
[Rapports d'activité dans le centre d’administration Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 