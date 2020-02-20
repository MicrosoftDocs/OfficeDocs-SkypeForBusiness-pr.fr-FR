---
title: 'Lync Server 2013 : déploiement de pools frontaux couplés pour la récupération d’urgence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3aec22b4d2b4f3049ed2a74cd413fbce0d2eb167
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a>Déploiement de pools frontaux couplés pour la récupération d’urgence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Vous pouvez facilement déployer la topologie de récupération d’urgence des pools frontaux couplés à l’aide du générateur de topologie.

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a>Pour déployer une paire de pools de serveurs frontaux

1.  Si les pools ne sont pas encore définis, utilisez le générateur de topologies pour créer les pools.

2.  Dans le générateur de topologies, cliquez avec le bouton droit sur l’un des deux pools, puis cliquez sur **modifier les propriétés**.

3.  Cliquez sur **Résistance** dans le volet gauche, puis sélectionnez **Pool de stockage associé** dans le volet droit.

4.  Dans la zone située en dessous de **Pool de stockage associé**, sélectionnez le pool que vous voulez jumeler à celui-ci. Seuls les pools existants qui ne sont pas déjà jumelés avec un autre pool peuvent être choisis.
    
    ![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")  

5.  Sélectionnez **Basculement et restauration automatiques pour Voice**, puis cliquez sur **OK**.
    
    Quand vous affichez les détails de ce pool, le pool associé apparaît dans le volet droit sous **Résistance**.

6.  Utilisez le générateur de topologie pour publier la topologie.

7.  Si les deux pools n’étaient pas déjà déployés, déployez-les maintenant pour terminer la configuration. Vous pouvez ignorer les deux dernières étapes de cette procédure.
    
    Toutefois, si les pools étaient déjà déployés avant de définir la relation de paire, vous devez procéder aux deux dernières étapes suivantes.

8.  Sur chaque serveur frontal des deux pools, exécutez la commande suivante :
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    Cela permet de configurer les autres services requis pour un fonctionnement correct du jumelage de sauvegarde.

9.  À partir d’une invite de commandes Lync Server Management Shell, exécutez la commande suivante :
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. Forcez la synchronisation des données d’utilisateur et de conférence entre les deux pools, à l’aide des applets de commande suivantes :
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    La synchronisation des données peut durer un certain temps. Vous pouvez utiliser les applets de commande suivantes pour vérifier l’état. Assurez-vous que l’État dans les deux directions est stable.
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> L’option <STRONG>de basculement et de restauration automatiques pour Voice</STRONG> et les intervalles de temps associés dans le générateur de topologies s’appliquent uniquement aux fonctionnalités de résistance vocale introduites dans Lync Server 2010. La sélection de cette option ne signifie pas que le basculement du pool mentionné dans ce document est automatique. Le basculement et la restauration du pool requiert l’intervention manuelle d’un administrateur pour appeler respectivement les applets de commande de basculement et de restauration.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

