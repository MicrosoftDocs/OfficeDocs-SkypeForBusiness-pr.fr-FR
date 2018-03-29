---
title: Corriger ou mettre à jour des serveurs frontaux dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/4/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: 'Résumé : Apprenez à appliquer les correctifs et les mises à niveau de serveurs frontaux dans Skype pour Business Server.'
ms.openlocfilehash: 1f5ccd6531338d1e6b47dd8363b9386bcbeba0fc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server-2015"></a>Corriger ou mettre à jour des serveurs frontaux dans Skype Entreprise Server 2015
 
**Résumé :** apprendre à appliquer les correctifs et mises à niveau pour les serveurs frontaux dans Skype pour Business Server.
  
Lorsque vous appliquez le correctif les serveurs d’un pool frontal, vous le faire pour un seul serveur à la fois. 
  
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

    Cette applet de commande déplace tous les services à d’autres serveurs frontaux dans le pool et déconnecte ce serveur.
    
3. Appliquez la mise à niveau ou le correctif à ce serveur.
    
4. Sur le serveur mis à niveau, exécutez l’applet de commande suivante :
    
  ```
  Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
  ```

    Le serveur reprend le service.
    
5. Répétez les étapes 2 à 4 pour chaque serveur à mettre à niveau.
    

