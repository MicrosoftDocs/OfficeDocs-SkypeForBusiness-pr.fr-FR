---
title: Conditions préalables et autorisations pour la configuration de la Conférence rendez-vous
description: Conditions préalables et autorisations pour la configuration de la Conférence rendez-vous.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eced67f33e35c711c4fcd31120480b6d5c2e41ce
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576170"
---
# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a><span data-ttu-id="2b009-103">Conditions préalables et autorisations pour la configuration de la Conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b009-103">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b009-104">_**Dernière modification de la rubrique :** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="2b009-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="2b009-105">La Conférence rendez-vous est un composant facultatif de la charge de travail de conférence Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b009-105">Dial-in conferencing is an optional component of the Lync Server 2013 Conferencing workload.</span></span> <span data-ttu-id="2b009-106">Les composants que vous devez installer avant de pouvoir configurer la Conférence rendez-vous sont déployés lorsque vous utilisez le générateur de topologies pour concevoir votre topologie, puis configurer votre pool frontal ou votre serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2b009-106">The components you need to install before you can configure dial-in conferencing are deployed when you use the Topology Builder to design your topology and then set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="2b009-107">Cette rubrique décrit les étapes à accomplir avant de pouvoir configurer la conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="2b009-107">This topic describes what you need to have accomplished before you can configure dial-in conferencing.</span></span>

<span data-ttu-id="2b009-108">Elle suppose que vous avez pris connaissance des sections de planification liées à la charge de travail Conférence et en particulier à la conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="2b009-108">This section assumes that you have read the planning sections related to the Conferencing workload and dial-in conferencing in particular.</span></span>

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a><span data-ttu-id="2b009-109">Conditions préalables à la configuration de la conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="2b009-109">Dial-in Conferencing Configuration Prerequisites</span></span>

<span data-ttu-id="2b009-110">La Conférence rendez-vous nécessite les composants Lync Server 2013 suivants :</span><span class="sxs-lookup"><span data-stu-id="2b009-110">Dial-in conferencing requires the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="2b009-111">service d’application de communications unifiées (UCAS), désigné par *Service d’application*</span><span class="sxs-lookup"><span data-stu-id="2b009-111">Unified Communications Application Service (UCAS) (called the *Application service*)</span></span>

  - <span data-ttu-id="2b009-112">application Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="2b009-112">Conferencing Attendant application</span></span>

  - <span data-ttu-id="2b009-113">application d’annonce de conférence</span><span class="sxs-lookup"><span data-stu-id="2b009-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="2b009-114">page web Paramètres de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="2b009-114">Dial-in Conferencing Settings webpage</span></span>

  - <span data-ttu-id="2b009-115">Au moins un serveur de médiation Lync Server 2013 et au moins une passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="2b009-115">At least one Lync Server 2013 Mediation Server and at least one PSTN gateway</span></span>

