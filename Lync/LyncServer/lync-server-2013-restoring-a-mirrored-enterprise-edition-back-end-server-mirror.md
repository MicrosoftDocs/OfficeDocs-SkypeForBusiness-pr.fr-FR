---
title: Restauration d’un miroir de serveur principal Enterprise Edition en miroir
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5338dd867c5c6f3509f9d42107224cf7370a362c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>Restauration d’un serveur principal Enterprise Edition en miroir dans Lync Server 2013-Mirror

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-19_

Si vous disposez d’un serveur principal Enterprise Edition dans une configuration mise en miroir et que seul le miroir échoue, suivez les procédures décrites dans cette section. En cas d’échec de la base de données principale et du miroir, voir [restaurer un serveur principal Enterprise Edition dans Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Si seul le principal échoue, reportez-vous à la rubrique [restauration d’un serveur principal Enterprise Edition en miroir dans Lync server 2013-principal](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md). Si la base de données hébergeant le magasin central de gestion échoue, consultez [la rubrique restauration du serveur qui héberge le magasin central de gestion dans Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Si un serveur membre Enterprise Edition qui n’est pas le serveur principal échoue, consultez la rubrique [restauration d’un serveur membre Enterprise Edition dans Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Nous vous recommandons de prendre une copie de l’image du système avant de commencer la restauration. Vous pouvez utiliser cette image comme point de restauration, en cas de problème lors de la restauration. Vous pouvez utiliser la copie d’image après avoir installé le système d’exploitation et SQL Server, et restaurer ou réinscrire les certificats.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>Pour restaurer une base de données miroir de serveur principal Enterprise Edition

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous à un serveur frontal.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Désinstaller la mise en miroir. Tout d’abord, tapez l’applet de commande suivante :
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Par exemple :
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    Procédez ainsi pour tous les types de bases de données sur ce serveur.

4.  Créez un serveur vierge ou nouveau qui a le même nom de domaine complet (FQDN) (DB1.contoso.com) que l’ordinateur défaillant, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats. Ce serveur fonctionnera en tant que nouveau miroir.

5.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous au nouveau serveur.

6.  Installez SQL Server 2012 ou SQL Server 2008 R2, en conservant les mêmes noms d’instance qu’avant la défaillance.

7.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous à un serveur frontal.

8.  Utilisez le générateur de topologie pour installer la base de données miroir. Effectuez les opérations suivantes :
    
      - Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.
    
      - Cliquez avec le bouton droit sur le nœud Lync Server 2013, cliquez sur **topologie**, puis sur **installer la base de données**.
    
      - Suivez l’Assistant d' **installation de base de données** . Sur la page **créer des bases de données** , sélectionnez les bases de données que vous souhaitez recréer.
    
      - Suivez l’Assistant jusqu’à ce que vous soyez invité à **créer une base de données miroir** . Sélectionnez la base de données que vous souhaitez installer et terminez cette procédure.
        
        <div>
        

        > [!TIP]
        > Au lieu d’exécuter le générateur de topologie, vous pouvez utiliser l’applet de commande <STRONG>install-CsMirrorDatabase</STRONG> pour configurer la mise en miroir. Pour plus d’informations, voir la documentation Lync Server Management Shell.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

