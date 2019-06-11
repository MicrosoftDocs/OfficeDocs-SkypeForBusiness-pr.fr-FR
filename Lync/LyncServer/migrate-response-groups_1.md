---
title: Migrer des groupes Response Group
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bf7f0fa04f494eb49a0537011d5f9affcc68065
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>Migrer des groupes Response Group

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-19_

Après avoir déplacé vos utilisateurs vers les pools Lync Server 2013, vous pouvez migrer vos groupes de réponse. La migration de groupes de réponse inclut la copie de groupes d’agents, de files d’attente, de flux de travail et de fichiers audio, et le déplacement d’objets de contact de groupe de réponse du déploiement hérité vers le pool Lync Server 2013. Après la migration de vos groupes de réponse hérités, les appels vers les groupes de réponse sont gérés par l’application Response Group dans le pool Lync Server 2013. Les appels de Response Groups ne sont plus gérés par le pool hérité.

<div>


> [!NOTE]  
> Même si vous pouvez migrer des groupes de réponses avant de déplacer tous les utilisateurs vers le pool Lync Server 2013, nous vous recommandons de déplacer d’abord tous les utilisateurs. En particulier, les utilisateurs qui sont agents de groupe de réponse ne disposeront pas de toutes les fonctionnalités des nouvelles fonctionnalités tant qu’ils ne seront pas déplacés vers le pool Lync Server 2013.



</div>

Avant de migrer des groupes de réponse, vous devez avoir déployé un pool Lync Server 2013 qui inclut l’application Response Group. L’application Response Group est installée et activée par défaut lorsque vous déployez Enterprise Voice. Vous pouvez vous assurer que l’application Response Group est installée en exécutant l’applet de demande **Get-CsService-ApplicationServer** .

<div>


> [!NOTE]  
> Vous pouvez créer des groupes de réponse Lync Server 2013 dans le pool Lync Server 2013 avant de migrer vos groupes de réponse hérités.



</div>

Pour migrer des groupes de réponse d’un pool hérité vers Lync Server 2013, exécutez l’applet de **passe Move-CsRgsConfiguration** . Pour pouvoir exécuter **Move-CsRgsConfiguration**, vous devez d’abord installer le package d’interface de compatibilité descendante WMI (Windows Management Instrumentation). Installez cette application en exécutant OCSWMIBC. msi. Vous pouvez trouver OCSWMIBC. msi sur le support d’installation dans le dossier d’installation.

<div>


> [!IMPORTANT]  
> L’applet de passe de migration de groupe de réponse déplace la configuration de groupe de réponse pour le pool entier. Vous ne pouvez pas sélectionner des groupes, des files d’attente ou des flux de travail spécifiques à migrer.



</div>

Une fois les groupes de réponse migrés, vous devez mettre à jour l’URL utilisée par les agents formels pour se connecter et se déconnecter de leurs groupes de réponse, et utiliser le panneau de configuration de Lync Server ou les applets de commande Lync Server Management Shell pour vérifier le déplacement de tous les groupes d’agents, files d’attente et flux de travail. réussi.

<div>


> [!WARNING]  
> Lors de la migration de Response Groups, les groupes de réponse Office Communications Server 2007 R2 ne sont pas supprimés. Ne supprimez pas les groupes de réponse Office Communications Server 2007 R2. Si vous supprimez un groupe de réponses Office Communications Server 2007 R2, les groupes de réponse de Lync Server 2013 cessent de fonctionner.



</div>

<div>


> [!IMPORTANT]  
> Nous vous recommandons de ne pas supprimer les données de votre déploiement antérieur tant que vous n’avez pas désactivé le pool. Par ailleurs, nous vous conseillons vivement d’exporter des groupes de réponse immédiatement après la migration. Si un groupe de réponse Office Communications Server 2007 R2 est supprimé, vous pouvez restaurer vos groupes de réponse à partir de la sauvegarde pour obtenir les groupes de réponse Lync Server 2013 en cours d’exécution.



</div>

Lorsque vous exécutez l’applet de cmdlet **Move-CsRgsConfiguration** , les groupes d’agents, les files d’attente, les flux de travail et les fichiers audio restent dans le pool hérité à des fins de restauration. Toutefois, si vous avez besoin de revenir au pool hérité, vous devez exécuter l’applet de passe **Move-CsApplicationEndpoint** pour replacer les objets de contact sur le pool hérité.

