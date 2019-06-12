---
title: 'Lync Server 2013: accès à l’application Web de test'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d118f019883bd5c0f00295bb92287c9593192a3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-web-app-access-in-lync-server-2013"></a>Test de l’accès à l’application Web dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-06-07_


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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsWebApp. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsWebApp vérifie que les utilisateurs authentifiés peuvent participer à des conférences Lync Server à l’aide de Lync Web App. Lorsque vous exécutez l’applet de contrôle, test-CsWebApp contacte le service de ticket Web pour obtenir des tickets Web pour les utilisateurs spécifiés. Ces tickets servent efficacement d’admission aux conférences de Lync Server. Si les tickets peuvent être récupérés et si les utilisateurs peuvent s’authentifier, testez-CsWebApp puis contactez Lync Server et tentez d’établir des conférences distinctes pour la messagerie instantanée, le partage d’application et la collaboration de données.

Notez que test-CsWebApp vérifie uniquement les API et les connexions utilisées pour créer ces conférences. L’applet de contrôle a pour but de vérifier que Lync Web App peut être utilisé pour créer et rejoindre des conférences. Toutefois, elle ne crée et ne anime pas réellement de conférence.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’applet de contrôle test-CsWebApp peut être exécutée à l’aide d’une paire de comptes de test préconfigurés ou des comptes de deux utilisateurs qui sont activés pour Lync Server. Pour exécuter cette vérification à l’aide de comptes de test, vous devez simplement spécifier le nom de domaine complet du pool de serveurs Lync testé. Par exemple :

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

Pour exécuter ce contrôle à l’aide de comptes d’utilisateurs réels, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte. Vous devez alors inclure ces objets d’informations d’identification et les adresses SIP des deux comptes lors de l’appel de test-CsWebApp:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

Pour plus d’informations, consultez la rubrique d’aide de l’applet de [contrôle test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) . Notez que test-CsWebApp a été déconseillé pour une utilisation sur Lync Server 2013.

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si test-CsWebApp peut joindre les utilisateurs à leurs conférences, l’applet de contrôle renverra le résultat de test réussite:

Nom de domaine complet cible:

Résultat: réussite

Latence: 00:00:00

Message d’erreur:

Diagnostic

Si les utilisateurs ne peuvent pas rejoindre les conférences nécessaires, le résultat du test sera marqué comme ayant échoué. En règle générale, le test-CsWebApp signale également un message d’erreur et un diagnostic détaillés:

Nom de domaine complet (FQDN) cible: atl-cs-001.litwareinc.com

Résultat: échec

Latence: 00:00:00

Message d’erreur: aucun réponse reçu pour le service de ticket Web

Diagnostic: la requête HTTP n’est pas autorisée avec le client

schéma d’authentification «NTLM». L’authentification

l’en-tête reçu du serveur était «Negotiate, NTLM».

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Les échecs de test-CsWebApp impliquent généralement des erreurs d’authentification des utilisateurs. Si test-CsWebApp échoue, vous devez commencer par vérifier que les utilisateurs spécifiés disposent de comptes d’utilisateurs valides et sont activés pour Lync Server. Vous pouvez récupérer les informations sur le compte à l’aide d’une commande similaire à celle-ci:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Si la propriété Enabled n’est pas égale à true ou en cas d’échec de la commande, cela signifie que l’utilisateur ne possède pas de compte Lync Server valide. Vous devez également vérifier que les mots de passe que vous avez fournis à l’applet de contrôle sont valides.

</div>

</div>

<span> </span>

</div>

</div>

</div>

