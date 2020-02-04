---
title: 'Lync Server 2013 : Composants et topologies pour la surveillance'
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
ms.openlocfilehash: 76e857d0c80793f61b8e60686cc9455d27bb9f95
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a>Composants et topologies pour la surveillance dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-05_

Dans la mesure où les agents de collection de données unifiées sont automatiquement installés et activés sur chaque serveur frontal, vous n’avez pas besoin de configurer un serveur pour agir en tant que serveur de surveillance ; chaque serveur frontal fonctionne déjà en tant que serveur de surveillance. Toutefois, vous devrez installer et configurer une base de données pour qu’elle serve de magasin de données principal pour vos données de surveillance. Microsoft Lync Server 2013 peut utiliser les bases de données suivantes comme magasin principal de surveillance :

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

Notez que vous devez utiliser les éditions 64 bits de ces bases de données. les versions 32 bits de SQL Server ne peuvent pas être utilisées comme magasin principal pour le contrôle. De même, Lync Server 2013 ne prend pas en charge les éditions Express de SQL Server 2008 ou SQL Server 2012. Pour plus d’informations sur la configuration requise de base de données pour Lync Server 2013, voir la rubrique [prise en charge des logiciels de base de données dans Lync server 2013](lync-server-2013-database-software-support.md) dans le Guide de prise en charge de lync Server 2013.

N’oubliez pas que SQL Server doit être installé et configuré avant que vous ne procédiez au déploiement et à la configuration de la fonctionnalité de surveillance. Toutefois, il vous suffit de déployer SQL Server proprement dit ; vous n’avez pas besoin de configurer les bases de données de surveillance à l’avance. Au lieu de cela, celles-ci sont automatiquement créées lors de la publication de la topologie de votre serveur Lync.

Les données d’analyse peuvent utiliser la même instance SQL Server que d’autres types de données. Généralement, la base de données des enregistrements des détails des appels (LcsCdr) et la base de données de qualité de l’expérience (QoEMetrics) utilisent la même instance SQL ; par ailleurs, ces deux bases de données utilisent souvent la même instance SQL que la base de données d’archivage (LcsLog). La seule limitation réelle concernant les instances SQL Server est que chaque instance SQL Server est limitée à :

  - Une instance de la base de données du serveur principal Lync Server 2013. (En règle générale, il est déconseillé d’avoir colocalisé votre base de données de surveillance dans la même instance SQL, ou même sur le même ordinateur que la base de données principale. Même si cela est possible, vous courez le risque de la base de données de surveillance en utilisant l’espace disque requis par la base de données principale.)

  - une seule instance de la base de données LcsCdr ;

  - une seule instance de la base de données QoEMetrics ;

  - une seule instance de la base de données d’archivage.

En d’autres termes, vous ne pouvez pas avoir deux instances de la base de données LcsCdr dans la même instance de SQL Server. Si vous avez besoin d’instances multiples de la base de données LcsCdr, vous devrez configurer plusieurs instances de SQL Server.

<div>

## <a name="see-also"></a>Voir aussi


[Déploiement de la surveillance dans Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

