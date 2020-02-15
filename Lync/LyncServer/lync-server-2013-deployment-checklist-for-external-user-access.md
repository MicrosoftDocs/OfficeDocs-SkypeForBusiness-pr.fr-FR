---
title: 'Lync Server 2013 : liste de vérification du déploiement pour l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a624a60ba219d7707d1dcbfb060a0df409c6290
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="664ee-102">Liste de vérification du déploiement pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="664ee-102">Deployment checklist for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="664ee-103">_**Dernière modification de la rubrique :** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="664ee-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="664ee-104">Avant de déployer votre réseau de périmètre et d’implémenter la prise en charge pour les utilisateurs externes, vous devez déjà avoir déployé vos serveurs internes Microsoft Lync Server 2013, y compris un pool frontal ou un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="664ee-104">Before you deploy your perimeter network and implement support for external users, you must already have deployed your Microsoft Lync Server 2013 internal servers, including a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="664ee-105">Si vous envisagez de déployer les directeurs facultatifs dans votre réseau interne, vous devez également les déployer avant de déployer les serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="664ee-105">If you plan to deploy the optional Directors in your internal network, you should also deploy them prior to deploying Edge Servers.</span></span> <span data-ttu-id="664ee-106">Pour plus d’informations sur le processus de déploiement de directeur, voir [scénarios pour le directeur dans Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="664ee-106">For details about the Director deployment process, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

<span data-ttu-id="664ee-107">Microsoft Lync Server 2013 inclut des outils permettant de faciliter la planification et le déploiement des serveurs internes et des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="664ee-107">Microsoft Lync Server 2013 includes tools to facilitate planning and deployment of both internal servers and Edge Servers.</span></span> <span data-ttu-id="664ee-108">Une fois la topologie finalisée, publiez la définition de topologie qui en résulte dans votre environnement de production.</span><span class="sxs-lookup"><span data-stu-id="664ee-108">After the topology is completed, publish the resulting topology definition to your production environment.</span></span> <span data-ttu-id="664ee-109">Pour ce faire, vous devez être membre du groupe **Administrateurs du domaine** et du groupe **RTCUniversalServerAdmins**.</span><span class="sxs-lookup"><span data-stu-id="664ee-109">To do this, you must be a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group.</span></span>

  - <span data-ttu-id="664ee-110">**Outil de planification**   Office Communications Server 2007 R2 comprenait un outil de planification et un outil de planification Edge que vous pouvez utiliser pour vous aider à concevoir la topologie.</span><span class="sxs-lookup"><span data-stu-id="664ee-110">**Planning Tool**   Office Communications Server 2007 R2 included a Planning Tool and an Edge Planning Tool that you could use to help guide topology design.</span></span> <span data-ttu-id="664ee-111">Dans Lync Server 2010, ces deux outils ont été combinés en un seul outil de planification doté de fonctionnalités et de fonctionnalités supplémentaires, telles que la collecte du nombre d’utilisateurs planifiés, les exigences de la voix, les types d’accès des utilisateurs externes et les options de Fédération.</span><span class="sxs-lookup"><span data-stu-id="664ee-111">In Lync Server 2010, these two tools were combined into a single Planning Tool that has additional features and functionality, such as collecting planned user count, voice requirements, external user access types, and federation options.</span></span> <span data-ttu-id="664ee-112">Par ailleurs, vous pouvez planifier les paramètres réseau de votre infrastructure, tels que les adresses IP, les types d’équilibrage de charge, ainsi que d’autres considérations relatives aux réseaux de périmètre.</span><span class="sxs-lookup"><span data-stu-id="664ee-112">Additionally, you can plan your infrastructure’s network parameters, such as IP addresses, load balancer types and other perimeter network considerations.</span></span>

  - <span data-ttu-id="664ee-113">\*\*\*\*   Le générateur de topologie Lync Server 2013 du générateur de topologies vous permet de définir votre topologie et vos composants.</span><span class="sxs-lookup"><span data-stu-id="664ee-113">**Topology Builder**   Lync Server 2013 Topology Builder helps you define your topology and components.</span></span> <span data-ttu-id="664ee-114">Le générateur de topologie est essentiel pour déployer des serveurs exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="664ee-114">Topology Builder is essential to deploying servers running Lync Server 2013.</span></span> <span data-ttu-id="664ee-115">Le générateur de topologies publie les résultats dans un magasin central de gestion qui est utilisé pour configurer tous les serveurs exécutant Lync Server 2013 dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="664ee-115">Topology Builder publishes the results to a Central Management store that is used to configure all of the servers running Lync Server 2013 in your organization.</span></span> <span data-ttu-id="664ee-116">Vous ne pouvez pas installer Lync Server 2013 sur des serveurs sans utiliser le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="664ee-116">You cannot install Lync Server 2013 on servers without using Topology Builder.</span></span>

