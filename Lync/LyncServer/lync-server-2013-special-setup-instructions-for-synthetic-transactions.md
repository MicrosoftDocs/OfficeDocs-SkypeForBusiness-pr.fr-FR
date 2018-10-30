---
title: Instructions d’installation spéciales pour les transactions synthétiques
TOCTitle: Instructions d’installation spéciales pour les transactions synthétiques
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49891380
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instructions d’installation spéciales pour les transactions synthétiques

 

_**Dernière rubrique modifiée :** 2015-11-16_

La plupart des transactions synthétiques peuvent s’exécuter sur un nœud observateur en l’état ; en d’autres termes, dès que la transaction synthétique est ajoutée aux paramètres de configuration du nœud observateur, ce dernier peut commencer à utiliser la transaction synthétique lors de ses tests. Cependant, ce n’est pas le cas pour toutes les transactions synthétiques. Les exceptions, c’est-à-dire les transactions synthétiques qui nécessitent des instructions d’installation spéciales, sont traitées dans les sections suivantes.

## Transactions synthétiques de conférence de données

Si votre ordinateur nœud observateur se situe à l’extérieur de votre réseau de périmètre, vous ne pourrez probablement pas exécuter la transaction synthétique de conférence de données à moins que vous ne désactiviez au préalable les paramètres proxy d’Internet Explorer pour le compte Service réseau. Pour désactiver les paramètres proxy pour ce service, procédez comme suit :

1.  Sur l’ordinateur nœud observateur, cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Accessoires**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.

2.  Dans la fenêtre de console, tapez la commande suivante, puis appuyez sur Entrée :
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

Le message suivant s’affiche dans la fenêtre commande :

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

Ce message signifie que vous avez désactivé les paramètres proxy d’Internet Explorer pour le compte Service réseau.

## Transactions synthétiques de la messagerie unifiée Exchange

La transaction synthétique de la messagerie unifiée Exchange vérifie que les utilisateurs test peuvent se connecter à des comptes de messagerie vocale hébergés dans Exchange. Ces utilisateurs doivent être préconfigurés avec des comptes de messagerie vocale avant qu’ils ne puissent utiliser les tests de messagerie unifiée Exchange.

## Transactions synthétiques de conversation permanente

Pour utiliser la transaction synthétique de conversation permanente, les administrateurs doivent d’abord créer un canal et donner aux utilisateurs test l’autorisation de l’utiliser. L’applet de commande [Test-CsPersistentChatMessage](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsPersistentChatMessage) peut être utilisée pour configurer correctement ces utilisateurs test :

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

Cette tâche de configuration doit être exécutée au sein de l’entreprise :

  - Si elle est exécutée à partir d’un ordinateur non-serveur, l’utilisateur qui exécute l’applet de commande doit être membre du rôle PersistentChatAdministrators pour le contrôle d’accès en fonction du rôle.

  - Si elle est exécutée à partir du serveur lui-même, l’utilisateur qui exécute l’applet de commande doit être un membre du groupe RTCUniversalServerAdmins.

Dans la commande précédente, le paramètre Setup est inclus et a la valeur True ($True). Si vous incluez le paramètre Setup, Test-CsPersistentChatMessage crée une salle de conversation permanente spéciale et remplit cette salle avec les utilisateurs test. Cela permet de s’assurer qu’il y a bien une salle de conversation disponible à des fins de test. Notez que le paramètre Setup doit uniquement être exécuté à partir d’un serveur frontal.

La salle de conversation créée par Test-CsPersistentChatMessage ne peut être supprimée que par un administrateur.

## Transactions synthétiques pour les appels d’égal à égal PSTN

La transaction synthétique [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsPstnPeerToPeerCall) vérifie la capacité de passer et de recevoir des appels via le réseau téléphonique commuté (PSTN).

Pour exécuter cette transaction synthétique, les administrateurs doivent configurer les éléments suivants :

  - Deux utilisateurs test (un appelant et un récepteur) activés pour Voix Entreprise

  - Numéros de sélection directe à l’arrivée (SDA) pour chaque compte d’utilisateur

  - Stratégies de voix et itinéraires des communications vocales qui permettent aux appels au numéro du récepteur d’atteindre la passerelle PSTN

  - Passerelle PSTN qui accepte les appels, et médias qui acheminent les appels au pool d’accueil d’un récepteur en fonction du numéro composé

## Transactions synthétiques du magasin de contacts unifié

La transaction synthétique du magasin de contacts unifié vérifie que Lync Server 2013 est capable de récupérer des contacts au nom d’un utilisateur de Microsoft Exchange Server 2013.

Pour utiliser cette transaction synthétique, les conditions suivantes doivent être remplies :

  - [Gestion de l’authentification serveur à serveur (Oauth) et des applications partenaires dans Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) doit être configuré entre Lync Server 2013 et Exchange 2013 ;

  - les utilisateurs test doivent avoir une boîte aux lettres Exchange 2013 valide.

Une fois ces conditions remplies, les administrateurs peuvent exécuter la commande suivante pour vérifier que l’utilisateur avec l’adresse SIP kenmyer@litwareinc.com peut récupérer ses contacts à partir du magasin de contacts unifié :

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

Notez l’utilisation du paramètre Setup dans la commande précédente. Si le paramètre Setup est inclus lors de l’exécution de Test-CsUnifiedContactStore, les contacts de l’utilisateur spécifié (dans ce cas, sip:kenmyer@litwareinc.com) sont déplacés vers le magasin de contacts unifié. (Bien sûr, si les contacts de l’utilisateur sont déjà dans le magasin de contacts unifié, ils ne sont pas déplacés.) Le paramètre Setup n’est généralement utilisé qu’une seule fois (la première fois que Test-CsUnifiedContactStore est exécuté) et doit uniquement être utilisé avec des utilisateurs test, c’est-à-dire des comptes d’utilisateur qui ne seront jamais connectés à Lync Server. Une fois que votre utilisateur test est migré vers le magasin de contacts unifié, vous pouvez vérifier qu’il est possible de récupérer les contacts de l’utilisateur en appelant CsUnifiedContactStore-Test sans le paramètre Setup :

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

## Transactions synthétiques XMPP

La transaction synthétique de messagerie instantanée XMPP (Extensible Messaging and Presence Protocol) requiert que la fonctionnalité XMPP soit configurée avec un ou plusieurs domaines fédérés.

Pour activer la transaction synthétique XMPP, un paramètre XmppTestReceiverMailAddress doit être fourni avec un compte d’utilisateur au niveau d’un domaine XMPP routable. Par exemple :

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

Dans cet exemple, une règle Lync Server 2013 doit exister pour router les messages pour litwareinc.com vers une passerelle XMPP.

