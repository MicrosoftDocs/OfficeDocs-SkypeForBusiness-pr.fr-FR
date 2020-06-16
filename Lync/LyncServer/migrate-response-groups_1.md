---
title: Effectuer la migration de groupes Response Group
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de012d0886c51cd70d5003beb24053ff86af05b7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>Effectuer la migration de groupes Response Group

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Une fois les utilisateurs déplacés vers les pools Lync Server 2013, vous pouvez migrer vos groupes Response Group. La migration de groupes Response Group consiste à copier des groupes d’agents, des files d’attente, des flux de travail et des fichiers audio, ainsi qu’à transférer des objets contact Response Group depuis le déploiement hérité vers le pool Lync Server 2013. Une fois vos groupes de réponse hérités migrés, les appels vers les groupes Response Group sont gérés par l’application Response Group dans le pool Lync Server 2013. Les appels destinés aux groupes Response Group ne sont plus gérés par le pool hérité.

<div>


> [!NOTE]  
> Bien que vous puissiez migrer des groupes Response Group avant de déplacer tous les utilisateurs vers le pool Lync Server 2013, nous vous recommandons de déplacer tous les utilisateurs en premier. En particulier, les utilisateurs qui sont des agents Response Group ne disposent pas de toutes les fonctionnalités des nouvelles fonctionnalités tant qu’ils ne sont pas déplacés vers le pool Lync Server 2013.



</div>

Avant de migrer les groupes Response Group, vous devez avoir déployé un pool Lync Server 2013 qui inclut l’application Response Group. L’application Response Group est installée et activée par défaut lorsque vous déployez voix entreprise. Vous pouvez vous assurer que l’application Response Group est installée en exécutant la cmdlet **Get-CsService-ApplicationServer** .

<div>


> [!NOTE]  
> Vous pouvez créer des groupes de réponses Lync Server 2013 dans le pool Lync Server 2013 avant de migrer vos groupes de réponses hérités.



</div>

Pour migrer des groupes Response Group d’un pool hérité vers le Lync Server 2013, exécutez la cmdlet **Move-applet csrgsconfiguration** . Avant d’exécuter **Move-CsRgsConfiguration**, vous devez installer le package des interfaces de compatibilité descendante Windows Management Instrumentation (WMI). Installez cette application en exécutant OCSWMIBC.msi. Vous trouverez OCSWMIBC.msi sur le média d’installation, dans le dossier d’installation.

<div>


> [!IMPORTANT]  
> La cmdlet Response Group migration déplace la configuration Response Group pour l’ensemble du pool. Vous ne pouvez pas sélectionner de groupes, files d’attente ou flux de travail spécifiques à migrer.



</div>

Après avoir migré les groupes Response Group, vous devez mettre à jour l’URL utilisée par les agents formels pour se connecter à leurs groupes Response Group et les déconnecter, et utiliser le panneau de configuration Lync Server ou les cmdlets Lync Server Management Shell pour vérifier que tous les groupes d’agents, files d’attente et flux de travail ont été déplacés avec succès.

<div>


> [!WARNING]  
> Lors de la migration de groupes Response Group, les groupes Response Group Office Communications Server 2007 R2 ne sont pas supprimés. Ne supprimez pas les groupes Response Group Office Communications Server 2007 R2. Si vous supprimez un groupe Response Group Office Communications Server 2007 R2, les groupes Response Group dans Lync Server 2013 cessent de fonctionner.



</div>

<div>


> [!IMPORTANT]  
> Nous vous recommandons de ne pas supprimer les données de votre déploiement précédent tant que vous n’avez pas désaffecté le pool. En outre, nous vous recommandons fortement d’exporter les groupes Response Group immédiatement après la migration. Si un groupe Response Group Office Communications Server 2007 R2 est supprimé, vous pouvez restaurer vos groupes Response Group à partir de la sauvegarde pour obtenir les groupes de réponses Lync Server 2013 en cours d’exécution à nouveau.



</div>

Lorsque vous exécutez l’applet de commande **Move-applet csrgsconfiguration** , les groupes d’agents, les files d’attente, les flux de travail et les fichiers audio restent dans le pool hérité à des fins de restauration. Toutefois, si vous devez restaurer le pool hérité, vous devez exécuter la cmdlet **Move-CsApplicationEndpoint** pour déplacer les objets contact vers le pool hérité.

