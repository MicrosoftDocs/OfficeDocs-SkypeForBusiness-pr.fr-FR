---
title: Rapport de détails de session
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: e62ac09f-dfdc-4306-8e06-31349a3b27f0
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
description: Rapports, le nouveau tableau de bord d'Office 365, vous donne une vue d'ensemble de l'activité de tous les produits Office 365 dans votre organisation. Il vous permet d'explorer les rapports au niveau de chaque produit pour obtenir une vue d'ensemble plus précise des activités qu'ils contiennent.
ms.openlocfilehash: 1e72c4f13934961808aa861b1863db2befa6ea49
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="session-details-report"></a>Rapport de détails de session

Le nouveau tableau de bord **Rapports** d'Office 365 vous donne une vue d'ensemble de l'activité de tous les produits Office 365 dans votre organisation. Il vous permet d'explorer les rapports au niveau de chaque produit pour obtenir une vue d'ensemble plus précise des activités qu'ils contiennent. Par exemple, vous pouvez utiliser le rapport **Skype pour plus de détails de Session de l’entreprise** pour afficher des détails sur les expériences d’appel de l’utilisateur.
  
Consultez [vue d’ensemble des rapports](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) pour plusieurs rapports qui sont disponibles.
  
Ce rapport, ainsi que l’autre Skype pour des rapports d’activité vous donnent des détails sur l’activité, y compris les détails de la session au sein de votre organisation. Ces informations sont très utiles lorsque vous étudie, de planification et effectuer d’autres activités des décisions pour votre entreprise et pour configurer les [crédits de Communications](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md).
  
> [!NOTE]
> Vous pouvez accéder à tous les rapports Skype Entreprise lorsque vous vous connectez au centre d'administration d'Office 365 en tant qu'administrateur. 
  
## <a name="how-to-get-to-the-skype-for-business-session-details-report"></a>Comment obtenir le Skype pour le rapport de détails de Session de l’entreprise

1. Accédez au **Centre d’administration Office 365** > **rapports**
    
2. Sélectionnez les **rapports** à partir du menu de gauche, puis cliquez sur **utilisation**.
    
3. Dans la liste **Sélectionnez un rapport**, cliquez sur **Skype pour plus de détails de Session de l’entreprise**.
    
    > [!TIP]
    > Si vous ne voyez pas ce rapport répertorié, passez à **Skype pour le centre d’administration Business** > **rapports** > **Détails de la Session**. 
  
    > [!IMPORTANT]
    > En fonction de l'abonnement Office 365 que vous avez souscrit, tous les produits et les rapports présentés dans cet article ne seront peut-être pas disponibles. 
  
## <a name="interpret-the-skype-for-business-session-details-report"></a>Interpréter le Skype pour le rapport de détails de Session de l’entreprise

Vous pouvez obtenir un affichage dans Skype de l’utilisateur pour les détails de la session en examinant les colonnes qui s’affichent.
  
Voici une illustration du rapport.
  
