---
title: Expander de paramètres de Registre pour Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Modifier les paramètres de résilience et de configurer les propriétés suivantes :'
ms.openlocfilehash: 88a2d75ff6f0225328a0f27743e0129950a5ca91
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a>Expander de paramètres de Registre pour Lync Server 2010
 
Modifier les paramètres de **résilience** et de configurer les propriétés suivantes :
  
- Sélectionnez le **pool de Registre de sauvegarde associé** dans la liste.
    
    Si vous le souhaitez, activez la case à cocher de **basculement automatique sur incident et retour arrière pour la voix** .
    
    Configurez l' **intervalle de détection de défaillance voix (s)** et l' **intervalle de restauration automatique de voix (s)**. Par défaut, les intervalles sont 120 secondes pour la détection des pannes vocales et 240 secondes pour la restauration automatique de voix.
    
    > [!CAUTION]
    > Le nombre de secondes que vous définissez pour les intervalles de basculement et de restauration doit être testé avec soin pour vous assurer que la résilience fonctionne comme prévu. Définition de l’intervalle à faible (autrement dit, moins de 120 secondes) ou le basculement et la restauration trop étroitement la valeur peuvent provoquer le basculement réelle et de la restauration automatique ne fonctionne ne pas comme prévu. 
  
 **OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.
  
 **Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.
  
 **Aide** : permet d’afficher cet écran d’aide.
  

