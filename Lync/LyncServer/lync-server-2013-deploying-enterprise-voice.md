---
title: 'Lync Server 2013 : déploiement d’Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf57d55899d556ddfde633c975ae9f0516e48e14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="c93bf-102">Déploiement d’Enterprise Voice dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-102">Deploying Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c93bf-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="c93bf-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="c93bf-104">Lync Server 2013, voix entreprise fait partie de l’infrastructure de serveur 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c93bf-104">Lync Server 2013, Enterprise Voice is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="c93bf-105">Le déploiement de voix entreprise nécessite les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="c93bf-105">Deploying Enterprise Voice requires that you:</span></span>

<div id="sectionSection0" class="section">

1.  <span data-ttu-id="c93bf-106">Reportez-vous à la section [planning pour Enterprise Voice dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) de la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="c93bf-106">Review the [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) section of the Planning documentation.</span></span>

2.  <span data-ttu-id="c93bf-107">Finalisez les plans des fonctionnalités et composants à déployer avec cette charge de travail.</span><span class="sxs-lookup"><span data-stu-id="c93bf-107">Finalize plans for features and components to deploy with this workload.</span></span>

3.  <span data-ttu-id="c93bf-108">Exécutez l’outil de planification pour concevoir une topologie reflétant vos décisions de déploiement.</span><span class="sxs-lookup"><span data-stu-id="c93bf-108">Run Planning Tool to design a topology that reflects your deployment decisions.</span></span>

