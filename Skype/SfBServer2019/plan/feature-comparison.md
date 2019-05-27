---
title: Comparaison des fonctionnalités de client de bureau pour Skype entreprise Server 2019
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 'Résumé: les administrateurs Skype entreprise Server 2019 ou Skype entreprise Online peuvent utiliser ces tableaux pour comprendre les fonctionnalités prises en charge pour les clients.'
ms.openlocfilehash: e26c5020f780542a890b9016057171c59a3eee32
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280569"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2019"></a>Comparaison des fonctionnalités de client de bureau pour Skype entreprise Server 2019

**Résumé:** Les administrateurs Skype entreprise Server 2019 ou Skype entreprise Online peuvent utiliser ces tableaux pour savoir quelles fonctionnalités sont prises en charge sur les clients.

 Avant de déployer ou de procéder à la mise à niveau vers Skype entreprise Server, vérifiez quels clients sont déjà utilisés au sein de votre organisation. Utilisez les tableaux ci-dessous pour comprendre l’impact de la prise en charge des fonctionnalités sur ces clients. Cela peut vous aider à communiquer les modifications aux utilisateurs, opérer le processus de déploiement et bien comprendre les avantages de la mise à niveau vers le dernier client.

Certaines fonctions disponibles avec Skype entreprise Server 2019 ne sont pas disponibles dans Skype entreprise online. Pour plus d’détails, voir limitations relatives aux [comptes d’utilisateurs en ligne ou hybrides](feature-comparison.md#Online-Hybrid) . Les administrateurs de Skype entreprise Online peuvent consulter la rubrique [Description du service Skype entreprise Online](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) pour plus d’informations sur les différentes offres disponibles.

Les tableaux suivants présentent les fonctionnalités disponibles avec chaque client fonctionnant avec Skype entreprise Server 2019 ou Skype entreprise online. Vous pouvez également vous reporter à la rubrique [comparaison des fonctionnalités du client mobile pour Skype entreprise](../../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) pour les comparaisons de fonctionnalités de téléphone intelligent et de client tablette. Les licences d’accès client ou USL (User Subscription License) qu’achète votre organisation auront également un impact sur les fonctionnalités auxquelles les utilisateurs ont accès. Le déploiement du client complet ou de base pour les utilisateurs dépend de la licence ou de l’offre que votre organisation choisit d’acheter. Pour plus d’informations, consultez le [Guide des licences](https://products.office.com/en-us/skype-for-business/it-pros) .

> [!IMPORTANT]
> Skype entreprise Server 2019 et Skype entreprise Online prennent en charge les clients suivants: Lync 2013, Skype entreprise 2015 et Skype entreprise 2016, ainsi que le client Skype entreprise 2019. Pour plus d’informations sur ces clients lorsqu’ils sont utilisés avec d’autres serveurs, voir les [tableaux de comparaison des clients pour Lync Server 2013](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.15%29.aspx) et la [comparaison des fonctionnalités du client de bureau pour Skype entreprise 2015](../../SfbServer/plan-your-deployment/clients-and-devices/desktop-feature-comparison.md). 


> [!NOTE]
> Le client navigateur Skype entreprise Web App et l’application réunions Skype de l’application Windows 10 fournissent uniquement une [prise en charge des réunions](feature-comparison.md#BKMK_Conferencing). Reportez-vous à la rubrique [Plan for Meetings clients (Web App and Meetings App)](../../SfbServer/plan-your-deployment/clients-and-devices/meetings-clients.md) pour en savoir plus sur ces clients.

## <a name="enhanced-presence-support"></a>Prise en charge de la présence avancée
<a name="BKMK_EnhancedPresence"> </a>

Ce tableau couvre les fonctionnalités de présence avancée qui vont plus loin qu’une simple indication spécifiant si un utilisateur est en ligne, hors ligne, occupé, etc. 


| Fonctionnalité                                                                                  | Client Skype entreprise 2015, 2016 ou 2019 | Skype Entreprise sur Mac | Client 2013 Lync |
|:----------------------------------------------------------------------------------------------------|:----------------------------------------------|:--------------------------|:-----------------|
| Publier le statut                                                                                      | &#x2714;                                      | &#x2714; &#x2776;         | &#x2714;         |
| Afficher le statut                                                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Afficher les notes de statut et les messages de notification d'absence du bureau                                                        | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Ajouter un emplacement personnalisé                                                                               | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Ajouter une note personnalisée                                                                                   | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Utiliser une photo à partir d’un site public pour Mon image  <br/> (non disponible dans Skype entreprise Online) | &#x2714;                                      |                           | &#x2714;         |

 &#x2776;  Ne prend pas en charge l’état de publication en fonction des informations de disponibilité du calendrier.

## <a name="contacts-and-contact-groups-support"></a>Prise en charge des contacts et groupes de contacts
<a name="BKMK_Contacts"> </a>

Ce tableau couvre les fonctionnalités liées à la gestion des contacts de messagerie instantanée et de présence. 


| Fonctionnalité                                                                            | Client Skype entreprise 2015, 2016 ou 2019 | Skype Entreprise sur Mac | Client 2013 Lync |
|:----------------------------------------------------------------------------------------------|:----------------------------------------------|:--------------------------|:-----------------|
| Liste de contacts préremplie                                                                   | &#x2714;                                      |                           |                  |
| Afficher et modifier la liste des contacts                                                                 | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Ajouter une balise à des contacts pour les alertes de changement de statut                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Contrôler les niveaux de confidentialité                                                                 | &#x2714;                                      |                           | &#x2714;         |
| Effectuer des recherches dans le carnet d'adresses de l'entreprise                                                             | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Rechercher des contacts Microsoft Outlook                                                             | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Gérer des groupes de contacts                                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Développer des groupes de distribution et des groupes Office 365                                              | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Rechercher des groupes Response Group  <br/> (non disponible dans Skype entreprise Online)                | &#x2714;                                      |                           | &#x2714;         |
| Afficher le groupe de contacts récent                                                                 | &#x2714;                                      |                           | &#x2714;         |
| Afficher le groupe de conversations actuel                                                           | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Afficher d'autres vues des contacts (par exemple, mosaïque)                                           | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Trier les contacts par groupe, relation ou nouveau (personnes qui vous ont ajouté à leur liste de contacts) | &#x2714;                                      |                           | &#x2714;         |
| Trier les contacts selon leur statut (disponibilité)                                                        | &#x2714;                                      |                           | &#x2714;         |
| Rechercher et ajouter des contacts Exchange                                                              | &#x2714;                                      |                           | &#x2714;         |

## <a name="im-support"></a>Prise en charge de la messagerie instantanée
<a name="BKMK_IMSupport"> </a>

Ce tableau couvre les fonctionnalités liées à la prise en charge de la messagerie instantanée.

|Fonctionnalité | Client Skype entreprise 2015, 2016 ou 2019 | Skype Entreprise sur Mac | Client 2013 Lync | 
|:-----|:-----|:-----|:-----|  
|Démarrer une conversation par messagerie instantanée avec un contact  |&#x2714;|&#x2714;|&#x2714;|  
|Parcourir plusieurs conversations par messagerie instantanée/Suivre plusieurs conversations dans une seule fenêtre avec onglets   |&#x2714;|&#x2714;|&#x2714;| 
|Enregistrer des conversations par messagerie instantanée dans Outlook  |&#x2714;|&#x2714; Si l’historique des conversations côté serveur est activé   |&#x2714;|   
|Vérification de l'orthographe |&#x2714;|&#x2714;||   
|Recherche de compétences (avec l'intégration de SharePoint Server)   <br/> (Skype entreprise Server local et SharePoint 2013 local sont requis pour la recherche de compétences.)  |&#x2714;||&#x2714;|
|Intégration de la conversation permanente (Conversation de groupe)   <br/> (non disponible pour Skype entreprise Online)|&#x2714;||&#x2714;|  
|Transformer une salle de conversation permanente en réunion Skype Entreprise d'un simple clic   <br/> (non disponible pour Skype entreprise Online) |&#x2714;||&#x2714;| 
|Images intégrées de l'expéditeur et du destinataire dans la fenêtre de messagerie instantanée |&#x2714;||&#x2714;| 
|Recevoir des messages manuscrits |&#x2714;||&#x2714;| 
|Définir les messages instantanés sur Importance haute |&#x2714;||&#x2714;|

## <a name="meetings-support"></a>Prise en charge des réunions
<a name="BKMK_Conferencing"> </a>

Ce tableau couvre les fonctionnalités liées à la prise en charge des réunions.

> [!NOTE]
>  Les fonctionnalités de réunion Skype entreprise ne sont pas disponibles dans le plan autonome 1 de Skype entreprise online.  Le plan 1 est en cours de [retrait](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement
).

Dans les sessions Skype-à-Skype, un utilisateur du plan 1 de Skype Entreprise Online peut participer au partage de bureau et d'applications s'il est invité par un utilisateur qui a accès aux fonctionnalités de partage.
Pour plus d’informations, reportez-vous à la [Description du service Skype entreprise Online](https://technet.microsoft.com/library/jj822172.aspx). 

|Fonctionnalité | Client 2016 Skype entreprise | Skype Entreprise sur Mac | Skype entreprise Web App | Client 2015 Skype entreprise | Client 2013 Lync | 
|:-----|:-----|:-----|:-----|:-----|:-----|  
|Ajouter l'audio de l'ordinateur  |&#x2714;|&#x2714;|& # x2714; (nécessite un plug-in)  |&#x2714;|&#x2714;| 
|Ajouter la vidéo |&#x2714;|&#x2714;|& # x2714; (nécessite un plug-in) |&#x2714;|&#x2714;| 
|Afficher une vidéo à plusieurs (vue galerie)  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Partage d'écran vidéo    |&#x2714;|&#x2714;|&#x2714; Lecture seule   ||| 
|Utiliser des commandes de présentateur lors des réunions |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;| 
|Accéder à une liste détaillée des réunions |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|  
|Participer à une conversation par messagerie instantanée à plusieurs |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|  
|Partager le bureau (si option activée)  |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; (nécessite un plug-in) |&#x2714;| &#x2714;|
|Partager un programme (si option activée) |&#x2714;|Afficher seulement   |& # x2714; (nécessite un plug-in)  |&#x2714;|&#x2714;|   
|Ajouter des participants anonymes (si option activée) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Utiliser les réunions audio rendez-vous & # x2777;|&#x2714; |&#x2714;|&#x2714;  |&#x2714;|&#x2714;  |
|Démarrer une réunion Conférence maintenant|&#x2714;|&#x2714;||&#x2714;|&#x2714;|  
|Ajouter et présenter des fichiers Microsoft PowerPoint |&#x2714;| &#x2778; Annotations non disponibles   |&#x2714;|&#x2714;|&#x2714;| 
|Parcourir des fichiers Microsoft PowerPoint |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;| 
|Ajouter et modifier des notes de réunion OneNote  |&#x2714;||Modifier uniquement (pas ajouter)  |&#x2714;|&#x2714;|
|Utiliser un tableau blanc |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Mener des sondages |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Télécharger des fichiers pour les partager avec des tiers |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Planifier une réunion ou une conférence |Outlook ou Skype entreprise Web Scheduler  |Outlook ou Skype entreprise Web Scheduler |Skype entreprise Web Scheduler |Outlook ou Skype entreprise Web Scheduler   |Outlook ou Lync Web Scheduler |  
|Q&amp;A Manager |&#x2714;|||||
|Désactiver la vidéo des participants |&#x2714;||&#x2714;|||
|Désactiver la messagerie instantanée pour la réunion |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Désactiver le son des participants |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Inviter tout le monde à participer |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Produire une diffusion de réunion Skype |&#x2714;|||||
|Un délégué peut planifier une réunion pour le compte d'un délégant |&#x2714;|&#x2714;|&#x2714;|||
|Synchroniser les délégués entre Skype Entreprise et Outlook |&#x2714;||&#x2714;|&#x2714;|| 
|Définir la vidéo à la une (verrouiller la vidéo) |&#x2714;||&#x2714;|&#x2714;|&#x2714;| 
|Donner/prendre le contrôle du partage d'écran  |&#x2714;||&#x2714;|||

 &#x2776;  Les participants ne peuvent pas contrôler les bureaux partagés par Skype entreprise sur Mac, Lync pour Mac 2011 ou les utilisateurs de Communicator pour Mac 2011. Les utilisateurs de Skype entreprise sur Mac, de Lync pour Mac 2011 et de Communicator pour Mac 2011 ne peuvent pas contrôler les bureaux partagés par les utilisateurs Windows. Cela ne fonctionne pas non plus avec Skype entreprise Web App sur Max OSX.

 &#x2777;  Pour Skype entreprise Online, cette fonctionnalité nécessite Microsoft RTC Conferencing, Exchange Unified Messaging ou un fournisseur de services d’audioconférence tiers.

 &#x2778;  Le client 2011 Lync pour Mac ne peut pas afficher les présentations PowerPoint de Microsoft Office 2013 lors de leur partage dans une conférence par le biais de l’application Web Skype entreprise.

&#x2779;  Pour les applications 2016 Skype entreprise, vous devez utiliser la version «démarrer en un clic», 16.0.4227 ou une version ultérieure.

&#x2780;  Pour les applications 2015 Skype entreprise, vous devez disposer de la mise à jour de septembre, Build 15.0.4747 ou version ultérieure.

## <a name="voice-telephony-support"></a>Prise en charge de la voix (téléphonie)
<a name="BKMK_Telephony"> </a>

Ce tableau couvre les fonctionnalités liées à la prise en charge des services vocaux.

> [!NOTE]
> Les fonctionnalités de voix de Skype entreprise sont limitées à certaines offres d’abonnement à Skype entreprise online. Pour plus d’informations, reportez-vous à la [Description du service Skype entreprise Online](https://technet.microsoft.com/library/jj822172.aspx). 

 | Fonctionnalité | Client Skype entreprise 2015, 2016 ou 2019 | Skype Entreprise sur Mac | Client 2013 Lync |  
|:-----|:-----|:-----|:-----| 
|Démarrer un appel |&#x2714;|&#x2714;|&#x2714;|
|Cliquer pour appeler un contact |&#x2714;|&#x2714;|&#x2714;|
|Transférer un appel |&#x2714;|&#x2714;|&#x2714;|  
|Gérer le transfert d'appel |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Gérer les paramètres d'appel d'équipe |&#x2714;||&#x2714; &#x2776; |
|Gérer les délégués |&#x2714;|&#x2714;   |&#x2714; &#x2776; |
|Appeler un groupe Response Group|&#x2714;||&#x2714; &#x2776; |
|Prendre en charge les services d'urgence (E-911) |&#x2714;|&#x2714; |&#x2714; &#x2776; |
|Notification de message instantané à un ou plusieurs URI SIP pour un appel E-911 |&#x2714;|&#x2714;|&#x2714;|
|Notification de message instantané à une liste de distribution pour un appel E-911|&#x2714;|&#x2714;|&#x2714;|
|Se connecter à la messagerie vocale, configurer ou changer le message d'accueil |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Notification des appels manqués |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Passer un appel pour le compte d'un autre contact (scénario responsable/délégué) |&#x2714;|&#x2714;|&#x2714; &#x2776; |
|Gérer les appels d'une autre personne, si celle-ci est configurée en tant que déléguée |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Parcage d'appel |&#x2714;||&#x2714; &#x2776; |
|Prise d'appel de groupe |&#x2714;||&#x2714; &#x2776; |
|Routage géodépendant |&#x2714;|&#x2714;|&#x2714;| 
|Gérer un groupe Response Group/d'appel d'équipe |&#x2714;||&#x2714;|

 &#x2776;  Cette fonctionnalité n’est pas disponible dans Skype entreprise online.

## <a name="external-users-support"></a>Prise en charge des utilisateurs externes
<a name="BKMK_ExternalUsers"> </a>

Ce tableau couvre les fonctionnalités liées à la prise en charge des utilisateurs externes hébergés sur le PSTN.


|Fonctionnalité | Client Skype entreprise 2015, 2016 ou 2019 | Skype Entreprise sur Mac | Client 2013 Lync |  
|:-----|:-----|:-----|:-----|  
|Démarrer une conversation par messagerie instantanée avec un contact public |&#x2714;|&#x2714;|&#x2714;| 
|Démarrer une conversation par messagerie instantanée avec un contact fédéré |&#x2714;|&#x2714;|&#x2714;| 
|Mener des appels à deux ou plus avec des utilisateurs externes   <br/> (non disponible dans Skype entreprise Online)  |&#x2714;|&#x2714;|&#x2714;| 

## <a name="recording-support"></a>Prise en charge de l'enregistrement
<a name="BKMK_Recording"> </a>

Ce tableau couvre les fonctionnalités liées à la prise en charge de l’enregistrement des réunions.

| Fonctionnalité | Client Skype entreprise 2015, 2016 ou 2019 | Skype Entreprise sur Mac | Client 2013 Lync |   
|:-----|:-----|:-----|:-----|  
|Enregistrement côté client du son, de la vidéo, du partage d'application, du partage de bureau et du contenu téléchargé |&#x2714; &#x2776; ||&#x2714; &#x2776; |
|Enregistrement côté client des transferts de fichiers, des pages OneNote partagées et des annotations PowerPoint| &#x2714; &#x2777; ||&#x2714; &#x2777; |
|Sélection de la résolution d'enregistrement préférée  |&#x2714;||&#x2714;|

 &#x2776;  L’enregistrement n’est pas disponible dans certaines offres autonomes Skype entreprise online. L'enregistrement nécessite des droits complets de client Skype Entreprise.

 &#x2777;  L’enregistrement de transferts de fichiers, de pages OneNote partagées et d’annotations PowerPoint n’est pas disponible dans Skype entreprise online.

## <a name="modern-authentication"></a>Authentification moderne
<a name="BKMK_Recording"> </a>

Ce tableau couvre les fonctionnalités qui requièrent la prise en charge de l'authentification moderne. 

L’authentification moderne nécessite également une topologie décrite dans [les topologies Skype entreprise prises en charge pour l’authentification moderne](../../SfbServer/plan-your-deployment/modern-authentication/topologies-supported.md).


 | Fonctionnalité | Client Skype entreprise 2015, 2016 ou 2019 | Skype Entreprise sur Mac | Client 2013 Lync | 
|:-----|:-----|:-----|:-----|  
|Authentification moderne |&#x2714;|&#x2714;|&#x2714;|
|Authentification multifacteur|&#x2714;|&#x2714;|&#x2714;|
|Authentification avec certificat |& # x2714; (appareil joint à un domaine uniquement) |&#x2714;|& # x2714; (appareil joint à un domaine uniquement)  |
|Authentification Kerberos |&#x2714;||&#x2714;|

## <a name="archiving-compliance-and-logging-support"></a>Prise en charge de l'archivage, de la conformité et de la journalisation
<a name="BKMK_Archiving"> </a>

Ce tableau présente les fonctionnalités liées à la prise en charge de l’archivage et des fonctions de journalisation.


 | Fonctionnalité | Client Skype entreprise 2015, 2016 ou 2019 | Skype Entreprise sur Mac | Client 2013 Lync |  
|:-----|:-----|:-----|:-----|  
|Archivage des conversations par messagerie instantanée dans l’historique des conversations Outlook|&#x2714; &#x2776; |&#x2714; Si l’historique des conversations côté serveur est activé  |&#x2714; &#x2776; | 
|Archivage côté client du son, de la vidéo, du partage d’applications, du partage de bureau et du contenu téléchargé  |&#x2714; &#x2776; ||&#x2714; &#x2776; |
|Archivage côté client des transferts de fichiers, pages OneNote partagées et annotations PowerPoint (non disponibles dans Skype entreprise Online)  |&#x2714;||&#x2714;|
|Accès aux journaux de connexion à partir de l’icône Skype entreprise dans la barre des tâches |&#x2714;||&#x2714;|

 &#x2776;  Pour les utilisateurs de Skype entreprise Online, cette fonctionnalité nécessite Exchange Online et est contrôlée par l’attribut conservation inaltérable de l’utilisateur.

## <a name="client-limitations"></a>Limitations du client
<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Limitations du client de base
<a name="Full-Basic"> </a>

Les fonctionnalités suivantes sont disponibles avec le client complet et ne sont pas disponibles avec le client de base: 

- Gérer les paramètres d'appel d'équipe

- Gérer les délégués

- Passer un appel pour le compte d'un autre contact (scénario responsable/délégué)

- Gérer les appels d'une autre personne, si celle-ci est configurée en tant que déléguée

- Gestion d’un grand nombre d’appels

- Appeler un groupe Response Group

- Parcage d'appel

- Modifier le message d’accueil

- Prise d'appel de groupe

### <a name="online-or-hybrid-user-account-limitations"></a>Limitations relatives aux comptes d’utilisateurs en ligne ou hybrides
<a name="Online-Hybrid"> </a>

Les comptes d’utilisateur peuvent exister en ligne ou en local, ce qui affectera les fonctionnalités disponibles pour cet utilisateur. Les utilisateurs disposant d’un compte dans Skype entreprise Online ne pourront pas accéder aux fonctions suivantes, même avec le client complet: 

- Présence améliorée: utiliser une photo de n’importe quel site public pour mon image

- Contacts: recherche de Response Groups

- Prise en charge de la messagerie instantanée: intégration des discussions permanentes (discussion de groupe)

- Prise en charge de la messagerie instantanée: remonter une salle de conversation permanente pour une réunion Skype entreprise d’un simple clic

- Utilisateurs externes: diriger des appels à deux ou plusieurs parties avec des utilisateurs externes

## <a name="see-also"></a>Voir aussi
<a name="Types"> </a>

[Planifier des clients et des appareils](../../SfbServer/plan-your-deployment/clients-and-devices/clients-and-devices.md)

[Dernières versions de Skype Entreprise qui utilisent Windows Installer (MSI)](../../SfbServer/sfb-client-updates.md)
