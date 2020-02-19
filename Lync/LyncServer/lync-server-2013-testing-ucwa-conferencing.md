---
title: 'Lync Server 2013 : test de la Conférence UCWA'
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
ms.openlocfilehash: 8855abbb92accbae66048905869f20958e128019
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-CsUcwaConference</strong> . Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande **test-CsUcwaConference** vérifie qu’une paire d’utilisateurs test peut planifier, joindre, puis mener une conférence en ligne à l’aide de l’API Web communications unifiées (UCWA). Pour ce faire, l’applet de commande utilise le service de ticket Web Lync Server pour authentifier les deux utilisateurs de test et les inscrire auprès de Lync Server. L’applet de commande commence alors une conférence en se servant des informations d’identification de l’organisateur et invite les participants à se joindre à la réunion. Une fois la réunion jointe, l’applet de commande **test-CsUcwaConference** vérifie que les utilisateurs peuvent effectuer des actions telles que les pools de messages instantanés et de réunions Exchange, puis déconnecte la Conférence et annule l’inscription des deux utilisateurs de test. La conférence planifiée sera également supprimée une fois le test terminé.

La cmdlet **test-CsUcwaConference** peut également être utilisée pour déterminer si les utilisateurs anonymes peuvent participer à des conférences en ligne.

Notez que l’applet de commande **test-CsUcwaConference** ne doit pas être exécutée sur un pool Microsoft Lync Server 2010, sauf si UCWA a été installé sur ce pool. Si UCWA n’a pas été installé, l’appel de l’applet de commande **test-CsUcwaConference** échouera.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La commande présentée dans l’exemple 1 vérifie que deux utilisateurs de test peuvent participer à une conférence UCWA dans le pool atl-cs-001.litwareinc.com. Notez que cette commande échoue si vous n’avez pas défini au préalable deux utilisateurs de test de configuration d’analyse d’intégrité pour atl-cs-001.litwareinc.com.

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

Les commandes indiquées dans l’exemple 2 testent la capacité d’une paire d’utilisateurs\\(litwareinc Pilar\\et litwareinc kenmyer) à participer à une conférence UCWA. Pour ce faire, la première commande de l’exemple utilise la cmdlet Get-Credential pour créer un objet d’informations d’identification de l’interface de ligne de commande Windows PowerShell qui contient le nom et le mot de passe de l’utilisateur Pilar Ackerman. (Étant donné que le nom de\\connexion, litwareinc Pilar, a été inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell nécessite uniquement que l’administrateur entre le mot de passe du compte Pilar Ackerman.) L’objet Credentials qui en résulte est ensuite stocké dans une variable nommée $cred 1. La deuxième commande effectue la même action, en retournant cette fois un objet d’identification pour le compte de Ken Myer.

Avec les deux objets Credential en main, la troisième commande de l’exemple détermine si les deux utilisateurs peuvent participer à une conférence UCWA. Pour exécuter cette tâche, la cmdlet **test-CsUcwaConference** est appelée, ainsi que les paramètres suivants : TargetFqdn (nom de domaine complet du pool de serveurs d’inscriptions); OrganizerSipAddress (adresse SIP de l’organisateur de la réunion); OrganizerCredential (l’objet Windows PowerShell qui contient les informations d’identification pour ce même utilisateur); ParticipantSipAddress (l’adresse SIP de l’autre utilisateur de test); et ParticipantCredential (l’objet interface de ligne de commande Windows PowerShell qui contient les informations d’identification pour l’autre utilisateur).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si la Conférence est correctement configurée, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée with **Success :**

Nom de domaine complet cible : atl-cs-001.litwareinc.com

URI cible : https://LyncTest-SE. LyncTest. SelfHost. Corp.

Microsoft.com:443/CertProv/CertProvisiongService.svc

Résultat : opération réussie

Latence : 00:00:14.9862716

Message d’erreur :

Diagnostique

Si les utilisateurs spécifiés ne peuvent pas utiliser la fonctionnalité de conférence, le résultat est affiché en **échec**et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

AVERTISSEMENT : impossible de lire le numéro de port du serveur d’inscriptions pour le serveur complet

nom de domaine (FQDN). À l’aide du numéro de port de serveur d’inscriptions par défaut. Rogation

System. InvalidOperationException : aucun cluster correspondant n’a été trouvé dans la topologie.

Regardez

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Test-CsUcwaConference : aucun utilisateur de test n’est affecté à

\[LyncTest.SelfHost.Corp.Microsoft.com\]. Vérifiez la configuration de l’utilisateur test.

À la ligne : 1 char : 1

\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo : ResourceUnavailable : ( :) \[Test-CsUcwaConference\]

, InvalidOperationException

\+FullyQualifiedErrorId : NotFoundTestUsers, Microsoft. RTC. Management. synthé

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec **de test-CsUcwaConference** :

  - Une valeur de paramètre incorrecte a été fournie. Si ce paramètre est utilisé, les paramètres facultatifs doivent être configurés correctement ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.

  - La possibilité d’effectuer une conférence dépend de la stratégie de conférence qui a été attribuée à l’utilisateur qui a organisé la Conférence (dans le cas de la cmdlet **test-CsUcwaConference** , qui est l’expéditeur). Si l’organisateur n’est pas autorisé à inclure des activités collaboratives dans sa réunion (par exemple, si la propriété EnableDataCollaboration de sa stratégie de conférence est définie sur false), la cmdlet **test-CsUcwaConference** échouera.

  - Cette commande échoue si le serveur Edge est mal configuré ou s’il n’est pas encore déployé.

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

