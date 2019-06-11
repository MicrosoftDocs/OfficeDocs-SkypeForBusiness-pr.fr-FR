---
title: 'Lync Server 2013: vérifier la configuration de Trunk par rapport à un numéro de téléphone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b667f43e430b5047f72e2d8352f57337f0849055
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>Vérifier la configuration de Trunk par rapport à un numéro de téléphone dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsTrunkConfiguration. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Les ISL SIP connectent le réseau d’entreprise voix interne de Lync Server à l’un des éléments suivants:

  - Le réseau téléphonique public commuté (RTC).

  - Un échange de succursale public IP (PBX).

  - Contrôleur de bordure de session (SBC).

L’applet de contrôle test-CsTrunkConfiguration vérifie qu’un numéro de téléphone (tel qu’un appel) peut être converti en réseau E. 164 et routé sur une ligne SIP spécifiée.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Pour exécuter l’applet de contrôle test-CsTrunkConfiguration, vous devez d’abord utiliser l’applet de contrôle Get-CsTrunkConfiguration pour récupérer une instance de vos paramètres de configuration de Trunk SIP. cette instance est alors canalisée vers test-CsTrunkConfiguration:

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

L’exécution de test-CsTrunkConfiguration sans avoir d’abord exécuté Get-CsTrunkConfiguration ne fonctionne pas. Par exemple, cette commande échoue sans renvoyer de données:

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

Si vous avez plusieurs collections de paramètres de configuration de Trunk SIP, vous pouvez utiliser une commande similaire à celle qui suit pour tester chaque collection sur le même numéro de téléphone:

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Pour plus d’informations, consultez la documentation d’aide de l’applet de contrôle test-CsTrunkConfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si test-CsTrunkConfiguration peut émettre un appel vers le numéro composé, le numéro de téléphone traduit (au format E. 164) et la règle utilisée pour traduire ce numéro de téléphone s’affichent à l’écran.

TranslatedNumber MatchingRule

\---------------- ------------

\+12065551219 global/Redmond

Si le test échoue, test-CsTrunkConfiguration renvoie les valeurs de propriété vides:

TranslatedNumber MatchingRule

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Si test-CsTrunkConfiguration ne renvoie aucune correspondance qui signifie généralement que les paramètres de configuration de Trunk en cours de test ne disposent pas d’une règle de traduction de numéro de téléphone prenant en charge la conversion du numéro numéroté au format E. 164. Pour récupérer les règles de traduction affectées à un ensemble de paramètres de configuration de Trunk, vous pouvez utiliser une syntaxe similaire à celle-ci:

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

Cela renvoie des informations similaires à ce qui suit pour chaque règle de traduction:

Description: numéros de téléphone sans code de pays ou indicatif régional.

Modèle: ^\\+ (\\d\*) $

`Translation : $1`

Nom: NoAreaCode

À ce stade, vous vérifiez la valeur de la propriété Pattern (qui est une chaîne d' [expression régulière](http://go.microsoft.com/fwlink/?linkid=400464) ) pour vérifier si une des règles de traduction est configurée pour gérer le numéro numéroté. Si ce n’est pas le cas, vous devrez modifier une des règles existantes (Set-CsOutboundTranslationRule) ou utiliser l’applet de nouvelle applet de nouveau-CsOutboundTranslationRule pour ajouter une nouvelle règle à la collection.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

