---
title: Restauration d’un serveur principal Enterprise Edition en miroir-principal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12c4d942bc4f08c12e2ff63250d1b87807a50963
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a>Restauration d’un serveur principal Enterprise Edition en miroir dans Lync Server 2013-principal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-17_

Si vous disposez d’un serveur principal Enterprise Edition dans une configuration en miroir et que seule la base de données principale échoue, suivez les procédures décrites dans cette section. En cas d’échec de la base de données principale et du miroir, voir [restaurer un serveur principal Enterprise Edition dans Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Si seul le miroir échoue, reportez-vous à la rubrique [restauration d’un serveur principal Enterprise Edition en miroir dans Lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md). Si la base de données hébergeant le magasin central de gestion échoue, consultez [la rubrique restauration du serveur qui héberge le magasin central de gestion dans Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Si un serveur membre Enterprise Edition qui n’est pas le serveur principal échoue, consultez la rubrique [restauration d’un serveur membre Enterprise Edition dans Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Nous vous recommandons de prendre une copie de l’image du système avant de commencer la restauration. Vous pouvez utiliser cette image comme point de restauration, en cas de problème lors de la restauration. Vous pouvez utiliser la copie d’image après avoir installé le système d’exploitation et SQL Server, et restaurer ou réinscrire les certificats.

Dans cette rubrique, l’exemple de base de données principale aura un nom de domaine complet (FQDN) de BE1.contoso.com et la base de données miroir aura le nom de domaine complet (FQDN) de BE2.contoso.com.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a>Pour restaurer une base de données principale de serveur principal Enterprise Edition

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous à un serveur frontal.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Forcez toutes les bases de données configurées à basculer vers le miroir. Pour chaque type de base de données que vous avez configuré sur ce serveur, tapez l’applet de commande suivante :
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    Par exemple :
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > Si vous avez configuré votre base de données principale afin d’utiliser une mise en miroir synchronisée avec un témoin, le basculement est automatique.

    
    </div>

4.  Une fois le basculement terminé, effectuez les opérations suivantes :
    
      - Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.
    
      - Désactivez la mise en miroir sur le serveur principal : cliquez avec le bouton droit sur le pool sous **Pools frontaux Enterprise Edition** , puis sélectionnez **modifier les propriétés**. Sous l’onglet **général** , sous **associations**, désactivez la case à cocher **activer la mise en miroir du magasin SQL Server** . Procédez ainsi pour l’archivage et la surveillance, le cas échéant. Cliquez ensuite sur **OK**.
    
      - Cliquez avec le bouton droit sur le nœud Lync Server 2013, cliquez sur **topologie**, puis sur **publier**.
    
      - Sélectionnez le serveur principal qui fonctionne toujours (BE2.contoso.com) comme nouveau magasin SQL. Pour ce faire, cliquez avec le bouton droit sur le pool sous **Pools frontaux Enterprise Edition** et sélectionnez **modifier les propriétés**. Sous l’onglet **général** , sous **associations**, tapez le nom de domaine complet du serveur principal opérationnel dans le champ **magasin SQL Server** (dans notre exemple, BE2.contoso.com).
    
      - Cliquez avec le bouton droit sur le nœud Lync Server 2013, cliquez sur **topologie**, puis sur **publier**.
    
      - Redémarrez les services afin que chaque serveur puisse lire la nouvelle topologie. À partir d’un environnement Lync Server Management Shell, exécutez les applets de commande suivantes sur chaque serveur frontal qui appartient à ce pool :
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  Désinstaller la mise en miroir. À partir d’un environnement Lync Server Management Shell, exécutez l’applet de commande suivante :
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Par exemple :
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    Procédez ainsi pour tous les types de bases de données sur ce serveur.

6.  Créez un serveur nouveau ou propre qui a le même nom de domaine complet (dans cet exemple, DB1.contoso.com) comme ordinateur défaillant, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats. Ce serveur fonctionnera en tant que nouveau miroir.

7.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous au nouveau serveur.

8.  Installez SQL Server 2012 ou SQL Server 2008 R2, en conservant les mêmes noms d’instance qu’avant la défaillance.

9.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous à un serveur frontal.

10. Utilisez le générateur de topologie pour installer la base de données miroir. Effectuez les opérations suivantes :
    
      - Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.
    
      - Activer la mise en miroir sur le serveur principal. Pour ce faire, cliquez avec le bouton droit sur le pool sous **Pools frontaux Enterprise Edition** et sélectionnez **modifier les propriétés**. Sous l’onglet **général** , sous **associations**, activez la case à cocher **activer la mise en miroir du magasin SQL Server** . Effectuez également cette opération pour l’archivage et la surveillance, le cas échéant.
        
        Ensuite, dans le champ **magasin SQL Server de mise en miroir** , tapez le nom de domaine complet (FQDN) du nouveau serveur (n cet exemple, BE1.contoso.com). Cliquez ensuite sur **OK**.
    
      - Cliquez avec le bouton droit sur le nœud Lync Server 2013, cliquez sur **topologie**, puis sur **installer la base de données**.
    
      - Suivez l’Assistant d' **installation de base de données** . Sur la page **créer des bases de données** , sélectionnez les bases de données que vous souhaitez recréer.
    
      - Suivez l’Assistant jusqu’à ce que vous arriviez à l’invite **créer une base de données miroir**. Sélectionnez la base de données que vous souhaitez installer et terminez ce processus.

</div>

</div>

<span> </span>

</div>

</div>

</div>

