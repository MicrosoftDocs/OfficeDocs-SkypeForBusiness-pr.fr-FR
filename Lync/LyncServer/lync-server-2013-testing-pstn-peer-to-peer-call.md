---
title: 'Lync Server 2013 : test des appels d’égal à égal PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33aa0447c90ea9c76a1956cb817f0e61ce0d626e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504041"
---
# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a>Test des appels d’égal à égal RTC dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<td><p>Journalière</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsPstnPeerToPeerCall. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande Test-CsPstnPeerToPeerCall vérifie si une paire d’utilisateurs doit effectuer un appel P2P sur la passerelle PSTN (réseau téléphonique commuté). Lorsque vous appelez test-CsPstnPeerToPeerCall, l’applet de commande tente d’abord de se connecter deux utilisateurs de test à Lync Server. En supposant que les ouvertures de sessions réussissent, l’utilisateur 1 tentera d’appeler l’utilisateur 2 sur la passerelle PSTN. Test-CsPstnPeerToPeerCall effectuera cet appel à l’aide du plan de numérotation, de la stratégie de voix, ainsi que d’autres paramètres de stratégie et de configuration affectés à l’utilisateur test. Si le test se déroule comme prévu, l’applet de commande vérifie que l’utilisateur 2 a pu répondre à l’appel, puis se déconnecte des deux comptes de test à partir du système.

Test-CsPstnPeerToPeerCall effectue un appel téléphonique réel, qui vérifie qu’une connexion peut être établie et qui transmet également des codes DTMF sur le réseau pour déterminer si des médias peuvent être envoyés via la connexion. L’appel est traité par l’applet de commande elle-même et aucune interruption manuelle de l’appel n’est nécessaire. (Autrement dit, personne ne doit répondre, puis raccrocher le téléphone qui a été appelé.)

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-CsPstnPeerToPeerCall peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou des comptes de deux utilisateurs activés pour Lync Server. Pour exécuter cette vérification à l’aide de comptes de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé. Par exemple :

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

Pour exécuter cette vérification à l’aide de comptes d’utilisateur réels, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte. Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsque vous appelez test-CsPstnPeerToPeerCall :

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si les utilisateurs spécifiés peuvent effectuer un appel P2P, vous recevrez un résultat semblable à celui-ci, la propriété Result étant marquée comme **Success :**

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:06.8630376

«

Diagnostique

Si les utilisateurs spécifiés ne peuvent pas effectuer un appel P2P, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:0182361

Erreur : 403, interdit

Diagnostic : ErrorCode = 12001, source = ATL-CS-001.litwareinc.com,

Raison = la stratégie de l’utilisateur ne contient pas l’utilisation de l’itinéraire téléphonique

La sortie précédente indique que le test a échoué car la stratégie de voix attribuée à au moins un des utilisateurs spécifiés n’inclut pas d’utilisation téléphonique. (Les utilisations téléphoniques lient les stratégies vocales aux itinéraires des communications vocales. Sans une stratégie de voix ni un itinéraire des communications vocales, vous ne pouvez pas passer d’appels sur le RTC.)

Si Test-CsPstnPeerToPeerCall échoue, vous pouvez réexécuter le test, en incluant cette fois le paramètre Verbose :

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, Test-CsPstnPeerToPeerCall renvoie un compte pas à pas de chaque action effectuée lors de la vérification de la capacité de l’utilisateur spécifié à se connecter à Lync Server. Par exemple, cette sortie indique que des problèmes réseau empêchent une connexion au réseau téléphonique commuté (RTC) :

Établissement de l’appel audio vidéo à « SIP : + 12065551219@litwareinc. com ; user = Phone ».

Une exception’A 404 (introuvable) a été reçue du réseau et l’opération a échoué.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques raisons courantes pour lesquelles Test-CsPstnPeerToPeerCall peut échouer :

  - Vous avez spécifié un compte d’utilisateur qui n’est pas valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :
    
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

