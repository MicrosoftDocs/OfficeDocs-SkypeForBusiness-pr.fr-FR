---
title: 'Lync Server 2013: test de la messagerie à l’aide de XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acd03cdf2a5215c980b788dbaffafc5936fe5b5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a>Test de la messagerie à l’aide de XMPP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-11-03_


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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande <strong>test-CsXmppIM</strong> . Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Le protocole XMPP est un protocole de communication standard (basé sur le langage XML) utilisé pour envoyer des messages sur Internet. XMPP a été nommé Jabber à l’origine, et est pris en charge par plusieurs applications de messagerie et de communication par Internet, comme Google Talk et chat Facebook. L’applet de **contrôle test-CsXmppIM** vérifie qu’un utilisateur peut échanger des messages instantanés avec un utilisateur sur un réseau XMPP. Notez que pour que ce test réussisse, vous devez disposer d’une adresse SIP valide pour l’utilisateur XMPP, et cette adresse SIP doit être située sur un réseau configuré en tant que partenaire XMPP autorisé.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’exemple suivant vérifie les fonctionnalités de messagerie instantanée XMPP pour le pool atl-cs-001.litwareinc.com. Cette commande ne fonctionne que si les utilisateurs de test sont définis pour le pool atl-cs-001.litwareinc.com. Si tel est le cas, la commande détermine si le premier utilisateur du test peut envoyer un message instantané XMPP à un utilisateur disposant de l’adresse adelaney@contoso.com.

Si les utilisateurs de test ne sont pas définis, la commande échoue, car il ne connaît pas l’utilisateur sur lequel se connecter. Si vous n’avez pas défini les utilisateurs de test pour un pool, vous devez inclure le paramètre UserSipAddress et les informations d’identification de l’utilisateur que la commande doit utiliser lors de la tentative de connexion.

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

Les commandes indiquées dans l’exemple suivant testent la capacité d’un utilisateur spécifique (\\litwareinc Pilar) à se connecter pour envoyer un message instantané XMPP à l’utilisateur adelaney@contoso.com. Pour cela, la première commande de l’exemple utilise l’applet de commande Get-Credential pour créer un objet d’information d’interface de ligne de commande Windows PowerShell contenant le nom et le mot de passe de l’utilisateur Pilar Arès. (Dans la mesure où le\\nom de connexion litwareinc Pilar a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell exige uniquement de l’administrateur d’entrer le mot de passe du compte Arès Pilar.) L’objet Credential obtenu est ensuite stocké dans une variable nommée $cred 1.

La deuxième commande vérifie que l’utilisateur peut se connecter au pool atl-cs-001.litwareinc.com et envoyer le message instantané XMPP. Pour exécuter cette tâche, l’applet de **contrôle test-CsXmppIm** est appelée, avec quatre paramètres: TargetFqdn (nom de domaine complet (FQDN) du pool d’inscriptions); Receiver (adresse SIP de l’utilisateur auquel le message est adressé); UserCredential (l’objet Windows PowerShell contenant les informations d’identification de l’utilisateur de Pilar Arès); et UserSipAddress (adresse SIP correspondant aux informations d’identification fournies par l’utilisateur).

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si la messagerie instantanée XMPP est configurée correctement, vous recevrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie:**

Nom de domaine complet (FQDN) cible: atl-cs-001.litwareinc.com

Résultat: réussite

Latence: 00:00:02.5361946

Message d’erreur:

Diagnostic

Si les utilisateurs spécifiés ne peuvent pas utiliser la messagerie instantanée XMPP, le résultat est affiché en tant qu' **échec**et des informations supplémentaires seront enregistrées dans les propriétés d’erreur et de diagnostic:

AVERTISSEMENT: impossible de lire le numéro de port du Bureau d’enregistrement pour le nom complet fourni

nom de domaine (FQDN). Utilisation du numéro de port de bureau par défaut. Sauf

System. InvalidOperationException: aucun cluster correspondant détecté dans la topologie.

dès

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Nom de domaine complet (FQDN) cible: atl-cs-001.litwareinc.com

Résultat: échec

Latence: 00:00:00

Message d’erreur: 10060, une tentative de connexion a échoué car la partie connectée

ne répond pas correctement après un certain temps, ou

échec de la connexion établie, car l’hôte connecté a

échec de la réponse à 10.188.116.96:5061

Exception interne: une tentative de connexion a échoué, car le

la fête connectée ne répond pas correctement après un délai de

heure ou échec de la connexion en raison d’un hôte connecté

échec de la réponse à 10.188.116.96:5061

Diagnostic

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles **les tests-CsXmppIM** peuvent échouer:

  - Une valeur de paramètre incorrecte a été fournie. S’il est utilisé, les paramètres facultatifs doivent être correctement configurés ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et déterminez si l’opération aboutit.

  - Cette commande échoue si la configuration de la passerelle XMPP est mal configurée ou n’est pas encore déployée.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Set-CsXmppGatewayConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

