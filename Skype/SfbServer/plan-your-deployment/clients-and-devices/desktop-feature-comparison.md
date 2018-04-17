---
title: Comparaison des fonctionnalités des clients de bureau pour Skype Entreprise
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
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 'Summary: Skype for Business Server 2015 or Skype for Business Online administrators can use these tables to understand what features are supported on which clients.'
ms.openlocfilehash: 0ce6457bea83c775ca5cf9373a5724f95785ddb1
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="desktop-client-feature-comparison-for-skype-for-business"></a>Comparaison des fonctionnalités des clients de bureau pour Skype Entreprise
 
**Summary:** Skype for Business Server 2015 or Skype for Business Online administrators can use these tables to understand what features are supported on which clients.
  
 Before you deploy or upgrade to Skype for Business, check which clients are already in use in your organization. Use the tables below to understand the feature support impact on those clients. Cela peut vous aider à communiquer les modifications aux utilisateurs, opérer le processus de déploiement et bien comprendre les avantages de la mise à niveau vers le dernier client.
  
Some features available with Skype for Business Server 2015 are not available in Skype for Business Online, see [Online or Hybrid user account limitations](desktop-feature-comparison.md#Online-Hybrid) for specifics. Skype for Business Online Admins may want to refer to [Skype for Business Online Service Description](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) for information on the different plans available to them.
  
The following tables show the features that are available with each client that works with Skype for Business Server 2015 or Skype for Business Online. You may also want to refer to [Mobile client feature comparison for Skype for Business](mobile-feature-comparison.md) for smart phone and tablet client feature comparisons. Les licences d’accès client ou USL (User Subscription License) qu’achète votre organisation auront également un impact sur les fonctionnalités auxquelles les utilisateurs ont accès. Le déploiement du client complet ou de base pour les utilisateurs dépend de la licence ou de l’offre que votre organisation choisit d’acheter. See the [Licensing Guide](https://products.office.com/en-us/skype-for-business/it-pros) for more details.
  
> [!IMPORTANT]
> Skype for Business Server 2015 and Skype for Business Online support the following previously released clients: Lync 2013, Lync 2010, Lync 2010 Mobile, Lync Phone Edition, and Lync 2010 Attendant. For information about these clients when used with other servers, see the [Client comparison tables for Lync Server 2013](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.15%29.aspx) and [Client comparison tables for Lync Server 2010](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.14%29.aspx). 
  
> [!NOTE]
> The **Lync 2010 Attendant** client is not supported in Skype for Business Online.
  
> [!NOTE]
> The Skype for Business Web App browser client and Skype Meetings App Windows 10 app only provide [Meetings support](desktop-feature-comparison.md#BKMK_Conferencing). Refer to [Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md) for more about these clients.
  
## <a name="enhanced-presence-support"></a>Prise en charge de la présence avancée
<a name="BKMK_EnhancedPresence"> </a>

Ce tableau couvre les fonctionnalités de présence avancée qui vont plus loin qu’une simple indication spécifiant si un utilisateur est en ligne, hors ligne, occupé, etc. 
  
|Fonctionnalité|Client Skype Entreprise 2015 ou 2016|Skype Entreprise sur Mac|Lync 2013 client|application Lync du Windows Store|Lync 2010 | Intendant Lync 2010|Lync Phone Edition|Communicator pour Mac 2011|Lync pour Mac 2011|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Publier le statut  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|
|Afficher le statut  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher les notes de statut et les messages de notification d'absence du bureau  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ajouter un emplacement personnalisé  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Ajouter une note personnalisée  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Utiliser une photo à partir d’un site public pour Mon image  <br/> (not available in Skype for Business Online)  <br/> |&#x2714;||&#x2714;|||||||

 &#x2776;  Does not support publishing status based on calendar free/busy information.
  
## <a name="contacts-and-contact-groups-support"></a>Prise en charge des contacts et groupes de contacts
<a name="BKMK_Contacts"> </a>

Ce tableau couvre les fonctionnalités liées à la gestion des contacts de messagerie instantanée et de présence. 
  

|Fonctionnalité|Client Skype Entreprise 2015 ou 2016|Skype Entreprise sur Mac | Lync 2013 client | application Lync du Windows Store | Lync 2010 | Intendant Lync 2010 | Lync Phone Edition | Communicator pour Mac 2011 | Lync pour Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Liste de contacts préremplie  <br/> |&#x2714;|||||||||
|Afficher et modifier la liste des contacts  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ajouter une balise à des contacts pour les alertes de changement de statut  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;||||
|Contrôler les niveaux de confidentialité  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Effectuer des recherches dans le carnet d'adresses de l'entreprise  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Rechercher des contacts Microsoft Outlook  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gérer des groupes de contacts  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Développer des groupes de distribution et des groupes Office 365  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Rechercher des groupes Response Group  <br/> (not available in Skype for Business Online)  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Afficher le groupe de contacts récent  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Afficher le groupe de conversations actuel  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|||
|Afficher d'autres vues des contacts (par exemple, mosaïque)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Sort contacts by Group, Relationship, or New (people who've added you to their Contacts list)  <br/> |&#x2714;||&#x2714;|Trier par groupe  <br/> |&#x2714;|&#x2714;||||
|Trier les contacts selon leur statut (disponibilité)  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;|||&#x2714;|
|Rechercher et ajouter des contacts Exchange  <br/> |&#x2714;||&#x2714;||||||&#x2714;|
   
## <a name="im-support"></a>Prise en charge de la messagerie instantanée
<a name="BKMK_IMSupport"> </a>

Ce tableau couvre les fonctionnalités liées à la prise en charge de la messagerie instantanée.
  

|Fonctionnalité | Client Skype Entreprise 2015 ou 2016 | Skype Entreprise sur Mac | Lync 2013 client | application Lync du Windows Store | Lync 2010 | Intendant Lync 2010 | Lync Phone Edition | Communicator pour Mac 2011 | Lync pour Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Démarrer une conversation par messagerie instantanée avec un contact  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Parcourir plusieurs conversations par messagerie instantanée/Suivre plusieurs conversations dans une seule fenêtre avec onglets  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Enregistrer des conversations par messagerie instantanée dans Outlook  <br/> |&#x2714;|&#x2714;If server side conversation history is turned on  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;||Enregistré dans Communicator pour Mac  <br/> |Enregistré dans Lync pour Mac  <br/> |
|Utiliser des modèles de conversation existants  <br/> |||||&#x2714;|&#x2714;||||
|Vérification de l'orthographe  <br/> |&#x2714;|&#x2714;||&#x2714;|||||&#x2714;|
|Skill search (with SharePoint Server integration)  <br/> (On-premises Skype for Business Server and on-premises SharePoint 2013 are required for skill search.)  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||
|Intégration de la conversation permanente (Conversation de groupe)  <br/> (not available for Skype for Business Online)  <br/> |&#x2714;||&#x2714;|||||||
|Escalate a Persistent Chat room to a Skype for Business Meeting with one click  <br/> (not available for Skype for Business Online)  <br/> |&#x2714;||&#x2714;|||||||
|Images intégrées de l'expéditeur et du destinataire dans la fenêtre de messagerie instantanée  <br/> |&#x2714;||&#x2714;|&#x2714;||||||
|Envoyer des messages manuscrits  <br/> ||||&#x2714;||||||
|Recevoir des messages manuscrits  <br/> |&#x2714;||&#x2714;|&#x2714;||||||
|Définir les messages instantanés sur Importance haute  <br/> |&#x2714;||&#x2714;|||||||
   
## <a name="meetings-support"></a>Prise en charge des réunions
<a name="BKMK_Conferencing"> </a>

Ce tableau couvre les fonctionnalités liées à la prise en charge des réunions.
  
> [!NOTE]
>  Skype for Business meeting features aren't available in Skype for Business Online Standalone Plan 1.

Dans les sessions Skype-à-Skype, un utilisateur du plan 1 de Skype Entreprise Online peut participer au partage de bureau et d'applications s'il est invité par un utilisateur qui a accès aux fonctionnalités de partage.   
For details, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx). 
  
|Fonctionnalité | Skype for Business 2016 client | Skype Entreprise sur Mac | Application web Skype Entreprise | Skype for Business 2015 client | Lync 2013 client | application Lync du Windows Store | Lync 2010 | Intendant Lync 2010 | Lync Phone Edition | Communicator pour Mac 2011 | Lync pour Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Ajouter l’audio de l’ordinateur  <br/> |&#x2714;|&#x2714;|&#x2714;(requires plug-in)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ajouter la vidéo  <br/> |&#x2714;|&#x2714;|&#x2714;(requires plug-in)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|&#x2714;|
|Afficher une vidéo à plusieurs (vue galerie)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Partage d'écran vidéo  <br/> |&#x2714;|&#x2714;Only for users homed on Skype for Business Online  <br/> |&#x2714;View-only  <br/> |||||||||
|Utiliser des commandes de présentateur lors des réunions  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Accéder à une liste détaillée des réunions  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Participer à une conversation par messagerie instantanée à plusieurs  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Partager le bureau (si option activée)  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; (requires plug-in)  <br/> |&#x2714;|&#x2714;||&#x2714;|||&#x2714; &#x2776; |&#x2714; &#x2776; |
|Partager un programme (si option activée)  <br/> |&#x2714;|Afficher uniquement  <br/> |&#x2714;(requires plug-in)  <br/> |&#x2714;|&#x2714;||&#x2714;||||Afficher uniquement  <br/> |
|Ajouter des participants anonymes (si option activée)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Utiliser les réunions audio rendez-vous  <br/> |&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714;|&#x2714;|||&#x2714;|
|Démarrer une réunion Conférence maintenant  <br/> |&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Ajouter et présenter des fichiers Microsoft PowerPoint  <br/> |&#x2714;| &#x2778; View only, annotations not available  <br/> |&#x2714;|&#x2714;|&#x2714;|Présence uniquement  <br/> |&#x2714;|||| &#x2778; View only, annotations not available  <br/> |
|Parcourir des fichiers Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Ajouter et modifier des notes de réunion OneNote  <br/> |&#x2714;||Modifier uniquement (pas ajouter)  <br/> |&#x2714;|&#x2714;|||||||
|Utiliser un tableau blanc  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Mener des sondages  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Télécharger des fichiers pour les partager avec des tiers  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Planifier une réunion ou une conférence  <br/> |Outlook or Skype for Business Web Scheduler  <br/> |Outlook or Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |Outlook or Skype for Business Web Scheduler  <br/> |Outlook or Lync Web Scheduler  <br/> |Outlook or Lync Web Scheduler  <br/> |Outlook  <br/> ||||Outlook  <br/> |
|Q&amp;A Manager  <br/> |&#x2714;|||||||||||
|Désactiver la vidéo des participants  <br/> |&#x2714;||&#x2714;|||||||||
|Désactiver la messagerie instantanée pour la réunion  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|||||||
|Désactiver le son des participants  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Inviter tout le monde à participer  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Produire une diffusion de réunion Skype  <br/> |&#x2714;|||||||||||
|Un délégué peut planifier une réunion pour le compte d'un délégant  <br/> |&#x2714;|Skype Entreprise Online uniquement <br/>|&#x2714;|||||||||
|Synchroniser les délégués entre Skype Entreprise et Outlook  <br/> |&#x2714;||&#x2714;|||||||||
|Partage d'écran vidéo  <br/> |&#x2714;| Skype Entreprise Online uniquement <br/> |&#x2714;||&#x2714;|||||||
|Définir la vidéo à la une (verrouiller la vidéo)  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Donner/prendre le contrôle du partage d'écran  <br/> |&#x2714;||&#x2714;|||||||||
   
 &#x2776;  Participants can't control desktops that are shared by Skype for Business on Mac, Lync for Mac 2011, or Communicator for Mac 2011 users. Skype for Business on Mac, Lync for Mac 2011 and Communicator for Mac 2011 users can't control desktops shared by Windows users. Cela ne peut fonctionner pour lʼapplication Skype Entreprise Web sur Max OSX.
  
 &#x2777;  For Skype for Business Online, this feature requires Microsoft PSTN Conferencing, Exchange Unified Messaging, or a 3rd party audio conferencing provider.
  
 &#x2778;  The Lync for Mac 2011 client cannot view Microsoft Office 2013 PowerPoint presentations when they have been shared in a conference by the Skype for Business Web App.
  
## <a name="voice-telephony-support"></a>Prise en charge de la voix (téléphonie)
<a name="BKMK_Telephony"> </a>

Ce tableau couvre les fonctionnalités liées à la prise en charge des services vocaux.
  
> [!NOTE]
> Skype for Business Voice (Telephony) features are limited to certain Skype for Business Online subscription plans. > For details, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx). 
  
 | Fonctionnalité | Client Skype Entreprise 2015 ou 2016 | Skype Entreprise sur Mac | Lync 2013 client | application Lync du Windows Store | Lync 2010 | Intendant Lync 2010 | Lync Phone Edition | Communicator pour Mac 2011 | Lync pour Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Démarrer un appel  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Cliquer pour appeler un contact  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Transférer un appel  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gérer le transfert d'appel  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gérer les paramètres d'appel d'équipe  <br/> |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Gérer les délégués  <br/> |&#x2714;|&#x2714;Requires Skype for Business Server 2015 CU4 or later  <br/> |&#x2714; &#x2776; ||&#x2714;||||&#x2714;|
