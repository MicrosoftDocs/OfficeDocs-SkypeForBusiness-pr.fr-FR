---
title: Configuration des utilisateurs et des paramètres de configuration du nœud observateur
description: Configuration des utilisateurs test de nœud observateur et des paramètres de configuration.
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
ms.openlocfilehash: e39a35d3db6ed80c715c706f4b5766e4b684e39e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542180"
---
# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>Configuration des utilisateurs test de nœud observateur et des paramètres de configuration dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-29_

Après avoir configuré l’ordinateur qui jouera le rôle de nœud observateur, vous devez :

1.  créer les comptes tests devant être utilisés par ces nœuds observateurs. SI vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser l’applet de commande [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) pour activer ces comptes pour une utilisation sur le nœud observateur ;

2.  mettre à jour les paramètres de configuration du nœud observateur.

Cette section traite des sujets suivants :

  - Configuration de comptes d’utilisateurs tests

  - Configuration d’un nœud observateur de base avec les transactions synthétiques par défaut

  - Configuration de tests étendus

  - Ajout et suppression de transactions synthétiques

  - Affichage et test de la configuration du nœud observateur

<div>

## <a name="configuring-test-user-accounts"></a>Configuration de comptes d’utilisateurs tests

Les utilisateurs test n’ont pas besoin de représenter des personnes réelles, mais ils doivent être des comptes de services de domaine Active Directory valides ; en outre, ces comptes doivent être activés pour Lync Server 2013, ils doivent avoir des adresses SIP valides, et ils doivent être activés pour voix entreprise (pour utiliser la transaction synthétique Test-CsPstnPeerToPeerCall). Si vous utilisez la méthode d’authentification TrustedServer, il vous suffit de vous assurer que ces comptes existent et ont été configurés comme indiqué dans cet article. Vous devez assigner au moins trois utilisateurs tests pour chaque pool que vous souhaitez tester.

Si vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser la cmdlet **Set-applet cstestusercredential** et Lync Server Management Shell pour permettre à ces comptes de test de fonctionner avec les transactions synthétiques. Pour ce faire, vous pouvez exécuter une commande semblable à la suivante. (Ces commandes partent du principe que les trois comptes d’utilisateur Active Directory ont déjà été créés et que ces comptes ont été activés pour Lync Server 2013.) :

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

Notez que vous devez inclure non seulement l’adresse SIP, mais également le nom d’utilisateur et le mot de passe. Si vous omettez le mot de passe, Set-CsTestUserCredential vous invitera à entrer ces informations. Le nom d’utilisateur peut être spécifié à l’aide du format nom d’utilisateur du nom de domaine \\ indiqué ci-dessus, ou en utilisant le format nom d’utilisateur Name@domain, par exemple :

    -UserName "watcher3@litwareinc.com"

Pour vérifier que les informations d’identification de l’utilisateur de test ont été créées, exécutez les commandes suivantes à partir de Lync Server Management Shell :

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

Des informations semblables aux suivantes doivent être renvoyées pour chaque utilisateur :

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configuration d’un nœud observateur de base avec les transactions synthétiques par défaut

Une fois les utilisateurs tests créés, vous pouvez créer un nœud observateur en exécutant une commande semblable à la suivante :

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

Cette commande crée un nœud observateur qui utilise les paramètres par défaut et exécute le jeu de transactions synthétiques par défaut. Le nouveau nœud observateur utilise également les utilisateurs tests watcher1@litwareinc.com, watcher2@litwareinc.com et watcher3@litwareinc.com. Si le nœud observateur utilise l’authentification TrustedServer, les trois comptes de test peuvent être des comptes d’utilisateurs valides activés pour Active Directory et Lync Server. Si le nœud observateur utilise la méthode d’authentification Negotiate, vous devez également activer ces comptes d’utilisateurs pour le nœud observateur à l’aide de l’applet de commande **Set-CsTestUserCredential**.

</div>

<div>

## <a name="configuring-extended-tests"></a>Configuration de tests étendus

Si vous souhaitez activer le test PSTN (Public Switched Telephone Network), qui vérifie la connectivité avec le réseau téléphonique commuté, vous devez effectuer certaines tâches de configuration supplémentaires lors de la configuration du nœud observateur. Tout d’abord, vous devez associer vos utilisateurs tests au type de test PSTN. Pour ce faire, exécutez une commande semblable à celle-ci à partir de Lync Server Management Shell :

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

Notez que les résultats de cette commande doivent être stockés dans une variable. Dans cet exemple, il s’agit de la variable nommée $pstnTest.

