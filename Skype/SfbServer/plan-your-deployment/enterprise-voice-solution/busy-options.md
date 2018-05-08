---
title: Planifier les options Occupé pour Skype Entreprise Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/24/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: En savoir plus sur la fonctionnalité de disponibilité dans Skype pour Business Server 2015.
ms.openlocfilehash: b800989d091a0363e75901c8420d5b71a8030f10
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>Planifier les options Occupé pour Skype Entreprise Server
 
En savoir plus sur la fonctionnalité de disponibilité dans Skype pour Business Server 2015.
  
Busy Options est une nouvelle stratégie de voix de la mise à jour cumulative de juillet 2016, qui vous permet de configurer la manière dont les appels entrants sont gérés lorsqu'un utilisateur participe déjà à un appel ou à une conférence, ou lorsqu'il a mis un appel en attente. Les nouveaux appels ou les appels entrants peuvent être rejetés avec une tonalité d’occupation ou sont transférés vers la messagerie vocale. 
  
La stratégie Busy Options est prise en charge pour le basculement et la récupération d’urgence sur les pools frontaux associés et les serveurs Survivable Branch Server.
  
Cette rubrique décrit la fonctionnalité Busy Options. Pour plus d’informations sur comment installer et configurer les Options de disponibilité, voir [installer et configurer les Options de disponibilité pour Skype pour Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).
  
## <a name="configuration-options"></a>Options de configuration

Si Busy Options est activée pour l'organisation, l'ensemble des utilisateurs de votre organisation, qu'il s'agisse des utilisateurs de Voix Entreprise ou non, peuvent utiliser les fonctionnalités suivantes :
  
- Busy on Busy : les nouveaux appels entrants seront rejetés avec une tonalité d’occupation si l'utilisateur est occupé.
    
- Voicemail on Busy : les nouveaux appels entrants seront transférés vers la messagerie si l'utilisateur est occupé.
    
La fonctionnalité Busy Option fournit une capacité de basculement. Si un problème se produit et les utilisateurs basculement vers un autre serveur frontal ou vers un autre pool dans Skype pour Business Server, leurs paramètres Options occupé (e) seront préservées.
  
Quelle que soit la manière dont ils ont configuré Busy Option, les utilisateurs participant à un appel ou une conférence, ou ceux ayant mis un appel en absence, peuvent toujours lancer de nouveaux appels ou de nouvelles conférences.   
  
Après la configuration, le paramètre Options occupé (e) est en vigueur pour Skype de tous les utilisateurs pour les clients et périphériques d’appel Business. En fonction des paramètres de la fonctionnalité Busy Option des utilisateurs, la sonnerie de l'appel qui est rejeté ou transféré vers la messagerie vocale ne retentira pas sur le dispositif d'appel de l'utilisateur (que ce soit Macintosh, Bureau Windows, clients mobiles ou téléphones IP) sur lequel il est connecté. 
  
Les utilisateurs verront les notifications d’appels manqués sur leur Skype pour les clients professionnels et les appareils, et ils seront avertis par courrier électronique ainsi que. Une notification s'affichera sur le client Skype Entreprise des appelants dont l'appel a été rejeté en raison du statut Busy on Busy, les informant que l'utilisateur qu'ils ont tenté de joindre est déjà en communication.
  
Vous pouvez configurer la fonctionnalité de disponibilité à l’aide de Skype pour les applets de commande PowerShell de l’entreprise :
  
- Activer ou désactiver la stratégie de voix Busy Options pour l'entreprise.
    
- Administrer le statut Busy on Busy ou Voicemail on Busy pour l'ensemble des utilisateurs de l'entreprise.
    
- Administrer le statut Busy on Busy ou Voicemail on Busy pour l'ensemble des utilisateurs hébergés sur un pool frontal spécifique.
    
- Administrer le statut Busy on Busy ou Voicemail on Busy pour une liste d'utilisateurs.
    
- Administrer le statut Busy on Busy ou Voicemail on Busy pour un utilisateur spécifique.
    
## <a name="interoperability-with-voice-applications"></a>Interopérabilité avec les applications Voix

Options de disponibilité fournit une interopérabilité avec les applications vocales suivantes dans Skype pour les entreprises :
  
- Response Groups (RGS)
    
  - La fonctionnalité Busy Options définie sur les chiffres Response Group sera ignorée par le système ; plusieurs appels simultanés seront autorisés.  
    
  - L'expérience actuelle de routage des participants dans Response Groups restera inchangée pour les agents avec les paramètres Busy Options.
    
  - Les appels provenant de Response Groups à destination des utilisateurs qui sont des agents Response Groups ne seront pas limités par les paramètres Busy Options et l'expérience RGS actuelle sera maintenue.
    
  - Les appels non associés à RGS vers les agents seront honorés par leurs paramètres Busy Options.
    
- Appel d’équipe
    
  - Les appels entrants vers les utilisateurs qui sont définies pour un appel d’équipe seront prioritaires pour ignorer occupé (e) sur occupé (e) et la messagerie vocale sur les paramètres occupé (e).
    
  - L'expérience actuelle de l'appel d'équipe restera inchangée avec la fonctionnalité Busy Options définie pour les utilisateurs.
    
  - Les appels non associés à l'appel d'équipe vers les agents seront honorés par leurs paramètres Busy Options.
    
- Délégation patron/administrateur  
    
  - Les appels entrants vers les utilisateurs qui sont configurés pour une délégation/administration du responsable soit en tant que directeur ou un administrateur qui seront prioritaires pour ignorer occupé (e) sur occupé (e) et la messagerie vocale sur les paramètres occupé (e).
    
  - L'expérience actuelle de délégation patron/administrateur restera inchangée avec la fonctionnalité Busy Options définie pour les administrateurs ou les patrons.
    
  - Les appels non associés à la délégation patron/administrateur vers les administrateurs seront honorés par leurs paramètres Busy Options.
    
- Mode partage de lignes    
    
  - Les paramètres Busy Options sur les comptes d'utilisateur configurés pour le mode partage de ligne seront ignorés.  
    
  - Informations de disponibilité native de partagé apparence de la ligne sur occupé (e) et la messagerie vocale sur les options de disponibilité sont honorées à la place.
    
- Service de parcage des appels  
    
  - Les appels parqués qui n'ont pas été extraits et qui sont émis de nouveau en raison de l'expiration du délai d'attente seront émis systématiquement vers l'utilisateur qui a parqué l'appel via la fonctionnalité Busy Options.  
    
- Conférence téléphonique
    
  - Les utilisateurs qui participent à une conférence téléphonique sont considérés comme occupés et les nouveaux appels entrants sont rejetés avec une tonalité d’occupation ou transférés vers la messagerie vocale en fonction des paramètres définis pour Busy Options.
    
  - Les utilisateurs qui participent à une conférence peuvent toujours démarrer de nouveaux appels ou de nouvelles conférences via la fonctionnalité Busy Options.
    
  - Les utilisateurs qui participent à une conférence peuvent toujours recevoir des invitations pour participer à de nouvelles conférences, mais les nouveaux appels d’égal à égal seront rejetés en fonction des paramètres définis pour Busy Options.
    
- Sonnerie simultanée et transfert d’appel
    
    La fonctionnalité Busy on Busy n’est pas conçue pour fonctionner avec la sonnerie simultanée et le transfert d’appel.
    

