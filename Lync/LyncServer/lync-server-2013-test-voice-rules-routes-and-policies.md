---
title: 'Lync Server 2013 : test des règles, des itinéraires et des stratégies de voix'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b903ff4453f15bc22b6715abe27cc045381c0e5b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527851"
---
# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a>Test des règles, des itinéraires et des stratégies de voix dans Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsVoiceUser. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Lorsqu’un utilisateur passe un appel téléphonique, l’itinéraire emprunté par l’appel pour atteindre sa destination dépend à la fois des stratégies et des plans de numérotation attribués à cet utilisateur. À partir de l’adresse SIP d’un utilisateur et d’un numéro de téléphone, l’applet de commande Test-CsVoiceUser vérifie si l’utilisateur en question peut effectuer un appel à ce numéro. Si le test réussit, Test-CsVoiceUser renvoie les éléments suivants :

  - Le nombre est traduit au format E. 164 (basé sur le plan de numérotation de l’utilisateur)

  - Règle de normalisation qui a fourni cette traduction

  - Itinéraire des communications vocales utilisé (en fonction de la priorité de l’itinéraire);

  - L’utilisation téléphonique qui a lié la stratégie de voix de l’utilisateur à l’itinéraire des communications vocales.

Test-CsVoiceUser vous permet de déterminer si un numéro de téléphone spécifique achemine et traduit comme prévu, et peut vous aider à résoudre les problèmes liés aux appels rencontrés par les utilisateurs individuels.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Lors de l’exécution de l’applet de commande Test-CsVoiceUser, vous devez fournir deux informations : le numéro composé (DialedNumber) et l’identité du compte d’utilisateur testé. Par exemple, cette commande teste la capacité de l’utilisateur qui a l’adresse SIP sip :kenmyer@litwareinc.com à appeler le numéro de téléphone + 1206555-1219 :

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

Le numéro de téléphone doit être mis en forme de la manière dont vous pensez qu’il est composé. Par exemple, si les utilisateurs ne composent généralement pas le 1 avant d’effectuer un appel longue distance, vous devez utiliser ce format :

`-DialedNumber "2065551219"`

Bien entendu, dans ce cas, le test échoue si vous n’avez pas de règle de normalisation qui peut convertir correctement le numéro 2065551219 au format de téléphone E. 164 utilisé par Lync Server. Pour plus d’informations, consultez la rubrique d’aide New-CsVoiceNormalizationRule cmdlet.

Si vous souhaitez exécuter le même test sur chacun de vos comptes d’utilisateur, vous pouvez utiliser une commande semblable à celle-ci :

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande Test-CsVoiceUser.

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si le test est réussi (c’est-à-dire, si l’utilisateur peut effectuer un appel téléphonique vers le numéro spécifié), le résultat affiche des informations telles que le numéro de téléphone traduit et la règle de normalisation correspondante et l’itinéraire des communications vocales :

TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage

\----------------    ------------    ------------------    -------------

\+12065551219 descripti...    LocalRoute local

En raison des limites de l’écran Windows PowerShell, il se peut qu’au moins une partie des informations renvoyées (notamment la description complète de la règle de normalisation correspondante) ne s’affiche pas à l’écran. Si vous êtes intéressé uniquement par la réussite ou l’échec du test, cela n’a pas d’importance. Si vous préférez afficher les détails complets des données renvoyées, redirigez la sortie vers la cmdlet Format-List lors de l’exécution du test :

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

Cela permet d’afficher la sortie dans un format plus facile à lire :

TranslatedNumber : + 12065551219

MatchingRule : description =; Modèle = ^ ( \\ d {11} ) $; Translation = + $1 ;

Nom = préfixe tout ; IsInternalExtension = false

FirsMatchingRoute : LocalRoute

MatchingUsage : local

Si le test échoue, Test-CsVoiceUser renvoie un ensemble vide de valeurs de propriété :

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\---------------- ------------ ------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Il existe un certain nombre de raisons pour lesquelles la cmdlet Test-CsVoiceUser peut échouer : il se peut qu’il n’existe pas de règle de normalisation pouvant traduire le numéro de téléphone fourni. Il peut y avoir des problèmes avec l’itinéraire des communications vocales. Il peut y avoir un problème de configuration avec le plan de numérotation affecté à l’utilisateur en question. Pour cette raison, vous souhaiterez peut-être inclure le paramètre Verbose lorsque vous exécutez l’applet de commande Test-CsVoiceUser :

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

Lorsque la cmdlet verbose est incluse, Test-CsVoiceUser affiche un compte détaillé de toutes les étapes de la procédure de vérification. Par exemple, vous pouvez voir des étapes similaires à celles-ci : 

VERBOSe : localisation de l’utilisateur avec l’identité « sip :kenmyer@litwareinc.com »

VERBOSe : chargement du plan de numérotation : « RedmondDialPlan »

Ces informations supplémentaires peuvent fournir des indications sur les étapes à suivre pour identifier la cause de l’échec. Par exemple, la sortie détaillée indiquée ici nous indique que le plan de numérotation est affecté à l’utilisateur testé RedmondDialPlan. Si le test a échoué, une étape suivante logique consiste à vérifier que RedmondDialPlan peut traduire le numéro de téléphone fourni.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Test-CsVoiceUser](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