4.  <span data-ttu-id="c93bf-109">Ouvrez la conception topologique dans le générateur de topologie, comme décrit dans la rubrique [définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="c93bf-109">Open the topology design in Topology Builder, as described in [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c93bf-110">L’installation du générateur de topologie fait partie du processus de déploiement du pool interne.</span><span class="sxs-lookup"><span data-stu-id="c93bf-110">Installation of Topology Builder is part of the deployment process for the internal pool.</span></span> <span data-ttu-id="c93bf-111">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-install-lync-server-administrative-tools.md">installation des outils d’administration de Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="c93bf-111">For details, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="c93bf-112">Par ailleurs, vous devez déjà avoir déployé Lync Server Enterprise Edition dans des sites centraux et des sites de succursales correspondant à la topologie de référence que vous choisissez de déployer.</span><span class="sxs-lookup"><span data-stu-id="c93bf-112">Additionally, you must have already deployed Lync Server, Enterprise Edition at central sites and branch sites that correspond to the reference topology that you choose to deploy.</span></span> <span data-ttu-id="c93bf-113">Vous ne pouvez pas déployer les composants voix entreprise tant que vous n’avez pas défini, publié et installé des fichiers pour au moins un pool interne et vous devez utiliser le générateur de topologie pour définir et publier un pool interne.</span><span class="sxs-lookup"><span data-stu-id="c93bf-113">You can’t deploy Enterprise Voice components until you have defined, published, and installed files for at least one internal pool, and you must use Topology Builder to define and publish an internal pool.</span></span>

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

<span data-ttu-id="c93bf-114">Pour afficher des topologies de référence à l’aide d’exemples de déploiement des rôles de serveur voix entreprise (et leur relation entre un autre et les rôles serveur Lync Server 2013), voir [topologies de référence dans Lync server 2013](lync-server-2013-reference-topologies.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="c93bf-114">To view reference topologies with examples of where Enterprise Voice server roles can be deployed (and their relationship to one another and other Lync Server 2013 server roles), see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span>

<span data-ttu-id="c93bf-115">Pour afficher une topologie de référence illustrant et expliquant un exemple de déploiement de contrôle d’admission des appels, notamment les régions réseau, les sites réseau et les sous-réseaux, voir [exemple : rassemblement de vos exigences en matière de contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="c93bf-115">To view a reference topology that illustrates and explains a sample call admission control deployment, including network regions, network sites, and subnets, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c93bf-116">Pour déployer Enterprise Voice sur un site central, poursuivez la lecture des rubriques de cette section.</span><span class="sxs-lookup"><span data-stu-id="c93bf-116">To deploy Enterprise Voice at a central site, continue reading the topics in this section.</span></span> <span data-ttu-id="c93bf-117">Pour déployer Enterprise Voice sur un site de succursale, passez à la partie <A href="lync-server-2013-deploying-branch-sites.md">déploiement de sites de succursales dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="c93bf-117">To deploy Enterprise Voice at a branch site, skip to <A href="lync-server-2013-deploying-branch-sites.md">Deploying branch sites in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="c93bf-118">Cette section comprend des procédures pour les déploiements dans lesquels un serveur de médiation est colocalisé sur chaque serveur frontal ou serveur Standard Edition, comme recommandé, ainsi que pour les déploiements avec un pool de serveurs de médiation autonome.</span><span class="sxs-lookup"><span data-stu-id="c93bf-118">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="c93bf-119">Vous pouvez ignorer le contenu suivant si vous avez utilisé le générateur de topologie pour définir et publier une topologie qui collocates un serveur de médiation sur chaque serveur frontal ou serveur Standard Edition, car l’Assistant déploiement a déjà installé automatiquement les fichiers pour Serveur de médiation lors de l’installation de fichiers pour votre pool de serveurs principal ou votre serveur Standard Edition :</span><span class="sxs-lookup"><span data-stu-id="c93bf-119">You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>

  - [<span data-ttu-id="c93bf-120">Configuration des jonctions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-120">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

<span data-ttu-id="c93bf-121">Si vous avez utilisé le générateur de topologie pour définir et publier un serveur de médiation dans un pool autonome, vous pouvez utiliser le contenu suivant :</span><span class="sxs-lookup"><span data-stu-id="c93bf-121">If you used Topology Builder to define and publish a Mediation Server in a stand-alone pool, you can use the following content:</span></span>

  - <span data-ttu-id="c93bf-122">Vérifiez que votre topologie répond aux conditions préalables relatives aux logiciels et aux environnements, comme décrit dans la section [conditions vocales d’entreprise pour Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="c93bf-122">Verify that your topology meets the software and environment prerequisites, as described in [Enterprise Voice prerequisites for Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c93bf-123">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c93bf-123">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="c93bf-124">Configuration requise de Voix Entreprise pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-124">Enterprise Voice prerequisites for Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [<span data-ttu-id="c93bf-125">Déploiement des serveurs de médiation et définition des homologues dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-125">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [<span data-ttu-id="c93bf-126">Configuration des jonctions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-126">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [<span data-ttu-id="c93bf-127">Configuration des plans de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-127">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [<span data-ttu-id="c93bf-128">Configuration des stratégies vocales, des enregistrements d’utilisation RTC et des itinéraires vocaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-128">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [<span data-ttu-id="c93bf-129">Exportation et importation de la configuration du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-129">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="c93bf-130">Test du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-130">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [<span data-ttu-id="c93bf-131">Publier les modifications en attente apportées à la configuration du routage de la voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-131">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="c93bf-132">Déploiement de la messagerie unifiée Exchange locale pour fournir la messagerie vocale Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-132">Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail</span></span>](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [<span data-ttu-id="c93bf-133">Mise à disposition de la messagerie vocale Lync Server 2013 aux utilisateurs sur la messagerie unifiée Exchange hébergée</span><span class="sxs-lookup"><span data-stu-id="c93bf-133">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [<span data-ttu-id="c93bf-134">Configuration de l’intégration locale de Lync Server 2013 à Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c93bf-134">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [<span data-ttu-id="c93bf-135">Déploiement de fonctionnalités avancées d’entreprise voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-135">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [<span data-ttu-id="c93bf-136">À propos des régions réseau, des sites réseau et des sous-réseaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-136">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [<span data-ttu-id="c93bf-137">Créer ou modifier une région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-137">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [<span data-ttu-id="c93bf-138">Création ou modification d’un site réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-138">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [<span data-ttu-id="c93bf-139">Association d’un sous-réseau à un site réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-139">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [<span data-ttu-id="c93bf-140">Configurer le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-140">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)
    
      - [<span data-ttu-id="c93bf-141">Configuration d’Enhanced 9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-141">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [<span data-ttu-id="c93bf-142">Configuration de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-142">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [<span data-ttu-id="c93bf-143">Activer les utilisateurs d’Enterprise Voice dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-143">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c93bf-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c93bf-144">See Also</span></span>


[<span data-ttu-id="c93bf-145">Déploiement de sites de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-145">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)  
[<span data-ttu-id="c93bf-146">Configuration de conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-146">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)  
[<span data-ttu-id="c93bf-147">Configuration du parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-147">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)  
[<span data-ttu-id="c93bf-148">Configuration des annonces pour les numéros non affectés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-148">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[<span data-ttu-id="c93bf-149">Déploiement de la surveillance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c93bf-149">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

