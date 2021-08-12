---
title: Expanseur des paramètres du serveur d’inscriptions
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: La résilience apporte une très grande disponibilité et offre la récupération d’urgence au pool de serveurs d’inscriptions. Lorsqu’il est configuré, un serveur d’inscriptions de sauvegarde permet de prendre le relais d’un serveur d’inscriptions en cas d’échec du serveur d’inscriptions principal, permettant aux utilisateurs de se connecter et de communiquer. Il est possible que les utilisateurs ne disposent pas de toutes les fonctionnalités, en fonction des systèmes défaillants sur le serveur d’inscriptions principal.
ms.openlocfilehash: 75184413222c2de6d580b1ae088b4d65bc7e9851fd10aaaba6b303daa1a53e5e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329638"
---
# <a name="registrar-settings-expander"></a>Expandeur des paramètres du serveur d’inscriptions
 
La résilience apporte une très grande disponibilité et offre la récupération d’urgence au pool de serveurs d’inscriptions. Lorsqu’il est configuré, un serveur d’inscriptions de sauvegarde permet de prendre le relais d’un serveur d’inscriptions en cas d’échec du serveur d’inscriptions principal, permettant aux utilisateurs de se connecter et de communiquer. Il est possible que les utilisateurs ne disposent pas de toutes les fonctionnalités, en fonction des systèmes défaillants sur le serveur d’inscriptions principal.
  
Dans la section **Résilience** de la boîte de dialogue **Modifier les propriétés** de votre Survivable Branch Appliance ou de votre serveur Survivable Branch Server, vous pouvez modifier les paramètres suivants :
  
- **Service utilisateur associé et pool de sauvegarde du bureau d’enregistrement** Dans la liste de listes, sélectionnez le pool frontal Êdition Entreprise ou le serveur frontal Édition Standard qui doit agir en tant que serveur d’inscriptions de sauvegarde pour le Survivable Branch Appliance ou le serveur Survivable Branch Server.
    
- **Activer le failover et la récupération** Sélectionnez ce paramètre pour permettre la détection automatique d’un échec du bureau d’enregistrement et la détermination automatique du fait que le bureau d’enregistrement principal est en cours de mise en service et prêt à reprendre le processus de bureau d’enregistrement.
    
- **Intervalle de détection d’échec (en secondes)** Tapez le nombre de secondes qui doivent s’écoulées avant qu’il soit déterminé que le bureau d’enregistrement principal a échoué. La valeur par défaut est 120 secondes. Ce champ est obligatoire si vous sélectionnez **Activer le basculement et la restauration automatique**.
    
- **Intervalle de détection de retour (s)** Tapez le nombre de secondes qui doivent s’écoulées avant qu’il soit déterminé que le bureau d’enregistrement principal est pris en compte. La valeur par défaut est 240 secondes. Ce champ est obligatoire si vous sélectionnez **Activer le basculement et la restauration automatique**.
    
> [!IMPORTANT]
> Lorsque vous définissez l’intervalle entre deux détections d’échec et de secours, prenez garde à ne pas saisir un intervalle qui provoquera le basculement et le secours si le serveur d’inscriptions ne répond pas pendant un court moment. Le serveur d’inscriptions peut cesser de répondre pendant de courts moments en fonction du chargement du pool ou des serveurs. 
  

