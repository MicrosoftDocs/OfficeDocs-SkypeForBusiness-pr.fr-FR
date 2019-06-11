---
title: 'Lync Server 2013: instructions de configuration spéciales pour les transactions synthétiques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8c2f0f45aa2187f1b47f8dfa81b3ba121388f6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a>Instructions de configuration spéciales pour les transactions synthétiques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2015-11-16_

La plupart des transactions synthétiques peuvent s’exécuter sur un nœud d’observation en l’aspect; autrement dit, dès que la transaction synthétique a été ajoutée aux paramètres de configuration du nœud d’observation, le nœud d’observation peut commencer à utiliser la transaction synthétique lors de ses tests. Toutefois, ce n’est pas vrai pour toutes les transactions synthétiques. Les exceptions (transactions synthétiques qui nécessitent des instructions de configuration spéciales) sont décrites dans les sections suivantes.

<div>

## <a name="dealing-with-server-timeout-errors"></a>Gestion des erreurs de temporisation du serveur

Dans certains cas, il est possible que vous rencontriez des erreurs de temporisation serveur (code d’erreur 504). Ces erreurs se produisent généralement en raison de problèmes de pare-feu. Lors de l’exécution d’une transaction synthétique, cette transaction s’exécute sous le processus MonitoringHost. exe. en retour, MonitoringHost. exe démarre une instance du processus PowerShell. exe. Si MonitoringHost. exe ou PowerShell. exe est bloqué par votre pare-feu, la transaction synthétique échoue et génère une erreur 504.

Pour résoudre ce problème, vous devez créer manuellement des règles de pare-feu entrant pour MonitoringHost. exe et PowerShell. exe sur l’ordinateur local. Cette opération peut être réalisée via un pare-feu Windows ou un logiciel de pare-feu local tiers, en fonction de la configuration préexistante de votre serveur.

