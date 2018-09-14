---
title: Comparaison des fonctionnalités de client mobile pour Skype pour les entreprises
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Résumé : Passez en revue la prise en charge de la fonctionnalité pour le client mobile lors de la planification pour Skype pour Business Server.'
ms.openlocfilehash: f04d0162113db68e2507930e827904110b69066f
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965747"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Comparaison des fonctionnalités de client mobile pour Skype pour les entreprises
 
**Résumé :** Passez en revue la prise en charge de la fonctionnalité pour le client mobile lors de la planification pour Skype pour Business Server.
  
Cet article compare les fonctionnalités entre Skype pour les clients mobiles métiers et le Skype pour le client de bureau d’entreprise dans les catégories suivantes :
  
- Connexion, notifications Push et fonctionnalités générales
    
- Présence avancée
    
- Contacts et groupes de contacts
    
- Messagerie instantanée
    
- Skype pour les entreprises à Skype Business audio et vidéo
    
- Téléconférence
    
- Téléphonie
    
- Utilisateurs externes
    
- Archivage et conformité
    
-  Authentification moderne
    
Les tableaux suivants répertorient les fonctionnalités disponibles pour Skype pour les utilisateurs professionnels dans un déploiement local de Skype pour Business Server. Les mêmes fonctionnalités sont également disponibles pour Skype pour les utilisateurs professionnels en ligne et de Microsoft Office 365, sauf indication contraire dans les notes de fin de la table.
  
