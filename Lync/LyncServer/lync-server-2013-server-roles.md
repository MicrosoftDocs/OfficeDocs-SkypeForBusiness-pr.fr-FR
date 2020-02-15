---
title: Rôles serveur Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 093161cec5a13ac12840776dec731773782966c9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a><span data-ttu-id="aeb1a-102">Rôles serveur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb1a-102">Server roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aeb1a-103">_**Dernière modification de la rubrique :** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="aeb1a-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="aeb1a-104">Chaque serveur exécutant Lync Server exécute un ou plusieurs *rôles serveur*.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-104">Each server running Lync Server runs one or more *server roles*.</span></span> <span data-ttu-id="aeb1a-105">Un rôle serveur est un ensemble défini de fonctionnalités Lync Server fournies par ce serveur.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-105">A server role is a defined set of Lync Server functionalities provided by that server.</span></span> <span data-ttu-id="aeb1a-106">Il n’est pas nécessaire de déployer tous les rôles serveur disponibles dans votre réseau.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-106">You do not need to deploy all available server roles in your network.</span></span> <span data-ttu-id="aeb1a-107">Installez seulement ceux qui contiennent la fonctionnalité voulue.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-107">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="aeb1a-108">Même si vous n’êtes pas familiarisé avec les rôles serveur dans Lync Server, l’outil de planification peut vous aider à obtenir la meilleure solution pour les serveurs que vous devez déployer, en fonction des fonctionnalités que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-108">Even if you are not familiar with server roles in Lync Server, the Planning Tool can guide you to the best solution for the servers that you need to deploy, based on the features that you want.</span></span> <span data-ttu-id="aeb1a-109">Cette section propose une brève vue d’ensemble des rôles serveur et des fonctionnalités générales qu’ils fournissent :</span><span class="sxs-lookup"><span data-stu-id="aeb1a-109">This section provides a brief overview of the server roles and the general features that they provide:</span></span>

  - <span data-ttu-id="aeb1a-110">Serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="aeb1a-110">Standard Edition Server</span></span>

  - <span data-ttu-id="aeb1a-111">Serveur frontal et serveur principal</span><span class="sxs-lookup"><span data-stu-id="aeb1a-111">Front End Server and Back End Server</span></span>

  - <span data-ttu-id="aeb1a-112">Serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aeb1a-112">Edge Server</span></span>

  - <span data-ttu-id="aeb1a-113">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="aeb1a-113">Mediation Server</span></span>

  - <span data-ttu-id="aeb1a-114">48000b</span><span class="sxs-lookup"><span data-stu-id="aeb1a-114">Director</span></span>

  - <span data-ttu-id="aeb1a-115">Serveur frontal de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="aeb1a-115">Persistent Chat Front End Server</span></span>

  - <span data-ttu-id="aeb1a-116">Magasin de conversation permanente (serveur principal de conversation permanente)</span><span class="sxs-lookup"><span data-stu-id="aeb1a-116">Persistent Chat Store (Persistent Chat Back End Server)</span></span>

  - <span data-ttu-id="aeb1a-117">Magasin de conformité de conversation permanente (serveur principal de conformité de conversation permanente)</span><span class="sxs-lookup"><span data-stu-id="aeb1a-117">Persistent Chat Compliance Store (Persistent Chat Compliance Back End Server)</span></span>

<span data-ttu-id="aeb1a-118">Pour la plupart des rôles serveur, pour l’extensibilité et la haute disponibilité, vous pouvez déployer des *pools* de plusieurs serveurs exécutant tous le même rôle serveur.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-118">For most server roles, for scalability and high availability you can deploy *pools* of multiple servers all running the same server role.</span></span> <span data-ttu-id="aeb1a-119">Chaque serveur d’un pool doit exécuter un ou plusieurs rôles serveur identiques.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-119">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="aeb1a-120">Pour la plupart des types de pools dans Lync Server, vous devez déployer un équilibreur de charge pour répartir le trafic entre les différents serveurs du pool.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-120">For most types of pools in Lync Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="aeb1a-121">Lync Server prend en charge l’équilibrage de charge DNS (Domain Name System) et les programmes d’équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-121">Lync Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

<div>

## <a name="standard-edition-server"></a><span data-ttu-id="aeb1a-122">Serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="aeb1a-122">Standard Edition Server</span></span>

