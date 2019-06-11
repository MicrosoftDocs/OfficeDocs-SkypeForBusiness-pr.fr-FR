---
title: 'Lync Server 2013: test du plan de numérotation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2815248084e7591c11157cde3fb4851722315073
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a>Test du plan de numérotation dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsDialPlan. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsDialPlan vous permet d’afficher les résultats de l’application d’un plan de numérotation à un numéro de téléphone donné. Les plans de numérotation fournissent des informations, telles que les règles de normalisation, requises pour permettre aux utilisateurs d’entreprise Voice d’effectuer des appels téléphoniques. À partir d’un numéro composé et d’un plan de numérotation, cette applet de contrôle vérifie quelle règle de normalisation du plan de numérotation sera appliquée et quel sera le numéro traduit.

Vous pouvez utiliser cette cmdlet pour résoudre les problèmes liés aux traductions de nombres ou pour vérifier l’application de règles à certains numéros.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’applet de contrôle test-CsDialPlan vous demande d’effectuer deux actions. Tout d’abord, vous devez obtenir une instance du plan de numérotation testé. pour ce faire, vous pouvez utiliser l’applet de passe Get-CsDialPlan. Deuxièmement, vous devez spécifier le numéro de téléphone qui doit être normalisé. Le format utilisé pour le numéro de téléphone doit correspondre au numéro composé par un utilisateur. Par exemple, cette commande récupère une instance du plan de numérotation, RedmondDialPlan et vérifie si le numéro de téléphone 12065551219 peut être normalisé:

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

Si vous disposez d’une règle de normalisation qui ajoute automatiquement le code du pays (dans cet exemple, 1) et l’indicatif de la région (206), vous pouvez vérifier le numéro de téléphone 5551219 comme suit:

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Test-CsDialPlan est différent de la plupart des cmdlets de test du serveur Lync, car il n’indique qu’un test a réussi ou échoué. Lors de l’utilisation de test-CsDialPlan, vous ne recevez pas de sortie semblable à celle-ci avec le résultat clairement libellé:

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: réussite

Latence: 00:00:06.8630376

Error

Diagnostic

Si test-CsDialPlan réussit, vous recevez des informations sur la règle de normalisation qui a pu traduire et utiliser le numéro de téléphone spécifié.

TranslatedNumber: + 12065551219

MatchingRule: description =; Modèle = ^ (\\j (11)) $; Traduction = + $1;

Nom = tout préfixe; IsInternalExtension = false

Si test-CsDialPlan échoue (autrement dit, si le plan de numérotation ne dispose pas d’une règle de normalisation qui peut traduire le numéro de téléphone spécifié), il vous suffit de recevoir la sortie «vider» comme suit:

TranslatedNumber :

MatchingRule :

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsDialPlan peuvent échouer:

  - Vous avez peut-être déjà utilisé un format incorrect lorsque vous spécifiez le numéro de téléphone. Les plans de numérotation incluent des règles de normalisation qui permettent à Lync Server de traduire les numéros de téléphone numérotés ou entrés par un utilisateur. Par conséquent, votre plan de numérotation doit être doté de règles de normalisation correspondant aux numéros que les utilisateurs peuvent composer. Par exemple, si les utilisateurs peuvent composer le code de pays, l’indicatif régional et le numéro de téléphone lui-même, cela signifie que votre plan de numérotation doit être doté d’une règle de normalisation pour gérer les numéros de téléphone comme suit:
    
    12065551219
    
    Toutefois, si vous entrez un numéro de téléphone incorrect (par exemple, en ne disquittant pas le dernier chiffre), test-CsDialPlan échoue. Ce n’est pas parce que le plan de numérotation est défectueux, car vous avez entré un numéro de téléphone qui ne peut pas être interprété.

</div>

</div>

<span> </span>

</div>

</div>

</div>

