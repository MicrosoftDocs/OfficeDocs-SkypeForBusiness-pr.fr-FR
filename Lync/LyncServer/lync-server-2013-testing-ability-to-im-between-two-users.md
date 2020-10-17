---
title: 'Lync Server 2013 : test de la fonctionnalité de messagerie instantanée entre deux utilisateurs'
description: 'Lync Server 2013 : test de la fonctionnalité de messagerie instantanée entre deux utilisateurs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1409cfb58ed435a66dcf61db56660ca760e16422
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560800"
---
# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a>Test de la fonctionnalité de messagerie instantanée entre deux utilisateurs dans Lync Server 2013

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
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsIM. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de commande Test-CsIM vérifie qu’une paire d’utilisateurs de test peut échanger des messages instantanés. Lorsqu’elle est appelée, la cmdlet Test-CsIM démarre en tentant d’ouvrir une session sur une paire d’utilisateurs test vers Lync Server. En supposant que les deux ouvertures de sessions réussissent, l’applet de commande démarre une session de messagerie instantanée entre les deux utilisateurs de test. (L’utilisateur 1 invite l’utilisateur 2 à une session de messagerie instantanée et l’utilisateur 2 accepte l’invitation.) Après avoir vérifié que les messages peuvent être échangés entre les deux utilisateurs, Test-CsIM termine la session de messagerie instantanée et enregistre les deux utilisateurs dans le système.

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-CsIM peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration des comptes de test pour l’exécution des tests Lync Server) ou des comptes de deux utilisateurs activés pour Lync Server. Pour exécuter cette vérification à l’aide de comptes de test, il vous suffit de spécifier le nom de domaine complet du pool Lync Server testé. Par exemple :

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

Pour exécuter cette vérification à l’aide de comptes d’utilisateur réels, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte. Vous devez ensuite inclure ces objets Credentials et les adresses SIP des deux comptes lorsque vous appelez test-CsIM :

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Si les deux utilisateurs peuvent effectuer une session de messagerie instantanée, vous recevrez une sortie semblable à celle-ci, avec la propriété Result marquée with **Success :**

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : opération réussie

Latence : 00:00:06.6630911

«

Diagnostique

Si les utilisateurs de test ne peuvent pas terminer la session, le résultat est affiché en panne et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Erreur : 504, délai d’attente du serveur

Diagnostic : ErrorCode = 2, source = ATL-CS-001. litwareinc. com, Reason = Voir

Code de réponse et expression de motif.

Microsoft. RTC. signalisation. DiagnosticHeader

Par exemple, la sortie précédente indique que le test a échoué, car l’utilisateur spécifié est introuvable. Vous pouvez déterminer si une adresse SIP est valide (et si l’utilisateur auquel cette adresse SIP a été attribuée a été activé pour Lync Server) en exécutant la commande suivante :

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

Si Test-CsIM échoue, vous pouvez réexécuter le test, en incluant cette fois le paramètre Verbose :

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, Test-CsIM renvoie un compte pas à pas de chaque action effectuée lors de la vérification de la capacité des deux utilisateurs de test à prendre part à une session de messagerie instantanée. Par exemple, voici un exemple de sortie qui se produit lorsqu’un jeu incorrect d’informations d’identification de l’utilisateur (dans ce cas, un mot de passe incorrect) est fourni à test-CsIM :

Envoi d’une demande d’inscription :

Nom de domaine complet cible = atl-cs-011.litwareinc.com

Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com

Port de serveur d’inscriptions = 5061

Le type d’authentification « IWA » est sélectionné.

Accès à l’inscription sur SIP/ATL-CS-001. litwareinc. com

Activité « Register » terminée dans le « 0,0601795 » secondes.

Une exception’l’ouverture de session a été refusée. Vérifiez que les informations d’identification correctes sont utilisées et que le compte est actif. ' s’est produite pendant le flux de travail.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques raisons courantes pour lesquelles Test-CsIM peut échouer :

  - Vous avez spécifié un compte d’utilisateur qui n’est pas valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à celle-ci :
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est actuellement pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à la suivante :
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
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

