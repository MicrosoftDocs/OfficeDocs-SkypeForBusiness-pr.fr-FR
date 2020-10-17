---
title: 'Lync Server 2013 : test du partage d’application'
description: 'Lync Server 2013 : test du partage d’application.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f857908e374239b4054985b88951cd12720ed418
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560720"
---
# <a name="testing-application-sharing-in-lync-server-2013"></a>Test du partage d’application dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<td><p>Journalière</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsASConference. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande **test-CsASConference** vérifie qu’une paire d’utilisateurs test peut participer à une conférence en ligne qui inclut le partage d’application. Pour ce faire, l’applet de commande enregistre les deux utilisateurs avec Lync Server 2013, puis il utilise l’un des comptes d’utilisateur pour créer une nouvelle conférence qui inclut le partage d’applications. L’applet de commande vérifie ensuite si le second utilisateur peut participer à cette conférence.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La commande indiquée dans l’exemple 1 vérifie qu’une conférence de partage d’application peut être menée sur le pool atl-cs-001.litwareinc.com. Cette commande part du principe que vous avez configuré une paire d’utilisateurs de test pour le pool spécifié. En l’absence d’utilisateurs de test, la commande échoue.

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

L’exemple 2 teste la capacité du service de lanceur de participation à participer à une conférence de partage d’application sur le pool atl-cs-001.litwareinc.com. Notez que cette commande teste uniquement le service proprement dit ; vous n’avez pas besoin d’appareils mobiles pour exécuter la commande.

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

Les commandes indiquées dans l’exemple 2 testent la capacité d’une paire d’utilisateurs (litwareinc \\ Pilar et litwareinc \\ kenmyer) à se connecter à Lync Server 2013, puis à effectuer une conférence de partage d’application. Pour ce faire, la première commande de l’exemple utilise l’applet de commande Get-Credential pour créer un objet Credential de l’interface de ligne de commande Windows PowerShell contenant le nom et le mot de passe de l’utilisateur Pilar Ackerman. (Étant donné que le nom de connexion, litwareinc \\ Pilar, a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell nécessite uniquement que l’administrateur entre le mot de passe du compte Pilar Ackerman.) L’objet Credential qui en résulte est ensuite stocké dans une variable nommée $cred 1. La deuxième commande effectue la même action, en retournant cette fois un objet d’identification pour le compte de Ken Myer.

Avec les objets Credential en main, la troisième commande détermine si ces deux utilisateurs peuvent se connecter à Lync Server 2013 et effectuer une conférence de partage d’application. Pour exécuter cette tâche, la cmdlet **test-CsASConference** est appelée, ainsi que les paramètres suivants : TargetFqdn (nom de domaine complet du pool de serveurs d’inscriptions); SenderSipAddress (l’adresse SIP pour le premier utilisateur test); SenderCredential (l’objet Windows PowerShell contenant les informations d’identification pour ce même utilisateur); ReceiverSipAddress (l’adresse SIP de l’autre utilisateur de test); et ReceiverCredential (l’objet Windows PowerShell contenant les informations d’identification pour l’autre utilisateur de test).

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si le partage d’application est correctement configuré, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success :**

Nom de domaine complet cible : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:01

Message d’erreur :

Diagnostique

Si les utilisateurs spécifiés ne peuvent pas partager d’applications, le résultat est affiché sous la forme échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

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

Par exemple, la sortie précédente inclut la note « la partie connectée n’a pas répondu correctement » qui indique généralement un problème avec le serveur Edge.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec **de test-CsASConference** :

  - Une valeur de paramètre incorrecte a été fournie. Si ce paramètre est utilisé, les paramètres facultatifs doivent être configurés correctement ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.

  - Cette commande échoue si les utilisateurs de test ont reçu une stratégie de conférence qui les empêche d’utiliser le partage d’application.

  - Cette commande échoue si le serveur Edge est mal configuré ou s’il n’est pas encore déployé.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

