---
title: Planifier les options Occupé pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: En savoir plus sur la fonctionnalité options occupées dans Skype entreprise Server.
ms.openlocfilehash: 8e88b4bf3b92c7fea9bcf79822e2711ff3bee7de
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277103"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>Planifier les options Occupé pour Skype Entreprise Server
 
En savoir plus sur la fonctionnalité options occupées dans Skype entreprise Server.
  
Busy Options est une nouvelle stratégie de voix de la mise à jour cumulative de juillet 2016, qui vous permet de configurer la manière dont les appels entrants sont gérés lorsqu'un utilisateur participe déjà à un appel ou à une conférence, ou lorsqu'il a mis un appel en attente. Les nouveaux appels ou les appels entrants peuvent être rejetés avec une tonalité d’occupation ou sont transférés vers la messagerie vocale. 
  
La stratégie Busy Options est prise en charge pour le basculement et la récupération d’urgence sur les pools frontaux associés et les serveurs Survivable Branch Server.
  
Cette rubrique décrit la fonctionnalité Busy Options. Pour savoir comment installer et configurer la fonctionnalité Busy Options, reportez-vous à [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).
  
## <a name="configuration-options"></a>Options de configuration

Si Busy Options est activée pour l'organisation, l'ensemble des utilisateurs de votre organisation, qu'il s'agisse des utilisateurs de Voix Entreprise ou non, peuvent utiliser les fonctionnalités suivantes :
  
- Busy on Busy : les nouveaux appels entrants seront rejetés avec une tonalité d’occupation si l'utilisateur est occupé.
    
- Voicemail on Busy : les nouveaux appels entrants seront transférés vers la messagerie si l'utilisateur est occupé.
    
La fonctionnalité Busy Option fournit une capacité de basculement. Dans le cas où un problème se produit et que les utilisateurs basculent vers un autre serveur frontal ou vers un autre pool dans Skype entreprise Server, leurs paramètres d’options occupés seront conservés.
  
Quelle que soit la manière dont ils ont configuré Busy Option, les utilisateurs participant à un appel ou une conférence, ou ceux ayant mis un appel en absence, peuvent toujours lancer de nouveaux appels ou de nouvelles conférences.   
  
Après la configuration, le paramètre options de disponibilité est activé pour tous les appareils et clients de l’utilisateur Skype entreprise. En fonction des paramètres de la fonctionnalité Busy Option des utilisateurs, la sonnerie de l'appel qui est rejeté ou transféré vers la messagerie vocale ne retentira pas sur le dispositif d'appel de l'utilisateur (que ce soit Macintosh, Bureau Windows, clients mobiles ou téléphones IP) sur lequel il est connecté. 
  
Les utilisateurs verront les notifications d’appel manqué sur leurs clients et appareils Skype entreprise et ils seront également avertis par e-mail. Une notification s'affichera sur le client Skype Entreprise des appelants dont l'appel a été rejeté en raison du statut Busy on Busy, les informant que l'utilisateur qu'ils ont tenté de joindre est déjà en communication.
  
Vous pouvez configurer la fonctionnalité d’options occupées en utilisant les cmdlets PowerShell Skype entreprise pour:
  
- Activer ou désactiver la stratégie de voix Busy Options pour l'entreprise.
    
- Administrer le statut Busy on Busy ou Voicemail on Busy pour l'ensemble des utilisateurs de l'entreprise.
    
- Administrer le statut Busy on Busy ou Voicemail on Busy pour l'ensemble des utilisateurs hébergés sur un pool frontal spécifique.
    
- Administrer le statut Busy on Busy ou Voicemail on Busy pour une liste d'utilisateurs.
    
- Administrer le statut Busy on Busy ou Voicemail on Busy pour un utilisateur spécifique.
    
## <a name="interoperability-with-voice-applications"></a>Interopérabilité avec les applications Voix

Les options occupées permettent l’interopérabilité avec les applications vocales suivantes dans Skype entreprise:
  
- Response Groups (RGS)
    
  - La fonctionnalité Busy Options définie sur les chiffres Response Group sera ignorée par le système ; plusieurs appels simultanés seront autorisés.  
    
  - L'expérience actuelle de routage des participants dans Response Groups restera inchangée pour les agents avec les paramètres Busy Options.
    
  - Les appels provenant de Response Groups à destination des utilisateurs qui sont des agents Response Groups ne seront pas limités par les paramètres Busy Options et l'expérience RGS actuelle sera maintenue.
    
  - Les appels non associés à RGS vers les agents seront honorés par leurs paramètres Busy Options.
    
- Appel d’équipe
    
  - Les appels entrants vers des utilisateurs qui sont configurés pour un appel d’équipe sont classés par ordre de priorité pour ignorer les valeurs occupées et les messages vocaux sur les paramètres occupés.
    
  - L'expérience actuelle de l'appel d'équipe restera inchangée avec la fonctionnalité Busy Options définie pour les utilisateurs.
    
  - Les appels non associés à l'appel d'équipe vers les agents seront honorés par leurs paramètres Busy Options.
    
- Délégation patron/administrateur  
    
  - Les appels entrants vers des utilisateurs qui sont configurés pour un responsable/une délégation d’administration, en tant que patron ou administrateur, sont classés par ordre de priorité pour ignorer les disponibilités et les messages vocaux sur les paramètres occupés.
    
  - L'expérience actuelle de délégation patron/administrateur restera inchangée avec la fonctionnalité Busy Options définie pour les administrateurs ou les patrons.
    
  - Les appels non associés à la délégation patron/administrateur vers les administrateurs seront honorés par leurs paramètres Busy Options.
    
- Mode partage de lignes    
    
  - Les paramètres Busy Options sur les comptes d'utilisateur configurés pour le mode partage de ligne seront ignorés.  
    
  - Le champ natif occupé de la ligne en fonction de la disponibilité et de la boîte vocale est accepté à la place.
    
- Service de parcage des appels  
    
  - Les appels parqués qui n'ont pas été extraits et qui sont émis de nouveau en raison de l'expiration du délai d'attente seront émis systématiquement vers l'utilisateur qui a parqué l'appel via la fonctionnalité Busy Options.  
    
- Conférence téléphonique
    
  - Les utilisateurs qui participent à une conférence téléphonique sont considérés comme occupés et les nouveaux appels entrants sont rejetés avec une tonalité d’occupation ou transférés vers la messagerie vocale en fonction des paramètres définis pour Busy Options.
    
  - Les utilisateurs qui participent à une conférence peuvent toujours démarrer de nouveaux appels ou de nouvelles conférences via la fonctionnalité Busy Options.
    
  - Les utilisateurs qui participent à une conférence peuvent toujours recevoir des invitations pour participer à de nouvelles conférences, mais les nouveaux appels d’égal à égal seront rejetés en fonction des paramètres définis pour Busy Options.
    
- Sonnerie simultanée et transfert d’appel
    
    La fonctionnalité Busy on Busy n’est pas conçue pour fonctionner avec la sonnerie simultanée et le transfert d’appel.
    

