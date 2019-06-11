---
title: 'Lync Server 2013: test du partage lors de conférences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce4cd1a45d1eddf8875d85ff28886b0c04c29cfe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a>Test du partage lors de conférences dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-11-01_


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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande <strong>test-CsDataConference</strong> . Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Dans Lync Server 2013, une conférence de données est une conférence qui utilise les activités de collaboration, comme le tableau blanc ou les annotations. L’applet de **contrôle test-CsDataConference** vous permet de vérifier qu’une paire d’utilisateurs est en mesure de participer à une conférence de données.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La commande décrite dans l’exemple 1 vérifie qu’une conférence de données peut être effectuée sur le pool atl-cs-001.litwareinc.com. Cette commande part du principe que vous avez configuré un couple d’utilisateurs de test pour le pool spécifié. S’il n’existe pas de tels utilisateurs de test, la commande échoue.

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

Les commandes illustrées dans l’exemple 2 permettent de tester la capacité d’une paire\\d’utilisateurs (\\litwareinc Pilar et litwareinc kenmyer) de se connecter à Lync Server 2013 et de conduire une conférence de données. Pour cela, la première commande de l’exemple utilise l’applet de commande **Get-Credential** pour créer un objet d’information d’interface de ligne de commande Windows PowerShell contenant le nom et le mot de passe de l’utilisateur Pilar Arès. (Dans la mesure où le nom\\de connexion, litwareinc Pilar, a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell n’exige que l’administrateur entre le mot de passe du compte Pilar Arès.) L’objet Credential obtenu est ensuite stocké dans une variable nommée $cred 1. La deuxième commande effectue la même opération en renvoyant alors un objet Credential pour le compte Ken Myer.

Avec les objets d’information d’identification disponibles, la troisième commande détermine si les deux utilisateurs suivants peuvent se connecter à Lync Server 2013 et diriger une conférence de données. Pour effectuer cette tâche, l’applet de commande **test-CsDataConference** est appelée, ainsi que les paramètres suivants: TargetFqdn (nom de domaine complet (FQDN) du pool d’inscriptions); SenderSipAddress (adresse SIP pour le premier utilisateur test); SenderCredential (objet Windows PowerShell contenant les informations d’identification pour ce même utilisateur); ReceiverSipAddress (adresse SIP de l’autre utilisateur du test); et ReceiverCredential (objet Windows PowerShell contenant les informations d’identification de l’autre utilisateur du test).

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si les conférences de données sont configurées correctement, vous recevrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie:**

Nom de domaine complet (FQDN) cible: atl-cs-001.litwareinc.com

Résultat: réussite

Latence: 00:00:00

Message d’erreur:

Diagnostic

Si les utilisateurs spécifiés ne peuvent pas utiliser le partage de données, le résultat est affiché en tant qu' **échec**et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic:

Nom de domaine complet (FQDN) cible: atl-cs-001.litwareinc.com

Résultat: échec

Latence: 00:00:00

Message d’erreur: 10060, une tentative de connexion a échoué car la partie connectée

ne répond pas correctement après un certain temps, ou

échec de la connexion établie, car l’hôte connecté a

échec de la \[réponse à 2001:4898: E8: f39e: 5c9a: ad83:81b3\]: 9944:5061

Exception interne: une tentative de connexion a échoué, car le

la fête connectée ne répond pas correctement après un délai de

heure ou échec de la connexion en raison d’un hôte connecté

échec de la réponse

\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061

Diagnostic

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles **les tests-CsDataConference** peuvent échouer:

  - Une valeur de paramètre incorrecte a été fournie. S’il est utilisé, les paramètres facultatifs doivent être correctement configurés ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et déterminez si l’opération aboutit.

  - La capacité à organiser une conférence de données dépend de la stratégie de conférence qui a été affectée à l’utilisateur qui a organisé la Conférence (dans le cas de l’applet de **contrôle CsDataConference** ). Si l’organisateur n’est pas autorisé à inclure des activités de collaboration dans sa réunion (par exemple, si sa propriété EnableDataCollaboration est définie sur false), l’applet de commande **test-CsDataConference** échoue.

  - Cette commande échoue si le serveur de périphérie est mal configuré ou n’est pas encore déployé.

</div>

</div>

<span> </span>

</div>

</div>

</div>

