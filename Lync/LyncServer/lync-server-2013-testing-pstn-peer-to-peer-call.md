---
title: 'Lync Server 2013: test de l’appel d’égal à égal PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51b74697c7d6d5a037537bb036494d89264c4e75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a>Test de l’appel d’égal à égal RTC dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsPstnPeerToPeerCall. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsPstnPeerToPeerCall vérifie la possibilité pour une paire d’utilisateurs d’effectuer un appel d’égal à égal sur la passerelle RTC (réseau téléphonique commuté). Lorsque vous appelez test-CsPstnPeerToPeerCall, l’applet de connexion tente d’abord de se connecter à deux utilisateurs de test sur Lync Server. En supposant que les ouvertures de session aboutissent, l’applet de connexion a alors une tentative d’appel de la part de l’utilisateur 2 par le biais de la passerelle RTC. Test-CsPstnPeerToPeerCall effectue l’appel à l’aide du plan de numérotation, de la stratégie vocale et d’autres paramètres de stratégie et de configuration attribués à l’utilisateur de test. Si le test s’exécute comme prévu, l’applet de connexion vérifie que l’utilisateur 2 a pu répondre à l’appel, puis déconnecte les deux comptes de test du système.

Test-CsPstnPeerToPeerCall effectue un appel téléphonique réel et vérifie qu’il est possible d’établir une connexion et qu’elle transmet également des codes DTMF sur le réseau pour déterminer si le média peut être envoyé sur la connexion. L’appel est alors reçu par l’applet de demande et aucune terminaison manuelle de l’appel n’est nécessaire. (Autrement dit, personne ne doit répondre et raccrocher le téléphone appelé.)

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’applet de contrôle test-CsPstnPeerToPeerCall peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou les comptes de tous les utilisateurs qui sont activés pour Lync Server. Pour exécuter cette vérification à l’aide de comptes de test, vous devez simplement spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé. Par exemple :

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

Pour exécuter ce contrôle à l’aide de comptes d’utilisateurs réels, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte. Vous devez alors inclure ces objets d’informations d’identification et les adresses SIP des deux comptes lors de l’appel de test-CsPstnPeerToPeerCall:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si les utilisateurs spécifiés peuvent effectuer un appel d’égal à égal, vous recevrez une sortie semblable à celle-ci, avec la propriété Result marquée comme **réussie:**

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: réussite

Latence: 00:00:06.8630376

Error

Diagnostic

Si les utilisateurs spécifiés ne parviennent pas à effectuer un appel d’égal à égal, le résultat est affiché en tant qu’échec et des informations supplémentaires seront enregistrées dans les propriétés d’erreur et de diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: échec

Latence: 00:00:0182361

Erreur: 403, interdit

Diagnostic: codeerreur = 12001, source = ATL-CS-001.litwareinc.com,

Raison = la stratégie utilisateur ne contient pas l’utilisation de l’itinéraire du téléphone

La sortie précédente indique que le test a échoué, car la stratégie vocale affectée à au moins un des utilisateurs spécifiés n’inclut pas une utilisation du téléphone. (Les utilisations du téléphone lient les politiques vocales aux itinéraires vocaux. Sans qu’il s’agissait d’une stratégie vocale et d’un itinéraire vocal correspondant, vous ne pouvez pas passer d’appels sur PSTN.)

Si test-CsPstnPeerToPeerCall échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose:

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, test-CsPstnPeerToPeerCall renvoie un compte étape par étape de chaque action qu’il a effectuée lors de la vérification de la possibilité de l’utilisateur spécifié de se connecter à Lync Server. Par exemple, cette sortie indique que des problèmes réseau empêchent une connexion avec le RTC:

Etablissement d’un appel vidéo audio sur’SIP: +12065551219@litwareinc.com; utilisateur = téléphone'.

Une exception «une 404 (non trouvée) a été reçue du réseau et l’opération a échoué.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsPstnPeerToPeerCall peuvent échouer:

  - Vous avez spécifié un compte d’utilisateur qui n’est pas valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à ce qui suit:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

  - La stratégie vocale attribuée à l’utilisateur spécifié ne dispose pas d’une utilisation PSTN valide. Vous pouvez déterminer la politique vocale affectée à un utilisateur à l’aide d’une commande similaire à celle-ci:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    Vous pouvez ensuite déterminer les utilisations RTC qui sont affectées à cette stratégie à l’aide d’une commande similaire à ce qui suit, qui extrait des informations sur le RedmondVoicePolicy de stratégie vocale par utilisateur:
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

