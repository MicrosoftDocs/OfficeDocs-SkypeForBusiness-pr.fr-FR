---
title: Exécuter la compatibilité descendante pour le serveur de conversation permanente
description: Exécutez la compatibilité descendante pour le serveur de conversation permanente.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0486992d44e6385559d3e9df9f9ffc2125120da
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570150"
---
# <a name="run-backward-compatibility-for-persistent-chat-server"></a><span data-ttu-id="f5355-103">Exécuter la compatibilité descendante pour le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="f5355-103">Run backward compatibility for Persistent Chat Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5355-104">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f5355-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f5355-105">Le point de terminaison Lync Server 2013, persistent Chat Server permet de créer une URL simple qui pointe vers un pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="f5355-105">The Lync Server 2013, Persistent Chat Server endpoint provides a way to create a simple URL that points to a Persistent Chat Server pool.</span></span> <span data-ttu-id="f5355-106">Cette fonctionnalité est utile pour les clients hérités (serveur de conversation de groupe Microsoft Office Communications Server 2007 R2 ou Lync Server 2010, conversation de groupe), car les utilisateurs peuvent entrer une URL simple dans la configuration manuelle lorsqu’ils tentent de faire pointer le client hérité vers un ordinateur exécutant Lync 2013, conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="f5355-106">This is useful for legacy clients (Microsoft Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat) because users can enter a simple URL in the manual configuration when trying to point the legacy client to a computer running Lync 2013, Persistent Chat.</span></span> <span data-ttu-id="f5355-107">Ce point de terminaison n’est pas utilisé par la conversation permanente et est requis uniquement pour les clients hérités.</span><span class="sxs-lookup"><span data-stu-id="f5355-107">This endpoint isn’t used by Persistent Chat, and is required for legacy clients only.</span></span> <span data-ttu-id="f5355-108">Cela est utile pour la période intermédiaire où les salles peuvent être migrées, mais les clients Lync 2013 n’ont pas été déployés au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="f5355-108">This is useful for the interim period where rooms may be migrated, but the Lync 2013 clients have not been deployed throughout the organization.</span></span> <span data-ttu-id="f5355-109">Les utilisateurs exécutant Lync 2010 Group chat (client) peuvent toujours se connecter au serveur principal du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="f5355-109">Users running Lync 2010 Group Chat (client) can then still connect to the Persistent Chat Server Back End Server.</span></span>

<span data-ttu-id="f5355-110">Vous n’avez pas besoin de créer plusieurs points de terminaison de serveur de conversation permanente ; il vous suffit d’en avoir un pour chaque pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="f5355-110">You don’t need to create multiple Persistent Chat Server endpoints; you just need one for each Persistent Chat Server pool.</span></span> <span data-ttu-id="f5355-111">Les administrateurs peuvent créer plusieurs points de terminaison (un par pool), mais les clients hérités peuvent être configurés pour se connecter à un seul pool à la fois.</span><span class="sxs-lookup"><span data-stu-id="f5355-111">Administrators can create multiple endpoints (one per pool), but legacy clients can be configured to connect to only one pool at a time.</span></span> <span data-ttu-id="f5355-112">Dans le scénario classique ou standard, le déploiement hérité est un seul pool.</span><span class="sxs-lookup"><span data-stu-id="f5355-112">In the usual or mainstream scenario, the legacy deployment is one pool only.</span></span> <span data-ttu-id="f5355-113">Un nouveau déploiement migre généralement ce pool vers un nouveau Lync Server 2013 et peut ajouter des pools de serveurs de conversation permanente supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="f5355-113">A new deployment generally migrates that pool to a new Lync Server 2013 and might add some new additional Persistent Chat Server pools.</span></span>

