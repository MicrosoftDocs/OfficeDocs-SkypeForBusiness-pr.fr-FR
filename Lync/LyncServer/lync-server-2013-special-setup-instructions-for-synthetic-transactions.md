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

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="597f2-102">Instructions de configuration spéciales pour les transactions synthétiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="597f2-102">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="597f2-103">_**Dernière modification de la rubrique :** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="597f2-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="597f2-p101">La plupart des transactions synthétiques peuvent s’exécuter sur un nœud observateur en l’état ; en d’autres termes, dès que la transaction synthétique est ajoutée aux paramètres de configuration du nœud observateur, ce dernier peut commencer à utiliser la transaction synthétique lors de ses tests. Cependant, ce n’est pas le cas pour toutes les transactions synthétiques. Les exceptions, c’est-à-dire les transactions synthétiques qui nécessitent des instructions d’installation spéciales, sont traitées dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="597f2-p101">Most synthetic transactions can run on a watcher node as-is; that is, as soon as the synthetic transaction has been added to the watcher node configuration settings, the watcher node can begin using the synthetic transaction during its test passes. However, this is not true for all synthetic transactions. The exceptions—synthetic transactions that require special setup instructions—are discussed in the following sections.</span></span>

<div>

## <a name="dealing-with-server-timeout-errors"></a><span data-ttu-id="597f2-107">Traitement des erreurs de délai d’attente du serveur</span><span class="sxs-lookup"><span data-stu-id="597f2-107">Dealing With Server Timeout Errors</span></span>

<span data-ttu-id="597f2-108">Dans certains cas, vous pouvez constater que vos transactions synthétiques échouent avec des erreurs de délai d’attente du serveur (code d’erreur 504).</span><span class="sxs-lookup"><span data-stu-id="597f2-108">In some cases you might find that your synthetic transactions are failing with server timeout errors (error code 504).</span></span> <span data-ttu-id="597f2-109">Ces erreurs sont généralement dues à des problèmes de pare-feu.</span><span class="sxs-lookup"><span data-stu-id="597f2-109">These errors are typically due to firewall problems.</span></span> <span data-ttu-id="597f2-110">Lorsqu’une transaction synthétique est exécutée, cette transaction s’exécute sous le processus MonitoringHost. exe ; MonitoringHost. exe démarre ensuite une instance du processus PowerShell. exe.</span><span class="sxs-lookup"><span data-stu-id="597f2-110">When a synthetic transaction is executed, that transaction runs under the MonitoringHost.exe process; in turn, MonitoringHost.exe starts an instance of the PowerShell.exe process.</span></span> <span data-ttu-id="597f2-111">Si MonitoringHost. exe ou PowerShell. exe est bloqué par votre pare-feu, la transaction synthétique échoue et génère une erreur 504.</span><span class="sxs-lookup"><span data-stu-id="597f2-111">If either MonitoringHost.exe or PowerShell.exe is blocked by your firewall then the synthetic transaction will fail and will generate a 504 error.</span></span>

<span data-ttu-id="597f2-112">Pour résoudre ce problème, vous devez créer manuellement les règles de pare-feu entrant pour MonitoringHost. exe et PowerShell. exe sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="597f2-112">To resolve this issue, you should manually create inbound firewall rules for both MonitoringHost.exe and PowerShell.exe on the local machine.</span></span> <span data-ttu-id="597f2-113">Cette opération peut être réalisée via le pare-feu Windows ou un logiciel de pare-feu local tiers, en fonction de la configuration préexistante de votre serveur.</span><span class="sxs-lookup"><span data-stu-id="597f2-113">This can be done via Windows firewall or a third-party local firewall software, depending on your server's preexisting configuration.</span></span>

