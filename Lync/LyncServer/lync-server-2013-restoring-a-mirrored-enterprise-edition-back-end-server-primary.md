---
title: Restauration d’un serveur back-end Enterprise Edition (principal)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbf0c8562ed4180fb14bf0bda74a03dd4ee8f746
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a>Restauration d’un serveur principal Enterprise Edition en miroir sur Lync Server 2013-principal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-17_

Si vous disposez d’un serveur principal Enterprise Edition dans une configuration en miroir et que seule la base de données principale ne fonctionne pas, suivez les procédures décrites dans cette section. En cas d’échec de la base de données principale et du miroir, voir [restaurer un serveur principal Enterprise Edition dans Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Si le miroir ne fonctionne que le miroir, voir [restaurer un serveur principal Enterprise Edition en miroir dans Lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md). En cas d’échec de la base de données qui héberge la Banque d’administration centrale, voir [restauration du serveur qui héberge le magasin de gestion central dans Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Si un serveur membre Enterprise Edition qui n’est pas le serveur principal ne fonctionne pas, consultez la rubrique [restauration d’un serveur membre Enterprise Edition dans Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Nous vous recommandons de prendre une copie d’image du système avant de commencer la restauration. Vous pouvez utiliser cette image comme point de restauration en cas de problème de restauration. Vous souhaiterez peut-être prendre la copie d’image après l’installation du système d’exploitation et de SQL Server, puis restaurez ou Réinscrivez les certificats.

Dans cette rubrique, l’exemple de base de données principale aura un nom de domaine complet (FQDN) de BE1.contoso.com et la base de données miroir aura un nom de domaine complet de BE2.contoso.com.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a>Pour restaurer la base de données principale du serveur principal de l’édition entreprise

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous à un serveur frontal.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Forcez la reprise de toutes les bases de données configurées sur le miroir. Pour chacun des types de bases de données que vous avez configurés sur ce serveur, tapez l’applet de commande suivante:
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    Par exemple :
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > Si vous avez configuré votre base de données principale pour utiliser la mise en miroir synchronisée avec un témoin, le basculement est automatique.

    
    </div>

4.  Après avoir terminé le basculement, effectuez les opérations suivantes:
    
      - Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.
    
      - Désactiver la mise en miroir sur le serveur principal: cliquez avec le bouton droit sur le pool sous **Pools front end Edition** et sélectionnez **modifier les propriétés**. Sous l’onglet **général** , sous **associations**, décochez la case **activer la mise en miroir du magasin SQL Server** . Procédez comme suit pour l’archivage et la surveillance selon les besoins. Cliquez ensuite sur **OK**.
    
      - Cliquez avec le bouton droit sur le nœud Lync Server 2013, cliquez sur **Topology**, puis sur **publier**.
    
      - Sélectionnez le serveur principal qui fonctionne toujours (BE2.contoso.com) comme nouveau SQL Store. Pour ce faire, cliquez avec le bouton droit sur le pool sous **Pools front end Edition** , puis sélectionnez **modifier les propriétés**. Dans l’onglet **général** , sous **associations**, tapez le nom de domaine complet du système principal de fonctionnement dans le champ **SQL Server Store** (dans notre exemple, BE2.contoso.com).
    
      - Cliquez avec le bouton droit sur le nœud Lync Server 2013, cliquez sur **Topology**, puis sur **publier**.
    
      - Redémarrez les services de sorte que chaque serveur puisse lire la nouvelle topologie. À partir d’un environnement Lync Server Management Shell, exécutez les applets de commande suivantes sur chaque serveur frontal qui appartient à ce pool:
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  Désinstaller la mise en miroir. Sur Lync Server Management Shell, exécutez l’applet de commande suivante:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Par exemple :
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    Procédez de la sorte pour tous les types de bases de données sur ce serveur.

6.  Créez un serveur propre ou nouveau portant le même nom de domaine complet (dans cet exemple, DB1.contoso.com) en tant qu’ordinateur en panne, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats. Ce serveur va fonctionner en tant que nouveau miroir.

7.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous au nouveau serveur.

8.  Installez SQL Server 2012 ou SQL Server 2008 R2, en conservent le nom de l’instance avant l’échec.

9.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous à un serveur frontal.

10. Utilisez le générateur de topologie pour installer une base de BDD en miroir. Procédez comme suit:
    
      - Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.
    
      - Activez la mise en miroir sur le serveur principal. Pour ce faire, cliquez avec le bouton droit de la liste sur le pool sous **Pools front end Enterprise Edition** , puis sélectionnez **modifier les propriétés**. Sous l’onglet **général** , sous **associations**, activez la case à cocher **activer la mise en miroir du magasin SQL Server** . Le cas échéant, effectuez cette opération pour l’archivage et le contrôle.
        
        Ensuite, dans le champ **Mirroring SQL Server Store** , tapez le nom de domaine complet (FQDN) du nouveau serveur (n cet exemple, BE1.contoso.com). Cliquez ensuite sur **OK**.
    
      - Cliquez avec le bouton droit sur le nœud Lync Server 2013, cliquez sur **Topology**, puis cliquez sur **installer la base de données**.
    
      - Suivez l’Assistant d' **installation de base de données** . Dans la page **créer des bases de données** , sélectionnez les bases de données que vous voulez recréer.
    
      - Suivez la procédure de l’Assistant jusqu’à ce que vous arriviez à l’invite, **créez une base de données miroir**. Sélectionnez la base de données que vous voulez installer, puis terminez la procédure.

</div>

</div>

<span> </span>

</div>

</div>

</div>

