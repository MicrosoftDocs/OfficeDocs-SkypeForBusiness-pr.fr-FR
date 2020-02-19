---
title: 'Lync Server 2013 : test de l’appel téléphonique RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3678a38e8f95b87b08283203ec3f16fd9dfd4ee3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a>Test de l’appel téléphonique RTC dans Lync Server 2013

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
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

La cmdlet Test-CsPstnOutboundCall teste la capacité d’un utilisateur à appeler un numéro de téléphone situé sur le RTC. Lors de l’exécution de test-CsPstnOutboundCall, la cmdlet tente d’abord de connecter l’utilisateur de test à Lync Server. Si l’ouverture de session réussit, l’applet de commande tente alors d’effectuer un appel téléphonique via la passerelle PSTN. Cet appel téléphonique sera effectué à l’aide du plan de numérotation, de la stratégie de voix, ainsi que d’autres stratégies et paramètres affectés au compte de test. Lorsque l’appel reçoit une réponse, l’applet de commande envoie des codes DTMF (Dual-Tone Multi-Frequency) sur le réseau pour vérifier la connectivité multimédia.

Lors de la réalisation d’un test, Test-CsPstnOutboundCall passe un appel téléphonique réel : le téléphone cible retentit et doit être décroché pour que le test réussisse. Par ailleurs, cet appel doit être conclu manuellement par l’administrateur.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-CsPstnOutboundCall peut être exécutée à l’aide d’un compte de test préconfiguré (consultez la rubrique Configuration des comptes de test pour l’exécution des tests Lync Server) ou du compte de tout utilisateur activé pour Lync Server. Pour exécuter cette vérification à l’aide d’un compte de test, il vous suffit de spécifier le nom de domaine complet (FQDN) du pool Lync Server testé et le numéro de téléphone PSTN appelé. Par exemple :

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

Pour exécuter cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell qui contient le nom de compte et le mot de passe. Vous devez ensuite inclure cet objet d’informations d’identification et l’adresse SIP attribuée au compte lorsque vous appelez test-CsPstnOutboundCall :

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si l’utilisateur spécifié peut passer l’appel et si l’appel reçoit une réponse, vous recevrez un résultat semblable à celui-ci, avec la propriété Result marquée with **Success :**

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:06.8630376

«

Diagnostique

Si l’utilisateur spécifié ne peut pas passer l’appel ou si l’appel n’a pas reçu de réponse, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:0987365

Erreur : 403, interdit

Diagnostic : ErrorCode = 12001, source = ATL-CS-001. litwareinc. com, Reason = User

La stratégie ne contient pas d’utilisation de l’itinéraire téléphonique

La sortie précédente indique que le test a échoué car la stratégie de voix attribuée à l’utilisateur spécifié n’inclut pas d’utilisation téléphonique. (Les utilisations téléphoniques lient les stratégies vocales aux itinéraires des communications vocales. Sans une stratégie de voix et un itinéraire de communications vocales correspondant, vous ne pouvez pas effectuer d’appels sur le réseau téléphonique commuté (RTC).)

Si test-CsPstnOutboundCall échoue, vous pouvez réexécuter le test, ce qui inclut le paramètre Verbose :

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

Lorsque le paramètre Verbose est inclus, test-CsPstnOutboundCall renvoie un compte pas à pas de chaque action qu’il a tentée lorsqu’il a vérifié la capacité de l’utilisateur spécifié à se connecter à Lync Server. Par exemple, cette sortie indique que des problèmes réseau empêchent une connexion au réseau téléphonique commuté (RTC) :

Établissement de l’appel audio vidéo à « SIP : + 12065551219@litwareinc. com ; user = Phone ».

Une exception’A 404 (introuvable) a été reçue du réseau et l’opération a échoué.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec de test-CsPstnOutboundCall :

  - Vous avez spécifié un compte d’utilisateur non valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

  - La stratégie de voix attribuée à l’utilisateur spécifié ne dispose pas d’une utilisation PSTN valide. Vous pouvez déterminer la stratégie de voix qui est affectée à un utilisateur à l’aide d’une commande semblable à celle-ci :
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    Vous pouvez ensuite déterminer les utilisations PSTN (le cas échéant) qui sont affectées à cette stratégie à l’aide d’une commande semblable à la suivante, qui récupère des informations sur la stratégie de voix par utilisateur RedmondVoicePolicy :
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

