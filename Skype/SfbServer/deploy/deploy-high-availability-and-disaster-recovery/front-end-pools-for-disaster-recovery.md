---
title: Déployer des pools frontux couplés pour la récupération d’urgence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Vous pouvez décider d’utiliser des pools frontux couplés pour fournir une protection contre la récupération d’urgence, mais cela n’est pas obligatoire.
ms.openlocfilehash: 9aec106905b2d8628e30461dce130f301aef1b25
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741330"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>Déployer des pools frontux couplés pour la récupération d’urgence dans Skype Entreprise Server
 
Vous pouvez décider d’utiliser des pools frontux couplés pour fournir une protection contre la récupération d’urgence, mais cela n’est pas obligatoire.
  
Vous pouvez facilement déployer la topologie de récupération d’urgence des pools frontux couplés à l’aide du Générateur de topologies. 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>Pour déployer une paire de pools de serveurs frontaux

1. Si les pools sont nouveaux et pas encore définis, utilisez le Générateur de topologie pour créer les pools.
    
2. Dans le Générateur de topologie, cliquez avec le bouton droit sur l’un des deux pools, puis cliquez **sur Modifier les propriétés.**
    
3. Cliquez sur **Résistance** dans le volet gauche, puis sélectionnez **Pool de stockage associé** dans le volet droit.
    
4. Dans la zone située en dessous de **Pool de stockage associé**, sélectionnez le pool que vous voulez jumeler à celui-ci. Seuls les pools existants qui ne sont pas déjà jumelés avec un autre pool peuvent être choisis.
    
5. Sélectionnez **Basculement et restauration automatiques pour Voice**, puis cliquez sur **OK**.
    
    Quand vous affichez les détails de ce pool, le pool associé apparaît dans le volet droit sous **Résistance**. 
    
6. Utilisez le Générateur de topologie pour publier la topologie.
    
7. Si les deux pools n’étaient pas déjà déployés, déployez-les maintenant pour terminer la configuration. Vous pouvez ignorer les dernières étapes de cette procédure.
    
    Toutefois, si les pools ont déjà été déployés avant de définir la relation couplée, vous devez effectuer les étapes finales suivantes.
    
8. Sur chaque serveur frontal des deux pools, exécutez la commande suivante :
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    Cela permet de configurer les autres services requis pour un fonctionnement correct du jumelage de sauvegarde.
    
9. Une fois que Bootstrapper a terminé l’installation des composants requis pour le jumelage de sauvegarde sur chaque serveur frontal des deux pools, n’oubliez pas de réapplinger toute mise à jour cumulative existante précédemment appliquée sur ces serveurs frontaux dans les deux pools, puis de continuer à l’étape suivante.

10. À partir d Skype Entreprise Server’invite de commandes Management Shell, exécutez la commande suivante : 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. Forcez la synchronisation des données utilisateur et de conférence des deux pools avec les cmdlets suivantes :
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    La synchronisation des données peut durer un certain temps. Vous pouvez utiliser les applets de commande suivantes pour vérifier l’état. Assurez-vous que l’état dans les deux sens est stable.
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> L’option De **failover et de failback** automatique pour Voice et les intervalles de temps associés dans le Générateur de topologie s’appliquent uniquement aux fonctionnalités de résistance vocale introduites dans Lync Server. La sélection de cette option ne signifie pas que le basculement du pool mentionné dans ce document est automatique. Le basculement et la restauration du pool requiert l’intervention manuelle d’un administrateur pour appeler respectivement les applets de commande de basculement et de restauration.
  
## <a name="see-also"></a>Voir aussi

[Récupération d’urgence du pool frontal dans Skype Entreprise Server](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
