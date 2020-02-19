---
title: 'Lync Server 2013 : présentation des exigences en matière de pare-feu pour SQL Server'
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
ms.openlocfilehash: 38a6fba264edb7659ba9324ce663de9de38a575b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a>Présentation des exigences en matière de pare-feu pour SQL Server avec Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Pour un déploiement Standard Edition, les exceptions de pare-feu sont créées automatiquement lors de l’installation de Lync Server 2013. Toutefois, pour les déploiements Enterprise Edition, vous devez configurer manuellement les exceptions de pare-feu sur le serveur principal SQL Server. Le protocole TCP/IP autorise l’utilisation unique d’un port donné pour une adresse IP donnée. Cela signifie que dans le cas d’un serveur SQL Server, vous pouvez affecter le port TCP 1433 à l’instance de base de données par défaut. Pour toutes les autres instances, vous devez utiliser le Gestionnaire de configuration SQL Server pour affecter les ports uniques et inutilisés. Cette rubrique traite des sujets suivants :

  - Configuration requise pour une exception de pare-feu dans le cadre de l’utilisation de l’instance par défaut

  - Configuration requise pour une exception de pare-feu pour le service SQL Server Browser

  - Configuration requise pour les ports d’écoute statiques lors de l’utilisation d’instances nommées

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a>Configuration requise pour une exception de pare-feu dans le cadre de l’utilisation de l’instance par défaut

Si vous utilisez l’instance par défaut de SQL Server pour une base de données lors du déploiement de Lync Server 2013, les conditions requises suivantes pour la règle de pare-feu sont utilisées pour garantir la communication entre le pool frontal et l’instance par défaut de SQL Server.


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
<td><p>Entrant vers SQL Server</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a>Configuration requise pour une exception de pare-feu pour le service SQL Server Browser

Le service SQL Server Browser localise les instances de base de données et indique le port que l’instance (nommée ou par défaut) doit utiliser.


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
<td><p>DATAGRAMME</p></td>
<td><p>1434</p></td>
<td><p>Entrant</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a>Configuration requise pour les ports d’écoute statiques lors de l’utilisation d’instances nommées

Lors de l’utilisation d’instances nommées dans la configuration SQL Server pour les bases de données prenant en charge Lync Server 2013, vous configurez des ports statiques à l’aide du gestionnaire de configuration SQL Server. Une fois les ports statiques affectés à chaque instance nommée, vous devez créer des exceptions pour chaque port statique du pare-feu.


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
<td><p>Défini statiquement</p></td>
<td><p>Entrant</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a>Documentation SQL Server

La documentation Microsoft SQL Server 2012 fournit des instructions détaillées sur la configuration de l’accès au pare-feu pour les bases de données. Pour plus d’informations sur Microsoft SQL Server 2012, reportez-vous à la section « Configuration du pare [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031)-feu Windows pour autoriser l’accès à SQL Server » à l’adresse.

</div>

</div>

<span> </span>

</div>

</div>

</div>

