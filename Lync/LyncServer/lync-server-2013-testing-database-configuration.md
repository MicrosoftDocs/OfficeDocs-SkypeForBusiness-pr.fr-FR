---
title: 'Lync Server 2013 : test de la configuration de base de données'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1d57659c93aa42392f5408721157df1d14b56b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504101"
---
# <a name="testing-database-configuration-in-lync-server-2013"></a>Test de la configuration de la base de données dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-07-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Planification de la vérification</p></td>
<td><p>Journalière</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins et disposer de privilèges d’administrateur sur le serveur SQL Server.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-applet csdatabase</strong> . Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande **test-applet csdatabase** vérifie la connectivité avec une ou plusieurs bases de données Lync Server 2013. Lorsqu’elle est exécutée, l’applet de commande **test-applet csdatabase** lit la topologie Lync Server, tente de se connecter aux bases de données appropriées, puis signale la réussite ou l’échec de chaque tentative. Si une connexion peut être établie, l’applet de commande fournit également des informations telles que le nom de la base de données, les informations de version SQL Server et l’emplacement des éventuelles bases de données miroir installées.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La commande de l’exemple 1 vérifie la configuration de la base de données Central Management.

    Test-CsDatabase -CentralManagementDatabase

L’exemple 2 vérifie toutes les bases de données Lync Server installées sur l’ordinateur atl-sql-001.litwareinc.com.

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

Dans l’exemple 3, la vérification est exécutée uniquement pour la base de données Archiving installée sur l’ordinateur atl-sql-001.litwareinc.com. Notez que l’inclusion du paramètre SqlInstanceName permet de spécifier l’instance SQL Server (Archinst) où se trouve la base de données Archiving.

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

La commande illustrée à l’exemple 4 vérifie les bases de données installées l’ordinateur local.

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si la connectivité de la base de données est correctement configurée, vous recevrez un résultat similaire à celui-ci, avec la propriété réussite marquée **true**:

SqlServerFqdn : atl-sql-001.litwareinc.com

SqlInstanceName : RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName : XDS

Source

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

Réussite : true

SqlServerFqdn : atl-sql-001.litwareinc.com

SqlInstanceName : RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName : lis

Source

SQLServerVersion :

ExpectedVersion : 3.1.1

InstalledVersion :

Réussite : true

Si la base de données est correctement configurée mais toujours disponible, le champ réussite affiche **false**et des avertissements et informations supplémentaires sont fournis :

SqlServerFqdn : atl-sql-001.litwareinc.com

SqlInstanceName : RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName : XDS

Source

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

Réussite : false

SqlServerFqdn : atl-cs-001.litwareinc.com

SqlInstanceName : RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName : lis

Source

SQLServerVersion :

ExpectedVersion : 3.1.1

InstalledVersion :

Réussite : false

AVERTISSEMENT : Test-CsDatabase rencontré des erreurs. Consulter le fichier journal pour un

analyse détaillée et vérification de la prise en compte de toutes les erreurs (2) et avertissements (0)

avant de continuer.

AVERTISSEMENT : les résultats détaillés sont disponibles à l’adresse

"C : \\ Users \\ testing \\ AppData \\ local \\ temp \\ 2 \\ test-applet csdatabase-b18d488a-8044-4679-bbf2-

04d593cce8e6.html».

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec **de test-applet csdatabase** :

  - Une valeur de paramètre incorrecte a été fournie. Si ce paramètre est utilisé, les paramètres facultatifs doivent être configurés correctement ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.

  - Cette commande échoue si la base de données n’est pas configurée correctement ou n’est pas encore déployée.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsDatabaseMirrorState](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-CsUserDatabaseState](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

