---
title: 'Lync Server 2013 : test des appels audio et vidéo d’égal à égal'
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
ms.openlocfilehash: e319ace4ee4cc6613ac5ed29659ac14c5853d7b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a>Test de l’appel audio/vidéo d’égal à égal dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsP2PAV. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

Test-CsP2PAV est utilisé pour déterminer si un binôme peut participer à une conversation A/V pair-à-pair. Pour tester ce scénario, l’applet de connexion démarre en se connectant aux deux utilisateurs de Lync Server. En supposant que les deux ouvertures de session aboutissent, le premier utilisateur invite alors le second utilisateur à rejoindre un appel A/V. Le deuxième utilisateur accepte l’appel, le lien entre les deux utilisateurs est testé, puis l’appel est terminé et les utilisateurs de test sont déconnectés du système.

Test-CsP2PAV n’effectue pas réellement d’appel A/V. Les informations multimédias ne sont pas échangées entre les utilisateurs test. Au lieu de cela, l’applet de demande vérifie simplement que les connexions appropriées peuvent être établies et que les deux utilisateurs peuvent effectuer un tel appel.

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) .

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’applet de contrôle test-CsP2PAV peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou les comptes de tous les utilisateurs qui sont activés pour Lync Server. Pour exécuter cette vérification à l’aide de comptes de test, vous devez simplement spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé. Par exemple :

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

Pour exécuter cette vérification à l’aide de comptes d’utilisateurs réels, vous devez créer deux objets d’informations d’identification Lync Server (objets contenant le nom de compte et le mot de passe) pour chaque compte. Vous devez alors inclure ces objets d’informations d’identification et les adresses SIP des deux comptes lors de l’appel de test-CsP2PAV :

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si les deux utilisateurs de test peuvent effectuer un appel A/V d’égal à égal, vous recevrez une sortie semblable à ce qui suit avec la propriété Result marquée comme **réussie :**

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : réussite

Latence : 00:00:06.8630376

Error

Diagnostic

Si les utilisateurs ne parviennent pas à effectuer l’appel, le résultat est affiché en tant qu’échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Erreur : 480, temporairement indisponible

Diagnostic : codeerreur = 15030, source = ATL-CS-001. litwareinc. com ; raison = échec

pour acheminer vers Exchange Server

Microsoft. RTC. signalisation. DiagnosticHeader

Par exemple, la sortie précédente indique que le test a échoué, car le serveur Microsoft Exchange n’a pas pu être contacté. Ce message d’erreur indique généralement un problème de configuration de la messagerie unifiée Exchange.

Si test-CsP2PAV échoue alors, vous souhaiterez peut-être réexécuter le test, cette fois-ci, y compris le paramètre Verbose :

Test-CsP2PAV-TargetFqdn « atl-cs-001.litwareinc.com »-détails

Lorsque le paramètre Verbose est inclus, test-CsP2PAV renvoie un compte étape par étape de chaque action qu’il a effectuée lors de la vérification de la capacité de l’utilisateur à se connecter à Lync Server. Par exemple, supposons que votre test ait échoué avec le diagnostic suivant :

Codeerreur = 6003, source = ATL-CS-001. litwareinc. com ; raison = non prise en charge d’une demande de boîte de dialogue

Si vous exécutez de nouveau test-CsP2PAV et incluez le paramètre Verbose, vous obtiendrez une sortie semblable à ce qui suit :

DÉTAILLÉ : activité de’Register’démarrée.

Envoi de la demande d’inscription :

Nom de domaine complet cible = atl-cs-011.litwareinc.com

Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com

Port du Bureau d’enregistrement = 5062.

Le type d’authentification « IWA » est sélectionné.

Exception «le point de terminaison n’a pas pu s’inscrire. Voir le code d’après pour une raison spécifique. ' Il s’est produit lors de l’exécution du flux de travail Microsoft. RTC. SyntheticTransactions. flux de travail. STP2PAVWorkflow.

Même si vous examinez soigneusement la sortie, il est possible que vous voyiez un port de Registre incorrect (port 5062). À son tour, cela a entraîné l’échec du test.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsP2PAV peuvent échouer :

  - Vous avez spécifié un compte d’utilisateur qui n’est pas valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit :
    
    Get-CsUser "sip :kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à ce qui suit :
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

