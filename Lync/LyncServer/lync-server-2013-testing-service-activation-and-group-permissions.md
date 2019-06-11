---
title: 'Lync Server 2013: vérification des autorisations d’activation et de groupe des services'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6616e1f2835ab55f9e3e8f98e5a8693ef3d2fb4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a>Test de l’activation et du regroupement des services dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-06-05_


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
<td><p>Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsTopology. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsTopology vous permet de vérifier que Lync Server 2013 fonctionne correctement dans une étendue globale. Par défaut, l’applet de contrôle vérifie l’intégralité de l’infrastructure de votre serveur Lync, en vérifiant que les services requis s’exécutent et que les autorisations appropriées sont définies pour ces services et pour les groupes de sécurité universelles créés lors de l’installation de Lync Server. .

En plus de vérifier la validité de l’installation de Lync Server, test-CsTopology vous permet également de vérifier la validité d’un service spécifique. Par exemple, la commande suivante vérifie l’état du serveur de conférence A/V sur le pool atl-cs-001.litwareinc.com:

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Par défaut, test-CsTopology affiche un faible niveau de sortie à l’écran. À la place, les informations renvoyées par l’applet de passe sont écrites dans un fichier HTML. Le paramètre rapport vous permet de spécifier un chemin d’accès et un nom de fichier pour le fichier HTML généré par test-CsTopology. Si vous n’incluez pas le paramètre de rapport, le fichier HTML sera automatiquement enregistré dans votre dossier utilisateurs et sera doté du nom semblable à ce qui suit: ce84964a-c4da-4622-ad34-c54ff3ed361f. html.

L’exemple de commande suivant exécute test-CsTopology et enregistre la sortie dans un fichier nommé C:\\logs\\ComputerTest. html:

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Contrairement à la plupart des cmdlets de test, test-CsTopology renvoie la réussite ou l’échec du rapport. En partie, il s’agit d’un grand nombre de contrôles de vérification que l’applet de contrôle doit effectuer chaque fois qu’elle s’exécute. Au lieu de cela, les données sont enregistrées dans un rapport HTML qui peut être affiché à l’aide d’Internet Explorer.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsTopology peuvent échouer:

  - La réplication n’est peut-être pas à jour sur l’ordinateur de test. Vous pouvez vérifier l’état de réplication actuel d’un ordinateur en exécutant l’applet de contrôle Get-CsManagementStoreReplicationStatus:
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    Si l’état de la réplication n’est pas à jour, vous pouvez le faire manuellement en utilisant une commande similaire à celle-ci:
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - La topologie peut être activée. Si vous modifiez la topologie du serveur Lync (modifications qui peuvent affecter l’ordinateur local), vous devez activer la nouvelle topologie. Vous pouvez activer la topologie à tout moment en exécutant la commande suivante:
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

