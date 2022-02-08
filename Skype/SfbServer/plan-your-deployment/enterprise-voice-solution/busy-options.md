---
title: Planifier les options Busy pour Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Découvrez la fonctionnalité Busy Options dans Skype Entreprise Server.
ms.openlocfilehash: 6d020887b4eac47cb54ba96e8b72a0393f21014c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387832"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a>Planifier les options Busy pour Skype Entreprise Server
 
Découvrez la fonctionnalité Busy Options dans Skype Entreprise Server.
  
Busy Options est une nouvelle stratégie de voix introduite dans la mise à jour cumulative de juillet 2016 qui vous permet de configurer la façon dont les appels entrants sont gérés lorsqu’un utilisateur est déjà en cours d’appel ou de conférence, ou qu’un appel est mis en attente. Les appels nouveaux ou entrants peuvent être rejetés avec une signal occupé ou transmis à la messagerie vocale. 
  
La stratégie Busy Options est prise en charge pour leover et la récupération d’urgence sur les pools frontaux couplés et les serveurs Survivable Branch Servers (SBS).
  
Cette rubrique décrit les fonctionnalités de Busy Options. Pour plus d’informations sur l’installation et la configuration de Busy Options, voir [Install and configure Busy Options for Skype Entreprise Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).
  
## <a name="configuration-options"></a>Options de configuration

Si Busy Options est activée pour l’organisation, tous les utilisateurs de votre organisation, les utilisateurs Voix Entreprise et non Voix Entreprise, peuvent utiliser les fonctionnalités suivantes :
  
- Occupé(s) : dans lequel les nouveaux appels entrants sont rejetés avec une signal occupé si l’utilisateur est occupé.
    
- Messagerie vocale sur busy : dans laquelle les nouveaux appels entrants sont transmis à la messagerie vocale si l’utilisateur est occupé.
    
La fonctionnalité Busy Options offre une fonctionnalité deover. Si un problème se produit et que les utilisateurs échouent vers un autre serveur frontal ou un autre pool dans Skype Entreprise Server, leurs paramètres Busy Options sont conservés.
  
Quelle que soit la configuration de leurs options d’occupé, les utilisateurs d’un appel ou d’une conférence, ou ceux qui ont un appel en attente, ne sont pas empêchés de lancer de nouveaux appels ou conférences. 
  
Après la configuration, le paramètre Busy Options est en vigueur pour tous les appareils et clients d’appel Skype Entreprise utilisateur. En fonction des paramètres Busy Options de l’utilisateur, l’appel rejeté ou envoyé à la messagerie vocale ne sonne pas sur les périphériques d’appel de l’utilisateur (y compris Macintosh, Windows Desktop, clients mobiles ou téléphones IP) sur lesquels l’utilisateur est connecté. 
  
Les utilisateurs voient les notifications d’appel manqué sur leurs clients et appareils Skype Entreprise, et ils sont également avertis par courrier électronique. Les appelants dont l’appel a été rejeté en raison de Busy on Busy voient une notification dans leur client Skype Entreprise indiquant que l’utilisateur qu’ils ont tenté de joindre est occupé lors d’un autre appel.
  
Vous pouvez configurer la fonctionnalité Busy Options à l’aide Skype Entreprise cmdlets PowerShell pour :
  
- Activez ou désactivez la stratégie Busy Options Voice pour le Enterprise.
    
- Administrer Busy on Busy ou Voicemail on Busy pour tous les utilisateurs du Enterprise.
    
- Administrer Busy on Busy ou Voicemail on Busy pour tous les utilisateurs d’un pool frontal particulier.
    
- Administrer Busy on Busy ou Voicemail on Busy pour obtenir la liste des utilisateurs.
    
- Administrer Busy on Busy ou Voicemail on Busy pour un seul utilisateur.
    
## <a name="interoperability-with-voice-applications"></a>Interopérabilité avec les applications vocales

Busy Options offre une interopérabilité avec les applications Voice suivantes dans Skype Entreprise :
  
- Response Groups (RGS)
    
  - Les options Busy définies sur les numéros Response Group sont ignorées par le système . plusieurs appels simultanés seront autorisés. 
    
  - L’expérience actuelle de routage attendant dans Response Groups reste inchangée pour les agents avec les paramètres Busy Options.
    
  - Les appels provenant de Response Groups vers les utilisateurs qui sont des agents Response Groups ne seront pas limitées par les paramètres Busy Options et l’expérience RGS actuelle sera conservée.
    
  - Les appels non liés à RGS aux agents seront honorés par leurs paramètres Busy Options.
    
- Appel d’équipe
    
  - Les appels entrants aux utilisateurs qui sont configurer pour un appel d’équipe seront classés par ordre de priorité pour ignorer les paramètres Busy on Busy et Voicemail on Busy.
    
  - L’expérience actuelle de l’appel d’équipe reste inchangée avec busy options définies pour les utilisateurs.
    
  - Les appels non liés à l’appel d’équipe à ces utilisateurs seront honorés par leurs paramètres Busy Options.
    
- Délégation responsable/administrateur 
    
  - Les appels entrants aux utilisateurs qui sont configurer pour une délégation de chef/administrateur en tant que chef ou administrateur seront hiérarchisés pour ignorer les paramètres Busy on Busy et Voicemail on Busy.
    
  - L’expérience actuelle de délégation de responsable/administrateur reste inchangée avec busy options définies pour les administrateurs ou les responsables.
    
  - Les appels non associés à la délégation d’administrateur/de délégation d’administrateur aux administrateurs seront honorés par leurs paramètres Busy Options.
    
- Mode partage de lignes 
    
  - Les paramètres Busy Options sur les comptes d’utilisateurs qui sont configurer pour l’apparence de ligne partagée sont ignorés. 
    
  - Les options Busy on Busy et Voicemail on Busy natives de l’apparence de ligne partagée seront honorées à la place.
    
- Service de parc d’appel 
    
  - Les appels par parcés qui n’ont pas été récupérés et qui sonnent en raison du délai d’arrêt seront autorisés à sonner pour l’utilisateur qui a par parcé l’appel par busy options. 
    
- Conférence téléphonique
    
  - Les utilisateurs des appels de conférence sont considérés comme occupés et les nouveaux appels entrants sont rejetés avec une signal occupé ou transmis à la messagerie vocale en fonction de leurs paramètres Busy Options.
    
  - Les utilisateurs des conférences ne sont pas empêchés de lancer de nouveaux appels ou conférences par Busy Options.
    
  - Les utilisateurs des conférences peuvent toujours recevoir de nouvelles invitations aux conférences, mais les nouveaux appels d’égal à égal seront rejetés en fonction de leurs paramètres Busy Options.
    
- Sonnerie simultanée et forwarding d’appel
    
    La fonctionnalité Busy on Busy n’est pas conçue pour fonctionner avec la sonnerie simultanée et le forwarding d’appel.
    

