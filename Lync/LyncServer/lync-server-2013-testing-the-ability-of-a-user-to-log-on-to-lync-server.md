---
title: 'Lync Server 2013 : test de la capacité d’un utilisateur à se connecter à Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71629cb844b8f65ab6f54c0d604fad0d152705d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>Test de la capacité d’un utilisateur à se connecter à Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-06-05_


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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsRegistration. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande test-CsRegistration vous permet de vérifier que les utilisateurs de votre organisation peuvent se connecter à Lync Server. Lorsque vous exécutez test-CsRegistration, l’applet de commande tente de se connecter à un utilisateur de test sur Lync Server, puis, si elle réussit, déconnecte cet utilisateur de test du système. Tout cela se passe sans aucune intervention de l’utilisateur et ce, sans affecter aucun utilisateur. Par exemple, supposons que le compte de test sip :kenmyer@litwareinc.com correspond à un utilisateur réel qui possède un compte de serveur Lync réel. Dans ce cas, le test sera effectué sans interrompre les activités de l’utilisateur réel Ken Myer. Lorsque le compte de test Ken Myer se déconnecte du système, Ken Myer la personne reste connectée.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-CsRegistration peut être exécutée à l’aide d’un compte de test préconfiguré (consultez la rubrique Configuration des comptes de test pour l’exécution des tests Lync Server) ou du compte de tout utilisateur activé pour Lync Server. Pour exécuter cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet (FQDN) du pool de serveurs d’inscriptions Lync Server testé. Par exemple :

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell qui contient le nom de compte et le mot de passe. Vous devez ensuite inclure cet objet d’informations d’identification et l’adresse SIP attribuée au compte lorsque vous appelez test-CsRegistration :

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si l’utilisateur spécifié peut se connecter à (puis se déconnecter de) Lync Server, vous recevrez un résultat semblable à celui-ci avec la propriété Result marquée comme **Success :**

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:06.8630376

«

Diagnostique

Si l’utilisateur spécifié ne peut pas se connecter ou se déconnecter, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Erreur : 404, introuvable

Diagnostic : ErrorCode = 1003, source = ATL-CS-001. litwareinc. com, Reason = l’utilisateur ne

existe pas

Microsoft. RTC. signalisation. DiagnosticHeader

Par exemple, la sortie précédente indique que le test a échoué, car l’utilisateur spécifié est introuvable. Vous pouvez déterminer si une adresse SIP est valide (et si l’utilisateur auquel cette adresse SIP est attribuée est activée pour Lync Server) en exécutant la commande suivante :

    Get-CsUser "sip:kenmyer@litwareinc.com"

Si test-CsRegistration échoue, vous pouvez réexécuter le test, ce qui inclut le paramètre Verbose :

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, test-CsRegistration renvoie un compte pas à pas de chaque action qu’il a tentée lorsqu’il a vérifié la capacité de l’utilisateur spécifié à se connecter à Lync Server. Par exemple :

VERBOSe : activité « enregistrer » démarrée.

Envoi d’une demande d’inscription :

Nom de domaine complet cible = atl-cs-011.litwareinc.com

Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com

Port de serveur d’inscriptions = 5061.

Le type d’authentification « approuvé » est sélectionné.

Une exception’le point de terminaison ne peut pas s’inscrire. Voir le code d’erreur pour une raison spécifique» s’est produit lors de l’exécution du flux de travail Microsoft. RTC. SyntheticTransactions. Workflow. STRegistrerWorkflow.

Pile des appels d’exception : at Microsoft. RTC. signalisation. SipAsyncResult'1. ThrowIfFailed ()

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec de test-CsRegistration :

  - Vous avez spécifié un compte d’utilisateur incorrect. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

  - Vous avez spécifié un pool de serveurs d’inscriptions incorrect. Vous pouvez renvoyer les noms de domaine complets de vos pools de serveurs d’inscriptions à l’aide de la commande suivante :
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - Le pool de serveurs d’inscriptions n’est pas disponible actuellement. Essayez d’exécuter une commande ping sur le pool pour voir s’il répond :
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

