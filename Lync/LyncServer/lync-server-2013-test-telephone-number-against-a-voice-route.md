---
title: 'Lync Server 2013: test du numéro de téléphone par rapport à un itinéraire vocal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed50971c9656d454a44eeee627de95c187ef008f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>Testez le numéro de téléphone par rapport à un itinéraire vocal dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-05-20_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Échéancier de vérification</p></td>
<td><p>Mois</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsVoiceRoute. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Les itinéraires vocaux fonctionnent conjointement avec les politiques vocales pour vous permettre d’acheminer les appels voix entreprise vers le réseau PSTN. Chaque itinéraire vocal inclut une expression régulière (un modèle de nombre) qui identifie les numéros de téléphone qui seront routés par le biais d’un itinéraire vocal donné: l’itinéraire sera en mesure de gérer les numéros de téléphone correspondant à cette expression régulière. Par exemple, un itinéraire vocal peut avoir une expression régulière qui lui permet de gérer tout numéro à 10 chiffres. Cela signifie que l’itinéraire peut gérer un numéro de téléphone tel que celui-ci:

  - 2065551219

L’itinéraire ne peut pas gérer l’un ou l’autre des deux nombres suivants, aucun des deux chiffres:

  - 5551219

  - 12065551219

L’applet de contrôle test-CsVoiceRoute vérifie si un itinéraire vocal donné peut acheminer un numéro de téléphone spécifié.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Le processus en deux étapes permet de vérifier que la capacité d’un itinéraire vocal est d’acheminer un numéro de téléphone spécifié. Tout d’abord, vous devez utiliser l’applet de contrôle Get-CsVoiceRoute pour renvoyer une instance de ce routage, puis vous devez utiliser l’applet de contrôle CsVoiceRoute de test pour vérifier la capacité de cet itinéraire à gérer le numéro de téléphone cible. Par exemple, si vous avez la possibilité de vérifier si l’itinéraire vocal de RedmondVoiceRoute peut acheminer le numéro de téléphone 2065551219:

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

Notez que le numéro de téléphone doit être tapé pour que les utilisateurs puissent composer ce numéro. Par exemple, si vous ne pensez pas que les utilisateurs incluent l’indicatif du pays et l’indicatif de la région lorsque vous composez, utilisez une syntaxe semblable à celle-ci:

`-TargetNumber "5551219"`

Dans le cas présent, le numéro de la cible quitte le code de pays et l’indicatif de la région.

Pour utiliser une seule commande pour tester tous les itinéraires vocaux sur un numéro cible spécifié, utilisez la syntaxe suivante:

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

Pour plus d’informations, consultez la documentation d’aide de l’applet de contrôle test-CsVoiceRoute.

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si l’itinéraire vocal peut router le numéro de téléphone cible, l’applet de contrôle de test-CsVoiceRoute renvoie uniquement la valeur true:

MatchesPattern

\--------------

True

Cela signifie que l’itinéraire peut gérer des nombres similaires au numéro cible. Si l’itinéraire vocal ne peut pas gérer le numéro cible, test-CsVoiceRoute renvoie la valeur false:

MatchesPattern

\--------------

False

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Lors du test des itinéraires vocaux, «Failure» est un terme relatif. Dans ce cas, cela ne veut pas dire que l’itinéraire est quelque peu «rompu», ce qui signifie que l’itinéraire ne peut pas gérer le numéro cible. Cela peut être dû au fait que l’itinéraire vocal a été configuré de manière incorrecte. Cela peut également signifier que l’itinéraire n’était jamais destiné à gérer des nombres à l’aide de ce modèle. Par exemple, si vous ne souhaitez pas acheminer les appels vers d’autres pays sur un itinéraire donné, il est possible que l’itinéraire soit configuré pour rejeter tous les numéros de téléphone incluant un code de pays. Si test-CsVoiceRoute renvoie la valeur faux lorsque vous vous attendiez à ce qu’il retourne vrai, vérifiez que vous avez correctement tapé le numéro cible. Si tel est le cas, utilisez une commande similaire à celle-ci pour afficher le NumberPattern configuré pour l’itinéraire:

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

