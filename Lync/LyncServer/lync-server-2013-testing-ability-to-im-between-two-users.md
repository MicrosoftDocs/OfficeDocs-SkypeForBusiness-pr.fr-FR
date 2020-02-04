---
title: 'Lync Server 2013 : possibilité de test de la fonctionnalité de messagerie instantanée entre deux utilisateurs'
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
ms.openlocfilehash: 201aceceadeba3c6c97530925273097fe039bc08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a>Fonctionnalité de test de la fonctionnalité de messagerie instantanée entre deux utilisateurs dans Lync Server 2013

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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsIM. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsIM vérifie qu’un binôme d’utilisateurs de test peut échanger des messages instantanés. Lorsqu’il est appelé, l’applet de connexion test-CsIM démarre en essayant de se connecter à une paire d’utilisateurs de test sur Lync Server. En supposant que les deux ouvertures de session aboutissent, l’applet de connexion démarre une session de messagerie instantanée entre les deux utilisateurs test. (L’utilisateur 1 invite l’utilisateur 2 à une session de messagerie instantanée et l’utilisateur 2 accepte l’invitation.) Après avoir vérifié que les messages peuvent être échangés entre les deux utilisateurs, testez-CsIM, puis mettez fin à la session de messagerie instantanée et enregistre les deux utilisateurs en dehors du système.

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’applet de contrôle test-CsIM peut être exécutée à l’aide d’une paire de comptes de test préconfigurés (voir Configuration de comptes de test pour exécuter des tests Lync Server) ou les comptes de tous les utilisateurs qui sont activés pour Lync Server. Pour exécuter cette vérification à l’aide de comptes de test, vous devez simplement spécifier le nom de domaine complet (FQDN) du pool de serveurs Lync testé. Par exemple :

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

Pour exécuter ce contrôle à l’aide de comptes d’utilisateurs réels, vous devez créer deux objets d’informations d’identification Windows PowerShell (objets contenant le nom de compte et le mot de passe) pour chaque compte. Vous devez alors inclure ces objets d’informations d’identification et les adresses SIP des deux comptes lors de l’appel de test-CsIM :

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Si les deux utilisateurs peuvent terminer une session de messagerie instantanée, vous recevrez une sortie semblable à ce qui suit, avec la propriété Result marquée comme **réussie :**

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : réussite

Latence : 00:00:06.6630911

Error

Diagnostic

Si les utilisateurs de test ne peuvent pas effectuer la session, le résultat est affiché en tant qu’échec et des informations supplémentaires sont enregistrées dans les propriétés d’erreur et de diagnostic :

TargetFqdn : atl-cs-001.litwareinc.com

Résultat : échec

Latence : 00:00:00

Erreur : 504, délai du serveur

Diagnostic : codeerreur = 2, source = ATL-CS-001. litwareinc. com, Reason = Voir

Code de réponse et phrase de raison.

Microsoft. RTC. signalisation. DiagnosticHeader

Par exemple, l’état précédent de sortie a échoué en raison de l’échec de la recherche de l’utilisateur spécifié. Vous pouvez déterminer si une adresse SIP est valide (et si l’utilisateur affecté à cette adresse SIP a été activé pour Lync Server) en exécutant la commande suivante :

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

Si test-CsIM échoue, il est possible que vous souhaitiez réexécuter le test, cette fois-ci, y compris le paramètre Verbose :

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Lorsque le paramètre Verbose est inclus, test-CsIM renvoie un compte étape par étape de chaque action qu’il a effectuée lors de la vérification de la capacité des deux utilisateurs de test à participer à une session de messagerie instantanée. Par exemple, voici un exemple de sortie qui se produit lorsqu’un ensemble incorrect d’informations d’identification de l’utilisateur (dans ce cas, un mot de passe incorrect) est fourni à test-CsIM :

Envoi de la demande d’inscription :

Nom de domaine complet cible = atl-cs-011.litwareinc.com

Adresse SIP de l’utilisateur = sip :kenmyer@litwareinc.com

Port du Bureau d’enregistrement = 5061

Le type d’authentification « IWA » est sélectionné.

Accès à l’enregistrement par SIP/ATL-CS-001. litwareinc. com

Activité « Register » achevée en « 0,0601795 » secondes.

Une exception’la connexion a été refusée. Vérifiez que les informations d’identification correctes sont utilisées et que le compte est actif. ' s’est produite lors du flux de travail.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsIM peuvent échouer :

  - Vous avez spécifié un compte d’utilisateur qui n’est pas valide. Vous pouvez vérifier qu’un compte d’utilisateur existe en exécutant une commande semblable à ce qui suit :
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - Le compte d’utilisateur est valide, mais le compte n’est pas activé pour Lync Server. Pour vérifier qu’un compte d’utilisateur est activé pour Lync Server, exécutez une commande semblable à ce qui suit :
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
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

