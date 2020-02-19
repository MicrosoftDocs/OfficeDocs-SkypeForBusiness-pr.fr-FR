---
title: 'Lync Server 2013 : autorisations de déploiement pour SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a6697fdb4910b16592ace53e08dcc754cdb2446
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a>Autorisations de déploiement pour SQL Server dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Microsoft SQL Server 2012 a des exigences spécifiques lors de l’installation et du déploiement de Lync Server 2013. Étant donné que Windows et SQL Server définissent leur sécurité différemment, la connexion en tant qu’administrateur dans le domaine Active Directory n’accorde pas implicitement des autorisations pour SQL Server. Vous devez être membre de l’entité sysadmin sur le serveur SQL Server que vous configurez.

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a>Autorisations requises pour l’installation de la base de données et de Lync Server

Les options suivantes détaillent trois autorisations et des associations d’appartenance aux groupes pour l’installation des fichiers Lync Server 2013 et des bases de données SQL Server. Choisissez le scénario qui répond le mieux aux exigences de votre organisation.

### <a name="permissions-and-group-membership-associations"></a>Associations des autorisations et de l’appartenance à un groupe

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rôle SQL Server ou Lync Server 2013</th>
<th>Autorisations SQL Server et appartenance à un groupe en fonction du rôle</th>
<th>Rôle : autorisations Lync Server 2013 classiques et appartenance aux groupes</th>
<th>Possibilités associées aux autorisations</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Administrateur Lync Server 2013</p></td>
<td><p>Doit être membre du groupe de sécurité sysadmins SQL Server et membre du groupe Administrateurs local SQL Server</p></td>
<td><p>Doit être membre du groupe RTCUniversalServerAdmins</p></td>
<td><p>L’administrateur Lync Server 2013 dispose des autorisations appropriées pour installer les bases de données Lync Server 2013 et SQL Server.</p></td>
</tr>
<tr class="even">
<td><p>Administrateur SQL Server</p></td>
<td><p>Membre du groupe sysadmins SQL Server (ou équivalent) et membre du groupe Administrateurs local SQL Server</p></td>
<td><p>Doit être membre du groupe RTCUniversalServerReadOnly</p></td>
<td><p>L’administrateur SQL Server dispose des autorisations appropriées pour installer les bases de données Lync Server 2013 et SQL Server.</p></td>
</tr>
<tr class="odd">
<td><p>Les deux administrateurs partageant les tâches d’installation</p></td>
<td><p>L’administrateur SQL Server est membre du groupe sysadmins (ou équivalent) et membre du groupe Administrateurs local SQL Server</p></td>
<td><p>L’administrateur Lync Server 2013 est membre de RTCUniversalServerAdmins</p></td>
<td><p>L’administrateur Lync Server 2013 peut installer Lync Server 2013, mais ne peut pas installer les bases de données. L’administrateur SQL Server utilise les applets de commande Lync Server Management Shell et Windows PowerShell fournies par l’administrateur Lync Server 2013 pour installer les bases de données. Lync Server 2013 Management Shell utilisé par l’administrateur SQL Server est installé sur le serveur frontal. Ainsi, il n’est pas nécessaire d’installer les outils d’administration Lync Server 2013 sur le serveur basé sur SQL Server.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

