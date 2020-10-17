---
title: 'Lync Server 2013 : test de la conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c1980d66649ff465ad251d5b95a9642e5bcd43c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504071"
---
# <a name="testing-persistent-chat-in-lync-server-2013"></a>Test de la conversation permanente dans Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-cspersistentchatmessage ne</strong> . Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande **test-cspersistentchatmessage ne** vérifie qu’une paire d’utilisateurs de test peut échanger des messages à l’aide du service de conversation permanente. Pour ce faire, l’applet de commande enregistre les deux utilisateurs sur Lync Server 2013, connecte les utilisateurs à une salle de conversation permanente, échange une paire de messages, puis quitte la salle de conversation et déconnecte les deux utilisateurs. Notez que les appels à cette cmdlet échouent si vous n’avez pas créé de salles de conversation ou si les deux comptes d’utilisateur test ne sont pas affectés d’une stratégie de conversation permanente qui leur accorde l’accès au service de conversation permanente.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Les commandes illustrées dans l’exemple suivant testent la capacité d’une paire d’utilisateurs (litwareinc \\ Pilar et litwareinc \\ kenmyer) à se connecter à Lync Server 2013, puis à échanger des messages à l’aide du service de conversation permanente. Pour ce faire, la première commande de l’exemple utilise la cmdlet **Get-Credential** pour créer un objet d’informations d’identification de l’interface de ligne de commande Windows PowerShell qui contient le nom et le mot de passe de l’utilisateur Pilar Ackerman. (Étant donné que le nom de connexion, litwareinc \\ Pilar, a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell nécessite uniquement que l’administrateur entre le mot de passe du compte Pilar Ackerman.) L’objet Credentials qui en résulte est ensuite stocké dans une variable nommée $cred 1. La deuxième commande effectue la même action, en retournant cette fois un objet d’identification pour le compte de Ken Myer.

Avec les objets Credential en main, la troisième commande détermine si ces deux utilisateurs peuvent se connecter à Lync Server 2013 et échanger des messages à l’aide de la conversation permanente. Pour effectuer cette tâche, la cmdlet **test-cspersistentchatmessage ne** est appelée à l’aide des paramètres suivants : TargetFqdn (nom de domaine complet du pool de serveurs d’inscriptions); SenderSipAddress (l’adresse SIP pour le premier utilisateur test); SenderCredential (l’objet Windows PowerShell qui contient les informations d’identification pour ce même utilisateur); ReceiverSipAddress (l’adresse SIP de l’autre utilisateur de test); et ReceiverCredential (l’objet Windows PowerShell qui contient les informations d’identification pour l’autre utilisateur de test).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si l’utilisateur spécifié possède une stratégie d’emplacement valide, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success**:

Nom de domaine complet cible : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:00

Message d’erreur :

Diagnostique

Si les utilisateurs spécifiés ne peuvent pas échanger de messages à l’aide du service de conversation permanente, le résultat est affiché en tant que **défaillance**et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

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

échec de la réponse \[ 2001:4898 : E8 : f39e : 5c9a : ad83:81b3:9944 :: \] 5061

Exception interne : une tentative de connexion a échoué car le

la partie connectée n’a pas répondu correctement après une période de

heure ou échec de la connexion établie car l’hôte connecté

n’a pas répondu

\[2001:4898 : E8 : f39e : 5c9a : ad83:81b3:9944 : \] : 5061

Diagnostique

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec **de test-cspersistentchatmessage ne** :

  - Une valeur de paramètre incorrecte a été fournie. Les comptes de test requis peuvent ne pas exister ou avoir été correctement créés.

  - Un problème de réseau est peut-être à l’origine d’un retard inattendu qui a expiré le test.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Grant-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[New-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[Set-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

