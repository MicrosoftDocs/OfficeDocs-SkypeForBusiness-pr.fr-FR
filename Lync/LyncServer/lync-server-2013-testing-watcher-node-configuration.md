---
title: 'Lync Server 2013 : test de la configuration du nœud observateur d’observateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 920fc39d3800f83a2d40a613c391b2f0c93e4dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a>Test de la configuration du nœud FileSystemWatcher dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-11-03_


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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande <strong>test-CsWatcherNodeConfiguration</strong> . Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Si vous utilisez Microsoft System Center Operations Manager pour contrôler Lync Server 2013, vous avez la possibilité de configurer des « nœuds d’observation » : les ordinateurs qui exécutent de manière régulière et automatique des transactions de synthèse pour vérifier que le serveur Lync fonctionne correctement. devait. Les nœuds d’observation sont assignés aux pools et sont gérés à l’aide des cmdlets **CsWatcherNodeConfiguration** . Notez que vous n’avez pas besoin d’installer de nœuds FileSystemWatcher si vous utilisez System Center Operations Manager. Vous pouvez toujours surveiller votre système sans utiliser de nœuds FileSystemWatcher. La seule différence réside dans le fait que les transactions synthétiques que vous souhaitez exécuter doivent être appelées manuellement au lieu d’être automatiquement appelées par Operations Manager.

L’applet de **contrôle test-CsWatcherNodeConfiguration** vous permet de vérifier qu’un nœud d’observateur a été correctement configuré et qu’il est affecté à un pool Lync Server 2013 valide. Notez que l’applet de **contrôle test-CsWatcherNodeConfiguration** doit être exécutée sur le nœud Watcher lui-même. L’applet de commande ne peut pas être exécutée sur des ordinateurs distants.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La commande suivante vérifie les paramètres de configuration de chaque nœud FileSystemWatcher utilisé au sein de l’organisation.

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

La sortie d’exemple réussie suivante illustre un système avec quatre serveurs Edge.

Validation de la liste de ressources atl-cs-001.litwareinc.com par rapport à la topologie.

Réussite : atl-cs-001.litwareinc.com de réserve cible existe dans la topologie.

Réussite : le rôle de bureau d’enregistrement de la liste de atl-cs-001.litwareinc.com est installé.

Réussite : la version du pool cible atl-cs-001.litwareinc.com est prise en charge.

Réussite : le numéro de port pour le pool cible 5061 atl-cs-001.litwareinc.com est correct.

La vérification de l’absence de pools dans la configuration de nœud d’observateur est démarrée. Si des erreurs sont détectées, elles sont imprimées.

La vérification de l’absence de pools dans la configuration du nœud d’observation est terminée.

La recherche de clés de registre de nœud d’observation créées par l’installation du nœud d’observateur est démarrée. Si des erreurs sont détectées, elles sont imprimées.

La vérification des clés de registre de nœud d’observation créées par l’installation du nœud d’observation est terminée. Le type d’authentification détecté est Negotiate.

Validation réussie de l’existence des informations d’identification de l’utilisateur du test SIP : user1@ atl-cs-001.litwareinc.com dans le magasin de gestion des informations d’identification.

Validation réussie de l’existence des informations d’identification de l’utilisateur du test SIP : user2@ atl-cs-001.litwareinc.com dans le magasin de gestion des informations d’identification.

La vérification de l’absence de pools dans la configuration de nœud d’observateur est démarrée. Si des erreurs sont détectées, elles sont imprimées.

AVERTISSEMENT : le pool atl-cs-001.litwareinc.com possède le Bureau d’enregistrement

rôle installé, mais aucun utilisateur de test n’est configuré pour celui-ci.

La vérification de l’absence de pools dans la configuration du nœud d’observation est terminée.

La vérification des clés de registre de nœud d’observateur créées par l’installation du nœud d’observateur est

lance. Si des erreurs sont détectées, elles sont imprimées.

Test-CsWatcherNodeConfiguration : impossible de trouver la clé de registre d’intégrité dans

Logiciel\\de\\Communications en temps réel Microsoft en temps réel. Vérifiez que le nœud FileSystemWatcher. msi est

installé correctement.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles **les tests-CsWatcherNodeConfiguration** peuvent échouer :

  - Le nœud de l’observateur n’est pas correctement installé.

  - Aucun utilisateur de test n’est configuré.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[New-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[Remove-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[Set-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

