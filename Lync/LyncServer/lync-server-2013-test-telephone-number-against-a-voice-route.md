---
title: 'Lync Server 2013 : test du numéro de téléphone par rapport à un itinéraire des communications vocales'
description: 'Lync Server 2013 : test du numéro de téléphone par rapport à un itinéraire des communications vocales.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 789f4a538a992a72abf61f4c1fbdb98370f2e643
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563390"
---
# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>Tester le numéro de téléphone par rapport à un itinéraire des communications vocales dans Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsVoiceRoute. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Les itinéraires des communications vocales fonctionnent avec les stratégies de voix pour acheminer les appels voix entreprise vers le réseau RTC. Chaque itinéraire des communications vocales inclut une expression régulière (un modèle numérique) qui identifie les numéros de téléphone qui seront acheminés via un itinéraire de communications vocales donné : l’itinéraire sera en mesure de gérer les numéros de téléphone qui correspondent à cette expression régulière. Par exemple, un itinéraire des communications vocales peut avoir une expression régulière qui lui permet de gérer n’importe quel nombre à 10 chiffres. Cela signifie que l’itinéraire peut traiter un numéro de téléphone tel que celui-ci :

  - 2065551219

L’itinéraire ne sera pas en mesure de gérer l’un ou l’autre des deux nombres suivants, aucun n’ayant 10 chiffres :

  - 5551219

  - 12065551219

L’applet de commande Test-CsVoiceRoute vérifie si un itinéraire de communications vocales donné peut acheminer un numéro de téléphone spécifié.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La vérification de la capacité d’un itinéraire des communications vocales à acheminer un numéro de téléphone spécifié est un processus en deux étapes. Tout d’abord, vous devez utiliser l’applet de commande Get-CsVoiceRoute pour retourner une instance de cet itinéraire de communications vocales, puis utiliser la cmdlet Test-CsVoiceRoute pour vérifier la capacité de cet itinéraire à gérer le numéro de téléphone cible. Par exemple, cette commande vérifie si l’itinéraire de communications vocales RedmondVoiceRoute peut acheminer le numéro de téléphone 2065551219 :

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

Notez que le numéro de téléphone doit être tapé comme vous souhaitez que les utilisateurs composent ce numéro. Par exemple, si vous ne prévoyez pas que les utilisateurs doivent inclure le code du pays et l’indicatif régional lors de la numérotation, utilisez une syntaxe similaire à celle-ci :

`-TargetNumber "5551219"`

Dans ce cas, le numéro cible exclut le code du pays et l’indicatif régional.

Pour utiliser une commande unique afin de tester tous les itinéraires des communications vocales par rapport à un numéro cible spécifié, utilisez une syntaxe semblable à celle-ci :

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande Test-CsVoiceRoute.

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si l’itinéraire des communications vocales peut acheminer le numéro de téléphone cible, la cmdlet Test-CsVoiceRoute renvoie simplement la valeur true :

MatchesPattern

\--------------

Vrai

Cela signifie que le routage peut gérer des nombres similaires au numéro cible. Si l’itinéraire des communications vocales ne peut pas gérer le numéro cible, Test-CsVoiceRoute renvoie la valeur false :

MatchesPattern

\--------------

False

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Lors du test des itinéraires des communications vocales, « échec » est un terme relatif. Dans ce cas, cela ne signifie pas que l’itinéraire est quelque peu « brisé »; à la place, il signifie simplement que l’itinéraire ne peut pas gérer le numéro cible. Cela peut être dû à une configuration incorrecte de l’itinéraire des communications vocales. Cela peut également signifier que l’itinéraire n’était jamais destiné à gérer les numéros à l’aide de ce modèle. Par exemple, si vous ne souhaitez pas acheminer les appels vers d’autres pays sur un itinéraire donné, celui-ci peut être configuré pour refuser tous les numéros de téléphone incluant un code pays. Si Test-CsVoiceRoute renvoie la valeur false lorsque vous attendiez qu’il renvoie la valeur true, vérifiez que vous avez tapé correctement le numéro cible. Si vous l’avez fait, utilisez une commande semblable à celle-ci pour afficher les NumberPattern configurés pour l’itinéraire :

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Test-CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

