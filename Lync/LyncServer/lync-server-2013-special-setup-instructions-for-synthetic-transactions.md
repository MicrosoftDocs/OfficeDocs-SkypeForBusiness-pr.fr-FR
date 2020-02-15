---
title: 'Lync Server 2013 : instructions de configuration spéciales pour les transactions synthétiques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a749e4349f6dae6ab7cae079af443734f9cfbc15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a>Instructions de configuration spéciales pour les transactions synthétiques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-11-16_

La plupart des transactions synthétiques peuvent s’exécuter sur un nœud observateur en l’état ; en d’autres termes, dès que la transaction synthétique est ajoutée aux paramètres de configuration du nœud observateur, ce dernier peut commencer à utiliser la transaction synthétique lors de ses tests. Cependant, ce n’est pas le cas pour toutes les transactions synthétiques. Les exceptions, c’est-à-dire les transactions synthétiques qui nécessitent des instructions d’installation spéciales, sont traitées dans les sections suivantes.

<div>

## <a name="dealing-with-server-timeout-errors"></a>Traitement des erreurs de délai d’attente du serveur

Dans certains cas, vous pouvez constater que vos transactions synthétiques échouent avec des erreurs de délai d’attente du serveur (code d’erreur 504). Ces erreurs sont généralement dues à des problèmes de pare-feu. Lorsqu’une transaction synthétique est exécutée, cette transaction s’exécute sous le processus MonitoringHost. exe ; MonitoringHost. exe démarre ensuite une instance du processus PowerShell. exe. Si MonitoringHost. exe ou PowerShell. exe est bloqué par votre pare-feu, la transaction synthétique échoue et génère une erreur 504.

Pour résoudre ce problème, vous devez créer manuellement les règles de pare-feu entrant pour MonitoringHost. exe et PowerShell. exe sur l’ordinateur local. Cette opération peut être réalisée via le pare-feu Windows ou un logiciel de pare-feu local tiers, en fonction de la configuration préexistante de votre serveur.

