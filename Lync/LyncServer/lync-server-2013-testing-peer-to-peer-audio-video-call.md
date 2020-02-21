---
title: 'Lync Server 2013 : test de l’appel audio/vidéo d’égal à égal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea5283f588315d06387ed2d441f138538cd13ca3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a>Test des appels audio/vidéo d’égal à égal dans Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsP2PAV. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Test-CsP2PAV est utilisé pour déterminer si une paire d’utilisateurs de test peut participer à une conversation A/V P2P. Pour tester ce scénario, la cmdlet démarre en ouvrant une session sur les deux utilisateurs sur Lync Server. Si les deux connexions réussissent, le premier utilisateur invite alors le deuxième à participer à un appel audio/vidéo. Le deuxième utilisateur accepte l’appel, la connexion entre les deux utilisateurs est testée, puis l’appel est mené à son terme et enfin les utilisateurs de test sont déconnectés du système.

Test-CsP2PAV n’effectue pas réellement un appel A/V. Les informations multimédias ne sont pas échangées entre les utilisateurs de test. Au lieu de cela, l’applet de commande vérifie simplement que les connexions appropriées peuvent être établies et que les deux utilisateurs peuvent effectuer un tel appel.

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) .

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-CsP2PAV peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou des comptes de deux utilisateurs activés pour Lync Server. Pour exécuter cette vérification à l’aide de comptes de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé. Par exemple :

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

Pour exécuter cette vérification à l’aide de comptes d’utilisateur réels, vous devez créer deux objets d’informations d’identification Lync Server (objets contenant le nom de compte et le mot de passe) pour chaque compte. Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsque vous appelez test-CsP2PAV :

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si les deux utilisateurs de test peuvent effectuer un appel A/V P2P, vous recevrez un résultat similaire à celui-ci avec la propriété Result marquée comme **Success :**

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:06.8630376

«

Diagnostique

Si les utilisateurs test ne peuvent pas effectuer l’appel, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Erreur : 480, temporairement indisponible

Diagnostic : ErrorCode = 15030, source = ATL-CS-001. litwareinc. com, Reason = failed

pour acheminer vers Exchange Server

Microsoft. RTC. signalisation. DiagnosticHeader

Par exemple, la sortie précédente indique que le test a échoué, car le serveur Microsoft Exchange n’a pas pu être contacté. Ce message d’erreur indique généralement un problème de configuration de la messagerie unifiée Exchange.

Si test-CsP2PAV échoue, vous pouvez réexécuter le test, ce qui inclut le paramètre Verbose :

Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose

Lorsque le paramètre Verbose est inclus, test-CsP2PAV renvoie un compte pas à pas de chaque action qu’il a effectuée lors de la vérification de la capacité de l’utilisateur spécifié à se connecter à Lync Server. Par exemple, supposons que votre test a échoué avec le diagnostic suivant :

ErrorCode = 6003, source = ATL-CS-001. litwareinc. com, Reason = non pris en charge par la requête de boîte de dialogue

Si vous réexécutez test-CsP2PAV et que vous incluez le paramètre Verbose, vous obtiendrez un résultat semblable à celui-ci :

VERBOSe : activité « enregistrer » démarrée.

Envoi d’une demande d’inscription :

Nom de domaine complet cible = atl-cs-011.litwareinc.com

Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com

Port de serveur d’inscriptions = 5062.

Le type d’authentification « IWA » est sélectionné.

Une exception’le point de terminaison n’a pas pu s’inscrire. Voir le code d’ErrorCode pour des raisons spécifiques. s’est produite lors de l’exécution de flux de travail Microsoft. RTC. SyntheticTransactions. workflows. STP2PAVWorkflow.

Bien qu’il ne soit pas immédiatement visible, si vous examinez attentivement la sortie, vous verrez qu’un port de serveur d’inscriptions incorrect (port 5062) a été spécifié. À son tour, ce qui a provoqué l’échec du test.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec de test-CsP2PAV :

  - Vous avez spécifié un compte d’utilisateur qui n’est pas valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :
    
    Get-CsUser "sip :kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

