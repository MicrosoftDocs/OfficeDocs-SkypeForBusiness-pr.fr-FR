---
title: 'Lync Server 2013 : test du routage des appels de téléphonie RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 750efc8ced1dbb4c048d10c879f0bfa2dd4a4f32
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a>Test du routage des appels RTC dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-11-01_


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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-CsInterTrunkRouting</strong> . Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande **test-CsInterTrunkRouting** vérifie que les appels peuvent être acheminés d’un SIP à un autre. Pour ce faire, l’applet de commande reçoit un numéro de téléphone et une configuration de jonction. **Test-CsInterTrunkRouting** indique alors les itinéraires correspondants et les utilisations RTC correspondantes pour le numéro spécifié. Notez que les appels peuvent être routés entre des segments uniquement si ceux-ci ont un modèle de numéro qui correspond au numéro de téléphone spécifié et uniquement s’ils partagent au moins une utilisation PSTN.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Les commandes indiquées ci-dessous renvoient les itinéraires correspondants et les utilisations téléphoniques correspondantes qui permettent aux utilisateurs d’appeler le numéro de téléphone 1-206-555-1219 à l’aide des paramètres de configuration de jonction pour le site de Redmond.

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si les appels peuvent être acheminés d’un SIP à un autre, vous recevrez un résultat semblable à celui-ci :

FirstMatchingRoute MatchingUsage MatchingRoutes

\------------------ ------------- --------------

RedmondRoute LocalUsage {RedmondRoute}

Si le test a échoué, vous recevrez un résultat similaire à celui-ci :

Test-CsInterTrunkRouting : impossible de traiter la transformation d’argument sur le paramètre

« TrunkConfiguration ». TrunkConfigurationsetting non valide (paramètre). Spécifier une

paramètre valide (paramètre), puis réessayez.

À la ligne : 1 char : 79

\+Test-CsInterTrunkRouting-TargetNumber "Tél : + 12065551219"

\-TrunkConfiguration $t...

\+

~~

\+CategoryInfo : InvalidData : ( :) \[Test-CsInterTrunkRouting\], par

ameterBindingArgumentTransformationException

\+FullyQualifiedErrorId : ParameterArgumentTransformationError, Microsoft. R

TC. Management. Voice. cmdlets. TestOcsInterTrunkRoutingCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec **de test-CsInterTrunkRouting** :

  - Vous avez spécifié des paramètres non valides. La jonction n’est peut-être pas encore correctement configurée et le numéro cible spécifié est peut-être incorrect ou non valide.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[Get-applet cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

