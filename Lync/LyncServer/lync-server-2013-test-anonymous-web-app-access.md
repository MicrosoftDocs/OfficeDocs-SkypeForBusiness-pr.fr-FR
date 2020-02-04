---
title: 'Lync Server 2013 : tester l’accès d’une application Web anonyme'
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
ms.openlocfilehash: 8aabac9e106c325b7b1b964e6e594bb2b05ef85c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a>Tester l’accès d’une application Web anonyme dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsWebAppAnonymous. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsWebAppAnonymous vérifie qu’un utilisateur anonyme peut participer à des conférences Lync Server à l’aide de Lync Web App. Lorsque vous exécutez l’applet de contrôle, test-CsWebAppAnonymous contacte le service de ticket Web pour obtenir un ticket Web pour l’utilisateur anonyme. Si l’applet de demande réussit à obtenir ce ticket, test-CsWebAppAnonymous contacte alors Lync Server et tente d’établir des conférences distinctes pour la messagerie instantanée, le partage d’application et la collaboration de données.

Notez que test-CsWebAppAnonymous vérifie uniquement les API et les connexions utilisées pour créer ces conférences. Le cmdlet ne crée et ne fait pas de conférences.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’applet de contrôle test-CsWebAppAnonymous peut être exécutée à l’aide d’une paire de comptes de test préconfigurés ou des comptes de deux utilisateurs qui sont activés pour Lync Server. Pour exécuter cette vérification à l’aide de comptes de test, vous devez simplement spécifier le nom de domaine complet du pool de serveurs Lync testé. Par exemple :

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

Pour exécuter cette vérification à l’aide de comptes d’utilisateurs réels, vous devez créer deux objets d’informations d’identification Lync Server Management Shell (objets contenant le nom de compte et le mot de passe) pour chaque compte. Vous devez alors inclure ces objets d’informations d’identification et les adresses SIP des deux comptes lors de l’appel de test-CsWebAppAnonymous :

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

Pour plus d’informations, consultez la rubrique d’aide de l’applet de contrôle test-CsWebAppAnonymous. Notez que test-CsWebAppAnonymous est déconseillé pour une utilisation sur Lync Server 2013.

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si test-CsWebAppAnonymous peut rejoindre l’utilisateur anonyme dans ses conférences, l’applet de contrôle renverra le résultat de test réussite :

Nom de domaine complet cible :

Résultat : réussite

Latence : 00:00:00

Message d’erreur :

Diagnostic

Si l’utilisateur anonyme ne peut pas participer aux conférences nécessaires, le résultat du test sera marqué comme ayant échoué. En règle générale, le test-CsWebAppAnonymous signale également un message d’erreur et un diagnostic détaillés :

Nom de domaine complet (FQDN) cible : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:05.9746266

Message d’erreur : aucun réponse reçu pour le service de ticket Web

Diagnostic : la requête HTTP n’est pas autorisée avec le client

schéma d’authentification « NTLM ». L’authentification

l’en-tête reçu du serveur était « Negotiate, NTLM ».

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Les échecs de test-CsWebAppAnonymous font généralement appel à des erreurs d’authentification de l’utilisateur : vous devez exécuter le test à l’aide d’un compte d’utilisateur valide, même si la cmdlet vérifie la capacité d’un utilisateur anonyme à se connecter à Lync Server. En cas d’échec de test-CsWebAppAnonymous, vous devez vérifier que l’utilisateur spécifié a valide un compte d’utilisateur de Lync Server. Vous pouvez récupérer les informations de compte de Lync Server en utilisant une commande similaire à celle-ci :

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Si la propriété Enabled n’est pas égale à true ou en cas d’échec de la commande, cela signifie que l’utilisateur ne possède pas de compte Lync Server valide.

Vous devez également vérifier que le mot de passe que vous avez fourni lorsque vous exécutez l’applet de contrôle est un mot de passe valide.

Les problèmes de configuration liés à Office Web Apps Server peuvent également entraîner l’échec de test-CsWebAppAnonymous ; C’est souvent le cas si vous recevez le code de diagnostic suivant :

La requête HTTP n’est pas autorisée avec le schéma d’authentification du client « NTLM ». L’en-tête d’authentification reçu du serveur était « Negotiate, NTLM ».

Pour plus d’informations sur le diagnostic et la résolution des problèmes liés au serveur Office Web Apps, voir le billet de blog [Office Web Apps server 2013-les ordinateurs sont toujours signalés comme défectueux](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).

</div>

</div>

<span> </span>

</div>

</div>

</div>

