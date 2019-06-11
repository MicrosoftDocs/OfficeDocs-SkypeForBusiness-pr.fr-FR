---
title: Restauration d’un serveur principal en miroir d’Enterprise Edition-miroir
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 113d69d7aa39673686ff870c36a64bd1a8fe90f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>Restauration d’un serveur principal Enterprise Edition en miroir sur Lync Server 2013-Mirror

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-19_

Si vous disposez d’un serveur principal Enterprise Edition dans une configuration en miroir et que le miroir échoue uniquement, suivez les procédures décrites dans cette section. En cas d’échec de la base de données principale et du miroir, voir [restaurer un serveur principal Enterprise Edition dans Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). En cas d’échec du serveur principal, voir [restauration d’un serveur principal Enterprise Edition en miroir dans Lync Server 2013-principal](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md). En cas d’échec de la base de données qui héberge la Banque d’administration centrale, voir [restauration du serveur qui héberge le magasin de gestion central dans Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Si un serveur membre Enterprise Edition qui n’est pas le serveur principal ne fonctionne pas, consultez la rubrique [restauration d’un serveur membre Enterprise Edition dans Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Nous vous recommandons de prendre une copie d’image du système avant de commencer la restauration. Vous pouvez utiliser cette image comme point de restauration en cas de problème de restauration. Vous souhaiterez peut-être prendre la copie d’image après l’installation du système d’exploitation et de SQL Server, puis restaurez ou Réinscrivez les certificats.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>Pour restaurer la base de données miroir du serveur principal Enterprise Edition

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous à un serveur frontal.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Désinstaller la mise en miroir. Tout d’abord, tapez l’applet de commande suivante:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Par exemple :
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    Procédez de la sorte pour tous les types de bases de données sur ce serveur.

4.  Créez un serveur propre ou nouveau doté du même nom de domaine complet (DB1.contoso.com) que l’ordinateur en panne, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats. Ce serveur va fonctionner en tant que nouveau miroir.

5.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous au nouveau serveur.

6.  Installez SQL Server 2012 ou SQL Server 2008 R2, en conservent le nom de l’instance avant l’échec.

7.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous à un serveur frontal.

8.  Utilisez le générateur de topologie pour installer la base de données miroir. Procédez comme suit:
    
      - Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.
    
      - Cliquez avec le bouton droit sur le nœud Lync Server 2013, cliquez sur **Topology**, puis cliquez sur **installer la base de données**.
    
      - Suivez l’Assistant d' **installation de base de données** . Dans la page **créer des bases de données** , sélectionnez les bases de données que vous voulez recréer.
    
      - Suivez les instructions de l’Assistant jusqu’à ce qu’une invite de **création de base de données miroir** s’affiche. Sélectionnez la base de données que vous voulez installer et suivez ce processus.
        
        <div>
        

        > [!TIP]
        > Au lieu d’exécuter le générateur de topologie, vous pouvez utiliser l’applet de applet <STRONG>install-CsMirrorDatabase</STRONG> pour configurer la mise en miroir. Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

