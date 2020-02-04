---
title: Configuration des utilisateurs et des paramètres de configuration du nœud FileSystemWatcher
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3713844d5d2364459a28c5919bb1d32d421d706
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>Configuration des utilisateurs et des paramètres de configuration du nœud FileSystemWatcher dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-29_

Après avoir configuré l’ordinateur qui jouera le rôle de nœud observateur, vous devez :

1.  Créez les comptes de test à utiliser par ces nœuds d’observation. Si vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser l’applet de commande [Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) pour activer ces comptes pour une utilisation sur le nœud observateur.

2.  Mettre à jour les paramètres de configuration du nœud observateur.

Cette section comprend les éléments suivants :

  - Configuration des comptes d’utilisateurs test

  - Configuration d’un nœud d’observateur de base avec les transactions synthétiques par défaut

  - Configuration de tests étendus

  - Ajout et suppression de transactions synthétiques

  - Affichage et test de la configuration du nœud observateur

<div>

## <a name="configuring-test-user-accounts"></a>Configuration des comptes d’utilisateurs test

Les utilisateurs test n’ont pas besoin de représenter des personnes réelles, mais ils doivent être des comptes de services de domaine Active Directory valides. de plus, ces comptes doivent être activés pour Lync Server 2013, ils doivent disposer d’adresses SIP valides, et ils doivent être activés pour Enterprise Voice (pour utiliser la transaction synthétique test-CsPstnPeerToPeerCall). Si vous utilisez la méthode d’authentification TrustedServer, il vous suffit de vérifier qu’il existe des comptes et qu’ils ont été configurés comme indiqué ici. Vous devez assigner au moins trois utilisateurs tests pour chaque pool que vous souhaitez tester.

Si vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser l’applet de contrôle **Set-CsTestUserCredential** et Lync Server Management Shell pour permettre à ces comptes de test d’utiliser les transactions synthétiques. Pour cela, vous pouvez exécuter une commande semblable à la suivante. (Ces commandes présupposent que les trois comptes d’utilisateurs Active Directory ont déjà été créés et que ces comptes ont été activés pour Lync Server 2013) :

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

Notez que vous devez inclure la seule adresse SIP mais également le nom d’utilisateur et le mot de passe. Si vous n’incluez pas le mot de passe jeu-CsTestUserCredential vous invite à entrer ces informations. Le nom d’utilisateur peut être spécifié en utilisant le\\format de nom d’utilisateur de nom de domaine présenté ci-dessus, ou à l’aide du nom name@domain l’utilisateur. par exemple :

    -UserName "watcher3@litwareinc.com"

Pour vérifier que les informations d’identification de l’utilisateur ont été créées, exécutez les commandes suivantes dans Lync Server Management Shell, procédez comme suit :

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

Des informations similaires doivent être renvoyées pour chaque utilisateur :

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configuration d’un nœud d’observateur de base avec les transactions synthétiques par défaut

Après la création des utilisateurs de test, vous pouvez créer un nœud FileSystemWatcher à l’aide d’une commande similaire à celle-ci :

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

Cette commande crée un nœud observateur qui utilise les paramètres par défaut et exécute le jeu de transactions synthétiques par défaut. Le nouveau nœud observateur utilise également les utilisateurs tests watcher1@litwareinc.com, watcher2@litwareinc.com et watcher3@litwareinc.com. Si le nœud de l’observateur d’observation utilise l’authentification TrustedServer, les trois comptes de test peuvent être tout compte d’utilisateur valide activé pour Active Directory et Lync Server. Si le nœud d’observation utilise la méthode d’authentification Negotiate, vous devez également activer ces comptes d’utilisateurs pour le nœud de l’observateur à l’aide de l’applet de passe **Set-CsTestUserCredential** .

</div>

<div>

## <a name="configuring-extended-tests"></a>Configuration de tests étendus

Si vous voulez activer le réseau téléphonique commuté (RTC) qui vérifie la connectivité avec le réseau téléphonique public commuté, vous devez effectuer une configuration supplémentaire lors de la configuration du nœud d’observation. Tout d’abord, vous devez associer vos utilisateurs de test au type de test PSTN. Pour cela, exécutez une commande similaire à celle-ci à partir de Lync Server Management Shell :

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

Notez que les résultats de cette commande doivent être stockés dans une variable. Dans cet exemple, il s’agit d’une variable nommée $pstnTest.

À ce stade, vous pouvez utiliser l’applet de contrôle **New-CsWatcherNodeConfiguration** pour associer le type de test (stocké dans le $pstnTest variable) à un pool Lync Server 2013. Par exemple, la commande suivante crée une nouvelle configuration de nœud d’observation pour le pool atl-cs-001.litwareinc.com, en ajoutant les trois utilisateurs de test précédemment créés et en ajoutant également le type de test PSTN :

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Notez que la commande précédente échoue si vous n’avez pas installé les fichiers principaux de Lync Server et la base de données RTCLocal sur l’ordinateur de nœud d’observation.

