---
title: Correctifs ou mise à jour des serveurs frontaux Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: 'Résumé : Découvrez comment appliquer des mises à jour ou correctifs aux serveurs frontaux Skype pour Business Server.'
ms.openlocfilehash: 29191192b1dab16b79cc594cc0a7b3b68aaa906f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20972771"
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server"></a>Correctifs ou mise à jour des serveurs frontaux Skype pour Business Server
 
**Résumé :** Apprenez comment appliquer les correctifs et mises à niveau pour les serveurs frontaux Skype pour Business Server.
  
Lorsque vous appliquez le correctif les serveurs dans un pool frontal, procéder à un serveur à la fois. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Pour appliquer une mise à niveau aux serveurs frontaux d’un pool

1. Tapez l’applet de commande suivante :
    
  ```
  Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
  ```

     si cet applet indique qu’il manque des réplicas, exécutez l’applet de commande suivant pour récupérer le pool avant d’appliquer des correctifs.
    
  ```
  Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
  ```

2. Sur le premier serveur à « corriger », exécutez l’applet de commande suivant :
    
  ```
  Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
  ```

    Cette applet de commande déplace tous les services à d’autres serveurs frontaux du pool et déconnecte ce serveur.
    
3. Appliquez la mise à niveau ou le correctif à ce serveur.
    
4. Sur le serveur mis à niveau, exécutez l’applet de commande suivante :
    
  ```
  Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
  ```

    Le serveur reprend le service.
    
5. Répétez les étapes 2 à 4 pour chaque serveur à mettre à niveau.
    

