---
title: Déployer les pools frontaux couplés pour la récupération d’urgence dans Skype pour Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Vous pouvez décider d'utiliser des pools frontaux couplés pour assurer une protection en cas de récupération d’urgence, bien que ceci ne soit pas nécessaire.
ms.openlocfilehash: 028e0b4966a15b81b3e6e5627e63261207835f1f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225538"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>Déployer les pools frontaux couplés pour la récupération d’urgence dans Skype pour Business Server
 
Vous pouvez décider d'utiliser des pools frontaux couplés pour assurer une protection en cas de récupération d’urgence, bien que ceci ne soit pas nécessaire.
  
Vous pouvez facilement déployer la topologie de récupération d’urgence des paires pools frontaux à l’aide du Générateur de topologie. 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>Pour déployer une paire de pools de serveurs frontaux

1. Si les pools sont nouveaux et pas encore définis, utilisez le Générateur de topologie pour créer les pools.
    
2. Dans le Générateur de topologie, cliquez sur une des deux pools, puis cliquez sur **Modifier les propriétés**.
    
3. Cliquez sur **Résistance** dans le volet gauche, puis sélectionnez **Pool de stockage associé** dans le volet droit.
    
4. Dans la zone située en dessous de **Pool de stockage associé**, sélectionnez le pool que vous voulez jumeler à celui-ci. Seuls les pools existants qui ne sont pas déjà jumelés avec un autre pool peuvent être choisis.
    
5. Sélectionnez **Basculement et restauration automatiques pour Voice**, puis cliquez sur **OK **.
    
    Quand vous affichez les détails de ce pool, le pool associé s’affiche dans le volet droit sous **Résistance**.  
    
6. Utilisez le Générateur de topologie pour publier la topologie.
    
7. Si les deux pools n’étaient pas déjà déployés, déployez-les maintenant pour terminer la configuration. Vous pouvez ignorer les deux dernières étapes de cette procédure.
    
    Cependant, si les pools étaient déjà déployés avant de définir la relation de paire, vous devez procéder aux deux dernières étapes suivantes.
    
8. Sur chaque serveur frontal des deux pools, exécutez la commande suivante :
    
   ```
   <system drive>\Program Files\Skype for Business Server 2015\Deployment\Bootstrapper.exe 
   ```

    Cela permet de configurer les autres services requis pour un fonctionnement correct du jumelage de sauvegarde.
    
9. À partir d’un Skype pour l’invite de commandes Business Server Management Shell, exécutez la commande suivante : 
    
   ```
   Start-CsWindowsService -Name LYNCBACKUP
   ```

10. Forcez la synchronisation des données d’utilisateur et de conférence entre les deux pools, à l’aide des applets de commande suivantes :
    
    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    La synchronisation des données peut durer un certain temps. Vous pouvez utiliser les applets de commande suivantes pour vérifier l’état. Assurez-vous que l’état de synchronisation dans les deux sens est stable.
    
    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> L’option de **basculement automatique et restauration pour la voix** et les intervalles de temps associé dans le Générateur de topologie s’appliquent uniquement aux fonctionnalités de résilience vocale qui ont été introduites dans Lync Server. La sélection de cette option ne signifie pas que le basculement du pool mentionné dans ce document est automatique. Le basculement et la restauration du pool requiert l’intervention manuelle d’un administrateur pour appeler respectivement les applets de commande de basculement et de restauration.
  
## <a name="see-also"></a>Voir aussi

[La récupération d’urgence dans Skype fin pool de serveurs frontaux pour Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