Si vous utilisez un pare-feu réseau entre l’ordinateur hôte de transactions synthétiques et les serveurs Lync que vous essayez de surveiller, vous devez traiter l’hôte en tant qu’ordinateur client et observer toutes les exigences de port de pare-feu pour les [ports et les protocoles. pour les serveurs internes dans Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a>Transactions synthétiques de conférence de données

Si votre ordinateur de nœud d’observateur se trouve en dehors de votre réseau de périmètre, vous ne pourrez probablement pas exécuter la transaction synthétique de conférence de données, sauf si vous désactivez d’abord les paramètres de proxy d’Internet Explorer pour le compte de service réseau. Pour désactiver les paramètres de proxy pour ce service, procédez comme suit:

1.  Sur l’ordinateur du nœud d’observation, cliquez sur **Démarrer**, sur **tous les programmes**, sur **accessoires**, cliquez avec le bouton droit sur **invite de commandes**, puis cliquez sur **exécuter en tant qu’administrateur**.

2.  Dans la fenêtre de la console, tapez la commande suivante, puis appuyez sur entrée:
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

Le message suivant s’affiche dans la fenêtre de commande:

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

Ce message signifie que vous avez désactivé les paramètres de proxy d’Internet Explorer pour le compte de service réseau.

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a>Transactions synthétiques de la messagerie unifiée Exchange

La transaction synthétique de la messagerie unifiée Exchange vérifie que les utilisateurs test peuvent se connecter à des comptes de messagerie vocale hébergés dans Exchange. Ces utilisateurs doivent être préconfigurés avec des comptes de messagerie vocale pour pouvoir utiliser les tests de MU Exchange.

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a>Transactions synthétiques de conversation permanente

Pour utiliser la transaction synthétique des conversations permanentes, les administrateurs doivent d’abord créer un canal et donner aux utilisateurs du test l’autorisation d’utiliser ce dernier. L’applet de [contrôle test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) peut être utilisée pour configurer correctement ces utilisateurs de test:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

Cette tâche de configuration doit être exécutée au sein de l’entreprise:

  - S’il est exécuté à partir d’un ordinateur non serveur, l’utilisateur qui exécute l’applet de commande doit être membre du rôle PersistentChatAdministrators pour le contrôle d’accès basé sur les rôles (RBAC).

  - S’il est exécuté sur le serveur lui-même, l’utilisateur qui exécute l’applet de contrôle doit être membre du groupe RTCUniversalServerAdmins.

Dans la commande précédente, le paramètre d’installation était inclus et défini sur true ($True). Si vous incluez le paramètre Setup, test-CsPersistentChatMessage créer une salle de conversation persistante spéciale et remplira cette salle auprès des utilisateurs test. Cela permet de s’assurer qu’une salle de conversation est réellement disponible aux fins de test. Notez que le paramètre d’installation ne doit être exécuté qu’à partir d’un serveur frontal.

La salle de conversation créée par test-CsPersistentChatMessage peut être supprimée uniquement par un administrateur.

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a>Transactions synthétiques d’appels d’égal à égal RTC

La transaction synthétique [test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) vérifie la possibilité de passer et de recevoir des appels par le biais du réseau téléphonique public commuté (RTC).

Pour exécuter cette transaction synthétique, les administrateurs doivent configurer les éléments suivants:

  - Deux utilisateurs de test (un appelant et un destinataire) activés pour voix entreprise.

  - Numéros de sélection directe à l’arrivée (SDA) pour chaque compte d’utilisateur.

  - Politiques vocales et itinéraires vocaux permettant d’appeler le numéro du destinataire pour joindre la passerelle PSTN.

  - Passerelle RTC qui accepte les appels et les éléments multimédias qui acheminent les appels vers les appels vers le pool d’hébergement d’un destinataire en fonction du numéro composé.

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a>Transactions synthétiques du magasin de contacts unifié

La transaction synthétique du magasin de contacts unifié vérifie que Lync Server 2013 est en mesure de récupérer des contacts de la part d’un utilisateur à partir de Microsoft Exchange Server 2013.

Pour utiliser cette transaction synthétique, les conditions suivantes doivent être remplies :

  - La [gestion de l’authentification de serveur à serveur (OAuth) et des applications partenaires dans Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) doivent être configurées entre lync Server 2013 et Exchange 2013.

  - Les utilisateurs test doivent avoir une boîte aux lettres Exchange 2013 valide.

Une fois ces conditions satisfaites, les administrateurs peuvent exécuter la commande suivante pour vérifier que l’utilisateur possédant l’adresse kenmyer@litwareinc.com peut récupérer ses contacts auprès du magasin de contacts unifié:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

Notez l’utilisation du paramètre Setup utilisé dans la commande précédente. Si le paramètre d’installation est inclus lors de l’exécution de test-CsUnifiedContactStore, les contacts de l’utilisateur spécifié (dans ce cas, sip:kenmyer@litwareinc.com) seront déplacés vers le magasin de contacts unifié. (Bien entendu, si le contact de l’utilisateur se trouve déjà dans le magasin de contacts unifié, il n’est pas nécessaire de le déplacer.) Le paramètre Setup est généralement utilisé une seule fois (la première fois que le test-CsUnifiedContactStore est exécuté) et doit être utilisé uniquement avec les utilisateurs test. c’est-à-dire, avec les comptes d’utilisateurs qui ne seront jamais enregistrés sur Lync Server. Après la migration de votre utilisateur de test vers le magasin de contacts unifié, vous pouvez vérifier que les contacts de l’utilisateur peuvent être récupérés en appelant test-CsUnifiedContactStore sans le paramètre d’installation:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a>Transactions synthétiques XMPP

La transaction synthétique de messagerie instantanée (extensible Messaging and Presence Protocol) nécessite que la fonctionnalité XMPP soit configurée avec un ou plusieurs domaines fédérés.

Pour activer la transaction synthétique XMPP, un paramètre XmppTestReceiverMailAddress doit être fourni avec un compte d’utilisateur sur un domaine XMPP routable. Par exemple :

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

Dans cet exemple, une règle Lync Server 2013 doit exister pour acheminer les messages pour litwareinc.com vers une passerelle XMPP.

</div>

</div>

<span> </span>

</div>

</div>

</div>

