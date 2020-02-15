---
title: 'Lync Server 2013 : vérifier les règles de normalisation vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52820473a632598779aae9023967598b8ae27f89
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a>Vérifier les règles de normalisation vocale dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-20_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Planification de la vérification</p></td>
<td><p>Tous les mois</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsVoiceNormalizationRule. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Les règles de normalisation vocale sont utilisées pour convertir un numéro de téléphone composé par un utilisateur (par exemple, 2065551219) au format E. 164 utilisé par Lync Server (+ 12065551219). Par exemple, si les utilisateurs sont à l’habitude de composer un numéro de téléphone sans inclure le code du pays ou l’indicatif régional (par exemple, 5551219), vous devez disposer d’une règle de normalisation vocale pouvant convertir ce numéro au format E. 164 : + 12065551219. Sans cette règle, l’utilisateur ne peut pas appeler 555-1219.

L’applet de commande test-CsVoiceNormalizationRule vérifie qu’une règle de normalisation vocale spécifiée peut convertir un numéro de téléphone spécifié. Par exemple, cette commande vérifie si la règle de normalisation NoAreaCode peut normaliser et convertir la chaîne de numérotation 5551219.

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Pour exécuter la cmdlet Test-CsVoiceNormalizationRule, vous devez d’abord utiliser la cmdlet Get-CsVoiceNormalizationRule pour récupérer une instance de la règle testée, puis canaliser cette instance à test-CsVoiceNormalizationRule. Une syntaxe similaire à celle-ci ne fonctionnera pas :

Test-CsVoiceNormalizationRule-DialedNumber "12065551219" – NormalizationRule "Global/prefix All"

À la place, utilisez une syntaxe telle que la suivante, qui combine les cmdlets Get-CsVoiceNormalizationRule et test-CsVoiceNormalizationRule :

Get-CsVoiceNormalizationRule-Identity "Global/prefix All" | Test-CsVoiceNormalizationRule-DialedNumber "12065551219"

<div>


> [!NOTE]  
> . Vous pouvez également utiliser cette approche pour récupérer une instance d’une règle, puis la tester sur un numéro de téléphone spécifié :



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

Entrez la valeur du paramètre DialedNumber exactement comme vous prévoyez que ce numéro doit être composé. Par exemple, si la règle de normalisation vocale spécifiée est censée ajouter automatiquement le code du pays (1 initiale dans la valeur 12065551219), vous devez laisser le code du pays :

`-DialedNumber "2065551219"`

Si la règle est configurée correctement, elle ajoute automatiquement le code du pays lors de la conversion du numéro au format E. 164 utilisé par Lync Server.

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande test-CsVoiceNormalizationRule.

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si la règle de normalisation vocale spécifiée peut traduire le numéro fourni, le numéro traduit s’affiche à l’écran :

TranslatedNumber

\----------------

\+12065551219

Si le test échoue, un numéro traduit vide est renvoyé :

TranslatedNumber

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Si le test-CsVoiceNormalizationRule renvoie un numéro traduit, cela signifie que la règle de normalisation vocale spécifiée n’a pas pu convertir le numéro de téléphone fourni au format E. 164 utilisé par Lync Server. Pour vérifier que vous avez correctement tapé le numéro de téléphone, vérifiez tout d’abord que vous avez tapé le numéro de téléphone. Par exemple, vous pouvez vous attendre à ce que votre règle de normalisation vocale ait des problèmes de traduction d’un numéro semblable à celui-ci :

`-DialedNumber "1"`

En supposant que le numéro a été saisi correctement, l’étape suivante consiste à vérifier que la règle de normalisation spécifiée est conçue pour gérer ce numéro de téléphone. Par exemple, une règle de normalisation peut être conçue pour gérer le format 12065551219, mais une deuxième règle peut être conçue pour gérer le numéro 2065551219. (Il s’agit du même numéro de téléphone, moins le code pays 1 au début.) Pour renvoyer des informations détaillées sur une règle de normalisation vocale, exécutez une commande semblable à celle-ci :

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

Pour renvoyer des informations détaillées sur toutes les règles de normalisation vocale, exécutez cette commande à la place :

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Test-CsVoiceNormalizationRule](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

