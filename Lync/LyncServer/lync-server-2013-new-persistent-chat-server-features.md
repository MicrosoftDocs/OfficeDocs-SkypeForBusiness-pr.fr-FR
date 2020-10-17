---
title: 'Lync Server 2013 : nouvelles fonctionnalités de serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd9288fea9105be27428ac94d992de6e147f4900
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534181"
---
# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a><span data-ttu-id="5af44-102">Nouvelles fonctionnalités de serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5af44-102">New Persistent Chat Server features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5af44-103">_**Dernière modification de la rubrique :** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="5af44-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="5af44-104">Lync Server 2013, serveur de conversation permanente vous permet de participer à des conversations en plusieurs rubriques, qui sont conservées au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="5af44-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="5af44-105">Le serveur de conversation permanente peut aider votre organisation à effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5af44-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="5af44-106">améliorer la communication entre les équipes géographiquement dispersées et multifonctionnelles ;</span><span class="sxs-lookup"><span data-stu-id="5af44-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="5af44-107">élargir la prise en compte des informations et la participation ;</span><span class="sxs-lookup"><span data-stu-id="5af44-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="5af44-108">améliorer la communication dans l’ensemble de votre organisation ;</span><span class="sxs-lookup"><span data-stu-id="5af44-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="5af44-109">réduire la surcharge d’informations ;</span><span class="sxs-lookup"><span data-stu-id="5af44-109">Reduce information overload</span></span>

  - <span data-ttu-id="5af44-110">améliorer la prise en compte des informations ;</span><span class="sxs-lookup"><span data-stu-id="5af44-110">Improve information awareness</span></span>

  - <span data-ttu-id="5af44-111">accroître la dissémination des connaissances et des informations importantes.</span><span class="sxs-lookup"><span data-stu-id="5af44-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="5af44-112">Lync Server 2013, le serveur de conversation permanente n’est pas disponible dans Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="5af44-112">Lync Server 2013, Persistent Chat Server is not available in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="5af44-113">Pour le moment, il n’est disponible que pour les clients Lync 2013 locaux.</span><span class="sxs-lookup"><span data-stu-id="5af44-113">At this time, it is available only to on-premise Lync 2013 customers.</span></span>

<span data-ttu-id="5af44-114">Dans Lync 2013, la fonctionnalité de conversation permanente est intégrée au client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5af44-114">In Lync 2013, Persistent Chat functionality is integrated into the Lync 2013 client.</span></span> <span data-ttu-id="5af44-115">Par conséquent, les utilisateurs ont accès à la messagerie instantanée/présence, audio/vidéo, à la Conférence et à la conversation permanente dans le client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5af44-115">As a result, users have access to Instant Messaging/Presence, Audio/Video, Conferencing, and Persistent Chat all in the Lync 2013 client.</span></span> <span data-ttu-id="5af44-116">Pour plus d’informations sur le client Lync 2013, voir <https://go.microsoft.com/fwlink/p/?linkid=270877> .</span><span class="sxs-lookup"><span data-stu-id="5af44-116">For more information about the Lync 2013 client, see <https://go.microsoft.com/fwlink/p/?linkid=270877>.</span></span>

<span data-ttu-id="5af44-117">Cette rubrique décrit les modifications apportées aux fonctionnalités entre la nouvelle version de Lync Server 2013, le serveur de conversation permanente et la version précédente (Microsoft Lync Server 2010, Group chat), notamment :</span><span class="sxs-lookup"><span data-stu-id="5af44-117">This topic describes feature changes between the new version of Lync Server 2013, Persistent Chat Server and the previous version (Microsoft Lync Server 2010, Group Chat), including:</span></span>

  - <span data-ttu-id="5af44-118">Fournir une expérience administrative dans le panneau de configuration Lync Server et éliminer l’outil d’administration de conversation de groupe</span><span class="sxs-lookup"><span data-stu-id="5af44-118">Provide an administrative experience in Lync Server Control Panel, and eliminate the Group Chat Admin Tool</span></span>

  - <span data-ttu-id="5af44-119">Intégrer les paramètres de configuration du serveur de conversation permanente dans le générateur de topologie en supprimant l’outil de configuration de conversation de groupe</span><span class="sxs-lookup"><span data-stu-id="5af44-119">Integrate configuration settings for Persistent Chat Server into Topology Builder by eliminating the Group Chat Configuration tool</span></span>

  - <span data-ttu-id="5af44-120">Faciliter la migration et la mise à niveau à partir de versions précédentes du serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="5af44-120">Ease migration and upgrade from previous versions of Persistent Chat Server</span></span>

  - <span data-ttu-id="5af44-121">Fournir des solutions de haute disponibilité et de récupération d’urgence</span><span class="sxs-lookup"><span data-stu-id="5af44-121">Provide high availability and disaster recovery solutions</span></span>

