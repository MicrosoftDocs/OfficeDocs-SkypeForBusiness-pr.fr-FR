---
title: Configuration requise et autorisations pour la configuration de conférence rendez-vous
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
ms.openlocfilehash: e6610272c39583b70c1ab20d8271551796f65372
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a><span data-ttu-id="1b236-102">Configuration requise et autorisations pour la configuration de conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b236-102">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b236-103">_**Dernière modification de la rubrique :** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="1b236-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="1b236-104">La fonction de conférence rendez-vous est un composant facultatif de la charge de travail des conférences Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b236-104">Dial-in conferencing is an optional component of the Lync Server 2013 Conferencing workload.</span></span> <span data-ttu-id="1b236-105">Pour pouvoir configurer une conférence rendez-vous, les composants que vous devez installer peuvent être déployés lorsque vous utilisez le générateur de topologie pour concevoir votre topologie, puis configurer votre pool frontal ou votre serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="1b236-105">The components you need to install before you can configure dial-in conferencing are deployed when you use the Topology Builder to design your topology and then set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="1b236-106">Cette rubrique décrit ce que vous devez faire pour pouvoir configurer les conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="1b236-106">This topic describes what you need to have accomplished before you can configure dial-in conferencing.</span></span>

<span data-ttu-id="1b236-107">Cette section suppose que vous avez lu en particulier les sections de planification relatives à la charge de travail des conférences et aux conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="1b236-107">This section assumes that you have read the planning sections related to the Conferencing workload and dial-in conferencing in particular.</span></span>

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a><span data-ttu-id="1b236-108">Conditions préalables à la configuration des conférences rendez-vous</span><span class="sxs-lookup"><span data-stu-id="1b236-108">Dial-in Conferencing Configuration Prerequisites</span></span>

<span data-ttu-id="1b236-109">Les conférences rendez-vous nécessitent les composants Lync Server 2013 suivants :</span><span class="sxs-lookup"><span data-stu-id="1b236-109">Dial-in conferencing requires the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="1b236-110">Service d’application de communications unifiées (UCAS), désigné par *Service d’application*</span><span class="sxs-lookup"><span data-stu-id="1b236-110">Unified Communications Application Service (UCAS) (called the *Application service*)</span></span>

  - <span data-ttu-id="1b236-111">Application Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="1b236-111">Conferencing Attendant application</span></span>

  - <span data-ttu-id="1b236-112">Application d’annonce de conférence</span><span class="sxs-lookup"><span data-stu-id="1b236-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="1b236-113">Page web Paramètres de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="1b236-113">Dial-in Conferencing Settings webpage</span></span>

  - <span data-ttu-id="1b236-114">Au moins un serveur de médiation Lync Server 2013 et au moins une passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="1b236-114">At least one Lync Server 2013 Mediation Server and at least one PSTN gateway</span></span>

