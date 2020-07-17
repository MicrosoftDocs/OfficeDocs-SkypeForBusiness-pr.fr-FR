---
title: Gérer les serveurs frontaux dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Résumé : Découvrez comment ajouter, supprimer, corriger ou mettre à jour des serveurs frontaux dans Skype entreprise Server.'
ms.openlocfilehash: 3d2298711e707ed897b26939fd383dbedcfb3957
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098412"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Gérer les serveurs frontaux dans Skype entreprise Server
 
Cet article explique comment ajouter ou supprimer des serveurs frontaux et comment appliquer des mises à niveau ou des correctifs sur des serveurs frontaux.

  > [!NOTE]
> Skype entreprise Server 2019 ne prend pas en charge les pools frontaux Enterprise Edition avec deux serveurs frontaux et n’autorise pas la publication de la topologie dans ce scénario.

## <a name="add-or-remove-front-end-servers"></a>Ajouter ou supprimer des serveurs frontaux
  
Lorsque vous ajoutez un serveur frontal à un pool, ou que vous supprimez un serveur frontal d’un pool, vous devez redémarrer le pool. 
  
> [!IMPORTANT]
> Lorsque vous ajoutez ou supprimez un serveur dans le pool de votre topologie, puis que vous publiez la topologie mise à jour, tous les serveurs du pool sont redémarrés en même temps. Pendant que les serveurs redémarrent, le pool est hors connexion, ce qui interrompt le service pour les utilisateurs connectés à ce pool. Pour empêcher toute interruption de service pour les utilisateurs, envisagez de publier la topologie avec le nouveau serveur dans le pool en dehors des heures d’ouverture. 
  
Vous pouvez utiliser la procédure suivante lors de l’ajout ou de la suppression d’un serveur frontal.
  
> [!NOTE]
> Si vous ajoutez de nouveaux serveurs au pool, mettez à jour vos nouveaux serveurs de pool de sorte qu’ils se trouvent au même niveau de mise à jour cumulative que les serveurs existants dans le pool. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Pour ajouter ou supprimer des serveurs frontaux

1. Si vous supprimez des serveurs frontaux, commencez par arrêter les nouvelles connexions à ces serveurs. Pour ce faire, vous pouvez utiliser l’applet de commande suivante :
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. Ouvrez le Générateur de topologie, puis ajoutez ou supprimez les serveurs nécessaires. 
    
3. Publiez la topologie.
    
    > [!IMPORTANT]
    > Lorsque vous ajoutez ou supprimez un serveur dans le pool de votre topologie, puis que vous publiez la topologie mise à jour, tous les serveurs du pool sont redémarrés en même temps. Pendant que les serveurs redémarrent, le pool est hors connexion, ce qui interrompt le service pour les utilisateurs connectés à ce pool. Pour empêcher toute interruption de service pour les utilisateurs, envisagez de publier la topologie avec le nouveau serveur dans le pool en dehors des heures d’ouverture. 
  
  > [!NOTE]
> De plus, lorsque vous ajoutez ou supprimez un serveur dans le pool, vous devez exécuter l’Assistant Déploiement de Skype entreprise Server sur chaque ordinateur ajouté ou supprimé, pour plus d’informations, reportez-vous à la rubrique [installation de Skype entreprise Server sur des serveurs dans la topologie](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server) .
  
4. Si vous avez modifié le nombre de serveurs dans votre pool frontal de l’une des manières suivantes, réinitialisez le pool en tapant l’applet de commande suivante : Reset-CsPoolRegistrarState-ResetType FullReset-PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 à n’importe quel
    
     - Any à 2
    
     - 3 à n’importe quel
    
     - Any à 3
    
5. Redémarrez le pool en tapant l’applet de commande suivante :
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>Correctif ou mise à jour des serveurs frontaux

Lorsque vous appliquez un correctif aux serveurs d’un pool frontal, vous pouvez le faire sur un serveur à la fois. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Pour appliquer une mise à niveau sur les serveurs frontaux dans un pool

1. Tapez l’applet de commande suivante :
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Si cette applet de commande affiche des réplicas manquants, exécutez l’applet de commande suivante pour récupérer le pool avant d’appliquer les correctifs.
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. Sur le premier serveur auquel vous souhaitez appliquer un correctif, exécutez l’applet de commande suivante :
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Cette applet de commande déplace tous les services vers d’autres serveurs frontaux dans le pool et met ce serveur hors connexion.
    
3. Appliquez la mise à niveau ou le correctif à ce serveur.
    
4. Sur le serveur mis à niveau, exécutez l’applet de commande suivante :
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    Le serveur est renvoyé au service.
    
5. Répétez les étapes 2-4 pour chaque serveur qui doit être mis à niveau.
    
