---
title: 'Lync Server 2013 : tester les règles vocales, les itinéraires et les stratégies'
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
ms.openlocfilehash: 0c3b2d98846e537a9a416eaabaf6b02627c7273f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a>Tester les règles vocales, les itinéraires et les stratégies dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsVoiceUser. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Lorsqu’un utilisateur effectue un appel téléphonique, le routage de l’appel prend pour atteindre sa destination dépend des stratégies et des plans de numérotation attribués à cet utilisateur. À partir de l’adresse SIP et du numéro de téléphone d’un utilisateur, l’applet de contrôle test-CsVoiceUser vérifie si l’utilisateur en question peut effectuer un appel à ce numéro. Si le test réussit, test-CsVoiceUser renvoie la valeur suivante :

  - Le numéro a été converti au format E. 164 (en fonction du plan de numérotation de l’utilisateur).

  - Règle de normalisation ayant fourni cette traduction

  - La gamme vocale utilisée (en fonction de la priorité de l’itinéraire);

  - L’utilisation du téléphone qui a lié la politique vocale de l’utilisateur à l’itinéraire vocal.

Test-CsVoiceUser vous permet de déterminer si un numéro de téléphone spécifique sera routé et traduit comme prévu et peut vous aider à résoudre les problèmes liés aux appels rencontrés par les utilisateurs individuels.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Lorsque vous exécutez l’applet de contrôle test-CsVoiceUser, vous devez fournir deux éléments d’information : le numéro numéroté (DialedNumber) et l’identité du compte d’utilisateur testé. Par exemple, la commande suivante teste la capacité de l’utilisateur qui dispose de l’adresse sip :kenmyer@litwareinc.com pour effectuer un appel vers le numéro de téléphone + 1206555-1219 :

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

Le numéro de téléphone doit être mis en forme comme vous le souhaitez. Par exemple, si les utilisateurs n’entrent pas en principe le 1er avant de passer un appel longue distance, utilisez ce format :

`-DialedNumber "2065551219"`

Bien entendu, dans ce cas, le test échoue si vous n’avez pas de règle de normalisation qui peut traduire correctement le numéro 2065551219 au format de téléphone E. 164 utilisé par Lync Server. Pour plus d’informations, consultez la rubrique d’aide New-CsVoiceNormalizationRule cmdlet.

Si vous souhaitez exécuter ce test sur chacun de vos comptes d’utilisateurs, vous pouvez utiliser une commande semblable à ce qui suit :

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

Pour plus d’informations, consultez la documentation d’aide de l’applet de contrôle test-CsVoiceUser.

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si le test est effectué avec succès (autrement dit, si l’utilisateur peut effectuer un appel téléphonique au numéro spécifié), la sortie affiche des informations telles que le numéro de téléphone traduit et la règle de normalisation et l’itinéraire vocaux correspondants :

TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage

\----------------    ------------    ------------------    -------------

\+12065551219 descripteur...    LocalRoute local

En raison des limitations de l’écran Windows PowerShell, il est possible que certaines informations renvoyées (en particulier la description complète de la règle de normalisation correspondante) n’apparaissent pas à l’écran. Si vous êtes uniquement intéressé par la réussite ou l’échec du test, cela peut avoir un problème. Si vous préférez afficher tous les détails des données renvoyées, vous pouvez les canalr dans la cmdlet Format-List lors de l’exécution du test :

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

La sortie s’affichera dans un autre format compatible avec le lecteur :

TranslatedNumber : + 12065551219

MatchingRule : description =; Pattern = ^ (\\d{11}) $; Traduction = + $1 ;

Nom = préfixe tout ; IsInternalExtension = faux

FirsMatchingRoute : LocalRoute

MatchingUsage : local

Si le test échoue, test-CsVoiceUser renvoie un ensemble vide de valeurs de propriété :

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\---------------- ------------ ------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

L’applet de commande test-CsVoiceUser peut échouer pour différentes raisons : il est possible qu’il n’y ait pas de règle de normalisation qui peut traduire le numéro de téléphone fourni. Il y a peut-être des problèmes avec l’itinéraire vocal. Il y a peut-être un problème de configuration avec le plan de numérotation affecté à l’utilisateur en question. Pour cette raison, vous souhaiterez peut-être inclure le paramètre Verbose lorsque vous exécutez l’applet de contrôle de test-CsVoiceUser :

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

Lorsque l’applet de demande détaillée est incluse, test-CsVoiceUser émet un compte détaillé de toutes les étapes de la procédure de vérification. Par exemple, il se peut que vous voyiez des étapes semblables à ce qui suit : 

DÉTAILLÉ : localisation de l’utilisateur avec l’identité « sip :kenmyer@litwareinc.com »

DÉTAILLÉ : Téléchargement d’un plan de numérotation : « RedmondDialPlan »

Les informations supplémentaires suivantes peuvent fournir des conseils sur les mesures que vous pouvez prendre pour identifier la cause du problème. Par exemple, la sortie détaillée présentée ici nous indique que l’utilisateur testé a été affecté au plan de numérotation RedmondDialPlan. Si le test échoue, une étape suivante logique consiste à vérifier que RedmondDialPlan peut traduire le numéro de téléphone fourni.

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