À ce stade, vous pouvez utiliser la cmdlet **New-applet cswatchernodeconfiguration** pour associer le type de test (stocké dans la variable $pstnTest) à un pool Lync Server 2013. Par exemple, la commande suivante crée une configuration de nœud observateur pour le pool atl-cs-001.litwareinc.com, ajoute les trois utilisateurs tests créés précédemment et ajoute également le type de test PSTN :

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Notez que la commande précédente échoue si vous n’avez pas installé les fichiers Core de Lync Server et la base de données RTCLocal sur l’ordinateur du nœud observateur.

Pour tester plusieurs stratégies de voix, vous devez créer un test étendu pour chaque stratégie à l’aide de l’applet de commande **New-CsExtendedTest**. Les utilisateurs assignés à ce test doivent être configurés avec les stratégies de voix souhaitées. Les tests étendus sont ensuite passés à l’applet de commande **New-CsWatcherNodeConfiguration** à l’aide d’une commande semblable à la suivante :

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

Si New-CsWatcherNodeConfiguration est appelée sans utiliser le paramètre Tests, cela signifie que seules les transactions synthétiques par défaut (et la transaction synthétique étendue spécifiée) seront activées pour le nouveau nœud observateur. Dans ce cas, le nœud observateur testera les composants suivants :

  - Registration

  - IM (Messagerie instantanée)

  - GroupIM

  - P2PAV (sessions audio/vidéo d’égal à égal)

  - AvConference (audioconférence)

  - Présence

  - ABS (Service de carnet d’adresses)

  - ABWQ (Service web de carnet d’adresses)

  - PSTN (appels de passerelle PSTN, spécifiés comme test étendu. Par défaut, le test PSTN est désactivé. Il est activé dans ce cas uniquement car la commande a activé PSTN à l’aide du paramètre ExtendedTests.)

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

Après avoir configuré un nœud observateur, vous pouvez utiliser l’applet de commande **Set-CsWatcherNodeConfiguration** pour ajouter ou supprimer des transactions synthétiques du nœud. Par exemple, pour ajouter le test PersistentChatMessage au nœud observateur, utilisez la méthode Add et une commande semblable à la suivante :

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

Plusieurs tests peuvent être ajoutés en séparant leur nom par des virgules. Par exemple :

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

Notez qu’une erreur se produit si un ou plusieurs de ces tests (par exemple DataConference) a déjà été activé sur le nœud observateur. Dans ce cas, vous recevez un message d’erreur semblable au suivant :

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

Lorsque cette erreur se produit, aucune modification n’est appliquée. La commande doit être réexécutée en supprimant le test dupliqué.

Pour supprimer une transaction synthétique d’un nœud observateur, utilisez la méthode Remove plutôt que la méthode Add. Par exemple, la commande suivante supprime le test ABWQ d’un nœud observateur :

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

Vous pouvez aussi utiliser la méthode Replace pour remplacer tous les tests activés actuellement par un ou plusieurs nouveaux tests. Par exemple, si vous souhaitez que le nœud observateur exécute seulement le test de messagerie instantanée, vous pouvez exécuter la commande suivante :

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

Lorsque vous exécutez cette commande, toutes les transactions synthétiques sur le nœud observateur spécifié sont désactivées, à l’exception de la messagerie instantanée.

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>Affichage et test de la configuration du nœud observateur

Si vous souhaitez afficher les tests qui ont été assignés à un nœud observateur, exécutez une commande semblable à la suivante :

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

Cette commande renvoie des informations semblables aux suivantes, en fonction des transactions synthétiques qui ont été assignées au nœud :

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
> Pour afficher les transactions synthétiques par ordre alphabétique, exécutez plutôt la commande suivante :<BR>Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object



</div>

Pour vérifier qu’un nœud observateur a été créé, tapez la commande suivante à partir de Lync Server Management Shell :

    Get-CsWatcherNodeConfiguration

Des informations analogues aux suivantes seront retournées :

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

Pour vérifier que le nœud observateur a été correctement configuré, tapez la commande suivante à partir de Lync Server Management Shell :

    Test-CsWatcherNodeConfiguration

Cette commande teste chaque nœud observateur de votre déploiement et indique notamment :

  - si le rôle de serveur d’inscriptions requis a été installé ;

  - si la clé de Registre nécessaire a été créée pour vous lors de l’exécution de Set-CsWatcherNodeConfiguration ;

  - Vos serveurs exécutent la version correcte de Lync Server.

  - si vos ports ont été configurés correctement ;

  - si vos utilisateurs de test assignés disposent des informations d’identification requises.

</div>

</div>

<span> </span>

</div>

</div>

</div>

