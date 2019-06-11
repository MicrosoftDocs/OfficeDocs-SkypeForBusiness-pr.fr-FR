---
title: 'Lync Server 2013: test de la possibilité de connexion d’un utilisateur à Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adf6cae2899d08765faf5d605ea20ae111f395ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>Test de la capacité d’un utilisateur à se connecter à Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-06-05_


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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsRegistration. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsRegistration vous permet de vérifier que les utilisateurs de votre organisation peuvent se connecter au serveur Lync. Lorsque vous exécutez test-CsRegistration, l’applet de connexion tente de se connecter à un utilisateur de test sur Lync Server, puis, si elle est réussie, déconnecte l’utilisateur de test du système. Tout cela se produit sans aucune interaction de l’utilisateur, sans affecter les utilisateurs réels. Par exemple, supposons que le compte de test sip:kenmyer@litwareinc.com correspond à un utilisateur réel possédant un compte de serveur Lync réel. Dans ce cas, le test sera mené sans interruption pour le véritable Ken Myer. Lorsque le compte de test Ken Myer se déconnecte du système, Ken Myer la personne reste connectée.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Vous pouvez exécuter l’applet de contrôle test-CsRegistration à l’aide d’un compte de test préconfiguré (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou du compte d’un utilisateur qui est activé pour Lync Server. Pour effectuer cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet (FQDN) du pool d’inscriptions du serveur Lync testé. Par exemple :

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

Pour effectuer cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell contenant le nom et le mot de passe du compte. Vous devez alors inclure cet objet Credential et l’adresse SIP attribuée au compte lorsque vous appelez le test-CsRegistration:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si l’utilisateur spécifié peut se connecter à (et se déconnecter de) Lync Server, vous recevrez une sortie semblable à ce qui suit avec la propriété Result marquée comme **réussie:**

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: réussite

Latence: 00:00:06.8630376

Error

Diagnostic

Si l’utilisateur spécifié ne peut pas se connecter ou se déconnecter, le résultat est affiché en tant qu’échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: échec

Latence: 00:00:00

Erreur: 404, introuvable

Diagnostic: codeerreur = 1003, source = ATL-CS-001. litwareinc. com, Reason = utilisateur

existe pas

Microsoft. RTC. signalisation. DiagnosticHeader

Par exemple, l’état précédent de sortie a échoué en raison de l’échec de la recherche de l’utilisateur spécifié. Vous pouvez déterminer si une adresse SIP est valide (et si l’utilisateur a activé cette adresse SIP pour Lync Server) en exécutant la commande suivante:

    Get-CsUser "sip:kenmyer@litwareinc.com"

Si test-CsRegistration échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose:

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, test-CsRegistration renvoie un compte étape par étape de chaque action qu’il a effectuée lors de la vérification de la possibilité de l’utilisateur spécifié de se connecter à Lync Server. Par exemple :

DÉTAILLÉ: activité de’Register’démarrée.

Envoi de la demande d’inscription:

Nom de domaine complet cible = atl-cs-011.litwareinc.com

Adresse SIP de l’utilisateur = sip:kenmyer@litwareinc.com

Port du Bureau d’enregistrement = 5061.

Le type d’authentification «approuvé» est sélectionné.

Exception: le point de terminaison ne peut pas s’inscrire. Voir le code d’erreur pour une raison précise qu’il s’est produit lors de l’exécution du flux de travail Microsoft. RTC. SyntheticTransactions. Workflow. STRegistrerWorkflow.

Pile d’appels d’exception: Microsoft. RTC. signalisation. SipAsyncResult'1. ThrowIfFailed ()

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsRegistration peuvent échouer:

  - Vous avez spécifié un compte d’utilisateur incorrect. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à ce qui suit:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

  - Vous avez spécifié un pool d’inscriptions incorrect. Vous pouvez renvoyer les noms de domaine complets de vos pools de bureaux d’enregistrement à l’aide de la commande suivante:
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - Le pool d’inscriptions n’est pas disponible pour le moment. Essayez d’utiliser la commande ping du pool pour voir s’il répond:
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

