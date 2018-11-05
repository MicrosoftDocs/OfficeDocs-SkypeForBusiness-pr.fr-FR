---
title: 'Lync Server 2013 : Description des exigences de pare-feu pour SQL Server'
TOCTitle: Description des exigences de pare-feu pour SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425818(v=OCS.15)
ms:contentKeyID: 49296784
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Description des exigences de pare-feu pour SQL Server avec Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Dans un déploiement Standard Edition, les exceptions du pare-feu sont automatiquement créées pendant l’installation de Lync Server 2013. En revanche, dans les déploiements Enterprise Edition, vous devez configurer les exceptions de pare-feu manuellement sur le serveur SQL Server principal. Le protocole TCP/IP autorise l’utilisation unique d’un port donné pour une adresse IP donnée. Cela signifie que dans le cas d’un serveur SQL Server, vous pouvez affecter le port TCP 1433 à l’instance de base de données par défaut. Pour toutes les autres instances, vous devez utiliser le Gestionnaire de configuration SQL Server pour affecter les ports uniques et inutilisés. Cette rubrique traite des sujets suivants :

  - Configuration requise pour une exception de pare-feu dans le cadre de l’utilisation de l’instance par défaut

  - Configuration requise pour une exception de pare-feu pour le service SQL Server Browser

  - Configuration requise pour les ports d’écoute statiques lors de l’utilisation d’instances nommées

## Configuration requise pour une exception de pare-feu dans le cadre de l’utilisation de l’instance par défaut

Si vous utilisez l’instance par défaut SQL Server d’une base de données lors du déploiement de Lync Server 2013, les exigences de règle de pare-feu suivantes permettent d’assurer la communication entre le pool frontal et cette instance.


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


## Configuration requise pour une exception de pare-feu pour le service SQL Server Browser

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
<td><p>UDP</p></td>
<td><p>1434</p></td>
<td><p>Inbound</p></td>
</tr>
</tbody>
</table>


## Configuration requise pour les ports d’écoute statiques lors de l’utilisation d’instances nommées

Si vous utilisez des instances nommées dans la configuration SQL Server pour des bases de données prenant en charge Lync Server 2013, vous devez configurer les ports statiques à l’aide du Gestionnaire de configuration SQL Server. Une fois les ports statiques affectés à chaque instance nommée, vous devez créer des exceptions pour chaque port statique du pare-feu.


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
<td><p>Inbound</p></td>
</tr>
</tbody>
</table>


## Documentation SQL Server

La documentation Microsoft SQL Server 2012 fournit des instructions détaillées concernant la configuration de l’accès des bases de données au pare-feu. Pour plus d’informations sur Microsoft SQL Server 2012, reportez-vous à « Configurer le Pare-feu Windows pour autoriser l’accès à SQL Server » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031).

