---
title: 'Lync Server 2013 : test du partage d’application'
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
ms.openlocfilehash: ab428e5bbfb5ffc58fa7b1d092cd7fc04b117226
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a>Test du partage d’application dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsASConference. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de **contrôle test-CsASConference** vérifie qu’un binôme d’utilisateurs de test peut participer à une conférence en ligne incluant le partage d’application. Pour ce faire, l’applet de demande enregistre les deux utilisateurs avec Lync Server 2013, puis utilise l’un des comptes d’utilisateurs pour créer une nouvelle conférence incluant le partage d’applications. L’applet de connexion vérifie alors que le second utilisateur est en mesure de rejoindre la Conférence.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La commande décrite dans l’exemple 1 vérifie qu’une conférence de partage d’application peut être effectuée sur le pool atl-cs-001.litwareinc.com. Cette commande part du principe que vous avez configuré un couple d’utilisateurs de test pour le pool spécifié. S’il n’existe pas de tels utilisateurs de test, la commande échoue.

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

Dans l’exemple 2, le service de lancement de jointure peut participer à une conférence de partage d’application sur le pool atl-cs-001.litwareinc.com. Notez que cette commande teste uniquement le service proprement dit ; pour exécuter la commande, vous n’avez pas besoin d’appareils mobiles.

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

Les commandes illustrées dans l’exemple 2 testent la capacité d’une paire d'\\utilisateurs (litwareinc\\Pilar et litwareinc kenmyer) à se connecter à Lync Server 2013, puis à effectuer une conférence de partage d’application. Pour cela, la première commande de l’exemple utilise l’applet de commande Get-Credential pour créer un objet d’information d’interface de ligne de commande Windows PowerShell contenant le nom et le mot de passe de l’utilisateur Pilar Arès. (Dans la mesure où le nom\\de connexion, litwareinc Pilar, a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell n’exige que l’administrateur entre le mot de passe du compte Pilar Arès.) L’objet Credential obtenu est ensuite stocké dans une variable nommée $cred 1. La deuxième commande effectue la même opération en renvoyant alors un objet Credential pour le compte Ken Myer.

Avec les objets d’information d’identification disponibles, la troisième commande détermine si les deux utilisateurs suivants peuvent se connecter à Lync Server 2013 et diriger une conférence de partage d’application. Pour effectuer cette tâche, l’applet de commande **test-CsASConference** est appelée, ainsi que les paramètres suivants : TargetFqdn (nom de domaine complet (FQDN) du pool d’inscriptions); SenderSipAddress (adresse SIP pour le premier utilisateur test); SenderCredential (objet Windows PowerShell contenant les informations d’identification pour ce même utilisateur); ReceiverSipAddress (adresse SIP de l’autre utilisateur du test); et ReceiverCredential (objet Windows PowerShell contenant les informations d’identification de l’autre utilisateur du test).

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si le partage d’application est correctement configuré, vous recevrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie :**

Nom de domaine complet (FQDN) cible : atl-cs-001.litwareinc.com

Résultat : réussite

Latence : 00:00:01

Message d’erreur :

Diagnostic

Si les utilisateurs spécifiés ne peuvent pas partager des applications, le résultat est affiché en tant qu’échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

Nom de domaine complet (FQDN) cible : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Message d’erreur : 10060, une tentative de connexion a échoué car la partie connectée

ne répond pas correctement après un certain temps, ou

échec de la connexion établie, car l’hôte connecté a

échec de la réponse à 10.188.116.96:5061

Exception interne : une tentative de connexion a échoué, car le

la fête connectée ne répond pas correctement après un délai de

heure ou échec de la connexion en raison d’un hôte connecté

échec de la réponse à 10.188.116.96:5061

Diagnostic

Par exemple, la sortie précédente inclut la remarque « la partie connectée n’a pas répondu correctement », qui indique généralement un problème avec le serveur Edge.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles **les tests-CsASConference** peuvent échouer :

  - Une valeur de paramètre incorrecte a été fournie. S’il est utilisé, les paramètres facultatifs doivent être correctement configurés ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et déterminez si l’opération aboutit.

  - Cette commande échouera si les utilisateurs test disposent d’une stratégie de conférence qui les empêche d’utiliser le partage d’application.

  - Cette commande échoue si le serveur de périphérie est mal configuré ou n’est pas encore déployé.

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

