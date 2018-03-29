---
title: Expander des paramètres de Registre
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: Résilience fournit une haute disponibilité et reprise après sinistre pour le pool de Registrar. En fournissant une Registre de sauvegarde en cas de défaillance de l’agent d’enregistrement principal, la sauvegarde Registre peut prendre en charge pour le Registre a échoué, ce qui permet aux utilisateurs de se connecter et communiquer. Les utilisateurs peuvent potentiellement bénéficier des fonctionnalités réduites, selon les systèmes ont échoué dans le Registre principal.
ms.openlocfilehash: 9d8460f0a883dfabc55153744ba4f3f886b34898
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="registrar-settings-expander"></a>Expander des paramètres de Registre
 
Résilience fournit une haute disponibilité et reprise après sinistre pour le pool de Registrar. En fournissant une Registre de sauvegarde en cas de défaillance de l’agent d’enregistrement principal, la sauvegarde Registre peut prendre en charge pour le Registre a échoué, ce qui permet aux utilisateurs de se connecter et communiquer. Les utilisateurs peuvent potentiellement bénéficier des fonctionnalités réduites, selon les systèmes ont échoué dans le Registre principal.
  
Dans la section de la **résilience** de la boîte de dialogue **Modifier les propriétés** de votre Survivable Branch Appliance ou le serveur Survivable Branch Server, vous pouvez modifier les paramètres suivants :
  
- **Pool de sauvegarde Registre et de service associé à l’utilisateur** Dans la liste déroulante, sélectionnez le pool frontal de Enterprise Edition ou Standard Edition serveur frontal qui est d’agir en tant que la sauvegarde du Registre pour le Survivable Branch Appliance ou le serveur Survivable Branch Server.
    
- **Activer le basculement et restauration automatique** Sélectionnez ce paramètre pour permettre la détection automatique d’un échec greffier et la détermination automatique qui le greffier principal est sauvegardée et prêt à reprendre le processus d’inscription.
    
- **Intervalle de détection de défaillance (s)** Tapez le nombre de secondes qui doit s’écouler avant qu’il est déterminé que le principal Registre a échoué. La valeur par défaut est de 120 secondes. Ce champ est obligatoire si vous sélectionnez **Activer le basculement et restauration automatique**.
    
- **Intervalle de détection de secours (s)** Tapez le nombre de secondes qui doit s’écouler avant qu’il est déterminé que le Registre principal est sauvegardé. La valeur par défaut est 240 secondes. Ce champ est obligatoire si vous sélectionnez **Activer le basculement et secours**.
    
> [!IMPORTANT]
> Lorsque vous définissez l’intervalle de détection de panne et l’intervalle de détection de secours, être faites attention à ne pas entrer un intervalle qui entraîne le basculement et de secours pour se produire si le Registre ne répond pas pendant une courte période de temps. Il est possible que le Registre principal peut ne pas répond pour courtes périodes de temps basée sur le chargement du pool ou des serveurs. 
  

