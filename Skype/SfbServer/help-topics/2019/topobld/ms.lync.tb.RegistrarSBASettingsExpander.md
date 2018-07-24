---
title: Expanseur des paramètres du serveur d’inscriptions SBA
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
ROBOTS: NOINDEX, NOFOLLOW
description: 'Modifier les paramètres de résilience et de configurer les propriétés suivantes :'
ms.openlocfilehash: 83ad2a3bff1e305d3d8559c6244313ebf05f173f
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21057201"
---
# <a name="registrar-sba-settings-expander"></a>Expanseur des paramètres du serveur d’inscriptions SBA
 
Modifier les paramètres de **résilience** et de configurer les propriétés suivantes :
  
- Sélectionnez le **pool de serveurs d’inscriptions de sauvegarde et de service utilisateur associé** dans la liste.
    
    Facultativement, activez la case à cocher **basculement automatique et restauration pour la voix** .
    
    Configurer l' **intervalle de détection de panne voix (s)** et l' **intervalle de la restauration de voix (s)**. Par défaut, les intervalles sont 120 pour détecter une défaillance voix et 240 secondes pour la restauration automatique de la voix.
    
    > [!CAUTION]
    > Le nombre de secondes que vous définissez pour les intervalles de basculement et de restauration doit être testé avec soin pour vous assurer que la résilience fonctionne comme prévu. Définir l’intervalle à faible (autrement dit, moins de 120 secondes) ou le basculement et la restauration définir trop près peuvent entraîner le basculement réel et la restauration automatique ne fonctionne ne pas comme prévu. 
  
 **OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.
  
 **Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.
  
 **Aide** : permet d’afficher cet écran d’aide.
  
## <a name="see-also"></a>Voir aussi

[Planification de voix Entrerprise](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)