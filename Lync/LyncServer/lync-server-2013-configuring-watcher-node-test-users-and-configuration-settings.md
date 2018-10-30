---
title: "Conf. des ut. de test d’un nœud observateur et paramètres de configuration"
TOCtitle: "Conf. des ut. de test d’un nœud observateur et paramètres de configuration"
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205152(v=OCS.15)
ms:contentKeyID: 49298484
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des utilisateurs de test d’un nœud observateur et paramètres de configuration

 

_**Dernière rubrique modifiée :** 2013-07-29_

Après avoir configuré l’ordinateur qui jouera le rôle de nœud observateur, vous devez :

1.  créer les comptes tests devant être utilisés par ces nœuds observateurs. SI vous utilisez la méthode d’authentification Negotiate, vous devez également utiliser l’applet de commande [Set-CsTestUserCredential](https://docs.microsoft.com/en-us/powershell/module/skype/) pour activer ces comptes pour une utilisation sur le nœud observateur ;

2.  mettre à jour les paramètres de configuration du nœud observateur.

Cette section traite des sujets suivants :

  - Configuration de comptes d’utilisateurs tests

  - Configuration d’un nœud observateur de base avec les transactions synthétiques par défaut

  - Configuration de tests étendus

  - Ajout et suppression de transactions synthétiques

  - Affichage et test de la configuration du nœud observateur

## Configuration de comptes d’utilisateurs tests

Il n’est pas nécessaire que les utilisateurs tests représentent des personnes réelles, mais il doit s’agir de comptes services de domaine Active Directory valides ; de plus, ces comptes doivent être activés pour Lync Server 2013, ils doivent avoir des adresses SIP valides et être activés pour Voix Entreprise (pour utiliser la transaction synthétique Test-CsPstnPeerToPeerCall). Si vous utilisez la méthode d’authentification TrustedServer, il vous suffit de vous assurer que ces comptes existent et ont été configurés comme indiqué dans cet article. Vous devez assigner au moins trois utilisateurs tests pour chaque pool que vous souhaitez tester.

Si vous utilisez la méthode d’authentification Negotiate, vous devez aussi utiliser l’applet de commande **Set-CsTestUserCredential** et Lync Server Management Shell pour activer ces comptes de sorte qu’ils fonctionnent avec les transactions synthétiques. Vous pouvez pour cela exécuter une commande semblable à la suivante. (Ces commandes supposent que les trois comptes d’utilisateurs Active Directory ont déjà été créés et activés pour Lync Server 2013.) :

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

Notez que vous devez inclure non seulement l’adresse SIP, mais également le nom d’utilisateur et le mot de passe. Si vous omettez le mot de passe, Set-CsTestUserCredential vous invitera à entrer ces informations. Le nom d’utilisateur peut être spécifié au format nom de domaine/nom d’utilisateur indiqué ci-dessus ou au format nom d’utilisateur@nom de domaine ; par exemple :

    -UserName "watcher3@litwareinc.com"

Pour vérifier que les informations d’identification de l’utilisateur test ont été créées, exécutez les commandes suivantes depuis Lync Server Management Shell :

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

Des informations semblables aux suivantes doivent être retournées pour chaque utilisateur :

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

## Configuration d’un nœud observateur de base avec les transactions synthétiques par défaut

Une fois les utilisateurs tests créés, vous pouvez créer un nœud observateur en exécutant une commande semblable à la suivante :

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

Cette commande crée un nœud observateur qui utilise les paramètres par défaut et exécute le jeu de transactions synthétiques par défaut. Le nouveau nœud observateur utilise également les utilisateurs tests watcher1@litwareinc.com, watcher2@litwareinc.com et watcher3@litwareinc.com. Si le nœud observateur utilise l’authentification TrustedServer, les trois comptes tests peuvent être n’importe quels comptes d’utilisateurs valides activés pour Active Directory et Lync Server. Si le nœud observateur utilise la méthode d’authentification Negotiate, vous devez également activer ces comptes d’utilisateurs pour le nœud observateur à l’aide de l’applet de commande **Set-CsTestUserCredential**.

## Configuration de tests étendus

Si vous souhaitez activer le test PSTN (Public Switched Telephone Network), qui vérifie la connectivité avec le réseau téléphonique commuté, vous devez effectuer certaines tâches de configuration supplémentaires lors de la configuration du nœud observateur. Tout d’abord, vous devez associer vos utilisateurs tests au type de test PSTN. Pour cela, exécutez une commande semblable à la suivante à partir de Lync Server Management Shell :

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

Notez que les résultats de cette commande doivent être stockés dans une variable. Dans cet exemple, il s’agit de la variable nommée $pstnTest.

À ce stade, vous pouvez utiliser l’applet de commande **New-CsWatcherNodeConfiguration** pour associer le type de test (stocké dans la variable $pstnTest) à un pool Lync Server 2013. Par exemple, la commande suivante crée une configuration de nœud observateur pour le pool atl-cs-001.litwareinc.com, ajoute les trois utilisateurs tests créés précédemment et ajoute également le type de test PSTN :

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Notez que la commande précédente échoue si vous n’avez pas installé les fichiers principaux Lync Server et la base de données RTCLocal sur l’ordinateur nœud observateur.

Pour tester plusieurs stratégies de voix, vous devez créer un test étendu pour chaque stratégie à l’aide de l’applet de commande **New-CsExtendedTest**. Les utilisateurs assignés à ce test doivent être configurés avec les stratégies de voix souhaitées. Les tests étendus sont ensuite passés à l’applet de commande **New-CsWatcherNodeConfiguration** à l’aide d’une commande semblable à la suivante :

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

Si New-CsWatcherNodeConfiguration est appelée sans utiliser le paramètre Tests, cela signifie que seules les transactions synthétiques par défaut (et la transaction synthétique étendue spécifiée) seront activées pour le nouveau nœud observateur. Dans ce cas, le nœud observateur testera les composants suivants :

  - Registration (Inscription)

  - IM (Messagerie instantanée)

  - GroupIM (messagerie instantanée de groupe)

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

## Ajout et suppression de transactions synthétiques

Après avoir configuré un nœud observateur, vous pouvez utiliser l’applet de commande **Set-CsWatcherNodeConfiguration** pour ajouter ou supprimer des transactions synthétiques du nœud. Par exemple, pour ajouter le test PersistentChatMessage au nœud observateur, utilisez la méthode Add et une commande semblable à la suivante :

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

Plusieurs tests peuvent être ajoutés en séparant leur nom par des virgules. Par exemple :

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

Notez qu’une erreur se produit si un ou plusieurs de ces tests (par exemple DataConference) a déjà été activé sur le nœud observateur. Dans ce cas, vous recevez un message d’erreur semblable au suivant :

    Set-CsWatcherNodeConfiguration : il existe une combinaison de clés dupliquée « DataConference » pour la clé « urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName » ou une contrainte d'identité unique.

Lorsque cette erreur se produit, aucune modification n’est appliquée. La commande doit être réexécutée en supprimant le test dupliqué.

Pour supprimer une transaction synthétique d’un nœud observateur, utilisez la méthode Remove plutôt que la méthode Add. Par exemple, la commande suivante supprime le test ABWQ d’un nœud observateur :

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

Vous pouvez aussi utiliser la méthode Replace pour remplacer tous les tests activés actuellement par un ou plusieurs nouveaux tests. Par exemple, si vous souhaitez que le nœud observateur exécute seulement le test de messagerie instantanée, vous pouvez exécuter la commande suivante :

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

Lorsque vous exécutez cette commande, toutes les transactions synthétiques sur le nœud observateur spécifié sont désactivées, à l’exception de la messagerie instantanée.

## Affichage et test de la configuration du nœud observateur

Si vous souhaitez afficher les tests qui ont été assignés à un nœud observateur, exécutez une commande semblable à la suivante :

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

Cette commande retourne des informations semblables aux suivantes, en fonction des transactions synthétiques qui ont été assignées au nœud :

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference

> [!TIP]  
> Pour afficher les transactions synthétiques par ordre alphabétique, exécutez plutôt la commande suivante :<br />
Get-CsWatcherNodeConfiguration –Identity &quot;atl-cs-001.litwareinc.com&quot; | Select-Object –ExpandProperty Tests | Sort-Object

Pour vérifier qu’un nœud observateur a été créé, tapez la commande suivante à partir de Lync Server Management Shell :

    Get-CsWatcherNodeConfiguration

Des informations analogues aux suivantes seront retournées :

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

Pour vérifier que le nœud observateur a été configuré correctement, tapez la commande suivante à partir de Lync Server Management Shell :

    Test-CsWatcherNodeConfiguration

Cette commande teste chaque nœud observateur de votre déploiement et indique notamment :

  - si le rôle de serveur d’inscriptions requis a été installé ;

  - si la clé de Registre nécessaire a été créée pour vous lors de l’exécution de Set-CsWatcherNodeConfiguration ;

  - Si vos serveurs exécutent la version correcte de Lync Server ;

  - si vos ports ont été configurés correctement ;

  - si vos utilisateurs de test assignés disposent des informations d’identification requises.

