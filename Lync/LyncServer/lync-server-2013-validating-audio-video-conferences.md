---
title: 'Lync Server 2013 : validation des conférences audio/vidéo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb206930dae08d0c2fcf5fa6a26b427b28c03e1b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a>Validation des conférences audio/vidéo dans Lync Server 2013

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
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Planification de la vérification</p></td>
<td><p>Tous les jours</p></td>
</tr>
<tr class="odd">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="even">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsAVConference. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande test-CsAVConference vérifie si deux utilisateurs de test peuvent participer à une conférence audio/vidéo (A/V). Quand l’applet de commande est exécutée, les deux utilisateurs sont connectés au système. Une fois qu’ils ont été correctement connectés, le premier utilisateur crée une conférence A/V, puis attend que le deuxième utilisateur rejoigne la Conférence. Après un bref échange de données, la conférence est supprimée et les deux utilisateurs de test sont déconnectés.

Notez que test-CsAVConference n’effectue pas de conférence A/V réelle entre les deux utilisateurs test. Au lieu de cela, l’applet de commande vérifie que les deux utilisateurs peuvent effectuer toutes les connexions nécessaires pour mener une telle conférence.

Vous trouverez d’autres exemples pour cette commande à la rubrique [test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-CsAVConference peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou des comptes de deux utilisateurs activés pour Lync Server. Pour exécuter cette vérification à l’aide de comptes de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé. Par exemple :

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

Pour exécuter cette vérification à l’aide de comptes d’utilisateur réels, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte. Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsqu’ils appellent test-CsAVConference :

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si les utilisateurs spécifiés peuvent réussir une conférence A/V, vous recevrez une sortie semblable à celle-ci, avec la propriété Result marquée comme **Success :**

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:02.6841765

«

Diagnostique

Si les utilisateurs ne peuvent pas terminer la Conférence, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés Error et diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Erreur : 404, introuvable

Diagnostic : ErrorCode = 4005, source = ATL-CS-001.litwareinc.com,

Raison = l’URI de destination n’est pas activé pour SIP ou ne prend pas

présent.

Microsoft. RTC. signalisation. DiagnosticHeader

Par exemple, la sortie précédente indique que le test a échoué car au moins l’un des deux comptes d’utilisateur n’était pas valide, car le compte n’existe pas ou parce que le compte n’a pas été activé pour Lync Server. Vous pouvez vérifier l’existence des deux comptes de test et savoir s’ils ont été activés pour Lync Server, en exécutant une commande semblable à la suivante :

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

Si test-CsAVConference échoue, vous pouvez réexécuter le test, ce qui inclut le paramètre Verbose :

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, test-CsAVConference renvoie un compte pas à pas de chaque action effectuée lorsqu’il a vérifié que les utilisateurs spécifiés peuvent participer à une conférence AV. Par exemple, supposons que votre test échoue et que vous recevez le diagnostic suivant :

ErrorCode = 1008, source = accessproxy. litwareinc. com, Reason = impossible de résoudre l’enregistrement DNS SRV

Si vous réexécutez le test à l’aide du paramètre Verbose, les informations pas à pas renvoyées incluent une sortie semblable à celle-ci :

VERBOSe : activité « enregistrer » démarrée.

Envoi d’une demande d’inscription :

Nom de domaine complet cible = atl-cs-001.litwareinc.com

Adresse SIP de l’utilisateur = sip :davidlongmire@litwareinc.com

Port de serveur d’inscriptions = 5061.

Le type d’authentification « approuvé » est sélectionné.

Activité « Register » démarrée.

Envoi d’une demande d’inscription :

Nom de domaine complet cible = atl-cs-001.litwareinc.com

Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com

Port de serveur d’inscriptions = 5061.

Le type d’authentification « approuvé » est sélectionné.

Une exception’le point de terminaison n’a pas pu s’inscrire. Voir le code d’ErrorCode pour des raisons spécifiques. s’est produite pendant le flux de travail

La dernière ligne de cette sortie indique que l’utilisateur sip :kenmyer@litwareinc.com n’a pas pu s’inscrire auprès de Lync Server. Cela signifie que vous devez vérifier que l’adresse SIP sip :kenmyer@litwareinc.com est valide et que l’utilisateur associé est activé pour Lync Server.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec de test-CsAVConference :

  - Vous avez spécifié un compte d’utilisateur qui n’est pas valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

