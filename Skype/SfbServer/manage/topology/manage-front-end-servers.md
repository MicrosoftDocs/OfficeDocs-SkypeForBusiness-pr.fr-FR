---
title: Gérer les serveurs frontaux dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Résumé: Découvrez comment ajouter, supprimer ou mettre à jour les serveurs frontaux dans Skype entreprise Server.'
ms.openlocfilehash: 13af9198dfb83d14ad1d86885419fc9add29e07d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275156"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Gérer les serveurs frontaux dans Skype entreprise Server
 
Cet article explique comment ajouter ou supprimer des serveurs frontaux et comment appliquer des mises à niveau ou des correctifs à des serveurs frontaux.

## <a name="add-or-remove-front-end-servers"></a>Ajouter ou supprimer des serveurs frontaux
  
Lorsque vous ajoutez un serveur frontal à un pool, ou supprimez un serveur frontal d’un pool, vous devez redémarrer le pool. 
  
> [!IMPORTANT]
> Lorsque vous ajoutez ou que vous supprimez un serveur d’un pool dans votre topologie, puis publiez la topologie mise à jour, cela entraîne le redémarrage de tous les serveurs du pool au même moment. Pendant que les serveurs redémarrent, le pool est hors-ligne, ce qui interrompt le service pour les utilisateurs connectés à ce pool. Pour éviter toute interruption de service, prévoyez de publier la topologie avec le nouveau serveur dans le pool en dehors des heures de bureau. 
  
Vous pouvez utiliser la procédure suivante lors de l’ajout ou de la suppression d’un serveur frontal.
  
> [!NOTE]
> Si vous ajoutez des serveurs au pool, mettez à jour vos nouveaux serveurs du pool pour qu’ils se trouvent au même niveau de mise à jour cumulée que les serveurs existants du pool. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Pour ajouter ou supprimer des serveurs frontaux

1. Si vous supprimez un serveur frontal, vous devez d’abord arrêter de nouvelles connexions sur ces serveurs. Pour ce faire, vous pouvez utiliser l’applet de commande suivante :
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. Ouvrez le générateur de topologie et ajoutez ou supprimez les serveurs nécessaires. 
    
3. Publiez la topologie.
    
    > [!IMPORTANT]
    > Lorsque vous ajoutez ou que vous supprimez un serveur d’un pool dans votre topologie, puis publiez la topologie mise à jour, cela entraîne le redémarrage de tous les serveurs du pool au même moment. Pendant que les serveurs redémarrent, le pool est hors-ligne, ce qui interrompt le service pour les utilisateurs connectés à ce pool. Pour éviter toute interruption de service, prévoyez de publier la topologie avec le nouveau serveur dans le pool en dehors des heures de bureau. 
  
  > [!NOTE]
> Par ailleurs, lorsque vous ajoutez ou supprimez un serveur au pool, vous devez exécuter l’Assistant Déploiement de Skype entreprise Server sur chaque ordinateur ajouté ou supprimé pour plus d’informations, reportez-vous à la rubrique [installation de Skype entreprise Server sur les serveurs dans la topologie](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server) .
  
4. Si vous avez modifié le nombre de serveurs dans votre pool frontal de l’une des manières suivantes, reconfigurez le pool avec en tapant l’applet de commande suivante: Reset-CsPoolRegistrarState-ResetType FullReset-PoolFqdn 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 à quelconque
    
     - Quelconque à 2
    
     - 3 à quelconque
    
     - Quelconque à 3
    
5. Redémarrez le pool en tapant l’applet de commande suivante
    
   ```
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>Corriger ou mettre à jour des serveurs frontaux

Lorsque vous mettez à jour les serveurs dans une liste frontale, vous devez utiliser un serveur à la fois. 
  
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

    Cette applet de connexion déplace tous les services vers d’autres serveurs frontaux de la liste, et met ce serveur hors connexion.
    
3. Appliquez la mise à niveau ou le correctif à ce serveur.
    
4. Sur le serveur mis à niveau, exécutez l’applet de commande suivante :
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    Le serveur reprend le service.
    
5. Répétez les étapes 2 à 4 pour chaque serveur à mettre à niveau.
    
