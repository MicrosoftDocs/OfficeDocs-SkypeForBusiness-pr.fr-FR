---
title: Vue d’ensemble des fonctionnalités (outil de planification)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/6/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: Outil de planification Skype Entreprise Server 2015
ms.openlocfilehash: 3aa259314d8a92142cf37dcd3611773490248e02
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834784"
---
# <a name="feature-overview-planning-tool"></a><span data-ttu-id="0baa6-103">Vue d’ensemble des fonctionnalités (outil de planification)</span><span class="sxs-lookup"><span data-stu-id="0baa6-103">Feature Overview (Planning Tool)</span></span>
 
<span data-ttu-id="0baa6-104">Outil de planification Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="0baa6-104">Skype for Business Server 2015 Planning Tool</span></span>
  
<span data-ttu-id="0baa6-105">Vous pouvez utiliser la page **Sites centraux** de l’outil de planification pour concevoir le déploiement de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="0baa6-105">You can use the **Central Sites** page of the Planning Tool to design the Skype for Business Server deployment.</span></span> <span data-ttu-id="0baa6-106">Vous pouvez créer deux déploiements centralisés ou distribués.</span><span class="sxs-lookup"><span data-stu-id="0baa6-106">You can create two either a centralized or distributed deployment.</span></span> <span data-ttu-id="0baa6-107">Un déploiement centralisé ne possède qu’un seul site central, qui contient tous les utilisateurs Skype Entreprise de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0baa6-107">A centralized deployment only has one central site, which homes all Skype for Business users in your organization.</span></span> <span data-ttu-id="0baa6-108">Un déploiement distribué possède plusieurs sites centraux.</span><span class="sxs-lookup"><span data-stu-id="0baa6-108">A distributed deployment has more than one central site.</span></span> <span data-ttu-id="0baa6-109">Si vous déployez Skype Entreprise Server sur plusieurs sites centraux, vous entrez le nombre d’utilisateurs sur chaque site central dans l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="0baa6-109">If you deploy Skype for Business Server at multiple central sites, then you will enter the number of users at each central site in the Planning Tool.</span></span>
  
<span data-ttu-id="0baa6-110">Pour terminer la définition du site central, vous devez d’abord fournir les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0baa6-110">To complete the definition of the central site, you first need to provide the following information:</span></span>
  
- <span data-ttu-id="0baa6-111">**Nom du site** Entrez le nom du site central.</span><span class="sxs-lookup"><span data-stu-id="0baa6-111">**Site Name** Enter the name of the Central Site.</span></span>
    
- <span data-ttu-id="0baa6-112">**Nombre d’utilisateurs** Entrez le nombre d’utilisateurs, y compris les utilisateurs des sites de succursale qui sont homed into the central site.</span><span class="sxs-lookup"><span data-stu-id="0baa6-112">**Number of Users** Enter the number of users, including users at branch sites who are homed into the central site.</span></span>
    
- <span data-ttu-id="0baa6-113">**Utilisateurs d’accueil cloud** Entrez le nombre d’utilisateurs qui sont homed into the central site from Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="0baa6-113">**Cloud Homed Users** Enter the number of users that are homed into the central site from Skype for Business Online.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0baa6-114">Cet outil ne sera pas mis à jour pour Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0baa6-114">This tool will not be updated for Skype for Business Server 2019.</span></span>

## <a name="ui-elements"></a><span data-ttu-id="0baa6-115">Éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="0baa6-115">UI Elements</span></span>

<span data-ttu-id="0baa6-116">Les autres éléments ont été remplis avec les réponses que  vous avez fournies aux questions présentées dans l’Assistant De mise en service, ou, si vous avez ignoré l’Assistant, automatiquement rempli par l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="0baa6-116">The remaining elements have either been populated with the answers you provided to the questions presented in the **Get Started** wizard, or, if you skipped the wizard, automatically populated by the planning tool.</span></span>
  
### <a name="online-collaboration"></a><span data-ttu-id="0baa6-117">Collaboration en ligne</span><span class="sxs-lookup"><span data-stu-id="0baa6-117">Online Collaboration</span></span>

 <span data-ttu-id="0baa6-118">**La collaboration en** ligne contient les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="0baa6-118">**Online Collaboration** contains the following options:</span></span>
  