> [!NOTE]
> De l’aide en ligne et des ressources pour les utilisateurs finaux, voir [Découvrir les Skype pour les entreprises](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> Pour comparer les fonctionnalités disponibles dans les autres Skype pour les clients d’entreprise, voir [comparaison des fonctionnalités client de bureau pour Skype pour les entreprises](desktop-feature-comparison.md). 

> [!NOTE]
> Prise en charge MCX (Service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019. Tous les Skype en cours pour les clients mobiles métiers utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, présence et les contacts. Les utilisateurs avec les clients hérités MCX doivent mettre à niveau vers un client actuel.
  
## <a name="sign-in-push-notifications-and-general-features"></a>Connexion, notifications Push et fonctionnalités générales

 
 | Fonctionnalité  | Skype pour le client de bureau d’entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype pour session Business reste ouverte  <br/> |& #x 2714 ;|& #x 2714 ; & #x 2776 ; |& #x 2714 ; & #x 2776 ; |& #x 2714 ;|
|Prise en charge des notifications Push  <br/> |& #x 2714 ; & #x 2778 ; |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Possibilité de mettre en cache les informations de comptes de plusieurs utilisateurs sur le même appareil  <br/> |& #x 2714 ;||||
|Lecteur d’écran/voix off  <br/> |& #x 2714 ;|& #x 2714 ; & #x 2777 ;           En anglais uniquement  <br/> |& #x 2714 ;|& #x 2714 ;|
|Utilisation d’un clavier externe pour l’accessibilité  <br/> |& #x 2714 ;||& #x 2714 ;|& #x 2714 ;|
|Prise en charge du Programme d’amélioration du produit Microsoft  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
   
 & #x 2776 ;  Sur Windows Phone, Skype pour les entreprises se déconnecte automatiquement après une période d’inactivité, comme suit :
  
- Si l’utilisateur a activé les notifications push, Skype pour les entreprises se déconnecte après 10 jours d’inactivité.
    
- Si l’utilisateur n’a pas activé les notifications push, Skype pour les entreprises se déconnecte dès que l’utilisateur quitte l’application.
    
Sur des appareils iOS, Skype pour les entreprises se déconnecte automatiquement une fois que le client mobile n’a pas été contacté le serveur pour 10 jours en raison de la perte de connectivité réseau ou autres problèmes.
  
 & #x 2777 ;  Dans l’application.
  
 & #x 2778 ;  Les notifications sont disponibles lorsque l’application s’exécute en arrière-plan.
  
## <a name="enhanced-presence-support"></a>Prise en charge de la présence avancée


 | Fonctionnalité  | Skype pour le client de bureau d’entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Publier et afficher le statut  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Afficher le statut basé sur les informations de disponibilité du calendrier  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Afficher les notes de statut et les messages de notification d'absence du bureau  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Ajouter un emplacement personnalisé  <br/> |& #x 2714 ;||||
|Ajouter une note personnalisée  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Publier le statut d’après les informations de disponibilité du calendrier   <br/> |& #x 2714 ; & #x 2776 ; ||||
|Définir le statut de présence manuel (Occupé, Ne pas déranger, etc.)  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
   
 & #x 2776 ;  Skype pour les clients mobiles Business ne pas actualiser la présence d’un utilisateur en fonction des informations de calendrier et de disponibilité de l’utilisateur. Si un utilisateur de client mobile est également connecté à la Skype pour le client de bureau d’entreprise, le client de bureau met à jour la présence de l’utilisateur en fonction des informations de calendrier et de disponibilité de l’utilisateur. Si l’utilisateur est connecté à un client mobile uniquement, présence de l’utilisateur ne met pas à jour en fonction des informations de disponibilité des informations de calendrier.
  
## <a name="contacts-and-contact-groups-support"></a>Prise en charge des contacts et groupes de contacts


 | Fonctionnalité  | Skype pour le client de bureau d’entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Afficher la liste des contacts  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Afficher les groupes de contacts  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Afficher les groupes de contacts fréquents  <br/> |& #x 2714 ;||||
|Modifier la liste des contacts  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Ajouter une balise à des contacts pour les alertes de changement de statut  <br/> |& #x 2714 ;||||
|Contrôler les niveaux de confidentialité  <br/> |& #x 2714 ;||||
|Effectuer des recherches dans le carnet d'adresses de l'entreprise  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Effectuer des recherches dans les listes de contacts  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Gérer des groupes de contacts  <br/> |& #x 2714 ;|||& #x 2714 ;|
|Développer des groupes de distribution  <br/> |& #x 2714 ;|& #x 2714 ;||& #x 2714 ;|
|Rechercher des groupes Response Group  <br/> |& #x 2714 ; & #x 2776 ; |& #x 2714 ;||& #x 2714 ;|
|Afficher ou masquer les photos des contacts  <br/> |& #x 2714 ;|& #x 2714 ;|||
|Épingler un contact sur votre écran d’accueil  <br/> ||& #x 2714 ;|||
   
 & #x 2776 ;  Non disponible pour Skype pour les utilisateurs professionnels en ligne et/ou d’Office 365.
  
## <a name="instant-messaging-support"></a>Prise en charge de la messagerie instantanée


 | Fonctionnalité  | Skype pour le client de bureau d’entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Démarrer une conversation par messagerie instantanée avec un contact  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Participer à une conversation par messagerie instantanée à plusieurs  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Inviter d’autres personnes à partir d’une fenêtre de conversation  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Afficher les conversations actuelles  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Passer d’une conversation par messagerie instantanée à une autre  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Consigner automatiquement les conversations par messagerie instantanée dans Exchange  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Envoyer une conversation par messagerie instantanée sous forme de message électronique  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Écrire un courrier électronique à un contact  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Afficher les invitations de messagerie instantanée manquées  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Vibrer en cas de message instantané entrant  <br/> ||& #x 2714 ; & #x 2776 ; |& #x 2714 ;|& #x 2714 ;|
   
 & #x 2776 ;  Cet appareil vibre qu’à chaque fois qu’un message instantané est reçu, même si le message actuel dans la conversation par messagerie instantanée s’affiche.
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype pour les entreprises à Skype Business audio et vidéo


 | Fonctionnalité  | Skype pour le client de bureau d’entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype pour Business-Skype pour voix entreprise  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Skype pour l’entreprise pour la vidéo Business Skype  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
   
> [!NOTE]
> Sur un appareil mobile, la vidéo nécessite, par défaut, une connexion WiFi.  
  
## <a name="conferencing-support"></a>Prise en charge de la conférence


 | Fonctionnalité  | Skype pour le client de bureau d’entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Cliquer sur un lien dans le rappel de réunion pour participer à une réunion vidéo ou VoIP  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Participer à une conversation par messagerie instantanée à plusieurs  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Utiliser la conférence d’appel sortant (le serveur appelle l’appareil mobile)  <br/> |& #x 2714 ; & #x 2776 ; |& #x 2714 ; & #x 2776 ; |& #x 2714 ; & #x 2776 ; |& #x 2714 ; & #x 2776 ; |
|Utiliser l’audioconférence rendez-vous  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Visualiser la vidéo de la réunion  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Afficher une vidéo à plusieurs (vue galerie)  <br/> |& #x 2714 ;||||
|Patienter dans la salle d’attente de réunion  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Utiliser des commandes de présentateur lors des réunions  <br/> |& #x 2714 ;||||
|Accéder à une liste de réunion détaillée pour les conférences audio  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Accéder à une liste de réunion détaillée pour les conférences par messagerie instantanée  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Partager le Bureau ou un programme  <br/> |& #x 2714 ;||||
|Afficher le bureau partagé ou programme (VbSS ou RDP)  <br/> |& #x 2714 ;|& #x 2714 ; & #x 2777 ; |& #x 2714 ; & #x 2777 ; |& #x 2714 ; & #x 2777 ; |
|Afficher les fichiers PowerPoint partagés  <br/> |& #x 2714 ;|& #x 2714 ; & #x 2777 ; |& #x 2714 ; & #x 2777 ; |& #x 2714 ; & #x 2777 ; |
|Charger et présenter des fichiers PowerPoint  <br/> |& #x 2714 ;||& #x 2714 ; & #x 2777 ; |& #x 2714 ; & #x 2777 ; |
|Utiliser des outils de réunion (utiliser un tableau blanc, mener des enquêtes, partager des fichiers)  <br/> |& #x 2714 ;||||
|Parcourir une liste de vos réunions  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Participer à une réunion même si vous n’avez pas un Skype pour un compte professionnel  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Afficher plus d’informations sur les participants à la réunion  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Commencer une conversation de groupe non planifiée avec plusieurs participants directement de votre client ou appareil   <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;||
   
 & #x 2776 ;  Pour les utilisateurs Office 365, cette fonctionnalité nécessite Enterprise Voice, qui fait partie de la licence E5.
  
 & #x 2777 ;  Nécessite une connexion WiFi par défaut.
  
## <a name="telephony-support"></a>Prise en charge de la téléphonie


 | Fonctionnalité  | Skype pour le client de bureau d’entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Dans Skype pour les entreprises, cliquez sur l’icône d’appel pour appeler un contact  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Transférer un appel  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;||
|Transfert consultatif  <br/> |& #x 2714 ; & #x 2778 ; ||||
|Gérer le transfert d'appel  <br/> |& #x 2714 ; & #x 2776 ; |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Gérer les paramètres d'appel d'équipe  <br/> |& #x 2714 ; & #x 2776 ; ||||
|Gérer les délégués  <br/> |& #x 2714 ; & #x 2776 ; ||||
|Appeler un groupe Response Group  <br/> |& #x 2714 ; & #x 2776 ; ||||
|Prendre en charge des services d’urgence  <br/> |& #x 2714 ; & #x 2777 ; ||||
|Passer un appel pour le compte d'un autre contact (scénario responsable/délégué)  <br/> |& #x 2714 ; & #x 2776 ; ||||
|Gérer les appels d’un autre contact, si configuré en tant que délégué  <br/> |& #x 2714 ; & #x 2776 ; |& #x 2714 ; & #x 2776 ; |& #x 2714 ; & #x 2776 ; |& #x 2714 ; & #x 2776 ; |
|Utiliser l’appel via le Bureau   <br/> |& #x 2714 ; & #x 2776 ; |& #x 2714 ;|& #x 2714 ;||
|Accéder à la messagerie vocale  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;||
|Utiliser le clavier dans Skype pour les entreprises  <br/> |& #x 2714 ; & #x 2776 ; |& #x 2714 ;|& #x 2714 ;||
   
 & #x 2776 ;  Disponible à Skype pour les utilisateurs professionnels en ligne et/ou Office 365 E5, et les utilisateurs hébergés sur Skype pour Business Server ou de Lync Server 2013 avec Enterprise Voice est activé.
  
 & #x 2777 ;  Pour Skype pour les utilisateurs professionnels en ligne et/ou d’Office 365, cette fonctionnalité est prise en charge par les partenaires Microsoft.
  
 & #x 2778 ;  Client de bureau Windows uniquement.
  
## <a name="external-user-support"></a>Prise en charge des utilisateurs externes


 | Fonctionnalité  | Skype pour le client de bureau d’entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Démarrer une conversation par messagerie instantanée avec un contact public  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Démarrer une conversation par messagerie instantanée avec un contact fédéré  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Mener des appels à deux avec des utilisateurs externes  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Mener des appels à plusieurs avec des utilisateurs externes  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Utiliser l’appel via le bureau pour joindre un contact fédéré sur son téléphone mobile en appelant leur numéro Professionnel publié par & #x 2776 ;            <br/> ||& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
   
 & #x 2776 ;  Par défaut, les utilisateurs fédérés ont le niveau de confidentialité Contacts externes. Pour que vous puissiez joindre un contact fédéré sur son téléphone mobile en composant son numéro professionnel publié, le contact fédéré doit manuellement vous assigner le niveau de confidentialité Collègues.
  
## <a name="address-book-integration"></a>Intégration du carnet d’adresses


 | Fonctionnalité  | Skype pour le client de bureau d’entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Appeler les contacts du carnet d’adresses de l’appareil  <br/> ||& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Rendre Skype pour les appels professionnels aux contacts directement à partir du carnet d’adresses de périphérique  <br/> ||||& #x 2714 ;|
   
## <a name="archiving-and-compliance-support"></a>Prise en charge de l’archivage et de la conformité


 | Fonctionnalité  | Skype pour le client de bureau d’entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Fournir l’archivage côté client  <br/> |& #x 2714 ;||||
|Fournir l’enregistrement côté client  <br/> |& #x 2714 ; & #x 2776 ; ||||
   
 & #x 2776 ;  Non disponible pour Skype pour les utilisateurs professionnels en ligne et/ou d’Office 365.
  
## <a name="modern-authentication"></a>Authentification moderne

Ce tableau couvre les fonctionnalités qui requièrent la prise en charge de l'authentification moderne.
  
Authentification moderne requiert également une topologie décrite dans [Skype pour les topologies métiers pris en charge avec l’authentification moderne](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Fonctionnalité  | Skype pour le client de bureau d’entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Authentification moderne  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Authentification multifacteur  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Authentification avec certificat  <br/> |& #x 2714 ; (périphérique à un domaine uniquement)  <br/> ||& #x 2714 ;|& #x 2714 ;|
|Gestion des applications mobiles (via Intune)  <br/> |||& #x 2714 ;|& #x 2714 ;|
   

