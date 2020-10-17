---
title: 'Lync Server 2013 : configuration des serveurs proxy inverses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 640d8e97cf8b7a31e11cb2dc8f1b1394e4b1aae3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521811"
---
# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a><span data-ttu-id="b0589-102">Configuration des serveurs proxy inverses pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0589-102">Setting up reverse proxy servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0589-103">_**Dernière modification de la rubrique :** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="b0589-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="b0589-104">Pour les déploiements de serveur Edge Microsoft Lync Server 2013, un proxy inverse HTTPs dans le réseau de périmètre est nécessaire pour que les clients externes accèdent aux services Web Lync Server 2013 (appelés *composants Web* dans Office Communications Server) sur le directeur et le pool d’accueil de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b0589-104">For Microsoft Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for external clients to access the Lync Server 2013 Web Services (called *Web Components* in Office Communications Server) on the Director and the user’s home pool.</span></span> <span data-ttu-id="b0589-105">Les fonctionnalités qui nécessitent un accès externe via un proxy inverse sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="b0589-105">Some of the features that require external access through a reverse proxy include the following:</span></span>

  - <span data-ttu-id="b0589-106">Permettre aux utilisateurs externes de télécharger le contenu de vos réunions</span><span class="sxs-lookup"><span data-stu-id="b0589-106">Enabling external users to download meeting content for your meetings.</span></span>

  - <span data-ttu-id="b0589-107">Permettre aux utilisateurs externes de développer des groupes de distribution</span><span class="sxs-lookup"><span data-stu-id="b0589-107">Enabling external users to expand distribution groups.</span></span>

  - <span data-ttu-id="b0589-108">Permettre aux utilisateurs distants de télécharger des fichiers du Service de carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="b0589-108">Enabling remote users to download files from the Address Book service.</span></span>

  - <span data-ttu-id="b0589-109">Accès au client Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="b0589-109">Accessing the Lync Web App client.</span></span>

  - <span data-ttu-id="b0589-110">Accès à la page web des paramètres de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="b0589-110">Accessing the Dial-in Conferencing Settings webpage.</span></span>

  - <span data-ttu-id="b0589-111">Permettre aux périphériques externes de se connecter au service web de mise à jour des périphériques et d’obtenir des mises à jour</span><span class="sxs-lookup"><span data-stu-id="b0589-111">Enabling external devices to connect to Device Update web service and obtain updates.</span></span>

  - <span data-ttu-id="b0589-112">Permettre aux applications mobiles de découvrir et d’utiliser automatiquement les URL de mobilité (MCX) à partir d’Internet.</span><span class="sxs-lookup"><span data-stu-id="b0589-112">Enabling mobile applications to automatically discover and use the mobility (Mcx) URLs from the Internet.</span></span>

  - <span data-ttu-id="b0589-113">Activation du client Lync 2013, de l’application Lync Windows Store et de Lync 2013 mobile client pour localiser les URL de découverte Lync (découverte automatique) et utiliser UCWA (Unified Communications Web API).</span><span class="sxs-lookup"><span data-stu-id="b0589-113">Enabling the Lync 2013 client, Lync Windows Store app and Lync 2013 Mobile client to locate the Lync Discover (autodiscover) URLs and use Unified Communications Web API (UCWA).</span></span>

<span data-ttu-id="b0589-114">Nous vous recommandons de configurer le proxy inverse HTTP de sorte qu’il publie tous les services web dans tous les pools.</span><span class="sxs-lookup"><span data-stu-id="b0589-114">We recommend that you configure your HTTP reverse proxy to publish all Web Services in all pools.</span></span> <span data-ttu-id="b0589-115">Publishing https://ExternalFQDN/ \* publie tous les répertoires virtuels IIS pour un pool.</span><span class="sxs-lookup"><span data-stu-id="b0589-115">Publishing https:// ExternalFQDN/\* publishes all IIS virtual directories for a pool.</span></span> <span data-ttu-id="b0589-116">Une règle de publication est nécessaire pour chaque serveur Standard Edition, pool frontal, directeur ou pool directeur dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b0589-116">You need one publishing rule for each Standard Edition server, Front End pool, or Director or Director pool in your organization.</span></span>

