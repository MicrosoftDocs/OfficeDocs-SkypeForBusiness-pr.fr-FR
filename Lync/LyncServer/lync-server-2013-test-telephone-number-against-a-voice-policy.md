---
title: 'Lync Server 2013 : testez le numéro de téléphone en fonction de la politique vocale'
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
ms.openlocfilehash: 37d0c9ae6512cb7755c7ef73e4cfd3e37b92884d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a>Testez le numéro de téléphone en fonction de la politique vocale dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsVoicePolicy. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Possibilité pour les utilisateurs d’entreprise Voice de passer des appels sortants par le biais des charnières de réseau téléphonique commuté (RTC), en grande partie, sur les trois points suivants :

  - La stratégie vocale affectée à l’utilisateur.

  - Les itinéraires vocaux utilisés pour acheminer les appels de Lync Server vers le réseau PSTN.

  - L’utilisation RTC, propriété serveur Lync qui connecte une stratégie vocale à un itinéraire vocal.

L’utilisation RTC est particulièrement importante : il s’agit de la propriété qui connecte une stratégie vocale à un itinéraire vocal. (Une stratégie vocale et un itinéraire vocal sont considérés comme étant connectés s’ils ont au moins une utilisation PSTN en commun.) Les stratégies vocales peuvent être configurées sans spécifier d’utilisation PSTN. Dans ce cas, les utilisateurs qui ont été affectés à cette stratégie ne seront pas en mesure de passer des appels sortants sur le réseau PSTN. De même, les itinéraires vocaux qui n’ont pas au moins une utilisation RTC spécifiée ne seront pas en mesure d’acheminer les appels vers le réseau PSTN.

L’applet de commande test-CsVoicePolicy vérifie qu’une stratégie vocale donnée a une utilisation PSTN et que l’utilisation est partagée par au moins un itinéraire vocal. Si la vérification exécutée par test-CsVoicePolicy réussit, l’applet de commande renvoie le nom du premier itinéraire de voix valide qu’il trouve, ainsi que le nom de l’utilisation RTC qui connecte la stratégie à l’itinéraire.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Pour exécuter l’applet de contrôle de test-CsVoicePolicy, vous devez d’abord utiliser l’applet de contrôle Get-CsVoicePolicy pour récupérer une instance de la stratégie vocale à tester. cette instance doit alors être canalisée vers test-CsVoicePolicy. Par exemple :

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

Notez que cette commande, qui n’utilise pas Get-CsVoicePolicy pour récupérer une instance de la stratégie vocale, ne peut pas :

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

Si vous voulez cocher toutes les stratégies vocales sur un numéro de téléphone spécifié, utilisez une commande semblable à celle-ci :

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

Notez que TargetNumber doit être spécifié en utilisant le format E. 164. Test-CsVoicePolicy ne tente pas de normaliser ou de traduire des numéros de téléphone au format E. 164.

Pour plus d’informations, consultez la documentation d’aide de l’applet de contrôle test-CsVoicePolicy.

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si la stratégie vocale peut trouver un itinéraire vocal correspondant et une utilisation RTC correspondante, l’itinéraire et l’utilisation seront affichés à l’écran :

FirstMatchingRoute MatchingUsage

\------------------ -------------

RedmondVoiceRoute RedmondPstnUsage

Si une voie vocale ou une utilisation PSTN appropriée est introuvable, les valeurs de propriété vides seront affichées à l’écran :

FirstMatchingRoute MatchingUsage

\------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Si test-CsVoicePolicy ne renvoie aucune correspondance qui peut signifier que la stratégie vocale ne partage pas d’utilisation RTC avec un itinéraire vocal. Pour le vérifier, utilisez une applet de commande similaire à celle qui suit pour vérifier que les utilisations RTC attribuées à la stratégie vocale :

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

Ensuite, exécutez la commande suivante pour identifier les utilisations PSTN affectées à chacun de vos itinéraires vocaux :

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

Si vous voyez des correspondances (autrement dit, si vous voyez un ou plusieurs itinéraires vocaux qui partagent au moins une utilisation PSTN avec votre stratégie vocale), vous devez exécuter l’applet de commande test-CsVoiceRoute pour vérifier que l’itinéraire vocal peut composer le numéro de téléphone fourni.

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

