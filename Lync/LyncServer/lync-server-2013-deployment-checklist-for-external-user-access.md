---
title: 'Lync Server 2013 : Liste de vérification du déploiement pour l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c8831e8bd94040095fabd9fb335113b62b5287b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="cef82-102">Liste de vérification du déploiement pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cef82-102">Deployment checklist for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cef82-103">_**Dernière modification de la rubrique:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="cef82-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="cef82-104">Avant de déployer votre réseau de périmètre et de mettre en œuvre la prise en charge pour les utilisateurs externes, vous devez déjà avoir déployé vos serveurs internes Microsoft Lync Server 2013, y compris un pool frontal ou un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="cef82-104">Before you deploy your perimeter network and implement support for external users, you must already have deployed your Microsoft Lync Server 2013 internal servers, including a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="cef82-105">Si vous envisagez de déployer les directeurs facultatifs dans votre réseau interne, vous devez également les déployer avant de déployer des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="cef82-105">If you plan to deploy the optional Directors in your internal network, you should also deploy them prior to deploying Edge Servers.</span></span> <span data-ttu-id="cef82-106">Pour plus d’informations sur le processus de déploiement des directeurs, voir [scénarios pour le directeur dans Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="cef82-106">For details about the Director deployment process, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

<span data-ttu-id="cef82-107">Microsoft Lync Server 2013 inclut des outils permettant de faciliter la planification et le déploiement de serveurs intérieurs et de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="cef82-107">Microsoft Lync Server 2013 includes tools to facilitate planning and deployment of both internal servers and Edge Servers.</span></span> <span data-ttu-id="cef82-108">Une fois la topologie terminée, publiez la définition de topologie résultante dans votre environnement de production.</span><span class="sxs-lookup"><span data-stu-id="cef82-108">After the topology is completed, publish the resulting topology definition to your production environment.</span></span> <span data-ttu-id="cef82-109">Pour cela, vous devez être membre du groupe administrateurs de **domaine** et du groupe **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="cef82-109">To do this, you must be a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group.</span></span>

  - <span data-ttu-id="cef82-110">**Outil de planification**   Office Communications Server 2007 R2 incluait un outil de planification et un outil de planification d’arête que vous pouvez utiliser pour vous aider à concevoir la topologie.</span><span class="sxs-lookup"><span data-stu-id="cef82-110">**Planning Tool**   Office Communications Server 2007 R2 included a Planning Tool and an Edge Planning Tool that you could use to help guide topology design.</span></span> <span data-ttu-id="cef82-111">Dans Lync Server 2010, ces deux outils étaient réunis en un seul outil de planification doté de fonctionnalités et de fonctionnalités supplémentaires, telles que la collecte du nombre d’utilisateurs planifiés, des exigences vocales, des types d’accès des utilisateurs externes et des options de Fédération.</span><span class="sxs-lookup"><span data-stu-id="cef82-111">In Lync Server 2010, these two tools were combined into a single Planning Tool that has additional features and functionality, such as collecting planned user count, voice requirements, external user access types, and federation options.</span></span> <span data-ttu-id="cef82-112">De plus, vous pouvez planifier les paramètres réseau de votre infrastructure, tels que les adresses IP, les types d’équilibrage de charge et les autres aspects du réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="cef82-112">Additionally, you can plan your infrastructure’s network parameters, such as IP addresses, load balancer types and other perimeter network considerations.</span></span>

  - <span data-ttu-id="cef82-113">**Générateur de topologie**   Lync Server 2013 le générateur de topologie vous aide à définir votre topologie et vos composants.</span><span class="sxs-lookup"><span data-stu-id="cef82-113">**Topology Builder**   Lync Server 2013 Topology Builder helps you define your topology and components.</span></span> <span data-ttu-id="cef82-114">Le générateur de topologie est essentiel pour déployer des serveurs exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cef82-114">Topology Builder is essential to deploying servers running Lync Server 2013.</span></span> <span data-ttu-id="cef82-115">Le générateur de topologie publie les résultats dans un magasin central de gestion utilisé pour configurer tous les serveurs exécutant Lync Server 2013 au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="cef82-115">Topology Builder publishes the results to a Central Management store that is used to configure all of the servers running Lync Server 2013 in your organization.</span></span> <span data-ttu-id="cef82-116">Vous ne pouvez pas installer Lync Server 2013 sur les serveurs sans utiliser le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="cef82-116">You cannot install Lync Server 2013 on servers without using Topology Builder.</span></span>

