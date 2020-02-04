---
title: Composants et topologies utilisés pour les conférences dans Lync Server 2013
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
ms.openlocfilehash: db44e7c8430865fcf8138c9b51f6e700ff85dd7b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="86fb7-102">Composants et topologies utilisés pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86fb7-102">Components and topologies for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86fb7-103">_**Dernière modification de la rubrique :** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="86fb7-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="86fb7-104">Lorsque vous sélectionnez l’option conférences dans le générateur de topologie, la Conférence est déployée dans le cadre du serveur frontal ou du serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="86fb7-104">When you select conferencing in Topology Builder, conferencing is deployed as part of the Front End Server or Standard Edition server.</span></span> <span data-ttu-id="86fb7-105">Les conférences rendez-vous et le partage PowerPoint nécessitent des composants et une configuration supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="86fb7-105">Dial-in conferencing and PowerPoint sharing requires additional components and configuration.</span></span> <span data-ttu-id="86fb7-106">Les sections suivantes décrivent les composants et topologies pris en charge pour les conférences Web, les conférences A/V et la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="86fb7-106">The following sections describe the supported components and topologies for web conferencing, A/V conferencing, and dial-in conferencing.</span></span>

<div>

## <a name="supported-components"></a><span data-ttu-id="86fb7-107">Composants pris en charge</span><span class="sxs-lookup"><span data-stu-id="86fb7-107">Supported Components</span></span>

