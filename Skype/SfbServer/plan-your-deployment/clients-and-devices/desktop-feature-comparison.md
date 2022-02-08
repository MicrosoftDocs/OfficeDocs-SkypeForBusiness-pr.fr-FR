---
title: Comparaison des fonctionnalités du client de bureau pour Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
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
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 'Résumé : Skype Entreprise Server 2015 ou Skype Entreprise Online peuvent utiliser ces tableaux pour comprendre quelles fonctionnalités sont pris en charge sur quels clients.'
ms.openlocfilehash: 1b855cca4830473cd0cb9c4198784cec93868fc7
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388032"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2015"></a>Comparaison des fonctionnalités du client de bureau pour Skype Entreprise Server 2015

**Résumé : Skype Entreprise Server** 2015 ou Skype Entreprise Online peuvent utiliser ces tableaux pour comprendre quelles fonctionnalités sont pris en charge sur quels clients.
  
 Avant de déployer ou de mettre à niveau Skype Entreprise, vérifiez quels clients sont déjà utilisés dans votre organisation. Utilisez les tableaux ci-dessous pour comprendre l’impact de la prise en charge des fonctionnalités sur ces clients. Cela peut vous aider à communiquer les modifications apportées aux utilisateurs, à suivre le processus de déploiement et à bien comprendre les avantages de la mise à niveau vers le dernier client.
  