<div>


> [!IMPORTANT]  
> Nous vous recommandons de ne pas supprimer les données du groupe de réponses du pool hérité tant que vous n’avez pas désactivé le pool.



</div>

La procédure suivante pour la migration de configurations de groupe de réponse suppose que vous disposez d’une relation un-à-un entre vos pools hérités et les pools Lync Server 2013. Si vous envisagez de consolider ou de fractionner des listes lors de la migration et du déploiement, vous devez planifier les mappages de pool hérité par le pool Lync Server 2013.

<div>

## <a name="to-migrate-response-group-configurations"></a>Pour migrer les configurations de Response Group

1.  Recherchez OCSWMIBC. msi dans le dossier de configuration du support d’installation, puis installez-le.

2.  Ouvrez une session sur l’ordinateur avec un compte membre du groupe RTCUniversalServerAdmins ou disposant d’autorisations et de droits d’administrateur équivalents.

3.  Ouvrez Lync Server Management Shell.

4.  Dans la ligne de commande, tapez ce qui suit :
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Par exemple :
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  Si vous avez déployé l’onglet Response Group pour Microsoft Office Communicator 2007 R2 dans votre environnement Office Communications Server 2007 R2, supprimez l’onglet du fichier Office Communicator 2007 R2 Tabs. Xml.
    
    <div>
    

    > [!NOTE]  
    > Les agents officiels ont utilisé l’onglet Response Group pour se connecter à leurs groupes de réponse avant de recevoir des appels. Si vous avez déployé l’onglet Response Group, vous avez choisi l’emplacement du fichier Office Communicator 2007 R2. xml lors de son déploiement.

    
    </div>

6.  Fournir aux utilisateurs l’URL mise à jour indiquant que les agents doivent se connecter et se déconnecter de leurs groupes de réponse.
    
    <div>
    

    > [!NOTE]  
    > En général https://webpoolFQDN/RgsClients/Tab.aspx, l’URL est le nom de domaine complet (FQDN) du pool Web associé au pool que vous venez de migrer vers Lync Server 2013.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Cette étape n’est pas nécessaire lorsque les utilisateurs effectuent la mise à niveau vers Lync 2013, car l’URL est disponible dans le menu <STRONG>Outils</STRONG> de Lync.

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Pour vérifier la migration du groupe de réponse à l’aide du panneau de configuration de Lync Server

1.  Ouvrez le panneau de configuration de Lync Server.

2.  Dans le volet de navigation de gauche, cliquez sur **Response Groups**.

3.  Dans l’onglet **flux de travail** , vérifiez que tous les flux de travail de votre environnement Office Communications Server 2007 R2 sont inclus dans la liste.

4.  Cliquez sur l’onglet **file d’attente** pour vérifier que toutes les files d’attente de votre environnement Office Communications Server 2007 R2 sont incluses dans la liste.

5.  Cliquez sur l’onglet **groupe** , puis vérifiez que tous les groupes d’agents de votre environnement Office Communications Server 2007 R2 sont inclus dans la liste.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>Pour vérifier la migration de groupe de réponse à l’aide de cmdlets

1.  Ouvrez Lync Server Management Shell.
    
    Pour plus d’informations sur les applets de commande suivantes, exécutez:
    
        Get-Help <cmdlet name> -Detailed

2.  Dans la ligne de commande, tapez ce qui suit :
    
        Get-CsRgsAgentGroup

3.  Vérifiez que tous les groupes d’agents de votre environnement Office Communications Server 2007 R2 sont inclus dans la liste.

4.  Dans la ligne de commande, tapez ce qui suit :
    
        Get-CsRgsQueue

5.  Vérifiez que toutes les files d’attente de votre environnement Office Communications Server 2007 R2 sont incluses dans la liste.

6.  Dans la ligne de commande, tapez ce qui suit :
    
        Get-CsRgsWorkflow

7.  Vérifiez que tous les flux de travail de votre environnement Office Communications Server 2007 R2 sont inclus dans la liste.

</div>

</div>

<span> </span>

</div>

</div>

</div>

