---
title: Déployer et configurer la mobilité pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Cet article vous guide tout au long des étapes nécessaires pour configurer une installation de Skype entreprise Server existante afin qu’elle utilise le service de mobilité, ce qui permet à vos appareils mobiles de tirer parti des fonctionnalités de mobilité de Skype entreprise Server.
ms.openlocfilehash: 457eeff39c87f20326d64cc5227745b43e0af5f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029065"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="14957-103">Déployer et configurer la mobilité pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="14957-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="14957-104">Cet article vous guide tout au long des étapes nécessaires pour configurer une installation de Skype entreprise Server existante afin qu’elle utilise le service de mobilité, ce qui permet à vos appareils mobiles de tirer parti des fonctionnalités de mobilité de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="14957-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="14957-105">Après avoir examiné l’article [plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) , vous devez être prêt à suivre les étapes ci-dessous pour déployer la mobilité dans votre environnement Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="14957-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="14957-106">Les étapes sont les suivantes (et nous les incluons dans ce tableau une liste d’autorisations) :</span><span class="sxs-lookup"><span data-stu-id="14957-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="14957-107">**Étape**</span><span class="sxs-lookup"><span data-stu-id="14957-107">**Phase**</span></span>|<span data-ttu-id="14957-108">**Autorisations**</span><span class="sxs-lookup"><span data-stu-id="14957-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="14957-109">Créer des enregistrements DNS</span><span class="sxs-lookup"><span data-stu-id="14957-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="14957-110">Admins du domaine</span><span class="sxs-lookup"><span data-stu-id="14957-110">Domain Admins</span></span>  <br/> <span data-ttu-id="14957-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="14957-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="14957-112">Modifier les certificats</span><span class="sxs-lookup"><span data-stu-id="14957-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="14957-113">Administrateur local</span><span class="sxs-lookup"><span data-stu-id="14957-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="14957-114">Configurer le proxy inverse</span><span class="sxs-lookup"><span data-stu-id="14957-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="14957-115">Administrateur local</span><span class="sxs-lookup"><span data-stu-id="14957-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="14957-116">Configurer la découverte automatique pour la mobilité avec les déploiements hybrides</span><span class="sxs-lookup"><span data-stu-id="14957-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="14957-117">Admins du domaine</span><span class="sxs-lookup"><span data-stu-id="14957-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="14957-118">Tester votre déploiement de mobilité</span><span class="sxs-lookup"><span data-stu-id="14957-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="14957-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="14957-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="14957-120">Configurer les notifications de type push</span><span class="sxs-lookup"><span data-stu-id="14957-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="14957-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="14957-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="14957-122">Configurer la stratégie de mobilité</span><span class="sxs-lookup"><span data-stu-id="14957-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="14957-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="14957-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="14957-124">Toutes les sections suivantes contiennent des étapes qui supposent que vous avez lu la rubrique Planning.</span><span class="sxs-lookup"><span data-stu-id="14957-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="14957-125">Si vous êtes déroutant, n’hésitez pas à en consulter les informations.</span><span class="sxs-lookup"><span data-stu-id="14957-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="14957-126">La prise en charge de MCX (Mobility service) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="14957-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="14957-127">Tous les clients mobiles Skype entreprise actuels utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts.</span><span class="sxs-lookup"><span data-stu-id="14957-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="14957-128">Les utilisateurs avec des clients hérités qui utilisent MCX devront effectuer une mise à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="14957-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="14957-129">Créer des enregistrements DNS</span><span class="sxs-lookup"><span data-stu-id="14957-129">Create DNS records</span></span>
<span data-ttu-id="14957-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="14957-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="14957-131">Vous disposez peut-être déjà de ces éléments dans le cadre de votre environnement Skype entreprise Server, mais vous devez créer les enregistrements suivants pour que la découverte automatique fonctionne :</span><span class="sxs-lookup"><span data-stu-id="14957-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="14957-132">Un enregistrement DNS interne pour prendre en charge les utilisateurs mobiles qui se connectent à partir du réseau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="14957-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="14957-133">Un enregistrement DNS externe (ou public) pour prendre en charge les utilisateurs mobiles qui se connectent depuis l’extérieur du réseau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="14957-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="14957-134">Ces enregistrements peuvent être soit des noms (hôtes), soit des enregistrements CNAMe (vous n’avez pas à effectuer les deux à la fois, nous incluons simplement les étapes de tous les éléments ici).</span><span class="sxs-lookup"><span data-stu-id="14957-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="14957-135">Créer un enregistrement CNAMe DNS interne</span><span class="sxs-lookup"><span data-stu-id="14957-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="14957-136">Connectez-vous à un serveur DNS de votre réseau qui est membre du groupe **administrateurs du domaine** ou du groupe **DnsAdmins** .</span><span class="sxs-lookup"><span data-stu-id="14957-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="14957-137">Cliquez sur **Démarrer**, sélectionnez **Outils d’administration** (il se peut que vous deviez le **Rechercher** s’il n’est pas possible d’utiliser le menu Démarrer), puis cliquez sur **DNS** pour ouvrir le composant logiciel enfichable d’administration DNS.</span><span class="sxs-lookup"><span data-stu-id="14957-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="14957-138">Dans le volet de gauche de la fenêtre de la console, vous devez accéder au domaine qui héberge les serveurs frontaux de Skype entreprise Server et développer les **zones de recherche directes** .</span><span class="sxs-lookup"><span data-stu-id="14957-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="14957-139">Prenez un moment pour voir les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="14957-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="14957-140">Tout enregistrement A ou AAAA hôte pour votre serveur frontal (standard ou Enterprise) ou un ou plusieurs pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="14957-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="14957-141">N’importe quel enregistrement A ou AAAA hôte pour un directeur ou un pool directeur (Configuration facultative que vous pouvez avoir dans votre déploiement).</span><span class="sxs-lookup"><span data-stu-id="14957-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="14957-142">Une fois que vous avez noté cela, cliquez avec le bouton droit sur le nom de votre domaine SIP, puis choisissez **Nouvel alias (CNAME)** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="14957-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="14957-143">Dans la zone de texte **nom d’alias** , tapez lyncdiscoverinternal pour votre nom d’hôte, pour l’URL du service de découverte automatique interne.</span><span class="sxs-lookup"><span data-stu-id="14957-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="14957-144">Dans le **nom de domaine complet (FQDN) de l’hôte de destination**, vous devez taper ou parcourir le nom de domaine complet des services Web internes pour votre pool frontal (ou un serveur frontal unique, ou un pool ou directeur de directeur), identifié à l’étape 4 ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="14957-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="14957-145">Cliquez sur OK lorsque cette entrée est entrée.</span><span class="sxs-lookup"><span data-stu-id="14957-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="14957-146">Vous devrez créer un nouvel enregistrement CNAMe de découverte automatique dans la zone de recherche directe pour chaque domaine SIP pris en charge dans votre environnement Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="14957-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="14957-147">Créer un enregistrement CNAMe DNS externe</span><span class="sxs-lookup"><span data-stu-id="14957-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="14957-148">Ces étapes sont génériques, car nous ne pouvons pas indiquer quel fournisseur DNS public vous pouvez utiliser, mais nous souhaitons toujours vous aider. Connectez-vous à votre fournisseur DNS public à l’aide d’un compte qui pourra y créer de nouveaux enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="14957-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="14957-149">À ce stade, un domaine SIP doit déjà exister ici pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="14957-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="14957-150">Développez la **zone de recherche directe** pour ce domaine SIP, ou ouvrez-la.</span><span class="sxs-lookup"><span data-stu-id="14957-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="14957-151">Prenez un moment pour voir les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="14957-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="14957-152">Tout enregistrement A ou AAAA hôte pour votre serveur frontal (standard ou Enterprise) ou un ou plusieurs pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="14957-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="14957-153">N’importe quel enregistrement A ou AAAA hôte pour un directeur ou un pool directeur (Configuration facultative que vous pouvez avoir dans votre déploiement).</span><span class="sxs-lookup"><span data-stu-id="14957-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="14957-154">Une fois que vous disposez de ces informations, vous devez pouvoir sélectionner une option pour créer un **Nouvel alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="14957-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="14957-155">À présent, vous devriez pouvoir entrer un **nom d’alias**, vous devez entrer lyncdiscover ici pour l’URL du service de découverte automatique externe.</span><span class="sxs-lookup"><span data-stu-id="14957-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="14957-156">Il doit s’agir d’une zone à entrer dans un **nom de domaine complet (FQDN) pour l’hôte cible**, il doit s’agir du nom de domaine complet de votre pool frontal (ou d’un serveur frontal unique, ou du pool ou directeur de directeur) identifié à l’étape 3 ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="14957-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="14957-157">Vous devrez peut-être enregistrer cet emplacement, ou si vous devez créer des enregistrements CNAMe supplémentaires dans la zone de recherche directe de chaque domaine SIP dans votre environnement Skype entreprise Server, vous devez procéder ainsi, mais une fois que vous êtes prêt, enregistrez votre travail.</span><span class="sxs-lookup"><span data-stu-id="14957-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="14957-158">Créer un enregistrement DNS A interne</span><span class="sxs-lookup"><span data-stu-id="14957-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="14957-159">Connectez-vous à un serveur DNS de votre réseau qui est membre du groupe **administrateurs du domaine** ou du groupe **DnsAdmins** .</span><span class="sxs-lookup"><span data-stu-id="14957-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="14957-160">Cliquez sur **Démarrer**, sélectionnez **Outils d’administration** (il se peut que vous deviez le **Rechercher** s’il n’est pas possible d’utiliser le menu Démarrer), puis cliquez sur **DNS** pour ouvrir le composant logiciel enfichable d’administration DNS.</span><span class="sxs-lookup"><span data-stu-id="14957-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="14957-161">Dans le volet de gauche de la fenêtre de la console, vous devez accéder au domaine qui héberge les serveurs frontaux de Skype entreprise Server et développer les **zones de recherche directes** .</span><span class="sxs-lookup"><span data-stu-id="14957-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="14957-162">Prenez un moment pour voir les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="14957-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="14957-163">Tout enregistrement A ou AAAA hôte pour votre serveur frontal (standard ou Enterprise) ou un ou plusieurs pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="14957-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="14957-164">N’importe quel enregistrement A ou AAAA hôte pour un directeur ou un pool directeur (Configuration facultative que vous pouvez avoir dans votre déploiement).</span><span class="sxs-lookup"><span data-stu-id="14957-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="14957-165">Une fois que vous avez noté cela, cliquez avec le bouton droit sur le nom de votre domaine SIP, puis sélectionnez **nouvel hôte (A ou AAAA)** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="14957-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="14957-166">Dans la zone de texte **nom** , tapez lyncdiscoverinternal pour votre nom d’hôte, pour l’URL du service de découverte automatique interne.</span><span class="sxs-lookup"><span data-stu-id="14957-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="14957-167">Dans la zone **adresse IP** , tapez l’adresse IP interne des services Web pour votre pool frontal (ou un serveur frontal unique, ou un pool ou directeur de directeur), identifié à l’étape 4 ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="14957-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="14957-168">Une fois cette opération terminée, cliquez sur **Ajouter un hôte**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="14957-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="14957-169">Vous devrez créer un nouvel enregistrement Autodiscover A ou AAAA dans la zone de recherche directe pour chaque domaine SIP pris en charge dans votre environnement Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="14957-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="14957-170">Pour ce faire, répétez les étapes 6-8 autant de fois que nécessaire.</span><span class="sxs-lookup"><span data-stu-id="14957-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="14957-171">Lorsque vous avez fini, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="14957-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="14957-172">Créer un enregistrement A DNS externe</span><span class="sxs-lookup"><span data-stu-id="14957-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="14957-173">Ces étapes sont génériques, car nous ne pouvons pas indiquer quel fournisseur DNS public vous pouvez utiliser, mais nous souhaitons toujours vous aider. Connectez-vous à votre fournisseur DNS public à l’aide d’un compte qui pourra y créer de nouveaux enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="14957-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="14957-174">À ce stade, un domaine SIP doit déjà exister ici pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="14957-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="14957-175">Développez la **zone de recherche directe** pour ce domaine SIP, ou ouvrez-la.</span><span class="sxs-lookup"><span data-stu-id="14957-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="14957-176">Prenez un moment pour voir les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="14957-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="14957-177">Tout enregistrement A ou AAAA hôte pour votre serveur frontal (standard ou Enterprise) ou un ou plusieurs pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="14957-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="14957-178">N’importe quel enregistrement A ou AAAA hôte pour un directeur ou un pool directeur (Configuration facultative que vous pouvez avoir dans votre déploiement).</span><span class="sxs-lookup"><span data-stu-id="14957-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="14957-179">Une fois que vous disposez de ces informations, vous devez être en mesure de sélectionner une option pour créer un **nouvel hôte a ou AAAA**.</span><span class="sxs-lookup"><span data-stu-id="14957-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="14957-180">À présent, vous devriez pouvoir entrer un **nom**, vous devez entrer lyncdiscover ici pour l’URL du service de découverte automatique externe.</span><span class="sxs-lookup"><span data-stu-id="14957-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="14957-181">Ensuite, il doit y avoir une zone à saisir dans une **adresse IP**, il doit s’agir de l’adresse IP de votre pool frontal (ou d’un serveur frontal unique, ou d’un pool directeur ou directeur), identifié à l’étape 3 ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="14957-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="14957-182">Vous devrez peut-être enregistrer ici, ou si vous avez besoin de créer des enregistrements A ou AAAA supplémentaires dans la zone de recherche directe de chaque domaine SIP pour votre environnement Skype entreprise Server, vous devez procéder ainsi, mais une fois que vous êtes prêt, enregistrez votre travail.</span><span class="sxs-lookup"><span data-stu-id="14957-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="14957-183">Modifier les certificats</span><span class="sxs-lookup"><span data-stu-id="14957-183">Modify certificates</span></span>
<span data-ttu-id="14957-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="14957-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="14957-185">Si vous avez des questions sur la planification des certificats, nous avons documenté cela dans notre article [plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) .</span><span class="sxs-lookup"><span data-stu-id="14957-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="14957-186">Une fois que vous avez consulté ce qui suit, nous allons vous présenter les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="14957-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="14957-187">Ai-je besoin de nouveaux certificats ?</span><span class="sxs-lookup"><span data-stu-id="14957-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="14957-188">Demande de nouveaux certificats auprès de votre autorité de certification (CA).</span><span class="sxs-lookup"><span data-stu-id="14957-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="14957-189">Mise à jour de vos certificats sur place avec les remplacements à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14957-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="14957-190">Vérification des certificats à l’aide du composant logiciel enfichable Certificats dans la console MMC (Microsoft Management Console).</span><span class="sxs-lookup"><span data-stu-id="14957-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="14957-191">Ai-je besoin de nouveaux certificats ?</span><span class="sxs-lookup"><span data-stu-id="14957-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="14957-192">Tout d’abord, il se peut que vous deviez vérifier et voir quels certificats sont en place, et s’ils disposent ou non des entrées dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="14957-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="14957-193">Pour ce faire, vous devez vous connecter à votre serveur Skype entreprise à l’aide d’un compte administrateur local.</span><span class="sxs-lookup"><span data-stu-id="14957-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="14957-194">Pour certaines de ces étapes, il se peut que ce compte doive également disposer de droits sur l’autorité de certification émettrice.</span><span class="sxs-lookup"><span data-stu-id="14957-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="14957-195">Ouvrez Skype entreprise Server Management Shell (vous pouvez utiliser la recherche pour le trouver si vous ne l’avez pas épinglée à votre menu Démarrer ou à la barre des tâches).</span><span class="sxs-lookup"><span data-stu-id="14957-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="14957-196">Il va être essentiel de savoir quels certificats ont été affectés avant d’ajouter un certificat mis à jour.</span><span class="sxs-lookup"><span data-stu-id="14957-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="14957-197">Par conséquent, à la commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="14957-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="14957-198">Les informations de l’étape 3 vous seront propres.</span><span class="sxs-lookup"><span data-stu-id="14957-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="14957-199">Vous devez le Rechercher pour déterminer si vous avez un certificat unique qui a été affecté à plusieurs éléments, ou si vous avez un certificat différent affecté aux différents composants qui en ont besoin.</span><span class="sxs-lookup"><span data-stu-id="14957-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="14957-200">Le paramètre **use** vous indique le mode d’utilisation d’un certificat et le paramètre d' **empreinte** vous indique s’il s’agit du même certificat ou de plusieurs certificats.</span><span class="sxs-lookup"><span data-stu-id="14957-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="14957-201">Si vous avez les entrées SAN recommandées dans notre section planification, vous avez l’habitude.</span><span class="sxs-lookup"><span data-stu-id="14957-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="14957-202">Si ce n’est pas le cas, vous devrez demander un nouveau certificat ou plusieurs certificats (en fonction de votre configuration) auprès de votre autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="14957-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="14957-203">Demander un nouveau certificat ou des certificats auprès de votre autorité de certification (CA)</span><span class="sxs-lookup"><span data-stu-id="14957-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="14957-204">Une fois que vous avez vérifié les entrées SAN dont vous disposez, vous savez que vous disposez d’un **certificat unique** (après avoir vérifié les étapes ci-dessus), et que vous avez appris que vous n’avez pas toutes les entrées dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="14957-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="14957-205">Une nouvelle demande de certificat doit être effectuée sur votre autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="14957-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="14957-206">Ouvrez votre serveur PowerShell Skype entreprise :</span><span class="sxs-lookup"><span data-stu-id="14957-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="14957-207">Pour un SAN de service de découverte automatique manquant (en remplaçant le paramètre-ca par votre propre chemin d’accès de l’autorité de certification) :</span><span class="sxs-lookup"><span data-stu-id="14957-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="14957-208">À présent, si vous avez plusieurs domaines SIP, vous ne pouvez pas utiliser le paramètre AllSipDomain comme dans l’exemple ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="14957-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="14957-209">Vous devez utiliser le paramètre DomainName à la place.</span><span class="sxs-lookup"><span data-stu-id="14957-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="14957-210">Lorsque vous utilisez le paramètre DomainName, vous devez définir le nom de domaine complet (FQDN) pour les enregistrements lyncdiscoverinternal et lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="14957-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="14957-211">Voici un exemple (remplacement du paramètre-ca par votre propre chemin d’accès à l’autorité de certification) :</span><span class="sxs-lookup"><span data-stu-id="14957-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="14957-212">Ou, une fois que vous avez vérifié les entrées SAN dont vous disposez, vous avez trouvé **plusieurs certificats** qui n’ont pas toutes les entrées dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="14957-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="14957-213">Une nouvelle demande de certificat doit être effectuée sur votre autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="14957-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="14957-214">Ouvrez votre serveur PowerShell Skype entreprise :</span><span class="sxs-lookup"><span data-stu-id="14957-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="14957-215">Pour un SAN de service de découverte automatique manquant (en remplaçant le paramètre-ca par votre propre chemin d’accès de l’autorité de certification) :</span><span class="sxs-lookup"><span data-stu-id="14957-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="14957-216">À présent, si vous avez plusieurs domaines SIP, vous ne pouvez pas utiliser le paramètre AllSipDomain comme dans l’exemple ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="14957-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="14957-217">Vous devez utiliser le paramètre DomainName à la place.</span><span class="sxs-lookup"><span data-stu-id="14957-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="14957-218">Lorsque vous utilisez le paramètre DomainName, vous devez définir le nom de domaine complet (FQDN) pour les enregistrements lyncdiscoverinternal et lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="14957-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="14957-219">Voici quelques exemples (remplacer le paramètre-ca par votre propre chemin d’accès à l’autorité de certification) :</span><span class="sxs-lookup"><span data-stu-id="14957-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="14957-220">Une fois que les nouveaux certificats ont été générés par l’autorité de certification, vous devez les affecter.</span><span class="sxs-lookup"><span data-stu-id="14957-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="14957-221">Affecter des certificats à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="14957-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="14957-222">En fonction de ce que vous avez trouvé dans la section ai-je besoin de nouvelles certifications ci-dessus, vous devez exécuter l' **un** des éléments suivants.</span><span class="sxs-lookup"><span data-stu-id="14957-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="14957-223">Si vous disposez d’un certificat unique pour tous les éléments (les empreintes sont identiques), vous devez exécuter l’élément suivant :</span><span class="sxs-lookup"><span data-stu-id="14957-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="14957-224">Si vous avez des certificats différents pour des éléments (les empreintes sont tous différents), exécutez plutôt cette fonction :</span><span class="sxs-lookup"><span data-stu-id="14957-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="14957-225">Affichage des certificats dans la console MMC (Microsoft Management Console)</span><span class="sxs-lookup"><span data-stu-id="14957-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="14957-226">Vous avez la possibilité de consulter vos certificats à l’aide du composant logiciel enfichable Certificats pour la console MMC.</span><span class="sxs-lookup"><span data-stu-id="14957-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="14957-227">Il vous suffit de taper MMC dans la recherche et de le faire apparaître comme option d’application.</span><span class="sxs-lookup"><span data-stu-id="14957-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="14957-228">Pour ajouter le composant logiciel enfichable Certificats, vous devez cliquer sur **fichier**, puis sur **Ajouter/supprimer un composant logiciel enfichable...** (ou un raccourci clavier **Ctrl + M** fonctionne également).</span><span class="sxs-lookup"><span data-stu-id="14957-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="14957-229">Les **certificats** seront une option dans le volet de gauche, sélectionnez-le, puis **compte d’ordinateur** dans la fenêtre contextuelle, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="14957-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="14957-230">Toujours dans la fenêtre contextuelle, quelle que soit la probabilité que vous effectuiez cette opération sur l’ordinateur qui est à l’origine des certificats que vous devez consulter, conservez la sélection sur **ordinateur local** si c’est le cas.</span><span class="sxs-lookup"><span data-stu-id="14957-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="14957-231">Si vous travaillez sur un ordinateur distant, modifiez la case d’option sur **un autre ordinateur** , puis entrez le nom de domaine complet de l’ordinateur ou utilisez le bouton **Parcourir** pour rechercher cet ordinateur via ad.</span><span class="sxs-lookup"><span data-stu-id="14957-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="14957-232">Après avoir sélectionné l’ordinateur, vous devez cliquer sur **Terminer** lorsque vous êtes prêt, puis sur **OK** pour ajouter le composant logiciel enfichable à la console MMC.</span><span class="sxs-lookup"><span data-stu-id="14957-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="14957-233">Développez la section **certificats** dans le volet de gauche de la console MMC.</span><span class="sxs-lookup"><span data-stu-id="14957-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="14957-234">Développez également le dossier **personnel** , puis sélectionnez **certificats**.</span><span class="sxs-lookup"><span data-stu-id="14957-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="14957-235">Cela vous permet d’afficher les certificats de ce magasin.</span><span class="sxs-lookup"><span data-stu-id="14957-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="14957-236">Vous devez rechercher le certificat que vous souhaitez afficher, cliquez dessus avec le bouton droit, puis choisissez **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="14957-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="14957-237">Comment savoir quel certificat il s’agit ?</span><span class="sxs-lookup"><span data-stu-id="14957-237">How do you know what certificate this is?</span></span> <span data-ttu-id="14957-238">Il doit s’agir du certificat unique affecté à tous les éléments de votre batterie de serveurs, ou vous pouvez avoir plusieurs certificats pour différentes choses, tels que default, des services Web internes, etc., auquel cas vous devrez peut-être examiner plusieurs certificats.</span><span class="sxs-lookup"><span data-stu-id="14957-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="14957-239">Plusieurs certificats auront la même empreinte.</span><span class="sxs-lookup"><span data-stu-id="14957-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="14957-240">Une fois que vous avez obtenu la vue du **certificat** , choisissez **Détails**.</span><span class="sxs-lookup"><span data-stu-id="14957-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="14957-241">Cela vous permettra d’afficher le nom de l’objet du certificat lorsque vous sélectionnez l’option **objet**, et le nom de l’objet affecté et les propriétés associées sont affichés.</span><span class="sxs-lookup"><span data-stu-id="14957-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="14957-242">Vous devrez également vérifier les entrées de l' **autre nom du sujet** .</span><span class="sxs-lookup"><span data-stu-id="14957-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="14957-243">Vous trouverez un ou plusieurs des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="14957-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="14957-244">Nom du pool de ce pool, ou nom de serveur unique s’il ne s’agit pas d’un pool.</span><span class="sxs-lookup"><span data-stu-id="14957-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="14957-245">Nom du serveur auquel le certificat est affecté.</span><span class="sxs-lookup"><span data-stu-id="14957-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="14957-246">Enregistrements d’URL simples, généralement correspondant à la numérotation.</span><span class="sxs-lookup"><span data-stu-id="14957-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="14957-247">Noms externes des services Web et des services Web (par exemple, webpool01.contoso.net, webpool01.contoso.com), en fonction des choix effectués dans le générateur de topologie et des sélections de services Web remplacés.</span><span class="sxs-lookup"><span data-stu-id="14957-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="14957-248">S’il est déjà attribué, le lyncdiscover. \<sipdomain\> et lyncdiscoverinternal. \<enregistrements\> sipdomain.</span><span class="sxs-lookup"><span data-stu-id="14957-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="14957-249">Vous devrez vérifier plusieurs certificats si vous en avez attribué plusieurs (consultez la remarque ci-dessus).</span><span class="sxs-lookup"><span data-stu-id="14957-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="14957-250">Par conséquent, si vous trouvez lyncdiscover. \<sipdomain\> et lyncdiscoverinternal. \<enregistrements\> sipdomain, vous avez déjà configuré cette configuration.</span><span class="sxs-lookup"><span data-stu-id="14957-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="14957-251">Vous pouvez fermer la console MMC.</span><span class="sxs-lookup"><span data-stu-id="14957-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="14957-252">Si elles ne sont pas affectées, vous devez créer une demande de certificat (décrite ci-dessus) ou les installer après la demande (nous vous recommandons de suivre PowerShell ci-dessus).</span><span class="sxs-lookup"><span data-stu-id="14957-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="14957-253">Configurer le proxy inverse</span><span class="sxs-lookup"><span data-stu-id="14957-253">Configure the reverse proxy</span></span>
<span data-ttu-id="14957-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="14957-254"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="14957-255">Les étapes ci-dessous ne sont pas destinées à être suivies exactement.</span><span class="sxs-lookup"><span data-stu-id="14957-255">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="14957-256">En effet, dans les versions précédentes du produit, nous aurions pu vous présenter, par exemple, la configuration de la passerelle de gestion des menaces (TMG) et, si vous ne l’avez pas fait, vous devez utiliser votre propre version à partir de là.</span><span class="sxs-lookup"><span data-stu-id="14957-256">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="14957-257">TMG n’est plus offert par Microsoft en tant que produit, et si vous devez le configurer, vous pouvez consulter les [étapes de Lync Server 2013](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="14957-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="14957-258">Toutefois, les informations suivantes doivent être plus généralement utiles, même si vous ne pouvez pas fournir des étapes de procédure pas à pas spécifiques pour chaque proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="14957-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="14957-259">Deux éléments principaux sont à prendre en compte :</span><span class="sxs-lookup"><span data-stu-id="14957-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="14957-260">Allez-vous effectuer votre demande de découverte automatique initiale sur HTTPs (recommandé) ?</span><span class="sxs-lookup"><span data-stu-id="14957-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="14957-261">Si vous avez une règle de publication Web, vous devez la modifier.</span><span class="sxs-lookup"><span data-stu-id="14957-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="14957-262">Si vous n’avez pas encore de règle de publication Web, vous devez la créer.</span><span class="sxs-lookup"><span data-stu-id="14957-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="14957-263">Si vous effectuez votre demande de découverte automatique initiale sur HTTP, vous devez également créer ou modifier cette règle.</span><span class="sxs-lookup"><span data-stu-id="14957-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="14957-264">**Important** Une valeur de délai d’expiration du proxy est un nombre qui varie d’un déploiement à l’autre.</span><span class="sxs-lookup"><span data-stu-id="14957-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="14957-265">Vous devez surveiller votre déploiement et modifier la valeur pour la meilleure expérience pour les clients.</span><span class="sxs-lookup"><span data-stu-id="14957-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="14957-266">Vous pouvez définir la valeur sur 200.</span><span class="sxs-lookup"><span data-stu-id="14957-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="14957-267">Si vous prenez en charge les clients mobiles Lync dans votre environnement, vous devez définir la valeur sur 960 pour autoriser les délais d’expiration des notifications de type transmission à partir d’Office 365, dont la valeur de délai d’expiration est de 900.</span><span class="sxs-lookup"><span data-stu-id="14957-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="14957-268">Il est fort probable que vous deviez augmenter la valeur du délai d’expiration pour éviter que le client se déconnecte lorsque la valeur est trop faible ou réduire le nombre si les connexions par le biais du proxy ne se déconnectent pas bien après la déconnexion du client.</span><span class="sxs-lookup"><span data-stu-id="14957-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="14957-269">La surveillance et la détermination de la configuration habituelle de votre environnement sont la seule façon de déterminer le paramètre approprié pour cette valeur.</span><span class="sxs-lookup"><span data-stu-id="14957-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="14957-270">Modifier la règle de publication Web existante pour votre SAN de découverte automatique externe et votre URL</span><span class="sxs-lookup"><span data-stu-id="14957-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="14957-271">Ouvrez votre interface de proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="14957-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="14957-272">Vous devez localiser votre règle de publication Web, puis choisir l’option modifier (elle peut se trouver sur un menu ou un onglet, en fonction de la configuration de votre proxy inverse).</span><span class="sxs-lookup"><span data-stu-id="14957-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="14957-273">Il doit y avoir un domaine qui indique le type d’application de cette règle de publication Web.</span><span class="sxs-lookup"><span data-stu-id="14957-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="14957-274">Vous devez modifier cette règle pour les sites entrants ou les demandes de sites.</span><span class="sxs-lookup"><span data-stu-id="14957-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="14957-275">Vous allez **Ajouter** une nouvelle entrée.</span><span class="sxs-lookup"><span data-stu-id="14957-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="14957-276">Tapez le nom de votre site de découverte automatique (l’exemple que nous allons utiliser est lyncdiscover.contoso.com), puis cliquez sur **OK** ou sur **Enregistrer**, selon le format de votre proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="14957-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="14957-277">Vous avez peut-être un nouveau certificat qui contient l’entrée SAN de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="14957-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="14957-278">Celle-ci doit être installée et configurée pour être utilisée conformément aux paramètres de votre proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="14957-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="14957-279">N’oubliez pas d’enregistrer tous les éléments lorsque la configuration est terminée.</span><span class="sxs-lookup"><span data-stu-id="14957-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="14957-280">Si votre proxy inverse dispose d’une fonctionnalité de **test** , utilisez-le pour vous assurer que tout fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="14957-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="14957-281">À présent, vous devrez peut-être répéter ces étapes si vous avez un directeur ou un pool directeur dans votre environnement (cela signifie que vous disposez d’une deuxième règle).</span><span class="sxs-lookup"><span data-stu-id="14957-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="14957-282">Créer une règle de publication Web pour l’URL de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="14957-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="14957-283">Ouvrez votre interface de proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="14957-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="14957-284">Vous devez Rechercher l’emplacement dans l’interface dans lequel vous créez vos règles de publication Web, puis choisir l’option **nouveau** ou **créer** (il peut s’agir d’un menu ou d’un onglet, en fonction de votre configuration de proxy inverse).</span><span class="sxs-lookup"><span data-stu-id="14957-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="14957-285">Vous recherchez l’option permettant de créer une règle de publication Web.</span><span class="sxs-lookup"><span data-stu-id="14957-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="14957-286">En règle générale, vous devez entrer les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="14957-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="14957-287">**Name**: nom de votre règle</span><span class="sxs-lookup"><span data-stu-id="14957-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="14957-288">**Action**de la règle : dans ce cas, il s’agit d’une règle d' **autorisation** , que vous laissez passer par un proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="14957-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="14957-289">La règle ou l’option de **publication** que vous choisissez doit être **un seul site Web ou équilibreur de charge**.</span><span class="sxs-lookup"><span data-stu-id="14957-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="14957-290">Cela doit être **SSL** pour l’accès externe, choisissez cette option.</span><span class="sxs-lookup"><span data-stu-id="14957-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="14957-291">Vous devrez publier un chemin d’accès pour la **publication interne**, et entrer le nom de domaine complet (FQDN) des services Web externes sur le programme d’équilibrage de charge de votre pool frontal (ou le nom de domaine complet de l’équilibreur de charge du pool directeur s’il en existe un), par exemple, sfb_pool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="14957-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="14957-292">Vous devez taper \*\* / \*\*\* comme chemin d’accès à publier, mais vous devez également **transférer l’en-tête d’hôte d’origine**.</span><span class="sxs-lookup"><span data-stu-id="14957-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="14957-293">Il y aura une option pour les détails du **nom public ou externe** ou des informations.</span><span class="sxs-lookup"><span data-stu-id="14957-293">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="14957-294">Il s’agit de l’endroit où vous pouvez entrer :</span><span class="sxs-lookup"><span data-stu-id="14957-294">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="14957-295">**Accepter les demandes**, mais il doit s’agir du nom de domaine.</span><span class="sxs-lookup"><span data-stu-id="14957-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="14957-296">Pour le **nom**, vous devez entrer **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="14957-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="14957-297"><sipdomain>(il s’agit de l’URL du service de découverte automatique externe).</span><span class="sxs-lookup"><span data-stu-id="14957-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="14957-298">À présent, si vous créez une règle pour l’URL des services Web externes sur le pool frontal, vous devez taper le nom de domaine complet (FQDN) des services Web externes sur votre pool frontal (par exemple, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="14957-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="14957-299">Il y aura une option **path** , et vous devrez entrer \*\* / \*\*\* ici.</span><span class="sxs-lookup"><span data-stu-id="14957-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="14957-300">Vous devrez sélectionner un **écouteur SSL** avec votre certificat public à jour.</span><span class="sxs-lookup"><span data-stu-id="14957-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="14957-301">La **délégation de l’authentification** doit être définie sur **aucune délégation**, mais l’authentification client directe **doit** être autorisée.</span><span class="sxs-lookup"><span data-stu-id="14957-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="14957-302">La règle doit être définie sur **tous les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="14957-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="14957-303">Il doit s’agir de toutes les informations dont vous avez besoin pour créer cette règle et vous permettre de continuer.</span><span class="sxs-lookup"><span data-stu-id="14957-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="14957-304">Vous devez vous assurer que l' **en-tête d’hôte d’origine** est transféré.</span><span class="sxs-lookup"><span data-stu-id="14957-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="14957-305">Les ports du **serveur Web** devront également être définis, vous devrez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="14957-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="14957-306">**Rediriger les demandes vers le port http** et le numéro de port doit être **8080**.</span><span class="sxs-lookup"><span data-stu-id="14957-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="14957-307">**Rediriger les demandes vers le port SSL** et le numéro de port doit être **4443**.</span><span class="sxs-lookup"><span data-stu-id="14957-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="14957-308">Lorsque tout est configuré, vous devez enregistrer ou appliquer ces éléments, puis vous souhaitez tester la règle.</span><span class="sxs-lookup"><span data-stu-id="14957-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="14957-309">Créer une règle de publication Web pour le port 80 (facultatif)</span><span class="sxs-lookup"><span data-stu-id="14957-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="14957-310">Ouvrez votre interface de proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="14957-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="14957-311">Vous devez Rechercher l’emplacement dans l’interface dans lequel vous créez vos règles de publication Web, puis choisir l’option **nouveau** ou **créer** (il peut s’agir d’un menu ou d’un onglet, en fonction de votre configuration de proxy inverse).</span><span class="sxs-lookup"><span data-stu-id="14957-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="14957-312">Vous recherchez l’option permettant de créer une règle de publication Web.</span><span class="sxs-lookup"><span data-stu-id="14957-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="14957-313">En règle générale, vous devez entrer les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="14957-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="14957-314">**Name**: nom de votre règle</span><span class="sxs-lookup"><span data-stu-id="14957-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="14957-315">**Action**de la règle : dans ce cas, il s’agit d’une règle d' **autorisation** , que vous laissez passer par un proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="14957-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="14957-316">La règle ou l’option de **publication** que vous choisissez doit être **un seul site Web ou équilibreur de charge**.</span><span class="sxs-lookup"><span data-stu-id="14957-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="14957-317">Cela doit être une **connexion non sécurisée pour la connexion au serveur Web publié ou à la batterie de serveurs**.</span><span class="sxs-lookup"><span data-stu-id="14957-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="14957-318">Vous allez devoir publier un chemin d’accès pour la **publication interne**, et entrez le nom de domaine complet (FQDN) de l' **adresse IP virtuelle** de l’équilibreur de charge de votre pool frontal, par exemple, sfb_pool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="14957-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="14957-319">Vous devez taper \*\* / \*\*\* comme chemin d’accès à publier, mais vous devez également **transférer l’en-tête d’hôte d’origine**.</span><span class="sxs-lookup"><span data-stu-id="14957-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="14957-320">Il y aura une option pour les détails du **nom public ou externe** ou des informations.</span><span class="sxs-lookup"><span data-stu-id="14957-320">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="14957-321">Il s’agit de l’endroit où vous pouvez entrer :</span><span class="sxs-lookup"><span data-stu-id="14957-321">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="14957-322">**Accepter les demandes**, mais il doit s’agir du nom de domaine.</span><span class="sxs-lookup"><span data-stu-id="14957-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="14957-323">Pour le **nom**, vous devez entrer **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="14957-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="14957-324"><sipdomain>(il s’agit de l’URL du service de découverte automatique externe).</span><span class="sxs-lookup"><span data-stu-id="14957-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="14957-325">Il y aura une option **path** , et vous devrez entrer \*\* / \*\*\* ici.</span><span class="sxs-lookup"><span data-stu-id="14957-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="14957-326">Vous devrez sélectionner un port d’écoute Web ou autoriser votre proxy inverse à en créer un pour vous.</span><span class="sxs-lookup"><span data-stu-id="14957-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="14957-327">La **délégation de l’authentification** doit être définie sur **aucune délégation**, mais l’authentification client directe ne **doit pas** être autorisée.</span><span class="sxs-lookup"><span data-stu-id="14957-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="14957-328">La règle doit être définie sur **tous les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="14957-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="14957-329">Il doit s’agir de toutes les informations dont vous avez besoin pour créer cette règle et vous permettre de continuer.</span><span class="sxs-lookup"><span data-stu-id="14957-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="14957-330">Les ports de **serveur Web** doivent être définis, vous devez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="14957-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="14957-331">**Rediriger les demandes vers le port http** et le numéro de port doit être **8080**.</span><span class="sxs-lookup"><span data-stu-id="14957-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="14957-332">**Rediriger les demandes vers le port SSL** et le numéro de port doit être **4443**.</span><span class="sxs-lookup"><span data-stu-id="14957-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="14957-333">Lorsque tout est configuré, vous devez enregistrer ou appliquer ces éléments, puis vous souhaitez tester la règle.</span><span class="sxs-lookup"><span data-stu-id="14957-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="14957-334">Configurer la découverte automatique pour la mobilité avec les déploiements hybrides</span><span class="sxs-lookup"><span data-stu-id="14957-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="14957-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="14957-335"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="14957-336">Les environnements hybrides dans Skype entreprise Server sont des environnements qui combinent un environnement local et un environnement O365.</span><span class="sxs-lookup"><span data-stu-id="14957-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="14957-337">Lorsque vous utilisez Skype entreprise Server dans un environnement hybride, le service de découverte automatique doit pouvoir localiser un utilisateur dans l’un de ces environnements.</span><span class="sxs-lookup"><span data-stu-id="14957-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="14957-338">Pour permettre aux clients mobiles de découvrir où se trouve un utilisateur, le service de découverte automatique doit être configuré avec une nouvelle URL (Uniform Resource Locator).</span><span class="sxs-lookup"><span data-stu-id="14957-338">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="14957-339">Voici comment procéder :</span><span class="sxs-lookup"><span data-stu-id="14957-339">The steps are:</span></span>
  
