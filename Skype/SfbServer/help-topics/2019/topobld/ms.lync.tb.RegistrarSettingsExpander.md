---
title: Expanseur des paramètres du serveur d’inscriptions
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: Résistance fournit une haute disponibilité et récupération d’urgence pour le pool de serveurs d’inscriptions. En fournissant une serveur d’inscriptions de sauvegarde en cas de défaillance d’inscriptions principale, la sauvegarde de serveurs d’inscriptions peut prendre en charge pour le serveur d’inscriptions ayant échoué, permettant aux utilisateurs de se connecter et communiquer. Les utilisateurs peuvent bénéficier potentiellement avec fonctionnalités réduites, selon lequel les systèmes ont échoué avec le serveur d’inscriptions principal.
ms.openlocfilehash: b1609bfa8fd3fe9fb58d02c2154a3427c5ba94c0
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19964687"
---
# <a name="registrar-settings-expander"></a>Expanseur des paramètres du serveur d’inscriptions
 
Résistance fournit une haute disponibilité et récupération d’urgence pour le pool de serveurs d’inscriptions. En fournissant une serveur d’inscriptions de sauvegarde en cas de défaillance d’inscriptions principale, la sauvegarde de serveurs d’inscriptions peut prendre en charge pour le serveur d’inscriptions ayant échoué, permettant aux utilisateurs de se connecter et communiquer. Les utilisateurs peuvent bénéficier potentiellement avec fonctionnalités réduites, selon lequel les systèmes ont échoué avec le serveur d’inscriptions principal.
  
Dans la section **résistance** de la boîte de dialogue **Modifier les propriétés** de votre Survivable Branch Appliance ou un serveur Survivable Branch Server, vous pouvez modifier les paramètres suivants :
  
- **Pool de serveurs d’inscriptions de sauvegarde et de service utilisateur associé** Dans la liste déroulante, sélectionnez le pool frontal Enterprise Edition ou Standard Edition serveur frontal qui doit agir en tant que la sauvegarde du serveur d’inscriptions pour le Survivable Branch Appliance ou serveur Survivable Branch Server.
    
- **Activer le basculement et la restauration automatique** Sélectionnez cette option pour permettre la détection automatique Échec d’un serveur d’inscriptions et le calcul automatique du serveur d’inscriptions principal est sauvegardée et prêt à reprendre le processus de serveur d’inscriptions.
    
- **Intervalle de détection de panne (s)** Tapez le nombre de secondes qui doivent s’écouler avant qu’il est déterminé que le serveur principal serveur d’inscriptions a échoué. La valeur par défaut est 120 secondes. Ce champ est obligatoire si vous sélectionnez **Activer le basculement et la restauration automatique**.
    
- **Intervalle de détection de secours (s)** Tapez le nombre de secondes qui doivent s’écouler avant qu’il est déterminé que le serveur d’inscriptions principal est sauvegardé. La valeur par défaut est 240 secondes. Ce champ est obligatoire si vous sélectionnez **Activer le basculement et secours**.
    
> [!IMPORTANT]
> Lorsque vous définissez l’intervalle de détection de panne et l’intervalle de détection de secours, être veiller à ne pas saisir un intervalle qui provoquera le basculement et de secours se produire si le serveur d’inscriptions ne répond pas pour un certain laps de temps. Il est possible que le serveur d’inscriptions principal peut ne pas répond de courtes périodes de temps, basées sur le chargement du pool ou serveurs. 
  

