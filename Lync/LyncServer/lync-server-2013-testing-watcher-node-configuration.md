---
title: 'Lync Server 2013 : test de la configuration du nœud observateur'
description: 'Lync Server 2013 : test de la configuration du nœud observateur.'
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
ms.openlocfilehash: f1eeb141eee011d7e06f5dd49e483e026484d733
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546840"
---
# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a>Test de la configuration du nœud observateur dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-applet cswatchernodeconfiguration</strong> . Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Si vous utilisez Microsoft System Center Operations Manager pour analyser Lync Server 2013, vous avez la possibilité de configurer les « nœuds observateur » : ordinateurs qui exécutent régulièrement et automatiquement des transactions synthétiques pour vérifier que Lync Server fonctionne comme prévu. Les nœuds observateurs sont affectés à des pools et sont gérés à l’aide des applets de commande **applet cswatchernodeconfiguration** . Notez que vous n’avez pas besoin d’installer des nœuds observateur si vous utilisez System Center Operations Manager. Vous pouvez toujours surveiller votre système sans utiliser de nœuds observateur. La seule différence réside dans le fait que les transactions synthétiques que vous souhaitez exécuter doivent être appelées manuellement au lieu d’être appelées automatiquement par Operations Manager.

L’applet de commande **test-applet cswatchernodeconfiguration** vous permet de vérifier qu’un nœud observateur a été correctement configuré et qu’il est affecté à un pool Lync Server 2013 valide. Notez que la cmdlet **test-applet cswatchernodeconfiguration** doit être exécutée sur le nœud observateur lui-même. L’applet de commande ne peut pas être exécutée sur des ordinateurs distants.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La commande suivante vérifie les paramètres de configuration de chaque nœud observateur utilisé dans l’organisation.

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

L’exemple de sortie réussi suivant illustre un système avec quatre serveurs Edge.

Validation du pool cible atl-cs-001.litwareinc.com par rapport à la topologie.

Opération réussie : le pool cible atl-cs-001.litwareinc.com existe dans la topologie.

Opération réussie : le rôle serveur d’inscriptions atl-cs-001.litwareinc.com a été installé sur le pool cible.

Opération réussie : la version du pool cible atl-cs-001.litwareinc.com est prise en charge.

Opération réussie : le numéro de port du pool cible 5061 atl-cs-001.litwareinc.com est correct.

La vérification des pools manquants dans la configuration du nœud observateur est démarrée. Si une erreur est détectée, elle est imprimée.

La vérification des pools manquants dans la configuration du nœud observateur est terminée.

La vérification des clés de Registre du nœud observateur créées par l’installation du nœud observateur est démarrée. Si une erreur est détectée, elle est imprimée.

La vérification des clés de Registre du nœud observateur créées par l’installation du nœud observateur est terminée. Le type d’authentification détecté est Negotiate.

Existence de la validation des informations d’identification de l’utilisateur test SIP : user1@ atl-cs-001.litwareinc.com dans le magasin de gestion des informations d’identification.

Existence de la validation des informations d’identification de l’utilisateur test SIP : user2@ atl-cs-001.litwareinc.com dans le magasin de gestion des informations d’identification.

La vérification des pools manquants dans la configuration du nœud observateur est démarrée. Si une erreur est détectée, elle est imprimée.

AVERTISSEMENT : le pool atl-cs-001.litwareinc.com possède un serveur d’inscriptions

rôle installé, mais aucun utilisateur de test n’est configuré pour lui.

La vérification des pools manquants dans la configuration du nœud observateur est terminée.

La vérification des clés de Registre du nœud observateur créées par l’installation du nœud observateur est

début. Si une erreur est détectée, elle est imprimée.

Test-CsWatcherNodeConfiguration : impossible de trouver la clé de registre d’intégrité dans

Logiciels \\ Microsoft \\ communications en temps réel. Assurez-vous que le nœud observateur. msi est

installé correctement.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec **de test-applet cswatchernodeconfiguration** :

  - Le nœud observateur n’est pas installé correctement.

  - Aucun utilisateur de test n’est configuré.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Get-applet cswatchernodeconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[New-applet cswatchernodeconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[Remove-applet cswatchernodeconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[Set-applet cswatchernodeconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

