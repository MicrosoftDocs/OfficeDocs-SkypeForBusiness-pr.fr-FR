---
title: Composants et topologies Lync Server 2013 pour les conférences
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d14c12ad1e28dc2a40fed5b19b5928a5bedc069
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="2b076-102">Composants et topologies pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b076-102">Components and topologies for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b076-103">_**Dernière modification de la rubrique :** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="2b076-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="2b076-104">Lorsque vous sélectionnez Conférence dans le générateur de topologie, la fonctionnalité de conférence est déployée dans le cadre du serveur frontal ou du serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2b076-104">When you select conferencing in Topology Builder, conferencing is deployed as part of the Front End Server or Standard Edition server.</span></span> <span data-ttu-id="2b076-105">La Conférence rendez-vous et le partage PowerPoint nécessitent des composants et une configuration supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="2b076-105">Dial-in conferencing and PowerPoint sharing requires additional components and configuration.</span></span> <span data-ttu-id="2b076-106">Les sections suivantes décrivent les composants et topologies pris en charge pour la conférence Web, la conférence A/V et la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="2b076-106">The following sections describe the supported components and topologies for web conferencing, A/V conferencing, and dial-in conferencing.</span></span>

<div>

## <a name="supported-components"></a><span data-ttu-id="2b076-107">Composants pris en charge</span><span class="sxs-lookup"><span data-stu-id="2b076-107">Supported Components</span></span>

<span data-ttu-id="2b076-108">Les seuls composants conférence Web et conférence A/V requis sont les serveurs frontaux ou les serveurs Standard Edition de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2b076-108">The only components web conferencing and A/V conferencing require are your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="2b076-109">Pour obtenir la liste des configurations matérielle et logicielle requises pour les serveurs frontaux et les serveurs Standard Edition, reportez-vous à la rubrique Hardware Supported [for Lync server 2013](lync-server-2013-supported-hardware.md) and [Server Software and Infrastructure Support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span><span class="sxs-lookup"><span data-stu-id="2b076-109">For a list of hardware and software requirements for the Front End Servers and Standard Edition servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

