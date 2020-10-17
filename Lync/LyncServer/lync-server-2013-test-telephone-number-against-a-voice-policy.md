---
title: 'Lync Server 2013 : test du numéro de téléphone par rapport à une stratégie de voix'
description: 'Lync Server 2013 : test du numéro de téléphone par rapport à une stratégie de voix.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a6523e7657bd4c30c23909bb02e2569b6067298
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548030"
---
# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a>Tester le numéro de téléphone par rapport à une stratégie de voix dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<td><p>Mensuelle</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsVoicePolicy. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Possibilité pour les utilisateurs de voix entreprise d’effectuer des appels téléphoniques sortants sur les charnières de réseau téléphonique commuté (PSTN), en grande partie, sur trois points :

  - Stratégie de voix attribuée à l’utilisateur.

  - Itinéraires des communications vocales utilisés pour acheminer les appels depuis Lync Server vers le réseau RTC.

  - L’utilisation RTC, une propriété Lync Server qui connecte une stratégie de voix à un itinéraire de communications vocales.

L’utilisation RTC est particulièrement importante : il s’agit de la propriété qui connecte une stratégie de voix à un itinéraire de communications vocales. (Une stratégie de voix et un itinéraire de communications vocales sont appelés connectés s’ils disposent d’au moins une utilisation RTC en commun.) Les stratégies de voix peuvent être configurées sans spécifier d’utilisation PSTN. Dans ce cas, les utilisateurs auxquels cette stratégie a été attribuée ne peuvent pas effectuer d’appels sortants sur le réseau RTC. De même, les itinéraires de communications vocales qui n’ont pas au moins une utilisation PSTN spécifiée ne pourront pas acheminer les appels vers le réseau RTC.

L’applet de commande Test-CsVoicePolicy vérifie qu’une stratégie de voix donnée a une utilisation PSTN et que l’utilisation est partagée par au moins un itinéraire de communications vocales. Si la vérification exécutée par Test-CsVoicePolicy réussit, la cmdlet indique le nom du premier itinéraire de communications vocales valide, ainsi que le nom de l’utilisation PSTN qui connecte la stratégie à l’itinéraire.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Pour exécuter l’applet de commande Test-CsVoicePolicy vous devez d’abord utiliser la cmdlet Get-CsVoicePolicy récupérer une instance de la stratégie de voix à tester ; cette instance doit ensuite être redirigée vers test-CsVoicePolicy. Par exemple :

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

Notez que cette commande, qui n’utilise pas Get-CsVoicePolicy pour récupérer une instance de stratégie de voix, échoue :

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

Si vous souhaitez vérifier toutes les stratégies de voix sur un numéro de téléphone spécifié, utilisez une commande semblable à celle-ci :

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

Notez que le TargetNumber doit être spécifié à l’aide du format E. 164. Test-CsVoicePolicy n’essaie pas de normaliser ou de traduire les numéros de téléphone au format E. 164.

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande Test-CsVoicePolicy.

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si la stratégie de voix peut trouver un itinéraire de communications vocales correspondant et une utilisation PSTN correspondante, l’itinéraire et l’utilisation seront affichés à l’écran :

FirstMatchingRoute MatchingUsage

\------------------ -------------

RedmondVoiceRoute RedmondPstnUsage

Si un itinéraire de communications vocales approprié ou une utilisation PSTN appropriée est introuvable, les valeurs de propriétés vides s’affichent à l’écran :

FirstMatchingRoute MatchingUsage

\------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Si Test-CsVoicePolicy ne renvoie pas de correspondance, cela signifie que la stratégie de voix ne partage pas une utilisation PSTN avec un itinéraire de communications vocales. Pour vérifier que, utilisez une cmdlet semblable à la suivante pour vérifier que les utilisations PSTN affectées à la stratégie de voix :

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

Ensuite, exécutez la commande suivante pour déterminer les utilisations RTC attribuées à chacun de vos itinéraires vocaux :

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

Si vous voyez des correspondances (c’est-à-dire, si vous voyez un ou plusieurs itinéraires vocaux qui partagent au moins une utilisation PSTN avec votre stratégie de voix), vous devez exécuter l’applet de commande Test-CsVoiceRoute pour vérifier que l’itinéraire des communications vocales peut composer le numéro de téléphone fourni.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Test-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