|Appeler un groupe Response Group  <br/> |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Prendre en charge les services d'urgence (E-911)  <br/> |&#x2714;|&#x2714;Requires Skype for Business Server 2015 CU6 or later  <br/> |&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Notification de messagerie instantanée aux URI SIP pour un appel E-911  <br/> |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Notification de messagerie instantanée à la liste de distribution pour un appel E-911  <br/> |&#x2714;||&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Se connecter à la messagerie vocale, configurer ou changer le message d'accueil  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Notification des appels manqués  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Passer un appel pour le compte d'un autre contact (scénario responsable/délégué)  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|||||
|Gérer les appels d'une autre personne, si celle-ci est configurée en tant que déléguée  <br/> |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;|||
|Gérer un volume d'appels important  <br/> |||||&#x2714;|&#x2714;||||
|Parcage d'appel  <br/> |&#x2714;||&#x2714; &#x2776; |||||||
|Prise d'appel de groupe  <br/> |&#x2714;||&#x2714; &#x2776; ||||&#x2714;|||
|Routage géodépendant  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gérer un groupe Response Group/d'appel d'équipe  <br/> |&#x2714;||&#x2714;|||||||
   
 &#x2776;  This feature isn't available in Skype for Business Online.
  
## <a name="external-users-support"></a>Prise en charge des utilisateurs externes
<a name="BKMK_ExternalUsers"> </a>