<span data-ttu-id="2b076-110">Lync Server 2013 utilise Office Web Apps et Office Web Apps Server pour gérer le partage et le rendu des présentations PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="2b076-110">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="2b076-111">Pour plus d’informations sur l’installation et la configuration d’Office Web Apps Server, voir Configuration de l' [intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="2b076-111">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="2b076-112">Outre la configuration requise pour la conférence Web et la conférence A/V, la Conférence rendez-vous utilise les composants Lync Server 2013 suivants :</span><span class="sxs-lookup"><span data-stu-id="2b076-112">In addition to the requirements for web conferencing and A/V conferencing, dial-in conferencing uses the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="2b076-113">**Application service**   application service fournit une plateforme pour le déploiement, l’hébergement et la gestion des applications de communications unifiées.</span><span class="sxs-lookup"><span data-stu-id="2b076-113">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications (UC) applications.</span></span> <span data-ttu-id="2b076-114">La Conférence rendez-vous utilise deux applications de communications unifiées qui nécessitent le service d’application : annonce du surveillant de conférence et de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="2b076-114">Dial-in conferencing uses two UC applications that require Application service: Conferencing Attendant and Conferencing Announcement.</span></span> <span data-ttu-id="2b076-115">Le service d’application est installé et activé par défaut sur chaque serveur frontal dans un pool frontal et sur chaque serveur Standard Edition Server lorsque vous déployez une charge de travail Conférence et sélectionnez l’option de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="2b076-115">Application service is installed and activated by default on every Front End Server in a Front End pool and on every Standard Edition server when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="2b076-116">\*\*\*\*   L’application de surveillance de conférence d’application du service de conférence est une application de communications unifiées qui accepte les appels PSTN (réseau téléphonique commuté), lance des invites et joint les appels à une conférence a/V.</span><span class="sxs-lookup"><span data-stu-id="2b076-116">**Conferencing Attendant application**   Conferencing Attendant application is a unified communications application that accepts public switched telephone network (PSTN) calls, plays prompts, and joins the calls to an A/V conference.</span></span> <span data-ttu-id="2b076-117">L’application de surveillance de conférence est installée et activée par défaut lorsque vous déployez une charge de travail de conférence et sélectionnez l’option Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="2b076-117">Conferencing Attendant application is installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="2b076-118">**Annonce de conférence**   l’application d’annonce de conférence d’applications est une application de communications unifiées qui diffuse des tonalités et des invites aux participants PSTN sur certaines actions, comme lorsque les participants rejoignent ou quittent une conférence, les participants sont activés ou désactivés, une personne entre dans la salle d’attente ou la Conférence est verrouillée ou déverrouillée.</span><span class="sxs-lookup"><span data-stu-id="2b076-118">**Conferencing Announcement application**   Conferencing Announcement application is a unified communications application that plays tones and prompts to PSTN participants on certain actions, such as when participants join or leave a conference, participants are muted or unmuted, someone enters the conference lobby, or the conference is locked or unlocked.</span></span> <span data-ttu-id="2b076-119">L’application d’annonce de conférence prend également en charge les commandes de numérotation en fréquences vocales (DTMF) à partir du clavier du téléphone.</span><span class="sxs-lookup"><span data-stu-id="2b076-119">Conferencing Announcement application also supports dual-tone multifrequency (DTMF) commands from the phone keypad.</span></span> <span data-ttu-id="2b076-120">L’application d’annonce de conférence est automatiquement installée et activée par défaut lorsque vous déployez une charge de travail de conférence et sélectionnez l’option Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="2b076-120">Conferencing Announcement application is automatically installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="2b076-121">**Page Paramètres de conférence**   rendez-vous la page Paramètres de conférence rendez-vous affiche les numéros de conférence rendez-vous avec leurs langues disponibles, les informations de conférence affectées (c’est-à-dire pour les réunions qui n’ont pas besoin d’être planifiées) et les contrôles DTMF de conférence, et prend en charge la gestion des informations sur les conférences et les numéros de conférence associés.</span><span class="sxs-lookup"><span data-stu-id="2b076-121">**Dial-in Conferencing Settings page**   The Dial-in Conferencing Settings page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="2b076-122">La page Paramètres de conférence rendez-vous est automatiquement installée dans le cadre des services Web.</span><span class="sxs-lookup"><span data-stu-id="2b076-122">The Dial-in Conferencing Settings page is automatically installed as part of Web Services.</span></span>

  - <span data-ttu-id="2b076-123">**Lync Server 2013, serveur de médiation et**   Conférence rendez-vous de passerelle PSTN nécessite un serveur de médiation pour traduire la signalisation (et les médias, dans certaines configurations) entre Lync Server 2013 et la passerelle PSTN, ainsi qu’une passerelle PSTN pour traduire la signalisation et les médias entre le serveur de médiation et la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="2b076-123">**Lync Server 2013, Mediation Server and PSTN gateway**   Dial-in conferencing requires a Mediation Server to translate signaling (and media, in some configurations) between Lync Server 2013 and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="2b076-124">Pour la Conférence rendez-vous, vous devez déployer au moins un serveur de médiation et au moins l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="2b076-124">For dial-in conferencing, you must deploy at least one Mediation Server and at least one of the following:</span></span>
    
      - <span data-ttu-id="2b076-125">Passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="2b076-125">PSTN gateway</span></span>
    
      - <span data-ttu-id="2b076-126">IP-PBX</span><span class="sxs-lookup"><span data-stu-id="2b076-126">IP-PBX</span></span>
    
      - <span data-ttu-id="2b076-127">Contrôleur de frontière de session (SBC) (pour un fournisseur de services de téléphonie Internet auquel vous vous connectez en configurant une jonction SIP)</span><span class="sxs-lookup"><span data-stu-id="2b076-127">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2b076-128">Si vous déployez également voix entreprise, le serveur de médiation et les passerelles RTC font partie du déploiement voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="2b076-128">If you are also deploying Enterprise Voice, Mediation Server and PSTN gateways are part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="2b076-129">Si vous déployez pas Voix Entreprise, vous devez déployer au moins un serveur de médiation et une passerelle PSTN, un système IP-PBX ou un contrôleur de frontière de session pour la conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="2b076-129">If you are not deploying Enterprise Voice, you need to deploy at least one Mediation Server and at least one PSTN gateway, IP-PBX, or SBC for dial-in conferencing.</span></span>

    
    </div>

  - <span data-ttu-id="2b076-130">\*\*\*\*   Le magasin de fichiers du magasin de fichiers est utilisé pour les fichiers audio de nom enregistrés.</span><span class="sxs-lookup"><span data-stu-id="2b076-130">**File store**   File store is used for recorded name audio files.</span></span> <span data-ttu-id="2b076-131">Le magasin de fichiers est un composant standard dans chaque déploiement Enterprise Edition ou Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2b076-131">File Store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="2b076-132">\*\*\*\*   Le magasin d’utilisateurs du magasin d’utilisateurs est utilisé pour stocker les codes confidentiels de l’utilisateur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b076-132">**User store**   User store is used to store user Lync Server 2013 PINs.</span></span> <span data-ttu-id="2b076-133">Les codes confidentiels sont hachés.</span><span class="sxs-lookup"><span data-stu-id="2b076-133">PINs are hashed.</span></span> <span data-ttu-id="2b076-134">Le magasin d’utilisateurs est un composant standard dans chaque déploiement Enterprise Edition ou Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2b076-134">The User store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="2b076-135">**Panneau de configuration Lync Server**   certains paramètres de rendez-vous peuvent être configurés à l’aide du panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b076-135">**Lync Server Control Panel**   Some dial-in settings can be configured by using Lync Server Control Panel.</span></span>

  - <span data-ttu-id="2b076-136">**Lync Server Management Shell**   tous les paramètres de rendez-vous peuvent être configurés à l’aide des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2b076-136">**Lync Server Management Shell**   All dial-in settings can be configured by using Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="2b076-137">Les applets de commande Lync Server Management Shell sont disponibles pour le déploiement, la configuration, l’exécution, la surveillance et le dépannage de l’application de surveillance de conférence et de l’application de conférence.</span><span class="sxs-lookup"><span data-stu-id="2b076-137">Lync Server Management Shell cmdlets are available for deploying, configuring, running, monitoring, and troubleshooting Conferencing Attendant application and Conferencing Announcement application.</span></span> <span data-ttu-id="2b076-138">Pour plus d’informations sur les cmdlets spécifiques, reportez-vous à la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2b076-138">For details about specific cmdlets, see Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="2b076-139">Topologies prises en charge</span><span class="sxs-lookup"><span data-stu-id="2b076-139">Supported Topologies</span></span>