<span data-ttu-id="aeb1a-123">Le serveur Standard Edition est conçu pour les petites organisations et pour les projets pilotes de grandes organisations.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-123">The Standard Edition server is designed for small organizations, and for pilot projects of large organizations.</span></span> <span data-ttu-id="aeb1a-124">Il permet à de nombreuses fonctionnalités de Lync Server, y compris les bases de données nécessaires, de s’exécuter sur un seul serveur.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-124">It enables many of the features of Lync Server, including the necessary databases, to run on a single server.</span></span> <span data-ttu-id="aeb1a-125">Cela vous permet de disposer des fonctionnalités de Lync Server pour un coût réduit, mais ne fournit pas une véritable solution de haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-125">This enables you to have Lync Server functionality for a lower cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="aeb1a-126">Standard Edition Server vous permet d’utiliser la messagerie instantanée, la présence, les conférences et voix entreprise, qui s’exécutent toutes sur un serveur.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-126">Standard Edition server enables you to use instant messaging (IM), presence, conferencing, and Enterprise Voice, all running on one server.</span></span>

<span data-ttu-id="aeb1a-127">Pour une solution à haute disponibilité, utilisez Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-127">For a high-availability solution, use Lync Server Enterprise Edition.</span></span>

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="aeb1a-128">Serveur frontal et serveur principal</span><span class="sxs-lookup"><span data-stu-id="aeb1a-128">Front End Server and Back End Server</span></span>

<span data-ttu-id="aeb1a-129">Dans Lync Server Enterprise Edition, le serveur frontal est le rôle serveur principal et exécute de nombreuses fonctions Lync Server de base.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-129">In Lync Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Lync Server functions.</span></span> <span data-ttu-id="aeb1a-130">Le serveur frontal, ainsi que les serveurs principaux, sont les seuls rôles de serveur requis dans n’importe quel déploiement Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-130">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Lync Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="aeb1a-p106">Un *pool frontal* est un ensemble de serveurs frontaux, configurés à l’identique, qui fonctionnent de pair pour proposer des services à un groupe commun d’utilisateurs. Un pool de plusieurs serveurs exécutant le même rôle fournit l’extensibilité et la fonction de basculement.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-p106">A *Front End pool* is a set of Front End Servers, configured identically, that work together to provide services for a common group of users. A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="aeb1a-133">Le serveur frontal inclut les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="aeb1a-133">The Front End Server includes the following:</span></span>

  - <span data-ttu-id="aeb1a-134">Enregistrement et authentification des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="aeb1a-134">User authentication and registration</span></span>

  - <span data-ttu-id="aeb1a-135">Informations de présence et échange de cartes de visite</span><span class="sxs-lookup"><span data-stu-id="aeb1a-135">Presence information and contact card exchange</span></span>

  - <span data-ttu-id="aeb1a-136">Services de carnet d’adresses et développement de listes de distribution</span><span class="sxs-lookup"><span data-stu-id="aeb1a-136">Address book services and distribution list expansion</span></span>

  - <span data-ttu-id="aeb1a-137">Fonctionnalités de messagerie instantanée, y compris les conférences de messagerie instantanée à plusieurs</span><span class="sxs-lookup"><span data-stu-id="aeb1a-137">IM functionality, including multiparty IM conferences</span></span>

  - <span data-ttu-id="aeb1a-138">Conférence web, conférence rendez-vous PSTN et conférence A/V (si déployée)</span><span class="sxs-lookup"><span data-stu-id="aeb1a-138">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed)</span></span>

  - <span data-ttu-id="aeb1a-139">Hébergement d’applications, pour les deux applications incluses dans Lync Server (par exemple, application de service de conférence et de groupe de réponse) et applications tierces</span><span class="sxs-lookup"><span data-stu-id="aeb1a-139">Application hosting, for both applications included with Lync Server (for example, Conferencing Attendant and Response Group application), and third-party applications</span></span>

  - <span data-ttu-id="aeb1a-140">Surveillance éventuelle permettant de collecter des informations d’utilisation sous forme d’enregistrements des détails des appels et d’enregistrements des erreurs des appels (CER).</span><span class="sxs-lookup"><span data-stu-id="aeb1a-140">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="aeb1a-141">Ces informations fournissent des mesures sur la qualité des médias (audio et vidéo) qui traversent votre réseau pour les appels voix entreprise et les conférences A/V.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-141">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

  - <span data-ttu-id="aeb1a-142">Composants web pour des tâches web prises en charge tels que le planificateur web et le lanceur de participation.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-142">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

  - <span data-ttu-id="aeb1a-143">Archivage éventuel permettant d’archiver les communications de messagerie instantanée et le contenu des réunions pour des raisons de conformité.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-143">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="aeb1a-144">Pour plus d’informations, reportez-vous à la rubrique [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-144">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>
    
    <span data-ttu-id="aeb1a-145">Dans Lync Server 2010 et les versions antérieures, la surveillance et l’archivage étaient des rôles serveur distincts, non colocalisés sur un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-145">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

  - <span data-ttu-id="aeb1a-146">Services web de conversation permanente, si cette dernière est activée, pour la gestion des salles de conversation et le téléchargement de fichiers.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-146">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="aeb1a-p109">Les pools frontaux sont également le magasin principal pour les données utilisateur et de conférence. Des informations sur chaque utilisateur sont répliquées sur trois serveurs frontaux dans le pool, puis sauvegardées sur les serveurs principaux.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-p109">Front End Pools are also the primary store for user and conference data. Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="aeb1a-149">De plus, un pool frontal dans le déploiement exécute également le *serveur de gestion centralisée*, qui gère et déploie les données de configuration de base sur tous les serveurs exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-149">Additionally, one Front End pool in the deployment also runs the *Central Management Server*, which manages and deploys basic configuration data to all servers running Lync Server.</span></span> <span data-ttu-id="aeb1a-150">Le serveur de gestion centralisée fournit également Lync Server Management Shell et les fonctionnalités de transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-150">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="aeb1a-151">Les serveurs principaux sont des serveurs de base de données exécutant Microsoft SQL Server qui fournissent les services de base de données pour le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-151">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="aeb1a-152">Les serveurs principaux servent de magasins de sauvegarde pour les données utilisateur et de conférence du pool, et sont les magasins principaux pour d’autres bases de données telles que la base de données de groupes Response Group.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-152">The Back End Servers serve as backup stores for the pool’s user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="aeb1a-153">Vous pouvez avoir un seul serveur principal, mais une solution qui utilise la mise en miroir SQL Server est recommandée pour le basculement.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-153">You can have a single Back End Server, but a solution that uses SQL Server mirroring is recommended for failover.</span></span> <span data-ttu-id="aeb1a-154">Les serveurs principaux n’exécutent aucun logiciel Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-154">Back End Servers do not run any Lync Server software.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aeb1a-155">Nous ne recommandons pas les bases de données colocaliser Lync Server avec d’autres bases de données.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-155">We do not recommend collocating Lync Server databases with other databases.</span></span> <span data-ttu-id="aeb1a-156">Dans ce cas, la disponibilité et les performances risquent en effet d’être affectées.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-156">If you do so, availability and performance may be affected.</span></span>