<span data-ttu-id="b0589-117">En outre, vous devez publier les URL simples.</span><span class="sxs-lookup"><span data-stu-id="b0589-117">In addition, you need to publish the simple URLs.</span></span> <span data-ttu-id="b0589-118">Si l’organisation dispose d’un directeur ou d’un pool directeur, le proxy inverse HTTP écoute les requêtes HTTP/HTTPS vers les URL simples et les redirige via proxy vers le répertoire virtuel externe des services web sur le directeur ou le pool directeur.</span><span class="sxs-lookup"><span data-stu-id="b0589-118">If the organization has a Director or Director pool, the HTTP reverse proxy listens for HTTP/HTTPS requests to the simple URLs and proxies them to the external Web Services virtual directory on the Director or Director pool.</span></span> <span data-ttu-id="b0589-119">Si vous n’avez pas déployé de directeur, vous devez désigner un pool pour traiter les requêtes transmises aux URL simples.</span><span class="sxs-lookup"><span data-stu-id="b0589-119">If you have not deployed a Director, you need to designate one pool to handle requests to the simple URLs.</span></span> <span data-ttu-id="b0589-120">(S’il ne s’agit pas du pool d’accueil de l’utilisateur, le proxy redirigera ces requêtes vers les services web sur le pool d’accueil de l’utilisateur).</span><span class="sxs-lookup"><span data-stu-id="b0589-120">(If this is not the user’s home pool, it will redirect them onward to the Web Services on the user’s home pool).</span></span> <span data-ttu-id="b0589-121">Les URL simples peuvent être traitées par une règle de publication web dédiée ou vous pouvez les ajouter aux noms publics de la règle de publication web pour le directeur.</span><span class="sxs-lookup"><span data-stu-id="b0589-121">The simple URLs can be handled by a dedicated web publishing rule, or you can add it to the public names of the web publishing rule for the Director.</span></span> <span data-ttu-id="b0589-122">Vous devez également publier l’URL du service de découverte automatique externe.</span><span class="sxs-lookup"><span data-stu-id="b0589-122">You also need to publish the external Autodiscover Service URL.</span></span>

<span data-ttu-id="b0589-123">Vous pouvez utiliser Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1 ou Internet Information Server 7,0, 7,5 ou 8,0 avec application Routing Routing (IIS ARR) en tant que proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="b0589-123">You can use Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, or Internet Information Server 7.0, 7.5 or 8.0 with Application Request Routing (IIS ARR) as a reverse proxy.</span></span> <span data-ttu-id="b0589-124">Les étapes détaillées de cette section décrivent comment configurer Forefront Threat Management Gateway 2010 et les étapes de configuration d’ISA Server 2006 sont presque identiques.</span><span class="sxs-lookup"><span data-stu-id="b0589-124">The detailed steps in this section describe how to configure Forefront Threat Management Gateway 2010, and the steps for configuring ISA Server 2006 are almost identical.</span></span> <span data-ttu-id="b0589-125">Des conseils sont également fournis pour IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="b0589-125">Guidance is also provided for IIS ARR.</span></span> <span data-ttu-id="b0589-126">Si vous utilisez un proxy inverse différent, consultez la documentation de ce produit et mappez les conditions requises définies ici aux fonctionnalités associées dans d’autres proxys inverses.</span><span class="sxs-lookup"><span data-stu-id="b0589-126">If you are using a different reverse proxy, consult the documentation for that product and map the requirements defined here to the associated features in other reverse proxies.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b0589-127">Internet Information Server application Request Routing (IIS ARR) est une option entièrement testée et prise en charge pour l’implémentation d’un proxy inverse pour Lync Server 2010 et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b0589-127">Internet Information Server Application Request Routing (IIS ARR) is a fully tested and supported option for implementing a reverse proxy for Lync Server 2010 and Lync Server 2013.</span></span> <span data-ttu-id="b0589-128">En novembre 2012, Microsoft a cessé les ventes de licences de ForeFront Threat Management Gateway 2010 ou TMG.</span><span class="sxs-lookup"><span data-stu-id="b0589-128">In November, 2012, Microsoft ceased license sales of ForeFront Threat Management Gateway 2010, or TMG.</span></span> <span data-ttu-id="b0589-129">TMG reste un produit entièrement pris en charge et est toujours disponible sur les appliances vendues par des tiers.</span><span class="sxs-lookup"><span data-stu-id="b0589-129">TMG is still a fully supported product, and is still available for sale on appliances sold by third parties.</span></span> <span data-ttu-id="b0589-130">De plus, de nombreux programmes d’équilibrage de la charge matérielle et pare-feu tiers fournissent la prise en charge du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="b0589-130">Also, many third party hardware load balancers and firewalls provide reverse proxy support.</span></span> <span data-ttu-id="b0589-131">Pour les programmes d’équilibrage de la charge matérielle et les pare-feu qui fournissent des fonctionnalités de proxy inverse, consultez votre fournisseur pour obtenir des instructions spécifiques sur la configuration de son produit afin de fournir une prise en charge de proxy inverse pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b0589-131">For hardware load balancers and firewalls that provide reverse proxy features, check with your vendor for specific instructions on how to configure their product to provide reverse proxy support for Lync Server.</span></span> <span data-ttu-id="b0589-132">Vous pouvez également afficher les tiers qui ont envoyé une documentation pour leur produit à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b0589-132">You can also view third parties that have submitted documentation for their product to Microsoft.</span></span> <span data-ttu-id="b0589-133">La prise en charge est fournie par le tiers pour leur solution.</span><span class="sxs-lookup"><span data-stu-id="b0589-133">Support is provided by the third party for their solution.</span></span> <span data-ttu-id="b0589-134">Pour voir les tiers qui sont actifs dans la fourniture de solutions, voir <A href="https://go.microsoft.com/fwlink/?linkid=268730">infrastructure Qualified for Microsoft Lync</A>.</span><span class="sxs-lookup"><span data-stu-id="b0589-134">To see third parties that are active in providing solutions, see <A href="https://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync</A>.</span></span>