<span data-ttu-id="2b076-140">Dans Lync Server 2013, le serveur qui exécute les services de conférence est toujours colocalisé avec les serveurs frontaux ou les serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2b076-140">In Lync Server 2013, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="2b076-141">Lors du déploiement initial, le générateur de topologie vous offre la possibilité d’inclure des conférences dans votre topologie.</span><span class="sxs-lookup"><span data-stu-id="2b076-141">During your initial deployment, Topology Builder gives you the option to include conferencing in your topology.</span></span> <span data-ttu-id="2b076-142">Vous pouvez également utiliser le générateur de topologie pour ajouter des conférences à un déploiement existant.</span><span class="sxs-lookup"><span data-stu-id="2b076-142">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="2b076-143">Pour plus d’informations, reportez-vous à [la rubrique définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="2b076-143">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

<div>

## <a name="dial-in-conferencing-toplogies"></a><span data-ttu-id="2b076-144">Topologies de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="2b076-144">Dial in Conferencing Toplogies</span></span>

<span data-ttu-id="2b076-145">Vous pouvez déployer la Conférence rendez-vous dans les topologies et configurations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2b076-145">You can deploy dial-in conferencing in the following topologies and configurations:</span></span>

  - <span data-ttu-id="2b076-146">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="2b076-146">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="2b076-147">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="2b076-147">Lync Server 2013 Enterprise Edition</span></span>

  - <span data-ttu-id="2b076-148">Avec ou sans voix entreprise</span><span class="sxs-lookup"><span data-stu-id="2b076-148">With or without Enterprise Voice</span></span>

