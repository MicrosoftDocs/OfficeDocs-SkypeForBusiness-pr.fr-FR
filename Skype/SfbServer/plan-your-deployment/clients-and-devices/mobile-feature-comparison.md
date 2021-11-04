---
title: Comparaison des fonctionnalités des clients mobiles pour Skype Entreprise
ms.author: v-mahoffman
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Résumé : Examinez la prise en charge des fonctionnalités pour le client mobile lors de la planification de Skype Entreprise Server.'
ms.openlocfilehash: 9b619219666a89e40870caf4cea80a683011775c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759566"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Comparaison des fonctionnalités des clients mobiles pour Skype Entreprise
 
**Résumé :** Examinez la prise en charge des fonctionnalités pour le client mobile lors de la planification de Skype Entreprise Server.
  
Cet article compare les fonctionnalités entre Skype Entreprise clients mobiles et le client Skype Entreprise bureau dans les catégories suivantes :
  
- Se connectez, notifications Push et fonctionnalités générales
    
- Présence enrichie
    
- Contacts et groupes de contacts
    
- Messagerie instantanée
    
- Skype Entreprise pour Skype Entreprise audio et vidéo
    
- Conférence
    
- Téléphonie
    
- Utilisateurs externes
    
- Archivage et conformité
    
-  Authentification moderne
    
Les tableaux suivants listent les fonctionnalités disponibles Skype Entreprise utilisateurs dans un déploiement local de Skype Entreprise Server. Les mêmes fonctionnalités sont également disponibles pour Skype Entreprise Online et Microsoft 365 ou Office 365 utilisateurs, sauf indication contraire dans les notes de bas de page du tableau.
  
