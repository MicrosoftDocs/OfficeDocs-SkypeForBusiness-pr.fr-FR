---
title: 'Lync Server 2013 : test de l’accès des utilisateurs mobiles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83d5be38ecddad1f9388f5e2efb33994b49e4bfd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519211"
---
# <a name="test-mobile-user-access-in-lync-server-2013"></a>Tester l’accès des utilisateurs mobiles dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-06-07_


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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsMcxConference. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Le service de mobilité permet aux utilisateurs d’appareils mobiles d’effectuer les opérations suivantes :

1.  Échanger des messages instantanés et des informations de présence.

2.  Stockez et récupérez les messages vocaux en interne au lieu de leur fournisseur sans fil.

3.  Tirez parti des fonctionnalités de Lync Server, telles que l’appel via le bureau et la Conférence rendez-vous. L’applet de commande Test-CsMcxConference offre un moyen rapide et simple de vérifier que les utilisateurs peuvent participer à des conférences Lync Server à l’aide d’un appareil mobile.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Pour exécuter cette vérification, vous devez créer trois objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte. Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsque vous appelez Test-CsMcxConference comme illustré dans l’exemple suivant :

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si la vérification réussit, Test-CsMcxConference signalera un résultat de test réussi :

Nom de domaine complet cible : atl-cs-001.litwareinc.com

URI cible : http://atl-cs-001.litwareinc.com:443/mcx

Résultat : opération réussie

Latence : 00:00:00

Message d’erreur :

Diagnostique

Si la vérification échoue Test-CsMcxConference signale un résultat de test de défaillance. Ce résultat de test est généralement accompagné d’un message d’erreur détaillé et d’un diagnostic. Par exemple :

Nom de domaine complet cible : atl-cs-001.litwareinc.com

URI cible : https://atl-cs-001.litwareinc.com:443/mcx

Résultat : échec

Latence : 00:00:00

Message d’erreur : aucune réponse reçue pour le service Web-Ticket.

Exception interne : la demande HHTP n’est pas autorisée avec le client

schéma de négociation « NTLM ». En-tête d’authentification reçu

à partir du serveur était « Negotiate ».

Exception interne : le serveur distant a renvoyé une erreur : (401)

Non autorisé.

Diagnostique

Diagnostic interne : X-MS-Server-Fqdb : atl-cs-001.litwareinc.com

Cache-Control : Private

Content-type : text/html ; charset = UTF-8.

Serveur : Microsoft-IIS/8.5

WWW-Authenticate : Negotiate, NTLM

X-alimenté par : ASP.NET

X-Content-type-options : nosniffer

Date : Wed, 28 mai 2014 19:22:19 GMT

Longueur de contenu : 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Si Test-CsMcxConference échoue, vous devez commencer par vérifier que le service de mobilité est en cours d’exécution et qu’il est accessible. Vous pouvez effectuer cette opération à l’aide d’un navigateur Web pour vérifier que l’URL du service de mobilité de votre pool Lync Server est accessible. Par exemple, cette commande vérifie l’URL du pool atl-cs-001.litwareinc.com :

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

S’il est possible d’accéder au service de mobilité, vous devez vérifier que vos utilisateurs test disposent de comptes Lync Server valides. Vous pouvez récupérer les informations de compte à l’aide d’une commande semblable à celle-ci :

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Si la propriété Enabled n’a pas la valeur true ou si la commande échoue, cela signifie que l’utilisateur ne dispose pas d’un compte Lync Server valide. Vous devez également vérifier que chaque compte d’utilisateur est activé pour la mobilité. Pour ce faire, commencez par déterminer la stratégie de mobilité affectée au compte :

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

Une fois que vous avez déterminé le nom de la stratégie, utilisez l’applet de commande Get-CsMobilityPolicy pour vérifier que la propriété EnableMobility de la stratégie en question (par exemple, RedmondMobilityPolicy) a la valeur true :

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Si vous recevez un message d’erreur « en-tête d’authentification » lorsque vous exécutez Test-CsMcxConference cela signifie que vous n’avez pas spécifié de compte d’utilisateur valide, vérifiez le nom d’utilisateur et le mot de passe, puis recommencez le test. Si vous êtes convaincu que le compte d’utilisateur est valide, utilisez l’applet de commande Get-CsWebServiceConfiguration et vérifiez la valeur de la propriété UseWindowsAuth. Cela vous permettra de savoir quelles méthodes d’authentification sont activées dans votre organisation.

Pour plus d’informations sur la résolution des problèmes liés au service de mobilité, voir le billet de blog [Troubleshooting External Lync Mobility connectivity problems Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