<span data-ttu-id="2b009-116">Vous déployez ces composants lorsque vous utilisez le générateur de topologie pour définir et publier votre topologie, puis déployer un pool frontal ou un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2b009-116">You deploy these components when you use the Topology Builder to define and publish your topology and then deploy a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="2b009-117">Si vous déployez voix entreprise, vous devez la déployer avant de configurer la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="2b009-117">If you are deploying Enterprise Voice, you should deploy it before you configure dial-in conferencing.</span></span> <span data-ttu-id="2b009-118">Si vous ne déployez pas voix entreprise, vous pouvez déployer un serveur de médiation et une passerelle PSTN (réseau téléphonique commuté) lorsque vous déployez votre pool frontal ou votre serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2b009-118">If you are not deploying Enterprise Voice, you can deploy a Mediation Server and a public switched telephone network (PSTN) gateway when you deploy your Front End pool or Standard Edition server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="2b009-119">Si vous effectuez une mise à niveau d’Office Communications Server 2007 R2 vers Lync Server 2013, déployez la Conférence rendez-vous dans chaque pool que vous envisagez d’utiliser pour héberger les conférences Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b009-119">If you are upgrading from Office Communications Server 2007 R2 to Lync Server 2013, deploy dial-in conferencing in every pool that you plan to use to host Lync Server 2013 conferences.</span></span> <span data-ttu-id="2b009-120">Pour plus d’informations sur la migration des conférences rendez-vous, consultez la rubrique <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2b009-120">For details about migrating dial-in conferencing, see <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="2b009-121">Cette section suppose que vous avez :</span><span class="sxs-lookup"><span data-stu-id="2b009-121">This section assumes that you have done the following:</span></span>

  - <span data-ttu-id="2b009-122">Application des dernières mises à jour à votre environnement Office Communications Server 2007 R2, si vous effectuez une migration vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b009-122">Applied the latest updates to your Office Communications Server 2007 R2 environment, if you are migrating to Lync Server 2013.</span></span>

  - <span data-ttu-id="2b009-123">Utilisation du générateur de topologies pour concevoir et configurer votre topologie.</span><span class="sxs-lookup"><span data-stu-id="2b009-123">Used Topology Builder to design and configure your topology.</span></span> <span data-ttu-id="2b009-124">lors de la spécification de votre charge de travail Conférence, vous avez sélectionné l’option de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="2b009-124">While specifying the Conferencing workload, you selected the dial-in conferencing option.</span></span> <span data-ttu-id="2b009-125">Pour plus d’informations sur la définition de votre topologie, reportez-vous à la rubrique [Defining and Configuring the Topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="2b009-125">For details about defining your topology, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="2b009-126">publié votre topologie et configuré le pool frontal ou le serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="2b009-126">Published your topology, and set up the Front End pool or Standard Edition server.</span></span> <span data-ttu-id="2b009-127">Pour plus d’informations sur la publication de la topologie et l’installation de Lync Server 2013, voir [Deploying Lync server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="2b009-127">For details about publishing the topology and installing Lync Server 2013, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="2b009-128">Lorsque vous installez votre topologie publiée, la page web Paramètres de conférence rendez-vous est installée sur le serveur frontal ou le serveur Standard Edition Server dans le cadre des services web.</span><span class="sxs-lookup"><span data-stu-id="2b009-128">When you install your published topology, the Dial-in Conferencing Settings webpage is installed on the Front End Server or Standard Edition server as part of Web Services.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="2b009-129">Si vous modifiez le chemin d’accès du magasin de fichiers dans le générateur de topologie après avoir déployé Lync Server 2013, vous devez redémarrer les applications de surveillance de conférence et d’annonce de conférence pour utiliser le nouveau chemin d’accès.</span><span class="sxs-lookup"><span data-stu-id="2b009-129">If you change the path for the File Store in Topology Builder after you deploy Lync Server 2013, you need to restart the Conferencing Attendant and Conferencing Announcement applications to use the new path.</span></span>

    
    </div>

  - <span data-ttu-id="2b009-130">Voix entreprise déployée.</span><span class="sxs-lookup"><span data-stu-id="2b009-130">Deployed Enterprise Voice.</span></span> <span data-ttu-id="2b009-131">Si vous ne déployez pas voix entreprise, vous avez colocalisé un serveur de médiation sur le serveur frontal Enterprise Edition ou le serveur Standard Edition, ou vous avez déployé un serveur de médiation autonome et vous avez déployé une passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="2b009-131">If you are not deploying Enterprise Voice, you either collocated a Mediation Server on the Enterprise Edition Front End Server or the Standard Edition server, or you deployed a stand-alone Mediation Server, and you deployed a PSTN gateway.</span></span> <span data-ttu-id="2b009-132">Pour plus d’informations sur le déploiement de voix entreprise, reportez-vous à la rubrique [déploiement de voix entreprise dans Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="2b009-132">For details about deploying Enterprise Voice, see [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span> <span data-ttu-id="2b009-133">Pour plus d’informations sur l’installation d’un serveur de médiation autonome et d’une passerelle PSTN, voir [Deploying Mediation Servers and Defining Peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="2b009-133">For details about installing a stand-alone Mediation Server and PSTN gateway, see [Deploying Mediation Servers and defining peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) in the Deployment documentation.</span></span>

<span data-ttu-id="2b009-134">Le graphique suivant présente les étapes à effectuer avant de pouvoir configurer la conférence rendez-vous, ainsi que celles permettant de configurer la conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="2b009-134">The following flowchart shows the steps that you must perform before you can configure dial-in conferencing and the steps that you perform to configure dial-in conferencing.</span></span>

<span data-ttu-id="2b009-135">**Déploiement de la conférence rendez-vous**</span><span class="sxs-lookup"><span data-stu-id="2b009-135">**Deploying dial-in conferencing**</span></span>

<span data-ttu-id="2b009-136">![Organigramme de déploiement de conférence rendez-vous](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Organigramme de déploiement de conférence rendez-vous")</span><span class="sxs-lookup"><span data-stu-id="2b009-136">![Dial-in Conferencing Deployment flowchart](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Dial-in Conferencing Deployment flowchart")</span></span>

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a><span data-ttu-id="2b009-137">Autorisations de la conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="2b009-137">Dial-in Conferencing Permissions</span></span>

<span data-ttu-id="2b009-138">Pour configurer la conférence rendez-vous, vous devez utiliser les outils d’administration suivants :</span><span class="sxs-lookup"><span data-stu-id="2b009-138">To configure dial-in conferencing, you need to use the following administrative tools:</span></span>

  - <span data-ttu-id="2b009-139">Panneau de configuration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b009-139">Lync Server 2013 Control Panel</span></span>

  - <span data-ttu-id="2b009-140">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="2b009-140">Lync Server Management Shell</span></span>

<span data-ttu-id="2b009-141">Ces outils permettent de configurer les paramètres de conférence rendez-vous ainsi que les plans de numérotation, les stratégies et les autres paramètres nécessaires à la conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="2b009-141">You use these administrative tools to configure dial-in conferencing settings, and the dial plans, policies, and other settings that dial-in conferencing requires.</span></span>

<span data-ttu-id="2b009-142">La configuration de la conférence rendez-vous nécessite l’un des rôles administratifs suivants, selon la tâche :</span><span class="sxs-lookup"><span data-stu-id="2b009-142">Configuring dial-in conferencing requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="2b009-143">**CsVoiceAdministrator**     Ce rôle d’administrateur permet de créer, configurer et gérer les stratégies et les paramètres liés à la voix.</span><span class="sxs-lookup"><span data-stu-id="2b009-143">**CsVoiceAdministrator**   This administrator role can create, configure, and manage voice-related settings and policies.</span></span>

  - <span data-ttu-id="2b009-144">**CsUserAdministrator**     Ce rôle d’administrateur permet d’activer et de désactiver des utilisateurs pour Lync Server et d’affecter des stratégies existantes, telles que des stratégies de conférence et des stratégies de code confidentiel, aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2b009-144">**CsUserAdministrator**   This administrator role can enable and disable users for Lync Server and assign existing policies, such as conferencing policies and PIN policies, to users.</span></span>

  - <span data-ttu-id="2b009-145">**CsAdministrator**     Ce rôle d’administrateur peut effectuer toutes les tâches de CsVoiceAdministrator et de CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2b009-145">**CsAdministrator**   This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b009-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2b009-146">See Also</span></span>


[<span data-ttu-id="2b009-147">Déploiement de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b009-147">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

