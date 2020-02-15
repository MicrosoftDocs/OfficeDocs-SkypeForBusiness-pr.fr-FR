---
title: 'Lync Server 2013 : test de l’accès à l’application Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a48580561a1a070b44b202e5d49c89261518dafe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42017845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-web-app-access-in-lync-server-2013"></a>Tester l’accès à l’application Web dans Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsWebApp. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande test-CsWebApp vérifie que les utilisateurs authentifiés peuvent participer à des conférences Lync Server à l’aide de Lync Web App. Lorsque vous exécutez l’applet de commande, test-CsWebApp contacte le service de ticket Web pour obtenir des tickets Web pour les utilisateurs spécifiés. Ces tickets agissent efficacement comme des « tickets d’admission » pour la Conférence Lync Server. Si les tickets peuvent être récupérés, et si les utilisateurs peuvent être authentifiés, test-CsWebApp contacte ensuite Lync Server et tente d’établir des conférences distinctes pour la messagerie instantanée, le partage d’application et la collaboration de données.

Notez que test-CsWebApp vérifie simplement les API et les connexions utilisées pour créer ces conférences. L’applet de commande est conçue pour vérifier que Lync Web App peut être utilisé pour créer et rejoindre des conférences. Toutefois, il ne crée pas réellement de conférence.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-CsWebApp peut être exécutée à l’aide d’une paire de comptes de test préconfigurés ou des comptes de deux utilisateurs activés pour Lync Server. Pour exécuter cette vérification à l’aide de comptes de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé. Par exemple :

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

Pour exécuter cette vérification à l’aide de comptes d’utilisateur réels, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte. Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsque vous appelez test-CsWebApp :

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) . Notez que test-CsWebApp était déconseillé pour une utilisation sur Lync Server 2013.

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si test-CsWebApp peut joindre les utilisateurs à leurs conférences, la cmdlet renverra le résultat du test réussite :

Nom de domaine complet cible :

Résultat : opération réussie

Latence : 00:00:00

Message d’erreur :

Diagnostique

Si les utilisateurs ne peuvent pas rejoindre les conférences nécessaires, le résultat du test sera marqué comme étant un échec. En règle générale, test-CsWebApp signale également un message d’erreur détaillé et un diagnostic :

Nom de domaine complet cible : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Message d’erreur : aucune réponse reçue pour le service de ticket Web

Diagnostic : la demande HTTP n’est pas autorisée avec le client

modèle d’authentification « NTLM ». L’authentification

l’en-tête reçu du serveur était « Negotiate, NTLM ».

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Les défaillances test-CsWebApp impliquent généralement des erreurs d’authentification de l’utilisateur. Si test-CsWebApp échoue, vérifiez d’abord que les utilisateurs spécifiés disposent de comptes d’utilisateur valides et sont activés pour Lync Server. Vous pouvez récupérer les informations de compte à l’aide d’une commande semblable à celle-ci :

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Si la propriété Enabled n’a pas la valeur true ou si la commande échoue, cela signifie que l’utilisateur ne dispose pas d’un compte Lync Server valide. Vous devez également vérifier que les mots de passe que vous avez fournis à la cmdlet sont valides.

</div>

</div>

<span> </span>

</div>

</div>

</div>

