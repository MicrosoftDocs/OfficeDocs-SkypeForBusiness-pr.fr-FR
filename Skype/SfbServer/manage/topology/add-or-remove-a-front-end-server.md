---
title: Ajouter ou supprimer un serveur frontal dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Résumé : Découvrez comment ajouter ou supprimer des serveurs frontaux dans Skype pour Business Server.'
ms.openlocfilehash: 80b0dab56d3adfb08856348b7ec749ef2e91079f
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569005"
---
# <a name="add-or-remove-a-front-end-server-in-skype-for-business-server-2015"></a>Ajouter ou supprimer un serveur frontal dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment ajouter ou supprimer des serveurs frontaux dans Skype pour Business Server.
  
Lorsque vous ajoutez un serveur frontal à un pool, ou supprimez un serveur frontal d’un pool, vous devez redémarrer le pool. 
  
> [!IMPORTANT]
> Lorsque vous ajoutez ou que vous supprimez un serveur d’un pool dans votre topologie, puis publiez la topologie mise à jour, cela entraîne le redémarrage de tous les serveurs du pool au même moment. Pendant que les serveurs redémarrent, le pool est hors-ligne, ce qui interrompt le service pour les utilisateurs connectés à ce pool. Pour éviter toute interruption de service, prévoyez de publier la topologie avec le nouveau serveur dans le pool en dehors des heures de bureau. 
  
Vous pouvez utiliser la procédure suivante lors de l’ajout ou suppression d’un serveur frontal.
  
> [!NOTE]
> Si vous ajoutez des serveurs au pool, mettez à jour vos nouveaux serveurs du pool pour qu’ils se trouvent au même niveau de mise à jour cumulée que les serveurs existants du pool. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Pour ajouter ou supprimer des serveurs frontaux

1. Si vous supprimez les serveurs frontaux, arrêtez tout d’abord nouvelles connexions à ces serveurs. Pour ce faire, vous pouvez utiliser l’applet de commande suivante :
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. Ouvrez le Générateur de topologie et comment ajouter ou supprimer les serveurs nécessaires. 
    
3. Publiez la topologie.
    
    > [!IMPORTANT]
    > Lorsque vous ajoutez ou que vous supprimez un serveur d’un pool dans votre topologie, puis publiez la topologie mise à jour, cela entraîne le redémarrage de tous les serveurs du pool au même moment. Pendant que les serveurs redémarrent, le pool est hors-ligne, ce qui interrompt le service pour les utilisateurs connectés à ce pool. Pour éviter toute interruption de service, prévoyez de publier la topologie avec le nouveau serveur dans le pool en dehors des heures de bureau. 
  
4. Si vous avez modifié le nombre de serveurs dans votre pool frontal dans une des manières suivantes, puis réinitialisez le pool avec en tapant l’applet de commande suivante : Reset-cspoolregistrarstate ne - ResetType FullReset - PoolFqdn 
    
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