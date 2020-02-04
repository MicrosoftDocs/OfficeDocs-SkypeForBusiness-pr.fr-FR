---
title: 'Lync Server 2013 : tester la capacité des utilisateurs mobiles à échanger des messages instantanés'
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
ms.openlocfilehash: db5af113c6ea87a700ca824bcef09b525338f4e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a>Testez la capacité des utilisateurs mobiles à échanger des messages instantanés dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsMcxP2PIM. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Le service de mobilité permet aux utilisateurs de périphériques mobiles d’effectuer les opérations suivantes :

1.  Échangez des messages instantanés et des informations de présence.

2.  Stockez et récupérez les messages vocaux en interne plutôt qu’avec leur opérateur sans fil.

3.  Tirez parti des fonctionnalités du serveur Lync, telles que les appels par le biais de tâches et de conférences rendez-vous.

L’applet de contrôle test-CsMxcP2PIM fournit un moyen rapide et facile de vérifier que les utilisateurs peuvent utiliser le service de mobilité pour échanger des messages instantanés.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Pour effectuer ce test, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom et le mot de passe du compte) pour chaque compte. Vous devez alors inclure ces objets d’informations d’identification et les adresses SIP des deux comptes lors de l’appel de test-CsMcxP2PIM :

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

Pour plus d’informations, consultez la rubrique d’aide de l’applet de [contrôle test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si les deux utilisateurs de test peuvent échanger des messages instantanés à l’aide du service de mobilité, le test-CsMcxP2PIM renvoie le résultat réussite du test :

Nom de domaine complet (FQDN) cible : atl-cs-001.litwareinc.com

URI de destination :http://atl-cs-001.litwareinc.com:443/mcx

Résultat : réussite

Latence : 00:00:00

Message d’erreur :

Diagnostic

Si le test échoue, le résultat est défini sur échec et un message d’erreur et un diagnostic détaillés s’affichent :

Nom de domaine complet (FQDN) cible : atl-cs-001.litwareinc.com

URI de destination :https://atl-cs-001.litwareinc.com:443/mcx

Résultat : échec

Latence : 00:00:00

Message d’erreur : aucune réponse n’est reçue pour le service de ticket Web.

Exception interne : la requête HHTP n’est pas autorisée avec

le schéma de négociation du client « NTLM ». L’authentification

l’en-tête reçu du serveur était « Negotiate, NTLM ».

Exception interne : le serveur distant a renvoyé une erreur :

(401) non autorisé.

Diagnostic

Diagnostic interne : X-MS-Server-Fqdb : ATL-CS-

001.litwareinc.com

Cache-contrôle : privé

Type de contenu : texte/html ; charset = UTF-8.

Serveur : Microsoft-IIS/8.5

WWW-authentifier : Negotiate, NTLM

X-par : ASP.NET

X-type de contenu-options : nosniff

Date : Wed, 28 2014 19:16:05 GMT

Longueur du contenu : 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Si test-CsMcxP2PIM échoue, la première étape consiste à vérifier que le service de mobilité est actif et qu’il est en cours d’exécution. Vous pouvez effectuer cette opération à l’aide d’un navigateur Web pour vérifier qu’il est possible d’accéder à l’URL du service de mobilité pour votre pool Lync Server. Par exemple, la commande suivante vérifie l’URL du pool atl-cs-001.litwareinc.com :

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

Si le service de mobilité semble être en cours d’exécution, assurez-vous que les deux utilisateurs de test disposent de comptes Lync Server valides. Vous pouvez récupérer les informations sur le compte à l’aide d’une commande similaire à celle-ci :

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Si la propriété Enabled n’est pas égale à true ou en cas d’échec de la commande, cela signifie que l’utilisateur ne possède pas de compte Lync Server valide.

Vous devez également vérifier que l’utilisateur est activé pour la mobilité. Pour ce faire, vous devez d’abord déterminer la stratégie de mobilité affectée au compte :

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

Lorsque vous connaissez le nom de la stratégie, utilisez l’applet de contrôle Get-CsMobilityPolicy pour vérifier que la stratégie en question (par exemple, RedmondMobilityPolicy) a la propriété EnableMobility définie sur la valeur true :

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Si vous recevez un message d’erreur avec des en-têtes d’authentification, cela signifie souvent que vous n’avez pas spécifié de compte d’utilisateur valide. Vérifiez le nom d’utilisateur et le mot de passe, puis relancez le test. Si vous êtes convaincu que le compte d’utilisateur est valide, utilisez l’applet de contrôle Get-CsWebServiceConfiguration et vérifiez la valeur de la propriété UseWindowsAuth. Cela vous indique les méthodes d’authentification activées au sein de votre organisation. Pour obtenir des conseils supplémentaires sur la résolution des problèmes liés au service de mobilité, voir le billet de blog [résolution des problèmes de connectivité externes Lync Mobility](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