Ce tableau couvre les fonctionnalités liées à la prise en charge des utilisateurs externes hébergés sur le PSTN.
  

|Fonctionnalité | Client Skype Entreprise 2015 ou 2016 | Skype Entreprise sur Mac | Lync 2013 client | application Lync du Windows Store | Lync 2010 | Intendant Lync 2010 | Lync Phone Edition | Communicator pour Mac 2011 | Lync pour Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Démarrer une conversation par messagerie instantanée avec un contact public  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Démarrer une conversation par messagerie instantanée avec un contact fédéré  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Mener des appels à deux ou à plusieurs avec des utilisateurs externes  <br/> (not available in Skype for Business Online)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
## <a name="recording-support"></a>Prise en charge de l'enregistrement
<a name="BKMK_Recording"> </a>

Ce tableau couvre les fonctionnalités liées à la prise en charge de l’enregistrement des réunions.
  
| Future/capability** | Client Skype Entreprise 2015 ou 2016 | Skype Entreprise sur Mac | Lync 2013 client | application Lync du Windows Store | Lync 2010 | Intendant Lync 2010 | Lync Phone Edition | Communicator pour Mac 2011 | Lync pour Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Enregistrement côté client du son, de la vidéo, du partage d’application, du partage de Bureau et du contenu téléchargé  <br/> |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Enregistrement côté client des transferts de fichiers, des pages OneNote partagées et des annotations PowerPoint  <br/> |&#x2714; &#x2777; ||&#x2714; &#x2777; ||&#x2714;|||||
|Sélection de la résolution d'enregistrement préférée  <br/> |&#x2714;||&#x2714;|||||||
   
 &#x2776;  Recording is unavailable in certain Skype for Business Online standalone plans. L'enregistrement nécessite des droits complets de client Skype Entreprise.
  
 &#x2777;  Recording of file transfers, shared OneNote pages, and PowerPoint annotations is unavailable in Skype for Business Online.
  