- <span data-ttu-id="0baa6-119">**Messagerie instantanée et présence**</span><span class="sxs-lookup"><span data-stu-id="0baa6-119">**IM and Presence**</span></span>
    
    <span data-ttu-id="0baa6-120">La messagerie instantanée permet aux utilisateurs de communiquer les uns avec les autres en temps réel sur leurs ordinateurs à l’aide de messages texte.</span><span class="sxs-lookup"><span data-stu-id="0baa6-120">Instant Messaging (IM) enables users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="0baa6-121">Les sessions de messagerie unifiée à deux ou à plusieurs personnes sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="0baa6-121">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="0baa6-122">La présence fournit des informations aux utilisateurs sur l’état d’autres personnes sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="0baa6-122">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="0baa6-123">Le statut de présence d’un utilisateur fournit des informations pour aider d’autres personnes à déterminer si l’utilisateur est en ligne et comment contacter au mieux l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0baa6-123">A user's presence status provides information to help others determine whether the user is online and how to best contact the user.</span></span> <span data-ttu-id="0baa6-124">Par exemple, il est préférable de contacter un utilisateur qui se trouve dans une réunion par courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="0baa6-124">For example, a user who is in a meeting is best contacted by email.</span></span>
    
- <span data-ttu-id="0baa6-125">**Conférence audio et vidéo**</span><span class="sxs-lookup"><span data-stu-id="0baa6-125">**Audio and Video Conferencing**</span></span>
    
    <span data-ttu-id="0baa6-126">La conférence audio/vidéo (A/V) permet des conférences audio et vidéo en temps réel.</span><span class="sxs-lookup"><span data-stu-id="0baa6-126">Audio/Video (A/V) conferencing enables real-time audio and video conferences.</span></span>
    
- <span data-ttu-id="0baa6-127">**Conférence rendez-vous**</span><span class="sxs-lookup"><span data-stu-id="0baa6-127">**Dial-in Conferencing**</span></span>
    
    <span data-ttu-id="0baa6-128">La conférence rendez-vous permet aux utilisateurs de joindre un service A/V à partir d’un téléphone sur le réseau téléphonique téléphonique PSTN.</span><span class="sxs-lookup"><span data-stu-id="0baa6-128">Dial-in conferencing enables users to join an A/V from a telephone on the PSTN.</span></span> <span data-ttu-id="0baa6-129">La conférence dial-in nécessite que vous déployiez les applications Conferencing Attendant et Conferencing Announcement Service.</span><span class="sxs-lookup"><span data-stu-id="0baa6-129">Dial-in conferencing requires that you deploy the Conferencing Attendant and Conferencing Announcement Service applications.</span></span>
    
- <span data-ttu-id="0baa6-130">**Conférence web**</span><span class="sxs-lookup"><span data-stu-id="0baa6-130">**Web Conferencing**</span></span>
    
    <span data-ttu-id="0baa6-131">La conférence web permet aux utilisateurs d’entreprise à l’intérieur et à l’extérieur du pare-feu de créer et de participer à des conférences en temps réel hébergées sur vos serveurs internes.</span><span class="sxs-lookup"><span data-stu-id="0baa6-131">Web conferencing enables enterprise users inside and outside of the firewall to create and join real-time conferences that are hosted on your internal servers.</span></span>
    
- <span data-ttu-id="0baa6-132">**Conversation permanente**</span><span class="sxs-lookup"><span data-stu-id="0baa6-132">**Persistent Chat**</span></span>
    
    <span data-ttu-id="0baa6-133">La conversation permanente permet à plusieurs utilisateurs de participer à des conversations dans lesquelles ils publient et accèdent à du contenu sur des sujets spécifiques, notamment du texte, des liens et des fichiers.</span><span class="sxs-lookup"><span data-stu-id="0baa6-133">Persistent Chat enables multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="0baa6-134">Bien que les utilisateurs puissent communiquer en temps réel pendant une session, le contenu de chaque session est permanent, ce qui signifie qu’il reste disponible après la fin d’une session.</span><span class="sxs-lookup"><span data-stu-id="0baa6-134">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>
    
### <a name="users"></a><span data-ttu-id="0baa6-135">Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="0baa6-135">Users</span></span>

 <span data-ttu-id="0baa6-136">**Les utilisateurs** contiennent les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="0baa6-136">**Users** contains the following options:</span></span>
  
- <span data-ttu-id="0baa6-137">**Organisation interne**</span><span class="sxs-lookup"><span data-stu-id="0baa6-137">**Internal organization**</span></span>
    
- <span data-ttu-id="0baa6-138">**Fédération avec d’autres organisations**</span><span class="sxs-lookup"><span data-stu-id="0baa6-138">**Federation with other organizations**</span></span>
    