<span data-ttu-id="1b236-115">Vous déployez ces composants lorsque vous utilisez le générateur de topologie pour définir et publier votre topologie, puis déployer un pool frontal ou un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="1b236-115">You deploy these components when you use the Topology Builder to define and publish your topology and then deploy a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="1b236-116">Si vous déployez Enterprise Voice, vous devez le déployer avant de configurer la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="1b236-116">If you are deploying Enterprise Voice, you should deploy it before you configure dial-in conferencing.</span></span> <span data-ttu-id="1b236-117">Si vous n’êtes pas le déploiement d’Enterprise Voice, vous pouvez déployer un serveur de médiation et une passerelle de réseau téléphonique commuté (PSTN) lors du déploiement de votre pool frontal ou du serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="1b236-117">If you are not deploying Enterprise Voice, you can deploy a Mediation Server and a public switched telephone network (PSTN) gateway when you deploy your Front End pool or Standard Edition server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="1b236-118">Si vous effectuez une mise à niveau d’Office Communications Server 2007 R2 vers Lync Server 2013, déployez des conférences rendez-vous dans chaque liste que vous envisagez d’utiliser pour héberger des conférences Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b236-118">If you are upgrading from Office Communications Server 2007 R2 to Lync Server 2013, deploy dial-in conferencing in every pool that you plan to use to host Lync Server 2013 conferences.</span></span> <span data-ttu-id="1b236-119">Pour plus d’informations sur la migration des conférences rendez-vous, voir <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">migration d’Office Communications Server 2007 R2 vers Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1b236-119">For details about migrating dial-in conferencing, see <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="1b236-120">Cette section part du principe que vous avez réalisé les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="1b236-120">This section assumes that you have done the following:</span></span>

  - <span data-ttu-id="1b236-121">Appliquez les mises à jour les plus récentes de votre environnement Office Communications Server 2007 R2, si vous effectuez une migration vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b236-121">Applied the latest updates to your Office Communications Server 2007 R2 environment, if you are migrating to Lync Server 2013.</span></span>

  - <span data-ttu-id="1b236-122">Utiliser le générateur de topologie pour concevoir et configurer votre topologie.</span><span class="sxs-lookup"><span data-stu-id="1b236-122">Used Topology Builder to design and configure your topology.</span></span> <span data-ttu-id="1b236-123">Lorsque vous spécifiez la charge de travail de conférence, vous avez sélectionné l’option Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="1b236-123">While specifying the Conferencing workload, you selected the dial-in conferencing option.</span></span> <span data-ttu-id="1b236-124">Pour plus d’informations sur la définition de votre topologie, voir [définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="1b236-124">For details about defining your topology, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="1b236-125">A publié votre topologie et configuré le pool frontal ou un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="1b236-125">Published your topology, and set up the Front End pool or Standard Edition server.</span></span> <span data-ttu-id="1b236-126">Pour plus d’informations sur la publication de la topologie et l’installation de Lync Server 2013, voir [déploiement de Lync server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="1b236-126">For details about publishing the topology and installing Lync Server 2013, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="1b236-127">Lorsque vous installez votre topologie publiée, la page Web des paramètres de conférence rendez-vous est installée sur le serveur frontal ou sur le serveur Standard Edition dans le cadre des services Web.</span><span class="sxs-lookup"><span data-stu-id="1b236-127">When you install your published topology, the Dial-in Conferencing Settings webpage is installed on the Front End Server or Standard Edition server as part of Web Services.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="1b236-128">Si vous modifiez le chemin d’accès du magasin de fichiers dans le générateur de topologie après le déploiement de Lync Server 2013, vous devez redémarrer les applications du surveillant de conférences et de l’annonce de conférence pour utiliser le nouveau chemin.</span><span class="sxs-lookup"><span data-stu-id="1b236-128">If you change the path for the File Store in Topology Builder after you deploy Lync Server 2013, you need to restart the Conferencing Attendant and Conferencing Announcement applications to use the new path.</span></span>

    
    </div>

  - <span data-ttu-id="1b236-129">Voix entreprise déployée.</span><span class="sxs-lookup"><span data-stu-id="1b236-129">Deployed Enterprise Voice.</span></span> <span data-ttu-id="1b236-130">Si vous n’effectuez pas le déploiement d’Enterprise Voice, vous colocalisez un serveur de médiation sur le serveur frontal Enterprise Edition ou le serveur Standard Edition Server, ou vous avez déployé un serveur de médiation autonome et vous avez déployé une passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="1b236-130">If you are not deploying Enterprise Voice, you either collocated a Mediation Server on the Enterprise Edition Front End Server or the Standard Edition server, or you deployed a stand-alone Mediation Server, and you deployed a PSTN gateway.</span></span> <span data-ttu-id="1b236-131">Pour plus d’informations sur le déploiement de voix entreprise, reportez-vous à la rubrique [déploiement d’Enterprise Voice dans Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="1b236-131">For details about deploying Enterprise Voice, see [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span> <span data-ttu-id="1b236-132">Pour plus d’informations sur l’installation d’un serveur de médiation autonome et d’une passerelle RTC, voir [déploiement de serveurs de médiation et définition d’homologues dans Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="1b236-132">For details about installing a stand-alone Mediation Server and PSTN gateway, see [Deploying Mediation Servers and defining peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) in the Deployment documentation.</span></span>

<span data-ttu-id="1b236-133">Le diagramme suivant montre les étapes que vous devez effectuer avant de configurer la Conférence rendez-vous et les étapes que vous devez effectuer pour configurer la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="1b236-133">The following flowchart shows the steps that you must perform before you can configure dial-in conferencing and the steps that you perform to configure dial-in conferencing.</span></span>

<span data-ttu-id="1b236-134">**Déploiement de conférences rendez-vous**</span><span class="sxs-lookup"><span data-stu-id="1b236-134">**Deploying dial-in conferencing**</span></span>

<span data-ttu-id="1b236-135">![Diagramme de déploiement de la Conférence rendez-vous](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Diagramme de déploiement de la Conférence rendez-vous")</span><span class="sxs-lookup"><span data-stu-id="1b236-135">![Dial-in Conferencing Deployment flowchart](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Dial-in Conferencing Deployment flowchart")</span></span>

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a><span data-ttu-id="1b236-136">Autorisations de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="1b236-136">Dial-in Conferencing Permissions</span></span>

<span data-ttu-id="1b236-137">Pour configurer des conférences rendez-vous, vous devez utiliser les outils d’administration suivants :</span><span class="sxs-lookup"><span data-stu-id="1b236-137">To configure dial-in conferencing, you need to use the following administrative tools:</span></span>

  - <span data-ttu-id="1b236-138">Panneau de configuration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b236-138">Lync Server 2013 Control Panel</span></span>

  - <span data-ttu-id="1b236-139">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="1b236-139">Lync Server Management Shell</span></span>

<span data-ttu-id="1b236-140">Les outils d’administration suivants vous permettent de configurer les paramètres de conférence rendez-vous, ainsi que les plans de numérotation, les politiques et d’autres paramètres nécessaires à la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="1b236-140">You use these administrative tools to configure dial-in conferencing settings, and the dial plans, policies, and other settings that dial-in conferencing requires.</span></span>

<span data-ttu-id="1b236-141">La configuration de la Conférence rendez-vous nécessite l’un des rôles d’administration suivants, en fonction de la tâche :</span><span class="sxs-lookup"><span data-stu-id="1b236-141">Configuring dial-in conferencing requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="1b236-142">**CsVoiceAdministrator**   ce rôle d’administrateur peut créer, configurer et gérer les paramètres et les stratégies relatives à la voix.</span><span class="sxs-lookup"><span data-stu-id="1b236-142">**CsVoiceAdministrator**   This administrator role can create, configure, and manage voice-related settings and policies.</span></span>

  - <span data-ttu-id="1b236-143">**CsUserAdministrator**   ce rôle d’administrateur peut activer et désactiver des utilisateurs pour Lync Server et affecter des stratégies existantes, telles que les stratégies de conférences et les stratégies de code confidentiel, aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1b236-143">**CsUserAdministrator**   This administrator role can enable and disable users for Lync Server and assign existing policies, such as conferencing policies and PIN policies, to users.</span></span>

  - <span data-ttu-id="1b236-144">**CsAdministrator**   ce rôle d’administrateur peut effectuer toutes les tâches de CsVoiceAdministrator et de CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1b236-144">**CsAdministrator**   This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1b236-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1b236-145">See Also</span></span>


[<span data-ttu-id="1b236-146">Déploiement d’Enterprise Voice dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b236-146">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

