---
title: 'Lync Server 2013: test de l’audioconférence tierce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1c23f65015dd34f5efbaafa8472466394caa52c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a>Test de l’audioconférence tierce dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsAudioConferencingProvider. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Un fournisseur de services d’audioconférence est une société tierce qui propose des services de conférence aux entreprises. Entre autres, il permet aux utilisateurs localisés hors site et non connectés au réseau de l’entreprise ou à Internet, de participer à la partie audio d’une conférence ou d’une réunion. Les fournisseurs de services d’audioconférence fournissent souvent des services haut de gamme tels que la traduction dynamique, la transcription et l’assistance directe par opérateur.

L’applet de **contrôle test-CsAudioConferencingProvider** est utilisée pour vérifier qu’un utilisateur est en mesure d’établir une connexion à son fournisseur de services d’audioconférence. Notez que cette applet de cmdlet peut être exécutée d’une des deux manières suivantes. De nombreux administrateurs utilisent les applets de contrôle CsHealthMonitoringConfiguration pour configurer les utilisateurs de test pour chacun de leurs pools de bureaux d’enregistrement. Ces utilisateurs de test représentent une paire de comptes d’utilisateurs préconfigurés pour une utilisation avec des transactions synthétiques. (En général, il s’agit des comptes de test et non des comptes appartenant aux utilisateurs réels.) Si les utilisateurs de test sont configurés pour un pool, les administrateurs peuvent exécuter l’applet **de connexion test-CsAudioConferencingProvider** sur ce pool sans avoir à spécifier l’identité (et fournir les informations d’identification pour) le compte d’utilisateur impliqué dans le test.

Une autre solution consiste à ce que les administrateurs puissent exécuter l’applet **de contrôle CsAudioConferencingProvider** en utilisant un compte d’utilisateur réel. Si vous décidez d’effectuer le test en utilisant un compte d’utilisateur réel, vous devez fournir le nom de connexion et le mot de passe pour ce compte.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Exemple 1 vérifie si un utilisateur de test défini pour le pool atl-cs-001.litwareinc.com est en mesure de se connecter à son fournisseur de services d’audioconférence. Ce contrôle nécessite qu’au moins un utilisateur de test soit défini pour le pool. Si aucun utilisateur de test n’a été défini pour atl-cs-001.litwareinc.com, la commande échouera. ce n’est pas parce que l’applet de **contrôle de test-CsAudioConferencingProvider** ne connaît pas l’utilisateur à employer dans le test. Si vous n’avez pas défini les utilisateurs test pour un pool, vous devez inclure le paramètre UserSipAddress et les informations d’identification du compte d’utilisateur que la commande doit utiliser pour vérifier la connexion à un fournisseur de services d’audioconférence.

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

Les commandes illustrées dans l’exemple 2 permettent de tester la capacité d’un\\utilisateur spécifique (litwareinc kenmyer) de se connecter à son fournisseur de services d’audioconférence. Pour cela, la première commande de l’exemple utilise l’applet de commande Get-Credential pour créer un objet d’information d’identification de l’interface de ligne de commande Windows PowerShell contenant le nom et le mot de passe de l’utilisateur Ken Myer. (Dans la mesure où le\\nom de connexion litwareinc kenmyer a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell n’exige que l’administrateur entre le mot de passe du compte Ken Myer.) L’objet Credentials obtenu est stocké dans une variable nommée $credential.

La deuxième commande vérifie alors que l’utilisateur peut se connecter à son fournisseur de services d’audioconférence. Pour effectuer cette tâche, l’applet de contrôle test-CsAudioConferencingProvider est appelée, avec trois paramètres: TargetFqdn (nom de domaine complet du pool d’inscriptions); UserCredential (l’objet Windows PowerShell contenant les informations d’identification de l’utilisateur de Ken Myer); et UserSipAddress (adresse SIP correspondant aux informations d’identification fournies par l’utilisateur).

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si le fournisseur de services d’audioconférence est configuré correctement, vous recevrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie:**

Nom de domaine complet (FQDN) cible: atl-sql-001.litwareinc.com

Résultat: réussite

Latence: 00:00:00

Message d’erreur:

Diagnostic

Si l’utilisateur spécifié ne peut pas se connecter ou se déconnecter, le résultat s’affichera en tant qu' **échec**et des informations supplémentaires seront enregistrées dans les propriétés d’erreur et de diagnostic:

Nom de domaine complet (FQDN) cible: atl-sql-001.litwareinc.com

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

Par exemple, la sortie précédente inclut la remarque «la partie connectée n’a pas répondu correctement», qui indique généralement un problème avec le serveur Edge.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles **les tests-CsAudioConferencingProvider** peuvent échouer:

  - Une valeur de paramètre incorrecte a été fournie. Comme indiqué dans l’exemple précédent, les paramètres facultatifs doivent être correctement configurés ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et déterminez si l’opération aboutit.

  - Notez que le test échoue si l’utilisateur utilisé par l’applet de **contrôle de test-CsAudioConferencingProvider** n’a pas été affecté à un fournisseur de services d’audioconférence.

  - Cette commande échoue si le serveur de périphérie est mal configuré ou n’est pas encore déployé.

</div>

</div>

<span> </span>

</div>

</div>

</div>