- <span data-ttu-id="0baa6-139">**Fédération avec les versions précédentes**</span><span class="sxs-lookup"><span data-stu-id="0baa6-139">**Federation with previous versions**</span></span>
    
- <span data-ttu-id="0baa6-140">**Fédération avec les fournisseurs de services de messagerie instantanée publics** Permet aux utilisateurs de votre organisation d’établir une communication avec des fournisseurs de services de messagerie instantanée publics tels que MSN, Yahoo! et AOL.</span><span class="sxs-lookup"><span data-stu-id="0baa6-140">**Federation with public IM services providers** Allows users in your organization to establish communication with public instant messaging service providers such as MSN, Yahoo!, and AOL.</span></span> <span data-ttu-id="0baa6-141">Une licence distincte est nécessaire pour établir une fédération avec les réseaux de messagerie instantanée publics.</span><span class="sxs-lookup"><span data-stu-id="0baa6-141">A separate license is required to establish federation with public instant messaging networks.</span></span>
    
- <span data-ttu-id="0baa6-142">**Fédération avec un fournisseur de services XMPP**</span><span class="sxs-lookup"><span data-stu-id="0baa6-142">**Federation with XMPP-based service provider**</span></span>
    
    <span data-ttu-id="0baa6-143">Skype Entreprise Server 2015 introduit un proxy XMPP entièrement intégré (déployé sur les serveurs Edge) et une passerelle XMPP déployée sur vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="0baa6-143">Skype for Business Server 2015 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="0baa6-144">Vous pouvez déployer l’ajout et la configuration du proxy XMPP et de la passerelle XMPP pour permettre aux utilisateurs de Skype Entreprise Server 2015 d’ajouter des contacts de partenaires XMPP pour la messagerie instantanée et la présence.</span><span class="sxs-lookup"><span data-stu-id="0baa6-144">You can deploy Adding and configuring the XMPP proxy and XMPP gateway will allow your Skype for Business Server 2015 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>

> [!NOTE]
> <span data-ttu-id="0baa6-145">Les passerelles et proxys XMPP sont disponibles dans Skype Entreprise Server 2015, mais ne sont plus pris en charge dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0baa6-145">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0baa6-146">Pour [plus d’informations, voir](../../../SfBServer2019/migration/migrating-xmpp-federation.md) Migration de la fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="0baa6-146">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    
- <span data-ttu-id="0baa6-147">**Mobilité**</span><span class="sxs-lookup"><span data-stu-id="0baa6-147">**Mobility**</span></span>
    
    <span data-ttu-id="0baa6-148">Lorsque vous déployez le service de mobilité de Skype Entreprise Server 2015, les utilisateurs peuvent utiliser les appareils mobiles Apple iOS, Android, Windows Phone ou Nokia pris en charge pour effectuer des activités telles que l’envoi et la réception de messages instantanés, l’affichage des contacts et l’affichage de la présence.</span><span class="sxs-lookup"><span data-stu-id="0baa6-148">When you deploy the Skype for Business Server 2015 Mobility Service, users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span>
    
- <span data-ttu-id="0baa6-149">**Boîte aux lettres Exchange W15**</span><span class="sxs-lookup"><span data-stu-id="0baa6-149">**W15 Exchange mailbox**</span></span>
    
    <span data-ttu-id="0baa6-150">Skype Entreprise Server 2015 vous permet de stocker des messages vocaux dans la messagerie unifiée Exchange ; Ces messages vocaux s’affichent ensuite sous la plupart des messages électroniques dans la boîte de réception de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0baa6-150">Skype for Business Server 2015 enables you to have voicemail messages stored in Exchange Unified Messaging (UM); those voicemail messages will then appear as email messages in your users' Inboxes.</span></span>
    
### <a name="voice"></a><span data-ttu-id="0baa6-151">Voix</span><span class="sxs-lookup"><span data-stu-id="0baa6-151">Voice</span></span>

 <span data-ttu-id="0baa6-152">**Voice** contient les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="0baa6-152">**Voice** contains the following options:</span></span>
  