Si vous utilisez un pare-feu réseau entre l’ordinateur hôte de transactions synthétiques et les serveurs Lync que vous tentez de surveiller, vous devez traiter l’hôte comme un ordinateur client et observer toutes les exigences de port de pare-feu des [ports et des protocoles pour les serveurs internes dans Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a>Transactions synthétiques de conférence de données

Si votre ordinateur nœud observateur se trouve en dehors de votre réseau de périmètre, vous ne pourrez probablement pas exécuter la transaction synthétique de conférence de données, sauf si vous avez d’abord désactivé les paramètres de proxy Internet Explorer pour le compte service réseau. Pour désactiver les paramètres proxy pour ce service, procédez comme suit :

1.  Sur l’ordinateur sur lequel se trouve le nœud observateur, cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Accessoires**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.

2.  Dans la fenêtre de console, tapez la commande suivante, puis appuyez sur Entrée :
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

Le message suivant s’affiche dans la fenêtre commande :

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

Ce message signifie que vous avez désactivé les paramètres de proxy Internet Explorer pour le compte service réseau.

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a>Transactions synthétiques de la messagerie unifiée Exchange

La transaction synthétique de messagerie unifiée Exchange vérifie que les utilisateurs de test peuvent se connecter aux comptes de messagerie instantanée hébergés dans Exchange. Ces utilisateurs doivent être préconfigurés avec des comptes de messagerie vocale avant qu’ils ne puissent utiliser les tests de messagerie unifiée Exchange.

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a>Transactions synthétiques de conversation permanente

Pour utiliser la transaction synthétique de conversation permanente, les administrateurs doivent d’abord créer un canal et donner aux utilisateurs test les autorisations leur permettant de l’utiliser. La cmdlet [test-cspersistentchatmessage ne](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) peut être utilisée pour configurer correctement ces utilisateurs de test :

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

Cette tâche de configuration doit être exécutée au sein de l’entreprise :

  - Si elle est exécutée à partir d’un ordinateur non-serveur, l’utilisateur qui exécute l’applet de commande doit être membre du rôle PersistentChatAdministrators pour le contrôle d’accès en fonction du rôle.

  - Si elle est exécutée à partir du serveur lui-même, l’utilisateur qui exécute l’applet de commande doit être un membre du groupe RTCUniversalServerAdmins.

Dans la commande précédente, le paramètre Setup est inclus et a la valeur True ($True). Si vous incluez le paramètre Setup, test-Cspersistentchatmessage ne créera une salle de conversation permanente spéciale et remplira cette salle avec les utilisateurs de test. Cela permet de s’assurer qu’il y a bien une salle de conversation disponible à des fins de test. Notez que le paramètre Setup ne doit être exécuté qu’à partir d’un serveur frontal.

La salle de conversation créée par Test-CsPersistentChatMessage ne peut être supprimée que par un administrateur.

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a>Transactions synthétiques pour les appels d’égal à égal PSTN

La transaction synthétique [test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) vérifie la capacité de passer et de recevoir des appels via le réseau téléphonique commuté (PSTN).

Pour exécuter cette transaction synthétique, les administrateurs doivent configurer les éléments suivants :

  - Deux utilisateurs de test (un appelant et un récepteur) activés pour voix entreprise.

  - Numéros de sélection directe à l’arrivée (SDA) pour chaque compte d’utilisateur

  - Stratégies de voix et itinéraires des communications vocales qui permettent aux appels au numéro du récepteur d’atteindre la passerelle PSTN

  - Passerelle PSTN qui accepte les appels, et médias qui acheminent les appels au pool d’accueil d’un récepteur en fonction du numéro composé

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a>Transactions synthétiques du magasin de contacts unifié

La transaction synthétique du magasin de contacts unifié vérifie que Lync Server 2013 est capable de récupérer des contacts au nom d’un utilisateur à partir de Microsoft Exchange Server 2013.

Pour utiliser cette transaction synthétique, les conditions suivantes doivent être remplies :

  - La [gestion de l’authentification de serveur à serveur (OAuth) et des applications partenaires dans Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) doit être configurée entre lync Server 2013 et Exchange 2013.

  - Les utilisateurs test doivent disposer d’une boîte aux lettres Exchange 2013 valide.

Une fois ces conditions remplies, les administrateurs peuvent exécuter la commande suivante pour vérifier que l’utilisateur avec l’adresse SIP kenmyer@litwareinc.com peut récupérer ses contacts à partir du magasin de contacts unifié :

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

Notez l’utilisation du paramètre Setup dans la commande précédente. Si le paramètre Setup est inclus lors de l’exécution de Test-CsUnifiedContactStore, les contacts de l’utilisateur spécifié (dans ce cas, sip:kenmyer@litwareinc.com) sont déplacés vers le magasin de contacts unifié. (Bien entendu, si les contacts de l’utilisateur sont déjà dans le magasin de contacts unifié, il n’est pas nécessaire de le déplacer.) Le paramètre Setup n’est généralement utilisé qu’une seule fois (la première fois test-CsUnifiedContactStore est exécutée) et doit être utilisée uniquement avec les utilisateurs de test ; autrement dit, avec des comptes d’utilisateur qui ne seront jamais connectés à Lync Server. Une fois que votre utilisateur test est migré vers le magasin de contacts unifié, vous pouvez vérifier qu’il est possible de récupérer les contacts de l’utilisateur en appelant CsUnifiedContactStore-Test sans le paramètre Setup :

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a>Transactions synthétiques XMPP

La transaction synthétique de messagerie instantanée XMPP (Extensible Messaging and Presence Protocol) requiert que la fonctionnalité XMPP soit configurée avec un ou plusieurs domaines fédérés.

Pour activer la transaction synthétique XMPP, un paramètre XmppTestReceiverMailAddress doit être fourni avec un compte d’utilisateur au niveau d’un domaine XMPP routable. Par exemple :

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

Dans cet exemple, une règle Lync Server 2013 doit exister pour router les messages pour litwareinc.com vers une passerelle XMPP.

</div>

</div>

<span> </span>

</div>

</div>

</div>

