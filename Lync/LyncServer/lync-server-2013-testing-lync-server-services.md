---
title: 'Lync Server 2013 : test des services Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98c5f39a636eb300f19cd42131fc42d2480bbf14
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a>Test des services Lync Server dans Lync Server 2013

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
<td><p>Tous les jours</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsComputer. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Test-CsComputer vérifie l’état de tous les services Lync Server 2013 en cours d’exécution sur l’ordinateur local. (Test-CsComputer peut uniquement être exécuté localement, il ne peut pas être exécuté à partir d’une instance distante de Windows PowerShell.) L’applet de commande vérifie également si les ports de pare-feu appropriés sont ouverts sur l’ordinateur et détermine si les groupes Active Directory créés lors de l’installation de Lync Server 2013 ont été ajoutés aux groupes locaux correspondants. Par exemple, test-CsComputer vérifiera que le groupe Active Directory RTCUniversalUserAdmins a été ajouté au groupe administrateurs.

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-CsComputer ne peut être exécutée que sur l’ordinateur local, vous ne pouvez pas appeler test-CsComputer à partir d’une instance distante de Windows PowerShell. Par défaut, test-CsComputer affiche très peu de sortie à l’écran, et les informations renvoyées par l’applet de commande sont écrites dans un fichier HTML. Pour cette raison, nous vous recommandons d’inclure le paramètre Verbose et le paramètre report à chaque fois que vous exécutez la commande test-CsComputer. Le paramètre Verbose fournira une sortie plus détaillée à l’écran pendant l’exécution de l’applet de commande. Le paramètre Report vous permet de spécifier un chemin d’accès et un nom de fichier pour le fichier HTML généré par test-CsComputer. Si vous n’incluez pas le paramètre Report, le fichier HTML est automatiquement enregistré dans votre dossier Users et reçoit un nom semblable à celui-ci : ce84964a-c4da-4622-ad34-c54ff3ed361f. html.

L’exemple de commande suivant exécute test-CsComputer et enregistre la sortie dans un fichier nommé C :\\logs\\ComputerTest. html :

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

En raison du nombre de vérifications de vérification effectuées, test-CsComputer n’indique pas de simple **Oui, le test a réussi** ou **non, le test a échoué**. Au lieu de cela, vous devez afficher le fichier HTML généré à l’aide d’Internet Explorer pour déterminer la réussite ou l’échec de chaque test.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec de test-CsComputer :

  - L’ordinateur de test n’est peut-être pas activé pour une utilisation avec Lync Server. Cela peut se produire si les services ou les rôles serveur Lync Server sur l’ordinateur ont changé et que la cmdlet Enable-CsComputer n’a pas été exécutée. Pour résoudre ce problème, exécutez la commande suivante :
    
        Enable-CsComputer

  - La réplication n’est peut-être pas à jour sur l’ordinateur de test. Vous pouvez vérifier l’état de réplication actuel d’un ordinateur en exécutant la cmdlet Get-CsManagementStoreReplicationStatus :
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    Si le statut de la réplication n’est pas à jour, vous pouvez forcer manuellement la réplication à l’aide d’une commande semblable à celle-ci :
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - Il se peut que vous deviez activer la topologie. Si vous modifiez la topologie Lync Server (modifications susceptibles d’affecter l’ordinateur local), vous devez activer la nouvelle topologie. Vous pouvez activer la topologie à tout moment en exécutant la commande suivante :
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