- <span data-ttu-id="0baa6-153">**Voix Entreprise**</span><span class="sxs-lookup"><span data-stu-id="0baa6-153">**Enterprise Voice**</span></span>
    
    <span data-ttu-id="0baa6-154">Voix Entreprise est la solution VoIP de Microsft.</span><span class="sxs-lookup"><span data-stu-id="0baa6-154">Enterprise voice is Microsft's software-powered VoIP solution.</span></span> <span data-ttu-id="0baa6-155">Voix Entreprise permet aux utilisateurs d’utiliser Skype Entreprise pour appeler leur ordinateur.</span><span class="sxs-lookup"><span data-stu-id="0baa6-155">Enterprise voice enables users to use Skype for Business to place a phone call from their computer.</span></span>
    
- <span data-ttu-id="0baa6-156">**Messagerie unifiée Exchange**</span><span class="sxs-lookup"><span data-stu-id="0baa6-156">**Exchange Unified Messaging**</span></span>
    
    <span data-ttu-id="0baa6-157">La messagerie unifiée Exchange combine la messagerie vocale et la messagerie électronique dans une infrastructure de messagerie unique.</span><span class="sxs-lookup"><span data-stu-id="0baa6-157">Exchange Unified Messaging (UM) combines voice mail and email into a single messaging infrastructure.</span></span> <span data-ttu-id="0baa6-158">Skype Entreprise Server 2015 utilise la messagerie un réparation exchange pour fournir des services de répondeur automatique, d’accès abonné, de notification d’appel et de service de transport automatique.</span><span class="sxs-lookup"><span data-stu-id="0baa6-158">Skype for Business Server 2015 uses Exchange UM to provide call answering, subscriber access, call notification, and auto attendant services.</span></span> <span data-ttu-id="0baa6-159">Si vous utilisez ces services, vous devez intégrer la messagerie unie Exchange et Skype Entreprise Server dans une topologie Active Directory partagée.</span><span class="sxs-lookup"><span data-stu-id="0baa6-159">If you use these services, you will need to integrate Exchange UM and Skype for Business Server in a shared Active Directory topology.</span></span>
    
### <a name="additional-deployment-options"></a><span data-ttu-id="0baa6-160">Options de déploiement supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0baa6-160">Additional Deployment Options</span></span>

 <span data-ttu-id="0baa6-161">**Les options de déploiement supplémentaires** contiennent les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="0baa6-161">**Additional Deployment Options** contains the following options:</span></span>
  
- <span data-ttu-id="0baa6-162">**Haute disponibilité**</span><span class="sxs-lookup"><span data-stu-id="0baa6-162">**High Availability**</span></span>
    
    <span data-ttu-id="0baa6-163">La haute disponibilité active les serveurs de veille pour la prise en charge duover.</span><span class="sxs-lookup"><span data-stu-id="0baa6-163">High availability enables standby servers for failover support.</span></span>
    
- <span data-ttu-id="0baa6-164">**Récupération d’urgence**</span><span class="sxs-lookup"><span data-stu-id="0baa6-164">**Disaster Recovery**</span></span>
    
    <span data-ttu-id="0baa6-165">Les mesures de récupération d’urgence vous permettent de jumeler des pools frontaux situés dans deux centres de données.</span><span class="sxs-lookup"><span data-stu-id="0baa6-165">Disaster recovery measures enable you to pair Front End pools located in two datacenters.</span></span>
    
- <span data-ttu-id="0baa6-166">**Analyse**</span><span class="sxs-lookup"><span data-stu-id="0baa6-166">**Monitoring**</span></span>
    
    <span data-ttu-id="0baa6-167">La surveillance capture les enregistrements des détails des appels liés aux sessions de communication.</span><span class="sxs-lookup"><span data-stu-id="0baa6-167">Monitoring captures call detail records related to communication sessions.</span></span> <span data-ttu-id="0baa6-168">Il collecte également des mesures à partir de sessions audio et vidéo aux points de terminaison des participants.</span><span class="sxs-lookup"><span data-stu-id="0baa6-168">It also collects metrics from audio and video sessions at the participant endpoints.</span></span> <span data-ttu-id="0baa6-169">Le serveur de surveillance fournit des statistiques d’utilisation, des tendances et des statistiques sur la qualité des médias.</span><span class="sxs-lookup"><span data-stu-id="0baa6-169">Monitoring Server provides usage statistics, trends, and media quality statistics.</span></span>
    
- <span data-ttu-id="0baa6-170">**Archivage**</span><span class="sxs-lookup"><span data-stu-id="0baa6-170">**Archiving**</span></span>
    
    <span data-ttu-id="0baa6-171">L’archivage stocke les conversations et les conférences de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="0baa6-171">Archiving stores instant messaging conversations and conferences.</span></span>
    