1. <span data-ttu-id="14957-340">Ouvrez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="14957-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="14957-341">Exécutez la commande suivante pour obtenir la valeur de l’attribut **ProxyFQDN** pour votre environnement Skype entreprise Server :</span><span class="sxs-lookup"><span data-stu-id="14957-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="14957-342">Ensuite, dans la fenêtre du shell, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="14957-342">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="14957-343">Où [identity] est remplacé par le nom de domaine de l’espace d’adresses SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="14957-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="14957-344">Tester votre déploiement de mobilité</span><span class="sxs-lookup"><span data-stu-id="14957-344">Test your Mobility deployment</span></span>
<span data-ttu-id="14957-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="14957-345"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="14957-346">Une fois que vous avez déployé Skype for Business Server Mobility service et Skype for Business Server Autodiscover Service, vous pouvez exécuter une transaction de test pour vous assurer que votre déploiement fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="14957-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="14957-347">Vous pouvez exécuter **test-CsUcwaConference** pour tester la capacité de deux utilisateurs à créer, rejoindre et communiquer dans une conférence.</span><span class="sxs-lookup"><span data-stu-id="14957-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="14957-348">Vous aurez besoin de deux utilisateurs (réel ou test) et de leurs informations d’identification complètes pour effectuer ce test.</span><span class="sxs-lookup"><span data-stu-id="14957-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="14957-349">Cette commande fonctionne pour les clients Skype entreprise, ainsi que pour les clients Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="14957-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="14957-350">Pour les clients Lync Server 2010 sur Skype entreprise Server 2015, vous devez exécuter **test-CsMcxP2PIM** pour tester.</span><span class="sxs-lookup"><span data-stu-id="14957-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="14957-351">Vos utilisateurs de Lync Server 2010 devront toujours être des utilisateurs réels ou des utilisateurs de test prédéfinis, et vous aurez besoin de leurs informations d’identification de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="14957-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="14957-352">La prise en charge de MCX (Mobility service) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="14957-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="14957-353">Tous les clients mobiles Skype entreprise actuels utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts.</span><span class="sxs-lookup"><span data-stu-id="14957-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="14957-354">Les utilisateurs avec des clients hérités qui utilisent MCX devront effectuer une mise à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="14957-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="14957-355">Tester la Conférence pour les clients mobiles Skype entreprise et Lync 2013</span><span class="sxs-lookup"><span data-stu-id="14957-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="14957-356">Ouvrez une session en tant que membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="14957-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="14957-357">Démarrez **Skype entreprise Server Management Shell** (vous pouvez taper le nom dans la recherche ou accéder à **tous les programmes** et sélectionnez-le).</span><span class="sxs-lookup"><span data-stu-id="14957-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="14957-358">Sur la ligne de commande, entrez :</span><span class="sxs-lookup"><span data-stu-id="14957-358">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="14957-359">Il est également possible de définir des informations d’identification dans un script et de les transmettre à la cmdlet Test.</span><span class="sxs-lookup"><span data-stu-id="14957-359">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="14957-360">Nous avons un exemple de ce qui suit.</span><span class="sxs-lookup"><span data-stu-id="14957-360">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="14957-361">Conférence de test pour les clients mobiles Lync 2010</span><span class="sxs-lookup"><span data-stu-id="14957-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="14957-362">La prise en charge de MCX (Mobility service) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="14957-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="14957-363">Tous les clients mobiles Skype entreprise actuels utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts.</span><span class="sxs-lookup"><span data-stu-id="14957-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="14957-364">Les utilisateurs avec des clients hérités qui utilisent MCX devront effectuer une mise à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="14957-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="14957-365">Ouvrez une session en tant que membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="14957-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="14957-366">Démarrez **Skype entreprise Server Management Shell** (vous pouvez taper le nom dans la recherche ou accéder à **tous les programmes** et sélectionnez-le).</span><span class="sxs-lookup"><span data-stu-id="14957-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="14957-367">Sur la ligne de commande, entrez :</span><span class="sxs-lookup"><span data-stu-id="14957-367">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="14957-368">Il est également possible de définir des informations d’identification dans un script et de les transmettre à la cmdlet Test.</span><span class="sxs-lookup"><span data-stu-id="14957-368">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="14957-369">Nous avons un exemple de ce qui suit.</span><span class="sxs-lookup"><span data-stu-id="14957-369">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="14957-370">Pour revoir les procédures de commande, vous pouvez consulter [test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) et [test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="14957-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="14957-371">Configurer les notifications de type push</span><span class="sxs-lookup"><span data-stu-id="14957-371">Configure for push notifications</span></span>
<span data-ttu-id="14957-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="14957-372"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="14957-373">Les notifications de type diffuser, sous la forme de badges, d’icônes ou d’alertes, peuvent être envoyées à un appareil mobile même lorsque l’application Skype ou Lync est inactive.</span><span class="sxs-lookup"><span data-stu-id="14957-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="14957-374">Mais que sont les notifications de type transmission ?</span><span class="sxs-lookup"><span data-stu-id="14957-374">But what are push notifications?</span></span> <span data-ttu-id="14957-375">Il s’agit d’alertes d’événement, comme une invitation de messagerie instantanée nouvelle ou manquée, ou pour une messagerie vocale reçue.</span><span class="sxs-lookup"><span data-stu-id="14957-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="14957-376">Le service de mobilité Skype entreprise Server envoie ces notifications au service de notifications poussés de Skype entreprise Server basé sur le Cloud, qui envoie ensuite les notifications au service de notifications Microsoft (MSNS) pour les utilisateurs de Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="14957-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="14957-377">Cette fonctionnalité est identique à celle de Lync Server 2013, mais si vous disposez d’un serveur Skype entreprise, vous devez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="14957-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="14957-378">Pour un serveur Edge Skype entreprise Server, ajoutez un nouveau fournisseur d’hébergement, Microsoft Skype entreprise Online, puis configurez la Fédération des fournisseurs d’hébergement entre votre organisation et Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="14957-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="14957-379">Activez les notifications de type transmission en exécutant la cmdlet **Set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="14957-379">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="14957-380">Par défaut, les notifications push sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="14957-380">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="14957-381">Testez la configuration de votre Fédération et les notifications de transmission.</span><span class="sxs-lookup"><span data-stu-id="14957-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="14957-382">Configuration de votre serveur Microsoft Skype entreprise Edge pour les notifications de type transmission</span><span class="sxs-lookup"><span data-stu-id="14957-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="14957-383">Ouvrez une session avec un compte qui est membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype for Business Server Management Shell** et **OCSCore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="14957-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="14957-384">Démarrez **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="14957-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="14957-385">Ajoutez un fournisseur d’hébergement Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="14957-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="14957-386">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="14957-386">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="14957-387">Vous ne pouvez pas avoir plus d’une relation de Fédération avec un seul fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="14957-387">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="14957-388">Par conséquent, si vous avez déjà configuré un fournisseur d’hébergement qui a une relation de Fédération avec sipfed.online.lync.com, n’ajoutez pas un autre fournisseur d’hébergement pour lui, même si l’identité du fournisseur d’hébergement est différente de SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="14957-388">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="14957-389">Configurez la Fédération des fournisseurs d’hébergement entre votre organisation et le service de notifications par transmission Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="14957-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="14957-390">Sur la ligne de commande, vous devez taper :</span><span class="sxs-lookup"><span data-stu-id="14957-390">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="14957-391">Activer les notifications de type transmission</span><span class="sxs-lookup"><span data-stu-id="14957-391">Enable push notifications</span></span>