Certaines fonctionnalités disponibles avec Skype Entreprise Server 2015 ne sont pas disponibles dans Skype Entreprise Online. Pour plus d’informations, consultez les [limitations](desktop-feature-comparison.md#Online-Hybrid) de compte d’utilisateur en ligne ou hybride. Skype Entreprise Les administrateurs en ligne peuvent se reporter à Skype Entreprise [Description du service](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description) en ligne pour plus d’informations sur les différents plans qui leur sont proposés.

Voir [comparaison des fonctionnalités du client de bureau Skype Entreprise 2019](../../../SfBServer2019/plan/feature-comparison.md) pour la prise en charge des clients Skype Entreprise Server 2019.
  
Les tableaux suivants indiquent les fonctionnalités disponibles avec chaque client qui fonctionne avec Skype Entreprise Server 2015 ou Skype Entreprise Online. Vous pouvez également faire référence à la comparaison des fonctionnalités de [client mobile](mobile-feature-comparison.md) Skype Entreprise comparaison des fonctionnalités client pour smartphone et tablette. La licence d’accès au client ou la licence d’abonnement utilisateur que votre organisation achète aura également un impact sur les fonctionnalités disponibles pour vos utilisateurs. Le déploiement du client complet ou de base pour les utilisateurs dépend de la licence ou de l’offre que votre organisation choisit d’acheter. Pour plus [d’informations](https://products.office.com/skype-for-business/it-pros) , voir le Guide des licences.
  
> [!IMPORTANT]
> Skype Entreprise Server 2015 et Skype Entreprise Online prise en charge des clients précédemment publiés suivants : Lync 2013, Lync 2010, Lync 2010 Mobile, Lync Téléphone Edition et Lync 2010 Attendant. Pour plus d’informations sur ces clients lorsqu’ils sont utilisés avec d’autres serveurs, voir les tableaux de comparaison des clients pour [Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-desktop-client-comparison-tables) et client pour [Lync Server 2010](/previous-versions/office/skype-server-2010/gg425836(v=ocs.14)).

> [!NOTE]
> Le client **Lync 2010 Attendant** n’est pas pris en charge dans Skype Entreprise Online.

> [!NOTE]
> Le client Application Web Skype Entreprise navigateur et Skype l’application Réunions Windows 10 uniquement [la prise en charge des réunions](desktop-feature-comparison.md#BKMK_Conferencing). Pour plus [d’informations sur ces clients, voir Plan for Meetings clients (Web App and Meetings App).](meetings-clients.md)
  
## <a name="enhanced-presence-support"></a>Prise en charge améliorée de la présence

<a name="BKMK_EnhancedPresence"> </a>

Ce tableau couvre les fonctionnalités de présence améliorée qui s’étendent au-delà d’une simple indication de la présence d’un utilisateur en ligne, hors connexion, occupé, etc.
  
|Fonctionnalité/fonctionnalité|Skype Entreprise client 2015 ou 2016|Skype Entreprise sur Mac|Client Lync 2013|Application Lync Windows Store|Lync 2010 | Lync 2010 Attendant|Lync Phone Edition|Communicator for Mac 2011|Lync pour Mac 2011|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|État de publication |&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|
|Afficher l’état   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Afficher les notes de statut et les messages de notification d’absence du bureau |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ajouter un emplacement personnalisé |&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Ajouter une note personnalisée |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Utiliser une photo à partir d’un site public pour Mon image (non disponible dans Skype Entreprise Online) |&#x2714;||&#x2714;|||||||

 &#x2776; ne prend pas en charge l’état de publication basé sur les informations de libre/occupé du calendrier.
  
## <a name="contacts-and-contact-groups-support"></a>Prise en charge des contacts et des groupes de contacts

<a name="BKMK_Contacts"> </a>

Ce tableau couvre les fonctionnalités relatives à la gestion des contacts de messagerie instantanée et de présence.

|Fonctionnalité/fonctionnalité|Skype Entreprise client 2015 ou 2016|Skype Entreprise sur Mac | Client Lync 2013 | Application Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync pour Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Liste de contacts pré-remplie |&#x2714;|||||||||
|Afficher et modifier la liste des contacts |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ajouter une balise à des contacts pour les alertes de changement de statut |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;||||
|Contrôler les niveaux de confidentialité |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Effectuer des recherches dans le carnet d’adresses de l’entreprise |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Rechercher des contacts Microsoft Outlook |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gérer des groupes de contacts |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Développer les groupes de distribution et Microsoft 365 groupes |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Rechercher des groupes Response Group  <br/> (non disponible dans Skype Entreprise Online) |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Afficher le groupe de contacts le plus récent |&#x2714;||&#x2714;||&#x2714;|&#x2714;||||
|Afficher le groupe de conversation actuel |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|||
|Afficher d’autres vues des contacts (par exemple, mosaïque) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Trier les contacts par groupe, relation ou nouveau (personnes qui vous ont ajouté à leur liste de contacts) |&#x2714;||&#x2714;|Trier par groupe |&#x2714;|&#x2714;||||
|Trier les contacts par état (disponibilité) |&#x2714;||&#x2714;||&#x2714;|&#x2714;|||&#x2714;|
|Rechercher et ajouter des Exchange contacts |&#x2714;||&#x2714;||||||&#x2714;|

## <a name="im-support"></a>Prise en charge de la messagerie instantanée

<a name="BKMK_IMSupport"> </a>

Ce tableau couvre les fonctionnalités liées à la prise en charge de la messagerie instantanée.

|Fonctionnalité/fonctionnalité | Skype Entreprise client 2015 ou 2016 | Skype Entreprise sur Mac | Client Lync 2013 | Application Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync pour Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Lancer la messagerie instantanée avec un contact ou envoyer un e-mail à un contact |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Naviguer entre plusieurs conversations par messagerie instantanée/Suivre plusieurs conversations dans une seule fenêtre à onglets |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Enregistrer des conversations par messagerie instantanée dans Outlook |&#x2714;|&#x2714;si l’historique des conversations côté serveur est allumé  |&#x2714;|&#x2714;|&#x2714;|&#x2714;||Sauf dans Communicator pour Mac |Enregistré dans Lync pour Mac |
|Utiliser des modèles de conversation existants |||||&#x2714;|&#x2714;||||
|Vérifier l’orthographe |&#x2714;|&#x2714;||&#x2714;|||||&#x2714;|
|Recherche de compétences (avec intégration SharePoint Server)  <br/> (La recherche de compétences Skype Entreprise Server sur site et sur site SharePoint 2013.) |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||
|Intégration de la conversation permanente (conversation de groupe)  <br/> (non disponible pour Skype Entreprise Online) |&#x2714;||&#x2714;|||||||
|Faire d’une salle de conversation permanente une Skype Entreprise réunion en un clic  <br/> (non disponible pour Skype Entreprise Online) |&#x2714;||&#x2714;|||||||
|Images inline de l’expéditeur et du destinataire dans la fenêtre de messagerie instantanée |&#x2714;||&#x2714;|&#x2714;||||||
|Envoyer des messages manuscrits ||||&#x2714;||||||
|Recevoir des messages manuscrits |&#x2714;||&#x2714;|&#x2714;||||||
|Définir les messages instantanés comme étant de haute importance |&#x2714;||&#x2714;|||||||
|Transférer des fichiers dans des conversations de messagerie instantanée d’égal à égal |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|

## <a name="meetings-support"></a>Prise en charge des réunions

<a name="BKMK_Conferencing"> </a>

Ce tableau couvre les fonctionnalités liées à la prise en charge des réunions.
  
> [!NOTE]
> Skype Entreprise fonctionnalités de réunion ne sont pas disponibles dans Skype Entreprise Online Plan autonome 1.  Le plan 1 est [retiré](../../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement.md).

Dans les sessions Skype-à-Skype, un utilisateur Skype Entreprise Online Plan 1 peut participer au partage de bureau et au partage d’application s’il est invité par un utilisateur ayant accès aux fonctionnalités de partage.
Pour plus d’informations, [voir Skype Entreprise Online Service Description](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description).
  
|Fonctionnalité/fonctionnalité | Skype Entreprise client 2016 | Skype Entreprise sur Mac | Skype Entreprise Web App | Skype Entreprise client 2015 | Client Lync 2013 | Application Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync pour Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Ajouter l’audio de l’ordinateur |&#x2714;|&#x2714;|&#x2714;(nécessite un plug-in) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ajouter la vidéo |&#x2714;|&#x2714;|&#x2714;(nécessite un plug-in) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|&#x2714;|
|Afficher la vidéo à plusieurs (vue galerie) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||
|Partage d'écran sur vidéo |&#x2714;|&#x2714;|&#x2714;en affichage seul |||||||||
|Utiliser des commandes de présentateur lors des réunions |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Accéder à une liste de réunions détaillée |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|||&#x2714;|
|Prendre part à une conversation par messagerie instantanée à plusieurs |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Partager le Bureau (si activée) |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776; (nécessite un plug-in) |&#x2714;|&#x2714;||&#x2714;|||&#x2714; &#x2776; |&#x2714; &#x2776; |
|Partager un programme (si activée) |&#x2714;|Afficher uniquement   |&#x2714;(nécessite un plug-in) |&#x2714;|&#x2714;||&#x2714;||||Afficher uniquement |
|Ajouter des participants anonymes (si activée) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Utiliser les réunions audio rendez-vous |&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714;|&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714;|&#x2714;|||&#x2714;|
|Lancer une réunion Conférence maintenant |&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Ajouter et présenter des fichiers Microsoft PowerPoint |&#x2714;| &#x2778; annotations non disponibles |&#x2714;|&#x2714;|&#x2714;|Présent uniquement |&#x2714;|||| &#x2778; afficher uniquement, annotations non disponibles |
|Naviguer dans les fichiers PowerPoint Microsoft |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||&#x2714;|
|Ajouter et modifier des OneNote de réunion |&#x2714;||Modifier uniquement (pas ajouter) |&#x2714;|&#x2714;|||||||
|Utiliser un tableau blanc |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Mener des sondages |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|||||
|Télécharger fichiers à partager avec d’autres personnes |&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;||||&#x2714;|
|Planifier une réunion ou une conférence |Outlook ou Planificateur Web Skype Entreprise |Outlook ou Planificateur Web Skype Entreprise |Planificateur Web Skype Entreprise |Outlook ou Planificateur Web Skype Entreprise |Outlook ou Lync Web Scheduler |Outlook ou Lync Web Scheduler |Outlook ||||Outlook |
|Gestionnaire de QA&amp; |&#x2714;|||||||||||
|Désactiver la vidéo du participant|&#x2714;||&#x2714;|||||||||
 | |Désactiver la messagerie instantanée de réunion  |&#x2714;||&#x2714;|&#x2714;|&#x2714;|||||||
|Désactiver le son de l’audience   |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Faire de tout le monde un participant |&#x2714;||&#x2714;|&#x2714;|&#x2714;||||||&#x2714;|
|Produire une Réunion Skype diffusion  |&#x2714;|||||||||||
|Le délégué peut planifier une réunion pour le compte d’un délégant  |&#x2714;|&#x2714;|&#x2714;|||||||||
|Synchroniser les délégués entre Skype Entreprise et Outlook |&#x2714;||&#x2714;|||||||||
|Définir la vidéo à la une (verrouiller la vidéo) |&#x2714;||&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Donner/prendre le contrôle du partage d’écran |&#x2714;||&#x2714;|||||||||

 &#x2776; participants ne peuvent pas contrôler les bureaux partagés par Skype Entreprise sur Mac, Lync pour Mac 2011 ou Communicator pour Mac 2011. Skype Entreprise sur Mac, les utilisateurs de Lync pour Mac 2011 et Communicator pour Mac 2011 ne peuvent pas contrôler les bureaux partagés par les Windows utilisateurs. Cela ne fonctionne pas non plus pour les Application Web Skype Entreprise sur Max OSX.
  
 &#x2777; pour Skype Entreprise Online, cette fonctionnalité nécessite la conférence PSTN Microsoft, la messagerie unifiée Exchange ou un fournisseur tiers de services d’audioconférence.
  
 &#x2778; le client Lync pour Mac 2011 ne peut pas afficher les présentations Microsoft Office 2013 PowerPoint lorsqu’elles ont été partagées dans une conférence par le Application Web Skype Entreprise.
  
## <a name="voice-telephony-support"></a>Prise en charge de la voix (téléphonie)

<a name="BKMK_Telephony"> </a>

Ce tableau couvre les fonctionnalités liées à la prise en charge des services vocaux.
  
> [!NOTE]
> Skype Entreprise voice (téléphonie) sont limitées à certains plans d’abonnement Skype Entreprise Online. Pour plus d’informations, [voir Skype Entreprise Online Service Description](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description).
  
| Fonctionnalité/fonctionnalité | Skype Entreprise client 2015 ou 2016 | Skype Entreprise sur Mac | Client Lync 2013 | Application Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync pour Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Lancer un appel |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Cliquer pour appeler un contact  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Transférer un appel |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gérer le transfert d’appel |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gérer les paramètres d'appel d'équipe |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Gérer les délégués |&#x2714;|&#x2714;nécessite Skype Entreprise Server cu4 2015 ou ultérieure |&#x2714; &#x2776; ||&#x2714;||||&#x2714;|
|Démarrer un appel à un groupe Response Group |&#x2714;||&#x2714; &#x2776; ||&#x2714;|&#x2714;||||
|Prise en charge des services d’urgence (E-911)  |&#x2714;|&#x2714;nécessite Skype Entreprise Server cu6 2015 ou ultérieure |&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Notification de messagerie instantanée aux URI SIP pour un appel E-911 |&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Notification de messagerie instantanée à la liste de distribution pour un appel E-911 |&#x2714;||&#x2714;||&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Connecter messagerie vocale, configurer ou modifier le message d’accueil |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Notification d’appel manqué |&#x2714;|&#x2714;|&#x2714; &#x2776; |&#x2714;|&#x2714;|&#x2714;|&#x2714;|||
|Passer un appel pour le compte d'un autre contact (scénario responsable/délégué) |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|||||
|Gérer les appels d'une autre personne, si celle-ci est configurée en tant que déléguée |&#x2714;|&#x2714;|&#x2714; &#x2776; ||&#x2714;|&#x2714;|&#x2714;|||
|Gérer un volume d’appels important |||||&#x2714;|&#x2714;||||
|Parcage d'appel  |&#x2714;||&#x2714; &#x2776; |||||||
|Collecte d'appel de groupe  |&#x2714;||&#x2714; &#x2776; ||||&#x2714;|||
|Routage basé sur un emplacement  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|
|Gérer le groupe d’appels Response Group/Team |&#x2714;||&#x2714;|||||||
|Répondre à l’appel du attendant automatique |&#x2714;||&#x2714;|||||||

&#x2776; cette fonctionnalité n’est pas disponible dans Skype Entreprise Online.
  
## <a name="external-users-support"></a>Prise en charge des utilisateurs externes

<a name="BKMK_ExternalUsers"> </a>

Ce tableau couvre les fonctionnalités liées à la prise en charge des utilisateurs externes sur le réseau PSTN.

|Fonctionnalité/fonctionnalité | Skype Entreprise client 2015 ou 2016 | Skype Entreprise sur Mac | Client Lync 2013 | Application Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync pour Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Démarrer une conversation par messagerie instantanée avec un contact public  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Démarrer une conversation par messagerie instantanée avec un contact fédéré |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;||&#x2714;|&#x2714;|
|Mener des appels à deux ou à plusieurs avec des utilisateurs externes  <br/> (non disponible dans Skype Entreprise Online) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|

## <a name="recording-support"></a>Enregistrement de la prise en charge

<a name="BKMK_Recording"> </a>

Ce tableau couvre les fonctionnalités liées à la prise en charge de l’enregistrement des réunions.
  
| Future/capability** | Skype Entreprise client 2015 ou 2016 | Skype Entreprise sur Mac | Client Lync 2013 | Application Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync pour Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Enregistrement côté client de l’audio, de la vidéo, du partage d’application, du partage de bureau et du contenu téléchargé |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Enregistrement côté client des transferts de fichiers, des pages de OneNote partagées et des annotations PowerPoint client |&#x2714; &#x2777; ||&#x2714; &#x2777; ||&#x2714;|||||
|Sélectionner la résolution d’enregistrement préférée |&#x2714;||&#x2714;|||||||

 &#x2776;'enregistrement est indisponible dans certains plans autonomes Skype Entreprise Online. L’enregistrement nécessite des droits Skype Entreprise client complets.
  
 &#x2777;'enregistrement des transferts de fichiers, des pages de OneNote partagées et des annotations PowerPoint n’est pas disponible dans Skype Entreprise Online.
  
## <a name="modern-authentication"></a>Authentification moderne

<a name="BKMK_Recording"> </a>

Ce tableau couvre les fonctionnalités nécessitant la prise en charge de l’authentification moderne.
  
L’authentification moderne nécessite également une topologie décrite [dans Skype Entreprise topologies pris en charge avec l’authentification moderne](../../plan-your-deployment/modern-authentication/topologies-supported.md).

| Fonctionnalité/fonctionnalité | Skype Entreprise client 2015 ou 2016 | Skype Entreprise sur Mac | Client Lync 2013 | Application Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | Communicator for Mac 2011 | Lync pour Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Authentification moderne |&#x2714;|&#x2714;|&#x2714;|||||||
|Authentification multifacteur  |&#x2714;|&#x2714;|&#x2714;|||||||
|Authentification basée sur les certificats  |&#x2714;(appareil joint au domaine uniquement)| &#x2714;|&#x2714;(appareil joint au domaine uniquement)  |||||||
|Authentification Kerberos |&#x2714;||&#x2714;|||||||

## <a name="archiving-compliance-and-logging-support"></a>Prise en charge de l’archivage, de la conformité et de la journalisation

<a name="BKMK_Archiving"> </a>

Ce tableau couvre les fonctionnalités liées à la prise en charge des fonctions d’archivage et de journalisation.

| Fonctionnalité/fonctionnalité | Skype Entreprise client 2015 ou 2016 | Skype Entreprise sur Mac | Client Lync 2013 | Application Lync Windows Store | Lync 2010 | Lync 2010 Attendant | Lync Phone Edition | **Communicator for Mac 2011** | Lync pour Mac 2011 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Archivage des conversations par messagerie instantanée dans l’historique Outlook conversation |&#x2714; &#x2776; |&#x2714;si l’historique des conversations côté serveur est activé |&#x2714; &#x2776; |&#x2714; &#x2776; |&#x2714;|&#x2714;||Sauf dans Communicator pour Mac |Enregistré dans Lync pour Mac |
|Archivage côté client de l’audio, de la vidéo, du partage d’application, du partage de bureau et du contenu téléchargé |&#x2714; &#x2776; ||&#x2714; &#x2776; ||&#x2714;|||||
|Archivage côté client des transferts de fichiers, des pages de OneNote partagées et des annotations PowerPoint client  <br/> (non disponible dans Skype Entreprise Online)|&#x2714;||&#x2714;||&#x2714;|||||
|Accéder aux journaux de connexion à partir Skype Entreprise icône dans la barre des tâches |&#x2714;||&#x2714;|||||||

 &#x2776; pour les utilisateurs Skype Entreprise Online, cette fonctionnalité nécessite une Exchange Online et est contrôlée par l’attribut Exchange boîte aux lettres In-Place l’utilisateur.
  
## <a name="client-limitations"></a>Limitations du client

<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Restrictions de base appliquées aux certificats par les clients

<a name="Full-Basic"> </a>

Les fonctionnalités ci-dessous sont disponibles à l’aide du client Complet et ne sont pas disponibles avec le client de base :

- Gérer les paramètres d'appel d'équipe
- Gérer les délégués
- Gérer les appels d'une autre personne, si celle-ci est configurée en tant que déléguée
- Gérer un volume d'appels important
- Démarrer un appel à un groupe Response Group
- Parcage d'appel
- Modifier le message d’accueil
- Collecte d'appel de groupe
- Les e-mails de notification d’appel en manque ne sont pas générés lorsqu’un état utilisateur est désactivé et qu’il utilise un client Outlook hérité (2013 ou une précédente)

### <a name="online-or-hybrid-user-account-limitations"></a>Limites de compte d’utilisateur en ligne ou hybride

<a name="Online-Hybrid"> </a>

Les comptes d’utilisateur peuvent exister en ligne ou en local, ce qui affectera les fonctionnalités disponibles pour cet utilisateur. Les utilisateurs  ayant des comptes Skype Entreprise Online n’ont pas accès aux fonctionnalités suivantes, même avec le client Complet :
  
- Présence améliorée : utiliser une photo à partir de n’importe quel site public pour Mon image
- Contacts : rechercher des groupes Response Groups
- Prise en charge de la messagerie instantanée : intégration de la conversation permanente (conversation de groupe)
- Prise en charge de la messagerie instantanée : faire d’une salle de conversation permanente une Skype Entreprise réunion en un clic
- Utilisateurs externes : mener des appels à deux ou à plusieurs avec des utilisateurs externes

## <a name="see-also"></a>Voir aussi

<a name="Types"> </a>

[Planifier les clients et les appareils](clients-and-devices.md)

[Dernières mises à jour pour les versions de Skype Entreprise qui utilisent Windows Installer (MSI)](../../sfb-client-updates.md)