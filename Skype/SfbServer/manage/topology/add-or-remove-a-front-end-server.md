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
description: 'Résumé : Apprenez à ajouter ou supprimer des serveurs frontaux dans Skype pour Business Server.'
ms.openlocfilehash: aed52becf5d4cc97307f9788a81f8d6563d1d25d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-or-remove-a-front-end-server-in-skype-for-business-server-2015"></a>Ajouter ou supprimer un serveur frontal dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à ajouter ou supprimer des serveurs frontaux dans Skype pour Business Server.
  
Lorsque vous ajoutez un serveur frontal à un pool de, ou supprimez un serveur frontal d’un pool, vous devez ensuite redémarrer le pool. 
  
> [!IMPORTANT]
> Lorsque vous ajoutez ou que vous supprimez un serveur d’un pool dans votre topologie, puis publiez la topologie mise à jour, cela entraîne le redémarrage de tous les serveurs du pool au même moment. Pendant que les serveurs redémarrent, le pool est hors-ligne, ce qui interrompt le service pour les utilisateurs connectés à ce pool. Pour éviter toute interruption de service, prévoyez de publier la topologie avec le nouveau serveur dans le pool en dehors des heures de bureau. 
  
Vous pouvez utiliser la procédure suivante lors de l’ajout ou la suppression d’un serveur frontal.
  
> [!NOTE]
> Si vous ajoutez des serveurs au pool, mettez à jour vos nouveaux serveurs du pool pour qu’ils se trouvent au même niveau de mise à jour cumulée que les serveurs existants du pool. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Pour ajouter ou supprimer des serveurs frontaux

1. Si vous supprimez les serveurs frontaux, tout d’abord arrêter de nouvelles connexions aux serveurs. Pour ce faire, vous pouvez utiliser l’applet de commande suivante :
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. Ouvrir le Générateur de topologie et ajouter ou supprimer des serveurs nécessaires. 
    
3. Publiez la topologie.
    
    > [!IMPORTANT]
    > Lorsque vous ajoutez ou que vous supprimez un serveur d’un pool dans votre topologie, puis publiez la topologie mise à jour, cela entraîne le redémarrage de tous les serveurs du pool au même moment. Pendant que les serveurs redémarrent, le pool est hors-ligne, ce qui interrompt le service pour les utilisateurs connectés à ce pool. Pour éviter toute interruption de service, prévoyez de publier la topologie avec le nouveau serveur dans le pool en dehors des heures de bureau. 
  
4. Si vous avez modifié le nombre de serveurs dans votre pool frontal dans une des manières suivantes, puis réinitialisez le pool avec en tapant le cmdlet suivant : Reset-CsPoolRegistrarState - ResetType FullReset - PoolFqdn 
    
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


