---
title: 'Lync Server 2013 : test de conversation permanente'
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
ms.openlocfilehash: 78e756de75dda7d7b0a96d9a49233818a5c86576
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a>Test de conversation permanente dans Lync Server 2013

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
<td><p>Échéancier de vérification</p></td>
<td><p>Jour</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande <strong>test-CsPersistentChatMessage</strong> . Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de **contrôle test-CsPersistentChatMessage** vérifie qu’une paire d’utilisateurs de test peut échanger des messages à l’aide du service Chat permanent. Pour ce faire, l’applet de connexion enregistre les deux utilisateurs sur Lync Server 2013, connecte les utilisateurs à une salle de conversation permanente, échange une paire de messages, puis quitte la salle de conversation et déconnecte les deux utilisateurs. Notez que les appels à cette applet de contrôle échoueront si vous n’avez pas créé de salles de conversation ou si les deux comptes d’utilisateurs test ne disposent pas d’une stratégie de discussion persistante lui permettant d’accéder au service de chat permanent.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Les commandes indiquées dans l’exemple suivant testent la capacité d’une paire d’utilisateurs (\\litwareinc Pilar et\\litwareinc kenmyer) à se connecter à Lync Server 2013, puis échangent des messages à l’aide du service Chat permanent. Pour cela, la première commande de l’exemple utilise l’applet de commande **Get-Credential** pour créer un objet d’information d’interface de ligne de commande Windows PowerShell contenant le nom et le mot de passe de l’utilisateur Pilar Arès. (Dans la mesure où le nom\\de connexion, litwareinc Pilar, a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell n’exige que l’administrateur entre le mot de passe du compte Arès Pilar.) L’objet Credentials obtenu est ensuite stocké dans une variable nommée $cred 1. La deuxième commande effectue la même opération en renvoyant alors un objet Credential pour le compte Ken Myer.

Avec les objets d’information d’identification disponibles, la troisième commande détermine si ces deux utilisateurs peuvent se connecter à Lync Server 2013 et échanger des messages à l’aide d’une conversation permanente. Pour effectuer cette tâche, l’applet de commande **test-CsPersistentChatMessage** est appelée en utilisant les paramètres suivants : TargetFqdn (nom de domaine complet (FQDN) du pool d’inscriptions); SenderSipAddress (adresse SIP pour le premier utilisateur test); SenderCredential (objet Windows PowerShell contenant les informations d’identification pour ce même utilisateur); ReceiverSipAddress (adresse SIP de l’autre utilisateur du test); et ReceiverCredential (objet Windows PowerShell contenant les informations d’identification pour l’autre utilisateur de test).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si l’utilisateur spécifié dispose d’une stratégie d’emplacement valide, vous recevrez une sortie semblable à ce qui suit, avec la propriété Result marquée comme **réussie**:

Nom de domaine complet (FQDN) cible : atl-cs-001.litwareinc.com

Résultat : réussite

Latence : 00:00:00

Message d’erreur :

Diagnostic

Si les utilisateurs spécifiés ne peuvent pas échanger de messages à l’aide du service de chat permanent, le résultat s’affichera en **panne**et des informations supplémentaires seront enregistrées dans les propriétés d’erreur et de diagnostic :

AVERTISSEMENT : impossible de lire le numéro de port du Bureau d’enregistrement pour le nom complet fourni

nom de domaine (FQDN). Utilisation du numéro de port de bureau par défaut. Sauf

System. InvalidOperationException : aucun cluster correspondant détecté dans la topologie.

dès

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Nom de domaine complet (FQDN) cible : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Message d’erreur : 10060, une tentative de connexion a échoué car la partie connectée

ne répond pas correctement après un certain temps, ou

échec de la connexion établie, car l’hôte connecté a

échec de la \[réponse à 2001:4898 : E8 : f39e : 5c9a : ad83:81b3\]: 9944:5061

Exception interne : une tentative de connexion a échoué, car le

la fête connectée ne répond pas correctement après un délai de

heure ou échec de la connexion en raison d’un hôte connecté

échec de la réponse

\[2001:4898 : E8 : f39e : 5c9a : ad83:81b3:9944\]: 5061

Diagnostic

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles **les tests-CsPersistentChatMessage** peuvent échouer :

  - Une valeur de paramètre incorrecte a été fournie. Il est possible que les comptes de test requis n’existent pas ou aient été créés correctement.

  - Il est possible qu’il y ait un problème réseau entraînant un délai inattendu qui a entraîné le test.

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

