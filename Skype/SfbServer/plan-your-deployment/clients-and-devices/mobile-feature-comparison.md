---
title: Comparaison des fonctionnalités de client mobile pour Skype entreprise
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Résumé : consultez la prise en charge des fonctionnalités pour le client mobile lors de la planification de Skype entreprise Server.'
ms.openlocfilehash: 36ae93e796e4142a9ae3b5fb85ac806c9a38cdca
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777769"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Comparaison des fonctionnalités de client mobile pour Skype entreprise
 
**Résumé :** Consultez la prise en charge de la fonctionnalité pour le client mobile lors de la planification de Skype entreprise Server.
  
Cet article compare les fonctionnalités des clients mobiles Skype entreprise et du client de bureau Skype entreprise dans les catégories suivantes :
  
- Connexion, notifications de transmission et fonctionnalités générales
    
- Présence enrichie
    
- Contacts et groupes de contacts
    
- Messagerie instantanée
    
- Skype entreprise vers Skype entreprise audio et vidéo
    
- Vidéoconférence
    
- Téléphonie
    
- Utilisateurs externes
    
- Archivage et conformité
    
-  Authentification moderne
    
Les tableaux suivants répertorient les fonctionnalités disponibles pour les utilisateurs de Skype entreprise dans un déploiement local de Skype entreprise Server. Les mêmes fonctionnalités sont également disponibles pour les utilisateurs de Skype entreprise Online et Microsoft 365 ou Office 365, sauf indication contraire dans les notes de bas de page du tableau.
  