</div>

<span data-ttu-id="aeb1a-157">Parmi les informations stockées dans les bases de données du serveur principal se trouvent les informations de présence, les listes de contacts des utilisateurs, les données de conférence, notamment les données persistantes relatives à l’état des conférences actuelles, et les données de planification de conférence.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-157">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="aeb1a-158">Serveur Edge</span><span class="sxs-lookup"><span data-stu-id="aeb1a-158">Edge Server</span></span>

<span data-ttu-id="aeb1a-159">Le serveur Edge permet à vos utilisateurs de communiquer et de collaborer avec des utilisateurs à l’extérieur des pare-feu de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-159">Edge Server enables your users to communicate and collaborate with users outside the organization’s firewalls.</span></span> <span data-ttu-id="aeb1a-160">Ces utilisateurs externes peuvent inclure les utilisateurs de l’organisation qui travaillent actuellement hors site, les utilisateurs des organisations de partenaires fédérés et les utilisateurs externes qui ont été invités à participer à des conférences hébergées sur votre déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-160">These external users can include the organization’s own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Lync Server deployment.</span></span> <span data-ttu-id="aeb1a-161">Le serveur Edge permet également la connectivité aux services de connectivité de messagerie instantanée publique, y compris\!Windows Live, AOL, Yahoo et Google Talk.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-161">Edge Server also enables connectivity to public IM connectivity services, including Windows Live, AOL, Yahoo\!, and Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="aeb1a-162">À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="aeb1a-163">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="aeb1a-164">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-164">Messenger until the service shut down date.</span></span> <span data-ttu-id="aeb1a-165">Date de fin du 2014 juin pour AOL et Yahoo !</span><span class="sxs-lookup"><span data-stu-id="aeb1a-165">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="aeb1a-166">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-166">has been announced.</span></span> <span data-ttu-id="aeb1a-167">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-167">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="aeb1a-168">La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="aeb1a-168">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="aeb1a-169">Messenger.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-169">Messenger.</span></span> <span data-ttu-id="aeb1a-170">La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-170">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="aeb1a-171">Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-171">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="aeb1a-172">La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-172">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="aeb1a-173">La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-173">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="aeb1a-174">Le déploiement d’un serveur Edge active également des services de mobilité, lesquels permettent de prendre en charge des fonctionnalités Lync sur des appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-174">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="aeb1a-175">Les utilisateurs peuvent employer les appareils mobiles Apple iOS, Android, Windows Phone ou Nokia pris en charge pour s’adonner à des activités telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-175">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="aeb1a-176">En outre, les appareils mobiles prennent en charge certaines fonctionnalités Voix Entreprise, telles que le clic pour participer à une conférence, l’appel via le bureau, le numéro unique, la messagerie vocale et les appels manqués.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-176">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="aeb1a-177">La fonctionnalité de mobilité prend également en charge les *notifications push* pour les appareils mobiles qui ne prennent pas en charge les applications qui s’exécutent en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-177">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="aeb1a-178">Une notification push est une notification qui est envoyée à un appareil mobile à propos d’un événement qui se produit pendant qu’une application mobile n’est pas active.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-178">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="aeb1a-179">Les serveurs Edge incluent également un proxy XMPP (Extensible Messaging and Presence Protocol) entièrement intégré, avec une passerelle XMPP incluse sur les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-179">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="aeb1a-180">Vous pouvez configurer ces composants XMPP pour permettre à vos utilisateurs Lync Server 2013 d’ajouter des contacts à partir de partenaires XMPP (tels que Google Talk) pour la messagerie instantanée et la présence.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-180">You can configure these XMPP components to enable your Lync Server 2013 users to add contacts from XMPP-based partners (such as Google Talk) for instant messaging and presence.</span></span>