> [!NOTE]
> Pour obtenir de l’aide et des ressources en ligne pour les utilisateurs finaux, voir [Découvrir Skype Entreprise](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> Pour comparer les fonctionnalités disponibles dans d’Skype Entreprise clients de bureau, voir comparaison des fonctionnalités du client de bureau [pour Skype Entreprise](desktop-feature-comparison.md). 

> [!NOTE]
> La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible Skype Entreprise Server 2019. Tous les clients mobiles Skype Entreprise actuellement utilisent déjà l’API UCWA (Unified Communications Web API) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.
  
## <a name="sign-in-push-notifications-and-general-features"></a>Se connectez, notifications Push et fonctionnalités générales

 
 | Fonctionnalité/fonctionnalité  | Skype Entreprise client de bureau  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype Entreprise session reste en cours de session  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Prise en charge des notifications de type push  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714; &#x2779; |&#x2714; &#x2779; |
|Possibilité de mettre en cache les informations de comptes de plusieurs utilisateurs sur le même appareil  <br/> |&#x2714;||||
|Lecteur d’écran/voix sur deux  <br/> |&#x2714;|&#x2714; &#x2777;           anglais uniquement  <br/> |&#x2714;|&#x2714;|
|Utiliser un clavier externe pour l’accessibilité  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Prise en charge du Programme d’amélioration du produit Microsoft  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; sur Windows Phone, Skype Entreprise se signe automatiquement après une période d’inactivité, comme suit :
  
- Si l’utilisateur a activé les notifications Push, Skype Entreprise se Skype Entreprise après 10 jours d’inactivité.
    
- Si l’utilisateur n’a pas activé les notifications Push, Skype Entreprise se signe dès que l’utilisateur quitte l’application.
    
Sur les appareils iOS, Skype Entreprise se connecte automatiquement lorsque le client mobile n’a pas contacté le serveur pendant 10 jours en raison d’une perte de connectivité réseau ou d’autres problèmes.
  
 &#x2777; dans l’application uniquement.
  
 &#x2778; notifications sont disponibles lorsque l’application s’exécute en arrière-plan.
 
 &#x2779; services de notification mobile Google/Android/GCNS et Apple/APNS utilisent le chiffrement HTTPS/TLS pour la remise des notifications. La charge utile de notification est gérée en texte simple lorsqu’elle est traitée par le fournisseur de notifications.
 
-   Skype Entreprise pour Android reçoit des notifications simples (délivrées via GCNS) sans données client.
-   Skype Entreprise pour iOS reçoit des notifications (délivrées via APNS) qui peuvent inclure des données client pour l’appel ou le message.
 
  
## <a name="enhanced-presence-support"></a>Prise en charge améliorée de la présence


 | Fonctionnalité/fonctionnalité  | Skype Entreprise client de bureau  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Publier et afficher le statut  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher le statut basé sur les informations de disponibilité du calendrier  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher les notes de statut et les messages de notification d’absence du bureau  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ajouter un emplacement personnalisé  <br/> |&#x2714;||||
|Ajouter une note personnalisée  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Publier le statut d’après les informations de disponibilité du calendrier  <br/> |&#x2714; &#x2776; ||||
|Définir l’état de présence manuel (par exemple, Occupé, Ne pas déranger, et ainsi de suite)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; Skype Entreprise clients mobiles ne met pas à jour la présence d’un utilisateur en fonction des informations de son calendrier de libre/occupé. Si un utilisateur de client mobile est également inscrit au client de bureau Skype Entreprise, le client de bureau met à jour la présence de l’utilisateur en fonction des informations de calendrier de la période de libre/occupé de l’utilisateur. Si l’utilisateur est uniquement inscrit à un client mobile, la présence de l’utilisateur ne se met pas à jour en fonction des informations de calendrier de libre/occupé.
  
## <a name="contacts-and-contact-groups-support"></a>Prise en charge des contacts et des groupes de contacts


 | Fonctionnalité/fonctionnalité  | Skype Entreprise client de bureau  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Afficher la liste des contacts  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher les groupes de contacts  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher les groupes de contacts fréquents  <br/> |&#x2714;||||
|Modifier la liste des contacts  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ajouter une balise à des contacts pour les alertes de changement de statut  <br/> |&#x2714;||||
|Contrôler les niveaux de confidentialité  <br/> |&#x2714;||||
|Effectuer des recherches dans le carnet d’adresses de l’entreprise  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Effectuer des recherches dans les listes de contacts  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Gérer des groupes de contacts  <br/> |&#x2714;|||&#x2714;|
|Développer les groupes de distribution  <br/> |&#x2714;|&#x2714;||&#x2714;|
|Rechercher des groupes Response Group  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|Afficher ou masquer les photos des contacts  <br/> |&#x2714;|&#x2714;|||
|Épingler un contact à votre écran d’accueil  <br/> ||&#x2714;|||
   
 &#x2776; n’est pas disponible pour Skype Entreprise en ligne et/ou Microsoft 365 ou Office 365 utilisateurs.
  
## <a name="instant-messaging-support"></a>Prise en charge de la messagerie instantanée


 | Fonctionnalité/fonctionnalité  | Skype Entreprise client de bureau  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Lancer la messagerie instantanée avec un contact  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Prendre part à une conversation par messagerie instantanée à plusieurs  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Inviter d’autres personnes à partir d’une fenêtre de conversation  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher les conversations actuelles  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Passer d’une conversation par messagerie instantanée à une autre  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Consigner automatiquement les conversations par messagerie instantanée dans Exchange  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Envoyer une conversation par messagerie instantanée en tant que message électronique  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Écrire un courrier électronique à un contact  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher les invitations de messagerie instantanée manquées  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Vibrer en cas de message instantané entrant  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 &#x2776; cet appareil vibre chaque fois qu’un message instantané est reçu, même si le message actuel dans la conversation par messagerie instantanée s’affiche
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype Entreprise pour Skype Entreprise audio et vidéo


 | Fonctionnalité/fonctionnalité  | Skype Entreprise client de bureau  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype Entreprise-to-Skype Entreprise voice  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Skype Entreprise vidéo Skype Entreprise-to-Skype Entreprise  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> La vidéo sur un appareil mobile nécessite une connexion WiFi par défaut. 
  
## <a name="conferencing-support"></a>Prise en charge des conférences


 | Fonctionnalité/fonctionnalité  | Skype Entreprise client de bureau  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Cliquez sur un lien dans le rappel de réunion pour participer à une réunion vidéo ou VoIP  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Prendre part à une conversation par messagerie instantanée à plusieurs  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Utiliser la conférence d’appel sortant (le serveur appelle l’appareil mobile)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Utiliser l’audioconférence rendez-vous  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualiser la vidéo de la réunion  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher la vidéo à plusieurs (vue galerie)  <br/> |&#x2714;||||
|Patienter dans la salle d’attente de réunion  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Utiliser des commandes de présentateur lors des réunions  <br/> |&#x2714;||||
|Accéder à une liste de réunion détaillée pour les conférences audio  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Accéder à une liste de réunion détaillée pour les conférences par messagerie instantanée  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Partager le Bureau ou un programme  <br/> |&#x2714;||||
|Afficher un bureau ou un programme partagé (VbSS ou RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Afficher les fichiers de PowerPoint partagés  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777;&#x2778; |&#x2714; &#x2777; &#x2778;|
|Télécharger et présenter PowerPoint fichiers  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Utiliser les outils de réunion (utiliser le tableau blanc, mener des sondages, partager des fichiers)  <br/> |&#x2714;||||
|Parcourir une liste de vos réunions  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participer à une réunion même si vous n’avez pas de compte Skype Entreprise de réunion  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher plus d’informations sur les participants à la réunion  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Démarrer une conversation de groupe nonprogrammée avec plusieurs participants directement à partir de votre client ou de votre appareil  <br/> |&#x2714;|&#x2714;|&#x2714;||
   
 &#x2776; pour Microsoft 365 ou Office 365 utilisateurs, cette fonctionnalité nécessite Voix Entreprise, qui fait partie de la licence E5.
  
 &#x2777; nécessite une connexion WiFi par défaut.
 
 &#x2778; vidéo incorporée dans PowerPoint présentations n’est pas prise en charge.
  
## <a name="telephony-support"></a>Prise en charge de la téléphonie


 | Fonctionnalité/fonctionnalité  | Skype Entreprise client de bureau  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Dans Skype Entreprise, appuyez sur l’icône d’appel pour appeler un contact  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Transférer un appel  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Transfert consultatif  <br/> |&#x2714; &#x2778; ||||
|Gérer le transfert d’appel  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Gérer les paramètres d'appel d'équipe  <br/> |&#x2714; &#x2776; ||||
|Gérer les délégués  <br/> |&#x2714; &#x2776; ||||
|Démarrer un appel à un groupe Response Group  <br/> |&#x2714; &#x2776; ||||
|Prise en charge des services d’urgence  <br/> |&#x2714; &#x2777; ||||
|Passer un appel pour le compte d'un autre contact (scénario responsable/délégué)  <br/> |&#x2714; &#x2776; ||||
|Gérer les appels d’un autre contact, s’il est configuré en tant que délégué  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Utiliser l’appel via le travail  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|accéder à sa messagerie vocale ;  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Utiliser le clavier dans Skype Entreprise  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776; disponible pour les utilisateurs Skype Entreprise Online et/ou Office 365 E5 et les utilisateurs Skype Entreprise Server ou Lync Server 2013 avec l’Voix Entreprise activée.
  
 &#x2777; pour Skype Entreprise Online et/ou Microsoft 365 ou Office 365 utilisateurs, cette fonctionnalité est prise en charge par les partenaires Microsoft.
  
 &#x2778; Windows client de bureau uniquement.
  
## <a name="external-user-support"></a>Prise en charge des utilisateurs externes


 | Fonctionnalité/fonctionnalité  | Skype Entreprise client de bureau  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Démarrer une conversation par messagerie instantanée avec un contact public  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Démarrer une conversation par messagerie instantanée avec un contact fédéré  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Mener des appels à deux avec des utilisateurs externes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Mener des appels à plusieurs avec des utilisateurs externes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Utiliser l’appel via le travail pour joindre un contact fédéré sur son téléphone mobile en appelant son numéro de travail publié &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; par défaut, le niveau de confidentialité Contacts externes est affecté aux utilisateurs fédérés. Pour pouvoir joindre un contact fédéré sur son téléphone mobile en appelant son numéro de travail publié, le contact fédéré doit vous affecter manuellement le niveau de confidentialité Collègues.
  
## <a name="address-book-integration"></a>Intégration du carnet d’adresses


 | Fonctionnalité/fonctionnalité  | Skype Entreprise client de bureau  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Appeler les contacts du carnet d’adresses de l’appareil  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Effectuer des Skype Entreprise aux contacts directement à partir du carnet d’adresses de l’appareil  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Prise en charge de l’archivage et de la conformité


 | Fonctionnalité/fonctionnalité  | Skype Entreprise client de bureau  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Fournir l’archivage côté client  <br/> |&#x2714;||||
|Fournir l’enregistrement côté client  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776; n’est pas disponible pour Skype Entreprise en ligne et/ou Microsoft 365 ou Office 365 utilisateurs.
  
## <a name="modern-authentication"></a>Authentification moderne

Ce tableau couvre les fonctionnalités nécessitant la prise en charge de l’authentification moderne.
  
L’authentification moderne nécessite également une topologie décrite [dans Skype Entreprise topologies pris en charge avec l’authentification moderne.](../../plan-your-deployment/modern-authentication/topologies-supported.md)
  

 | Fonctionnalité/fonctionnalité  | Skype Entreprise client de bureau  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Authentification moderne  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Authentification multifacteur  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Authentification basée sur les certificats  <br/> |&#x2714;(appareil joint au domaine uniquement)  <br/> ||&#x2714;|&#x2714;|
|Gestion des applications mobiles (via Intune)  <br/> |||&#x2714;|&#x2714;|
   