<span data-ttu-id="2b076-149">Vous pouvez déployer une application de service d’applications, de surveillance de conférence et d’annonce de conférence dans un site central, mais pas dans un site de succursale.</span><span class="sxs-lookup"><span data-stu-id="2b076-149">You can deploy Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b076-150">Si vous déployez la Conférence rendez-vous, vous devez la déployer dans tous les pools où vous déployez les conférences Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b076-150">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="2b076-151">Vous n’avez pas besoin d’attribuer des numéros d’accès dans chaque pool, mais vous devez déployer la fonctionnalité de conférence rendez-vous dans chaque pool.</span><span class="sxs-lookup"><span data-stu-id="2b076-151">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="2b076-152">Cette exigence prend en charge la fonctionnalité de nom enregistré lorsqu’un utilisateur appelle un numéro d’accès à partir d’un pool pour joindre une conférence Lync Server 2013 dans un autre pool.</span><span class="sxs-lookup"><span data-stu-id="2b076-152">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a><span data-ttu-id="2b076-153">Topologies prises en charge pour Lync Server 2013 et Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="2b076-153">Supported Topologies for Lync Server 2013 and Office Web Apps</span></span>

<span data-ttu-id="2b076-154">Lync Server 2013 fournit les méthodes suivantes pour configurer Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="2b076-154">Lync Server 2013 provides the following ways to configure Office Web Apps Server.</span></span> <span data-ttu-id="2b076-155">En fonction de vos besoins, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="2b076-155">Depending on your needs you can:</span></span>

  - <span data-ttu-id="2b076-156">**Installez Lync Server 2013 et Office Web Apps Server sur site derrière le pare-feu de votre organisation et dans la même zone réseau.**</span><span class="sxs-lookup"><span data-stu-id="2b076-156">**Install both Lync Server 2013 and Office Web Apps Server on-premises behind your organization’s firewall, and in the same network zone.**</span></span> <span data-ttu-id="2b076-157">Avec cette topologie, l’accès externe au serveur Office Web Apps Server sera fourni par le biais de votre serveur proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="2b076-157">With this topology, external access to Office Web Apps Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="2b076-158">Lync Server 2013 et Office Web Apps Server (ou une batterie Office Web Apps Server) sont installés sur site et derrière le pare-feu de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2b076-158">Both Lync Server 2013 and Office Web Apps Server (or an Office Web Apps Server farm) are installed on-premises and behind your organization's firewall.</span></span> <span data-ttu-id="2b076-159">Idéalement, vous devez installer Office Web Apps Server dans la même zone de réseau que Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b076-159">Ideally, you should install Office Web Apps Server in the same network zone as Lync Server.</span></span>
    
    <span data-ttu-id="2b076-160">Les clients Lync externes peuvent se connecter à Lync Server 2013 et à Office Web Apps Server à l’aide d’un serveur proxy inverse, qui est un serveur qui prend des demandes en provenance d’Internet et les transmet au réseau interne.</span><span class="sxs-lookup"><span data-stu-id="2b076-160">External Lync clients can connect to Lync Server 2013 and to Office Web Apps Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="2b076-161">(Les clients internes n’ont pas besoin d’utiliser le serveur proxy inverse, car ils peuvent se connecter directement à Office Web Apps Server.) Cette topologie est idéale si vous voulez utiliser une batterie Office Web Apps Server dédiée qui est utilisée uniquement par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b076-161">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server farm that is only used by Lync Server 2013.</span></span>

  - <span data-ttu-id="2b076-162">**Utilisation d’un serveur Office Web Apps Server déployé en externe**</span><span class="sxs-lookup"><span data-stu-id="2b076-162">**Using an externally deployed Office Web Apps Server**</span></span>
    
    <span data-ttu-id="2b076-163">Dans cette topologie, Lync Server 2013 est déployé localement et utilise un serveur Office Web Apps Server déployé à l’extérieur de la zone réseau Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b076-163">In this topology, Lync Server 2013 is deployed on-premises, and uses an Office Web Apps Server that is deployed outside of Lync Server network zone.</span></span> <span data-ttu-id="2b076-164">Cela peut se produire lorsque Office Web Apps Server est partagé entre plusieurs applications au sein de l’entreprise et déployé sur un réseau qui exige que Lync Server utilise l’interface externe d’Office Web Apps Server et inversement.</span><span class="sxs-lookup"><span data-stu-id="2b076-164">This may happen when Office Web Apps Server is shared across multiple applications in the corporation and is deployed in a network requiring Lync Server to use the external interface of Office Web Apps Server and vice versa.</span></span>
    
    <span data-ttu-id="2b076-165">Il n’est pas nécessaire d’installer un serveur proxy inverse ; au lieu de cela, toutes les demandes du serveur Office Web Apps Server vers Lync Server 2013 sont acheminées via votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="2b076-165">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server to Lync Server 2013 are routed through your Edge Server.</span></span> <span data-ttu-id="2b076-166">Vos clients Lync internes et externes se connectent à Office Web Apps Server à l’aide de l’URL externe.</span><span class="sxs-lookup"><span data-stu-id="2b076-166">Both your internal and your external Lync clients connect to Office Web Apps Server using the external URL.</span></span>
    
    <span data-ttu-id="2b076-167">Si le serveur Office Web Apps Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez l’option le **serveur Office Web Apps Server est déployé sur un réseau externe (périmètre/Internet)** dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="2b076-167">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** in Topology Builder.</span></span> <span data-ttu-id="2b076-168">Pour plus d’informations, consultez la rubrique Configuration de l' [intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="2b076-168">For more details see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="2b076-169">Quelle que soit la topologie que vous sélectionnez, il est essentiel que les ports de pare-feu appropriés soient ouverts.</span><span class="sxs-lookup"><span data-stu-id="2b076-169">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="2b076-170">Vous devez vous assurer que les noms DNS, les adresses IP et les ports ne sont pas bloqués par des pare-feu sur le serveur Office Web Apps Server, l’équilibreur de charge ou Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b076-170">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server, the load balancer, or Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b076-171">Une autre option permettant de fournir un accès externe au serveur Office Web Apps Server consiste à déployer le serveur dans le réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="2b076-171">Another option for providing external access to Office Web Apps Server is to deploy the server in the perimeter network.</span></span> <span data-ttu-id="2b076-172">Si vous choisissez de le faire, gardez à l’esprit que le programme d’installation d’Office Web Apps Server requiert que l’ordinateur serveur soit membre de votre domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2b076-172">If you elect to do this, keep in mind that Office Web Apps Server setup requires the server computer to be a member of your Active Directory domain.</span></span> <span data-ttu-id="2b076-173">À moins que votre stratégie réseau ne permette aux ordinateurs du réseau de périmètre d’être des membres du domaine Active Directory, il est recommandé de ne pas installer Office Web Apps Server dans le réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="2b076-173">Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server in the perimeter network.</span></span> <span data-ttu-id="2b076-174">Au lieu de cela, vous devez installer Office Web Apps Server dans le réseau interne et fournir l’accès des utilisateurs externes par le biais de votre serveur proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="2b076-174">Instead, you should install Office Web Apps Server in the internal network and provide external user access through your reverse proxy server.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

