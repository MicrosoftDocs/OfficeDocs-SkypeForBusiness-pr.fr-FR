---
title: 'Lync Server 2013: test de Web Scheduler'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: beb4030a87302c8abaaba9418eaba06b831ed8d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a>Test de Web Scheduler dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande <strong>test-CsWebScheduler</strong> . Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de **contrôle test-CsWebScheduler** vous permet de déterminer si un utilisateur spécifique peut planifier une réunion à l’aide de Web Scheduler. Web Scheduler permet aux utilisateurs qui n’exécutent pas Outlook de planifier des réunions en ligne. Entre autres choses, cette nouvelle fonctionnalité (qui incorpore les fonctionnalités disponibles dans l’outil Web Scheduler inclus dans le kit de ressources Microsoft Lync Server 2010) permet aux utilisateurs d’effectuer les opérations suivantes:

  - Planifier une nouvelle réunion en ligne.

  - Répertorier toutes les réunions qu’il a planifiées.

  - Afficher/modifier une réunion existante.

  - Supprimez une réunion existante.

  - Envoyez une invitation électronique aux participants à la réunion à l’aide d’un serveur de messagerie SMTP préconfiguré.

  - Participez à une conférence existante.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’exemple suivant vérifie le planificateur Web pour le pool atl-cs-001.litwareinc.com. Cette commande ne fonctionne que si les utilisateurs de test sont définis pour le pool atl-cs-001.litwareinc.com. Si tel est le cas, la commande détermine si le premier utilisateur du test peut planifier une réunion en ligne à l’aide de Web Scheduler.

Si les utilisateurs de test ne sont pas définis, la commande échoue, car il ne connaît pas l’utilisateur sur lequel se connecter. Si vous n’avez pas défini les utilisateurs test pour un pool, vous devez inclure le paramètre UserSipAddress et les informations d’identification de l’utilisateur que la commande doit utiliser lors de la tentative de connexion.

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

Les commandes indiquées dans l’exemple suivant testent la capacité d’un utilisateur spécifique (\\litwareinc kenmeyer) pour planifier une réunion en ligne à l’aide de Web Scheduler. Pour cela, la première commande de l’exemple utilise l’applet de commande **Get-Credential** pour créer un objet d’informations d’identification d’interface de ligne de commande Windows PowerShell contenant le nom et le mot de passe de l’utilisateur Ken Meyer. (Dans la mesure où le\\nom de connexion litwareinc kenmeyer est inclus en tant que paramètre, la boîte de dialogue demande d’informations d’identification Windows PowerShell nécessite uniquement que l’administrateur entre le mot de passe du compte Ken Meyer.) L’objet Credential obtenu est ensuite stocké dans une variable nommée $cred 1.

La deuxième commande vérifie que l’utilisateur peut se connecter au pool atl-cs-001.litwareinc.com et planifier une réunion en ligne. Pour exécuter cette tâche, l’applet de **contrôle test-CsWebScheduler** est appelée, avec trois paramètres: TargetFqdn (nom de domaine complet du pool d’inscriptions); UserCredential (l’objet Windows PowerShell contenant les informations d’identification de l’utilisateur de Pilar Arès); et UserSipAddress (adresse SIP correspondant aux informations d’identification fournies par l’utilisateur).

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si Web Scheduler est correctement configuré, vous recevrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie**:

Nom de domaine complet (FQDN) cible: atl-cs-001.litwareinc.com

URI cible: https://atl-cs-001.litwareinc.com.

litwareinc.com:443/Scheduler

Résultat: réussite

Latence: 00:00:00

Message d’erreur:

Diagnostic

Si Web Scheduler n’est pas configuré correctement, le résultat est affiché en tant qu' **échec**et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic:

AVERTISSEMENT: impossible de lire le numéro de port du Bureau d’enregistrement pour le nom complet fourni

nom de domaine (FQDN). Utilisation du numéro de port de bureau par défaut. Sauf

System. InvalidOperationException: aucun cluster correspondant détecté dans la topologie.

dès

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Nom de domaine complet (FQDN) cible: atl-cs-001.litwareinc.com

URI de destination:

Résultat: échec

Latence: 00:00:00

Message d’erreur: aucun cluster correspondant détecté dans la topologie.

Diagnostic

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles **les tests-CsWebScheduler** peuvent échouer:

  - Une valeur de paramètre incorrecte a été fournie. S’il est utilisé, les paramètres facultatifs doivent être correctement configurés ou le test échoue. Réexécutez la commande sans les paramètres facultatifs et déterminez si l’opération aboutit.

  - Cette commande échoue si Web Scheduler n’est pas configuré correctement ou n’est pas encore déployé.

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

