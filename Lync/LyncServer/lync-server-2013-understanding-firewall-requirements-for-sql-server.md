---
title: 'Lync Server 2013 : Description des exigences de pare-feu pour SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dba3296ee01f997857660d2a3f328f663d32cf99
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a>Description des exigences de pare-feu pour SQL Server avec Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Dans le cadre d’un déploiement Standard Edition, des exceptions de pare-feu sont créées automatiquement lors de la configuration de Lync Server 2013. Toutefois, pour les déploiements Enterprise Edition, vous devez configurer les exceptions de pare-feu manuellement sur le serveur principal SQL Server. Le protocole TCP/IP permet d’utiliser un port donné une seule fois pour une adresse IP donnée. En d’autres termes, pour le serveur SQL Server, vous pouvez affecter l’instance de base de données par défaut, le port TCP 1433. Pour tous les autres cas, vous devez utiliser le gestionnaire de configuration SQL Server pour attribuer des ports uniques et inutilisés. Cette rubrique aborde les thèmes suivants :

  - Configuration requise pour une exception de pare-feu lors de l’utilisation de l’instance par défaut

  - Configuration requise pour une exception de pare-feu pour le service SQL Server Browser

  - Configuration requise pour les ports d’écoute statique lors de l’utilisation d’instances nommées

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a>Configuration requise pour une exception de pare-feu lors de l’utilisation de l’instance par défaut

Si vous utilisez l’instance par défaut de SQL Server pour une base de données lors du déploiement de Lync Server 2013, les exigences de règle de pare-feu suivantes permettent de garantir la communication du pool frontal à l’instance SQL Server par défaut.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocole</th>
<th>Port</th>
<th>Direction</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>1433</p></td>
<td><p>Entrant sur SQL Server</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a>Configuration requise pour une exception de pare-feu pour le service SQL Server Browser

Le service de navigateur SQL Server détermine les instances de base de données et communique le port que l’instance (nommée ou par défaut) est configurée pour l’utilisation.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocole</th>
<th>Port</th>
<th>Direction</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>1434</p></td>
<td><p>Entrant</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a>Configuration requise pour les ports d’écoute statique lors de l’utilisation d’instances nommées

Lors de l’utilisation d’instances nommées dans la configuration SQL Server pour les bases de données prenant en charge Lync Server 2013, vous devez configurer les ports statiques à l’aide du gestionnaire de configuration SQL Server. Une fois que les ports statiques ont été attribués à chaque instance nommée, vous créez des exceptions pour chaque port statique dans le pare-feu.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocole</th>
<th>Port</th>
<th>Direction</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>Défini de manière statique</p></td>
<td><p>Entrant</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a>Documentation SQL Server

La documentation Microsoft SQL Server 2012 fournit des instructions détaillées sur la configuration de l’accès par le pare-feu aux bases de données. Pour plus d’informations sur Microsoft SQL Server 2012, voir « Configuration du pare-feu Windows pour autoriser l’accès [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)à SQL Server » à l’adresse.

</div>

</div>

<span> </span>

</div>

</div>

</div>

