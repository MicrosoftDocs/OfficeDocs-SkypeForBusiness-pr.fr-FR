---
title: 'Lync Server 2013 : test du plan de numérotation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14c8e53b0b18ae7813cf0f2d63aaa54ffbd4998b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a>Test du plan de numérotation dans Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsDialPlan. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande test-CsDialPlan vous permet d’afficher les résultats de l’application d’un plan de numérotation à un numéro de téléphone donné. Les plans de numérotation fournissent des informations, telles que la manière dont les règles de normalisation sont appliquées, requises pour permettre aux utilisateurs de voix entreprise d’effectuer des appels téléphoniques. Dotée d’un numéro composé et d’un plan de numérotation, cette applet de commande vérifiera la règle de normalisation qui sera appliquée au sein du plan de numérotation et quel sera le numéro traduit.

Vous pouvez utiliser cette applet de commande pour résoudre les problèmes liés aux traductions de numéros ou pour vérifier comment appliquer des règles à certains numéros.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-CsDialPlan vous oblige à effectuer deux opérations. Tout d’abord, vous devez obtenir une instance du plan de numérotation testé ; Cela peut être réalisé à l’aide de la cmdlet Get-CsDialPlan. Deuxièmement, vous devez spécifier le numéro de téléphone qui doit être normalisé. Le format utilisé pour le numéro de téléphone doit correspondre au numéro composé par un utilisateur. Par exemple, cette commande extrait une instance du plan de numérotation, RedmondDialPlan, et vérifie si le numéro de téléphone 12065551219 peut être normalisé :

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

Si vous disposez d’une règle de normalisation qui ajoute automatiquement le code du pays (dans cet exemple, 1) et l’indicatif régional (206), vous pouvez vérifier le numéro de téléphone 5551219, comme suit :

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Test-CsDialPlan diffère de la plupart des applets de commande Lync Server test car il indique uniquement indirectement si un test a réussi ou échoué. Lors de l’utilisation de test-CsDialPlan, vous ne recevez pas de sortie semblable à celle-ci avec le résultat clairement étiqueté :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:06.8630376

«

Diagnostique

En revanche, si test-CsDialPlan réussit, vous recevrez des informations sur la règle de normalisation qui a réussi à traduire et à utiliser le numéro de téléphone spécifié :

TranslatedNumber : + 12065551219

MatchingRule : description =; Modèle = ^ (\\d (11)) $; Translation = + $1 ;

Nom = préfixe tout ; IsInternalExtension = false

Si test-CsDialPlan échoue (autrement dit, si le plan de numérotation ne dispose pas d’une règle de normalisation qui peut traduire le numéro de téléphone spécifié), vous recevrez simplement la sortie « vide » comme suit :

TranslatedNumber :

MatchingRule :

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec de test-CsDialPlan :

  - Vous avez peut-être utilisé un format incorrect lors de la spécification du numéro de téléphone. Les plans de numérotation incluent des règles de normalisation qui permettent à Lync Server de traduire les numéros de téléphone composés ou entrés par un utilisateur. Par conséquent, votre plan de numérotation doit avoir des règles de normalisation qui correspondent aux numéros susceptibles d’être composés par les utilisateurs. Par exemple, si les utilisateurs peuvent composer le code du pays, l’indicatif régional, puis le numéro de téléphone lui-même, cela signifie que votre plan de numérotation doit disposer d’une règle de normalisation pour gérer les numéros de téléphone comme ceci :
    
    12065551219
    
    Toutefois, si vous entrez un numéro de téléphone incorrect (par exemple, en ne laissant pas le chiffre final), test-CsDialPlan échoue. Cela n’est pas dû au fait que le plan de numérotation est défectueux mais parce que vous avez entré un numéro de téléphone qui ne peut pas être interprété.

</div>

</div>

<span> </span>

</div>

</div>

</div>

