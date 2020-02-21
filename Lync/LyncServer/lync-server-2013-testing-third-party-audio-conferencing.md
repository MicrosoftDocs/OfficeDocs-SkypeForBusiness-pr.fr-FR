---
title: 'Lync Server 2013 : test de l’audioconférence tierce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34e55661d2d28052f7672798059d458563ab5c8d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a>Test de l’audioconférence tierce dans Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsAudioConferencingProvider. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Un fournisseur de services d’audioconférence est une société tierce qui propose des services de conférence aux entreprises. Entre autres, les fournisseurs de services d’audioconférence permettent aux utilisateurs situés hors site et non connectés au réseau d’entreprise ou à Internet de participer à la partie audio d’une conférence ou d’une réunion. Souvent, les fournisseurs d’audioconférences proposent des services haut de gamme en direct tels que la traduction, la transcription et une assistance opérateur par conférence.

La cmdlet **test-CsAudioConferencingProvider** est utilisée pour vérifier qu’un utilisateur est en mesure d’établir une connexion à son fournisseur d’audioconférence. Notez que cette applet de commande peut être exécutée de deux manières. De nombreux administrateurs utiliseront les applets de commande CsHealthMonitoringConfiguration pour configurer des utilisateurs de test pour chacun de leurs pools de serveurs d’inscriptions. Ces utilisateurs de test sont un groupe de deux utilisateurs préconfigurés pour être utilisés avec des transactions synthétiques. (En général, il s’agit de comptes de test et non de comptes qui appartiennent à des utilisateurs réels.) Si les utilisateurs de test sont configurés pour un pool, les administrateurs peuvent exécuter l’applet de commande **test-CsAudioConferencingProvider** sur ce pool sans avoir à spécifier l’identité (et fournir les informations d’identification pour) du compte d’utilisateur impliqué dans le test.

Les administrateurs peuvent également exécuter l’applet de commande **test-CsAudioConferencingProvider** à l’aide d’un compte d’utilisateur réel. Si vous décidez d’effectuer le test à l’aide d’un tel compte, vous devrez saisir son nom de connexion et son mot de passe.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’exemple 1 vérifie si un utilisateur de test défini pour le pool atl-cs-001.litwareinc.com est capable de se connecter à son fournisseur de services d’audioconférence. Cette commande nécessite qu’au moins un utilisateur test soit défini pour le pool. Si aucun utilisateur de test n’a été défini pour atl-cs-001.litwareinc.com, la commande échouera ; Cela est dû au fait que l’applet de commande **test-CsAudioConferencingProvider** ne saura pas quel utilisateur utiliser dans le test. Si vous n’avez pas défini les utilisateurs de test pour un pool, vous devez inclure le paramètre UserSipAddress et les informations d’identification du compte d’utilisateur que la commande doit utiliser lors de la vérification de la connexion avec un fournisseur de services d’audioconférence.

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

Les commandes indiquées dans l’exemple 2 testent la capacité d’un utilisateur spécifique\\(litwareinc kenmyer) à se connecter à son fournisseur d’audioconférence. Pour ce faire, la première commande de l’exemple utilise la cmdlet Get-Credential pour créer un objet d’informations d’identification de l’interface de ligne de commande Windows PowerShell contenant le nom et le mot de passe de l’utilisateur Ken Myer. (Étant donné que le nom\\de connexion litwareinc kenmyer a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell nécessite uniquement que l’administrateur entre le mot de passe pour le compte Ken Myer.) L’objet Credentials qui en résulte est stocké dans une variable nommée $credential.

La deuxième commande vérifie ensuite si cet utilisateur peut se connecter à son fournisseur d’audioconférence. Pour exécuter cette tâche, la cmdlet Test-CsAudioConferencingProvider est appelée, ainsi que trois paramètres : TargetFqdn (le nom de domaine complet du pool de serveurs d’inscriptions); UserCredential (l’objet Windows PowerShell contenant les informations d’identification de l’utilisateur de Ken Myer); et UserSipAddress (adresse SIP correspondant aux informations d’identification de l’utilisateur fourni).

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si le fournisseur de services d’audioconférence est correctement configuré, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée with **Success :**

Nom de domaine complet cible : atl-sql-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:00

Message d’erreur :

Diagnostique

Si l’utilisateur spécifié ne peut pas se connecter ou se déconnecter, le résultat est affiché comme un **échec**et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :

Nom de domaine complet cible : atl-sql-001.litwareinc.com

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

Par exemple, la sortie précédente inclut la note « la partie connectée n’a pas répondu correctement » qui indique généralement un problème avec le serveur Edge.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec **de test-CsAudioConferencingProvider** :

  - Une valeur de paramètre incorrecte a été fournie. Comme indiqué dans l’exemple précédent, les paramètres facultatifs doivent être configurés correctement ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.

  - Notez que le test échoue si l’utilisateur employé par la cmdlet **test-CsAudioConferencingProvider** n’a pas reçu de fournisseur d’audioconférence.

  - Cette commande échoue si le serveur Edge est mal configuré ou s’il n’est pas encore déployé.

</div>

</div>

<span> </span>

</div>

</div>

</div>