</div>

<span data-ttu-id="b0589-135">Les rubriques et procédures suivantes utilisent Forefront Threat Management Gateway 2010 et IIS ARR comme base pour les procédures de déploiement et de configuration.</span><span class="sxs-lookup"><span data-stu-id="b0589-135">The following topics and procedures use Forefront Threat Management Gateway 2010 and IIS ARR as the basis for the deployment and configuration procedures.</span></span>

  - [<span data-ttu-id="b0589-136">Configurer les noms de domaine complets des batteries de serveurs Web pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0589-136">Configure web farm FQDNs for Lync Server 2013</span></span>](lync-server-2013-configure-web-farm-fqdns.md)

  - [<span data-ttu-id="b0589-137">Configurer les cartes réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0589-137">Configure network adapters in Lync Server 2013</span></span>](lync-server-2013-configure-network-adapters.md)

  - [<span data-ttu-id="b0589-138">Demander et configurer un certificat pour votre proxy HTTP inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0589-138">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [<span data-ttu-id="b0589-139">Configurer des règles de publication Web pour un pool interne unique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0589-139">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [<span data-ttu-id="b0589-140">Vérifier ou configurer l’authentification et la certification sur les répertoires virtuels IIS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0589-140">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [<span data-ttu-id="b0589-141">Créer des enregistrements DNS pour les serveurs proxy inverses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0589-141">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [<span data-ttu-id="b0589-142">Vérifier l’accès par le biais de votre proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0589-142">Verify access through your reverse proxy in Lync Server 2013</span></span>](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a><span data-ttu-id="b0589-143">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b0589-143">Before You Begin</span></span>

<span data-ttu-id="b0589-144">Pour déployer Forefront Threat Management Gateway 2010 en tant que proxy inverse, vous devez installer et configurer un serveur en vous conformant aux conditions préalables et à la configuration matérielle requise définies dans la documentation de Forefront Threat Management Gateway 2010.</span><span class="sxs-lookup"><span data-stu-id="b0589-144">To successfully deploy Forefront Threat Management Gateway 2010 as your reverse proxy, you need to setup and configure a server, using the prerequisites and hardware requirements defined in the Forefront Threat Management Gateway 2010 documentation.</span></span> <span data-ttu-id="b0589-145">Consultez la rubrique suivante pour configurer correctement le matériel et installer Forefront Threat Management Gateway 2010 sur le serveur avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="b0589-145">See the following topic set to properly configure the hardware and to install Forefront Threat Management Gateway 2010 on the server before proceeding.</span></span>

  - <span></span>  
    [<span data-ttu-id="b0589-146">Forefront Threat Management Gateway (TMG) 2010</span><span class="sxs-lookup"><span data-stu-id="b0589-146">Forefront Threat Management Gateway (TMG) 2010</span></span>](https://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [<span data-ttu-id="b0589-147">Recommandations matérielles sur Forefront TMG 2010</span><span class="sxs-lookup"><span data-stu-id="b0589-147">Forefront TMG 2010 hardware recommendations</span></span>](https://go.microsoft.com/fwlink/?linkid=291293)

<span data-ttu-id="b0589-148">Pour déployer IIS ARR comme serveur proxy inverse, consultez les rubriques suivantes pour configurer le matériel et les logiciels prérequis.</span><span class="sxs-lookup"><span data-stu-id="b0589-148">To successfully deploy IIS ARR as your reverse proxy, review the following topics to configure the hardware and the prerequisite software.</span></span>

  - <span></span>  
    <span data-ttu-id="b0589-149">Pour installer les services Internet (IIS) sur Windows Server 2008 ou Windows Server 2008 R2, consultez la rubrique [installation des services Internet (IIS) 7 sur Windows server 2008 ou Windows server 2008 R2](https://go.microsoft.com/fwlink/?linkid=291296) .</span><span class="sxs-lookup"><span data-stu-id="b0589-149">To install IIS on Windows Server 2008 or Windows Server 2008 R2, see [Installing IIS 7 on Windows Server 2008 or Windows Server 2008 R2](https://go.microsoft.com/fwlink/?linkid=291296)</span></span>

  - <span></span>  
    <span data-ttu-id="b0589-150">Pour installer les services Internet (IIS) sur Windows Server 2012, consultez la rubrique [installation des services Internet (IIS) 8 sur Windows server 2012](https://go.microsoft.com/fwlink/?linkid=291297)</span><span class="sxs-lookup"><span data-stu-id="b0589-150">To install IIS on Windows Server 2012, see [Installing IIS 8 on Windows Server 2012](https://go.microsoft.com/fwlink/?linkid=291297)</span></span>

  - <span></span>  
    <span data-ttu-id="b0589-151">Pour installer les services Internet (IIS) sur Windows Server 2012 R2, consultez la rubrique [installation des services Internet (IIS) 8,5 sur Windows server 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687) .</span><span class="sxs-lookup"><span data-stu-id="b0589-151">To install IIS on Windows Server 2012 R2, see [Installing IIS 8.5 on Windows Server 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687)</span></span>

  - <span></span>  
    <span data-ttu-id="b0589-152">Pour télécharger l’extension de routage des demandes d’applications pour les services Internet (IIS), suivez les instructions de la rubrique [application Request Routing v 2.5 Download](https://go.microsoft.com/fwlink/?linkid=291298)</span><span class="sxs-lookup"><span data-stu-id="b0589-152">To download the Application Request Routing extension for IIS, follow the instructions at [Application Request Routing v2.5 Download](https://go.microsoft.com/fwlink/?linkid=291298)</span></span>

  - <span></span>  
    <span data-ttu-id="b0589-153">Pour installer ARR, pour les instructions de la rubrique [install application Request Routing version 2](https://go.microsoft.com/fwlink/?linkid=291299)</span><span class="sxs-lookup"><span data-stu-id="b0589-153">To install ARR, for the instructions at [Install Application Request Routing Version 2](https://go.microsoft.com/fwlink/?linkid=291299)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b0589-154">Les instructions actuellement validées sont pour ARR 2,0.</span><span class="sxs-lookup"><span data-stu-id="b0589-154">The instructions currently posted are for ARR 2.0.</span></span> <span data-ttu-id="b0589-155">Pour l’installation de l’extension, il n’existe aucune différence entre les deux versions.</span><span class="sxs-lookup"><span data-stu-id="b0589-155">For installation of the extension, there is no difference between the two versions.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