## <a name="modern-authentication"></a>Authentification moderne
<a name="BKMK_Recording"> </a>

Ce tableau couvre les fonctionnalités qui requièrent la prise en charge de l'authentification moderne. 
  
Modern authentication also requires a topology described in [Skype for Business topologies supported with Modern Authentication](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Fonctionnalité | Client Skype Entreprise 2015 ou 2016 | Skype Entreprise sur Mac | Lync 2013 client | application Lync du Windows Store | Lync 2010 | Intendant Lync 2010 | Lync Phone Edition | Communicator pour Mac 2011 | Lync pour Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Authentification moderne  <br/> |&#x2714;|&#x2714;|&#x2714;|||||||
|Authentification multifacteur  <br/> |&#x2714;|&#x2714;|&#x2714;|||||||
|Authentification avec certificat  <br/> |&#x2714;(Domain-joined device only)  <br/> |&#x2714;|&#x2714;(Domain-joined device only)  <br/> |||||||
   
## <a name="archiving-compliance-and-logging-support"></a>Prise en charge de l'archivage, de la conformité et de la journalisation
<a name="BKMK_Archiving"> </a>

Ce tableau couvre les fonctionnalités liées à la prise en charge des fonctionnalités d’archivage et de journalisation.
  

 | Fonctionnalité | Client Skype Entreprise 2015 ou 2016 | Skype Entreprise sur Mac | Lync 2013 client | application Lync du Windows Store | Lync 2010 | Intendant Lync 2010 | Lync Phone Edition | **Communicator pour Mac 2011** | Lync pour Mac 2011 | 
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Archivage des conversations par messagerie instantanée dans l’historique des conversations Outlook  <br/> |&#x2714; &#x2776; |&#x2714;If server side conversation history is turned on  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|&#x2714;||Enregistré dans Communicator pour Mac  <br/> |Enregistré dans Lync pour Mac  <br/> |
|Archivage côté client du son, de la vidéo, du partage d’application, du partage de Bureau et du contenu téléchargé  <br/> |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Archivage côté client des transferts de fichiers, des pages OneNote partagées et des annotations PowerPoint  <br/> (unavailable in Skype for Business Online)  <br/> |&#x2714;||&#x2714;||&#x2714;|||||
|Access sign-in logs from Skype for Business icon in the task bar  <br/> |&#x2714;||&#x2714;|||||||
   
 &#x2776;  For Skype for Business Online users, this feature requires Exchange Online and is controlled by the user's Exchange mailbox In-Place Hold attribute.
  
## <a name="client-limitations"></a>Restrictions relatives aux clients 
<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Restrictions relatives aux clients de base
<a name="Full-Basic"> </a>

Les fonctionnalités ci-après sont disponibles avec le client complet. Elles ne sont pas intégrées au client de base :  
  
- Gérer les paramètres d’appel d’équipe
    
- Gérer les délégués
    
- Passer un appel pour le compte d’un autre contact (scénario responsable/délégué)
    
- Gérer les appels d’une autre personne, si celle-ci est configurée en tant que déléguée
    
- Gérer un volume d’appels important
    
- Démarrer un appel à un groupe Response Group
    
- Parcage d’appel
    
- Changer le message d’accueil
    
- Prise d’appel de groupe
    
### <a name="online-or-hybrid-user-account-limitations"></a>Restrictions relatives aux comptes d’utilisateur en ligne ou hybrides
<a name="Online-Hybrid"> </a>

Les comptes d’utilisateur peuvent exister en ligne ou dans les locaux, ce qui affectera les fonctionnalités auxquelles l’utilisateur correspondant peut accéder. Users with accounts on Skype for Business Online will not have access to the following features, even with the Full client: 
  
- Présence améliorée : Utiliser une photo à partir d’un site public pour Mon image
    
- Contacts : Rechercher des groupes Response Group
    
- Prise en charge de la messagerie instantanée : Intégration de la conversation permanente (Conversation de groupe)
    
- IM Support: Escalate a Persistent Chat room to a Skype for Business Meeting with one click
    
- Utilisateurs externes : Mener des appels à deux ou à plusieurs avec des utilisateurs externes
    
## <a name="see-also"></a>Voir aussi
<a name="Types"> </a>

[Plan for clients and devices](clients-and-devices.md)