<span data-ttu-id="5af44-122">Pour plus d’informations sur la dernière version du serveur de conversation permanente, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="5af44-122">For additional details about the latest version of Persistent Chat Server, see the following:</span></span>

  - <span data-ttu-id="5af44-123">Aide de la conversation permanente, à partir <https://go.microsoft.com/fwlink/p/?linkid=270945> de laquelle fournit une liste détaillée des fonctionnalités de conversation permanente, de leur fonctionnement et de leur utilisation lors de l’exécution du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5af44-123">The Persistent Chat Help at <https://go.microsoft.com/fwlink/p/?linkid=270945> which provides a detailed list of Persistent Chat features, how they work, and how to use them while running Persistent Chat Server.</span></span>

  - <span data-ttu-id="5af44-124">[Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification, [Deploying persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) dans la documentation de déploiement, [migration de Lync Server 2010, Group chat ou Office Communications Server 2007 R2 Group chat to Lync Server 2013, persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) dans la documentation de migration et [Managing Lync Server 2013, persistent Server](managing-lync-server-2013-persistent-chat-server.md) dans la documentation des opérations, qui fournissent toutes des instructions sur la configuration du serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5af44-124">The [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation, [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in the Migration documentation, and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) in the Operations documentation, all of which provide instructions for setting up Persistent Chat Server.</span></span>

  - <span data-ttu-id="5af44-125">Le fichier de Documentation.msi du serveur de conversation permanente (fichier Windows Installer) permet aux utilisateurs d’accéder à une documentation hors connexion complète sur le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5af44-125">The Persistent Chat Server Documentation.msi file (Windows Installer file) lets users access comprehensive offline documentation about Persistent Chat Server.</span></span>

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a><span data-ttu-id="5af44-126">Modifications de la topologie de clés pour le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="5af44-126">Key Topology Changes for Persistent Chat Server</span></span>

<span data-ttu-id="5af44-127">Voici les principales modifications apportées au serveur de conversation permanente :</span><span class="sxs-lookup"><span data-stu-id="5af44-127">The following high-level changes for Persistent Chat Server include:</span></span>

<span data-ttu-id="5af44-128">Le serveur de conversation permanente est maintenant un rôle de serveur.</span><span class="sxs-lookup"><span data-stu-id="5af44-128">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="5af44-129">Dans Microsoft Lync Server 2010, le serveur de conversation de groupe était une application tierce de confiance pour Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5af44-129">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="5af44-130">La conversation permanente peut être ajoutée à votre topologie Lync Server 2013 à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="5af44-130">Persistent Chat can be added to your Lync Server 2013 topology by using Topology Builder.</span></span> <span data-ttu-id="5af44-131">Dans Lync Server 2013, la fonctionnalité de serveur de conversation permanente est implémentée à l’aide de trois nouveaux rôles serveur :</span><span class="sxs-lookup"><span data-stu-id="5af44-131">In Lync Server 2013, Persistent Chat Server functionality is implemented by using three new server roles:</span></span>

  - <span data-ttu-id="5af44-132">**PersistentChatService :** Il s’agit du rôle frontal pour la conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5af44-132">**PersistentChatService:** This is the front end role for Persistent Chat.</span></span> <span data-ttu-id="5af44-133">Dans les déploiements Standard Edition, le rôle de service serveur de conversation permanente est colocalisé sur le serveur Standard Edition déployé par le programme d’amorçage, comme n’importe quel autre rôle Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5af44-133">In Standard Edition deployments, Persistent Chat Server Service Role is collocated on the Standard Edition server deployed by Bootstrapper, like any other Lync Server role.</span></span> <span data-ttu-id="5af44-134">Dans les déploiements Enterprise Edition, le rôle service de conversation permanente est déployé sur des ordinateurs autonomes par le programme d’amorçage, comme n’importe quel autre rôle Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5af44-134">In Enterprise Edition deployments, Persistent Chat Service Role is deployed on stand-alone computers by Bootstrapper, like any other Lync Server role.</span></span>

  - <span data-ttu-id="5af44-135">**PersistentChatStore :** Serveur principal qui correspond à la base de données de contenu de conversation permanente, dans laquelle tout le contenu de conversation est stocké.</span><span class="sxs-lookup"><span data-stu-id="5af44-135">**PersistentChatStore:** Back End Server that corresponds to the Persistent Chat content database, where all the chat content is stored.</span></span>

  - <span data-ttu-id="5af44-136">**PersistentChatComplianceStore :** Rôle de serveur principal qui correspond à la base de données de conformité de conversation permanente, dans laquelle tous les événements de conformité sont stockés.</span><span class="sxs-lookup"><span data-stu-id="5af44-136">**PersistentChatComplianceStore:** Back End Server role that corresponds to the Persistent Chat Compliance database, where all compliance events are stored.</span></span>

<span data-ttu-id="5af44-137">Ces rôles de serveur de conversation permanente sont facultatifs et installés uniquement par les clients qui souhaitent bénéficier d’une fonctionnalité de serveur de conversation permanente complète.</span><span class="sxs-lookup"><span data-stu-id="5af44-137">These Persistent Chat Server roles are optional, and are installed only by customers who want comprehensive Persistent Chat Server functionality.</span></span> <span data-ttu-id="5af44-138">Le rôle **PersistentChatComplianceStore** est uniquement nécessaire si vous choisissez de déployer la conformité de la conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5af44-138">The **PersistentChatComplianceStore** role is needed only if you choose to deploy Persistent Chat Compliance.</span></span>

<span data-ttu-id="5af44-139">Le rôle **PersistentChatService** exécute deux services :</span><span class="sxs-lookup"><span data-stu-id="5af44-139">The **PersistentChatService** role runs two services:</span></span>

  - <span data-ttu-id="5af44-140">Service de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="5af44-140">Persistent Chat service</span></span>

  - <span data-ttu-id="5af44-141">Service de conformité de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="5af44-141">Persistent Chat Compliance service</span></span>

<span data-ttu-id="5af44-142">L’exécution de ces services sur chaque serveur de conversation permanente offre une haute disponibilité pour ces services dans un pool de serveurs de conversation permanente multiserveur.</span><span class="sxs-lookup"><span data-stu-id="5af44-142">Having these services run on each Persistent Chat Server provides high availability for these services in a multiserver Persistent Chat Server pool.</span></span>

<span data-ttu-id="5af44-143">De plus, pour prendre en charge le téléchargement de fichiers et le téléchargement dans les salles de conversation permanente, le serveur de conversation permanente inclut un service Web.</span><span class="sxs-lookup"><span data-stu-id="5af44-143">Additionally, to support the file upload and download in Persistent Chat rooms, Persistent Chat Server includes a web service.</span></span> <span data-ttu-id="5af44-144">Auparavant, ce service était colocalisé sur le serveur de conversation permanente, le serveur frontal et les services IIS (Internet Information Services) requis à installer.</span><span class="sxs-lookup"><span data-stu-id="5af44-144">Previously, this service was collocated on the Persistent Chat Server, Front End Server and required Internet Information Services (IIS) to be installed as a prerequisite.</span></span> <span data-ttu-id="5af44-145">Dans le serveur de conversation permanente Lync Server 2013, le service de téléchargement/téléchargement de fichiers est colocalisé avec le serveur frontal Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5af44-145">In Lync Server 2013 Persistent Chat Server, the File Upload/Download web service is collocated with the Lync Server 2013 Front End Server.</span></span> <span data-ttu-id="5af44-146">En tant qu’effet secondaire, les services Internet (IIS) ne sont plus requis pour le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5af44-146">As a side effect, Internet Information Services (IIS) is no longer a prerequisite for Persistent Chat Server.</span></span> <span data-ttu-id="5af44-147">Le service Web de téléchargement/téléchargement de fichier est identifié comme **PersistentChat** dans le gestionnaire des services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="5af44-147">The File Upload/Download web service is identified as **PersistentChat** in the Internet Information Services (IIS) Manager.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5af44-148">Le rôle <STRONG>PersistentChatService</STRONG> peut s’exécuter sur le même serveur qu’un serveur frontal Lync Server 2013 &nbsp; uniquement si ce dernier est un serveur frontal Standard Edition &nbsp; .</span><span class="sxs-lookup"><span data-stu-id="5af44-148">The <STRONG>PersistentChatService</STRONG> role can run on the same server as a Lync Server 2013&nbsp;Front End Server only if that Front End Server is a Standard Edition&nbsp;Front End Server.</span></span> <span data-ttu-id="5af44-149">Le rôle <STRONG>PersistentChatService</STRONG> ne peut pas s’exécuter indépendamment d’un &nbsp; serveur frontal Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5af44-149">The <STRONG>PersistentChatService</STRONG> role cannot run independently of a Lync Server 2013&nbsp;Front End Server.</span></span> <span data-ttu-id="5af44-150">Elle peut être installée uniquement dans le cadre d’un déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5af44-150">It can be installed only in the context of a Lync Server 2013 deployment.</span></span>



</div>

<span data-ttu-id="5af44-151">Dans le serveur de conversation permanente, le service de recherche a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="5af44-151">In Persistent Chat Server, Lookup service has been eliminated.</span></span> <span data-ttu-id="5af44-152">Dans Lync Server 2010, Group chat, le service de recherche s’est exécuté sur chaque serveur frontal de serveur de conversation de groupe et a effectué le routage vers l’un des serveurs de canal.</span><span class="sxs-lookup"><span data-stu-id="5af44-152">In Lync Server 2010, Group Chat, the Lookup service ran on every Group Chat Server Front End Server, and performed routing to one of the Channel Servers.</span></span> <span data-ttu-id="5af44-153">Lync Server 2013 repose sur le routage à l’aide des objets contact, où chaque pool de serveur de conversation permanente est représenté par un objet contact qui est utilisé par les serveurs frontaux Lync Server pour identifier et acheminer les demandes vers un pool de serveurs de conversation permanente approprié, et vers l’un des ordinateurs exécutant le serveur de conversation permanente dans le pool.</span><span class="sxs-lookup"><span data-stu-id="5af44-153">Lync Server 2013 relies on routing by using contact objects, where each Persistent Chat Server pool is represented by a contact object that is used by the Lync Server Front End Servers to identify and route requests to an appropriate Persistent Chat Server pool, and to one of the computers running Persistent Chat Server in the pool.</span></span>

<span data-ttu-id="5af44-154">Dans Lync Server 2013, il existe des modifications de service de conformité :</span><span class="sxs-lookup"><span data-stu-id="5af44-154">In Lync Server 2013, there are Compliance service modifications:</span></span>

  - <span data-ttu-id="5af44-155">Dans Lync Server 2010, le service de conformité s’est exécuté en mode autonome (non colocalisé) et uniquement sur un seul serveur.</span><span class="sxs-lookup"><span data-stu-id="5af44-155">In Lync Server 2010, the Compliance service ran stand-alone (non-collocated), and only on a single server.</span></span> <span data-ttu-id="5af44-156">Le service de conformité s’exécute désormais sur tous les serveurs frontaux de serveur de conversation permanente, ainsi que le service de conversation permanente, et fournit ainsi une haute disponibilité dans un pool de serveurs de conversation permanente multiserveur.</span><span class="sxs-lookup"><span data-stu-id="5af44-156">The Compliance service now runs on all the Persistent Chat Server Front End Servers, alongside the Persistent Chat service, and thereby provides high availability in a multiserver Persistent Chat Server pool.</span></span> <span data-ttu-id="5af44-157">Un adaptateur de conformité unique peut être configuré pour extraire les données de la base de données de conformité et de l’un des autres systèmes (fichier XML, Archives hébergées par Exchange, etc.).</span><span class="sxs-lookup"><span data-stu-id="5af44-157">A single compliance adapter can be configured to extract data from the compliance database and into one of the other systems (XML file, Exchange-hosted archives, and so on).</span></span> <span data-ttu-id="5af44-158">Le serveur de conversation permanente inclut un adaptateur XML.</span><span class="sxs-lookup"><span data-stu-id="5af44-158">Persistent Chat Server includes an XML adapter.</span></span>

  - <span data-ttu-id="5af44-159">La file d’attente Message Queuing (également appelée MSMQ) qui est partagée par le service de conversation permanente et le service de conformité sur chaque serveur frontal de serveur de conversation permanente est désormais une file d’attente privée partagée uniquement par les deux services.</span><span class="sxs-lookup"><span data-stu-id="5af44-159">The Message Queuing (also known as MSMQ) queue that is shared by the Persistent Chat service and the Compliance service on each Persistent Chat Server Front End Server is now a private queue shared only by the two services.</span></span> <span data-ttu-id="5af44-160">Tous les services de conformité écrivent dans la même base de données principale de conformité.</span><span class="sxs-lookup"><span data-stu-id="5af44-160">All compliance services write to the same Compliance Back End database.</span></span> <span data-ttu-id="5af44-161">Ils sont également lus à partir de cette base de données, afin d’envoyer les données à leur instance de l’adaptateur.</span><span class="sxs-lookup"><span data-stu-id="5af44-161">They also all read from that database, for the purpose of sending the data to their instance of the adapter.</span></span> <span data-ttu-id="5af44-162">Le serveur principal de conformité est représenté sous la forme d’un nouveau rôle de serveur principal.</span><span class="sxs-lookup"><span data-stu-id="5af44-162">The Compliance Back End Server is represented as a new Back End Server role.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5af44-163">Comme dans les versions précédentes, toutes les données de conformité ne sont traitées qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="5af44-163">As in previous versions, all compliance data is processed only once.</span></span> <span data-ttu-id="5af44-164">Les données peuvent être traitées par n’importe quelle instance d’adaptateur appelée par le service de conformité exécuté sur les différents serveurs Lync Server 2013, persistent chat.</span><span class="sxs-lookup"><span data-stu-id="5af44-164">The data may be processed by any of the adapter instances invoked by the compliance service running on the various Lync Server 2013, Persistent Chat Server computers.</span></span> <span data-ttu-id="5af44-165">Dans le cas d’un serveur de conversation permanente, l’une des instances de carte peut traiter les données.</span><span class="sxs-lookup"><span data-stu-id="5af44-165">In Persistent Chat Server, any one of the adapter instances could process the data.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5af44-166">Pour plus d’informations sur l’installation de Message Queuing, voir <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">installer des systèmes d’exploitation et des logiciels prérequis sur les serveurs pour Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="5af44-166">For information about installing Message Queuing, see <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Install operating systems and prerequisite software on servers for Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="5af44-167">Dans Lync Server 2013, il existe des améliorations en matière de haute disponibilité et de récupération d’urgence :</span><span class="sxs-lookup"><span data-stu-id="5af44-167">In Lync Server 2013, there are improvements in both high availability and disaster recovery:</span></span>

  - <span data-ttu-id="5af44-168">Améliorations de la haute disponibilité : la mise en miroir SQL Server est utilisée pour fournir une haute disponibilité pour la base de données de contenu du serveur de conversation permanente et la base de données de conformité de conversation permanente dans un centre de données (sur site).</span><span class="sxs-lookup"><span data-stu-id="5af44-168">High availability improvements: SQL Server mirroring is used to provide high availability for the Persistent Chat Server content database and Persistent Chat compliance database within a data center (in-site).</span></span>

  - <span data-ttu-id="5af44-169">Améliorations de la récupération d’urgence : le serveur de conversation permanente prend en charge une architecture de pool étirée qui permet à un seul pool de serveurs de conversation permanente d’être étiré entre deux sites (c’est-à-dire un pool logique unique dans la topologie, avec des serveurs du pool physiquement situés sur deux sites).</span><span class="sxs-lookup"><span data-stu-id="5af44-169">Disaster recovery improvements: Persistent Chat Server supports a stretched pool architecture that enables a single Persistent Chat Server pool to be stretched across two sites (that is, a single logical pool in the topology, with servers in the pool physically located across two sites).</span></span> <span data-ttu-id="5af44-170">La copie des journaux de transaction SQL Server est utilisée pour la récupération d’urgence intersite.</span><span class="sxs-lookup"><span data-stu-id="5af44-170">SQL Server Log Shipping is used for cross-site disaster recovery.</span></span>

<span data-ttu-id="5af44-171">Pour plus d’informations sur la haute disponibilité et la récupération d’urgence, reportez-vous à la rubrique [configuration du serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="5af44-171">For more information about high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a><span data-ttu-id="5af44-172">Modifications de gestion et d’administration de clés pour le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="5af44-172">Key Administration and Management Changes for Persistent Chat Server</span></span>

<span data-ttu-id="5af44-173">Lync Server 2013 a facilité l’administration et la gestion du serveur de conversation permanente en fournissant les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="5af44-173">Lync Server 2013 has made it easier to administer and manage Persistent Chat Server by providing:</span></span>

  - <span data-ttu-id="5af44-174">Administration et gestion unifiées.</span><span class="sxs-lookup"><span data-stu-id="5af44-174">Unified administration and management.</span></span> <span data-ttu-id="5af44-175">Lync Server 2013 facilite la gestion et l’administration du serveur de conversation permanente à l’aide d’outils déjà familiers aux administrateurs Lync.</span><span class="sxs-lookup"><span data-stu-id="5af44-175">Lync Server 2013 makes it easier to manage and administer Persistent Chat Server by using tools that are already familiar to Lync administrators.</span></span> <span data-ttu-id="5af44-176">Le serveur de conversation permanente inclut une expérience d’interface utilisateur d’administration intégrée au panneau de configuration Lync Server, qui permet de résoudre les problèmes de performances liés aux versions précédentes de l’interface utilisateur du serveur de conversation de groupe.</span><span class="sxs-lookup"><span data-stu-id="5af44-176">Persistent Chat Server includes an administrative user interface experience that is integrated with the Lync Server Control Panel, which addresses performance issues with the previous versions of the Group Chat Server user interface.</span></span> <span data-ttu-id="5af44-177">De même, le serveur de conversation permanente inclut une collection d’applets de commande Windows PowerShell pour administrer et gérer les catégories de serveur de conversation permanente, les salles de serveur de conversation permanente (y compris la suppression de salles et le contenu obsolète) et les compléments.</span><span class="sxs-lookup"><span data-stu-id="5af44-177">Also, Persistent Chat Server includes a collection of Windows PowerShell cmdlets to administer and manage Persistent Chat Server categories, Persistent Chat Server rooms (including deleting rooms and purging obsolete content), and add-ins.</span></span>

  - <span data-ttu-id="5af44-178">Modèle d’administration simplifié.</span><span class="sxs-lookup"><span data-stu-id="5af44-178">Simplified administration model.</span></span> <span data-ttu-id="5af44-179">Lync Server 2013 a modifié et simplifié le modèle de serveur de conversation permanente en abordant les principaux besoins des clients :</span><span class="sxs-lookup"><span data-stu-id="5af44-179">Lync Server 2013 has changed and simplified the Persistent Chat Server model by addressing the following key customer requirements:</span></span>
    
      - <span data-ttu-id="5af44-180">Supprimez les hiérarchies imbriquées complexes des étendues et des catégories.</span><span class="sxs-lookup"><span data-stu-id="5af44-180">Remove the complex nested hierarchies of scopes and categories.</span></span>
    
      - <span data-ttu-id="5af44-181">Prise en charge pour définir des listes de refus, ainsi que des listes autorisées (étendues) pour les clients MindAlign actuels qui envisagent de migrer vers le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5af44-181">Support to define deny lists as well as allowed lists (scopes) for current MindAlign customers who are planning to migrate to Persistent Chat Server.</span></span>

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a><span data-ttu-id="5af44-182">Quelles sont les différences en ce qui concerne les rôles d’utilisateur des versions précédentes du serveur de conversation de groupe ?</span><span class="sxs-lookup"><span data-stu-id="5af44-182">What’s Different about User Roles from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="5af44-183">Lync Server 2010, Group chat disposait d’un rôle d’administrateur d’utilisateurs, d’un rôle d’administrateur de salle de conversation et d’un rôle d’administrateur Lync Server pouvant gérer les compléments. Le serveur de conversation permanente fournit simplement un rôle d’administrateur de conversation permanente (semblable aux autres rôles de contrôle d’accès basé sur un rôle de Lync Server).</span><span class="sxs-lookup"><span data-stu-id="5af44-183">Lync Server 2010, Group Chat had a user administrator role, a chat room administrator role and a Lync Server administrator role that could manage add-ins. Persistent Chat Server simply provides a Persistent Chat Administrator role (which is similar to other Lync Server role-based access control (RBAC) roles).</span></span> <span data-ttu-id="5af44-184">Toute personne qui est membre de ce rôle RBAC peut gérer les salles de conversation, les compléments et les catégories (et ainsi obtenir l’accès des utilisateurs pour ces catégories), ainsi que la configuration du pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5af44-184">Anyone who is a member of this RBAC role can manage chat rooms, add-ins, and categories (and therefore gain user access for these categories), and configuration of the Persistent Chat Server pool.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a><span data-ttu-id="5af44-185">Différences par rapport aux catégories de salles de conversation des versions précédentes du serveur de conversation de groupe</span><span class="sxs-lookup"><span data-stu-id="5af44-185">What’s Different about Chat Room Categories from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="5af44-186">Les catégories de salle de conversation ne peuvent plus être imbriquées et la catégorie racine ne peut plus être modifiée.</span><span class="sxs-lookup"><span data-stu-id="5af44-186">Chat room categories can no longer be nested, and the root category can no longer be modified.</span></span> <span data-ttu-id="5af44-187">AllowedMembers/membres refusés comprend ce qu’est une étendue utilisée dans les versions des serveurs de conversation de groupe héritées (sauf qu’elle n’a pas pris en charge la spécification d’une liste refusée).</span><span class="sxs-lookup"><span data-stu-id="5af44-187">AllowedMembers/DeniedMembers comprise what a scope used to be in legacy Group Chat Server versions (except that it didn’t support specifying a Denied list).</span></span> <span data-ttu-id="5af44-188">Les étendues ne peuvent plus être remplacées, car il n’y a pas de catégories imbriquées.</span><span class="sxs-lookup"><span data-stu-id="5af44-188">Scopes can no longer be overridden, because there are no nested categories.</span></span> <span data-ttu-id="5af44-189">Un administrateur de conversation permanente dans Lync Server 2013 peut créer et gérer des catégories de salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="5af44-189">A Persistent Chat Administrator in Lync Server 2013 can create and manage chat room categories.</span></span> <span data-ttu-id="5af44-190">Dans le cadre de la création et de la gestion des catégories de salles de conversation, un administrateur de conversation permanente peut configurer des principaux (groupes Active Directory/conteneurs/utilisateurs) qui ont accès à des membres/créateurs de salles de conversation d’une catégorie particulière.</span><span class="sxs-lookup"><span data-stu-id="5af44-190">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="5af44-191">Un administrateur de conversation permanente peut également ajouter membres refusés à une catégorie, et ces exclusions deviennent des exclusions explicites de la liste autorisée.</span><span class="sxs-lookup"><span data-stu-id="5af44-191">A Persistent Chat Administrator can also add DeniedMembers to a category, and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="5af44-192">Membres refusés remplacer ce qui se trouve dans AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="5af44-192">DeniedMembers override what’s in AllowedMembers.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a><span data-ttu-id="5af44-193">Quelles sont les différences entre les propriétés de salle de conversation des versions précédentes du serveur de conversation de groupe ?</span><span class="sxs-lookup"><span data-stu-id="5af44-193">What’s Different about Chat Room Properties from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="5af44-194">Un nouveau concept de salles de conversation ouvertes existe dans Lync Server 2013, serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5af44-194">A new concept of open chat rooms exists in Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="5af44-195">Tous les membres autorisés peuvent rejoindre la salle de conversation, sans membre exclusif.</span><span class="sxs-lookup"><span data-stu-id="5af44-195">All allowed members can join the chat room, without exclusive membership.</span></span>

<span data-ttu-id="5af44-196">Les propriétés de salle de conversation suivantes qui ont été incluses dans les versions précédentes du serveur de conversation permanente ont été éliminées :</span><span class="sxs-lookup"><span data-stu-id="5af44-196">The following chat room properties that were included in previous versions of Persistent Chat Server have been eliminated:</span></span>

  - <span data-ttu-id="5af44-197">Rubrique : une salle dispose désormais uniquement d’une description.</span><span class="sxs-lookup"><span data-stu-id="5af44-197">Topic: A Room now only has a Description.</span></span>

  - <span data-ttu-id="5af44-198">Créer une liste de membres : dans le serveur de conversation permanente, toutes les salles de conversation commencent par une appartenance vide (et peuvent augmenter jusqu’à une appartenance égal aux membres autorisés).</span><span class="sxs-lookup"><span data-stu-id="5af44-198">Create New Member list: In Persistent Chat Server, all chat rooms start with empty membership (and can maximize to a membership equaling the Allowed Members).</span></span>

  - <span data-ttu-id="5af44-199">Chargement de fichiers : permet de définir un paramètre par salle de conversation afin de contrôler si les téléchargements de fichiers/téléchargements ont été autorisés.</span><span class="sxs-lookup"><span data-stu-id="5af44-199">File Upload: Used to be a setting per chat room to control whether file upload/downloads were allowed.</span></span> <span data-ttu-id="5af44-200">Il définit à présent uniquement le niveau de catégorie et s’applique à toutes les salles de cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="5af44-200">This is now set only the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="5af44-201">Historique de la conversation : permet de définir un paramètre par salle de conversation afin de contrôler si l’historique de conversation a été activé, mais qui n’est défini qu’au niveau de la catégorie et s’applique à toutes les salles de cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="5af44-201">Chat History: Used to be a setting per chat room to control if Chat History was enabled, but is now set only at the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="5af44-202">Invitations : une salle hérite toujours du paramètre des invitations pour la catégorie ; ou elle peut être désactivée sur la salle.</span><span class="sxs-lookup"><span data-stu-id="5af44-202">Invites: A room always inherits the Invites setting for the category; or it can be turned off on the room.</span></span> <span data-ttu-id="5af44-203">Une salle ne peut pas activer les invitations si la catégorie a été définie précédemment sur invitations.</span><span class="sxs-lookup"><span data-stu-id="5af44-203">A room cannot turn on Invites if the category was previously set to Invites off.</span></span>

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a><span data-ttu-id="5af44-204">Quelles sont les différences par rapport aux stratégies des versions précédentes du serveur de conversation de groupe ?</span><span class="sxs-lookup"><span data-stu-id="5af44-204">What’s Different about Policies from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="5af44-205">Le serveur de conversation permanente a une nouvelle stratégie Lync activée avec la conversation permanente, par utilisateur/pool/site/paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="5af44-205">Persistent Chat Server has a new Lync policy enabled with Persistent Chat, per user/pool/site/global settings.</span></span> <span data-ttu-id="5af44-206">Dans le client Lync 2013, l’environnement de conversation permanente est disponible uniquement pour les utilisateurs qui sont activés par la stratégie pour la conversation permanente (directement ou par le biais du paramètre pool/site/global).</span><span class="sxs-lookup"><span data-stu-id="5af44-206">In the Lync 2013 client, the Persistent Chat environment is available only for users who are enabled by policy for Persistent Chat (either directly or through the pool/site/global setting).</span></span>

<span data-ttu-id="5af44-207">Les versions précédentes du serveur de conversation de groupe n’ont pas de stratégies intégrées dans les stratégies Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5af44-207">Previous versions of Group Chat Server did not have any policies integrated into the Lync Server policies.</span></span> <span data-ttu-id="5af44-208">Pour chaque utilisateur et par catégorie/salle, à l’aide de la fonctionnalité de **téléchargement de fichiers** par utilisateur, vous pouvez faire de l’utilisateur un administrateur d’utilisateur, un administrateur de salle de conversation ou configurer la capacité de téléchargement des fichiers par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5af44-208">On a per user and per category/room basis, by using the **Can Upload Files** per user feature, you could make the user a User administrator, a chat room administrator, or configure the user’s ability to upload files.</span></span> <span data-ttu-id="5af44-209">La fonctionnalité de **téléchargement de fichiers** du serveur de conversation permanente est une seule par catégorie.</span><span class="sxs-lookup"><span data-stu-id="5af44-209">The Persistent Chat Server **File Upload** feature is just per category.</span></span>

</div>

<div>

## <a name="logging"></a><span data-ttu-id="5af44-210">Logging</span><span class="sxs-lookup"><span data-stu-id="5af44-210">Logging</span></span>

<span data-ttu-id="5af44-211">La journalisation du serveur de conversation permanente et de System Center Operations Manager est intégrée à la journalisation du suivi de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5af44-211">Logging for Persistent Chat Server and System Center Operations Manager is integrated into the Lync Server 2013 trace logging.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5af44-212">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5af44-212">See Also</span></span>


[<span data-ttu-id="5af44-213">Planification du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5af44-213">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