<span data-ttu-id="aeb1a-181">Pour plus d’informations, reportez-vous à la rubrique [planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-181">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="aeb1a-182">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="aeb1a-182">Mediation Server</span></span>

<span data-ttu-id="aeb1a-183">Le serveur de médiation est un composant nécessaire pour la mise en œuvre de voix entreprise et de conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-183">Mediation Server is a necessary component for implementing Enterprise Voice and dial-in conferencing.</span></span> <span data-ttu-id="aeb1a-184">Le serveur de médiation traduit la signalisation et, dans certaines configurations, les médias entre votre infrastructure Lync Server interne et une passerelle RTC (Public Switched Telephone Network), un système IP-PBX ou une jonction SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="aeb1a-184">Mediation Server translates signaling, and, in some configurations, media between your internal Lync Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="aeb1a-185">Vous pouvez exécuter le serveur de médiation s’il est colocalisé sur le même serveur que le serveur frontal ou s’il est séparé dans un pool de serveurs de médiation autonome.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-185">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="aeb1a-186">Pour plus d’informations, reportez-vous à [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-186">For details, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="aeb1a-187">48000b</span><span class="sxs-lookup"><span data-stu-id="aeb1a-187">Director</span></span>

<span data-ttu-id="aeb1a-188">Les directeurs peuvent authentifier les demandes des utilisateurs de Lync Server, mais ils ne disposent pas de comptes d’utilisateurs personnels ou fournissent des services de présence ou de conférence.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-188">Directors can authenticate Lync Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="aeb1a-189">Les directeurs sont très utiles pour renforcer la sécurité dans les déploiements qui permettent l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-189">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="aeb1a-190">Le directeur peut authentifier les demandes avant de les envoyer aux serveurs internes.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-190">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="aeb1a-191">En cas d’attaque par déni de service, celle-ci s’arrête au niveau du directeur sans atteindre les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-191">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span> <span data-ttu-id="aeb1a-192">Pour plus d’informations, reportez-vous à [scénarios pour le directeur dans Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-192">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-roles"></a><span data-ttu-id="aeb1a-193">Rôles de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="aeb1a-193">Persistent Chat Server Roles</span></span>

<span data-ttu-id="aeb1a-p121">La conversation permanente permet aux utilisateurs de participer à des conversations thématiques à plusieurs qui persistent dans le temps. Le serveur frontal de conversation permanente exécute le service de conversation permanente. Le serveur principal de conversation permanente stocke les données d’historique de conversation, ainsi que des informations sur les catégories et les salles de conversation. Le serveur principal de conformité de conversation permanente peut stocker le contenu des conversations et les événements de conformité à des fins de conformité.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-p121">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time. The Persistent Chat Front End Server runs the persistent chat service. The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms. The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="aeb1a-198">Les serveurs exécutant Lync Server Standard Edition peuvent également exécuter la conversation permanente sur le même serveur.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-198">Servers running Lync Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="aeb1a-199">Vous ne pouvez pas colocaliser le serveur frontal de conversation permanente avec un serveur frontal Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="aeb1a-199">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="aeb1a-200">Pour plus d’informations, reportez-vous à la rubrique [Planning for persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="aeb1a-200">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aeb1a-201">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aeb1a-201">See Also</span></span>


[<span data-ttu-id="aeb1a-202">Composant de serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb1a-202">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  


[<span data-ttu-id="aeb1a-203">Planification de l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb1a-203">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
[<span data-ttu-id="aeb1a-204">Planification de l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb1a-204">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="aeb1a-205">Scénarios pour le directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb1a-205">Scenarios for the Director in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-the-director.md)  
[<span data-ttu-id="aeb1a-206">Planification du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb1a-206">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

