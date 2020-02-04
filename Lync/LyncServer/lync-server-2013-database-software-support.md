---
title: Prise en charge du logiciel de base de données Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4c39a51f742266c12f618f687c23c645977ffdb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a>Prise en charge du logiciel de base de données dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-12-01_

Lync Server 2013 prend en charge les systèmes de gestion de base de données suivants :

  - **Base de données principale d’un pool frontal, base de données d’archivage, base de données de surveillance, base de données de conversation persistante, et base de données de conformité de la conversation persistante**
    
      - Logiciel de base de données Microsoft SQL Server 2008 R2 Enterprise (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.
    
      - Microsoft SQL Server 2008 R2 Standard (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.
    
      - Microsoft SQL Server 2012 Enterprise (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.
    
      - Microsoft SQL Server 2012 Standard (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.

  - **Bases de données serveur de base de données et serveur frontal Standard Edition**
    
      - Microsoft SQL Server 2012 Express (édition 64 bits). Il est également recommandé d’exécuter le dernier Service Pack.
        
        Nous prenons en charge l’application de correctifs et la mise à niveau de Microsoft SQL Server sur des serveurs frontaux et des serveurs Standard Edition. Toutefois, lorsque vous effectuez une mise à niveau ou un correctif sur des serveurs frontaux, vous devez prendre en compte les exigences de quorum. Pour plus d’informations, voir [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) et [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2012 Express (64-bit Edition) est installé automatiquement par Lync Server 2013 sur chaque serveur Standard Edition et chaque serveur frontal serveur.

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server 2013 ne prend pas en charge l’édition 32 bits de SQL Server. Vous devez utiliser l’édition 64 bits.</P>
> <LI>
> <P>SQL Server Web Edition et SQL Server Workgroup Edition ne sont pas pris en charge. Vous ne pouvez pas les utiliser avec Lync Server 2013.</P>
> <LI>
> <P>Lync Server 2013 prend en charge la mise en miroir de base de données native.</P>
> <LI>
> <P>Pour utiliser le rôle serveur de surveillance, vous devez installer SQL Server Reporting Services.</P></LI></UL>



</div>

Dans un pool frontal, la base de données principale peut être un ordinateur SQL Server unique.

<div>


> [!IMPORTANT]  
> Si vous collocate les bases de données Lync Server avec d’autres bases de données, nous vous conseillons vivement d’évaluer tous les facteurs susceptibles d’affecter la disponibilité et les performances, et de veiller à ce que, en cas d’échec d’un nœud, le nœud restant puisse gérer le chargement. Pour vérifier les capacités de basculement, nous vous recommandons de tester tous les scénarios de basculement.



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>Utilisation de la mise en miroir SQL et du clustering SQL

Lync Server 2013 prend en charge l’utilisation de la mise en miroir SQL ou du regroupement SQL pour chaque base de données Lync Server. Vous pouvez facilement configurer la mise en miroir SQL à l’aide de l’outil générateur de topologie dans Lync Server 2013. Pour le clustering SQL avec basculement, vous devez utiliser SQL Server pour la configuration.

Lync Server 2013 prend en charge la mise en miroir SQL et la topologie de regroupement SQL pour tous les déploiements, y compris les déploiements Greenfield et les organisations ayant procédé à une mise à niveau à partir de versions précédentes de Lync Server.

La prise en charge du clustering SQL concerne les configurations active/passive. Pour des raisons de performance, le nœud passif ne doit pas être partagé par une autre instance SQL.

La prise en charge suivante est incluse :

  - Clustering de basculement à deux nœuds pour les configurations suivantes :
    
      - Microsoft SQL Server 2012 Standard (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.
    
      - Microsoft SQL Server 2008 R2 Standard (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.

  - Clustering de basculement à 16 nœuds maximum pour les configurations suivantes :
    
      - Microsoft SQL Server 2012 Enterprise (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.
    
      - Logiciel de base de données Microsoft SQL Server 2008 R2 Enterprise (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.

Pour plus d’informations sur la mise en miroir SQL, voir [disponibilité du serveur principal dans Lync Server 2013](lync-server-2013-back-end-server-high-availability.md). Pour plus d’informations sur le déploiement de la fonction de regroupement SQL, voir [configurer le regroupement SQL Server pour Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).

Pour plus d’informations et des meilleures pratiques pour la mise en cluster de basculement <http://technet.microsoft.com/en-us/library/hh231721.aspx>dans SQL Server 2012, voir. Pour la mise en cluster de basculement dans SQL <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>Server 2008, voir.

</div>

</div>

<span> </span>

</div>

</div>

</div>

