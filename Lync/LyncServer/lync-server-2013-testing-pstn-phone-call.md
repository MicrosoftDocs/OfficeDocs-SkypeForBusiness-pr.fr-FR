---
title: 'Lync Server 2013: test d’appel téléphonique PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 641b2f77079fee100d8f3ac85a1a7580d7cf7d84
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a>Test de l’appel téléphonique PSTN dans Lync Server 2013

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
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsPstnOutboundCall teste la possibilité pour un utilisateur de passer un appel à un numéro de téléphone situé sur le RTC. Lorsque vous exécutez test-CsPstnOutboundCall, l’applet de connexion tente d’abord de consigner l’utilisateur de test sur Lync Server. En cas de réussite de l’ouverture de session, l’applet de passe tente alors d’effectuer un appel téléphonique via la passerelle RTC. Cet appel téléphonique sera réalisé à l’aide du plan de numérotation, de la politique vocale et d’autres stratégies et paramètres attribués au compte de test. Lorsque l’appel est reçu, l’applet de connexion envoie des codes à deux tonalités (DTMF) sur le réseau pour vérifier la connectivité multimédia.

Lors de ses tests, le test-CsPstnOutboundCall effectue un appel réel: le téléphone cible sonne et répond au succès du test. Cet appel doit également être arrêté manuellement par l’administrateur.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

Vous pouvez exécuter l’applet de contrôle test-CsPstnOutboundCall à l’aide d’un compte de test préconfiguré (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou du compte d’un utilisateur qui est activé pour Lync Server. Pour effectuer cette vérification à l’aide d’un compte de test, vous devez simplement spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé et le numéro de téléphone RTC appelé. Par exemple :

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

Pour effectuer cette vérification à l’aide d’un compte d’utilisateur réel, vous devez d’abord créer un objet d’informations d’identification Windows PowerShell contenant le nom et le mot de passe du compte. Vous devez alors inclure cet objet Credential et l’adresse SIP attribuée au compte lorsque vous appelez le test-CsPstnOutboundCall:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si l’utilisateur spécifié peut effectuer l’appel et si l’appel est reçu, vous recevrez une sortie semblable à ce qui suit, avec la propriété Result marquée comme **réussie:**

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: réussite

Latence: 00:00:06.8630376

Error

Diagnostic

Si l’utilisateur spécifié ne peut pas effectuer l’appel ou si l’appel n’a pas de réponse, le résultat s’affichera en tant qu’échec et des informations supplémentaires seront enregistrées dans les propriétés d’erreur et de diagnostic:

TargetFqdn: atl-cs-001.litwareinc.com

Résultat: échec

Latence: 00:00:0987365

Erreur: 403, interdit

Diagnostic: codeerreur = 12001, source = ATL-CS-001. litwareinc. com, Reason = utilisateur

La stratégie ne contient pas l’utilisation de l’itinéraire du téléphone

La sortie précédente indique que le test a échoué, car la stratégie vocale affectée à l’utilisateur spécifié n’inclut pas une utilisation du téléphone. (Les utilisations du téléphone lient les politiques vocales aux itinéraires vocaux. Sans qu’il s’agissait d’une stratégie vocale et d’un itinéraire vocal correspondant, vous ne pouvez pas passer d’appels sur PSTN.)

Si test-CsPstnOutboundCall échoue alors, vous souhaiterez peut-être réexécuter le test, cette fois-ci, y compris le paramètre Verbose:

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

Lorsque le paramètre Verbose est inclus, test-CsPstnOutboundCall renvoie un compte étape par étape de chaque action qu’il a effectuée lors de la vérification de la possibilité de l’utilisateur spécifié de se connecter à Lync Server. Par exemple, cette sortie indique que des problèmes réseau empêchent une connexion avec le RTC:

Etablissement d’un appel vidéo audio sur’SIP: +12065551219@litwareinc.com; utilisateur = téléphone'.

Une exception «une 404 (non trouvée) a été reçue du réseau et l’opération a échoué.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsPstnOutboundCall peuvent échouer:

  - Vous avez spécifié un compte d’utilisateur non valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit:
    
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

