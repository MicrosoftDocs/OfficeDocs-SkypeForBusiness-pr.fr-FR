---
title: 'Lync Server 2013 : test du planificateur Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b385184486cdbf8e2ee18956df1546d09335e6c8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503941"
---
# <a name="testing-the-web-scheduler-in-lync-server-2013"></a>Test du planificateur Web dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<td><p>Journalière</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-applet cswebscheduler</strong> . Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande **test-applet cswebscheduler** vous permet de déterminer si un utilisateur spécifique peut planifier une réunion à l’aide du planificateur Web. Le planificateur Web permet aux utilisateurs qui n’exécutent pas Outlook de planifier des réunions en ligne. Entre autres, cette nouvelle fonctionnalité (qui intègre les fonctionnalités de l’outil Web Scheduler fourni avec le kit de ressources Microsoft Lync Server 2010) permet aux utilisateurs d’effectuer les opérations suivantes :

  - planifier une nouvelle réunion en ligne ;

  - dresser une liste de toutes les réunions qu’ils ont planifiées ;

  - afficher/modifier une réunion existante ;

  - supprimer une réunion existante ;

  - envoyer une invitation par courrier électronique aux participants aux réunions par le biais d’un serveur de messagerie SMTP ;

  - participer à une conférence existante.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’exemple suivant vérifie le planificateur Web pour le pool atl-cs-001.litwareinc.com. Cette commande fonctionne uniquement si les utilisateurs de test sont définis pour le pool atl-cs-001.litwareinc.com. Si c’est le cas, la commande détermine si le premier utilisateur de test peut planifier une réunion en ligne à l’aide du planificateur Web.

Si les utilisateurs de test ne sont pas définis, la commande échoue, car elle ne peut pas identifier l’utilisateur sous lequel se connecter. Si vous n’avez pas défini les utilisateurs de test pour un pool, vous devez inclure le paramètre UserSipAddress et les informations d’identification de l’utilisateur que la commande doit utiliser lors de la tentative de connexion.

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

Les commandes présentées dans l’exemple suivant testent la capacité d’un utilisateur spécifique (litwareinc \\ kenmeyer) à planifier une réunion en ligne à l’aide du planificateur Web. Pour ce faire, la première commande de l’exemple utilise la cmdlet **Get-Credential** pour créer un objet d’informations d’identification de l’interface de ligne de commande Windows PowerShell qui contient le nom et le mot de passe de l’utilisateur Ken Meyer. (Étant donné que le nom de connexion litwareinc \\ kenmeyer est inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell nécessite uniquement que l’administrateur entre le mot de passe du compte Ken Meyer.) L’objet Credential qui en résulte est ensuite stocké dans une variable nommée $cred 1.

La deuxième commande vérifie ensuite si cet utilisateur peut se connecter au pool atl-cs-001.litwareinc.com et planifier une réunion en ligne. Pour exécuter cette tâche, la cmdlet **test-applet cswebscheduler** est appelée, ainsi que trois paramètres : TargetFqdn (le nom de domaine complet du pool de serveurs d’inscriptions); UserCredential (l’objet Windows PowerShell qui contient les informations d’identification de l’utilisateur de Pilar Ackerman); et UserSipAddress (l’adresse SIP qui correspond aux informations d’identification de l’utilisateur fourni).

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si le planificateur Web est configuré correctement, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée comme **Success**:

Nom de domaine complet cible : atl-cs-001.litwareinc.com

URI cible : https://atl-cs-001.litwareinc.com.

litwareinc.com:443/Scheduler

Résultat : opération réussie

Latence : 00:00:00

Message d’erreur :

Diagnostique

Si le planificateur Web n’est pas configuré correctement, le résultat est affiché sous la forme **échec**et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

AVERTISSEMENT : impossible de lire le numéro de port du serveur d’inscriptions pour le serveur complet

nom de domaine (FQDN). À l’aide du numéro de port de serveur d’inscriptions par défaut. Rogation

System. InvalidOperationException : aucun cluster correspondant n’a été trouvé dans la topologie.

Regardez

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Nom de domaine complet cible : atl-cs-001.litwareinc.com

URI cible :

Résultat : échec

Latence : 00:00:00

Message d’erreur : aucun cluster correspondant n’a été trouvé dans la topologie.

Diagnostique

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec **de test-applet cswebscheduler** :

  - Une valeur de paramètre incorrecte a été fournie. Si ce paramètre est utilisé, les paramètres facultatifs doivent être configurés correctement ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.

  - Cette commande échoue si le planificateur Web est configuré de façon incorrecte ou s’il n’est pas encore déployé.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Set-CsWebServer](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