<span data-ttu-id="86fb7-108">Les seuls composants de conférence Web et de conférence A/V requis sont les serveurs front end de votre organisation ou les serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="86fb7-108">The only components web conferencing and A/V conferencing require are your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="86fb7-109">Pour obtenir la liste des configurations matérielles et logicielles requises pour les serveurs frontaux et les serveurs Standard Edition Server, voir [matériel pris en charge pour Lync server 2013](lync-server-2013-supported-hardware.md) et les [logiciels et les infrastructures du serveur sur Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span><span class="sxs-lookup"><span data-stu-id="86fb7-109">For a list of hardware and software requirements for the Front End Servers and Standard Edition servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

<span data-ttu-id="86fb7-110">Lync Server 2013 utilise Office Web Apps et Office Web Apps Server pour gérer le partage et le rendu des présentations PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="86fb7-110">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="86fb7-111">Pour plus d’informations sur l’installation et la configuration d’Office Web Apps Server, reportez-vous à la rubrique [configuration de l’intégration avec Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="86fb7-111">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="86fb7-112">Outre les exigences relatives aux conférences Web et aux conférences audiovisuelles, la Conférence rendez-vous utilise les composants Lync Server 2013 suivants :</span><span class="sxs-lookup"><span data-stu-id="86fb7-112">In addition to the requirements for web conferencing and A/V conferencing, dial-in conferencing uses the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="86fb7-113">\*\*\*\*   Le service d’application de service d’application fournit une plate-forme pour le déploiement, l’hébergement et la gestion des applications de communications unifiées.</span><span class="sxs-lookup"><span data-stu-id="86fb7-113">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications (UC) applications.</span></span> <span data-ttu-id="86fb7-114">Les conférences rendez-vous utilisent deux applications de communications unifiées qui nécessitent le service d’application : le surveillant de conférences et l’annonce de conférence.</span><span class="sxs-lookup"><span data-stu-id="86fb7-114">Dial-in conferencing uses two UC applications that require Application service: Conferencing Attendant and Conferencing Announcement.</span></span> <span data-ttu-id="86fb7-115">Le service d’application est installé et activé par défaut sur chaque serveur frontal d’une grappe frontale et sur tous les serveurs Standard Edition Server lorsque vous déployez une charge de travail de conférence et sélectionnez l’option Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="86fb7-115">Application service is installed and activated by default on every Front End Server in a Front End pool and on every Standard Edition server when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="86fb7-116">\*\*\*\* L’application attendant du surveillant de conférences est une application de communications unifiées qui accepte les appels de réseau téléphonique commuté (RTC), lit les invites et joint les appels à une conférence a/V.   </span><span class="sxs-lookup"><span data-stu-id="86fb7-116">**Conferencing Attendant application**   Conferencing Attendant application is a unified communications application that accepts public switched telephone network (PSTN) calls, plays prompts, and joins the calls to an A/V conference.</span></span> <span data-ttu-id="86fb7-117">L’application de surveillance des conférences est installée et activée par défaut lorsque vous déployez une charge de travail de conférence et sélectionnez l’option Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="86fb7-117">Conferencing Attendant application is installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="86fb7-118">**Annonce**   d’annonce d’annonce d’annonce d’application est une application de communications unifiées qui lit les sons et les invites des participants au RTC sur certaines actions, par exemple lorsque les participants rejoignent ou quittent une conférence, les participants sont en mode muet ou inversement.</span><span class="sxs-lookup"><span data-stu-id="86fb7-118">**Conferencing Announcement application**   Conferencing Announcement application is a unified communications application that plays tones and prompts to PSTN participants on certain actions, such as when participants join or leave a conference, participants are muted or unmuted, someone enters the conference lobby, or the conference is locked or unlocked.</span></span> <span data-ttu-id="86fb7-119">L’application d’annonce de conférence prend également en charge les commandes de double-tonalité (DTMF) sur le clavier du téléphone.</span><span class="sxs-lookup"><span data-stu-id="86fb7-119">Conferencing Announcement application also supports dual-tone multifrequency (DTMF) commands from the phone keypad.</span></span> <span data-ttu-id="86fb7-120">L’application d’annonce de conférences est automatiquement installée et activée par défaut lorsque vous déployez une charge de travail de conférence et sélectionnez l’option Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="86fb7-120">Conferencing Announcement application is automatically installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="86fb7-121">**Page des paramètres de conférence**   rendez-vous la page des paramètres de conférence rendez-vous affiche les numéros de conférence rendez-vous avec les langues disponibles, les informations sur les conférences téléphoniques affectées (c’est-à-dire pour les réunions dont le planning n’a pas besoin d’être planifié) et les commandes DTMF en conférence, et prend en charge la gestion de votre code confidentiel (pin) et des informations</span><span class="sxs-lookup"><span data-stu-id="86fb7-121">**Dial-in Conferencing Settings page**   The Dial-in Conferencing Settings page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="86fb7-122">La page des paramètres de conférence rendez-vous est automatiquement installée dans le cadre des services Web.</span><span class="sxs-lookup"><span data-stu-id="86fb7-122">The Dial-in Conferencing Settings page is automatically installed as part of Web Services.</span></span>

  - <span data-ttu-id="86fb7-123">\*\*\*\*   Les conférences rendez-vous de Lync Server 2013, de médiation Server et de passerelle RTC nécessitent un serveur de médiation pour traduire le signalement (et le média, dans certaines configurations) entre Lync Server 2013 et la passerelle RTC et une passerelle PSTN pour traduire les signaux et les médias entre le serveur de médiation et la passerelle RTC.</span><span class="sxs-lookup"><span data-stu-id="86fb7-123">**Lync Server 2013, Mediation Server and PSTN gateway**   Dial-in conferencing requires a Mediation Server to translate signaling (and media, in some configurations) between Lync Server 2013 and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="86fb7-124">Pour les conférences rendez-vous, vous devez déployer au moins un serveur de médiation et au moins l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="86fb7-124">For dial-in conferencing, you must deploy at least one Mediation Server and at least one of the following:</span></span>
    
      - <span data-ttu-id="86fb7-125">Passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="86fb7-125">PSTN gateway</span></span>
    
      - <span data-ttu-id="86fb7-126">IP-PBX</span><span class="sxs-lookup"><span data-stu-id="86fb7-126">IP-PBX</span></span>
    
      - <span data-ttu-id="86fb7-127">Contrôleur SBC (Session Border Controller) (pour un fournisseur de services de téléphonie Internet sur lequel vous vous connectez en configurant une jonction SIP [Session Initiation Protocol])</span><span class="sxs-lookup"><span data-stu-id="86fb7-127">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86fb7-128">Si vous déployez également Enterprise Voice, les passerelles RTC et serveur de médiation font partie du déploiement voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="86fb7-128">If you are also deploying Enterprise Voice, Mediation Server and PSTN gateways are part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="86fb7-129">Si vous ne déployez pas l’entreprise voix, vous devez déployer au moins un serveur de médiation et au moins une passerelle RTC, un PBX IP ou un SBC pour la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="86fb7-129">If you are not deploying Enterprise Voice, you need to deploy at least one Mediation Server and at least one PSTN gateway, IP-PBX, or SBC for dial-in conferencing.</span></span>

    
    </div>

  - <span data-ttu-id="86fb7-130">\*\*\*\*   La Banque de fichiers du magasin de fichiers est utilisée pour les fichiers audio de nom enregistrés.</span><span class="sxs-lookup"><span data-stu-id="86fb7-130">**File store**   File store is used for recorded name audio files.</span></span> <span data-ttu-id="86fb7-131">Le magasin de fichiers est un composant standard dans chaque déploiement Entreprise ou Standard.</span><span class="sxs-lookup"><span data-stu-id="86fb7-131">File Store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="86fb7-132">\*\*\*\*   Le magasin utilisateur du Windows Store est utilisé pour stocker les codes confidentiels de Lync Server 2013 des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="86fb7-132">**User store**   User store is used to store user Lync Server 2013 PINs.</span></span> <span data-ttu-id="86fb7-133">Les codes confidentiels sont hachés.</span><span class="sxs-lookup"><span data-stu-id="86fb7-133">PINs are hashed.</span></span> <span data-ttu-id="86fb7-134">Le magasin d’utilisateurs est un composant standard dans chaque déploiement Entreprise ou Standard.</span><span class="sxs-lookup"><span data-stu-id="86fb7-134">The User store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="86fb7-135">**Panneau**   de configuration de Lync Server vous pouvez configurer certains paramètres de connexion à l’aide du panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="86fb7-135">**Lync Server Control Panel**   Some dial-in settings can be configured by using Lync Server Control Panel.</span></span>

  - <span data-ttu-id="86fb7-136">**Lync Server Management Shell**   tous les paramètres de connexion peuvent être configurés à l’aide d’applets de cmdlet Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="86fb7-136">**Lync Server Management Shell**   All dial-in settings can be configured by using Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="86fb7-137">Les applets de contrôle Lync Server Management Shell sont disponibles pour le déploiement, la configuration, l’exécution, le contrôle et la résolution des problèmes liés à l’application du service de conférence et aux conférences.</span><span class="sxs-lookup"><span data-stu-id="86fb7-137">Lync Server Management Shell cmdlets are available for deploying, configuring, running, monitoring, and troubleshooting Conferencing Attendant application and Conferencing Announcement application.</span></span> <span data-ttu-id="86fb7-138">Pour en savoir plus sur les applets de connexion spécifiques, voir documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="86fb7-138">For details about specific cmdlets, see Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="86fb7-139">Topologies prises en charge</span><span class="sxs-lookup"><span data-stu-id="86fb7-139">Supported Topologies</span></span>

<span data-ttu-id="86fb7-140">Dans Lync Server 2013, le serveur exécutant Conferencing services est toujours localisé sur les serveurs front-end ou les serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="86fb7-140">In Lync Server 2013, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="86fb7-141">Pendant votre déploiement initial, le générateur de topologie vous donne la possibilité d’inclure des conférences dans votre topologie.</span><span class="sxs-lookup"><span data-stu-id="86fb7-141">During your initial deployment, Topology Builder gives you the option to include conferencing in your topology.</span></span> <span data-ttu-id="86fb7-142">Vous pouvez également utiliser le générateur de topologie pour ajouter la fonction de conférence à un déploiement existant.</span><span class="sxs-lookup"><span data-stu-id="86fb7-142">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="86fb7-143">Pour plus d’informations, reportez-vous à [définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="86fb7-143">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

<div>

## <a name="dial-in-conferencing-toplogies"></a><span data-ttu-id="86fb7-144">Accès aux conférences Toplogies</span><span class="sxs-lookup"><span data-stu-id="86fb7-144">Dial in Conferencing Toplogies</span></span>

<span data-ttu-id="86fb7-145">Vous pouvez déployer des conférences rendez-vous dans les topologies et configurations suivantes :</span><span class="sxs-lookup"><span data-stu-id="86fb7-145">You can deploy dial-in conferencing in the following topologies and configurations:</span></span>

  - <span data-ttu-id="86fb7-146">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86fb7-146">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="86fb7-147">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="86fb7-147">Lync Server 2013 Enterprise Edition</span></span>

  - <span data-ttu-id="86fb7-148">Avec ou sans Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="86fb7-148">With or without Enterprise Voice</span></span>

<span data-ttu-id="86fb7-149">Vous pouvez déployer une application de service d’application, de surveillant de conférences et d’annonce de conférence dans un site central, mais pas dans un site de filiale.</span><span class="sxs-lookup"><span data-stu-id="86fb7-149">You can deploy Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="86fb7-150">Si vous déployez la Conférence rendez-vous, vous devez la déployer dans chaque liste où vous déployez Lync Server 2013 Conferencing.</span><span class="sxs-lookup"><span data-stu-id="86fb7-150">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="86fb7-151">Il n’est pas nécessaire d’attribuer des numéros d’accès à chaque pool, mais vous devez déployer la fonctionnalité de conférence rendez-vous dans chaque pool.</span><span class="sxs-lookup"><span data-stu-id="86fb7-151">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="86fb7-152">Cette condition prend en charge la fonctionnalité de nom enregistré quand un utilisateur appelle un numéro d’accès à partir d’un pool pour participer à une conférence 2013 Server Lync dans un autre pool.</span><span class="sxs-lookup"><span data-stu-id="86fb7-152">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a><span data-ttu-id="86fb7-153">Topologies prises en charge pour Lync Server 2013 et Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="86fb7-153">Supported Topologies for Lync Server 2013 and Office Web Apps</span></span>

<span data-ttu-id="86fb7-154">Lync Server 2013 fournit les méthodes suivantes pour configurer Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="86fb7-154">Lync Server 2013 provides the following ways to configure Office Web Apps Server.</span></span> <span data-ttu-id="86fb7-155">En fonction de vos besoins, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="86fb7-155">Depending on your needs you can:</span></span>

  - <span data-ttu-id="86fb7-156">**Installez Lync Server 2013 et Office Web Apps Server en local derrière le pare-feu de votre organisation, puis dans la même zone réseau.**</span><span class="sxs-lookup"><span data-stu-id="86fb7-156">**Install both Lync Server 2013 and Office Web Apps Server on-premises behind your organization’s firewall, and in the same network zone.**</span></span> <span data-ttu-id="86fb7-157">Avec cette topologie, l’accès externe à Office Web Apps Server sera fourni par le biais de votre serveur proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="86fb7-157">With this topology, external access to Office Web Apps Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="86fb7-158">Lync Server 2013 et Office Web Apps Server (ou une batterie de serveurs Office Web Apps) sont installés en local et derrière le pare-feu de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="86fb7-158">Both Lync Server 2013 and Office Web Apps Server (or an Office Web Apps Server farm) are installed on-premises and behind your organization's firewall.</span></span> <span data-ttu-id="86fb7-159">Idéalement, vous devez installer Office Web Apps Server dans la même zone réseau que Lync Server.</span><span class="sxs-lookup"><span data-stu-id="86fb7-159">Ideally, you should install Office Web Apps Server in the same network zone as Lync Server.</span></span>
    
    <span data-ttu-id="86fb7-160">Les clients Lync externes peuvent se connecter à Lync Server 2013 et à Office Web Apps Server à l’aide d’un serveur de proxy inverse, qui est un serveur qui accepte les requêtes provenant d’Internet et les transmet au réseau interne.</span><span class="sxs-lookup"><span data-stu-id="86fb7-160">External Lync clients can connect to Lync Server 2013 and to Office Web Apps Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="86fb7-161">(Les clients internes n’ont pas besoin d’utiliser le serveur proxy inverse, car ils peuvent se connecter directement à Office Web Apps Server.) Cette topologie fonctionne de façon optimale si vous souhaitez utiliser une batterie de serveurs Office Web Apps dédiée qui est uniquement utilisée par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86fb7-161">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server farm that is only used by Lync Server 2013.</span></span>

  - <span data-ttu-id="86fb7-162">**Utilisation d’un serveur Office Web Apps déployé en externe**</span><span class="sxs-lookup"><span data-stu-id="86fb7-162">**Using an externally deployed Office Web Apps Server**</span></span>
    
    <span data-ttu-id="86fb7-163">Dans cette topologie, Lync Server 2013 est déployé en local et utilise un serveur Office Web Apps déployé en dehors de la zone réseau de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="86fb7-163">In this topology, Lync Server 2013 is deployed on-premises, and uses an Office Web Apps Server that is deployed outside of Lync Server network zone.</span></span> <span data-ttu-id="86fb7-164">Cela peut se produire lorsqu’Office Web Apps Server est partagé sur plusieurs applications dans l’entreprise et est déployé sur un réseau nécessitant que Lync Server utilise l’interface externe d’Office Web Apps Server et inversement.</span><span class="sxs-lookup"><span data-stu-id="86fb7-164">This may happen when Office Web Apps Server is shared across multiple applications in the corporation and is deployed in a network requiring Lync Server to use the external interface of Office Web Apps Server and vice versa.</span></span>
    
    <span data-ttu-id="86fb7-165">Vous n’avez pas besoin d’installer un serveur proxy inverse ; au lieu de cela, toutes les demandes du serveur Office Web Apps Server vers Lync Server 2013 sont routées via votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="86fb7-165">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server to Lync Server 2013 are routed through your Edge Server.</span></span> <span data-ttu-id="86fb7-166">Votre client interne et vos clients Lync externes se connectent à Office Web Apps Server en utilisant l’URL externe.</span><span class="sxs-lookup"><span data-stu-id="86fb7-166">Both your internal and your external Lync clients connect to Office Web Apps Server using the external URL.</span></span>
    
    <span data-ttu-id="86fb7-167">Si Office Web Apps Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez l’option le **déploiement d’Office Web Apps Server dans un réseau externe (c’est-à-dire le périmètre/Internet)** dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="86fb7-167">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** in Topology Builder.</span></span> <span data-ttu-id="86fb7-168">Pour plus d’informations, voir Configuration de l' [intégration à Office Web Apps Server et Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="86fb7-168">For more details see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="86fb7-169">Indépendamment de la topologie sélectionnée, les ports de pare-feu corrects doivent absolument être ouverts.</span><span class="sxs-lookup"><span data-stu-id="86fb7-169">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="86fb7-170">Vous devez vous assurer que les noms DNS, adresses IP et port ne sont pas bloqués par des pare-feu sur le serveur Office Web Apps, l’équilibrage de charge ou le serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="86fb7-170">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server, the load balancer, or Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="86fb7-171">Une autre option permettant d’offrir un accès externe à Office Web Apps Server consiste à déployer le serveur dans le réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="86fb7-171">Another option for providing external access to Office Web Apps Server is to deploy the server in the perimeter network.</span></span> <span data-ttu-id="86fb7-172">Si vous choisissez de le faire, n’oubliez pas que la configuration d’Office Web Apps Server nécessite que l’ordinateur serveur soit membre de votre domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="86fb7-172">If you elect to do this, keep in mind that Office Web Apps Server setup requires the server computer to be a member of your Active Directory domain.</span></span> <span data-ttu-id="86fb7-173">À moins que votre stratégie réseau autorise la possibilité pour les ordinateurs du réseau périmétrique d’être membres du domaine Active Directory, il est recommandé de ne pas installer le serveur Office Web Apps dans le réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="86fb7-173">Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server in the perimeter network.</span></span> <span data-ttu-id="86fb7-174">Au lieu de cela, vous devez installer Office Web Apps Server sur le réseau interne et fournir l’accès des utilisateurs externes par le biais de votre serveur proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="86fb7-174">Instead, you should install Office Web Apps Server in the internal network and provide external user access through your reverse proxy server.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