<span data-ttu-id="f5355-114">Ce scénario standard suit généralement ce modèle :</span><span class="sxs-lookup"><span data-stu-id="f5355-114">This mainstream scenario generally follows this pattern:</span></span>

  - <span data-ttu-id="f5355-115">Vous administrez les utilisateurs avec un pool Lync Server 2010, Group chat et vos clients Lync 2010 Group chat se connectent à ce pool à l’aide d’un utilisateur connu (SIP par défaut : ocschat@ \<domainName\> . com ou similaire).</span><span class="sxs-lookup"><span data-stu-id="f5355-115">You administer users with one Lync Server 2010, Group Chat pool, and your Lync 2010 Group Chat clients connect to that pool by using some well-known user (either default sip:ocschat@\<domainName\>.com, or a similar one).</span></span> <span data-ttu-id="f5355-116">Les utilisateurs sont des services de domaine Active Directory compatibles SIP, et le service de recherche s’inscrit auprès de ces derniers pour recevoir des demandes entrantes.</span><span class="sxs-lookup"><span data-stu-id="f5355-116">The users are SIP-enabled Active Directory Domain Services, and the Lookup service registers with them to receive incoming requests.</span></span>

  - <span data-ttu-id="f5355-117">Par la suite, vous installez un serveur de conversation permanente Lync Server 2013 et un pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="f5355-117">Subsequently, you install a Lync Server 2013 Persistent Chat Server and Persistent Chat Server pool.</span></span>

  - <span data-ttu-id="f5355-118">Pendant un moment où les utilisateurs sont généralement hors connexion (par exemple, un week-end) :</span><span class="sxs-lookup"><span data-stu-id="f5355-118">During a time when users are generally offline (for example, a weekend):</span></span>
    
      - <span data-ttu-id="f5355-119">Désactivez Lync Server 2010, Group chat.</span><span class="sxs-lookup"><span data-stu-id="f5355-119">Turn off Lync Server 2010, Group Chat.</span></span>
    
      - <span data-ttu-id="f5355-120">Migrez les données du pool de conversation de groupe Lync Server 2010 vers le pool de serveurs Lync Server 2013 persistent chat.</span><span class="sxs-lookup"><span data-stu-id="f5355-120">Migrate data from the Lync Server 2010, Group Chat pool to the Lync Server 2013 Persistent Chat Server pool.</span></span>
    
      - <span data-ttu-id="f5355-121">Supprimez l’utilisateur connu des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f5355-121">Delete the well-known user from the Active Directory Domain Services.</span></span>
    
      - <span data-ttu-id="f5355-122">Créez un *point de terminaison hérité* avec le même URI SIP que l’utilisateur connu précédemment supprimé.</span><span class="sxs-lookup"><span data-stu-id="f5355-122">Create a new *legacy endpoint* with the same SIP URI as the previously deleted well-known user.</span></span>
    
      - <span data-ttu-id="f5355-123">Démarrez les serveurs Lync Server 2013, persistent chat.</span><span class="sxs-lookup"><span data-stu-id="f5355-123">Start the Lync Server 2013, Persistent Chat Servers.</span></span>

  - <span data-ttu-id="f5355-124">Les utilisateurs se connectent à l’aide de leur service de conversation de groupe Lync 2010 (client) et se connectent à leurs données sans avoir à modifier la configuration.</span><span class="sxs-lookup"><span data-stu-id="f5355-124">Users log back on by using their Lync 2010 Group Chat (client) and connect to their data without needing to change any configuration.</span></span>

  - <span data-ttu-id="f5355-125">Par la suite, vous pouvez mettre hors service le Lync Server 2010, Group chat.</span><span class="sxs-lookup"><span data-stu-id="f5355-125">At a later time, you can decommission the Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="f5355-126">Par la suite, vous pouvez déployer Lync Server 2013, le serveur de conversation permanente et installer les nouveaux pools de serveurs de conversation permanente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5355-126">Subsequently, you can deploy Lync Server 2013, Persistent Chat Server, and install new Lync Server 2013 Persistent Chat Server pools.</span></span>

<span data-ttu-id="f5355-127">Pour plus d’informations sur la migration de Lync Server 2010, Group chat vers Lync Server 2013, persistent Chat Server, voir [migration from Lync server 2010, Group chat ou Office Communications server 2007 R2 Group chat to Lync Server 2013, persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="f5355-127">For details about migrating from Lync Server 2010, Group Chat to Lync Server 2013, Persistent Chat Server, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="f5355-128">Pour exécuter la compatibilité descendante (pour créer un point de terminaison de serveur de conversation permanente qui pointe vers un pool de serveurs de conversation permanente, qui peut être utilisé par les clients de pool de conversation de groupe hérités) :</span><span class="sxs-lookup"><span data-stu-id="f5355-128">To run backward compatibility (to create a Persistent Chat Server endpoint that points to a Persistent Chat Server pool, which can be used by legacy Group Chat pool clients):</span></span>

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

<span data-ttu-id="f5355-129">Ensuite, configurez les clients de conversation permanente de sorte qu’ils utilisent cette adresse SIP comme objet contact.</span><span class="sxs-lookup"><span data-stu-id="f5355-129">Next, configure Persistent Chat clients to use that SIP address as their contact object.</span></span> <span data-ttu-id="f5355-130">L’adresse SIP est créée avec la cmdlet **New-CsPersistentChatEndpoint** pour un pool de serveurs de conversation permanente spécifique.</span><span class="sxs-lookup"><span data-stu-id="f5355-130">The SIP address is created with the **New-CsPersistentChatEndpoint** cmdlet for a specific Persistent Chat Server pool.</span></span>

<span data-ttu-id="f5355-131">Pour ajouter le point de terminaison du serveur de conversation permanente à l’aide de l’interface de ligne de commande Windows PowerShell, tenez compte de l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="f5355-131">To add the Persistent Chat Server endpoint by using Windows PowerShell command-line interface, consider the following example.</span></span> <span data-ttu-id="f5355-132">Dans ce cas, vous configurez l’objet contact de sorte qu’il soit nommé « persistentchat » sur la topologie « contoso.com », où le nom de domaine complet (FQDN) du pool est « pcpool.contoso.com » :</span><span class="sxs-lookup"><span data-stu-id="f5355-132">In this case, you are configuring the contact object to be named "persistentchat" on the "contoso.com" topology, where the pool fully qualified domain name (FQDN) is "pcpool.contoso.com":</span></span>

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a><span data-ttu-id="f5355-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f5355-133">See Also</span></span>


[<span data-ttu-id="f5355-134">Migration de Lync Server 2010, conversation de groupe ou de la conversation de groupe Office Communications Server 2007 R2 vers Lync Server 2013, Serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="f5355-134">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

