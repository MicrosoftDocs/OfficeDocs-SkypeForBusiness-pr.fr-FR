---
title: Expandeur des paramètres du serveur d’inscriptions avancé
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: La résilience fournit une haute disponibilité et une reprise après sinistre pour le pool d’inscriptions. En fournissant un bureau d’enregistrement de sauvegarde en cas d’échec du Bureau d’enregistrement principal, le Bureau d’enregistrement de sauvegarde peut prendre le contrôle du Bureau d’enregistrement en panne, ce qui permet aux utilisateurs de se connecter et de communiquer. Les utilisateurs peuvent bénéficier de fonctionnalités réduites, en fonction des systèmes ayant échoué avec le Bureau d’enregistrement principal.
ms.openlocfilehash: cc025bdd09026ac3c3b15d2408d0c99b3494a04f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688037"
---
# <a name="registrar-settings-expander"></a>Expandeur des paramètres du serveur d’inscriptions avancé
 
La résilience fournit une haute disponibilité et une reprise après sinistre pour le pool d’inscriptions. En fournissant un bureau d’enregistrement de sauvegarde en cas d’échec du Bureau d’enregistrement principal, le Bureau d’enregistrement de sauvegarde peut prendre le contrôle du Bureau d’enregistrement en panne, ce qui permet aux utilisateurs de se connecter et de communiquer. Les utilisateurs peuvent bénéficier de fonctionnalités réduites, en fonction des systèmes ayant échoué avec le Bureau d’enregistrement principal.
  
Dans la section **résilience** de la boîte de dialogue **modifier les propriétés** pour votre appareil de branche Survivable ou votre serveur de succursales survivant, vous pouvez modifier les paramètres suivants :
  
- **Service utilisateur associé et pool d’inscriptions de sauvegarde** Dans la liste déroulante, sélectionnez le serveur frontal Enterprise Edition ou le serveur frontal Standard Edition principal qui doit agir en tant que bureau d’enregistrement de sauvegarde de l’appareil de succursale survivant ou du serveur de succursales survivant.
    
- **Activer le basculement et la restauration automatique** Sélectionnez ce paramètre pour activer la détection automatique d’un bureau d’enregistrement en échec et la détermination automatique du registre principal du Bureau d’enregistrement et la reprise du processus d’inscription.
    
- **Intervalle de détection des échecs (s)** Tapez le nombre de secondes qui doivent s’écouler avant qu’il ne soit déterminé que le Bureau d’enregistrement principal a échoué. La valeur par défaut est 120 secondes. Ce champ est obligatoire si vous sélectionnez **activer le basculement et la restauration automatique**.
    
- **Intervalle de détection de secours (s)** Tapez le nombre de secondes qui doivent s’écouler avant qu’il soit déterminé que le Bureau d’enregistrement principal est sauvegardé. La valeur par défaut est 240 secondes. Ce champ est obligatoire si vous sélectionnez **activer le basculement et**la reprise.
    
> [!IMPORTANT]
> Lorsque vous définissez l’intervalle de détection d’échec et l’intervalle de détection de secours, veillez à ne pas entrer un intervalle qui entraînera le basculement et le basculement sur le point d’échec de réponse pour le Bureau d’enregistrement. Il est possible que le Bureau d’enregistrement principal ne réponde pas pendant des périodes courtes en fonction du chargement du ou des serveurs. 
  

