---
title: Gérer les serveurs frontux dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Résumé : Découvrez comment ajouter, supprimer, patcher ou mettre à jour des serveurs frontux dans Skype Entreprise Server.'
ms.openlocfilehash: daa56be66a09d0969c193021aa3b847fc5972413
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837526"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Gérer les serveurs frontux dans Skype Entreprise Server
 
Cet article explique comment ajouter ou supprimer des serveurs frontaux et comment appliquer des mises à niveau ou des correctifs aux serveurs frontaux.

  > [!NOTE]
> Skype Entreprise Server 2019 ne prend pas en charge les pools front Êdition Entreprise avec deux serveurs frontux et n’autorise pas la publication de la topologie dans ce scénario.

## <a name="add-or-remove-front-end-servers"></a>Ajouter ou supprimer des serveurs frontux
  
Lorsque vous ajoutez un serveur frontal à un pool, ou que vous supprimez un serveur frontal d’un pool, vous devez redémarrer le pool. 
  
> [!IMPORTANT]
> Lorsque vous ajoutez ou supprimez un serveur au pool dans votre topologie, puis publiez la topologie mise à jour, tous les serveurs du pool redémarrent en même temps. Pendant que les serveurs redémarrent le pool est hors connexion, ce qui interrompt le service pour vos utilisateurs connectés à ce pool. Pour éviter toute interruption de service pour les utilisateurs, prévoyez de publier la topologie avec le nouveau serveur dans le pool en de nouvelles heures d’ouverture. 
  
Vous pouvez utiliser la procédure suivante lors de l’ajout ou de la suppression d’un serveur frontal.
  
> [!NOTE]
> Si vous ajoutez de nouveaux serveurs au pool, mettez à jour vos nouveaux serveurs de pool pour qu’ils soient au même niveau de mise à jour cumulative que les serveurs existants dans le pool. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Pour ajouter ou supprimer des serveurs frontux

1. Si vous supprimez des serveurs frontaux, commencez par arrêter les nouvelles connexions à ces serveurs. Pour ce faire, vous pouvez utiliser l’applet de commande suivante :
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. Ouvrez le Générateur de topologie, puis ajoutez ou supprimez les serveurs nécessaires. 
    
3. Publiez la topologie.
    
    > [!IMPORTANT]
    > Lorsque vous ajoutez ou supprimez un serveur au pool dans votre topologie, puis publiez la topologie mise à jour, tous les serveurs du pool redémarrent en même temps. Pendant que les serveurs redémarrent le pool est hors connexion, ce qui interrompt le service pour vos utilisateurs connectés à ce pool. Pour éviter toute interruption de service pour les utilisateurs, prévoyez de publier la topologie avec le nouveau serveur dans le pool en de nouvelles heures d’ouverture. 
  
  > [!NOTE]
> En outre, lorsque vous ajoutez ou supprimez un serveur au pool, vous devez exécuter l’Assistant Déploiement de Skype Entreprise Server sur chaque ordinateur ajouté ou supprimé. Pour plus d’informations, voir [Install Skype Entreprise Server on servers in the topology.](../../deploy/install/install-skype-for-business-server.md)
  
4. Si vous avez modifié le nombre de serveurs dans votre pool frontal de l’une des manières suivantes, réinitialisez-le en tapant l’applet de la cmdlet suivante : Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 à n’importe quel
    
     - De 2 à 2
    
     - 3 à n’importe quel
    
     - De 3 à 3
    
5. Redémarrez le pool en tapant l’cmdlet suivante
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>Patch or update Front End Servers

Lorsque vous patchez les serveurs d’un pool frontal, vous le faites d’un serveur à la fois. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Pour appliquer une mise à niveau aux serveurs frontux d’un pool

1. Tapez l’cmdlet suivante :
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Si cette cmdlet affiche des réplicas manquants, exécutez la cmdlet suivante pour récupérer le pool avant d’appliquer des correctifs.
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. Sur le premier serveur à mettre à jour, exécutez l’cmdlet suivante :
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Cette applet de bord déplace tous les services vers d’autres serveurs frontaux du pool et met ce serveur hors connexion.
    
3. Appliquez la mise à niveau ou le correctif à ce serveur.
    
4. Sur le serveur mis à niveau, exécutez l’cmdlet suivante :
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    Le serveur est remis en service.
    
5. Répétez les étapes 2 à 4 pour chaque serveur qui doit être mis à niveau.
