---
title: 'Lync Server 2013 : validation de conférences audio/vidéo'
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
ms.openlocfilehash: 89bb8f38ea650bf64179b917b227d7ccaaf10791
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a>Validation de conférences audio/vidéo dans Lync Server 2013

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
<td><p>Échéancier de vérification</p></td>
<td><p>Jour</p></td>
</tr>
<tr class="odd">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="even">
<td><p>Autorisations requises</p></td>
<td><p>Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsAVConference. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsAVConference vérifie si deux utilisateurs de test peuvent participer à une téléconférence audio/vidéo (A/V). Lorsque la cmdlet s’exécute, les deux utilisateurs sont connectés au système. Après une connexion réussie, le premier utilisateur crée une conférence A/V, puis attend le second utilisateur pour rejoindre cette conférence. Après un court échange de données, la Conférence est supprimée et les deux tests déconnectés.

Notez que test-CsAVConference n’effectue pas de conférence A/V réelle entre les deux utilisateurs test. Au lieu de cela, l’applet de connexion vérifie que les deux utilisateurs peuvent effectuer toutes les connexions nécessaires à la réalisation d’une telle conférence.

Vous trouverez d’autres exemples pour cette commande à l’adresse [test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’applet de contrôle test-CsAVConference peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou les comptes de tous les utilisateurs qui sont activés pour Lync Server. Pour exécuter cette vérification à l’aide de comptes de test, vous devez simplement spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé. Par exemple :

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

Pour exécuter ce contrôle à l’aide de comptes d’utilisateurs réels, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte. Vous devez alors inclure ces objets d’informations d’identification et les adresses SIP des deux comptes lors de l’appel de test-CsAVConference :

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si les utilisateurs spécifiés peuvent réussir une conférence A/V, vous recevrez une sortie similaire à celle-ci, avec la propriété Result marquée comme **réussie :**

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : réussite

Latence : 00:00:02.6841765

Error

Diagnostic

Si les utilisateurs ne peuvent pas effectuer la Conférence, le résultat est affiché en tant qu’échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Erreur : 404, introuvable

Diagnostic : codeerreur = 4005, source = ATL-CS-001.litwareinc.com,

Raison = URI de destination non activé pour le SIP ou non

Il.

Microsoft. RTC. signalisation. DiagnosticHeader

Par exemple, la sortie précédente indique que le test a échoué car au moins un des deux comptes utilisateur n’était pas valide, car le compte n’existe pas ou parce que le compte n’a pas été activé pour Lync Server. Vous pouvez vérifier l’existence des deux comptes de test et déterminer s’il a été activé pour Lync Server en exécutant une commande similaire à ce qui suit :

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

Si test-CsAVConference échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose :

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, test-CsAVConference renvoie un compte étape par étape de chaque action qu’il a effectuée lors de la vérification de la capacité des utilisateurs spécifiés à participer à une conférence AV. Par exemple, supposons que votre test échoue et que vous recevez le code de diagnostic suivant :

Codeerreur = 1008, source = accessproxy. litwareinc. com, raison = impossible de résoudre l’enregistrement SRV DNS

Si vous réexécutez le test en utilisant le paramètre Verbose, les informations détaillées renvoyées comportent une sortie semblable à ce qui suit :

DÉTAILLÉ : activité de’Register’démarrée.

Envoi de la demande d’inscription :

Nom de domaine complet cible = atl-cs-001.litwareinc.com

Adresse SIP de l’utilisateur = sip :davidlongmire@litwareinc.com

Port du Bureau d’enregistrement = 5061.

Le type d’authentification « approuvé » est sélectionné.

Activité’Register’démarrée.

Envoi de la demande d’inscription :

Nom de domaine complet cible = atl-cs-001.litwareinc.com

Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com

Port du Bureau d’enregistrement = 5061.

Le type d’authentification « approuvé » est sélectionné.

Exception «le point de terminaison n’a pas pu s’inscrire. Voir le code d’après pour une raison spécifique. ' s’est produite lors du flux de travail

La dernière ligne de cette sortie indique que l’utilisateur sip :kenmyer@litwareinc.com n’a pas pu s’inscrire sur Lync Server. Cela signifie que vous devez vérifier que l’adresse SIP sip :kenmyer@litwareinc.com est valide et que l’utilisateur associé est activé pour Lync Server.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsAVConference peuvent échouer :

  - Vous avez spécifié un compte d’utilisateur qui n’est pas valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit :
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à ce qui suit :
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

