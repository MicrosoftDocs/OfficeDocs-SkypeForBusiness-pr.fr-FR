---
title: 'Lync Server 2013 : le test de la fonctionnalité de messagerie instantanée de groupe'
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
ms.openlocfilehash: 8552d5caadf26d70265f5538f10c6152eb67dcc8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a>Possibilité de test de faire des conversations de groupe dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsGroupIM. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsGroupIM vérifie que les utilisateurs de votre organisation peuvent organiser des sessions de messagerie instantanée de groupe. Lorsque vous exécutez test-CsGroupIM, l’applet de connexion tente de se connecter à un couple d’utilisateurs de test sur Lync Server. En cas de succès, test-CsGroupIM crée une nouvelle conférence à l’aide du premier utilisateur de test, puis invite le second utilisateur à rejoindre la Conférence. Après un échange de messages, les deux utilisateurs sont alors déconnectés du système. Notez que tout cela se produit sans aucune interaction utilisateur, sans affecter les utilisateurs réels. Par exemple, supposons que le compte de test sip :kenmyer@litwareinc.com correspond à un utilisateur réel possédant un compte de serveur Lync réel. Dans ce cas, le test sera mené sans interruption pour le véritable Ken Myer. Par exemple, même lorsque le compte de test Ken Myer se déconnecte du système, Ken Myer la personne reste connectée. De même, le véritable Ken Myer ne recevra pas d’invitation à rejoindre la Conférence. Cette invitation sera envoyée au compte de test et acceptée par celle-ci.

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’applet de contrôle test-CsGroupIM peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou les comptes de tous les utilisateurs qui sont activés pour Lync Server. Pour exécuter cette vérification à l’aide de comptes de test, vous devez simplement spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé. Par exemple :

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

Pour exécuter cette vérification à l’aide de comptes d’utilisateurs réels, vous devez créer deux objets d’informations d’identification Lync Server Management Shell (objets contenant le nom de compte et le mot de passe) pour chaque compte. Vous devez alors inclure ces objets d’informations d’identification et les adresses SIP des deux comptes lors de l’appel de test-CsGroupIM :

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si les deux utilisateurs peuvent terminer une session de messagerie instantanée de groupe, vous recevrez une sortie similaire à celle-ci avec la propriété Result marquée comme **réussie :**

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : réussite

Latence : 00:00:06.3812203

Error

Diagnostic

Si les deux utilisateurs ne peuvent pas mettre fin à la session de messagerie instantanée, le résultat s’affichera en panne et des informations supplémentaires seront enregistrées dans les propriétés d’erreur et de diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Erreur : 404, introuvable

Diagnostic : codeerreur = 4005, source = ATL-CS-001.litwareinc.com,

Raison = URI de destination non activé pour le SIP ou non

Il.

Microsoft. RTC. signalisation. DiagnosticHeader

La sortie précédente indique que le test a échoué car au moins un des comptes de test n’est pas valide, car le compte n’existe pas ou parce que l’utilisateur n’a pas été activé pour Lync Server. Vous pouvez vérifier que le compte existe et que le compte a été activé pour nm-OCS-14-3e en exécutant une commande similaire à ce qui suit :

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

Si test-CsGroupIM échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose :

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, test-CsGroupIM renvoie un compte étape par étape de chaque action qu’il a effectuée lors de la vérification de la capacité des utilisateurs spécifiés à participer à une session de messagerie instantanée de groupe. Par exemple, si vous constatez qu’un ou plusieurs comptes d’utilisateur ne sont pas valides, vous pouvez réexécuter le test en utilisant le paramètre Verbose et déterminer le compte d’utilisateur qui n’est pas valide :

Envoi de la demande d’inscription :

 Nom de domaine complet cible = atl-cs-001.litwareinc.com

 Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com

 Register port = 5061

Le type d’authentification « IWA » est sélectionné.

Une exception’la connexion a été refusée. Vérifiez que les informations d’identification correctes sont utilisées et que le compte est actif'

Comme vous pouvez le voir dans cet exemple, l’utilisateur qui dispose de l’adresse SIP sip :kenmyer@litwareinc.com n’a pas réussi à se connecter.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsGroupIM peuvent échouer :

  - Vous avez spécifié un compte d’utilisateur incorrect. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit :
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur a été activé pour Lync Server, exécutez une commande semblable à ce qui suit :
    
    Get-CsUser "sip :kenmyer@litwareinc.com" | Option Sélectionner un objet activée
    
    Si la propriété Enabled est définie sur false, cela signifie que l’utilisateur n’est actuellement pas activé pour Lync Server.

  - Le service de messagerie instantanée n’est peut-être pas disponible. Lync Server vous permet de configurer le système de sorte que la messagerie instantanée ne soit pas disponible si vous n’êtes pas en mesure d’accéder à la base de données d’archivage. Vous pouvez vérifier qu’en exécutant une commande semblable à ce qui suit :
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    Si BlockOnArchiveFailure est défini sur true, vous devez déterminer si la base de données d’archivage est disponible ou non. Vous pouvez renvoyer les emplacements de vos bases de données d’archivage à l’aide de la commande suivante :
    
        Get-CsService -ArchivingDatabase

  - Le serveur d’archivage n’est peut-être pas disponible. Vous pouvez récupérer le nom de domaine complet (FQDN) de vos serveurs d’archivage à l’aide de la commande suivante :
    
        Get-CsService -ArchivingServer
    
    Vous pouvez ensuite exécuter une commande ping sur le serveur approprié pour vérifier qu’il est disponible. Par exemple :
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

