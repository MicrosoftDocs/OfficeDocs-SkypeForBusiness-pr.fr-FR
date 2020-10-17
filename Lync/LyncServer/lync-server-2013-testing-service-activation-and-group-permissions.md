---
title: 'Lync Server 2013 : test de l’activation de service et des autorisations de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92e29cafcfac7a74e43617841a174653f6072c5a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530521"
---
# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a>Test de l’activation de service et des autorisations de groupe dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-06-05_


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
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsTopology. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande Test-CsTopology vous permet de vérifier que Lync Server 2013 fonctionne correctement dans une étendue globale. Par défaut, l’applet de commande vérifie l’ensemble de votre infrastructure Lync Server, en vérifiant que les services requis sont en cours d’exécution et que les autorisations appropriées sont définies pour ces services et pour les groupes de sécurité universels créés lors de l’installation de Lync Server.

En plus de vérifier la validité de l’installation de Lync Server, Test-CsTopology vous permet également de vérifier la validité d’un service spécifique. Par exemple, cette commande vérifie l’état du serveur de conférence A/V sur le pool atl-cs-001.litwareinc.com :

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Par défaut, Test-CsTopology affiche très peu de sortie à l’écran. Au lieu de cela, les informations renvoyées par l’applet de commande sont écrites dans un fichier HTML. Le paramètre Report vous permet de spécifier un chemin d’accès et un nom de fichier pour le fichier HTML généré par test-CsTopology. Si vous n’incluez pas le paramètre Report, le fichier HTML est automatiquement enregistré dans votre dossier Users et un nom semblable à celui-ci est attribué : ce84964a-c4da-4622-ad34-c54ff3ed361f.html.

L’exemple de commande suivant exécute Test-CsTopology et enregistre la sortie dans un fichier nommé C : \\ Logs \\ComputerTest.html :

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Contrairement à la plupart des applets de commande de test, Test-CsTopology renvoie la réussite ou l’échec. En partie, cela est dû à un grand nombre de contrôles de vérification que l’applet de commande doit effectuer chaque fois qu’elle est exécutée. Au lieu de cela, les données sont enregistrées dans un rapport HTML qui peut être affiché à l’aide d’Internet Explorer.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques raisons courantes pour lesquelles Test-CsTopology peut échouer :

  - La réplication n’est peut-être pas à jour sur l’ordinateur de test. Vous pouvez vérifier l’état de réplication actuel d’un ordinateur en exécutant l’applet de commande Get-CsManagementStoreReplicationStatus :
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    Si l’état de la réplication n’est pas à jour, vous pouvez forcer manuellement la réplication à l’aide d’une commande semblable à celle-ci :
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - Il se peut que vous deviez activer la topologie. Si vous modifiez la topologie Lync Server (modifications susceptibles d’affecter l’ordinateur local), vous devez activer la nouvelle topologie. Vous pouvez activer la topologie à tout moment en exécutant la commande suivante :
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

