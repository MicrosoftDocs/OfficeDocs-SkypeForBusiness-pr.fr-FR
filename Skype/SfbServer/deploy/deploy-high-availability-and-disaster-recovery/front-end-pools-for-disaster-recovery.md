---
title: Déploiement de pools frontaux couplés pour une reprise après sinistre dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Vous pouvez décider d'utiliser des pools frontaux couplés pour assurer une protection en cas de récupération d’urgence, bien que ceci ne soit pas nécessaire.
ms.openlocfilehash: 4aa24c3a5150efbea87cd3837aca9216f047b11e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240034"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>Déploiement de pools frontaux couplés pour une reprise après sinistre dans Skype entreprise Server
 
Vous pouvez décider d'utiliser des pools frontaux couplés pour assurer une protection en cas de récupération d’urgence, bien que ceci ne soit pas nécessaire.
  
Vous pouvez facilement déployer la topologie de reprise après sinistre des pools front-end couplés à l’aide du générateur de topologie. 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>Pour déployer une paire de pools de serveurs frontaux

1. Si les pools sont nouveaux et ne sont pas encore définis, utilisez le générateur de topologie pour créer les pools.
    
2. Dans le générateur de topologie, cliquez avec le bouton droit sur l’un des deux pools, puis cliquez sur **modifier les propriétés**.
    
3. Cliquez sur **Résistance** dans le volet gauche, puis sélectionnez **Pool de stockage associé** dans le volet droit.
    
4. Dans la zone située en dessous de **Pool de stockage associé**, sélectionnez le pool que vous voulez jumeler à celui-ci. Seuls les pools existants qui ne sont pas déjà jumelés avec un autre pool peuvent être choisis.
    
5. Sélectionnez **Basculement et restauration automatiques pour Voice**, puis cliquez sur **OK **.
    
    Quand vous affichez les détails de ce pool, le pool associé s’affiche dans le volet droit sous **Résistance**.  
    
6. Utilisez le générateur de topologie pour publier la topologie.
    
7. Si les deux pools n’étaient pas déjà déployés, déployez-les maintenant pour terminer la configuration. Vous pouvez ignorer les deux dernières étapes de cette procédure.
    
    Cependant, si les pools étaient déjà déployés avant de définir la relation de paire, vous devez procéder aux deux dernières étapes suivantes.
    
8. Sur chaque serveur frontal des deux pools, exécutez la commande suivante :
    
   ```
   <system drive>\Program Files\Skype for Business Server 2015\Deployment\Bootstrapper.exe 
   ```

    Cela permet de configurer les autres services requis pour un fonctionnement correct du jumelage de sauvegarde.
    
9. À partir d’une invite de commandes de Skype entreprise Server Management Shell, exécutez la commande suivante: 
    
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
> L’option **reprise automatique et retour automatique pour les appels vocaux** et les intervalles de temps associés dans le générateur de topologie ne s’appliquent qu’aux fonctionnalités de résilience vocale introduites dans Lync Server. La sélection de cette option ne signifie pas que le basculement du pool mentionné dans ce document est automatique. Le basculement et la restauration du pool requiert l’intervention manuelle d’un administrateur pour appeler respectivement les applets de commande de basculement et de restauration.
  
## <a name="see-also"></a>Voir aussi

[Reprise après sinistre de la liste frontale dans Skype entreprise Server](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