<span data-ttu-id="597f2-114">Si vous utilisez un pare-feu réseau entre l’ordinateur hôte de transactions synthétiques et les serveurs Lync que vous tentez de surveiller, vous devez traiter l’hôte comme un ordinateur client et observer toutes les exigences de port de pare-feu des [ports et des protocoles pour les serveurs internes dans Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span><span class="sxs-lookup"><span data-stu-id="597f2-114">If you're employing a network firewall device between the synthetic transaction host machine and the Lync Servers you're attempting to monitor, you should treat the host as a client machine, and observer all firewall port requirements from [Ports and protocols for internal servers in Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span></span>

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a><span data-ttu-id="597f2-115">Transactions synthétiques de conférence de données</span><span class="sxs-lookup"><span data-stu-id="597f2-115">Data Conferencing Synthetic Transactions</span></span>

<span data-ttu-id="597f2-116">Si votre ordinateur nœud observateur se trouve en dehors de votre réseau de périmètre, vous ne pourrez probablement pas exécuter la transaction synthétique de conférence de données, sauf si vous avez d’abord désactivé les paramètres de proxy Internet Explorer pour le compte service réseau.</span><span class="sxs-lookup"><span data-stu-id="597f2-116">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Internet Explorer proxy settings for the Network Service account.</span></span> <span data-ttu-id="597f2-117">Pour désactiver les paramètres proxy pour ce service, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="597f2-117">To disable the proxy settings for this service, complete the following procedure:</span></span>

1.  <span data-ttu-id="597f2-118">Sur l’ordinateur sur lequel se trouve le nœud observateur, cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Accessoires**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="597f2-118">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="597f2-119">Dans la fenêtre de console, tapez la commande suivante, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="597f2-119">In the console window, type the following command and then press ENTER:</span></span>
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

<span data-ttu-id="597f2-120">Le message suivant s’affiche dans la fenêtre commande :</span><span class="sxs-lookup"><span data-stu-id="597f2-120">The following message will appear in the command window:</span></span>

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

<span data-ttu-id="597f2-121">Ce message signifie que vous avez désactivé les paramètres de proxy Internet Explorer pour le compte service réseau.</span><span class="sxs-lookup"><span data-stu-id="597f2-121">This message means that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a><span data-ttu-id="597f2-122">Transactions synthétiques de la messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="597f2-122">Exchange Unified Messaging Synthetic Transactions</span></span>

<span data-ttu-id="597f2-123">La transaction synthétique de messagerie unifiée Exchange vérifie que les utilisateurs de test peuvent se connecter aux comptes de messagerie instantanée hébergés dans Exchange.</span><span class="sxs-lookup"><span data-stu-id="597f2-123">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span> <span data-ttu-id="597f2-124">Ces utilisateurs doivent être préconfigurés avec des comptes de messagerie vocale avant qu’ils ne puissent utiliser les tests de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="597f2-124">These test users will need to be preconfigured with voicemail accounts before they can use the Exchange UM tests.</span></span>

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a><span data-ttu-id="597f2-125">Transactions synthétiques de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="597f2-125">Persistent Chat Synthetic Transactions</span></span>

<span data-ttu-id="597f2-126">Pour utiliser la transaction synthétique de conversation permanente, les administrateurs doivent d’abord créer un canal et donner aux utilisateurs test les autorisations leur permettant de l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="597f2-126">To use the Persistent Chat synthetic transaction, administrators must first create a channel and give the test users permissions to use it.</span></span> <span data-ttu-id="597f2-127">La cmdlet [test-cspersistentchatmessage ne](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) peut être utilisée pour configurer correctement ces utilisateurs de test :</span><span class="sxs-lookup"><span data-stu-id="597f2-127">The [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet can be used to properly configure these test users:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

<span data-ttu-id="597f2-128">Cette tâche de configuration doit être exécutée au sein de l’entreprise :</span><span class="sxs-lookup"><span data-stu-id="597f2-128">This setup task must be run from inside the enterprise:</span></span>

  - <span data-ttu-id="597f2-129">Si elle est exécutée à partir d’un ordinateur non-serveur, l’utilisateur qui exécute l’applet de commande doit être membre du rôle PersistentChatAdministrators pour le contrôle d’accès en fonction du rôle.</span><span class="sxs-lookup"><span data-stu-id="597f2-129">If run from a nonserver machine, the user who runs the cmdlet must be a member of the PersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>

  - <span data-ttu-id="597f2-130">Si elle est exécutée à partir du serveur lui-même, l’utilisateur qui exécute l’applet de commande doit être un membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="597f2-130">If run from the server itself, the user who runs the cmdlet should be a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="597f2-131">Dans la commande précédente, le paramètre Setup est inclus et a la valeur True ($True).</span><span class="sxs-lookup"><span data-stu-id="597f2-131">In the preceding command, the Setup parameter was included and set to True ($True).</span></span> <span data-ttu-id="597f2-132">Si vous incluez le paramètre Setup, test-Cspersistentchatmessage ne créera une salle de conversation permanente spéciale et remplira cette salle avec les utilisateurs de test.</span><span class="sxs-lookup"><span data-stu-id="597f2-132">If you include the Setup parameter, Test-CsPersistentChatMessage will create a special Persistent Chat room and populate that room with the test users.</span></span> <span data-ttu-id="597f2-133">Cela permet de s’assurer qu’il y a bien une salle de conversation disponible à des fins de test.</span><span class="sxs-lookup"><span data-stu-id="597f2-133">This helps to ensure that there is actually a chat room available for testing purposes.</span></span> <span data-ttu-id="597f2-134">Notez que le paramètre Setup ne doit être exécuté qu’à partir d’un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="597f2-134">Note that the Setup parameter should be run only from a Front End Server.</span></span>

<span data-ttu-id="597f2-135">La salle de conversation créée par Test-CsPersistentChatMessage ne peut être supprimée que par un administrateur.</span><span class="sxs-lookup"><span data-stu-id="597f2-135">The chat room that is created by Test-CsPersistentChatMessage can be deleted only by an administrator.</span></span>

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a><span data-ttu-id="597f2-136">Transactions synthétiques pour les appels d’égal à égal PSTN</span><span class="sxs-lookup"><span data-stu-id="597f2-136">PSTN Peer-to-Peer Call Synthetic Transactions</span></span>

<span data-ttu-id="597f2-137">La transaction synthétique [test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) vérifie la capacité de passer et de recevoir des appels via le réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="597f2-137">The [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) synthetic transaction verifies the ability to place and receive calls via the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="597f2-138">Pour exécuter cette transaction synthétique, les administrateurs doivent configurer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="597f2-138">To run this synthetic transaction, administrators must configure:</span></span>

  - <span data-ttu-id="597f2-139">Deux utilisateurs de test (un appelant et un récepteur) activés pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="597f2-139">Two test users (a caller and a receiver) enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="597f2-140">Numéros de sélection directe à l’arrivée (SDA) pour chaque compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="597f2-140">Direct Inward Dialing (DID) numbers for each user account.</span></span>

  - <span data-ttu-id="597f2-141">Stratégies de voix et itinéraires des communications vocales qui permettent aux appels au numéro du récepteur d’atteindre la passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="597f2-141">Voice policies and voice routes that enable calls to the receiver’s number to reach the PSTN gateway.</span></span>

  - <span data-ttu-id="597f2-142">Passerelle PSTN qui accepte les appels, et médias qui acheminent les appels au pool d’accueil d’un récepteur en fonction du numéro composé</span><span class="sxs-lookup"><span data-stu-id="597f2-142">A PSTN gateway that accepts calls, and media that route calls backs to a receiver’s home pool based on the number dialed.</span></span>

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a><span data-ttu-id="597f2-143">Transactions synthétiques du magasin de contacts unifié</span><span class="sxs-lookup"><span data-stu-id="597f2-143">Unified Contact Store Synthetic Transactions</span></span>

<span data-ttu-id="597f2-144">La transaction synthétique du magasin de contacts unifié vérifie que Lync Server 2013 est capable de récupérer des contacts au nom d’un utilisateur à partir de Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="597f2-144">The Unified Contact Store synthetic transaction verifies that Lync Server 2013 is able to retrieve contacts on behalf of a user from Microsoft Exchange Server 2013.</span></span>

<span data-ttu-id="597f2-145">Pour utiliser cette transaction synthétique, les conditions suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="597f2-145">To use this synthetic transaction, the following conditions must be met:</span></span>

  - <span data-ttu-id="597f2-146">La [gestion de l’authentification de serveur à serveur (OAuth) et des applications partenaires dans Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) doit être configurée entre lync Server 2013 et Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="597f2-146">[Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) must be configured between Lync Server 2013 and Exchange 2013.</span></span>

  - <span data-ttu-id="597f2-147">Les utilisateurs test doivent disposer d’une boîte aux lettres Exchange 2013 valide.</span><span class="sxs-lookup"><span data-stu-id="597f2-147">Test users must have a valid Exchange 2013 mailbox.</span></span>

<span data-ttu-id="597f2-148">Une fois ces conditions remplies, les administrateurs peuvent exécuter la commande suivante pour vérifier que l’utilisateur avec l’adresse SIP kenmyer@litwareinc.com peut récupérer ses contacts à partir du magasin de contacts unifié :</span><span class="sxs-lookup"><span data-stu-id="597f2-148">After these conditions are met, administrators can run the following command to verify that the user with the SIP address kenmyer@litwareinc.com can retrieve his contacts from the unified contact store:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

<span data-ttu-id="597f2-149">Notez l’utilisation du paramètre Setup dans la commande précédente.</span><span class="sxs-lookup"><span data-stu-id="597f2-149">Note the use of the Setup parameter used in the preceding command.</span></span> <span data-ttu-id="597f2-150">Si le paramètre Setup est inclus lors de l’exécution de Test-CsUnifiedContactStore, les contacts de l’utilisateur spécifié (dans ce cas, sip:kenmyer@litwareinc.com) sont déplacés vers le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="597f2-150">If the Setup parameter is included when running Test-CsUnifiedContactStore then the specified user’s contacts (in this case, sip:kenmyer@litwareinc.com) will be moved to the unified contact store.</span></span> <span data-ttu-id="597f2-151">(Bien entendu, si les contacts de l’utilisateur sont déjà dans le magasin de contacts unifié, il n’est pas nécessaire de le déplacer.) Le paramètre Setup n’est généralement utilisé qu’une seule fois (la première fois test-CsUnifiedContactStore est exécutée) et doit être utilisée uniquement avec les utilisateurs de test ; autrement dit, avec des comptes d’utilisateur qui ne seront jamais connectés à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="597f2-151">(Of course, if the user’s contacts are already in the Unified Contact Store then they do not have to be moved.) The Setup parameter is typically used only one time (the first time Test-CsUnifiedContactStore is executed), and should only be used with test users; that is, with user accounts that will never actually be logged on to Lync Server.</span></span> <span data-ttu-id="597f2-152">Une fois que votre utilisateur test est migré vers le magasin de contacts unifié, vous pouvez vérifier qu’il est possible de récupérer les contacts de l’utilisateur en appelant CsUnifiedContactStore-Test sans le paramètre Setup :</span><span class="sxs-lookup"><span data-stu-id="597f2-152">After your test user has been migrated to the unified contact store, you can verify that the user’s contacts can be retrieved by calling Test-CsUnifiedContactStore without the Setup parameter:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a><span data-ttu-id="597f2-153">Transactions synthétiques XMPP</span><span class="sxs-lookup"><span data-stu-id="597f2-153">XMPP Synthetic Transactions</span></span>

<span data-ttu-id="597f2-154">La transaction synthétique de messagerie instantanée XMPP (Extensible Messaging and Presence Protocol) requiert que la fonctionnalité XMPP soit configurée avec un ou plusieurs domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="597f2-154">The XMPP (Extensible Messaging and Presence Protocol) IM synthetic transaction requires that the XMPP feature be configured with one or more federated domains.</span></span>

<span data-ttu-id="597f2-155">Pour activer la transaction synthétique XMPP, un paramètre XmppTestReceiverMailAddress doit être fourni avec un compte d’utilisateur au niveau d’un domaine XMPP routable.</span><span class="sxs-lookup"><span data-stu-id="597f2-155">To enable the XMPP synthetic transaction, an XmppTestReceiverMailAddress parameter must be provided with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="597f2-156">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="597f2-156">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

<span data-ttu-id="597f2-157">Dans cet exemple, une règle Lync Server 2013 doit exister pour router les messages pour litwareinc.com vers une passerelle XMPP.</span><span class="sxs-lookup"><span data-stu-id="597f2-157">In this example, a Lync Server 2013 rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

