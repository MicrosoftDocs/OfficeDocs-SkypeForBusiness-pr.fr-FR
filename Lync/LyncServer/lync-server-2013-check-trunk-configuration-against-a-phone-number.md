---
title: 'Lync Server 2013 : vérifier la configuration de la jonction par rapport à un numéro de téléphone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2832af2c038383e0cca9f8cb931ce4b675b44f2b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>Vérifier la configuration de la jonction par rapport à un numéro de téléphone dans Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-applet cstrunkconfiguration. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Les jonctions SIP connectent le réseau voix entreprise interne de Lync Server à l’un des éléments suivants :

  - Le réseau téléphonique commuté (RTC).

  - Un autocommutateur public (PBX).

  - Un contrôleur de frontière de session (SBC).

L’applet de commande test-applet cstrunkconfiguration vérifie qu’un numéro de téléphone (tel qu’il est composé par un utilisateur) peut être converti en réseau E. 164 et acheminé via une jonction SIP spécifiée.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Pour exécuter la cmdlet Test-applet cstrunkconfiguration, vous devez d’abord utiliser la cmdlet Get-applet cstrunkconfiguration pour récupérer une instance de vos paramètres de configuration de jonction SIP ; cette instance est ensuite redirigée vers test-applet cstrunkconfiguration :

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

L’exécution de test-applet cstrunkconfiguration sans exécuter d’abord Get-applet cstrunkconfiguration ne fonctionne pas. Par exemple, cette commande échoue sans renvoyer de données :

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

Si vous avez plusieurs collections de paramètres de configuration de jonction SIP, vous pouvez utiliser une commande semblable à la suivante pour tester simultanément chaque collection avec le même numéro de téléphone :

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande test-applet cstrunkconfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si test-applet cstrunkconfiguration peut émettre un appel au numéro composé, le numéro de téléphone traduit (au format E. 164) et la règle utilisée pour convertir ce numéro de téléphone seront tous les deux affichés à l’écran :

TranslatedNumber MatchingRule

\---------------- ------------

\+12065551219 global/Redmond

Si le test échoue, test-applet cstrunkconfiguration renverra des valeurs de propriété vides :

TranslatedNumber MatchingRule

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Si test-applet cstrunkconfiguration ne renvoie pas une correspondance qui signifie généralement que les paramètres de configuration de jonction en cours de test n’ont pas de règle de conversion de numéros d’appels sortants capable de convertir le numéro composé au format E. 164. Pour récupérer les règles de traduction affectées à une collection de paramètres de configuration de jonction, vous pouvez utiliser une syntaxe similaire à celle-ci :

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

Qui renvoie des informations similaires à celles-ci pour chaque règle de traduction :

Description : numéros de téléphone sans code de pays ou indicatif régional.

Modèle : ^\\+ (\\d\*) $

`Translation : $1`

Nom : NoAreaCode

À ce stade, vous vérifiez la valeur de la propriété Pattern (qui est une chaîne d' [expression régulière](https://go.microsoft.com/fwlink/?linkid=400464) ) pour déterminer si des règles de conversion sont configurées pour gérer le numéro composé. Si ce n’est pas le cas, vous devez modifier l’une des règles existantes (Set-CsOutboundTranslationRule) ou utiliser l’applet de commande New-CsOutboundTranslationRule pour ajouter une nouvelle règle à la collection.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Test-applet cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

