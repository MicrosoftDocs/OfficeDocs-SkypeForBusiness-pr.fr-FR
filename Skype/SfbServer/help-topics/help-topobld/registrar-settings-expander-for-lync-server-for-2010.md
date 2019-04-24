---
title: Expandeur des paramètres du serveur d’inscriptions avancé pour Lync Server 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Modifier les paramètres de résilience et de configurer les propriétés suivantes :'
ms.openlocfilehash: 03c85341d8267e199cebbe8b3e3764e32ccc7f5d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219168"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a>Expandeur des paramètres du serveur d’inscriptions avancé pour Lync Server 2010
 
Modifier les paramètres de **résilience** et de configurer les propriétés suivantes :
  
- Sélectionnez le **pool de serveurs d’inscriptions de sauvegarde associé** dans la liste.
    
    Facultativement, activez la case à cocher **basculement automatique et restauration pour la voix** .
    
    Configurer l' **intervalle de détection de panne voix (s)** et l' **intervalle de la restauration de voix (s)**. Par défaut, les intervalles sont 120 pour détecter une défaillance voix et 240 secondes pour la restauration automatique de la voix.
    
    > [!CAUTION]
    > Le nombre de secondes que vous définissez pour les intervalles de basculement et de restauration doit être testé avec soin pour vous assurer que la résilience fonctionne comme prévu. Définir l’intervalle à faible (autrement dit, moins de 120 secondes) ou le basculement et la restauration définir trop près peuvent entraîner le basculement réel et la restauration automatique ne fonctionne ne pas comme prévu. 
  
  **OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.
  
  **Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.
  
  **Aide** : permet d’afficher cet écran d’aide.
  

