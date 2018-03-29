---
title: Déployer des pools frontaux couplés pour la récupération d’urgence dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 9/1/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Vous pouvez décider d'utiliser des pools frontaux couplés pour assurer une protection en cas de récupération d’urgence, bien que ceci ne soit pas nécessaire.
ms.openlocfilehash: e13694c364908cfef70edafc1e7eb0484c5fe1bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server-2015"></a>Déployer des pools frontaux couplés pour la récupération d’urgence dans Skype Entreprise Server 2015
 
Vous pouvez décider d'utiliser des pools frontaux couplés pour assurer une protection en cas de récupération d’urgence, bien que ceci ne soit pas nécessaire.
  
Vous pouvez facilement déployer la topologie de reprise après sinistre de paires pools Front-End à l’aide du Générateur de topologies. 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>Pour déployer une paire de pools de serveurs frontaux

1. Si les pools sont nouvelles et non encore définie, utilisez le Générateur de topologies pour créer les pools.
    
2. Dans le Générateur de topologies, cliquez droit sur un de ces deux groupes et puis cliquez sur **Modifier les propriétés**.
    
3. Cliquez sur **Résistance** dans le volet gauche, puis sélectionnez **Pool de stockage associé** dans le volet droit.
    
4. Dans la zone située en dessous de **Pool de stockage associé**, sélectionnez le pool que vous voulez jumeler à celui-ci. Seuls les pools existants qui ne sont pas déjà jumelés avec un autre pool peuvent être choisis.
    
5. Sélectionnez **Basculement et restauration automatiques pour Voice**, puis cliquez sur **OK **.
    
    Quand vous affichez les détails de ce pool, le pool associé s’affiche dans le volet droit sous **Résistance**.  
    
6. Utilisez le Générateur de topologies pour publier la topologie.
    
7. Si les deux pools n’étaient pas déjà déployés, déployez-les maintenant pour terminer la configuration. Vous pouvez ignorer les deux dernières étapes de cette procédure.
    
    Cependant, si les pools étaient déjà déployés avant de définir la relation de paire, vous devez procéder aux deux dernières étapes suivantes.
    
8. Sur chaque serveur frontal des deux pools, exécutez la commande suivante :
    
   ```
   <system drive>\Program Files\Skype for Business Server 2015\Deployment\Bootstrapper.exe 
   ```

    Cela permet de configurer les autres services requis pour un fonctionnement correct du jumelage de sauvegarde.
    
9. À partir d’un Skype pour Business Server Management Shell invite de commandes, exécutez la commande suivante : 
    
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
> L’option de **basculement automatique sur incident et retour arrière pour la voix** et les intervalles de temps associée dans le Générateur de topologie s’appliquent uniquement aux fonctionnalités de résilience vocale qui ont été introduites dans Lync Server. La sélection de cette option ne signifie pas que le basculement du pool mentionné dans ce document est automatique. Le basculement et la restauration du pool requiert l’intervention manuelle d’un administrateur pour appeler respectivement les applets de commande de basculement et de restauration.
  
## <a name="see-also"></a>Voir aussi

#### 

[Avant la reprise de pool fin dans Skype pour Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)

