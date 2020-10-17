---
title: 'Lync Server 2013 : test de la messagerie à l’aide de XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79af6165da1c8d5093912f36413ef98812226cbc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518991"
---
# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a>Test de la messagerie à l’aide de XMPP dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-11-03_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Planification de la vérification</p></td>
<td><p>Journalière</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-CsXmppIM</strong> . Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Le protocole XMPP (Extensible Messaging and Presence Protocol) est un protocole de communication standard (fondé sur XML) utilisé pour envoyer des messages sur Internet. XMPP a été initialement nommé Jabber, et est pris en charge par plusieurs applications de messagerie et de communication Internet, telles que Google Talk et Facebook chat. L’applet de commande **test-CsXmppIM** vérifie qu’un utilisateur peut échanger des messages instantanés avec un utilisateur sur un réseau XMPP. Notez que pour que ce test réussisse, vous devez disposer d’une adresse SIP valide pour l’utilisateur XMPP et que l’adresse SIP doit se trouver sur un réseau configuré en tant que partenaire XMPP autorisé.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’exemple suivant vérifie les fonctionnalités de messagerie instantanée XMPP pour le pool atl-cs-001.litwareinc.com. Cette commande fonctionne uniquement si les utilisateurs de test sont définis pour le pool atl-cs-001.litwareinc.com. Si c’est le cas, la commande détermine si le premier utilisateur test peut envoyer un message instantané XMPP à un utilisateur disposant de l’adresse SIP adelaney@contoso.com.

Si les utilisateurs de test ne sont pas définis, la commande échoue, car elle ne peut pas identifier l’utilisateur sous lequel se connecter. Si vous n’avez pas défini les utilisateurs de test pour un pool, vous devez inclure le paramètre UserSipAddress et les informations d’identification de l’utilisateur que la commande doit utiliser lors de la tentative de connexion.

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

Les commandes présentées dans l’exemple suivant testent la capacité d’un utilisateur spécifique (litwareinc \\ Pilar) à se connecter pour envoyer un message instantané XMPP à l’utilisateur adelaney@contoso.com. Pour ce faire, la première commande de l’exemple utilise l’applet de commande Get-Credential pour créer un objet d’informations d’identification de l’interface de ligne de commande Windows PowerShell qui contient le nom et le mot de passe de l’utilisateur Pilar Ackerman. (Étant donné que le nom de connexion litwareinc \\ Pilar a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell nécessite uniquement que l’administrateur entre le mot de passe du compte Pilar Ackerman.) L’objet Credential qui en résulte est ensuite stocké dans une variable nommée $cred 1.

La deuxième commande vérifie ensuite si cet utilisateur peut se connecter au pool atl-cs-001.litwareinc.com et envoyer le message instantané XMPP. Pour exécuter cette tâche, la cmdlet **test-CsXmppIm** est appelée, avec quatre paramètres : TargetFqdn (le nom de domaine complet (FQDN) du pool de serveurs d’inscriptions); Récepteur (adresse SIP de l’utilisateur auquel le message est adressé); UserCredential (l’objet Windows PowerShell qui contient les informations d’identification de l’utilisateur de Pilar Ackerman); et UserSipAddress (l’adresse SIP qui correspond aux informations d’identification de l’utilisateur fourni).

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si la messagerie instantanée XMPP est correctement configurée, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée with **Success :**

Nom de domaine complet cible : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:02.5361946

Message d’erreur :

Diagnostique

Si les utilisateurs spécifiés ne peuvent pas utiliser la messagerie instantanée XMPP, le résultat est affiché en **panne**et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

AVERTISSEMENT : impossible de lire le numéro de port du serveur d’inscriptions pour le serveur complet

nom de domaine (FQDN). À l’aide du numéro de port de serveur d’inscriptions par défaut. Rogation

System. InvalidOperationException : aucun cluster correspondant n’a été trouvé dans la topologie.

Regardez

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Nom de domaine complet cible : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Message d’erreur : 10060, une tentative de connexion a échoué car la partie connectée

ne répond pas correctement au bout d’un certain temps, ou

échec de la connexion établie car l’hôte connecté a

échec de la réponse de 10.188.116.96:5061

Exception interne : une tentative de connexion a échoué car le

la partie connectée n’a pas répondu correctement après une période de

heure ou échec de la connexion établie car l’hôte connecté

échec de la réponse de 10.188.116.96:5061

Diagnostique

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec **de test-CsXmppIM** :

  - Une valeur de paramètre incorrecte a été fournie. Si ce paramètre est utilisé, les paramètres facultatifs doivent être configurés correctement ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.

  - Cette commande échoue si la configuration de la passerelle XMPP n’est pas configurée correctement ou n’est pas encore déployée.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Set-applet csxmppgatewayconfiguration ne](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

