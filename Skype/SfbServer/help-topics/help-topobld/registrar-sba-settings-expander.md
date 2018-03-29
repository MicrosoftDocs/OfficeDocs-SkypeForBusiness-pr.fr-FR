---
title: Registrar SBA Settings Expander
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'You edit the settings for Resiliency and configure the following properties:'
ms.openlocfilehash: cdc367d1f010749e72ea2144e757d673bd41ba4a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="registrar-sba-settings-expander"></a>Registrar SBA Settings Expander
 
You edit the settings for **Resiliency** and configure the following properties:
  
- Select **Associated User service and backup Registrar pool** from the list.
    
    Optionally, select the **Automatic failover and failback for Voice** check box.
    
    Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**. By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.
    
    > [!CAUTION]
    > The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected. Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected. 
  
 **OK** : permet d’accepter et de valider les modifications de la boîte de dialogue.
  
 **Annuler** : permet d’annuler les modifications et de fermer la boîte de dialogue.
  
 **Aide** : permet d’afficher cet écran d’aide.
  
## <a name="see-also"></a>Voir aussi

#### 

[Planning for Enterprise Voice Resiliency](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

