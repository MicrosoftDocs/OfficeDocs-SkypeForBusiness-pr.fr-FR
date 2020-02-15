---
title: Prise en charge des logiciels de base de données Lync Server 2013
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
ms.openlocfilehash: da1ffd79ccfb652c0f853cb027577d477a14d33e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a>Prise en charge du logiciel de base de données dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-12-01_

Lync Server 2013 prend en charge les systèmes de gestion de bases de données suivants :

  - **Base de données principale d’un pool frontal, base de données d’archivage, base de données de surveillance, base de données de conversation persistante, et base de données de conformité de la conversation persistante**
    
      - Logiciel de base de données Microsoft SQL Server 2008 R2 Enterprise (édition 64 bits). L’exécution du Service Pack le plus récent est également recommandée.
    
      - Microsoft SQL Server 2008 R2 Standard (édition 64 bits). L’exécution du Service Pack le plus récent est également recommandée.
    
      - Microsoft SQL Server 2012 Enterprise (édition 64 bits). L’exécution du Service Pack le plus récent est également recommandée.
    
      - Microsoft SQL Server 2012 Standard (édition 64 bits). L’exécution du Service Pack le plus récent est également recommandée.

  - **Base de données du serveur Standard Edition et bases de données du serveur frontal**
    
      - Microsoft SQL Server 2012 Express (64-bit Edition). L’exécution du Service Pack le plus récent est également recommandée.
        
        Nous prenons en charge l’application de correctifs et la mise à niveau de Microsoft SQL Server sur les serveurs frontaux et les serveurs Standard Edition. Toutefois, lorsque vous effectuez une mise à niveau ou un correctif sur des serveurs frontaux, vous devez tenir compte des exigences en matière de quorum. Pour plus d’informations, reportez-vous [à mise à niveau ou mise à jour des serveurs frontaux dans Lync server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) et [topologies et composants pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2012 Express (64-bit Edition) est automatiquement installé par Lync Server 2013 sur chaque serveur Standard Edition et chaque serveur frontal.

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server 2013 ne prend pas en charge l’édition 32 bits de SQL Server. Vous devez utiliser l’édition 64 bits.</P>
> <LI>
> <P>SQL Server Web Edition et SQL Server Workgroup Edition ne sont pas pris en charge. Vous ne pouvez pas les utiliser avec Lync Server 2013.</P>
> <LI>
> <P>Lync Server 2013 prend en charge la mise en miroir native des bases de données.</P>
> <LI>
> <P>Pour utiliser le rôle serveur de surveillance, vous devez installer SQL Server Reporting Services.</P></LI></UL>



</div>

Dans un pool frontal, la base de données principale peut être un seul ordinateur SQL Server.

<div>


> [!IMPORTANT]  
> Si vous colocaliser des bases de données Lync Server avec d’autres bases de données, nous vous recommandons vivement d’évaluer tous les facteurs susceptibles d’affecter la disponibilité et les performances, et de s’assurer qu’en cas de défaillance d’un nœud, le reste du nœud peut gérer la charge. Pour vérifier les capacités de basculement, nous vous recommandons de tester tous les scénarios de basculement.



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>Utilisation de la mise en miroir SQL et du clustering SQL

Lync Server 2013 prend en charge l’utilisation de la mise en miroir SQL ou du clustering SQL pour chaque base de données Lync Server. Vous pouvez facilement configurer la mise en miroir SQL à l’aide de l’outil générateur de topologies dans Lync Server 2013. Pour le clustering SQL avec basculement, vous devez utiliser SQL Server pour le programme d’installation.

Lync Server 2013 prend en charge les topologies de mise en miroir SQL et de clustering SQL pour tous les déploiements, y compris les déploiements et les organisations déploiements qui ont été mis à niveau à partir de versions précédentes de Lync Server.

La prise en charge de la mise en cluster SQL est pour une configuration active/passive. Pour des raisons de performances, le nœud passif ne doit pas être partagé par une autre instance SQL.

La prise en charge suivante est incluse :

  - Clustering de basculement à deux nœuds pour les éléments suivants :
    
      - Microsoft SQL Server 2012 Standard (édition 64 bits). L’exécution du Service Pack le plus récent est également recommandée.
    
      - Microsoft SQL Server 2008 R2 Standard (édition 64 bits). L’exécution du Service Pack le plus récent est également recommandée.

  - Clustering de basculement à seize nœuds pour les éléments suivants :
    
      - Microsoft SQL Server 2012 Enterprise (édition 64 bits). L’exécution du Service Pack le plus récent est également recommandée.
    
      - Logiciel de base de données Microsoft SQL Server 2008 R2 Enterprise (édition 64 bits). L’exécution du Service Pack le plus récent est également recommandée.

Pour plus d’informations sur la mise en miroir SQL, reportez-vous à la rubrique [back end Server High Availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md). Pour plus d’informations sur le déploiement du clustering SQL, reportez-vous à [configurer le clustering SQL Server pour Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).

Pour plus d’informations et les meilleures pratiques pour le clustering de basculement dans <http://technet.microsoft.com/library/hh231721.aspx>SQL Server 2012, reportez-vous à la rubrique. Pour le clustering de basculement dans SQL Server <http://technet.microsoft.com/library/ms189134(v=sql.105).aspx>2008, reportez-vous à.

</div>

</div>

<span> </span>

</div>

</div>

</div>