<span data-ttu-id="664ee-117">Si vous avez conçu votre topologie Edge lors de votre processus de planification, y compris l’exécution du générateur de topologies pour définir votre topologie Edge, vous pouvez utiliser ces résultats pour démarrer le déploiement de votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="664ee-117">If you designed your edge topology during your planning process, including running Topology Builder to define your edge topology, you can use those results to start your Edge Server deployment.</span></span> <span data-ttu-id="664ee-118">Si vous n’avez pas terminé la création de votre topologie Edge ou si vous souhaitez modifier les informations que vous avez précédemment spécifiées, vous devez terminer l’exécution du générateur de topologie avant d’effectuer d’autres étapes de déploiement.</span><span class="sxs-lookup"><span data-stu-id="664ee-118">If you did not finish building your edge topology earlier or you want to change the information you previously specified, you must finish running Topology Builder before proceeding with other deployment steps.</span></span> <span data-ttu-id="664ee-119">Pour plus d’informations sur la création de votre topologie, reportez-vous à la rubrique [scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="664ee-119">For details about how to build your topology, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="664ee-120">Pour plus d’informations sur l’outil de planification et le générateur de topologies, voir [démarrage du processus de planification pour Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="664ee-120">For details about the Planning Tool and Topology Builder, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<span data-ttu-id="664ee-121">Le tableau suivant présente une vue d’ensemble du processus de déploiement des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="664ee-121">The following table provides an overview of the Edge Server deployment process.</span></span> <span data-ttu-id="664ee-122">Pour passer en revue les décisions de planification qui doivent être prises avant de déployer l’accès des utilisateurs externes, reportez-vous à la rubrique [scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="664ee-122">To review the planning decisions that must be made before deploying external user access, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="664ee-123">Les informations contenues dans le tableau suivant s’appliquent essentiellement à un nouveau déploiement.</span><span class="sxs-lookup"><span data-stu-id="664ee-123">The information in the following table focuses on a new deployment.</span></span> <span data-ttu-id="664ee-124">Si vous avez déployé des serveurs Edge dans un environnement Lync Server 2010, Office Communications Server 2007 R2 ou Office Communications Server 2007, consultez la rubrique <A href="migration.md">migration</A> pour plus d’informations sur la migration vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="664ee-124">If you have deployed Edge Servers in a Lync Server 2010, Office Communications Server 2007 R2 or Office Communications Server 2007 environment, see the <A href="migration.md">Migration</A> for details about migrating to Lync Server 2013.</span></span> <span data-ttu-id="664ee-125">La migration n’est pas prise en charge dans les versions antérieures à Office Communications Server 2007 R2, notamment Office Communications Server 2007, Live Communications Server 2005 et Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="664ee-125">Migration is not supported from any version prior to Office Communications Server 2007 R2, including Office Communications Server 2007, Live Communications Server 2005, and Live Communications Server 2003.</span></span>



</div>

<span data-ttu-id="664ee-126">Pour améliorer les performances et le niveau de sécurité des serveurs Edge, mais aussi pour faciliter leur déploiement, appliquez les recommandations suivantes lors du déploiement de votre réseau de périmètre et de vos serveurs Edge :</span><span class="sxs-lookup"><span data-stu-id="664ee-126">To enhance Edge Server performance and security, and to facilitate deployment, apply the following best practices when you deploy your perimeter network and Edge Servers:</span></span>

  - <span data-ttu-id="664ee-127">Déployez les serveurs Edge uniquement après avoir testé et vérifié le fonctionnement de Lync Server 2013 au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="664ee-127">Deploy Edge Servers only after you have tested and verified operation of Lync Server 2013 inside your organization.</span></span>

  - <span data-ttu-id="664ee-p108">Nous vous recommandons de déployer des serveurs Edge dans un groupe de travail et non pas dans un domaine. Cela simplifie l’installation et conserve les services AD DS (Active Directory Domain Services) en dehors du périmètre du réseau. Leur localisation peut en effet présenter des risques de sécurité importants.</span><span class="sxs-lookup"><span data-stu-id="664ee-p108">We recommend that you deploy Edge Servers in a workgroup rather than a domain. Doing so simplifies installation and keeps Active Directory Domain Services (AD DS) out of the perimeter network. Locating AD DS in the perimeter network can present a significant security risk.</span></span>

  - <span data-ttu-id="664ee-p109">L’association d’un serveur Edge Server à un domaine se trouvant entièrement dans le périmètre du réseau est prise en charge, mais non recommandée. Un serveur Edge qui fait partie intégrante du domaine interne enfreint les limites du réseau fiable. En termes de fiabilité, Internet se situe au plus bas de l’échelle, suivi des réseaux de périmètre, puis du réseau interne, qui est considéré comme le plus fiable. Un serveur Edge qui est membre du domaine fait automatiquement partie intégrante du réseau le plus fiable, mais réside dans un réseau moins fiable (le périmètre).</span><span class="sxs-lookup"><span data-stu-id="664ee-p109">Joining an Edge Server to a domain located entirely in the perimeter network is supported but not recommended. An Edge Server as part of the internal domain violates trusted network boundaries, where the Internet is least trusted, perimeter network is more trusted than the Internet, and the internal network is most trusted. An Edge server as a member of the domain is automatically a part of the most trusted network, but resides in a less trusted network (the perimeter).</span></span>

<div>

## <a name="deployment-process-for-edge-servers"></a><span data-ttu-id="664ee-134">Processus de déploiement des serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="664ee-134">Deployment Process for Edge Servers</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="664ee-135">Phase</span><span class="sxs-lookup"><span data-stu-id="664ee-135">Phase</span></span></th>
<th><span data-ttu-id="664ee-136">Étapes</span><span class="sxs-lookup"><span data-stu-id="664ee-136">Steps</span></span></th>
<th><span data-ttu-id="664ee-137">Autorisations</span><span class="sxs-lookup"><span data-stu-id="664ee-137">Permissions</span></span></th>
<th><span data-ttu-id="664ee-138">Documentation</span><span class="sxs-lookup"><span data-stu-id="664ee-138">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="664ee-139">Créez la topologie Edge appropriée et déterminez les composants adéquats.</span><span class="sxs-lookup"><span data-stu-id="664ee-139">Create the appropriate edge topology and determine the appropriate components.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="664ee-140">Exécutez le générateur de topologie pour configurer les paramètres du serveur Edge et créer et publier la topologie, puis utilisez Lync Server Management Shell pour exporter le fichier de configuration de topologie.</span><span class="sxs-lookup"><span data-stu-id="664ee-140">Run Topology Builder to configure Edge Server settings and create and publish the topology, and then use Lync Server Management Shell to export the topology configuration file.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="664ee-141">Groupe <strong>administrateurs du domaine</strong> et groupe <strong>RTCUniversalServerAdmins</strong> ou <strong>CsAdmins</strong></span><span class="sxs-lookup"><span data-stu-id="664ee-141"><strong>Domain Admins</strong> group and <strong>RTCUniversalServerAdmins</strong> or <strong>CsAdmins</strong> group</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="664ee-142">Vous pouvez définir une topologie à l’aide d’un compte qui est membre du groupe d’utilisateurs locaux, mais la publication d’une topologie nécessite un compte qui soit membre du groupe <STRONG>Administrateurs du domaine</STRONG> et du groupe <STRONG>RTCUniversalServerAdmins</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="664ee-142">You can define a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group.</span></span>


</div></td>
<td><p><span data-ttu-id="664ee-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Création d’une topologie de serveur Edge et de directeur dans Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="664ee-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="664ee-144">Préparez l’installation.</span><span class="sxs-lookup"><span data-stu-id="664ee-144">Prepare for setup.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="664ee-145">Assurez-vous que les conditions préalables du système sont respectées.</span><span class="sxs-lookup"><span data-stu-id="664ee-145">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="664ee-146">Configurez les adresses IP (IPv4 et IPv6, le cas échéant) des interfaces réseau interne et publique sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="664ee-146">Configure IP addresses (IPv4 and IPv6, if used) for both internal and public facing network interfaces on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="664ee-147">Configurez les enregistrements DNS internes et externes (hôte A et AAAA pour IPv4 et IPv6), y compris le suffixe DNS sur l’ordinateur à déployer en tant que serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="664ee-147">Configure internal and external DNS records (host A and AAAA for IPv4 and IPv6), including configuring the DNS suffix on the computer to be deployed as an Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="664ee-p110">(Facultatif) Créez et installez des certificats publics. La durée nécessaire à l’obtention de certificats dépend de l’autorité de certification qui les émet. Si vous n’effectuez pas cette étape à ce stade, vous devrez le faire lors de l’installation du serveur Edge. Les services du serveur Edge ne peuvent pas être démarrés tant que les certificats n’ont pas été obtenus et installés.</span><span class="sxs-lookup"><span data-stu-id="664ee-p110">(Optional) Create and install public certificates. The time required to obtain certificates depends on which certification authority (CA) issues the certificate. If you do not perform this step at this point, you must do it during Edge Server installation. The Edge Server services cannot be started until certificates are obtained and installed.</span></span></p></li>
<li><p><span data-ttu-id="664ee-p111">Provisionnez la prise en charge de la solution PIC (Public IM Connectivity) si votre déploiement doit prendre en charge les communications avec des utilisateurs Windows Live, AOL ou Yahoo!.</span><span class="sxs-lookup"><span data-stu-id="664ee-p111">Provision support for public IM connectivity, if your deployment is to support communications with Windows Live, AOL, or Yahoo! users.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="664ee-154">À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="664ee-154">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="664ee-155">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !.</span><span class="sxs-lookup"><span data-stu-id="664ee-155">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="664ee-156">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="664ee-156">Messenger until the service shut down date.</span></span> <span data-ttu-id="664ee-157">Date de fin du 2014 juin pour AOL et Yahoo !</span><span class="sxs-lookup"><span data-stu-id="664ee-157">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="664ee-158">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="664ee-158">has been announced.</span></span> <span data-ttu-id="664ee-159">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="664ee-159">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="664ee-160">La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="664ee-160">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="664ee-161">Messenger.</span><span class="sxs-lookup"><span data-stu-id="664ee-161">Messenger.</span></span> <span data-ttu-id="664ee-162">La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</span><span class="sxs-lookup"><span data-stu-id="664ee-162">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="664ee-163">Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="664ee-163">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="664ee-164">La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard.</span><span class="sxs-lookup"><span data-stu-id="664ee-164">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="664ee-165">La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</span><span class="sxs-lookup"><span data-stu-id="664ee-165">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
<li><p><span data-ttu-id="664ee-166">Mise en service de la prise en charge de XMPP et de la Fédération pour Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 Partners, si votre déploiement utilise ces</span><span class="sxs-lookup"><span data-stu-id="664ee-166">Provision support for XMPP and federation support for Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 partners, if your deployment will use these</span></span></p></li>
<li><p><span data-ttu-id="664ee-167">Configurez les pare-feu.</span><span class="sxs-lookup"><span data-stu-id="664ee-167">Configure firewalls.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="664ee-168">En fonction de votre organisation</span><span class="sxs-lookup"><span data-stu-id="664ee-168">As appropriate to your organization</span></span></p></td>
<td><p><span data-ttu-id="664ee-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Préparation de l’installation des serveurs dans le réseau de périmètre pour Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="664ee-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="664ee-170">Installez le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="664ee-170">Set up reverse proxy.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="664ee-171">Configurez le proxy inverse (par exemple, pour Microsoft Forefront Threat Management Gateway 2010 ou Microsoft Internet Security and Acceleration (ISA) Server avec Service Pack 1) dans le réseau de périmètre, obtenez les certificats publics nécessaires et configurez le règles de publication Web sur le serveur proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="664ee-171">Set up the reverse proxy (for example, for Microsoft Forefront Threat Management Gateway 2010 or Microsoft Internet Security and Acceleration (ISA) Server with Service Pack 1) in the perimeter network, obtain the necessary public certificates, and configure the web publishing rules on the reverse proxy server.</span></span></p>
<p><span data-ttu-id="664ee-172">Préparez le proxy inverse pour les services de mobilité si vous avez prévu de les déployer sur le pool frontal ou le serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="664ee-172">Prepare the reverse proxy for Mobility services if you have planned for Mobility and are deploying the Mobility services on the Front End pool or Standard Edition server.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="664ee-173">Groupe <strong>Administrateurs</strong> ou administrateur du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="664ee-173"><strong>Administrators</strong> group or Reverse Proxy administrator</span></span></p></td>
<td><p><span data-ttu-id="664ee-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up proxy inverse Servers for Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="664ee-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="664ee-175">Installez un directeur (facultatif).</span><span class="sxs-lookup"><span data-stu-id="664ee-175">Setup a Director (optional).</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="664ee-176">(Facultatif) Installez et configurez un ou plusieurs directeurs dans le réseau interne.</span><span class="sxs-lookup"><span data-stu-id="664ee-176">(Optional) Install and configure one or more Directors in the internal network.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="664ee-177">Groupe <strong>Administrateurs</strong></span><span class="sxs-lookup"><span data-stu-id="664ee-177"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="664ee-178"><a href="lync-server-2013-setting-up-the-director.md">Configuration du directeur dans Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="664ee-178"><a href="lync-server-2013-setting-up-the-director.md">Setting up the Director in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="664ee-179">Installez des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="664ee-179">Set up Edge Servers.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="664ee-180">Installez les logiciels prérequis.</span><span class="sxs-lookup"><span data-stu-id="664ee-180">Install prerequisite software.</span></span></p></li>
<li><p><span data-ttu-id="664ee-181">Transportez le fichier de configuration de topologie exporté vers chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="664ee-181">Transport the exported topology configuration file to each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="664ee-182">Installez le logiciel Lync Server 2013 sur chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="664ee-182">Install the Lync Server 2013 software on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="664ee-183">Configurez les serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="664ee-183">Configure the Edge Servers.</span></span></p></li>
<li><p><span data-ttu-id="664ee-184">Demandez et installez des certificats pour chaque serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="664ee-184">Request and install certificates for each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="664ee-185">Démarrez les services du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="664ee-185">Start the Edge Server services.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="664ee-186">Groupe <strong>Administrateurs</strong></span><span class="sxs-lookup"><span data-stu-id="664ee-186"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="664ee-187"><a href="lync-server-2013-setting-up-edge-servers.md">Setting up Edge servers in Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="664ee-187"><a href="lync-server-2013-setting-up-edge-servers.md">Setting up Edge Servers in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="664ee-188">Configurez le déploiement pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="664ee-188">Configure deployment for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="664ee-189">Utilisez le panneau de configuration Lync Server pour configurer la prise en charge de chacune des opérations suivantes (selon les cas) :</span><span class="sxs-lookup"><span data-stu-id="664ee-189">Use the Lync Server Control Panel to configure support for each of the following (as applicable):</span></span></p>
<ul>
<li><p><span data-ttu-id="664ee-190">Serveur relais multimédia</span><span class="sxs-lookup"><span data-stu-id="664ee-190">Media relay</span></span></p></li>
<li><p><span data-ttu-id="664ee-191">Itinéraire de fédération</span><span class="sxs-lookup"><span data-stu-id="664ee-191">Federation route</span></span></p></li>
<li><p><span data-ttu-id="664ee-192">Accès des utilisateurs distants</span><span class="sxs-lookup"><span data-stu-id="664ee-192">Remote user access</span></span></p></li>
<li><p><span data-ttu-id="664ee-193">Fédération avec Lync Server, Office Communications Server et Live Communications Server</span><span class="sxs-lookup"><span data-stu-id="664ee-193">Federation with Lync Server, Office Communications Server and Live Communications Server</span></span></p></li>
<li><p><span data-ttu-id="664ee-194">Solution PIC (Public IM Connectivity)</span><span class="sxs-lookup"><span data-stu-id="664ee-194">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="664ee-195">Fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="664ee-195">XMPP federation</span></span></p></li>
<li><p><span data-ttu-id="664ee-196">Utilisateurs anonymes</span><span class="sxs-lookup"><span data-stu-id="664ee-196">Anonymous users</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="664ee-197">Configurez les comptes d’utilisateurs pour la prise en charge de l’accès des utilisateurs distants, de la fédération, de la solution PIC (Public IM Connectivity) et des utilisateurs XMPP et anonymes (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="664ee-197">Configure user accounts for remote user access, federation, public IM connectivity, XMPP and anonymous user support (as applicable)</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="664ee-198">Groupe <strong>RTCUniversalServerAdmins</strong> ou compte d’utilisateur affecté au rôle <strong>CSAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="664ee-198"><strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p></td>
<td><p><span data-ttu-id="664ee-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuration de la prise en charge de l’accès des utilisateurs externes dans Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="664ee-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="664ee-200">Vérifiez votre configuration de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="664ee-200">Verify your Edge Server configuration.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="664ee-201">Vérifiez la connectivité serveur et la réplication des données de configuration à partir des serveurs internes.</span><span class="sxs-lookup"><span data-stu-id="664ee-201">Verify server connectivity and replication of configuration data from internal servers.</span></span></p></li>
<li><p><span data-ttu-id="664ee-202">Vérifiez que les utilisateurs externes peuvent se connecter, y compris les utilisateurs distants, les utilisateurs des domaines fédérés, les utilisateurs Public IM et les utilisateurs anonymes, selon votre type de déploiement.</span><span class="sxs-lookup"><span data-stu-id="664ee-202">Verify that external users can connect, including remote users, users in federated domains, public IM users, and anonymous users, as appropriate to your deployment.</span></span></p></li>
<li><p><span data-ttu-id="664ee-203">Vérifier la configuration et la communication à l’aide de l’analyseur de connectivité à distance Lync Server<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span><span class="sxs-lookup"><span data-stu-id="664ee-203">Verify configuration and communication using the Lync Server Remote Connectivity Analyzer <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span></span></p></li>
<li><p><span data-ttu-id="664ee-204">Résoudre les problèmes de configuration et de communication</span><span class="sxs-lookup"><span data-stu-id="664ee-204">Troubleshoot configuration and communication difficulties</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="664ee-205">Pour la vérification de la réplication, groupe <strong>RTCUniversalServerAdmins</strong> ou compte d’utilisateur affecté au rôle <strong>CSAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="664ee-205">For verification of replication, <strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p>
<p><span data-ttu-id="664ee-206">Pour la vérification de la connectivité utilisateur, un utilisateur pour chaque type d’accès des utilisateurs externes que vous prenez en charge</span><span class="sxs-lookup"><span data-stu-id="664ee-206">For verification of user connectivity, a user for each type of external user access that you support</span></span></p>
<p><span data-ttu-id="664ee-207">Utilisateurs distants</span><span class="sxs-lookup"><span data-stu-id="664ee-207">Remote users</span></span></p></td>
<td><p><span data-ttu-id="664ee-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Vérification de votre déploiement Edge dans Lync Server 2013</a> dans la documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="664ee-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