Pour tester plusieurs stratégies vocales, vous devez créer un test étendu pour chaque stratégie à l’aide de l’applet **de contrôle New-CsExtendedTest** . Les utilisateurs affectés à ce test doivent être configurés avec les politiques vocales désirées. Les tests étendus sont ensuite passés à l’applet **de commande New-CsWatcherNodeConfiguration** à l’aide d’une commande similaire à ce qui suit :

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

Si New-CsWatcherNodeConfiguration est appelé sans utiliser le paramètre tests, cela signifie que seules les transactions synthétiques par défaut (et la transaction synthétique étendue spécifiée) seront activées pour le nouveau nœud d’observation. Cela signifie que le nœud Watcher testera les composants suivants :

  - Enregistrement

  - IM

  - GroupIM (messagerie instantanée de groupe)

  - P2PAV (sessions audio/vidéo d’égal à égal)

  - AvConference (audioconférence)

  - Presence

  - ABS (Service de carnet d’adresses)

  - ABWQ (Service web de carnet d’adresses)

  - Appels RTC (RTC passerelle), spécifiés en tant que test étendu. Par défaut, le RTC est désactivé. Le test est activé uniquement dans ce cas, car la commande a activé PSTN à l’aide du paramètre ExtendedTests.)

Cela signifie également que les composants suivants ne seront pas testés par défaut :

  - AVEdgeConnectivity

  - MCXP2PIM (messagerie instantanée d’appareils mobiles)

  - ExumConnectivity (Messagerie unifiée Exchange)

  - JoinLauncher

  - PersistentChatMessage

  - DataConference

  - XmppIM

  - UnifiedContactStore

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a>Ajout et suppression de transactions synthétiques

Après avoir configuré un nœud FileSystemWatcher, vous pouvez utiliser l’applet de cmdlet **Set-CsWatcherNodeConfiguration** pour ajouter ou supprimer des transactions synthétiques du nœud. Par exemple, pour ajouter le test PersistentChatMessage au nœud observateur, utilisez la méthode Add et une commande semblable à la suivante :

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

Plusieurs tests peuvent être ajoutés en séparant leur nom par des virgules. Par exemple :

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

Notez qu’une erreur se produit lorsqu’un ou plusieurs de ces tests (par exemple, DataConference) ont déjà été activés sur le nœud d’observateur. Dans ce cas, vous recevez un message d’erreur semblable au suivant :

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

Lorsque cette erreur se produit, aucune modification n’est appliquée. La commande doit être réexécutée avec le test dupliqué supprimé.

Pour supprimer une transaction synthétique d’un nœud d’observation, utilisez la méthode Remove à la place de la méthode Add. Par exemple, la commande suivante supprime le test ABWQ d’un nœud observateur :

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

Vous pouvez également utiliser la méthode Replace pour remplacer tous les tests actuellement activés par un ou plusieurs nouveaux tests. Par exemple, si vous souhaitez qu’un nœud d’observation ne exécute que le test de messagerie instantanée, vous pouvez le configurer en utilisant la commande suivante :

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

Lors de l’exécution de la commande ci-dessus, toutes les transactions synthétiques sur le nœud d’observateur spécifié seront désactivées sauf pour les messages instantanés.

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>Affichage et test de la configuration du nœud observateur

Si vous souhaitez afficher les tests qui ont été assignés à un nœud observateur, exécutez une commande semblable à la suivante :

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

La commande précédente renverra des informations similaires à ce qui suit, en fonction des transactions de synthèse affectées au nœud :

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference

<div>


> [!TIP]
> Pour afficher les transactions synthétiques par ordre alphabétique, exécutez plutôt la commande suivante :<BR>Get-CsWatcherNodeConfiguration-Identity "atl-cs-001.litwareinc.com" | Select-Object-tests ExpandProperty | Objet de tri



</div>

Pour vérifier qu’un nœud d’observateur a été créé, tapez la commande suivante à partir de Lync Server Management Shell :

    Get-CsWatcherNodeConfiguration

Vous recevrez des informations similaires à ce qui suit :

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

Pour vérifier que le nœud d’observateur a été correctement configuré, tapez la commande suivante à partir de Lync Server Management Shell :

    Test-CsWatcherNodeConfiguration

La commande précédente testera chaque nœud d’observateur dans votre déploiement et vous fournira les informations suivantes :

  - Le rôle de bureau d’enregistrement requis a été installé.

  - La clé de registre requise a été créée pour vous lorsque vous avez exécuté Set-CsWatcherNodeConfiguration.

  - Vos serveurs exécutent la version appropriée de Lync Server.

  - Vos ports sont correctement configurés.

  - Les informations d’identification requises pour vos utilisateurs de tests sont obligatoires.

</div>

</div>

<span> </span>

</div>

</div>

</div>

