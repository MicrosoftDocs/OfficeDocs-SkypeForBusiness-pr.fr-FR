---
title: Expanseur des paramètres du serveur d’inscriptions
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: f6ea6907942111db92ca3bfe2dfef1712bd53a62
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217155"
---
# <a name="registrar-settings-expander"></a>Expanseur des paramètres du serveur d’inscriptions
 
La résilience apporte une très grande disponibilité et offre la récupération d’urgence au pool de serveurs d’inscriptions. Lorsqu’il est configuré, un serveur d’inscriptions de sauvegarde permet de prendre le relais d’un serveur d’inscriptions en cas d’échec du serveur d’inscriptions principal, permettant aux utilisateurs de se connecter et de communiquer. Il est possible que les utilisateurs ne disposent pas de toutes les fonctionnalités, en fonction des systèmes défaillants sur le serveur d’inscriptions principal.
  
Dans la section **Résilience** de la boîte de dialogue **Modifier les propriétés** de votre Survivable Branch Appliance ou de votre serveur Survivable Branch Server, vous pouvez modifier les paramètres suivants :
  
- **Service utilisateur associé et pool de serveurs d’inscriptions de sauvegarde** Dans la liste déroulante, sélectionnez le pool frontal Enterprise Edition ou le serveur frontal Standard Edition qui doit agir comme serveur d’inscriptions de sauvegarde pour le Survivable Branch Appliance ou le serveur Survivable Branch Server.
    
- **Activer le basculement et la restauration automatique** Sélectionnez ce paramètre pour autoriser la détection automatique d’un serveur d’inscriptions défaillant et la détermination automatique du fait que le serveur d’inscriptions principal est sauvegardé et prêt à reprendre le processus de serveur d’inscriptions.
    
- **Intervalle de détection des échecs (s)** Tapez le nombre de secondes qui doivent s’écouler avant qu’il soit déterminé que le serveur d’inscriptions principal a échoué. La valeur par défaut est 120 secondes. Ce champ est obligatoire si vous sélectionnez **Activer le basculement et la restauration automatique**.
    
- **Intervalle de détection de secours (s)** Tapez le nombre de secondes qui doivent s’écouler avant qu’il soit déterminé que le serveur d’inscriptions principal est sauvegardé. La valeur par défaut est 240 secondes. Ce champ est obligatoire si vous sélectionnez **Activer le basculement et la restauration automatique**.
    
> [!IMPORTANT]
> Lorsque vous définissez l’intervalle entre deux détections d’échec et de secours, prenez garde à ne pas saisir un intervalle qui provoquera le basculement et le secours si le serveur d’inscriptions ne répond pas pendant un court moment. Le serveur d’inscriptions peut cesser de répondre pendant de courts moments en fonction du chargement du pool ou des serveurs. 
  

