---
title: 'Lync Server 2013 : test de la fonctionnalité de messagerie instantanée de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97562d82f751280ec4d1a8f154af2b85ed2be128
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a>Test de la fonctionnalité de groupe de messagerie instantanée dans Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsGroupIM. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande test-CsGroupIM vérifie que les utilisateurs de votre organisation peuvent effectuer des sessions de messagerie instantanée de groupe. Lorsque vous exécutez la cmdlet Test-CsGroupIM, l’applet de commande tente de se connecter à une paire d’utilisateurs test à Lync Server. Si l’opération réussit, Test-CsGroupIM crée une nouvelle conférence à l’aide du premier utilisateur test, puis invite le deuxième utilisateur à participer à la conférence. Après un échange de messages, les deux utilisateurs sont déconnectés du système. Notez que tout cela se produit sans aucune interaction de l’utilisateur et sans affecter les utilisateurs réels. Par exemple, supposons que le compte de test sip :kenmyer@litwareinc.com correspond à un utilisateur réel qui possède un compte de serveur Lync réel. Dans ce cas, le test sera effectué sans interrompre les activités de l’utilisateur réel Ken Myer. Par exemple, même si le compte de test Ken Myer se déconnecte du système Ken Myer, l’utilisateur restera connecté. De même, le véritable Ken Myer ne reçoit pas d’invitation à participer à la Conférence. Cette invitation sera envoyée au compte de test et acceptée par ce dernier.

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-CsGroupIM peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou des comptes de deux utilisateurs activés pour Lync Server. Pour exécuter cette vérification à l’aide de comptes de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé. Par exemple :

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

Pour exécuter cette vérification à l’aide de comptes d’utilisateur réels, vous devez créer deux objets d’informations d’identification Lync Server Management Shell (objets qui contiennent le nom de compte et le mot de passe) pour chaque compte. Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsque vous appelez test-CsGroupIM :

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si les deux utilisateurs peuvent effectuer une session de messagerie instantanée de groupe, vous recevrez une sortie semblable à celle-ci avec la propriété Result marquée with **Success :**

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:06.3812203

«

Diagnostique

Si les deux utilisateurs ne peuvent pas effectuer la session de messagerie instantanée, le résultat est indiqué comme étant un échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Erreur : 404, introuvable

Diagnostic : ErrorCode = 4005, source = ATL-CS-001.litwareinc.com,

Raison = l’URI de destination n’est pas activé pour SIP ou ne prend pas

présent.

Microsoft. RTC. signalisation. DiagnosticHeader

La sortie précédente indique que le test a échoué car au moins l’un des comptes de test n’était pas valide, car le compte n’existe pas ou parce que l’utilisateur n’a pas été activé pour Lync Server. Vous pouvez vérifier que le compte existe et que le compte a été activé pour nm-OCS-14-3e en exécutant une commande semblable à celle-ci :

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

Si test-CsGroupIM échoue, vous pouvez réexécuter le test, ce qui inclut le paramètre Verbose :

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, test-CsGroupIM renvoie un compte pas à pas de chaque action effectuée lors de la vérification de la capacité des utilisateurs spécifiés à participer à une session de messagerie instantanée de groupe. Par exemple, si votre test échoue et que vous êtes informé qu’un ou plusieurs comptes d’utilisateur ne sont pas valides, vous pouvez réexécuter le test à l’aide du paramètre Verbose et déterminer le compte d’utilisateur qui n’est pas valide :

Envoi d’une demande d’inscription :

 Nom de domaine complet cible = atl-cs-001.litwareinc.com

 Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com

 Port d’inscription = 5061

Le type d’authentification « IWA » est sélectionné.

Une exception’l’ouverture de session a été refusée. Vérifiez que les informations d’identification correctes sont utilisées et que le compte est actif.

Comme vous pouvez le voir, dans cet exemple, l’utilisateur disposant de l’adresse SIP sip :kenmyer@litwareinc.com n’a pas pu se connecter.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec de test-CsGroupIM :

  - Vous avez spécifié un compte d’utilisateur incorrect. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur a été activé pour Lync Server, exécutez une commande semblable à la suivante :
    
    Get-CsUser "sip :kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

  - Le service de messagerie instantanée n’est peut-être pas disponible. Avec Lync Server, vous pouvez configurer le système de sorte que la messagerie instantanée ne soit pas disponible si la base de données d’archivage est inaccessible. Vous pouvez vérifier qu’en exécutant une commande semblable à la suivante :
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    Si BlockOnArchiveFailure est défini sur true, vous devez déterminer si la base de données d’archivage est disponible ou non. Vous pouvez renvoyer les emplacements de vos bases de données d’archivage à l’aide de la commande suivante :
    
        Get-CsService -ArchivingDatabase

  - Le serveur d’archivage n’est peut-être pas disponible. Vous pouvez récupérer le nom de domaine complet de vos serveurs d’archivage à l’aide de la commande suivante :
    
        Get-CsService -ArchivingServer
    
    Vous pouvez ensuite exécuter la commande ping sur le serveur approprié pour vérifier qu’il est disponible. Par exemple :
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

