---
title: 'Lync Server 2013 : test de la capacité des utilisateurs mobiles à échanger des messages instantanés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5885ed34fd28f06b9a7d8c4f95abc29d3b5e147
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a>Tester la capacité des utilisateurs mobiles à échanger des messages instantanés dans Lync Server 2013

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
<td><p>Tous les mois</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsMcxP2PIM. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Le service de mobilité permet aux utilisateurs d’appareils mobiles d’effectuer les opérations suivantes :

1.  Échanger des messages instantanés et des informations de présence.

2.  Stockez et récupérez les messages vocaux en interne au lieu de leur fournisseur sans fil.

3.  Tirez parti des fonctionnalités de Lync Server, telles que l’appel via le bureau et la Conférence rendez-vous.

L’applet de commande test-CsMxcP2PIM offre un moyen rapide et simple de vérifier que les utilisateurs peuvent utiliser le service de mobilité pour échanger des messages instantanés.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Pour exécuter ce test, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte. Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsque vous appelez test-CsMcxP2PIM :

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si les deux utilisateurs de test peuvent échanger des messages instantanés à l’aide du service de mobilité, la fonction test-CsMcxP2PIM renverra la réussite du test :

Nom de domaine complet cible : atl-cs-001.litwareinc.com

URI cible :http://atl-cs-001.litwareinc.com:443/mcx

Résultat : opération réussie

Latence : 00:00:00

Message d’erreur :

Diagnostique

Si le test échoue, le résultat est défini sur échec et un message d’erreur détaillé et un diagnostic s’affichent :

Nom de domaine complet cible : atl-cs-001.litwareinc.com

URI cible :https://atl-cs-001.litwareinc.com:443/mcx

Résultat : échec

Latence : 00:00:00

Message d’erreur : aucune réponse reçue pour le service de ticket Web.

Exception interne : la demande HHTP n’est pas autorisée avec

schéma de négociation client « NTLM ». L’authentification

l’en-tête reçu du serveur était « Negotiate, NTLM ».

Exception interne : le serveur distant a renvoyé une erreur :

(401) non autorisé.

Diagnostique

Diagnostic interne : X-MS-Server-Fqdb : ATL-CS-

001.litwareinc.com

Cache-Control : Private

Content-type : text/html ; charset = UTF-8.

Serveur : Microsoft-IIS/8.5

WWW-Authenticate : Negotiate, NTLM

X-alimenté par : ASP.NET

X-Content-type-options : nosniffer

Date : Wed, 28 mai 2014 19:16:05 GMT

Longueur de contenu : 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Si test-CsMcxP2PIM échoue, la première étape consiste à vérifier que le service de mobilité est opérationnel. Vous pouvez effectuer cette opération à l’aide d’un navigateur Web pour vérifier que l’URL du service de mobilité de votre pool Lync Server est accessible. Par exemple, cette commande vérifie l’URL du pool atl-cs-001.litwareinc.com :

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

Si le service de mobilité semble être en cours d’exécution, vérifiez que vos deux utilisateurs test ont des comptes Lync Server valides. Vous pouvez récupérer les informations de compte à l’aide d’une commande semblable à celle-ci :

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Si la propriété Enabled n’a pas la valeur true ou si la commande échoue, cela signifie que l’utilisateur ne dispose pas d’un compte Lync Server valide.

Vous devez également vérifier que l’utilisateur est activé pour la mobilité. Pour ce faire, commencez par déterminer la stratégie de mobilité affectée au compte :

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

Une fois que vous avez déterminé le nom de la stratégie, utilisez la cmdlet Get-CsMobilityPolicy pour vérifier que la stratégie en question (par exemple, RedmondMobilityPolicy) a la propriété EnableMobility définie sur true :

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Si vous recevez un message d’erreur avec des en-têtes d’authentification, cela signifie que vous n’avez pas spécifié de compte d’utilisateur valide. Vérifiez le nom d’utilisateur et le mot de passe, puis recommencez le test. Si vous êtes convaincu que le compte d’utilisateur est valide, utilisez la cmdlet Get-CsWebServiceConfiguration et vérifiez la valeur de la propriété UseWindowsAuth. Cela vous permettra de savoir quelles méthodes d’authentification sont activées dans votre organisation. Pour plus d’informations sur la résolution des problèmes liés au service de mobilité, voir le billet de blog [Troubleshooting External Lync Mobility connectivity problems Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

