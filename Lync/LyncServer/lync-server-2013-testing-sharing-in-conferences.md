---
title: 'Lync Server 2013 : test du partage dans les conférences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7a98312c04b943d485e1c6668b1c9347c9714e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a>Test du partage dans les conférences dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Planification de la vérification</p></td>
<td><p>Tous les jours</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-CsDataConference</strong> . Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Dans Lync Server 2013, une conférence de données est une conférence où des activités collaboratives telles que le tableau blanc ou les annotations sont utilisées. L’applet de commande **test-CsDataConference** vous permet de vérifier qu’une paire d’utilisateurs est en mesure de participer à une conférence de données.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La commande indiquée dans l’exemple 1 vérifie qu’une conférence de données peut être menée sur le pool atl-cs-001.litwareinc.com. Cette commande part du principe que vous avez configuré une paire d’utilisateurs de test pour le pool spécifié. En l’absence d’utilisateurs de test, la commande échoue.

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

Les commandes indiquées dans l’exemple 2 testent la capacité d’une paire d’utilisateurs\\(litwareinc Pilar\\et litwareinc kenmyer) à se connecter à Lync Server 2013, puis à mener une conférence de données. Pour ce faire, la première commande de l’exemple utilise la cmdlet **Get-Credential** pour créer un objet d’informations d’identification de l’interface de ligne de commande Windows PowerShell contenant le nom et le mot de passe de l’utilisateur Pilar Ackerman. (Étant donné que le nom de\\connexion, litwareinc Pilar, a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell nécessite uniquement que l’administrateur entre le mot de passe du compte Pilar Ackerman.) L’objet Credential qui en résulte est ensuite stocké dans une variable nommée $cred 1. La deuxième commande effectue la même action, en retournant cette fois un objet d’identification pour le compte de Ken Myer.

Avec les objets Credential en main, la troisième commande détermine si ces deux utilisateurs peuvent se connecter à Lync Server 2013 et mener une conférence de données. Pour exécuter cette tâche, la cmdlet **test-CsDataConference** est appelée, ainsi que les paramètres suivants : TargetFqdn (nom de domaine complet du pool de serveurs d’inscriptions); SenderSipAddress (l’adresse SIP pour le premier utilisateur test); SenderCredential (l’objet Windows PowerShell contenant les informations d’identification pour ce même utilisateur); ReceiverSipAddress (l’adresse SIP de l’autre utilisateur de test); et ReceiverCredential (l’objet Windows PowerShell contenant les informations d’identification pour l’autre utilisateur de test).

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si la Conférence de données est configurée correctement, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success :**

Nom de domaine complet cible : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:00

Message d’erreur :

Diagnostique

Si les utilisateurs spécifiés ne peuvent pas utiliser le partage de données, le résultat est indiqué comme étant un **échec**et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :

Nom de domaine complet cible : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Message d’erreur : 10060, une tentative de connexion a échoué car la partie connectée

ne répond pas correctement au bout d’un certain temps, ou

échec de la connexion établie car l’hôte connecté a

échec de la \[réponse 2001:4898 : E8 : f39e : 5c9a : ad83:81b3 :\]9944 :: 5061

Exception interne : une tentative de connexion a échoué car le

la partie connectée n’a pas répondu correctement après une période de

heure ou échec de la connexion établie car l’hôte connecté

n’a pas répondu

\[2001:4898 : E8 : f39e : 5c9a : ad83:81b3:9944\]:: 5061

Diagnostique

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec **de test-CsDataConference** :

  - Une valeur de paramètre incorrecte a été fournie. Si ce paramètre est utilisé, les paramètres facultatifs doivent être configurés correctement ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.

  - La possibilité d’effectuer une conférence de données dépend de la stratégie de conférence qui a été attribuée à l’utilisateur qui a organisé la Conférence (dans le cas de la cmdlet **test-CsDataConference** , qui est l’expéditeur). Si l’organisateur n’est pas autorisé à inclure des activités collaboratives dans sa réunion (par exemple, si la propriété EnableDataCollaboration de sa stratégie de conférence est définie sur false), la cmdlet **test-CsDataConference** échouera.

  - Cette commande échoue si le serveur Edge est mal configuré ou s’il n’est pas encore déployé.

</div>

</div>

<span> </span>

</div>

</div>

</div>