<span data-ttu-id="cef82-117">Si vous avez conçu votre topologie latérale lors du processus de planification, y compris l’exécution du générateur de topologie pour définir votre topologie de périphérie, vous pouvez utiliser ces résultats pour démarrer le déploiement de votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="cef82-117">If you designed your edge topology during your planning process, including running Topology Builder to define your edge topology, you can use those results to start your Edge Server deployment.</span></span> <span data-ttu-id="cef82-118">Si vous n’avez pas fini de générer votre topologie de périphérie ou si vous souhaitez modifier les informations que vous avez spécifiées, vous devez terminer d’exécuter le générateur de topologie avant d’effectuer d’autres étapes de déploiement.</span><span class="sxs-lookup"><span data-stu-id="cef82-118">If you did not finish building your edge topology earlier or you want to change the information you previously specified, you must finish running Topology Builder before proceeding with other deployment steps.</span></span> <span data-ttu-id="cef82-119">Pour plus d’informations sur la création de votre topologie, voir [scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="cef82-119">For details about how to build your topology, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="cef82-120">Pour plus d’informations sur l’outil de planification et le générateur de topologie, voir [commencer le processus de planification de Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="cef82-120">For details about the Planning Tool and Topology Builder, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<span data-ttu-id="cef82-121">Le tableau suivant fournit une vue d’ensemble du processus de déploiement de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="cef82-121">The following table provides an overview of the Edge Server deployment process.</span></span> <span data-ttu-id="cef82-122">Pour passer en revue les décisions de planification devant être prises avant de déployer l’accès des utilisateurs externes, voir [scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="cef82-122">To review the planning decisions that must be made before deploying external user access, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="cef82-123">Les informations figurant dans le tableau suivant portent sur un nouveau déploiement.</span><span class="sxs-lookup"><span data-stu-id="cef82-123">The information in the following table focuses on a new deployment.</span></span> <span data-ttu-id="cef82-124">Si vous avez déployé des serveurs Edge dans un environnement Lync Server 2010, Office Communications Server 2007 R2 ou Office Communications Server 2007, voir la <A href="migration.md">migration</A> pour plus d’informations sur la migration vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cef82-124">If you have deployed Edge Servers in a Lync Server 2010, Office Communications Server 2007 R2 or Office Communications Server 2007 environment, see the <A href="migration.md">Migration</A> for details about migrating to Lync Server 2013.</span></span> <span data-ttu-id="cef82-125">La migration n’est pas prise en charge dans les versions antérieures à Office Communications Server 2007 R2, y compris Office Communications Server 2007, Live Communications Server 2005 et Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="cef82-125">Migration is not supported from any version prior to Office Communications Server 2007 R2, including Office Communications Server 2007, Live Communications Server 2005, and Live Communications Server 2003.</span></span>



</div>

<span data-ttu-id="cef82-126">Pour améliorer les performances et la sécurité du serveur Edge et faciliter le déploiement, appliquez les meilleures pratiques suivantes lors du déploiement de votre réseau de périmètre et des serveurs Edge:</span><span class="sxs-lookup"><span data-stu-id="cef82-126">To enhance Edge Server performance and security, and to facilitate deployment, apply the following best practices when you deploy your perimeter network and Edge Servers:</span></span>

  - <span data-ttu-id="cef82-127">Déployez les serveurs Edge uniquement après avoir testé et vérifié le fonctionnement de Lync Server 2013 au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="cef82-127">Deploy Edge Servers only after you have tested and verified operation of Lync Server 2013 inside your organization.</span></span>

  - <span data-ttu-id="cef82-128">Nous vous recommandons de déployer des serveurs de périphérie dans un groupe de travail plutôt que sur un domaine.</span><span class="sxs-lookup"><span data-stu-id="cef82-128">We recommend that you deploy Edge Servers in a workgroup rather than a domain.</span></span> <span data-ttu-id="cef82-129">Cette opération simplifie l’installation et conserve les services de domaine Active Directory (AD DS) du réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="cef82-129">Doing so simplifies installation and keeps Active Directory Domain Services (AD DS) out of the perimeter network.</span></span> <span data-ttu-id="cef82-130">La recherche d’AD DS dans le réseau de périmètre peut présenter un risque de sécurité considérable.</span><span class="sxs-lookup"><span data-stu-id="cef82-130">Locating AD DS in the perimeter network can present a significant security risk.</span></span>

  - <span data-ttu-id="cef82-131">La participation à un serveur Edge vers un domaine situé entièrement dans le réseau de périmètre est prise en charge, mais n’est pas recommandée.</span><span class="sxs-lookup"><span data-stu-id="cef82-131">Joining an Edge Server to a domain located entirely in the perimeter network is supported but not recommended.</span></span> <span data-ttu-id="cef82-132">Un serveur Edge dans le cadre du domaine interne viole les limites réseau approuvées, où Internet est le moins fiable, le réseau de périmètre est plus fiable qu’Internet et le réseau interne est le plus fiable.</span><span class="sxs-lookup"><span data-stu-id="cef82-132">An Edge Server as part of the internal domain violates trusted network boundaries, where the Internet is least trusted, perimeter network is more trusted than the Internet, and the internal network is most trusted.</span></span> <span data-ttu-id="cef82-133">Un serveur Edge en tant que membre du domaine fait automatiquement partie du réseau le plus fiable, mais réside dans un réseau moins fiable (le périmètre).</span><span class="sxs-lookup"><span data-stu-id="cef82-133">An Edge server as a member of the domain is automatically a part of the most trusted network, but resides in a less trusted network (the perimeter).</span></span>

<div>

## <a name="deployment-process-for-edge-servers"></a><span data-ttu-id="cef82-134">Processus de déploiement pour les serveurs de périphérie</span><span class="sxs-lookup"><span data-stu-id="cef82-134">Deployment Process for Edge Servers</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cef82-135">Phase</span><span class="sxs-lookup"><span data-stu-id="cef82-135">Phase</span></span></th>
<th><span data-ttu-id="cef82-136">Étapes</span><span class="sxs-lookup"><span data-stu-id="cef82-136">Steps</span></span></th>
<th><span data-ttu-id="cef82-137">Autorisations</span><span class="sxs-lookup"><span data-stu-id="cef82-137">Permissions</span></span></th>
<th><span data-ttu-id="cef82-138">Documentation</span><span class="sxs-lookup"><span data-stu-id="cef82-138">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cef82-139">Créez la topologie de bord appropriée et déterminez les composants appropriés.</span><span class="sxs-lookup"><span data-stu-id="cef82-139">Create the appropriate edge topology and determine the appropriate components.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="cef82-140">Exécutez le générateur de topologie pour configurer les paramètres du serveur de bord et créer et publier la topologie, puis utilisez Lync Server Management Shell pour exporter le fichier de configuration de la topologie.</span><span class="sxs-lookup"><span data-stu-id="cef82-140">Run Topology Builder to configure Edge Server settings and create and publish the topology, and then use Lync Server Management Shell to export the topology configuration file.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cef82-141">Groupe <strong>administrateurs de domaine</strong> et groupe <strong>RTCUniversalServerAdmins</strong> ou <strong>CsAdmins</strong></span><span class="sxs-lookup"><span data-stu-id="cef82-141"><strong>Domain Admins</strong> group and <strong>RTCUniversalServerAdmins</strong> or <strong>CsAdmins</strong> group</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="cef82-142">Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs locaux, mais la publication d’une topologie nécessite un compte membre du groupe <STRONG>administrateurs de domaine</STRONG> et du groupe <STRONG>RTCUniversalServerAdmins</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="cef82-142">You can define a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group.</span></span>


</div></td>
<td><p><span data-ttu-id="cef82-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Création d’une topologie de périphérie et de réalisateur dans Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="cef82-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cef82-144">Préparez-vous à l’installation.</span><span class="sxs-lookup"><span data-stu-id="cef82-144">Prepare for setup.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="cef82-145">Vérifiez que les conditions système préalables sont remplies.</span><span class="sxs-lookup"><span data-stu-id="cef82-145">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="cef82-146">Configurez les adresses IP (IPv4 et IPv6, s’il est utilisé) pour les interfaces réseau internes et publiques sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="cef82-146">Configure IP addresses (IPv4 and IPv6, if used) for both internal and public facing network interfaces on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="cef82-147">Configurez les enregistrements DNS internes et externes (Host A et AAAA pour IPv4 et IPv6), y compris la configuration du suffixe DNS sur l’ordinateur pour être déployé en tant que serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="cef82-147">Configure internal and external DNS records (host A and AAAA for IPv4 and IPv6), including configuring the DNS suffix on the computer to be deployed as an Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="cef82-148">Facultatif Créez et installez des certificats publics.</span><span class="sxs-lookup"><span data-stu-id="cef82-148">(Optional) Create and install public certificates.</span></span> <span data-ttu-id="cef82-149">Le temps requis pour obtenir des certificats dépend de l’autorité de certification qui émet le certificat.</span><span class="sxs-lookup"><span data-stu-id="cef82-149">The time required to obtain certificates depends on which certification authority (CA) issues the certificate.</span></span> <span data-ttu-id="cef82-150">Si vous n’effectuez pas cette étape à ce stade, vous devez le faire lors de l’installation du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="cef82-150">If you do not perform this step at this point, you must do it during Edge Server installation.</span></span> <span data-ttu-id="cef82-151">Les services du serveur Edge ne peuvent pas être démarrés tant que les certificats n’ont pas été obtenus et installés.</span><span class="sxs-lookup"><span data-stu-id="cef82-151">The Edge Server services cannot be started until certificates are obtained and installed.</span></span></p></li>
<li><p><span data-ttu-id="cef82-152">La prise en charge de la connectivité PIC (Public IM Connectivity), si votre déploiement prend en charge les communications avec Windows Live, AOL ou Yahoo!</span><span class="sxs-lookup"><span data-stu-id="cef82-152">Provision support for public IM connectivity, if your deployment is to support communications with Windows Live, AOL, or Yahoo!</span></span> <span data-ttu-id="cef82-153">ont.</span><span class="sxs-lookup"><span data-stu-id="cef82-153">users.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="cef82-154">À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity («PIC USL») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="cef82-154">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="cef82-155">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo!</span><span class="sxs-lookup"><span data-stu-id="cef82-155">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="cef82-156">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="cef82-156">Messenger until the service shut down date.</span></span> <span data-ttu-id="cef82-157">Date de fin de vie du 2014 juin pour AOL et Yahoo!</span><span class="sxs-lookup"><span data-stu-id="cef82-157">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="cef82-158">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="cef82-158">has been announced.</span></span> <span data-ttu-id="cef82-159">Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cef82-159">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="cef82-160">La fonction USL (PIC) est une licence d’abonnement par mois qui est requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo!</span><span class="sxs-lookup"><span data-stu-id="cef82-160">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="cef82-161">Messenger.</span><span class="sxs-lookup"><span data-stu-id="cef82-161">Messenger.</span></span> <span data-ttu-id="cef82-162">La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo!, le contrat sous-jacent pour lequel le son est arrêté.</span><span class="sxs-lookup"><span data-stu-id="cef82-162">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="cef82-163">Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="cef82-163">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="cef82-164">La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync.</span><span class="sxs-lookup"><span data-stu-id="cef82-164">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="cef82-165">Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.</span><span class="sxs-lookup"><span data-stu-id="cef82-165">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
<li><p><span data-ttu-id="cef82-166">La prise en charge de XMPP et de la prise en charge de la Fédération pour Office Communications Server 2007, Office Communications Server 2007 R2 et les partenaires Lync Server 2010, si votre déploiement utilisera ces</span><span class="sxs-lookup"><span data-stu-id="cef82-166">Provision support for XMPP and federation support for Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 partners, if your deployment will use these</span></span></p></li>
<li><p><span data-ttu-id="cef82-167">Configurer des pare-feu.</span><span class="sxs-lookup"><span data-stu-id="cef82-167">Configure firewalls.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="cef82-168">En fonction de votre organisation</span><span class="sxs-lookup"><span data-stu-id="cef82-168">As appropriate to your organization</span></span></p></td>
<td><p><span data-ttu-id="cef82-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Préparer l’installation des serveurs dans le réseau de périmètre pour Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="cef82-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cef82-170">Configurez un proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="cef82-170">Set up reverse proxy.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="cef82-171">Configurez le proxy inverse (par exemple, pour la passerelle Microsoft Forefront Threat Management 2010 ou Microsoft Internet Security and Acceleration (ISA) Server avec Service Pack 1) dans le réseau de périmètre, obtenez les certificats publics nécessaires et configurez le règles de publication Web sur le serveur proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="cef82-171">Set up the reverse proxy (for example, for Microsoft Forefront Threat Management Gateway 2010 or Microsoft Internet Security and Acceleration (ISA) Server with Service Pack 1) in the perimeter network, obtain the necessary public certificates, and configure the web publishing rules on the reverse proxy server.</span></span></p>
<p><span data-ttu-id="cef82-172">Préparez le proxy inverse pour les services de mobilité si vous avez planifié la mobilité et déployez les services de mobilité sur le pool frontal ou le serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="cef82-172">Prepare the reverse proxy for Mobility services if you have planned for Mobility and are deploying the Mobility services on the Front End pool or Standard Edition server.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cef82-173">Groupe <strong>administrateurs</strong> ou administrateur de proxy inverse</span><span class="sxs-lookup"><span data-stu-id="cef82-173"><strong>Administrators</strong> group or Reverse Proxy administrator</span></span></p></td>
<td><p><span data-ttu-id="cef82-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configuration de serveurs proxy inverse pour Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="cef82-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cef82-175">Configurer un directeur (facultatif).</span><span class="sxs-lookup"><span data-stu-id="cef82-175">Setup a Director (optional).</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="cef82-176">Facultatif Installez et configurez un ou plusieurs directeurs sur le réseau interne.</span><span class="sxs-lookup"><span data-stu-id="cef82-176">(Optional) Install and configure one or more Directors in the internal network.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="cef82-177">Groupe <strong>administrateurs</strong></span><span class="sxs-lookup"><span data-stu-id="cef82-177"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="cef82-178"><a href="lync-server-2013-setting-up-the-director.md">Configuration du réalisateur dans Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="cef82-178"><a href="lync-server-2013-setting-up-the-director.md">Setting up the Director in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cef82-179">Configurez les serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="cef82-179">Set up Edge Servers.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="cef82-180">Installez le logiciel requis.</span><span class="sxs-lookup"><span data-stu-id="cef82-180">Install prerequisite software.</span></span></p></li>
<li><p><span data-ttu-id="cef82-181">Transférez le fichier de configuration topologique exporté vers chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="cef82-181">Transport the exported topology configuration file to each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="cef82-182">Installez le logiciel Lync Server 2013 sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="cef82-182">Install the Lync Server 2013 software on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="cef82-183">Configurez les serveurs de périphérie.</span><span class="sxs-lookup"><span data-stu-id="cef82-183">Configure the Edge Servers.</span></span></p></li>
<li><p><span data-ttu-id="cef82-184">Demandez et installez des certificats pour chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="cef82-184">Request and install certificates for each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="cef82-185">Démarrez les services Edge Server.</span><span class="sxs-lookup"><span data-stu-id="cef82-185">Start the Edge Server services.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="cef82-186">Groupe <strong>administrateurs</strong></span><span class="sxs-lookup"><span data-stu-id="cef82-186"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="cef82-187"><a href="lync-server-2013-setting-up-edge-servers.md">Configuration de serveurs de frontière dans Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="cef82-187"><a href="lync-server-2013-setting-up-edge-servers.md">Setting up Edge Servers in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cef82-188">Configurer le déploiement pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="cef82-188">Configure deployment for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="cef82-189">Utilisez le panneau de configuration de Lync Server pour configurer la prise en charge de chacun des éléments suivants (selon le cas):</span><span class="sxs-lookup"><span data-stu-id="cef82-189">Use the Lync Server Control Panel to configure support for each of the following (as applicable):</span></span></p>
<ul>
<li><p><span data-ttu-id="cef82-190">Relais multimédia</span><span class="sxs-lookup"><span data-stu-id="cef82-190">Media relay</span></span></p></li>
<li><p><span data-ttu-id="cef82-191">Itinéraire de Fédération</span><span class="sxs-lookup"><span data-stu-id="cef82-191">Federation route</span></span></p></li>
<li><p><span data-ttu-id="cef82-192">Accès des utilisateurs distants</span><span class="sxs-lookup"><span data-stu-id="cef82-192">Remote user access</span></span></p></li>
<li><p><span data-ttu-id="cef82-193">Fédération avec Lync Server, Office Communications Server et Live Communications Server</span><span class="sxs-lookup"><span data-stu-id="cef82-193">Federation with Lync Server, Office Communications Server and Live Communications Server</span></span></p></li>
<li><p><span data-ttu-id="cef82-194">Solution PIC (Public IM Connectivity)</span><span class="sxs-lookup"><span data-stu-id="cef82-194">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="cef82-195">Fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="cef82-195">XMPP federation</span></span></p></li>
<li><p><span data-ttu-id="cef82-196">Utilisateurs anonymes</span><span class="sxs-lookup"><span data-stu-id="cef82-196">Anonymous users</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="cef82-197">Configurer les comptes d’utilisateurs pour l’accès des utilisateurs distants, la Fédération, la connectivité PIC (Public IM Connectivity), le service d’assistance utilisateur (selon le cas)</span><span class="sxs-lookup"><span data-stu-id="cef82-197">Configure user accounts for remote user access, federation, public IM connectivity, XMPP and anonymous user support (as applicable)</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="cef82-198"><strong>RTCUniversalServerAdmins</strong> groupe ou compte d’utilisateur affecté au rôle <strong>CSAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="cef82-198"><strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p></td>
<td><p><span data-ttu-id="cef82-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuration de la prise en charge de l’accès des utilisateurs externes dans Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="cef82-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cef82-200">Vérifiez la configuration de votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="cef82-200">Verify your Edge Server configuration.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="cef82-201">Vérifier la connectivité du serveur et la réplication des données de configuration à partir de serveurs internes.</span><span class="sxs-lookup"><span data-stu-id="cef82-201">Verify server connectivity and replication of configuration data from internal servers.</span></span></p></li>
<li><p><span data-ttu-id="cef82-202">Vérifiez que les utilisateurs externes peuvent se connecter, y compris aux utilisateurs distants, aux utilisateurs des domaines fédérés, aux utilisateurs de messagerie instantanée publique et aux utilisateurs anonymes, en fonction de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="cef82-202">Verify that external users can connect, including remote users, users in federated domains, public IM users, and anonymous users, as appropriate to your deployment.</span></span></p></li>
<li><p><span data-ttu-id="cef82-203">Vérifier la configuration et la communication à l’aide de Lync Server Remote Connectivity Analyzer<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span><span class="sxs-lookup"><span data-stu-id="cef82-203">Verify configuration and communication using the Lync Server Remote Connectivity Analyzer <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span></span></p></li>
<li><p><span data-ttu-id="cef82-204">Résoudre les problèmes de configuration et de communication</span><span class="sxs-lookup"><span data-stu-id="cef82-204">Troubleshoot configuration and communication difficulties</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="cef82-205">Pour la vérification de la réplication, du groupe <strong>RTCUniversalServerAdmins</strong> ou du compte d’utilisateur affecté au rôle <strong>CSAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="cef82-205">For verification of replication, <strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p>
<p><span data-ttu-id="cef82-206">Pour la vérification de la connectivité utilisateur, un utilisateur pour chaque type d’accès des utilisateurs externes que vous prenez en charge</span><span class="sxs-lookup"><span data-stu-id="cef82-206">For verification of user connectivity, a user for each type of external user access that you support</span></span></p>
<p><span data-ttu-id="cef82-207">Utilisateurs distants</span><span class="sxs-lookup"><span data-stu-id="cef82-207">Remote users</span></span></p></td>
<td><p><span data-ttu-id="cef82-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Vérifier votre déploiement Edge dans Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="cef82-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

