---
title: 'Lync Server 2013: test de la configuration vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbe9be7e0f7962bbab546822e7ce6cd47e063540
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a>Test de la configuration vocale dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsVoiceTestConfiguration. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Lync Server inclut plusieurs cmdlets Windows PowerShell (par exemple, test-CsVoiceRoute et test-CsVoicePolicy, test-CsTrunkConfiguration) qui vous permettent de vérifier que les éléments individuels de votre infrastructure vocale d’entreprise – itinéraires vocaux, voix les stratégies, les Trunks SIP fonctionnent comme prévu.

S’il est important d’utiliser une voix entreprise pour tous les composants individuels: il est possible d’avoir un itinéraire vocal valide, une politique vocale valide et un Trunk SIP valide, mais les utilisateurs ne peuvent pas passer ou recevoir des appels téléphoniques. Pour cette raison, Lync Server vous permet également de créer des configurations de tests vocaux. Les configurations de tests vocaux représentent des scénarios d’entreprise vocaux communs: vous pouvez spécifier des éléments tels que les itinéraires vocaux, la politique vocale et un plan de numérotation, puis vérifier qu’ils sont en mesure de fonctionner ensemble afin de fournir un service téléphonique. De plus, vous pouvez valider vos attentes dans un scénario donné. Par exemple, supposons que vous vous attendiez que la combinaison du plan de numérotation A et de la stratégie vocale A pour effet d’acheminer les appels sur le routage vocal C. Vous pouvez entrer l’itinéraire vocal C en tant que ExpectedRoute. Lors de l’exécution du test, si l’itinéraire vocal C n’est pas utilisé, le test sera marqué comme ayant échoué.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Avant de tester les collections de configurations vocales à l’aide de Windows PowerShell, vous devez commencer par utiliser l’applet de contrôle Get-CsVoiceTestConfiguration pour récupérer une instance de ces paramètres de configuration. Cette instance doit alors être canalisée vers le test-CsVoiceTestConfiguration. Par exemple :

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Pour valider l’ensemble des paramètres de configuration des tests vocaux en même temps, utilisez cette commande à la place:

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

Pour plus d’informations, consultez la documentation d’aide de l’applet de contrôle test-CsVoiceTestConfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

L’applet de commande test-CsVoiceTestConfiguration indique si un test a échoué ou a abouti, et fournit des informations supplémentaires sur les tests réussis tels que la règle de traduction, l’itinéraire vocal et l’utilisation RTC utilisée pour effectuer la tâche:

Résultat: réussite

TranslatedNumber: + 15551234

MatchingRule: description =; Pattern = ^ (\\d{4}) $; Traduction = + 1\\d; Name = test; IsInternalExtension = false

FirstMatchingRoute: site: Redmond

MatchingUsage: local

Si le test échoue, le résultat est alors signalé comme Fail:

Résultat: échec

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Dans la mesure où le test de configuration de tests vocaux teste plusieurs éléments différents (politiques vocales, plans de numérotation, itinéraires vocaux, etc.), plusieurs facteurs peuvent entraîner l’échec d’un test. En cas d’échec d’un test, vous devez commencer par passer en revue les paramètres de configuration en utilisant l’applet de contrôle Get-CsVoiceTestConfiguration:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

Si les paramètres semblent être correctement configurés, exécutez de nouveau le test en incluant le paramètre Verbose:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Le paramètre Verbose fournit un compte étape par étape de chaque action effectuée par test-CsVoiceTestConfiguration, comme illustré dans cet exemple:

DÉTAILLÉ: Téléchargement d’un plan de numérotation: «global»

DÉTAILLÉ: chargement de la stratégie vocale: «RedmondDialPlan»

Ce compte détaillé peut fournir un indice utile sur l’endroit où le test a réellement échoué. Si ce n’est pas le cas, vous pouvez utiliser d’autres cmdlets Windows PowerShell (par exemple, test-CsVoicePolicy) et procéder de manière méthodique pour vérifier les composants individuels inclus dans les paramètres de configuration des tests vocaux.

Par ailleurs, n’ayez pas d’esprit qu’il est possible qu’un test soit en mesure d’acheminer un appel sans pour autant être marqué comme ayant échoué; Cela peut se produire si vous entrez des valeurs pour ExpectedRoute, ExpectedTranslatedNumber et ExpectedUsage, et que ces attentes ne sont pas satisfaites. Par exemple, supposons que vous entriez l’itinéraire de la voix C comme prévu, mais que le test termine réellement l’appel à l’aide de l’itinéraire vocal D. Dans ce cas, le test sera marqué comme failed, car l’itinéraire vocal attendu n’a pas été utilisé. En cas d’échec d’un test, vous pouvez supprimer les valeurs pour ExpectedRoute, ExpectedTranslatedNumber et ExpectedUsage puis réexécuter le test. Cela vous aide à déterminer si l’appel n’a pas pu être effectué ou si vous attendez une seule personne et que vous en avez réellement reçu une.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Test-CsVoiceTestConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