> [!NOTE]
> Pour obtenir de l’aide et des ressources en ligne pour les utilisateurs finaux, consultez la rubrique [découvrir Skype entreprise](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> Pour comparer les fonctionnalités disponibles dans les autres clients Skype entreprise, voir [Desktop Client Feature Comparison for Skype for Business](desktop-feature-comparison.md). 

> [!NOTE]
> La prise en charge de MCX (Mobility service) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. Tous les clients mobiles Skype entreprise actuels utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs avec des clients hérités qui utilisent MCX devront effectuer une mise à niveau vers un client actuel.
  
## <a name="sign-in-push-notifications-and-general-features"></a>Connexion, notifications de transmission et fonctionnalités générales

 
 | Fonctionnalité/capacité  | Client de bureau Skype entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|La session Skype entreprise reste connectée  <br/> |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|
|Prise en charge des notifications de type push  <br/> |&#x2714; &#x2778; |&#x2714;|&#x2714; &#x2779; |&#x2714; &#x2779; |
|Possibilité de mettre en cache les informations de comptes de plusieurs utilisateurs sur le même appareil  <br/> |&#x2714;||||
|Lecteur d’écran/voix sur  <br/> |&#x2714;|&#x2714; &#x2777;  anglais uniquement  <br/> |&#x2714;|&#x2714;|
|Utiliser un clavier externe pour l’accessibilité  <br/> |&#x2714;||&#x2714;|&#x2714;|
|Prise en charge du programme d’amélioration du produit Microsoft  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; sur Windows Phone, Skype entreprise se déconnecte automatiquement après une période d’inactivité, comme suit :
  
- Si l’utilisateur a activé les notifications de type poussé, Skype entreprise se déconnecte après 10 jours d’inactivité.
    
- Si l’utilisateur n’a pas activé les notifications de type poussé, Skype entreprise se déconnecte dès que l’utilisateur quitte l’application.
    
Sur les appareils iOS, Skype entreprise se déconnecte automatiquement une fois que le client mobile n’a pas contacté le serveur pendant 10 jours en raison d’une perte de connectivité réseau ou d’autres problèmes.
  
 &#x2777; dans l’application uniquement.
  
 Les notifications d' &#x2778; sont disponibles lorsque l’application est en cours d’exécution en arrière-plan.
 
 &#x2779; à la fois Google/Android/GCNS et Apple/APNS mobile Notification Services utilisent le chiffrement HTTPs/TLS pour la remise des notifications. La charge utile de notification est gérée en texte brut pendant le traitement par le fournisseur de notification.
 
-   Skype entreprise pour Android reçoit des notifications simples (fournies via GCNS) sans données client.
-   Skype entreprise pour iOS reçoit des notifications (livrées via APNS), qui peuvent inclure des données client pour l’appel ou le message.
 
  
## <a name="enhanced-presence-support"></a>Prise en charge améliorée de la présence


 | Fonctionnalité/capacité  | Client de bureau Skype entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Publier et afficher le statut  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher le statut basé sur les informations de disponibilité du calendrier  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher les notes de statut et les messages de notification d’absence du bureau  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ajouter un emplacement personnalisé  <br/> |&#x2714;||||
|Ajouter une note personnalisée  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Publier le statut d’après les informations de disponibilité du calendrier  <br/> |&#x2714; &#x2776; ||||
|Définir l’état de présence manuel (par exemple, occupé, ne pas déranger, etc.)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; les clients mobiles Skype entreprise ne mettent pas à jour la présence d’un utilisateur en fonction des informations de disponibilité du calendrier de l’utilisateur. Si un utilisateur de client mobile est également connecté au client de bureau Skype entreprise, le client de bureau met à jour la présence de l’utilisateur en fonction des informations de disponibilité de l’utilisateur. Si l’utilisateur est connecté à un client mobile uniquement, la présence de l’utilisateur n’est pas mise à jour en fonction des informations de disponibilité du calendrier.
  
## <a name="contacts-and-contact-groups-support"></a>Prise en charge des contacts et des groupes de contacts


 | Fonctionnalité/capacité  | Client de bureau Skype entreprise  | Windows Phone  | iOS  | Android |
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
|Développer des groupes de distribution  <br/> |&#x2714;|&#x2714;||&#x2714;|
|Rechercher des groupes Response Group  <br/> |&#x2714; &#x2776; |&#x2714;||&#x2714;|
|Afficher ou masquer les photos des contacts  <br/> |&#x2714;|&#x2714;|||
|Épingler un contact à votre écran d’accueil  <br/> ||&#x2714;|||
   
 &#x2776; non disponible pour les utilisateurs de Skype entreprise Online et/ou de Microsoft 365 ou Office 365.
  
## <a name="instant-messaging-support"></a>Prise en charge de la messagerie instantanée


 | Fonctionnalité/capacité  | Client de bureau Skype entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Lancer une messagerie instantanée avec un contact  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Prendre part à une conversation par messagerie instantanée à plusieurs  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Inviter d’autres personnes à partir d’une fenêtre de conversation  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher les conversations actuelles  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Passer d’une conversation par messagerie instantanée à une autre  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Consigner automatiquement les conversations par messagerie instantanée dans Exchange  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Envoyer une conversation par messagerie instantanée en tant que message électronique  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Écrire un courrier électronique à un contact  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher les invitations de messagerie instantanée manquées  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Vibrer en cas de message instantané entrant  <br/> ||&#x2714; &#x2776; |&#x2714;|&#x2714;|
   
 &#x2776; ce périphérique vibre chaque fois qu’un message instantané est reçu même si le message en cours dans la conversation de messagerie instantanée est affiché
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Skype entreprise vers Skype entreprise audio et vidéo


 | Fonctionnalité/capacité  | Client de bureau Skype entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype entreprise-vers Skype entreprise  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Vidéo Skype entreprise-vers Skype entreprise  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
   
> [!NOTE]
> La vidéo sur un appareil mobile nécessite une connexion WiFi par défaut. 
  
## <a name="conferencing-support"></a>Prise en charge des conférences


 | Fonctionnalité/capacité  | Client de bureau Skype entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Cliquer sur un lien dans le rappel de réunion pour participer à une réunion vidéo ou VoIP  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Prendre part à une conversation par messagerie instantanée à plusieurs  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Utiliser la conférence d’appel sortant (le serveur appelle l’appareil mobile)  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Utiliser l’audioconférence rendez-vous  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Visualiser la vidéo de la réunion  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher une vidéo à plusieurs (mode Galerie)  <br/> |&#x2714;||||
|Patienter dans la salle d’attente de réunion  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Utiliser des commandes de présentateur lors des réunions  <br/> |&#x2714;||||
|Accéder à une liste de réunion détaillée pour les conférences audio  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Accéder à une liste de réunion détaillée pour les conférences par messagerie instantanée  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Partager le Bureau ou un programme  <br/> |&#x2714;||||
|Afficher le bureau ou le programme partagé (VbSS ou RDP)  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Afficher les fichiers PowerPoint partagés  <br/> |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777;&#x2778; |&#x2714; &#x2777; &#x2778;|
|Charger et présenter des fichiers PowerPoint  <br/> |&#x2714;||&#x2714; &#x2777; |&#x2714; &#x2777; |
|Utiliser les outils de réunion (utiliser le tableau blanc, mener des sondages, partager des fichiers)  <br/> |&#x2714;||||
|Parcourir une liste de vos réunions  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participer à une réunion même si vous n’avez pas de compte Skype entreprise  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher plus d’informations sur les participants à la réunion  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Démarrer une conversation de groupe non planifiée avec plusieurs participants directement à partir de votre client ou appareil  <br/> |&#x2714;|&#x2714;|&#x2714;||
   
 &#x2776; pour les utilisateurs de Microsoft 365 ou Office 365, cette fonctionnalité nécessite voix entreprise, qui fait partie de la licence E5.
  
 &#x2777; nécessite une connexion WiFi par défaut.
 
 &#x2778; l’affichage de la vidéo incorporée dans les présentations PowerPoint n’est pas pris en charge.
  
## <a name="telephony-support"></a>Prise en charge de la téléphonie


 | Fonctionnalité/capacité  | Client de bureau Skype entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Dans Skype entreprise, appuyez sur l’icône d’appel pour appeler un contact.  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Transférer un appel  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Transfert consultatif  <br/> |&#x2714; &#x2778; ||||
|Gérer le transfert d’appel  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|
|Gérer les paramètres d'appel d'équipe  <br/> |&#x2714; &#x2776; ||||
|Gérer les délégués  <br/> |&#x2714; &#x2776; ||||
|Démarrer un appel à un groupe Response Group  <br/> |&#x2714; &#x2776; ||||
|Prise en charge des services d’urgence  <br/> |&#x2714; &#x2777; ||||
|Passer un appel pour le compte d'un autre contact (scénario responsable/délégué)  <br/> |&#x2714; &#x2776; ||||
|Gérer les appels d’un autre contact, s’il est configuré en tant que délégué  <br/> |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714; &#x2776; |
|Utiliser l’appel via le Bureau  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
|accéder à sa messagerie vocale ;  <br/> |&#x2714;|&#x2714;|&#x2714;||
|Utiliser le clavier dans Skype entreprise  <br/> |&#x2714; &#x2776; |&#x2714;|&#x2714;||
   
 &#x2776; disponible pour les utilisateurs de Skype entreprise Online et/ou Office 365 E5, et les utilisateurs hébergés sur Skype entreprise Server ou Lync Server 2013 avec voix entreprise activée.
  
 &#x2777; pour les utilisateurs de Skype entreprise Online et/ou Microsoft 365 ou Office 365, cette fonctionnalité est prise en charge par les partenaires Microsoft.
  
 &#x2778; client de bureau Windows uniquement.
  
## <a name="external-user-support"></a>Prise en charge des utilisateurs externes


 | Fonctionnalité/capacité  | Client de bureau Skype entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Démarrer une conversation par messagerie instantanée avec un contact public  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Démarrer une conversation par messagerie instantanée avec un contact fédéré  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Mener des appels à deux avec des utilisateurs externes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Mener des appels à plusieurs avec des utilisateurs externes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Utiliser l’appel via le Bureau pour joindre un contact fédéré sur son téléphone mobile en appelant leur numéro de travail publié &#x2776;            <br/> ||&#x2714;|&#x2714;|&#x2714;|
   
 &#x2776; par défaut, la relation de confidentialité des contacts externes est attribuée aux utilisateurs fédérés. Pour pouvoir joindre un contact fédéré sur son téléphone mobile en appelant son numéro professionnel publié, le contact fédéré doit vous affecter manuellement la relation de confidentialité des collègues.
  
## <a name="address-book-integration"></a>Intégration du carnet d’adresses


 | Fonctionnalité/capacité  | Client de bureau Skype entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Contacter le carnet d’adresses de l’appareil  <br/> ||&#x2714;|&#x2714;|&#x2714;|
|Effectuer des appels Skype entreprise vers des contacts directement à partir du carnet d’adresses de l’appareil  <br/> ||||&#x2714;|
   
## <a name="archiving-and-compliance-support"></a>Prise en charge de l’archivage et de la conformité


 | Fonctionnalité/capacité  | Client de bureau Skype entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Fournir l’archivage côté client  <br/> |&#x2714;||||
|Fournir l’enregistrement côté client  <br/> |&#x2714; &#x2776; ||||
   
 &#x2776; non disponible pour les utilisateurs de Skype entreprise Online et/ou de Microsoft 365 ou Office 365.
  
## <a name="modern-authentication"></a>Authentification moderne

Ce tableau couvre les fonctionnalités qui nécessitent une prise en charge pour l’authentification moderne.
  
L’authentification moderne nécessite également une topologie décrite dans les [topologies Skype entreprise prises en charge avec l’authentification moderne](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Fonctionnalité/capacité  | Client de bureau Skype entreprise  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Authentification moderne  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Authentification multifacteur  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Authentification basée sur un certificat  <br/> |&#x2714; (appareil joint à un domaine uniquement)  <br/> ||&#x2714;|&#x2714;|
|Gestion des applications mobiles (via Intune)  <br/> |||&#x2714;|&#x2714;|
   