1. <span data-ttu-id="14957-392">Ouvrez une session avec un compte qui est membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype for Business Server Management Shell** et **OCSCore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="14957-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="14957-393">Démarrez **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="14957-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="14957-394">Activer les notifications de type transmission :</span><span class="sxs-lookup"><span data-stu-id="14957-394">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="14957-395">Activer la Fédération :</span><span class="sxs-lookup"><span data-stu-id="14957-395">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="14957-396">Fédération de test et notifications de type transmission</span><span class="sxs-lookup"><span data-stu-id="14957-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="14957-397">Ouvrez une session avec un compte qui est membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype for Business Server Management Shell** et **OCSCore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="14957-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="14957-398">Démarrez **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="14957-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="14957-399">Testez la configuration de la Fédération :</span><span class="sxs-lookup"><span data-stu-id="14957-399">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="14957-400">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="14957-400">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="14957-401">Testez vos notifications d’envoi :</span><span class="sxs-lookup"><span data-stu-id="14957-401">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="14957-402">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="14957-402">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="14957-403">Configurer la stratégie de mobilité</span><span class="sxs-lookup"><span data-stu-id="14957-403">Configure Mobility policy</span></span>
<span data-ttu-id="14957-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="14957-404"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="14957-405">Vous avez la possibilité de contacter Skype entreprise Server pour déterminer qui peut utiliser votre service de mobilité, appeler via le bureau, une voix sur IP (VoIP) ou une vidéo, et si WiFi sera requis pour la voix ou la vidéo.</span><span class="sxs-lookup"><span data-stu-id="14957-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="14957-406">Appel via le bureau permet à un utilisateur mobile d’utiliser son numéro de téléphone professionnel au lieu de son numéro de téléphone mobile lors de l’envoi et de la réception d’appels.</span><span class="sxs-lookup"><span data-stu-id="14957-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="14957-407">La personne à l’autre bout de la ligne ne verra pas le numéro de téléphone portable de l’utilisateur mobile, et elle permettra à l’utilisateur d’envoyer des frais d’appels sortants.</span><span class="sxs-lookup"><span data-stu-id="14957-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="14957-408">Lors de la configuration de VoIP et de vidéo, les utilisateurs peuvent prendre et effectuer des appels VoIP et vidéo.</span><span class="sxs-lookup"><span data-stu-id="14957-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="14957-409">Les paramètres de l’utilisation WiFi déterminent si l’appareil mobile d’un utilisateur doit utiliser un réseau WiFi via un réseau de données cellulaires.</span><span class="sxs-lookup"><span data-stu-id="14957-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="14957-410">La mobilité, l’appel via le bureau et les fonctionnalités VoIP et vidéo sont toutes activées par défaut.</span><span class="sxs-lookup"><span data-stu-id="14957-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="14957-411">Le paramètre pour exiger WiFi pour VoIP et vidéo est désactivé.</span><span class="sxs-lookup"><span data-stu-id="14957-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="14957-412">Un administrateur a la possibilité de le modifier, de manière globale, par site ou par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="14957-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="14957-413">Pour pouvoir utiliser les fonctionnalités de mobilité et d’appel via le bureau, les utilisateurs doivent être :</span><span class="sxs-lookup"><span data-stu-id="14957-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="14957-414">Activé pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="14957-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="14957-415">Activé pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="14957-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="14957-416">Affectation d’une stratégie de mobilité dont l’option **EnableMobility** a la valeur **true**.</span><span class="sxs-lookup"><span data-stu-id="14957-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="14957-417">Pour que les utilisateurs puissent utiliser l’appel via le bureau, ils doivent également être :</span><span class="sxs-lookup"><span data-stu-id="14957-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="14957-418">Affectation d’une stratégie de voix pour laquelle l’option **activer la sonnerie simultanée de téléphones** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="14957-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="14957-419">Affectation d’une stratégie de mobilité dont la valeur de **EnableOutsideVoice** est définie sur **true**.</span><span class="sxs-lookup"><span data-stu-id="14957-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="14957-420">Les utilisateurs qui ne sont pas activés pour voix entreprise peuvent utiliser leur appareil mobile pour passer des appels VoIP Skype à Skype ou participer à des conférences à l’aide du lien Cliquer pour rejoindre les appareils mobiles, si les options appropriées sont définies pour la stratégie de voix à laquelle ils sont associés. avec.</span><span class="sxs-lookup"><span data-stu-id="14957-420">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="14957-421">Vous trouverez plus de détails dans la rubrique planification.</span><span class="sxs-lookup"><span data-stu-id="14957-421">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="14957-422">Modifier la stratégie de mobilité globale</span><span class="sxs-lookup"><span data-stu-id="14957-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="14957-423">Ouvrez une session avec un compte qui est membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype for Business Server Management Shell** et **OCSCore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="14957-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="14957-424">Démarrez **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="14957-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="14957-425">Désactivez l’accès à la mobilité et appelez via le Bureau de façon globale en tapant :</span><span class="sxs-lookup"><span data-stu-id="14957-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="14957-426">Vous pouvez désactiver l’appel via le bureau sans désactiver l’accès à la mobilité.</span><span class="sxs-lookup"><span data-stu-id="14957-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="14957-427">Mais vous ne pouvez pas désactiver la mobilité sans désactiver l’appel via le bureau.</span><span class="sxs-lookup"><span data-stu-id="14957-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="14957-428">Pour plus d’informations, consultez [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="14957-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="14957-429">Modifier la stratégie de mobilité par site</span><span class="sxs-lookup"><span data-stu-id="14957-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="14957-430">Ouvrez une session avec un compte qui est membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype for Business Server Management Shell** et **OCSCore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="14957-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="14957-431">Démarrez **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="14957-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="14957-432">Vous pouvez créer une stratégie au niveau du site, désactiver VoIP et la vidéo, activer l’utilisation de WiFi pour l’audio IP et exiger la vidéo Wi-Fi pour IP par site.</span><span class="sxs-lookup"><span data-stu-id="14957-432">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="14957-433">Type :</span><span class="sxs-lookup"><span data-stu-id="14957-433">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="14957-434">Pour plus d’informations, consultez la rubrique [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="14957-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="14957-435">Modifier la stratégie de mobilité par utilisateur</span><span class="sxs-lookup"><span data-stu-id="14957-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="14957-436">Ouvrez une session avec un compte qui est membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype for Business Server Management Shell** et **OCSCore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="14957-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="14957-437">Démarrez **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="14957-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="14957-438">Créez des stratégies de mobilité au niveau de l’utilisateur et désactivez la mobilité et l’appel via le bureau par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="14957-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="14957-439">Type :</span><span class="sxs-lookup"><span data-stu-id="14957-439">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="14957-440">Un autre exemple avec des exemples de données :</span><span class="sxs-lookup"><span data-stu-id="14957-440">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="14957-441">Vous pouvez désactiver l’appel via le bureau sans désactiver l’accès à la mobilité.</span><span class="sxs-lookup"><span data-stu-id="14957-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="14957-442">Mais vous ne pouvez pas désactiver la mobilité sans désactiver l’appel via le bureau.</span><span class="sxs-lookup"><span data-stu-id="14957-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

