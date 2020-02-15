---
title: 'Lync Server 2013 : test de la configuration des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2894d61a4dabd174315e24a225392bde7a893300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a>Tester la configuration de la voix dans Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-applet csvoicetestconfiguration. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Lync Server inclut plusieurs applets de commande Windows PowerShell (telles que test-CsVoiceRoute et test-CsVoicePolicy, test-applet cstrunkconfiguration) qui vous permettent de vérifier que les composants individuels de votre infrastructure voix entreprise-itinéraires vocaux, voix les stratégies, les jonctions SIP fonctionnent comme prévu.

Bien qu’il soit important d’utiliser la voix entreprise, tous les éléments individuels fonctionnent : il est possible de disposer d’un itinéraire de communications vocales valide, d’une stratégie de voix valide et d’une jonction SIP valide, tout en permettant aux utilisateurs de ne pas passer ou recevoir des appels téléphoniques. De ce fait, Lync Server offre également la possibilité de créer des configurations de test vocales. Les configurations de test vocales représentent des scénarios de voix entreprise courants : vous pouvez spécifier des éléments tels que l’itinéraire des communications vocales, une stratégie de voix et un plan de numérotation, puis vérifier que ces éléments individuels fonctionnent ensemble pour fournir un service téléphonique. En outre, vous pouvez valider vos attentes dans un scénario donné. Par exemple, supposons que vous vous attendiez à ce que la combinaison du plan de numérotation A et de la stratégie de voix B entraîne l’acheminement des appels par le biais de l’itinéraire des communications vocales C. Vous pouvez entrer l’itinéraire des communications vocales C comme ExpectedRoute. Lorsque vous exécutez le test, si l’itinéraire vocal C n’est pas employé, le test est marqué comme ayant échoué.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Avant de tester les collections de configuration des communications vocales à l’aide de Windows PowerShell, vous devez d’abord utiliser la cmdlet Get-applet csvoicetestconfiguration pour récupérer une instance de ces paramètres de configuration. Cette instance doit ensuite être redirigée vers le test-applet csvoicetestconfiguration. Par exemple :

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Pour valider tous les paramètres de configuration des tests vocaux en même temps, utilisez plutôt cette commande :

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande test-applet csvoicetestconfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

L’applet de commande test-applet csvoicetestconfiguration signale si un test a échoué ou réussi, et fournit des informations supplémentaires sur chaque test réussi, comme la règle de traduction, l’itinéraire de communications vocales et l’utilisation PSTN utilisée pour effectuer la tâche :

Résultat : opération réussie

TranslatedNumber : + 15551234

MatchingRule : description =; Modèle = ^ (\\d{4}) $; Translation = + 1\\d ; Name = test ; IsInternalExtension = false

FirstMatchingRoute : site : Redmond

MatchingUsage : local

Si le test échoue, le résultat est signalé comme étant échec :

Résultat : échec

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Étant donné que les tests de configuration des tests vocaux testent plusieurs éléments différents, notamment les stratégies de voix, les plans de numérotation, les itinéraires de communications vocales, etc., il existe plusieurs facteurs qui peuvent entraîner l’échec d’un test. Si un test échoue, la première étape consiste à passer en revue les paramètres de configuration eux-mêmes à l’aide de la cmdlet Get-applet csvoicetestconfiguration :

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

Si les paramètres semblent être configurés correctement, réexécutez le test en incluant le paramètre Verbose :

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Le paramètre Verbose fournit un compte pas à pas de chaque action effectuée par test-applet csvoicetestconfiguration, comme illustré dans l’exemple suivant :

VERBOSe : chargement du plan de numérotation : « global »

VERBOSe : chargement de la stratégie de voix : « RedmondDialPlan »

Ce compte pas à pas peut fournir un indice utile quant à l’endroit où le test a échoué. Si ce n’est pas le cas, vous pouvez utiliser d’autres applets de commande Windows PowerShell (par exemple, test-CsVoicePolicy) et méthodiquement commencer à vérifier les composants individuels inclus dans les paramètres de configuration des tests vocaux.

En outre, sachez qu’il est possible qu’un test puisse acheminer un appel et qu’il soit toujours marqué comme ayant échoué ; Cela peut se produire si vous entrez des valeurs pour ExpectedRoute, ExpectedTranslatedNumber et ExpectedUsage, et que ces attentes ne sont pas satisfaites. Par exemple, supposons que vous entriez l’itinéraire des communications vocales C comme itinéraire des communications vocales prévu, mais que le test termine effectivement l’appel à l’aide de l’itinéraire des communications vocales D. Dans ce cas, le test est marqué comme ayant échoué, car l’itinéraire des communications vocales attendu n’a pas été utilisé. Si un test échoue, vous pouvez supprimer les valeurs de ExpectedRoute, ExpectedTranslatedNumber et ExpectedUsage, puis réexécuter le test. Cela vous permettra de déterminer si l’échec de l’appel a échoué, ou si vous attendiez une chose et que vous en recevez une autre.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Test-applet csvoicetestconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

