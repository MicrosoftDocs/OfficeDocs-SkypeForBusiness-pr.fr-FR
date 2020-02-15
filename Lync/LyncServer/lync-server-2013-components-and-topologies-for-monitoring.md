---
title: 'Lync Server 2013 : composants et topologies pour la surveillance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 065cab8b4db7ecbc764ab8a8c6168c88fe1afd50
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a>Composants et topologies pour la surveillance dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-05_

Étant donné que les agents de collecte de données unifiée sont automatiquement installés et activés sur chaque serveur frontal, il n’est pas nécessaire de configurer un serveur comme serveur de surveillance ; chaque serveur frontal fonctionne déjà comme un serveur de surveillance. Toutefois, vous devrez installer et configurer une base de données qui servira de magasin de données principal pour vos données de surveillance. Microsoft Lync Server 2013 peut utiliser les bases de données suivantes en tant que magasin principal pour la surveillance :

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

Notez que vous devez utiliser les éditions 64 bits de ces bases de données ; les versions 32 bits de SQL Server ne peuvent pas être utilisées en tant que magasin principal pour la surveillance. De même, Lync Server 2013 ne prend pas en charge les éditions Express de SQL Server 2008 ou SQL Server 2012. Pour plus d’informations sur les exigences en matière de bases de données pour Lync Server 2013, voir la rubrique relative aux [logiciels de base de données dans Lync server 2013](lync-server-2013-database-software-support.md) dans le Guide de prise en charge de lync Server 2013.

Gardez à l’esprit que SQL Server doit être installé et configuré avant de déployer et de configurer la surveillance. Toutefois, vous devez seulement déployer SQL Server lui-même ; vous n’avez pas besoin de configurer les bases de données d’analyse à l’avance. Au lieu de cela, ces bases de données sont automatiquement créées pour vous lorsque vous publiez votre topologie Lync Server.

Les données de surveillance peuvent partager une instance SQL Server avec d’autres types de données. En règle générale, la base de données d’enregistrement des détails des appels (LcsCdr) et la base de données de qualité de l’expérience (QoEMetrics) partagent la même instance SQL ; Il est également courant que les deux bases de données de surveillance se trouvent dans la même instance SQL que la base de données d’archivage (LcsLog). La seule exigence réelle concernant les instances SQL Server est que n’importe quelle instance de SQL Server est limitée à ce qui suit :

  - Une instance de la base de données principale Lync Server 2013. (En règle générale, il n’est pas recommandé que votre base de données de surveillance soit colocalisée dans la même instance SQL, ou même sur le même ordinateur que la base de données principale. Bien que techniquement possible, vous courez le risque de la base de données de surveillance à l’aide de l’espace disque nécessaire pour la base de données principale.)

  - Une instance de la base de données d’enregistrement des détails des appels.

  - Une instance de la base de données de qualité de l’expérience.

  - Une instance de la base de données d’archivage.

En d’autres termes, vous ne pouvez pas avoir deux instances de la base de données LcsCdr dans la même instance de SQL Server. Si vous avez besoin de plusieurs instances de la base de données LcsCdr, vous devez configurer plusieurs instances de SQL Server.

<div>

## <a name="see-also"></a>Voir aussi


[Déploiement de la surveillance dans Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