- <span data-ttu-id="0baa6-172">**Intégration de l’archivage Exchange**</span><span class="sxs-lookup"><span data-stu-id="0baa6-172">**Exchange Archiving Integration**</span></span>
    
    <span data-ttu-id="0baa6-173">Si vous avez des utilisateurs qui sont homed on Exchange 2013 et que leurs boîtes aux lettres ont été mises en conservation In-Place, vous pouvez sélectionner l’option pour intégrer le stockage Skype Entreprise Server 2015 au stockage Exchange.</span><span class="sxs-lookup"><span data-stu-id="0baa6-173">If you have users who are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can select the option to integrate Skype for Business Server 2015 storage with Exchange storage.</span></span>
    
- <span data-ttu-id="0baa6-174">**IPv4**</span><span class="sxs-lookup"><span data-stu-id="0baa6-174">**IPv4**</span></span>
    
    <span data-ttu-id="0baa6-175">Les adresses IPv4 sont des adresses 32 bits qui permettent à un ordinateur de communiquer sur Internet.</span><span class="sxs-lookup"><span data-stu-id="0baa6-175">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="0baa6-176">En raison du nombre croissant d’appareils dans le monde, les adresses IPv4 disponibles sont à court. C’est pourquoi de nombreux nouveaux appareils utilisent des adresses IPv6.</span><span class="sxs-lookup"><span data-stu-id="0baa6-176">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span>
    
- <span data-ttu-id="0baa6-177">**IPv6**</span><span class="sxs-lookup"><span data-stu-id="0baa6-177">**IPv6**</span></span>
    
    <span data-ttu-id="0baa6-178">Les adresses IPv6 exécutent la même fonction que les adresses IPv4 (avec certaines fonctionnalités supplémentaires), mais au lieu d’utiliser uniquement 32 bits, les adresses IPv6 utilisent des adresses 128 bits.</span><span class="sxs-lookup"><span data-stu-id="0baa6-178">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="0baa6-179">Cela fournit non seulement un nouvel ensemble d’adresses, mais également un plus grand nombre d’adresses.</span><span class="sxs-lookup"><span data-stu-id="0baa6-179">This provides not only a new set of addresses, but also a much larger number of them.</span></span>
    
- <span data-ttu-id="0baa6-180">**service Web de mise à jour des périphériques**</span><span class="sxs-lookup"><span data-stu-id="0baa6-180">**Device Update Web service**</span></span>
    
    <span data-ttu-id="0baa6-181">Le service Web de mise à jour des périphériques permet de mettre à jour automatiquement tous les appareils, tels que Skype Entreprise pour Windows Phone, qui sont déployés en dehors de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0baa6-181">The Device Update Web service provides an automated way to update all devices, such as Skype for Business for Windows Phone, that are deployed outside of your organization.</span></span>
    
### <a name="server-applications"></a><span data-ttu-id="0baa6-182">Applications serveur</span><span class="sxs-lookup"><span data-stu-id="0baa6-182">Server Applications</span></span>

 <span data-ttu-id="0baa6-183">**Les applications serveur** contiennent les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="0baa6-183">**Server Applications** contains the following options:</span></span>
  
- <span data-ttu-id="0baa6-184">**Response Group**</span><span class="sxs-lookup"><span data-stu-id="0baa6-184">**Response Group**</span></span>
    
    <span data-ttu-id="0baa6-185">L’application Response Group répond et distribue automatiquement les appels à un agent de secours disponible.</span><span class="sxs-lookup"><span data-stu-id="0baa6-185">The Response Group application automatically answers and distributes calls to an available helpdesk agent.</span></span>
    
- <span data-ttu-id="0baa6-186">**Annonce**</span><span class="sxs-lookup"><span data-stu-id="0baa6-186">**Announcement**</span></span>
    
    <span data-ttu-id="0baa6-187">Si vous prévoyez de déployer Voix Entreprise, vous pouvez configurer la façon dont les appels téléphoniques sont gérés si le numéro composé est valide mais n’est pas affecté à une zone commune d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0baa6-187">If you plan to deploy Enterprise Voice, you might want to be able to configure how phone calls are handled if the dialed number is valid but not assigned to a user common area.</span></span> <span data-ttu-id="0baa6-188">Les administrateurs peuvent configurer le service d’annonce afin que ces appels sont transférés vers une destination prédéterminée (numéro de téléphone ou URI SIP) ou lire une annonce audio ou les deux.</span><span class="sxs-lookup"><span data-stu-id="0baa6-188">Administrators can configure Announcement Service so that these calls transfer to a predetermined destination (phone number or SIP URI) or play an audio announcement or both.</span></span> <span data-ttu-id="0baa6-189">L’utilisation du service d’annonce évite la situation dans laquelle un appelant maldialisation et entend une tonalité d’occupé ou le client SIP reçoit un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="0baa6-189">Using Announcement Service avoids the situation in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="0baa6-190">La fonctionnalité service d’annonce est une fonctionnalité PBX classique.</span><span class="sxs-lookup"><span data-stu-id="0baa6-190">Announcement Service functionality is a typical PBX feature.</span></span> 
    
