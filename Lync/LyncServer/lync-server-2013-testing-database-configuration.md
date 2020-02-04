---
title: 'Lync Server 2013 : test de la configuration d’une base de données'
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
ms.openlocfilehash: 6fcf6679481d4f35a457eb72960a8ae999b004d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a>Test de la configuration d’une base de données dans Lync Server 2013

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
<td><p>Échéancier de vérification</p></td>
<td><p>Jour</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsque l’application est exécutée en local à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins et doivent disposer de privilèges d’administrateur sur le serveur SQL Server.</p>
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande <strong>test-CsDatabase</strong> . Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de **contrôle test-CsDatabase** vérifie la connectivité à une ou plusieurs bases de données Lync Server 2013. Lors de l’exécution, l’applet de connexion **test-CsDatabase** lit la topologie du serveur Lync, tente de se connecter aux bases de données pertinentes, puis signale la réussite ou l’échec de chaque tentative. S’il est possible de créer une connexion, l’applet de contrôle renvoie également des informations telles que le nom de la base de données, les informations de version de SQL Server et l’emplacement de toutes les bases de données de miroirs installées.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La commande décrite dans l’exemple 1 vérifie la configuration de la base de données de gestion centrale.

    Test-CsDatabase -CentralManagementDatabase

L’exemple 2 vérifie toutes les bases de données serveur Lync installées sur l’ordinateur atl-sql-001.litwareinc.com.

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

Dans l’exemple 3, la vérification est effectuée uniquement pour la base de données d’archivage installée sur l’ordinateur atl-sql-001.litwareinc.com. Notez que le paramètre SqlInstanceName est inclus pour spécifier l’instance SQL Server (Archinst) de l’emplacement de la base de données d’archivage.

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

La commande affichée dans l’exemple 4 vérifie les bases de données installées sur l’ordinateur local.

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si la connectivité de la base de données est correctement configurée, vous recevrez une sortie similaire à celle-ci, avec la propriété réussite marquée comme **vraie**:

SqlServerFqdn : atl-sql-001.litwareinc.com

SqlInstanceName : RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName : XDS

DataSource :

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

Réussite : vrai

SqlServerFqdn : atl-sql-001.litwareinc.com

SqlInstanceName : RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName : lis

DataSource :

SQLServerVersion :

ExpectedVersion : 3.1.1

InstalledVersion :

Réussite : vrai

Si la base de données est configurée correctement mais toujours disponible, le champ réussite s’affichera comme **faux**, et des alertes et informations supplémentaires seront fournies :

SqlServerFqdn : atl-sql-001.litwareinc.com

SqlInstanceName : RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName : XDS

DataSource :

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

Réussite : faux

SqlServerFqdn : atl-cs-001.litwareinc.com

SqlInstanceName : RTC

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName : lis

DataSource :

SQLServerVersion :

ExpectedVersion : 3.1.1

InstalledVersion :

Réussite : faux

AVERTISSEMENT : test-CsDatabase a rencontré des erreurs. Consulter le fichier journal d’un

analyse détaillée et vérification de la prise en considération de toutes les erreurs (2) et avertissements (0)

avant de continuer.

AVERTISSEMENT : des résultats détaillés sont disponibles à l’adresse suivante :

"C :\\les\\utilisateurs\\testent\\AppData\\\\local\\Temp 2 test-CsDatabase-b18d488a-8044-4679-bbf2-

04d593cce8e6. html».

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles **les tests-CsDatabase** peuvent échouer :

  - Une valeur de paramètre incorrecte a été fournie. S’il est utilisé, les paramètres facultatifs doivent être correctement configurés ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et déterminez si l’opération aboutit.

  - Cette commande échoue si la base de données est mal configurée ou n’est pas encore déployée.

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