<div>


> [!IMPORTANT]  
> Nous vous recommandons de ne pas supprimer les données du groupe Response Group du pool hérité tant que vous n’avez pas désaffecté le pool.



</div>

La procédure qui suit pour la migration des configurations Response Group suppose que vous disposiez d’une relation un-à-un entre vos pools hérités et les pools Lync Server 2013. Si vous envisagez de consolider ou de fractionner les pools au cours de votre migration et de votre déploiement, vous devez planifier le pool hérité mappé vers le pool Lync Server 2013.

<div>

## <a name="to-migrate-response-group-configurations"></a>Pour migrer des configurations de groupe Response Group

1.  Localisez OCSWMIBC.msi dans le dossier d’installation du support d’installation, puis installez-le.

2.  Ouvrez une session sur l’ordinateur en utilisant un compte membre du groupe RTCUniversalServerAdmins ou disposant de droits et d’autorisations d’administrateur équivalents.

3.  Ouvrez Lync Server Management Shell.

4.  Sur la ligne de commande, tapez ce qui suit :
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Par exemple :
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  Si vous avez déployé l’onglet Response Group pour Microsoft Office Communicator 2007 R2 dans votre environnement Office Communications Server 2007 R2, supprimez l’onglet du fichier Office Communicator 2007 R2 tabs.xml.
    
    <div>
    

    > [!NOTE]  
    > Les agents formels ont utilisé l’onglet Response Group pour se connecter à leurs groupes de réponses avant de pouvoir recevoir des appels. Si vous avez déployé l’onglet Response Group, vous avez choisi l’emplacement du fichier Office Communicator 2007 R2 tabs.xml lors de son déploiement.

    
    </div>

6.  Fournissez aux utilisateurs l’URL mise à jour dont les agents ont besoin pour se connecter ou se déconnecter de leurs groupes de réponses.
    
    <div>
    

    > [!NOTE]  
    > L’URL est généralement https://webpoolFQDN/RgsClients/Tab.aspx , où webpoolfqdn représente est le nom de domaine complet (FQDN) du pool de sites Web associé au pool que vous venez de migrer vers Lync Server 2013.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Cette étape n’est pas nécessaire après la mise à niveau des utilisateurs vers Lync 2013 car l’URL est disponible à partir du menu <STRONG>Outils</STRONG> dans Lync.

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Pour vérifier la migration de groupes Response Group à l’aide du panneau de configuration Lync Server

1.  Ouvrez le Panneau de configuration Lync Server.

2.  Dans le volet de navigation gauche, cliquez sur **Services Response Group**.

3.  Sous l’onglet **flux de travail** , vérifiez que tous les flux de travail de votre environnement Office Communications Server 2007 R2 sont inclus dans la liste.

4.  Cliquez sur l’onglet **file d’attente** , puis vérifiez que toutes les files d’attente de votre environnement Office Communications Server 2007 R2 sont incluses dans la liste.

5.  Cliquez sur l’onglet **groupe** , puis vérifiez que tous les groupes d’agents de votre environnement Office Communications Server 2007 R2 sont inclus dans la liste.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>Pour vérifier la migration de groupes Response Group à l’aide d’applets de commande

1.  Ouvrez Lync Server Management Shell.
    
    Pour plus d’informations sur les applets de commande suivantes, exécutez :
    
        Get-Help <cmdlet name> -Detailed

2.  Sur la ligne de commande, tapez ce qui suit :
    
        Get-CsRgsAgentGroup

3.  Vérifiez que tous les groupes d’agents de votre environnement Office Communications Server 2007 R2 sont inclus dans la liste.

4.  Dans la ligne de commande, tapez le code suivant :
    
        Get-CsRgsQueue

5.  Vérifiez que toutes les files d’attente de votre environnement Office Communications Server 2007 R2 sont incluses dans la liste.

6.  Dans la ligne de commande, tapez le code suivant :
    
        Get-CsRgsWorkflow

7.  Vérifiez que tous les flux de travail de votre environnement Office Communications Server 2007 R2 sont inclus dans la liste.

</div>

</div>

<span> </span>

</div>

</div>

</div>

