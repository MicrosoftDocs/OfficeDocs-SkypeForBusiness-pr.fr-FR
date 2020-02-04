---
title: 'Lync Server 2013 : Autorisations de déploiement de SQL Server'
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
ms.openlocfilehash: 393e293dfc7e20fa1e990d9f87c17c6e72776be3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a>Autorisations de déploiement de SQL Server dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Microsoft SQL Server 2012 a des exigences spécifiques lors de l’installation et du déploiement de Lync Server 2013. Dans la mesure où Windows et SQL Server définissent la sécurité d’une manière différente, la connexion en tant qu’administrateur dans le domaine Active Directory n’accorde pas implicitement des autorisations pour SQL Server. Vous devez également être membre de l’entité sysadmin sur le serveur SQL Server que vous configurez.

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a>Autorisations requises pour l’installation de base de données et de Lync Server

Les options suivantes décrivent trois autorisations et des associations d’appartenance de groupe pour l’installation de fichiers Lync Server 2013 et de bases de données SQL Server. Choisissez le scénario qui correspond le mieux aux besoins de votre organisation.

### <a name="permissions-and-group-membership-associations"></a>Autorisations et associations d’appartenance aux groupes

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
<th>Rôles : autorisations SQL Server standard et appartenance au groupe</th>
<th>Rôles : autorisations et appartenances aux groupes Lync Server 2013 typiques</th>
<th>Résultat des autorisations</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Administrateur Lync Server 2013</p></td>
<td><p>Doit être membre du groupe de sécurité SQL Server sysadmin et membre du groupe administrateurs SQL Server local.</p></td>
<td><p>Doit être membre du groupe RTCUniversalServerAdmins</p></td>
<td><p>L’administrateur de Lync Server 2013 dispose des autorisations nécessaires pour installer les bases de données Lync Server 2013 et SQL Server.</p></td>
</tr>
<tr class="even">
<td><p>Administrateur SQL Server</p></td>
<td><p>Membre du groupe SQL Server sysadmin (ou équivalent) et membre du groupe administrateurs locaux SQL Server</p></td>
<td><p>Doit être membre du groupe RTCUniversalServerReadOnly</p></td>
<td><p>L’administrateur SQL Server dispose des autorisations appropriées pour installer à la fois Lync Server 2013 et les bases de données SQL Server.</p></td>
</tr>
<tr class="odd">
<td><p>Les administrateurs partagent les tâches d’installation</p></td>
<td><p>L’administrateur SQL Server est membre du groupe sysadmins (ou équivalent) et membre du groupe administrateurs SQL Server local.</p></td>
<td><p>L’administrateur Lync Server 2013 est membre de RTCUniversalServerAdmins</p></td>
<td><p>L’administrateur 2013 de Lync Server peut installer Lync Server 2013, mais ne peut pas installer les bases de données. L’administrateur SQL Server a recours aux cmdlets Lync Server Management Shell et Windows PowerShell fournies par l’administrateur 2013 de Lync Server. Lync Server 2013 Management Shell utilisé par l’administrateur SQL Server est installé sur le serveur frontal. Cela évite d’avoir à installer les outils d’administration de Lync Server 2013 sur le serveur SQL Server.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

