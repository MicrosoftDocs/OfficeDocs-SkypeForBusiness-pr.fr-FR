---
title: 'Lync Server 2013 : tester l’accès anonyme à l’application Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5001b7c318c9d165d9e20bbcde83e7f34b3b7cc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a>Tester l’accès aux applications Web anonymes dans Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsWebAppAnonymous. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande test-CsWebAppAnonymous vérifie qu’un utilisateur anonyme peut participer à des conférences Lync Server à l’aide de Lync Web App. Lorsque vous exécutez l’applet de commande, test-CsWebAppAnonymous contacte le service de ticket Web pour obtenir un ticket Web pour l’utilisateur anonyme. Si l’applet de commande réussit à obtenir ce ticket, test-CsWebAppAnonymous contacte ensuite Lync Server et tente d’établir des conférences distinctes pour la messagerie instantanée, le partage d’application et la collaboration de données.

Notez que test-CsWebAppAnonymous vérifie uniquement les API et les connexions utilisées pour créer ces conférences. L’applet de commande ne crée pas réellement de conférence.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-CsWebAppAnonymous peut être exécutée à l’aide d’une paire de comptes de test préconfigurés ou des comptes de deux utilisateurs activés pour Lync Server. Pour exécuter cette vérification à l’aide de comptes de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé. Par exemple :

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

Pour exécuter cette vérification à l’aide de comptes d’utilisateur réels, vous devez créer deux objets d’informations d’identification Lync Server Management Shell (objets qui contiennent le nom de compte et le mot de passe) pour chaque compte. Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsque vous appelez test-CsWebAppAnonymous :

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande test-CsWebAppAnonymous. Notez que test-CsWebAppAnonymous est déconseillé pour une utilisation sur Lync Server 2013.

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si test-CsWebAppAnonymous peut joindre l’utilisateur anonyme à ses conférences, la cmdlet renverra le résultat du test réussite :

Nom de domaine complet cible :

Résultat : opération réussie

Latence : 00:00:00

Message d’erreur :

Diagnostique

Si l’utilisateur anonyme ne peut pas rejoindre les conférences nécessaires, le résultat du test sera marqué comme étant un échec. En règle générale, test-CsWebAppAnonymous signale également un message d’erreur détaillé et un diagnostic :

Nom de domaine complet cible : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:05.9746266

Message d’erreur : aucune réponse reçue pour le service de ticket Web

Diagnostic : la demande HTTP n’est pas autorisée avec le client

modèle d’authentification « NTLM ». L’authentification

l’en-tête reçu du serveur était « Negotiate, NTLM ».

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Les échecs de test-CsWebAppAnonymous se produisent généralement autour des erreurs d’authentification de l’utilisateur : vous devez exécuter le test à l’aide d’un compte d’utilisateur valide même si l’applet de commande vérifie la capacité d’un utilisateur anonyme à se connecter à Lync Server. Si test-CsWebAppAnonymous échoue, vérifiez que l’utilisateur spécifié a un compte d’utilisateur de Lync Server valide. Vous pouvez récupérer les informations de compte Lync Server à l’aide d’une commande semblable à celle-ci :

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Si la propriété Enabled n’a pas la valeur true ou si la commande échoue, cela signifie que l’utilisateur ne dispose pas d’un compte Lync Server valide.

Vous devez également vérifier que le mot de passe que vous avez fourni lors de l’exécution de l’applet de commande est un mot de passe valide.

Les problèmes de configuration avec Office Web Apps Server peuvent également entraîner l’échec de test-CsWebAppAnonymous ; ce sera souvent le cas si vous recevez le diagnostic suivant :

La demande HTTP n’est pas autorisée avec le modèle d’authentification client « NTLM ». L’en-tête d’authentification reçu du serveur était « Negotiate, NTLM ».

Pour plus d’informations sur le diagnostic et la résolution des problèmes liés à Office Web Apps Server, voir le billet de blog [Office Web Apps server 2013-les ordinateurs sont toujours signalés comme défectueux](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).

</div>

</div>

<span> </span>

</div>

</div>

</div>