![Skype pour tableau de bord de rapport de détails de Session de professionnels.](../images/3d87ab39-6eaa-46b5-b5f9-7f54dc987ae0.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/>**Utilisateur de MSN Search par alias** vous permet de rechercher un utilisateur unique et affiche toutes les informations de session de l’utilisateur dans le tableau ci-dessous. 
***
![Numéro 2](../images/sfbcallout2.png)<br/>**Entrée de date heure** vous permet de que vous mettre dans la date de début. Vous pouvez utiliser le calendrier pour sélectionner la date ou entrer la date manuellement. Ce champ doit être renseigné.
***
![Numéro 3](../images/sfbcallout3.png)<br/>**Entrée de date heure** vous permet de que vous mettre dans la date de fin. Vous pouvez utiliser le calendrier pour sélectionner la date ou entrer la date manuellement. Si aucune date de fin n’est définie, la valeur par défaut est de 30 jours à compter de la date de début.
***
![Numéro 4](../images/sfbcallout4.png)<br/>La table affiche une répartition des tous les détails de la session par l’utilisateur. Affiche tous les utilisateurs qui ont Skype pour entreprise affectée ainsi que leurs informations de session. Vous pouvez ajouter ou supprimer des colonnes dans ce tableau. <br/><br/>La table contient les colonnes suivantes pour chaque session :
*    **ID de la boîte de dialogue** est l’ID de l’identificateur unique de la session SIP.
*    **Description des types de support** décrit si la session est une conférence téléphonique ou une session de P2P et le type de support utilisé (Audio/vidéo/Application partage).
*    **Heure de début** est l’heure de début de la session.
*    **Heure de fin** est l’heure de fin de la session.
*    **À partir de l’URI** est l’URI de l’utilisateur ou le service qui a ouvert la session. Peut être vide si l’utilisateur a ouvert la session à partir d’un téléphone RTC.
*    **Pour l’URI** est l’URI de l’utilisateur ou le service qui a été la cible de l’ouverture de session. Dans le cas de la conférence, il s’agit d’URI de l’organisateur. Peut être vide si la cible de la session a été un numéro de téléphone RTC.
*    **À partir de la version client** vous indique la version du client utilisé par l’utilisateur ou le service qui a initié la session et l’Agent utilisateur.
*    **Pour la version client** vous indique la version du client utilisé par l’utilisateur ou le service qui a été la cible de l’ouverture de session et l’Agent utilisateur.
*    **URL de conférence** est l’URL SIP de la conférence, si la session a été une conférence téléphonique. Tous les utilisateurs dans le même appel de conférence aura la même URL de conférence. 
*    **À partir d’un Tel numéro** est le numéro de téléphone a été la cible de la session, le cas échéant. Les derniers chiffres du numéro de téléphone peuvent être remplacés par 'x' pour protéger la confidentialité de l’utilisateur.
*    **À Tel numéro** est le numéro de téléphone a été la cible de la session, le cas échéant. Les derniers chiffres du numéro de téléphone peuvent être remplacés par 'x' pour protéger la confidentialité de l’utilisateur.
*    **À partir de l’Id de point de terminaison** est un GUID unique du point de terminaison utilisé par l’utilisateur de. Utilisé pour déterminer si l’utilisateur communique plusieurs sessions à partir du même point de terminaison. Peut être vide si l’utilisateur est à l’aide d’un téléphone RTC ou si la session a été ouverte à partir d’un service.
*    **Id point de terminaison** est un GUID unique du point de terminaison utilisé par l’utilisateur à. Utilisé pour déterminer si l’utilisateur communique plusieurs sessions à partir du même point de terminaison. Peut être vide si l’utilisateur est à l’aide d’un téléphone RTC, si la session a été ouverte à partir d’un service ou Impossible d’établir une session.
*    **Instance de conf** est un GUID unique pour l’instance de la conférence à l’aide de l’URL de conférence. Les réunions auront la même URL de conférence, mais chaque occurrence de la réunion aura une différence Conf Instance.
*    **De la part de URI** est l’URI de la personne qui a délégué au nom duquel la session est établie. <br/> **Visées par URI** est l’URI de l’utilisateur qui l’a visé l’établissement d’une session.
*    **Code de réponse** est le code de réponse SIP pour l’établissement de la session qui indique si la session a été établie.

Pour chaque session, il existe une table sub avec des données différentes en fonction du scénario. Voici les onglets disponibles dans la table sub pour le champ d’et pour l’utilisateur ou des services.
*    Onglet SESSION affiche les données sur les ordinateurs et les systèmes d’exploitation.
*    Onglet MEDIALINES affiche des informations de connectivité du réseau et de périphérique.
*    Onglet AUDIOSTREAMS montre les données de performance de réseau sur le flux de données audio de la session.
*    Onglet AUDIOCLIENTEVENTS affiche les données sur les problèmes de client détecté perturber l’expérience audio.
*    Onglet AUDIOSIGNALS affiche les données sur le traitement de la session du signal audio.
*    Onglet APPSHARINGSTREAMS montre les données de performance de réseau sur le partage d’application ou le flux de partage de bureau de la session.
*    Onglet VIDEOCLIENTEVENTS affiche les données sur les problèmes de client détecté perturber l’expérience vidéo.
*    Onglet VIDEOSTREAMS montre les données de performance de réseau aux flux de données vidéo de la session.
*    Onglet de détermination d’itinéraire affiche les tronçons réseau collectées via traceroute au cours de la session. Le chemin d’accès réel de support utilisé pour la session peut varier et ces données ne sont disponibles que lorsqu’il y a audio dans la session.
*    Onglet FEEDBACKREPORTS affiche toute fin de données de l’enquête appel fournies par les utilisateurs dans la session.
***
![Numéro 5](../images/sfbcallout5.png)<br/>Cliquez pour déplacer une colonne vers **Pour regrouper les informations autour d'une colonne en particulier, faites glisser et déplacez l'en-tête de la colonne ici** si vous souhaitez visualiser toutes les données regroupées dans une ou plusieurs colonnes. 
***
![Numéro 6](../images/sfbcallout6.png)<br/>Vous pouvez également exporter les données du rapport vers un fichier Excel .csv, en cliquant ou en appuyant sur le bouton **Exporter vers Excel**. <br/><br/> Cela exportera les données de tous les utilisateurs et vous permettra de trier et de filtrer plus simplement pour une analyse ultérieure. Si vous avez moins de 2 000 utilisateurs, vous pouvez trier et filtrer directement dans le tableau du rapport. Si vous avez plus de 2 000 utilisateurs, vous devrez exporter les données pour pouvoir les trier et les filtrer.  
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Autres rapports d'activité Skype Entreprise

- [Skype pour le rapport d’activité commerciale](activity-report.md) Vous pouvez voir combien vos utilisateurs sont à l’aide de peer-to-peer, d’organisation et participé aux sessions de conférence.
    
- [Skype pour le rapport d’utilisation du périphérique Business](device-usage-report.md) Vous pouvez pour voir les périphériques, y compris les systèmes d’exploitation basés sur Windows et les périphériques mobiles qui ont le Skype pour application métier installé et sont en servent pour la messagerie instantanée et des réunions.
    
- [Skype pour le rapport d’activité commerciale conférence organisateur](conference-organizer-activity-report.md) Vous pouvez voir combien vos utilisateurs sont organiser des conférences qui utilisent la messagerie instantanée, audio/vidéo, partage d’applications, Web, accès à distance-in/out - 3ème partie et accès à distance-in/out - Microsoft.
    
- [Skype Business conférence participant rapport d’activité](conference-participant-activity-report.md) Vous pouvez voir combien messagerie instantanée, audio/vidéo, partage d’applications, Web et et les conférences à distance d’entrée/sortie conférence sont participés.
    
- [Skype Business - to-peer rapport d’activité](peer-to-peer-activity-report.md) Vous pouvez voir combien vos utilisateurs sont à l’aide de messagerie instantanée, audio/vidéo, partage d’applications et le transfert de fichiers.
    
- [Skype pour le rapport d’utilisation métier RTPC](pstn-usage-report.md) Vous pouvez voir le nombre de minutes passé dans les appels entrant et sortant et le coût de ces appels.

- [Skype pour les utilisateurs professionnels bloqué rapport](users-blocked-report.md) Vous pouvez voir les utilisateurs de votre organisation qui ont été bloqués d’effectuer les appels RTPC.

- [Skype pour rapport de pools minute RTC de l’entreprise](pstn-minute-pools-report.md) , vous pouvez voir le nombre de minutes consommées au cours du mois en cours au sein de votre organisation.
    
## <a name="related-topics"></a>Rubriques connexes
[Rapports d'activité dans le centre d’administration Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 