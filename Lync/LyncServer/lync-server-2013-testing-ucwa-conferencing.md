---
title: 'Lync Server 2013 : test des conférences UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9496b2a860f0a8272d6eb98df6a2c897aa245ec9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a>Test de la Conférence UCWA dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande <strong>test-CsUcwaConference</strong> . Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de **contrôle test-CsUcwaConference** vérifie qu’un binôme d’utilisateurs de test peut planifier, rejoindre et diriger une conférence en ligne à l’aide de l’API Web Unified Communications Web (UCWA). Pour ce faire, le cmdlet utilise le service de ticket Web de Lync Server pour authentifier les deux utilisateurs test et les inscrire auprès de Lync Server. L’applet de commande démarre alors une conférence à l’aide des informations d’identification de la classe Organizer et invite le participant à rejoindre la réunion. Une fois la réunion jointe, l’applet de **contrôle CsUcwaConference de test** vérifie que les utilisateurs peuvent effectuer des actions telles que les messages instantanés Exchange et les pools, puis déconnecter la Conférence et annuler l’enregistrement des deux utilisateurs test. La conférence planifiée sera également supprimée une fois le test terminé.

L’applet de **contrôle test-CsUcwaConference** peut également être utilisée pour déterminer si des utilisateurs anonymes peuvent participer à des conférences en ligne.

Notez que l’applet de **contrôle test-CsUcwaConference** ne doit pas être exécutée sur un pool Microsoft Lync Server 2010, sauf si UCWA a été installé sur ce pool. Si UCWA n’a pas été installé, l’appel à l’applet de **contrôle CsUcwaConference** échoue.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La commande décrite dans l’exemple 1 vérifie qu’un binôme d’utilisateurs de test peut participer à une conférence UCWA sur le pool atl-cs-001.litwareinc.com. Notez que cette commande échoue si vous n’avez pas prédéfini une paire de tests de configuration de l’analyse de l’état des utilisateurs pour atl-cs-001.litwareinc.com.

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

Les commandes illustrées dans l’exemple 2 permettent de tester la capacité d’une paire\\d’utilisateurs (\\litwareinc Pilar et litwareinc kenmyer) de participer à une conférence UCWA. Pour cela, la première commande de l’exemple utilise l’applet de commande Get-Credential pour créer un objet d’information d’interface de ligne de commande Windows PowerShell contenant le nom et le mot de passe de l’utilisateur Pilar Arès. (Dans la mesure où le nom\\de connexion, litwareinc Pilar, a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell n’exige que l’administrateur entre le mot de passe du compte Arès Pilar.) L’objet Credentials obtenu est ensuite stocké dans une variable nommée $cred 1. La deuxième commande effectue la même opération en renvoyant alors un objet Credential pour le compte Ken Myer.

À l’aide des deux objets d’information d’identification disponibles, la troisième commande de l’exemple détermine si les deux utilisateurs peuvent participer à une conférence UCWA. Pour exécuter cette tâche, l’applet de commande **test-CsUcwaConference** est appelée, ainsi que les paramètres suivants : TargetFqdn (nom de domaine complet (FQDN) du pool d’inscriptions); OrganizerSipAddress (adresse SIP de l’organisateur de la réunion); OrganizerCredential (objet Windows PowerShell contenant les informations d’identification pour ce même utilisateur); ParticipantSipAddress (adresse SIP de l’autre utilisateur du test); et ParticipantCredential (l’objet d’interface de ligne de commande Windows PowerShell qui contient les informations d’identification pour l’autre utilisateur).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si la Conférence est configurée correctement, vous recevrez une sortie semblable à celle-ci, avec la propriété Result marquée comme **réussie :**

Nom de domaine complet (FQDN) cible : atl-cs-001.litwareinc.com

URI cible : https://LyncTest-SE. LyncTest. SelfHost. Corp.

Microsoft.com:443/CertProv/CertProvisiongService.svc

Résultat : réussite

Latence : 00:00:14.9862716

Message d’erreur :

Diagnostic

Si les utilisateurs spécifiés ne peuvent pas utiliser les conférences, le résultat est affiché en tant qu' **échec**et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

AVERTISSEMENT : impossible de lire le numéro de port du Bureau d’enregistrement pour le nom complet fourni

nom de domaine (FQDN). Utilisation du numéro de port de bureau par défaut. Sauf

System. InvalidOperationException : aucun cluster correspondant détecté dans la topologie.

dès

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Test-CsUcwaConference : il n’y a aucun utilisateur de test affecté à

\[LyncTest.SelfHost.Corp.Microsoft.com\]. Vérifiez la configuration de l’utilisateur test.

À la ligne : 1 car : 1

\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo : ResourceUnavailable : ( :) \[Test-CsUcwaConference\]

, InvalidOperationException

\+FullyQualifiedErrorId : NotFoundTestUsers, Microsoft. RTC. Management. synthé

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles **les tests-CsUcwaConference** peuvent échouer :

  - Une valeur de paramètre incorrecte a été fournie. S’il est utilisé, les paramètres facultatifs doivent être correctement configurés ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et déterminez si l’opération aboutit.

  - La possibilité d’organiser une conférence dépend de la stratégie de conférence qui a été affectée à l’utilisateur qui a organisé la Conférence (dans le cas de l’applet de **contrôle CsUcwaConference** , qui est le « sender »). Si l’organisateur n’est pas autorisé à inclure des activités de collaboration dans sa réunion (par exemple, si sa propriété EnableDataCollaboration est définie sur false), l’applet de commande **test-CsUcwaConference** échoue.

  - Cette commande échoue si le serveur de périphérie est mal configuré ou n’est pas encore déployé.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