- <span data-ttu-id="0baa6-191">**Parcage d’appel**</span><span class="sxs-lookup"><span data-stu-id="0baa6-191">**Call Park**</span></span>
    
    <span data-ttu-id="0baa6-192">L’application de parcage d’appel permet à un utilisateur Voix Entreprise de mettre un appel en attente à partir d’un téléphone, puis de recevoir l’appel d’un autre téléphone sans lier les ressources sur le téléphone qui a reçu l’appel.</span><span class="sxs-lookup"><span data-stu-id="0baa6-192">Call Park application enables an Enterprise Voice user to put a call on hold from one telephone, and then receive the call from another telephone without tying up resources on the phone that received the call.</span></span> <span data-ttu-id="0baa6-193">L’application de parcage d’appel est utile lorsqu’un utilisateur doit transférer un appel, mais que le destinataire spécifique est inconnu.</span><span class="sxs-lookup"><span data-stu-id="0baa6-193">Call Park application is useful when a user needs to transfer a call, but the specific recipient is unknown.</span></span> 
    
- <span data-ttu-id="0baa6-194">**Conference Attendant**</span><span class="sxs-lookup"><span data-stu-id="0baa6-194">**Conference Attendant**</span></span>
    
    <span data-ttu-id="0baa6-195">L’application Attendant de conférence offre des fonctionnalités d’audioconférence aux utilisateurs téléphoniques sans le service d’un fournisseur tiers de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="0baa6-195">Conferencing Attendant application provides audio conferencing capabilities to phone users without the service of a third-party audio conferencing provider.</span></span>
    
- <span data-ttu-id="0baa6-196">**Annonce de conférence**</span><span class="sxs-lookup"><span data-stu-id="0baa6-196">**Conferencing Announcement**</span></span>
    
    <span data-ttu-id="0baa6-197">L’application Annonce de conférence produit des tonalités signalant que les utilisateurs entrent ou quittent une conférence, ainsi que des notifications aux utilisateurs de téléphone lorsqu’ils sont mutés ou non.</span><span class="sxs-lookup"><span data-stu-id="0baa6-197">Conferencing Announcement application produces tones that signal when users enter or leave a conference, as well as notifications to phone users when they are muted or unmuted.</span></span>
    
- <span data-ttu-id="0baa6-198">**Contrôle d’admission des appels**</span><span class="sxs-lookup"><span data-stu-id="0baa6-198">**Call Admission Control**</span></span>
    
    <span data-ttu-id="0baa6-199">Le contrôle d’admission des appels (CAC), également appelé gestion de la bande passante wan, permet d’éviter une mauvaise qualité d’expérience pour les utilisateurs sur des réseaux saturés en déterminant, en fonction de la bande passante disponible, s’il faut autoriser et établir de nouvelles sessions de communication en temps réel.</span><span class="sxs-lookup"><span data-stu-id="0baa6-199">Call Admission Control (CAC), also known as WAN bandwidth management, helps to prevent poor quality of experience for users on congested networks by determining, based on available bandwidth, whether to allow and new real-time communications sessions to be established.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0baa6-200">Le contrôle d’accès au contrôle d’accès contrôle uniquement le trafic en temps réel et n’affecte pas le trafic de données.</span><span class="sxs-lookup"><span data-stu-id="0baa6-200">CAC only controls real-time traffic and does not affect data traffic.</span></span> 
  
    <span data-ttu-id="0baa6-201">Si une nouvelle session vocale ou vidéo dépasse les limites de bande passante que vous avez allouées sur un réseau wan, la session est bloquée ou (pour les appels téléphoniques uniquement) réacheminée vers le réseau téléphonique (PSTN).</span><span class="sxs-lookup"><span data-stu-id="0baa6-201">If a new voice or video session exceeds the bandwidth limits that you have allocated on a WAN, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>
    

