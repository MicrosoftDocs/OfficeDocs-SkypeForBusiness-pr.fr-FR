---
title: Mobile client feature comparison for Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Summary: Review the feature support for the mobile client while planning for Skype for Business Server 2015.'
ms.openlocfilehash: 4287c5baf0642fab9d55d291470b2352f3da5932
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Mobile client feature comparison for Skype for Business
 
**Summary:** Review the feature support for the mobile client while planning for Skype for Business Server 2015.
  
This article compares the features and capabilities among Skype for Business mobile clients and the Skype for Business desktop client in the following categories:
  
- Connexion, notifications Push et fonctionnalités générales
    
- Présence avancée
    
- Contacts et groupes de contacts
    
- Messagerie instantanée
    
- Skype for Business to Skype for Business audio and video
    
- Téléconférence
    
- Téléphonie
    
- Utilisateurs externes
    
- Archivage et conformité
    
-  Authentification moderne
    
The following tables list the features that are available to Skype for Business users in an on-premises deployment of Skype for Business Server 2015. The same features are also available to Skype for Business Online and Microsoft Office 365 users, unless otherwise indicated in the table footnotes.
  
> [!NOTE]
> For online help and resources for end users, see [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> To compare the features available in other Skype for Business clients, see [Desktop client feature comparison for Skype for Business](desktop-feature-comparison.md). 
  
## <a name="sign-in-push-notifications-and-general-features"></a>Connexion, notifications Push et fonctionnalités générales

 
 | Fonctionnalité  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business session remains signed in  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Prise en charge des notifications Push  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714;|&#x2714;|
|Possibilité de mettre en cache les informations de comptes de plusieurs utilisateurs sur le même appareil  <br/> |&#x2714;||||
|Lecteur d’écran/voix off  <br/> |&#x2714;|&#x2714; &#x2777;           English only  <br/> |&#x2714;|&#x2714;|
|Utilisation d’un clavier externe pour l’accessibilité  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Prise en charge du Programme d’amélioration du produit Microsoft  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  On Windows Phone, Skype for Business signs out automatically after a period of inactivity, as follows:
  
- If the user has enabled push notifications, Skype for Business signs out after 10 days of inactivity.
    
- If the user has not enabled push notifications, Skype for Business signs out as soon as the user leaves the app.
    
On iOS devices, Skype for Business signs out automatically after the mobile client has not contacted the server for 10 days due to loss of network connectivity or other issues.
  
 &#x2777;  In app only.
  
 &#x2778;  Notifications are available when the app is running in the background.
  
## <a name="enhanced-presence-support"></a>Prise en charge de la présence avancée


 | Fonctionnalité  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Publier et afficher le statut  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher le statut basé sur les informations de disponibilité du calendrier  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher les notes de statut et les messages de notification d'absence du bureau  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ajouter un emplacement personnalisé  <br/> |&#x2714;||||
|Ajouter une note personnalisée  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Publier le statut d’après les informations de disponibilité du calendrier   <br/> |&#x2714; &#x2776; ||||
|Définir le statut de présence manuel (Occupé, Ne pas déranger, etc.)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  Skype for Business mobile clients do not update a user's presence based on the user's free/busy calendar information. If a mobile client user is also signed in to the Skype for Business desktop client, the desktop client updates the user's presence based on the user's free/busy calendar information. If the user is signed in to a mobile client only, the user's presence does not update based on free/busy calendar information.
  
## <a name="contacts-and-contact-groups-support"></a>Prise en charge des contacts et groupes de contacts


 | Fonctionnalité  | Skype for Business Lync 2013 desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Afficher la liste des contacts  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher les groupes de contacts  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher les groupes de contacts fréquents  <br/> |&#x2714;||||
|Modifier la liste des contacts  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ajouter une balise à des contacts pour les alertes de changement de statut  <br/> |&#x2714;||||
|Contrôler les niveaux de confidentialité  <br/> |&#x2714;||||
|Effectuer des recherches dans le carnet d'adresses de l'entreprise  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Effectuer des recherches dans les listes de contacts  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Gérer des groupes de contacts  <br/> |&#x2714;|||&#x2714;|
|Développer des groupes de distribution  <br/> |&#x2714;|&#x2714;||&#x2714;|
|Rechercher des groupes Response Group  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|Afficher ou masquer les photos des contacts  <br/> |&#x2714;|&#x2714;|||
|Épingler un contact sur votre écran d’accueil  <br/> ||&#x2714;|||
   
 &#x2776;  Not available to Skype for Business Online and/or Office 365 users.
  
## <a name="instant-messaging-support"></a>Prise en charge de la messagerie instantanée


 | Fonctionnalité  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Démarrer une conversation par messagerie instantanée avec un contact  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participer à une conversation par messagerie instantanée à plusieurs  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Inviter d’autres personnes à partir d’une fenêtre de conversation  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher les conversations actuelles  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Passer d’une conversation par messagerie instantanée à une autre  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Consigner automatiquement les conversations par messagerie instantanée dans Exchange  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Envoyer une conversation par messagerie instantanée sous forme de message électronique  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Écrire un courrier électronique à un contact  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher les invitations de messagerie instantanée manquées  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Vibrer en cas de message instantané entrant  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 &#x2776;  This device vibrates every time an IM is received even if the current message in the IM conversation is displayed
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype for Business to Skype for Business audio and video


 | Fonctionnalité  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business-to-Skype for Business voice  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Skype for Business-to-Skype for Business video  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> Sur un appareil mobile, la vidéo nécessite, par défaut, une connexion WiFi.  
  
## <a name="conferencing-support"></a>Prise en charge de la conférence


 | Fonctionnalité  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Cliquer sur un lien dans le rappel de réunion pour participer à une réunion vidéo ou VoIP  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participer à une conversation par messagerie instantanée à plusieurs  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Utiliser la conférence d’appel sortant (le serveur appelle l’appareil mobile)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Utiliser l’audioconférence rendez-vous  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualiser la vidéo de la réunion  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher une vidéo à plusieurs (vue galerie)  <br/> |&#x2714;||||
|Patienter dans la salle d’attente de réunion  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Utiliser des commandes de présentateur lors des réunions  <br/> |&#x2714;||||
|Accéder à une liste de réunion détaillée pour les conférences audio  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Accéder à une liste de réunion détaillée pour les conférences par messagerie instantanée  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Partager le Bureau ou un programme  <br/> |&#x2714;||||
|View shared desktop or program (VbSS or RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Afficher les fichiers PowerPoint partagés  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Charger et présenter des fichiers PowerPoint  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Utiliser des outils de réunion (utiliser un tableau blanc, mener des enquêtes, partager des fichiers)  <br/> |&#x2714;||||
|Parcourir une liste de vos réunions  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Join a meeting even if you don't have a Skype for Business account  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher plus d’informations sur les participants à la réunion  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Commencer une conversation de groupe non planifiée avec plusieurs participants directement de votre client ou appareil   <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  For Office 365 users, this feature requires Enterprise Voice, which is part of the E5 license.
  
 &#x2777;  Requires a WiFi connection by default.
  
## <a name="telephony-support"></a>Prise en charge de la téléphonie


 | Fonctionnalité  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|In Skype for Business, tap the call icon to call a contact  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Transférer un appel  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Transfert consultatif  <br/> |&#x2714; &#x2778; ||||
|Gérer le transfert d'appel  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Gérer les paramètres d'appel d'équipe  <br/> |&#x2714; &#x2776; ||||
|Gérer les délégués  <br/> |&#x2714; &#x2776; ||||
|Appeler un groupe Response Group  <br/> |&#x2714; &#x2776; ||||
|Prendre en charge des services d’urgence  <br/> |&#x2714; &#x2777; ||||
|Passer un appel pour le compte d'un autre contact (scénario responsable/délégué)  <br/> |&#x2714; &#x2776; ||||
|Handle another contact's calls, if configured as a delegate  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Utiliser l’appel via le Bureau   <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|Accéder à la messagerie vocale  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Use the keypad in Skype for Business  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776;  Available to Skype for Business Online and/or Office 365 E5 users, and users homed on Skype for Business Server 2015 or Lync 2013 with Enterprise Voice enabled.
  
 &#x2777;  For Skype for Business Online and/or Office 365 users, this feature is supported by Microsoft partners.
  
 &#x2778;  Windows Desktop client only.
  
## <a name="external-user-support"></a>Prise en charge des utilisateurs externes


 | Fonctionnalité  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Démarrer une conversation par messagerie instantanée avec un contact public  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Démarrer une conversation par messagerie instantanée avec un contact fédéré  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Mener des appels à deux avec des utilisateurs externes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Mener des appels à plusieurs avec des utilisateurs externes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Use Call via Work to reach a federated contact on their mobile phone by calling their published work number  &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776;  By default, federated users are assigned the External Contacts privacy relationship. Pour que vous puissiez joindre un contact fédéré sur son téléphone mobile en composant son numéro professionnel publié, le contact fédéré doit manuellement vous assigner le niveau de confidentialité Collègues.
  
## <a name="address-book-integration"></a>Intégration du carnet d’adresses


 | Fonctionnalité  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Appeler les contacts du carnet d’adresses de l’appareil  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Make Skype for Business calls to contacts directly from device address book  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Prise en charge de l’archivage et de la conformité


 | Fonctionnalité  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Fournir l’archivage côté client  <br/> |&#x2714;||||
|Fournir l’enregistrement côté client  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776;  Not available to Skype for Business Online and/or Office 365 users.
  
## <a name="modern-authentication"></a>Authentification moderne

Ce tableau couvre les fonctionnalités qui requièrent la prise en charge de l'authentification moderne.
  
Modern authentication also requires a topology described in [Skype for Business topologies supported with Modern Authentication](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Fonctionnalité  | Skype for Business desktop client  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Authentification moderne  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Authentification multifacteur  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Authentification avec certificat  <br/> |&#x2714;(Domain-joined device only)  <br/> ||&#x2714;|&#x2714;|
|Mobile Application Management (via Intune)  <br/> |||&#x2714;|&#x2714;|
   

