---
title: 'Lync Server 2013 : test de la publication de la présence d’un utilisateur et abonnement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f6dcc7461362129df72eefd0fd1ab3f5dd809b5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a>Test de la publication de présence utilisateur et abonnement à Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Planification de la vérification</p></td>
<td><p>Tous les jours</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsPresence. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Test-CsPresence est utilisé pour déterminer si une paire d’utilisateurs de test peut se connecter à Lync Server, puis échanger des informations de présence. Pour ce faire, l’applet de commande connecte d’abord les deux utilisateurs au système. Si les deux connexions aboutissent, le premier utilisateur test demande à recevoir les informations de présence du deuxième utilisateur. Le deuxième utilisateur publie ces informations et Test-CsPresence vérifie que les informations ont été correctement transmises au premier utilisateur. Après l’échange d’informations de présence, les deux utilisateurs de test sont ensuite déconnectés de Lync Server.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-CsPresence peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou des comptes de deux utilisateurs activés pour Lync Server. Pour exécuter cette vérification à l’aide de comptes de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé. Par exemple :

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

Pour exécuter cette vérification à l’aide de comptes d’utilisateur réels, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte. Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsque vous appelez test-CsPresence :

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si les utilisateurs spécifiés peuvent échanger des informations de présence, vous recevrez une sortie semblable à celle-ci, avec la propriété Result marquée comme **Success :**

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:06.3280315

«

Diagnostique

Si les deux utilisateurs ne peuvent pas échanger les informations de présence, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Erreur : 404, introuvable

Diagnostic : ErrorCode = 4005, source = ATL-CS-001.litwareinc.com,

Raison = l’URI de destination n’est pas activé pour SIP ou ne prend pas

présent.

Microsoft. RTC. signalisation. DiagnosticHeader

Par exemple, la sortie précédente indique que le test a échoué car au moins l’un des deux comptes d’utilisateur n’est pas valide : le compte n’existe pas ou n’a pas été activé pour Lync Server. Vous pouvez vérifier que les comptes existent et déterminer s’ils sont activés pour Lync Server, en exécutant une commande semblable à celle-ci :

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

Si test-CsPresence échoue, vous pouvez réexécuter le test, ce qui inclut le paramètre Verbose :

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, test-CsPresence renvoie un compte pas à pas de chaque action qu’il a tentée lorsqu’il a vérifié la capacité de l’utilisateur spécifié à se connecter à Lync Server. Par exemple :

Accès à la demande d’inscription sur inconnu

Activité « Register » terminée dans le « 0,0345791 » secondes.

Activité « SelfSubscribeActivity » démarrée.

Activité « SelfSubscribeActivity » terminée en « 0,0041174 » secondes.

Activité « SubscribePresence » démarrée.

Activité « SubscribePresence » terminée en « 0,0038764 » secondes.

Activité « PublishPresence » démarrée.

Une exception « la notification de présence n’est pas reçue dans les 25 secondes. » s’est produite ruing Workflow Microsoft. RTC. SyntheticTransactions. workflows. STPresenceWorkflow exécution.

Le fait que la notification de présence n’a pas été reçue dans les 25 secondes peut indiquer que des problèmes réseau empêchent l’échange d’informations.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec de test-CsPresence :

  - Vous avez spécifié un compte d’utilisateur incorrect. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

