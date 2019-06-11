---
title: 'Lync Server 2013: test du service de réplicas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b1a9dca37c30231a2f0f297e94321dfc12405d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a>Test du service de réplication dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-11-03_


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
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande <strong>test-CsReplica</strong> . Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de **contrôle test-CsReplica** vérifie que le service de réplica Lync Server 2013 est en cours d’exécution sur l’ordinateur local. L’applet de **contrôle test-CsReplica** effectue les tâches suivantes:

  - vérification de l’état des services de l’agent de réplicateur et de l’agent d’enregistrement centralisé

  - vérification de l’ouverture des ports requis dans le pare-feu Windows

  - Il existe des groupes de sécurité de l’ordinateur local et actif nécessaires.

Notez que cette applet de cmdlet doit être exécutée localement. C’est-à-dire qu’il doit être exécuté sur le même ordinateur que le service de réplication exécuté. Il n’existe aucune option pour exécuter l’applet de commande **test-CsReplica** sur un serveur distant.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La commande décrite dans l’exemple 1 teste le service de réplica de Lync Server 2013 sur l’ordinateur local. Dans cet exemple, le paramètre Verbose est utilisé pour garantir que les informations relatives au test, y compris l’échec éventuel ou le succès du test, ainsi que l’emplacement du rapport généré par le test, s’affichent à l’écran.

    Test-CsReplica -Verbose

L’exemple 2 est une variante de la commande décrite dans l’exemple 1. Dans ce cas, le paramètre de rapport est inclus pour spécifier un chemin d’accès et un nom de dossier pour le rapport généré par le test. Si vous ne spécifiez pas de chemin d’accès au rapport, un nom généré automatiquement semblable à ce qui suit s’affiche:

C:\\utilisateurs\\administrateur. litwareinc\\AppData\\local\\Temp\\1\\test-CS-réplique-3db40ee0-4b5d-4f58-8d3d-b1e61253129e. html

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Insérez le corps de la section ici.

DÉTAILLÉ: création d’un nouveau fichier journal "C\\:\\les\\utilisateurs\\testent AppData Local\\Temp\\test-CsReplica-3cb066b3-DD23-411a-8932-99f01c0f940c. xml".

DÉTAILLÉ: création d’un nouveau fichier journal "C\\:\\les\\utilisateurs\\testent AppData Local\\Temp\\test-CsReplica-3cb066b3-DD23-411a-8932-99f01c0f940c. xml".

DÉTAILLÉ: le traitement de «test-CsReplica» s’est terminé correctement.

DÉTAILLÉ: des résultats détaillés sont disponibles à l’adresse «\\C\\:\\utilisateurs\\test\\de\\AppData Local Temp test-CsReplica-3cb066b3-DD23-411a-8932-99f01c0f940c. Xml».

DÉTAILLÉ: création d’un fichier journal

"C:\\les\\utilisateurs\\testent\\AppData\\\\local\\Temp 2 test-CsReplica-29fddb35-f56e-4e3c-8F4C-e

d3bd0e4a083. Xml».

DÉTAILLÉ: création d’un fichier journal

"C:\\les\\utilisateurs\\testent\\AppData\\\\local\\Temp 2 test-CsReplica-29fddb35-f56e-4e3c-8F4C-e

d3bd0e4a083. html».

AVERTISSEMENT: test-CsReplica a échoué.

AVERTISSEMENT: des résultats détaillés sont disponibles à l’adresse suivante:

"C:\\les\\utilisateurs\\testent\\AppData\\\\local\\Temp 2 test-CsReplica-29fddb35-f56e-4e3c-8F4C-e

d3bd0e4a083. html».

Test-CsReplica: échec de l’exécution de la commande: l’accès au Registre demandé n’est pas

acceptés.

À la ligne: 1 car: 1

\+Test-CsReplica-verbose

\+ ~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: InvalidOperation: (:) \[Test-CsReplica\], sécurité

Sauf

\+FullyQualifiedErrorId: ProcessingFailed, Microsoft. RTC. Management. deploy

Management. TestReplicaCmdlet

PS C:\\tests\\des utilisateurs\>

PS C:\\\> test\\des utilisateurs-CsUcwaConference-TargetFqdn "LyncTest. selfHost. Corp. M

icrosoft.com "

AVERTISSEMENT: impossible de lire le numéro de port du Bureau d’enregistrement pour le nom complet fourni

nom de domaine (FQDN). Utilisation du numéro de port de bureau par défaut. Sauf

System. InvalidOperationException: aucun cluster correspondant détecté dans la topologie.

dès

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Test-CsUcwaConference: il n’y a aucun utilisateur de test affecté à

\[LyncTest.SelfHost.Corp.Microsoft.com\]. Vérifiez la configuration de l’utilisateur test.

À la ligne: 1 car: 1

\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: ResourceUnavailable: (:) \[Test-CsUcwaConference\]

, InvalidOperationException

\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. RTC. Management. synthé

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles **les tests-CsReplica** peuvent échouer:

  - Il est possible qu’il y ait un problème plus important avec l’agent réplicateur et les services d’agent de connexion centralisés

  - Il est possible que les ports requis ne soient pas ouverts dans le pare-feu Windows

  - Le groupe de sécurité des ordinateurs Active Directory et local requis n’existe pas

</div>

</div>

<span> </span>

</div>

</div>

</div>

