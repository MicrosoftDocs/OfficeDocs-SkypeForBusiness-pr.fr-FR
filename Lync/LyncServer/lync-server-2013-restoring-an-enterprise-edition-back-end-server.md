---
title: 'Lync Server 2013 : restauration d’un serveur principal Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bd57054505b3200f63bed8a60c47b400f7e7642
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a>Restauration d’un serveur principal Enterprise Edition dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-18_

Suivez la procédure décrite dans cette rubrique dans les deux cas suivants :

  - Les bases de données principales et en miroir d’un serveur principal Enterprise Edition en miroir échouent.

  - Le serveur principal d’une édition d’entreprise qui n’est pas en miroir ne fonctionne pas.

Si vous disposez d’une version back-end Enterprise Edition en miroir et que seul le miroir ou la base de données principale échoue, consultez [la rubrique restauration d’un serveur principal Enterprise Edition dans Lync server 2013-principales](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) pour la restauration de la base de données principale et la [restauration d’un serveur principal Enterprise Edition en miroir de Lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) pour restaurer le miroir.

Si la Banque centrale de gestion échoue, voir [restauration du serveur qui héberge le magasin de gestion central dans Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Si un serveur membre Enterprise Edition qui n’est pas le serveur principal ne fonctionne pas, consultez la rubrique [restauration d’un serveur membre Enterprise Edition dans Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

<div>


> [!TIP]  
> Nous vous recommandons de prendre une copie d’image du système avant de commencer la restauration. Vous pouvez utiliser cette image comme point de restauration en cas de problème de restauration. Vous souhaiterez peut-être prendre la copie d’image après l’installation du système d’exploitation et de SQL Server, puis restaurez ou Réinscrivez les certificats.



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a>Pour restaurer un serveur principal Enterprise Edition

1.  Commencez par un serveur propre ou nouveau qui porte le même nom de domaine complet (FQDN) que l’ordinateur en panne, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats.
    
    <div>
    

    > [!NOTE]  
    > Pour effectuer cette étape, suivez les procédures de déploiement du serveur de votre organisation.

    
    </div>

2.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous au serveur que vous restaurez.

3.  Installez SQL Server 2012 ou SQL Server 2008 R2, en conservent le nom de l’instance avant l’échec.
    
    <div>
    

    > [!NOTE]  
    > Selon votre déploiement, le serveur principal peut inclure plusieurs bases de données colocalisées ou distinctes. Suivez la même procédure pour installer SQL Server que vous avez utilisé à l’origine pour déployer le serveur, y compris les autorisations et les connexions SQL Server.

    
    </div>

4.  Après avoir installé SQL Server, procédez comme suit :
    
    1.  Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.
    
    2.  Cliquez sur **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.
    
    3.  Sélectionnez la topologie, puis cliquez sur **Enregistrer**. Cliquez sur **Oui** pour confirmer votre sélection.
    
    4.  Cliquez avec le bouton droit sur le nœud **Lync Server 2013** , puis cliquez sur **publier la topologie**.
    
    5.  Suivez la procédure **publier l’Assistant topologie** . Dans la page **créer des bases de données** , sélectionnez les bases de données que vous voulez recréer.
        
        <div>
        

        > [!NOTE]  
        > Seules les bases de données autonomes sont affichées dans la page <STRONG>créer des bases de données</STRONG> .

        
        </div>
    
    6.  Si vous restaurez une fin en miroir, continuez à suivre le reste de l’Assistant jusqu’à ce que l’invite **créer une base de données miroir** s’affiche. Sélectionnez la base de données que vous voulez installer, puis terminez la procédure.
    
    7.  Suivez les autres instructions de l’Assistant, puis cliquez sur **Terminer**.
    
    <div>
    

    > [!TIP]  
    > Au lieu d’exécuter le générateur de topologie, vous pouvez utiliser l’applet de applet <STRONG>install-CsDatabase</STRONG> pour créer une base de données et l’applet de la cmdlet <STRONG>install-CsMirrorDatabase</STRONG> pour configurer la mise en miroir. Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell.

    
    </div>

5.  Restaurez les données utilisateur en procédant comme suit :
    
    1.  Copiez ExportedUserData. zip de\\ $Backup dans un répertoire local.
    
    2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.
    
    3.  Avant de restaurer les données utilisateur, vous devez arrêter les services Lync. Pour ce faire, tapez :
        
            Stop-CsWindowsService
    
    4.  Pour restaurer les données utilisateur, à partir de la ligne de commande, tapez :
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Par exemple :
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  Redémarrez les services Lync en entrant :
        
            Start-CsWindowsService

6.  Si vous avez déployé Response Group sur ce pool, restaurez les données de configuration du groupe de réponse. Pour plus d’informations, consultez la rubrique [restauration des paramètres du groupe de réponses dans Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

7.  Si vous restaurez un serveur principal qui inclut l’archivage ou la surveillance de bases de données, restaurez les données d’archivage ou de contrôle à l’aide d’un outil SQL Server, tel que SQL Server Management Studio. Pour plus d’informations, reportez-vous à la rubrique [restauration de données d’analyse ou d’archivage dans Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

