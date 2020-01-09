---
title: 'Lync Server 2013 : tester les notifications de transmission vers des téléphones intelligents'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 653becc1cc22abc8b3c04e0ab3d2a2d1260a98d9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a>Tester des notifications de transmission vers des téléphones intelligents dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2017-03-15_


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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsMcxPushNotification. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Le service de notifications de transmission (Apple Send notification service et service de notifications de transmission de messages Microsoft) peut envoyer des notifications relatives à des événements tels que les nouveaux messages instantanés et les nouveaux messages vocaux sur des appareils mobiles tels que les iPhone et les téléphones Windows, même si le client Lync sur ces appareils est actuellement suspendu ou en cours d’exécution en arrière-plan. Le service de notifications d’émission est un service basé sur le Cloud qui s’exécute sur les serveurs Microsoft. Pour tirer parti des notifications de transmission, vous devez être en mesure de vous connecter au centre de notifications de transmission Clearinghouse et de vous y authentifier. L’applet de contrôle test-CsMcxPushNotification permet aux administrateurs de vérifier que les demandes de notifications de transmission peuvent être routées via votre serveur Edge vers le centre de notifications de type Clearinghouse.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Pour tester le service de notifications d’émission, appelez l’applet de contrôle de test-CsMcxPushNotification. Vérifiez que vous spécifiez le nom de domaine complet de votre serveur Edge :

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

Pour plus d’informations, consultez la rubrique d’aide de l’applet de [contrôle test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si test-CsMcxPushNotification réussit l’applet de contrôle, elle renvoie le résultat de test réussite :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : réussite

Latence : 00:00:00

Error

Diagnostic

Si test-CsMcxPushNotification n’est pas en mesure de se connecter au centre de notifications de type Clearinghouse, l’applet de connexion ne renverra généralement aucun résultat de test d’échec En règle générale, la commande échoue entièrement. Par exemple :

Test-CsMcxPushNotification : une réponse de 504 (délai d’expiration du serveur) a été reçue du réseau et l’opération a échoué. Pour plus d’informations, consultez les détails de l’exception.

À la ligne : 1 car : 27

\+Test-CsMcxPushNotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com

\+CategoryInfo : OperationStopped : ( :) \[Test-CsMcxPushNotification\], FailureResponseException

\+FullyQualifiedErrorId : WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Si le service de notifications de transmission ne fonctionne pas, ce qui signifie généralement que vous rencontrez des problèmes de communication avec votre serveur Edge ou que vous rencontrez des problèmes pour communiquer avec le centre de suppression Si vous rencontrez des problèmes lorsque vous exécutez test-CsMcxPushNotification, la première chose à faire est de vérifier que votre serveur Edge fonctionne correctement. Pour cela, vous pouvez utiliser l’applet de contrôle CsAVEdgeConnectivity :

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Ce contrôle vérifie qu’un utilisateur spécifié peut se connecter au serveur Edge.

Si le serveur Edge semble fonctionner correctement, il se peut que vous ne puissiez pas vous connecter au centre de notifications de transmission Clearinghouse. En règle générale, cela signifie généralement que vous n’avez pas configuré l’URI de Clearinghouse correctement ou que vous n’avez pas d’enregistrement SRV DNS qui pointe vers cette URL. Vous pouvez vérifier que l’URI est défini sur la valeur correcte (sip :push@push.lync.com) en exécutant la commande suivante :

    Get-CsMcxConfiguration

Si la propriété PushNotificationProxyUri est définie sur une valeur autre que sip :push@push.lync.com, vous pouvez corriger ce problème à l’aide de l’applet de action Set-McxConfiguration. Par exemple, cette commande définit correctement l’URI au sein de votre organisation :

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) .

Si l’URI est configuré correctement, l’étape suivante consiste à vérifier que vous disposez d’un enregistrement DNS SRV qui est résolu vers votre domaine SIP et votre serveur Edge. Pour plus d’informations sur la configuration de ces enregistrements, voir la rubrique d’aide configuration requise pour la mobilité. Notez que le message d’erreur suivant indique généralement un problème avec les enregistrements DNS :

Une réponse de 504 (délai d’expiration du serveur) a été reçue du réseau et l’opération a échoué. Pour plus d’informations, consultez les détails de l’exception.

Il est également possible que test-CsMcxConfiguration ne fonctionne pas avec ce message d’erreur :

Test-CsMcxPushNotification : la demande de notifications de type pousser a été refusée.

À la ligne : 1 car : 27

\+Test-CsMcxPushNotification\<\<\<\<

\+CategoryInfo : OperationStopped : ( :) \[Test-CsMcxPushNotification\], SyntheticTransactionException

\+FullyQualifiedErrorId : WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet

Le message « la demande de notifications de transmission a été refusée » s’affiche généralement si vous avez activé le filtrage d’URL et que vous bloquez les préfixes http : et https :. Vous pouvez déterminer les préfixes bloqués à l’aide d’une commande semblable à ce qui suit :

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

Si http : ou https : apparaissent dans les résultats, vous devez les supprimer de la liste des préfixes bloqués pour que les notifications de transmission fonctionnent. Pour cela, vous pouvez utiliser des commandes similaires à celles-ci :

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

