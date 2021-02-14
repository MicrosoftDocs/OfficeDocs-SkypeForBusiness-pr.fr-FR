---
title: Déployer et configurer la mobilité pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Cet article vous explique comment configurer une installation Skype Entreprise Server existante pour utiliser le service de mobilité, ce qui permet à vos appareils mobiles de tirer parti des fonctionnalités de mobilité de Skype Entreprise Server.
ms.openlocfilehash: 420d34dcf1406df776e438e01007770e515c0d4a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820894"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="a271e-103">Déployer et configurer la mobilité pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a271e-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="a271e-104">Cet article vous explique comment configurer une installation Skype Entreprise Server existante pour utiliser le service de mobilité, ce qui permet à vos appareils mobiles de tirer parti des fonctionnalités de mobilité de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a271e-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="a271e-105">Après avoir consulté l’article [Plan for Mobility for Skype for Business Server,](../plan-your-deployment/mobility.md) vous devriez être prêt à suivre les étapes ci-dessous pour déployer la mobilité dans votre environnement Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a271e-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="a271e-106">Les étapes sont les suivantes (et nous allons inclure dans ce tableau une liste d’autorisations) :</span><span class="sxs-lookup"><span data-stu-id="a271e-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="a271e-107">**Étape**</span><span class="sxs-lookup"><span data-stu-id="a271e-107">**Phase**</span></span>|<span data-ttu-id="a271e-108">**Autorisations**</span><span class="sxs-lookup"><span data-stu-id="a271e-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a271e-109">Créer des enregistrements DNS</span><span class="sxs-lookup"><span data-stu-id="a271e-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="a271e-110">Admins du domaine</span><span class="sxs-lookup"><span data-stu-id="a271e-110">Domain Admins</span></span>  <br/> <span data-ttu-id="a271e-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="a271e-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="a271e-112">Modifier les certificats</span><span class="sxs-lookup"><span data-stu-id="a271e-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="a271e-113">Administrateur local</span><span class="sxs-lookup"><span data-stu-id="a271e-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="a271e-114">Configurer le proxy inverse</span><span class="sxs-lookup"><span data-stu-id="a271e-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="a271e-115">Administrateur local</span><span class="sxs-lookup"><span data-stu-id="a271e-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="a271e-116">Configurer la découverte automatique pour la mobilité avec des déploiements hybrides</span><span class="sxs-lookup"><span data-stu-id="a271e-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="a271e-117">Admins du domaine</span><span class="sxs-lookup"><span data-stu-id="a271e-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="a271e-118">Tester votre déploiement de mobilité</span><span class="sxs-lookup"><span data-stu-id="a271e-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="a271e-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a271e-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="a271e-120">Configurer les notifications de type push</span><span class="sxs-lookup"><span data-stu-id="a271e-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="a271e-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a271e-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="a271e-122">Configurer la stratégie de mobilité</span><span class="sxs-lookup"><span data-stu-id="a271e-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="a271e-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a271e-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="a271e-124">Toutes les sections suivantes contiennent des étapes qui supposent que vous avez lu la rubrique Planification.</span><span class="sxs-lookup"><span data-stu-id="a271e-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="a271e-125">Si vous êtes déconcertant, n’hésitez pas à consulter les informations qu’il vous reste.</span><span class="sxs-lookup"><span data-stu-id="a271e-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="a271e-126">La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a271e-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a271e-127">Tous les clients mobiles Skype Entreprise actuels utilisent déjà l’API web de communications unifiées (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts.</span><span class="sxs-lookup"><span data-stu-id="a271e-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="a271e-128">Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="a271e-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="a271e-129">Créer des enregistrements DNS</span><span class="sxs-lookup"><span data-stu-id="a271e-129">Create DNS records</span></span>
<span data-ttu-id="a271e-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="a271e-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="a271e-131">Vous en avez peut-être déjà dans le cadre de votre environnement Skype Entreprise Server, mais vous devez créer les enregistrements suivants pour que la découverte automatique fonctionne :</span><span class="sxs-lookup"><span data-stu-id="a271e-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="a271e-132">Un enregistrement DNS interne pour prendre en charge les utilisateurs mobiles qui se connectent à partir du réseau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a271e-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="a271e-133">Un enregistrement DNS externe (ou public) pour prendre en charge les utilisateurs mobiles qui se connectent depuis l’extérieur du réseau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a271e-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="a271e-134">Ces enregistrements peuvent être des noms A (hôte) ou des enregistrements CNAME (vous n’avez pas besoin d’effectuer les deux, nous allons simplement inclure les étapes pour tous les éléments ici).</span><span class="sxs-lookup"><span data-stu-id="a271e-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="a271e-135">Créer un enregistrement CNAME DNS interne</span><span class="sxs-lookup"><span data-stu-id="a271e-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="a271e-136">Connectez-vous à un serveur DNS de votre réseau qui est membre du groupe **Administrateurs** du domaine ou du groupe **DnsAdmins.**</span><span class="sxs-lookup"><span data-stu-id="a271e-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="a271e-137">Cliquez **sur** Démarrer, Choisissez outils  d’administration **(vous** devrez peut-être le rechercher s’il ne s’agit pas d’une option du menu Démarrer), puis cliquez sur **DNS** pour ouvrir le logiciel en ligne d’administration DNS.</span><span class="sxs-lookup"><span data-stu-id="a271e-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="a271e-138">Dans le volet gauche de la fenêtre de la console, vous devez aller dans le domaine qui est le domicile de vos serveurs frontux Skype Entreprise Server, puis développer les **zones** de recherche vers l’avant à cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="a271e-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="a271e-139">Prenez un moment pour voir lequel des deux cas suivants vous avez :</span><span class="sxs-lookup"><span data-stu-id="a271e-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="a271e-140">Tout enregistrement A ou AAAA d’hôte pour votre serveur frontal (Standard ou Entreprise) ou pool(s) frontal(s).</span><span class="sxs-lookup"><span data-stu-id="a271e-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="a271e-141">Tout enregistrement A ou AAAA d’hôte pour un directeur ou un pool directeur (configuration facultative que vous pouvez avoir dans votre déploiement).</span><span class="sxs-lookup"><span data-stu-id="a271e-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="a271e-142">Une fois que vous avez noté cela, cliquez avec le bouton droit sur votre nom de domaine SIP, puis sélectionnez **Nouvel alias (CNAME)** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="a271e-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="a271e-143">Dans la boîte de texte Nom **d’alias,** tapez lyncdiscoverinternal comme nom d’hôte, pour l’URL du service de découverte automatique interne.</span><span class="sxs-lookup"><span data-stu-id="a271e-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="a271e-144">Dans le nom de domaine complet **(FQDN** pour l’hôte cible), vous devez taper ou parcourir le nom de domaine complet des services web internes pour votre pool frontal (ou serveur frontal unique, ou pool directeur ou directeur), identifié à l’étape 4 ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="a271e-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="a271e-145">Cliquez sur OK lorsqu’il est entré.</span><span class="sxs-lookup"><span data-stu-id="a271e-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="a271e-146">Vous devez créer un enregistrement CNAME de découverte automatique dans la zone de recherche avant pour chaque domaine SIP pris en charge dans votre environnement Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a271e-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="a271e-147">Créer un enregistrement CNAME DNS externe</span><span class="sxs-lookup"><span data-stu-id="a271e-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="a271e-148">Ces étapes sont génériques, car nous ne pouvons pas savoir quel fournisseur DNS public vous utilisez, mais nous voulons quand même vous aider. Connectez-vous à votre fournisseur DNS public avec un compte qui pourra y effectuer de nouveaux enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="a271e-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="a271e-149">À ce stade, un domaine SIP doit déjà exister pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a271e-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="a271e-150">Développez **la zone de recherche avant** pour ce domaine SIP ou ouvrez-la.</span><span class="sxs-lookup"><span data-stu-id="a271e-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="a271e-151">Prenez un moment pour voir lequel des deux cas suivants vous avez :</span><span class="sxs-lookup"><span data-stu-id="a271e-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="a271e-152">Tout enregistrement A ou AAAA d’hôte pour votre serveur frontal (Standard ou Entreprise) ou pool(s) frontal(s).</span><span class="sxs-lookup"><span data-stu-id="a271e-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="a271e-153">Tout enregistrement A ou AAAA d’hôte pour un directeur ou un pool directeur (configuration facultative que vous pouvez avoir dans votre déploiement).</span><span class="sxs-lookup"><span data-stu-id="a271e-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="a271e-154">Une fois que vous avez ces informations, vous devez être en mesure de sélectionner une option pour créer un **nouvel alias (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="a271e-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="a271e-155">Maintenant que vous devez être en mesure d’entrer un nom **d’alias,** vous devez entrer lyncdiscover ici pour l’URL du service de découverte automatique externe.</span><span class="sxs-lookup"><span data-stu-id="a271e-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="a271e-156">Ensuite, il doit y avoir une zone à entrer dans un nom de domaine général pour l’hôte cible **;** il doit s’agit du nom de domaine général de votre pool frontal (ou serveur frontal unique, ou pool directeur ou directeur), identifié à l’étape 3 ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="a271e-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="a271e-157">Vous devrez peut-être enregistrer ici, ou si vous devez créer des enregistrements CNAME supplémentaires dans la zone de recherche avant de chaque domaine SIP de votre environnement Skype Entreprise Server, vous devez le faire, mais une fois prêt, enregistrez votre travail.</span><span class="sxs-lookup"><span data-stu-id="a271e-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="a271e-158">Créer un enregistrement DNS A interne</span><span class="sxs-lookup"><span data-stu-id="a271e-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="a271e-159">Connectez-vous à un serveur DNS de votre réseau qui est membre du groupe **Administrateurs** du domaine ou du groupe **DnsAdmins.**</span><span class="sxs-lookup"><span data-stu-id="a271e-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="a271e-160">Cliquez **sur** Démarrer, Choisissez outils  d’administration **(vous** devrez peut-être le rechercher s’il ne s’agit pas d’une option du menu Démarrer), puis cliquez sur **DNS** pour ouvrir le logiciel en ligne d’administration DNS.</span><span class="sxs-lookup"><span data-stu-id="a271e-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="a271e-161">Dans le volet gauche de la fenêtre de la console, vous devez aller dans le domaine qui est le domicile de vos serveurs frontux Skype Entreprise Server, puis développer les **zones** de recherche vers l’avant à cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="a271e-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="a271e-162">Prenez un moment pour voir lequel des deux cas suivants vous avez :</span><span class="sxs-lookup"><span data-stu-id="a271e-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="a271e-163">Tout enregistrement A ou AAAA d’hôte pour votre serveur frontal (Standard ou Entreprise) ou pool(s) frontal(s).</span><span class="sxs-lookup"><span data-stu-id="a271e-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="a271e-164">Tout enregistrement A ou AAAA d’hôte pour un directeur ou un pool directeur (configuration facultative que vous pouvez avoir dans votre déploiement).</span><span class="sxs-lookup"><span data-stu-id="a271e-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="a271e-165">Une fois que vous avez noté cela, cliquez avec le bouton droit sur votre nom de domaine SIP, puis choisissez Nouvel hôte **(A ou AAAA)** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="a271e-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="a271e-166">Dans la **boîte de** texte Nom, tapez lyncdiscoverinternal pour votre nom d’hôte, pour l’URL du service de découverte automatique interne.</span><span class="sxs-lookup"><span data-stu-id="a271e-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="a271e-167">Dans la boîte de texte Adresse **IP,** tapez l’adresse IP des services web internes pour votre pool frontal (ou serveur frontal unique, ou pool directeur ou directeur), identifiée à l’étape 4 ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="a271e-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="a271e-168">Lorsque cela est terminé, cliquez sur **Ajouter** un hôte, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="a271e-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="a271e-169">Vous devez créer un nouvel enregistrement A ou AAAA de découverte automatique dans la zone de recherche avant pour chaque domaine SIP pris en charge dans votre environnement Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a271e-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="a271e-170">Pour ce faire, répétez les étapes 6 à 8 autant de fois que nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a271e-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="a271e-171">Lorsque vous avez terminé, cliquez sur **Terminé.**</span><span class="sxs-lookup"><span data-stu-id="a271e-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="a271e-172">Créer un enregistrement DNS A externe</span><span class="sxs-lookup"><span data-stu-id="a271e-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="a271e-173">Ces étapes sont génériques, car nous ne pouvons pas savoir quel fournisseur DNS public vous utilisez, mais nous voulons quand même vous aider. Connectez-vous à votre fournisseur DNS public avec un compte qui pourra y effectuer de nouveaux enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="a271e-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="a271e-174">À ce stade, un domaine SIP doit déjà exister pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a271e-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="a271e-175">Développez **la zone de recherche avant** pour ce domaine SIP ou ouvrez-la.</span><span class="sxs-lookup"><span data-stu-id="a271e-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="a271e-176">Prenez un moment pour voir lequel des deux cas suivants vous avez :</span><span class="sxs-lookup"><span data-stu-id="a271e-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="a271e-177">Tout enregistrement A ou AAAA d’hôte pour votre serveur frontal (Standard ou Entreprise) ou pool(s) frontal(s).</span><span class="sxs-lookup"><span data-stu-id="a271e-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="a271e-178">Tout enregistrement A ou AAAA d’hôte pour un directeur ou un pool directeur (configuration facultative que vous pouvez avoir dans votre déploiement).</span><span class="sxs-lookup"><span data-stu-id="a271e-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="a271e-179">Une fois que vous avez ces informations, vous devez être en mesure de sélectionner une option pour créer un nouvel hôte **A ou AAAA**.</span><span class="sxs-lookup"><span data-stu-id="a271e-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="a271e-180">Maintenant que vous devez être en mesure d’entrer un **nom,** vous devez entrer lyncdiscover ici pour l’URL du service de découverte automatique externe.</span><span class="sxs-lookup"><span data-stu-id="a271e-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="a271e-181">Ensuite, il doit y avoir une zone à entrer dans une adresse IP , il doit s’agit de **l’adresse** IP de votre pool frontal (ou serveur frontal unique, ou pool directeur ou directeur), identifiée à l’étape 3 ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="a271e-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="a271e-182">Vous devrez peut-être enregistrer ici, ou si vous devez créer des enregistrements A ou AAAA supplémentaires dans la zone de recherche avant de chaque domaine SIP de votre environnement Skype Entreprise Server, vous devez le faire, mais une fois prêt, enregistrez votre travail.</span><span class="sxs-lookup"><span data-stu-id="a271e-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="a271e-183">Modifier les certificats</span><span class="sxs-lookup"><span data-stu-id="a271e-183">Modify certificates</span></span>
<span data-ttu-id="a271e-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="a271e-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="a271e-185">Si vous avez des questions sur la planification des certificats, nous l’avons documenté dans notre article [Plan for Mobility for Skype for Business Server.](../plan-your-deployment/mobility.md)</span><span class="sxs-lookup"><span data-stu-id="a271e-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="a271e-186">Une fois que vous aurez vérifié cela, nous vous passerons en revue les questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="a271e-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="a271e-187">Ai-je besoin de nouveaux certificats ?</span><span class="sxs-lookup"><span data-stu-id="a271e-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="a271e-188">Demande de nouveaux certificats auprès de votre autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="a271e-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="a271e-189">Mise à jour de vos certificats sur place avec les remplacements à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a271e-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="a271e-190">Vérification des certificats à l’aide du snapin Certificats dans la console MMC (Microsoft Management Console).</span><span class="sxs-lookup"><span data-stu-id="a271e-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="a271e-191">Ai-je besoin de nouveaux certificats ?</span><span class="sxs-lookup"><span data-stu-id="a271e-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="a271e-192">Tout d’abord, vous devrez peut-être vérifier et voir quels certificats sont en place, et s’ils ont ou non les entrées dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="a271e-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="a271e-193">Pour ce faire, vous devez vous connecter à Skype Entreprise Server avec un compte administrateur local.</span><span class="sxs-lookup"><span data-stu-id="a271e-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="a271e-194">Ce compte peut également avoir des droits sur l’autorité de certification émettrice pour certaines de ces étapes.</span><span class="sxs-lookup"><span data-stu-id="a271e-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="a271e-195">Ouvrez Skype Entreprise Server Management Shell (vous pouvez utiliser la recherche pour le trouver si vous ne l’avez pas épinglé à votre menu Démarrer ou à la barre des tâches).</span><span class="sxs-lookup"><span data-stu-id="a271e-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="a271e-196">Il sera essentiel pour vous de savoir quels certificats ont été affectés avant d’essayer d’ajouter un certificat mis à jour.</span><span class="sxs-lookup"><span data-stu-id="a271e-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="a271e-197">À partir de la commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="a271e-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="a271e-198">Les informations de l’étape 3 vous seront propres.</span><span class="sxs-lookup"><span data-stu-id="a271e-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="a271e-199">Vous devez l’examiner pour déterminer si vous avez un certificat unique affecté à plusieurs éléments ou si un certificat différent est affecté pour les différents composants qui en ont besoin.</span><span class="sxs-lookup"><span data-stu-id="a271e-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="a271e-200">Le **paramètre Use** vous indique comment un certificat est utilisé et le paramètre **Thumbprint** vous indique s’il s’agit du même certificat ou de plusieurs certificats.</span><span class="sxs-lookup"><span data-stu-id="a271e-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="a271e-201">Si vous avez les entrées SAN recommandées dans notre section Planification, vous êtes bon.</span><span class="sxs-lookup"><span data-stu-id="a271e-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="a271e-202">Si ce n’est pas le cas, vous devrez demander un nouveau certificat ou plusieurs certificats (selon votre configuration) auprès de votre autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="a271e-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="a271e-203">Demander un ou plusieurs nouveaux certificats auprès de votre autorité de certification</span><span class="sxs-lookup"><span data-stu-id="a271e-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="a271e-204">Une fois que vous avez vérifié les entrées SAN dont vous avez besoin, vous savez que vous avez un seul certificat **(après** avoir vérifié via les étapes ci-dessus) et vous avez appris que vous ne connaissez pas toutes les entrées dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="a271e-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="a271e-205">Une nouvelle demande de certificat doit être faite à votre ca.</span><span class="sxs-lookup"><span data-stu-id="a271e-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="a271e-206">Ouvrez Votre Skype Entreprise Server PowerShell :</span><span class="sxs-lookup"><span data-stu-id="a271e-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="a271e-207">Pour un SAN de service de découverte automatique manquant (en remplaçant le paramètre -Ca par votre propre chemin d’accès de l’autorité de certification) :</span><span class="sxs-lookup"><span data-stu-id="a271e-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="a271e-208">Maintenant, si vous avez plusieurs domaines SIP, vous ne pouvez pas utiliser le paramètre AllSipDomain comme dans l’exemple ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="a271e-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="a271e-209">Vous devez utiliser le paramètre DomainName à la place.</span><span class="sxs-lookup"><span data-stu-id="a271e-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="a271e-210">Lorsque vous utilisez le paramètre DomainName, vous devez définir le nom de domaine (FQDN) pour les enregistrements lyncdiscoverinternal et lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="a271e-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="a271e-211">Par exemple, (en remplaçant le paramètre -Ca par votre propre chemin d’accès à l’autorité de certification) :</span><span class="sxs-lookup"><span data-stu-id="a271e-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="a271e-212">Ou, après avoir vérifié les entrées SAN dont vous avez besoin, vous avez trouvé que vous avez plusieurs certificats qui ne sont pas toutes les **entrées** dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="a271e-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="a271e-213">Une nouvelle demande de certificat doit être faite à votre ca.</span><span class="sxs-lookup"><span data-stu-id="a271e-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="a271e-214">Ouvrez Votre Skype Entreprise Server PowerShell :</span><span class="sxs-lookup"><span data-stu-id="a271e-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="a271e-215">Pour un SAN de service de découverte automatique manquant (en remplaçant le paramètre -Ca par votre propre chemin d’accès de l’autorité de certification) :</span><span class="sxs-lookup"><span data-stu-id="a271e-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="a271e-216">Maintenant, si vous avez plusieurs domaines SIP, vous ne pouvez pas utiliser le paramètre AllSipDomain comme dans l’exemple ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="a271e-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="a271e-217">Vous devez utiliser le paramètre DomainName à la place.</span><span class="sxs-lookup"><span data-stu-id="a271e-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="a271e-218">Lorsque vous utilisez le paramètre DomainName, vous devez définir le nom de domaine (FQDN) pour les enregistrements lyncdiscoverinternal et lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="a271e-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="a271e-219">Par exemple (en remplaçant le paramètre -Ca par votre propre chemin d’accès à l’autorité de certification) :</span><span class="sxs-lookup"><span data-stu-id="a271e-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="a271e-220">Une fois que les nouveaux certificats ont été générés par l’ac, vous devez les affecter.</span><span class="sxs-lookup"><span data-stu-id="a271e-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a271e-221">Attribuer des certificats à l’aide de Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a271e-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="a271e-222">Selon ce que vous avez trouvé dans la section J’ai besoin de nouvelles certifications ci-dessus, vous devez **exécuter** l’une des procédures suivantes.</span><span class="sxs-lookup"><span data-stu-id="a271e-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="a271e-223">Si vous avez un seul certificat pour tout (les empreintes sont identiques), vous devez exécuter cette :</span><span class="sxs-lookup"><span data-stu-id="a271e-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="a271e-224">Si vous avez des certificats différents pour les éléments (les empreintes sont toutes différentes), exécutez-la à la place :</span><span class="sxs-lookup"><span data-stu-id="a271e-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="a271e-225">Affichage des certificats dans la console MMC (Microsoft Management Console)</span><span class="sxs-lookup"><span data-stu-id="a271e-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="a271e-226">Vous avez la possibilité d’examiner vos certificats à l’aide du logiciel en snap-in Certificats pour la MMC.</span><span class="sxs-lookup"><span data-stu-id="a271e-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="a271e-227">Il vous suffit de taper MMC dans la recherche et elle doit apparaître en tant qu’option d’application.</span><span class="sxs-lookup"><span data-stu-id="a271e-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="a271e-228">Pour ajouter le logiciel en un clin d’œil Certificats, vous devez cliquer sur **Fichier,** puis Ajouter/Supprimer un logiciel en un clin **d’œil...** (ou le raccourci clavier **Ctrl+M** fonctionne également).</span><span class="sxs-lookup"><span data-stu-id="a271e-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="a271e-229">**Les certificats** seront une option dans le volet de  gauche, sélectionnez-la, puis compte d’ordinateur dans la fenêtre fenêtre pop-up, puis **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a271e-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="a271e-230">Toujours dans la fenêtre pop-up, il est fort probable que vous le faisiez sur l’ordinateur qui est le domicile des certificats que vous devez examiner. Laissez donc la sélection sur l’ordinateur **local** si c’est le cas.</span><span class="sxs-lookup"><span data-stu-id="a271e-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="a271e-231">Si vous travaillez sur un ordinateur distant, modifiez la bouton d’radio sur **Un** autre  ordinateur, puis entrez le nom deqdn de cet ordinateur ou utilisez le bouton Parcourir pour rechercher cet ordinateur via AD.</span><span class="sxs-lookup"><span data-stu-id="a271e-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="a271e-232">Après avoir sélectionné l’ordinateur, vous  devez cliquer sur Terminer lorsque vous êtes prêt, puis **OK** pour ajouter le logiciel en snap-in à la MMC.</span><span class="sxs-lookup"><span data-stu-id="a271e-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="a271e-233">Développez la section **Certificats** dans le volet gauche de la MMC.</span><span class="sxs-lookup"><span data-stu-id="a271e-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="a271e-234">Développez **également le** dossier Personnel, puis sélectionnez **Certificats.**</span><span class="sxs-lookup"><span data-stu-id="a271e-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="a271e-235">Cela vous permet de voir les certificats dans ce magasin.</span><span class="sxs-lookup"><span data-stu-id="a271e-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="a271e-236">Vous devez localiser le certificat que vous souhaitez afficher, cliquer dessus avec le bouton droit, puis choisir **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="a271e-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a271e-237">Comment savoir quel certificat s’agit-il ?</span><span class="sxs-lookup"><span data-stu-id="a271e-237">How do you know what certificate this is?</span></span> <span data-ttu-id="a271e-238">Ce doit être le certificat unique affecté à tous les éléments de votre batterie de serveurs, ou vous pouvez avoir plusieurs certificats pour différents éléments, tels que default, Internal Web Services, etc., auquel cas vous devrez peut-être examiner plusieurs certificats.</span><span class="sxs-lookup"><span data-stu-id="a271e-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="a271e-239">Plusieurs certificats auront la même empreinte numérique.</span><span class="sxs-lookup"><span data-stu-id="a271e-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="a271e-240">Une fois que vous  avez obtenu l’affichage Certificat, choisissez **Détails**.</span><span class="sxs-lookup"><span data-stu-id="a271e-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="a271e-241">Cela vous permet de voir le nom de l’objet du certificat lorsque vous sélectionnez **Objet,** et le nom du sujet affecté et les propriétés associées sont affichés.</span><span class="sxs-lookup"><span data-stu-id="a271e-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="a271e-242">Vous devez également vérifier les entrées de **l’autre nom du** sujet.</span><span class="sxs-lookup"><span data-stu-id="a271e-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="a271e-243">Vous trouverez une ou plusieurs des informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a271e-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="a271e-244">Nom du pool ou nom du serveur unique s’il ne s’agit pas d’un pool.</span><span class="sxs-lookup"><span data-stu-id="a271e-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="a271e-245">Nom du serveur à qui le certificat est affecté.</span><span class="sxs-lookup"><span data-stu-id="a271e-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="a271e-246">Enregistrements d’URL simples, généralement meet et dialin.</span><span class="sxs-lookup"><span data-stu-id="a271e-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="a271e-247">Noms externes des services Web et internes des services Web (par exemple, webpool01.contoso.net, webpool01.contoso.com), en fonction des choix effectués dans le Générateur de topologie et les sélections de services Web surchargées.</span><span class="sxs-lookup"><span data-stu-id="a271e-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="a271e-248">S’il est déjà affecté, le lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="a271e-248">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="a271e-249">et lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="a271e-249">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="a271e-250">enregistrements.</span><span class="sxs-lookup"><span data-stu-id="a271e-250">records.</span></span>
    
     <span data-ttu-id="a271e-251">Vous devez vérifier plusieurs certificats si plusieurs certificats vous sont affectés (consultez la remarque ci-dessus).</span><span class="sxs-lookup"><span data-stu-id="a271e-251">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="a271e-252">Par conséquent, si vous trouvez lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="a271e-252">So, if you find lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="a271e-253">et lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="a271e-253">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="a271e-254">enregistrements, vous avez déjà configuré cette configuration.</span><span class="sxs-lookup"><span data-stu-id="a271e-254">records, you've got this configured already.</span></span> <span data-ttu-id="a271e-255">Vous pouvez fermer la MMC.</span><span class="sxs-lookup"><span data-stu-id="a271e-255">You can close the MMC.</span></span>
    
9. <span data-ttu-id="a271e-256">S’ils ne sont pas affectés, vous devrez soit effectuer une nouvelle demande de certificat (décrite ci-dessus), soit les installer après la demande (nous vous recommandons de suivre l’exemple PowerShell ci-dessus pour cela).</span><span class="sxs-lookup"><span data-stu-id="a271e-256">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="a271e-257">Configurer le proxy inverse</span><span class="sxs-lookup"><span data-stu-id="a271e-257">Configure the reverse proxy</span></span>
<span data-ttu-id="a271e-258"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="a271e-258"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="a271e-259">Les étapes ci-dessous ne sont pas destinées à être suivies exactement.</span><span class="sxs-lookup"><span data-stu-id="a271e-259">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="a271e-260">En effet, dans les versions précédentes du produit, nous vous avons parcourus, par exemple, en configurant TMG (Threat Management Gateway) et si vous n’utilisiez pas cette version, vous devrez trouver votre propre version à partir de là.</span><span class="sxs-lookup"><span data-stu-id="a271e-260">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="a271e-261">TMG n’est plus proposé par Microsoft en tant que produit et si vous devez encore le configurer, vous pouvez examiner les étapes [de Lync Server 2013.](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a271e-261">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="a271e-262">Toutefois, les informations suivantes sont destinées à être plus généralement utiles, même s’il n’existe aucun moyen de fournir des étapes de procédure pas à pas spécifiques pour chaque proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="a271e-262">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="a271e-263">Nous devons prendre en compte deux éléments principaux :</span><span class="sxs-lookup"><span data-stu-id="a271e-263">We have two main things to consider:</span></span>
  
- <span data-ttu-id="a271e-264">Allez-vous faire votre première demande de découverte automatique sur HTTPS (ce que nous vous recommandons) ?</span><span class="sxs-lookup"><span data-stu-id="a271e-264">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="a271e-265">Si vous avez une règle de publication web, vous devez la modifier.</span><span class="sxs-lookup"><span data-stu-id="a271e-265">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="a271e-266">Si vous n’avez pas encore de règle de publication web, vous devez la créer.</span><span class="sxs-lookup"><span data-stu-id="a271e-266">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="a271e-267">Si vous faites votre première demande de découverte automatique sur HTTP, vous devez également créer ou modifier cette règle.</span><span class="sxs-lookup"><span data-stu-id="a271e-267">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a271e-268">**Important** Une valeur de délai d’délai proxy est un nombre qui varie d’un déploiement à l’autre.</span><span class="sxs-lookup"><span data-stu-id="a271e-268">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="a271e-269">Vous devez surveiller votre déploiement et modifier la valeur pour une expérience de qualité pour les clients.</span><span class="sxs-lookup"><span data-stu-id="a271e-269">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="a271e-270">Vous pourrez peut-être définir la valeur sur 200.</span><span class="sxs-lookup"><span data-stu-id="a271e-270">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="a271e-271">Si vous prise en charge des clients mobiles Lync dans votre environnement, vous devez définir la valeur sur 960 pour autoriser les délai d’accès aux notifications Push à partir d’Office 365, dont la valeur de délai d’utilisation est de 900.</span><span class="sxs-lookup"><span data-stu-id="a271e-271">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="a271e-272">Il est très probable que vous de dû augmenter la valeur du délai d’délai pour éviter les déconnexions client lorsque la valeur est trop faible, ou diminuer le nombre si les connexions via le proxy ne se déconnectent pas, mais se désconnectent longtemps après la déconnexion du client.</span><span class="sxs-lookup"><span data-stu-id="a271e-272">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="a271e-273">La surveillance et la définition de ce qui est habituel pour votre environnement sont le seul moyen précis de déterminer le paramètre approprié pour cette valeur.</span><span class="sxs-lookup"><span data-stu-id="a271e-273">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="a271e-274">Modifier la règle de publication web existante pour votre SAN de découverte automatique externe et l’URL</span><span class="sxs-lookup"><span data-stu-id="a271e-274">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="a271e-275">Ouvrez votre interface de proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="a271e-275">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="a271e-276">Vous devez localiser votre règle de publication web et choisir l’option Modifier (elle peut se trouver dans un menu ou un onglet, en fonction de votre configuration de proxy inverse).</span><span class="sxs-lookup"><span data-stu-id="a271e-276">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="a271e-277">Il doit y avoir une zone qui indique à quoi s’applique cette règle de publication web.</span><span class="sxs-lookup"><span data-stu-id="a271e-277">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="a271e-278">Vous devez modifier cette règle pour les sites entrants ou les demandes de sites.</span><span class="sxs-lookup"><span data-stu-id="a271e-278">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="a271e-279">Vous allez ajouter **une** nouvelle entrée.</span><span class="sxs-lookup"><span data-stu-id="a271e-279">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="a271e-280">Tapez le nom de votre site de découverte automatique (l’exemple que nous allons utiliser est lyncdiscover.contoso.com), puis cliquez sur **OK** ou **Enregistrer,** en fonction du format de votre proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="a271e-280">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="a271e-281">Vous disposez peut-être d’un nouveau certificat avec l’entrée SAN de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="a271e-281">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="a271e-282">Il doit également être installé et configuré pour être utilisé en fonction des paramètres de votre proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="a271e-282">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="a271e-283">N’oubliez pas de tout enregistrer une fois la configuration terminée.</span><span class="sxs-lookup"><span data-stu-id="a271e-283">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="a271e-284">Si votre proxy inverse dispose d’une fonctionnalité **test,** utilisez-la pour vous assurer que tout fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="a271e-284">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="a271e-285">Maintenant, vous devrez peut-être répéter ces étapes si vous avez un directeur ou un pool directeur dans votre environnement (cela signifie que vous avez une deuxième règle).</span><span class="sxs-lookup"><span data-stu-id="a271e-285">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="a271e-286">Créer une règle de publication web pour l’URL de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="a271e-286">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="a271e-287">Ouvrez votre interface de proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="a271e-287">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="a271e-288">Vous devez localiser l’emplacement dans l’interface où vous  créez vos règles de publication web, puis choisir l’option  Nouveau ou Créer (elle peut se trouver dans un menu ou un onglet, en fonction de votre configuration de proxy inverse).</span><span class="sxs-lookup"><span data-stu-id="a271e-288">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="a271e-289">Vous recherchez l’option de création d’une règle de publication web.</span><span class="sxs-lookup"><span data-stu-id="a271e-289">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="a271e-290">En règle générale, vous devez entrer les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a271e-290">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="a271e-291">**Name**: nom de votre règle</span><span class="sxs-lookup"><span data-stu-id="a271e-291">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="a271e-292">**Action de** la règle :  dans ce cas, il s’agit d’une règle d’autoriser, vous laissez quelque chose passer par votre proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="a271e-292">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="a271e-293">La **règle de** publication ou l’option que vous choisissez serait un site web unique ou un **équilibrage de charge.**</span><span class="sxs-lookup"><span data-stu-id="a271e-293">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="a271e-294">Il doit s’agit **du SSL pour** l’accès externe, choisissez cette option.</span><span class="sxs-lookup"><span data-stu-id="a271e-294">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="a271e-295">Vous devrez publier un chemin d’accès pour la publication interne et entrer le nom deqdn des services web externes sur le programme d’équilibrage de charge de votre pool frontal (ou le nom de groupe du programme d’équilibrage de charge du pool directeur si vous en avez un), par exemple sfb_pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="a271e-295">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="a271e-296">Vous devez taper _ comme chemin d’accès à publier, mais vous devez également **/\\** _\*forward l’en-tête d’hôte d’origine\*\*.</span><span class="sxs-lookup"><span data-stu-id="a271e-296">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="a271e-297">Il y aura une option pour **les** informations ou les détails des noms publics ou externes.</span><span class="sxs-lookup"><span data-stu-id="a271e-297">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="a271e-298">Il s’agit de l’endroit où vous pourrez entrer :</span><span class="sxs-lookup"><span data-stu-id="a271e-298">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="a271e-299">**Acceptez les demandes,** mais il doit s’y prendre pour le nom de domaine.</span><span class="sxs-lookup"><span data-stu-id="a271e-299">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="a271e-300">Pour le **nom,** vous devez entrer **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="a271e-300">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="a271e-301"><sipdomain> (il s’agit de l’URL du service de découverte automatique externe).</span><span class="sxs-lookup"><span data-stu-id="a271e-301"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="a271e-302">Maintenant, si vous créez une règle pour l’URL des services web externes sur le pool frontal, vous devez taper le nom de domaine final pour les services web externes sur votre pool frontal (par exemple, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a271e-302">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="a271e-303">Il y aura une option **Chemin** d’accès, et vous devrez entrer **/\\** _ ici.</span><span class="sxs-lookup"><span data-stu-id="a271e-303">There will be a **Path** option, and you'll need to enter **/\\** _ here.</span></span>
    
   - <span data-ttu-id="a271e-304">Vous devez sélectionner un _ *SSL Listener*\* avec votre certificat public à jour.</span><span class="sxs-lookup"><span data-stu-id="a271e-304">You'll need to select a _ *SSL Listener*\* with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="a271e-305">**La délégation** d’authentification doit être définie sur **Aucune délégation,** mais l’authentification client directe **doit** être autorisée.</span><span class="sxs-lookup"><span data-stu-id="a271e-305">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="a271e-306">La règle doit être définie sur **Tous les utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="a271e-306">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="a271e-307">Il doit s’agir de toutes les informations dont vous avez besoin pour créer cette règle et vous permettre de continuer.</span><span class="sxs-lookup"><span data-stu-id="a271e-307">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="a271e-308">Vous devez vous assurer que l’en-tête d’hôte **d’origine** est bien transmis.</span><span class="sxs-lookup"><span data-stu-id="a271e-308">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="a271e-309">Les ports **de** serveur Web doivent également être définies, vous devez :</span><span class="sxs-lookup"><span data-stu-id="a271e-309">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="a271e-310">**Les demandes de redirection vers le port HTTP** et le numéro de port doivent être **8080**.</span><span class="sxs-lookup"><span data-stu-id="a271e-310">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="a271e-311">**Rediriger les demandes vers le port SSL** et le numéro de port doit être **4443**.</span><span class="sxs-lookup"><span data-stu-id="a271e-311">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="a271e-312">Lorsque tout est configuré, vous devez les enregistrer ou les appliquer, puis tester la règle.</span><span class="sxs-lookup"><span data-stu-id="a271e-312">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="a271e-313">Créer une règle de publication web pour le port 80 (facultatif)</span><span class="sxs-lookup"><span data-stu-id="a271e-313">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="a271e-314">Ouvrez votre interface de proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="a271e-314">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="a271e-315">Vous devez localiser l’emplacement dans l’interface où vous  créez vos règles de publication web, puis choisir l’option  Nouveau ou Créer (elle peut se trouver dans un menu ou un onglet, en fonction de votre configuration de proxy inverse).</span><span class="sxs-lookup"><span data-stu-id="a271e-315">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="a271e-316">Vous recherchez l’option de création d’une règle de publication web.</span><span class="sxs-lookup"><span data-stu-id="a271e-316">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="a271e-317">En règle générale, vous devez entrer les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a271e-317">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="a271e-318">**Name**: nom de votre règle</span><span class="sxs-lookup"><span data-stu-id="a271e-318">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="a271e-319">**Action de** la règle :  dans ce cas, il s’agit d’une règle d’autoriser, vous laissez quelque chose passer par votre proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="a271e-319">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="a271e-320">La **règle de** publication ou l’option que vous choisissez serait un site web unique ou un **équilibrage de charge.**</span><span class="sxs-lookup"><span data-stu-id="a271e-320">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="a271e-321">Il doit s’agit d’une connexion non sécurisée pour se connecter au serveur Web ou à la batterie **de serveurs publié.**</span><span class="sxs-lookup"><span data-stu-id="a271e-321">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="a271e-322">Vous devrez publier un chemin d’accès pour la publication interne et entrer le nom deqdn de l’adresse **IP** ip du programme d’équilibrage de charge de votre pool frontal. Par exemple, sfb_pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="a271e-322">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="a271e-323">Vous devez taper _ comme chemin d’accès à publier, mais vous devez également **/\\** _\*forward l’en-tête d’hôte d’origine\*\*.</span><span class="sxs-lookup"><span data-stu-id="a271e-323">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="a271e-324">Il y aura une option pour **les** informations ou les détails des noms publics ou externes.</span><span class="sxs-lookup"><span data-stu-id="a271e-324">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="a271e-325">Il s’agit de l’endroit où vous pourrez entrer :</span><span class="sxs-lookup"><span data-stu-id="a271e-325">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="a271e-326">**Acceptez les demandes,** mais il doit s’y prendre pour le nom de domaine.</span><span class="sxs-lookup"><span data-stu-id="a271e-326">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="a271e-327">Pour le **nom,** vous devez entrer **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="a271e-327">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="a271e-328"><sipdomain> (il s’agit de l’URL du service de découverte automatique externe).</span><span class="sxs-lookup"><span data-stu-id="a271e-328"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="a271e-329">Il y aura une option **Chemin** d’accès, et vous devrez entrer **/\\** _ ici.</span><span class="sxs-lookup"><span data-stu-id="a271e-329">There will be a **Path** option, and you'll need to enter **/\\** _ here.</span></span>
    
   - <span data-ttu-id="a271e-330">Vous devez sélectionner un listener web ou autoriser votre proxy inverse à en créer un pour vous.</span><span class="sxs-lookup"><span data-stu-id="a271e-330">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="a271e-331">_ *La délégation d’authentification*\* doit être définie sur **Aucune délégation,** mais l’authentification client directe **ne doit pas** être autorisée.</span><span class="sxs-lookup"><span data-stu-id="a271e-331">_ *Authentication Delegation*\* should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="a271e-332">La règle doit être définie sur **Tous les utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="a271e-332">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="a271e-333">Il doit s’agir de toutes les informations dont vous avez besoin pour créer cette règle et vous permettre de continuer.</span><span class="sxs-lookup"><span data-stu-id="a271e-333">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="a271e-334">Les ports du serveur **Web** doivent être définies, vous devez :</span><span class="sxs-lookup"><span data-stu-id="a271e-334">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="a271e-335">**Les demandes de redirection vers le port HTTP** et le numéro de port doivent être **8080**.</span><span class="sxs-lookup"><span data-stu-id="a271e-335">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="a271e-336">**Rediriger les demandes vers le port SSL** et le numéro de port doit être **4443**.</span><span class="sxs-lookup"><span data-stu-id="a271e-336">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="a271e-337">Lorsque tout est configuré, vous devez les enregistrer ou les appliquer, puis tester la règle.</span><span class="sxs-lookup"><span data-stu-id="a271e-337">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="a271e-338">Configurer la découverte automatique pour la mobilité avec des déploiements hybrides</span><span class="sxs-lookup"><span data-stu-id="a271e-338">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="a271e-339"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="a271e-339"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="a271e-340">Les environnements hybrides dans Skype Entreprise Server sont des environnements qui combinent un environnement local et un environnement O365.</span><span class="sxs-lookup"><span data-stu-id="a271e-340">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="a271e-341">Lorsque Skype Entreprise Server fonctionne dans un environnement hybride, le service de découverte automatique doit pouvoir localiser un utilisateur à partir de l’un de ces environnements.</span><span class="sxs-lookup"><span data-stu-id="a271e-341">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="a271e-342">Pour que les clients mobiles trouvent l’emplacement d’un utilisateur, le service de découverte automatique doit être configuré avec une nouvelle URL (Uniform Resource Locator).</span><span class="sxs-lookup"><span data-stu-id="a271e-342">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="a271e-343">Voici comment procéder :</span><span class="sxs-lookup"><span data-stu-id="a271e-343">The steps are:</span></span>
  
1. <span data-ttu-id="a271e-344">Ouvrez Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a271e-344">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="a271e-345">Exécutez la ligne suivante pour obtenir la valeur de l’attribut **ProxyFQDN** pour votre environnement Skype Entreprise Server :</span><span class="sxs-lookup"><span data-stu-id="a271e-345">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="a271e-346">Ensuite, toujours dans la fenêtre d’shell, exécutez :</span><span class="sxs-lookup"><span data-stu-id="a271e-346">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="a271e-347">Où [identity] est remplacé par le nom de domaine de l’espace d’adresses SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="a271e-347">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="a271e-348">Tester votre déploiement de mobilité</span><span class="sxs-lookup"><span data-stu-id="a271e-348">Test your Mobility deployment</span></span>
<span data-ttu-id="a271e-349"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="a271e-349"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="a271e-350">Une fois que vous avez déployé le service de mobilité Skype Entreprise Server et le service de découverte automatique Skype Entreprise Server, vous devez exécuter une transaction de test pour vous assurer que votre déploiement fonctionne bien.</span><span class="sxs-lookup"><span data-stu-id="a271e-350">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="a271e-351">Vous pouvez exécuter **Test-CsUcwaConference** pour tester la capacité de deux utilisateurs à créer, rejoindre et communiquer dans une conférence.</span><span class="sxs-lookup"><span data-stu-id="a271e-351">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="a271e-352">Vous aurez besoin de deux utilisateurs (réels ou tests) et de leurs informations d’identification complètes pour ce test.</span><span class="sxs-lookup"><span data-stu-id="a271e-352">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="a271e-353">Cette commande fonctionne aussi bien pour les clients Skype Entreprise que pour les clients Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a271e-353">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="a271e-354">Pour les clients Lync Server 2010 sur Skype Entreprise Server 2015, vous devez exécuter **Test-CsMcxP2PIM** pour le test.</span><span class="sxs-lookup"><span data-stu-id="a271e-354">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="a271e-355">Vos utilisateurs Lync Server 2010 devront toujours être des utilisateurs réels ou des utilisateurs de test prédéfincis, et vous aurez besoin de leurs informations d’identification de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="a271e-355">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="a271e-356">La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a271e-356">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a271e-357">Tous les clients mobiles Skype Entreprise actuels utilisent déjà l’API web de communications unifiées (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts.</span><span class="sxs-lookup"><span data-stu-id="a271e-357">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="a271e-358">Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="a271e-358">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="a271e-359">Test de la conférence pour les clients mobiles Skype Entreprise et Lync 2013</span><span class="sxs-lookup"><span data-stu-id="a271e-359">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="a271e-360">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span><span class="sxs-lookup"><span data-stu-id="a271e-360">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a271e-361">Démarrez **Skype Entreprise Server Management Shell** (vous pouvez taper le nom dans la recherche ou aller à **Tous** les programmes et le choisir).</span><span class="sxs-lookup"><span data-stu-id="a271e-361">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="a271e-362">À partir de la ligne de commande, entrez :</span><span class="sxs-lookup"><span data-stu-id="a271e-362">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="a271e-363">Il est également possible de définir des informations d’identification dans un script et de les transmettre à la cmdlet de test.</span><span class="sxs-lookup"><span data-stu-id="a271e-363">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="a271e-364">Nous en avons un exemple ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a271e-364">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="a271e-365">Test de la conférence pour les clients mobiles Lync 2010</span><span class="sxs-lookup"><span data-stu-id="a271e-365">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="a271e-366">La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a271e-366">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a271e-367">Tous les clients mobiles Skype Entreprise actuels utilisent déjà l’API web de communications unifiées (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts.</span><span class="sxs-lookup"><span data-stu-id="a271e-367">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="a271e-368">Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="a271e-368">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="a271e-369">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span><span class="sxs-lookup"><span data-stu-id="a271e-369">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a271e-370">Démarrez **Skype Entreprise Server Management Shell** (vous pouvez taper le nom dans la recherche ou aller à **Tous** les programmes et le choisir).</span><span class="sxs-lookup"><span data-stu-id="a271e-370">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="a271e-371">À partir de la ligne de commande, entrez :</span><span class="sxs-lookup"><span data-stu-id="a271e-371">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="a271e-372">Il est également possible de définir des informations d’identification dans un script et de les transmettre à la cmdlet de test.</span><span class="sxs-lookup"><span data-stu-id="a271e-372">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="a271e-373">Nous en avons un exemple ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a271e-373">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="a271e-374">Pour passer en revue les procédures de commande, vous pouvez consulter [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) et [Test-CsMcxP2PIM.](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a271e-374">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="a271e-375">Configurer les notifications de type push</span><span class="sxs-lookup"><span data-stu-id="a271e-375">Configure for push notifications</span></span>
<span data-ttu-id="a271e-376"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="a271e-376"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="a271e-377">Les notifications Push, sous forme de badges, d’icônes ou d’alertes, peuvent être envoyées à un appareil mobile même lorsque l’application Skype ou Lync est inactive.</span><span class="sxs-lookup"><span data-stu-id="a271e-377">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="a271e-378">Mais qu’est-ce que les notifications Push ?</span><span class="sxs-lookup"><span data-stu-id="a271e-378">But what are push notifications?</span></span> <span data-ttu-id="a271e-379">Il s’agit d’alertes d’événement, telles qu’une invitation de messagerie instantanée nouvelle ou manquée, ou pour une messagerie vocale reçue.</span><span class="sxs-lookup"><span data-stu-id="a271e-379">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="a271e-380">Le service de mobilité de Skype Entreprise Server envoie ces notifications au service de notification push Skype Entreprise Server basé sur le cloud, qui envoie ensuite les notifications au service MSNS (Microsoft Push Notification Service) pour les utilisateurs de Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="a271e-380">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="a271e-381">Cette fonctionnalité est inchangée par rapport à Lync Server 2013, mais si vous avez un serveur Skype Entreprise, vous devez :</span><span class="sxs-lookup"><span data-stu-id="a271e-381">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="a271e-382">Pour un serveur Edge Skype Entreprise Server, ajoutez un nouveau fournisseur d’hébergement, Microsoft Skype Entreprise Online, puis définissez la fédération des fournisseurs d’hébergement entre votre organisation et Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="a271e-382">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="a271e-383">Activez les notifications push en exécutant l’cmdlet **Set-CsPushNotificationConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="a271e-383">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="a271e-384">Par défaut, les notifications push sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="a271e-384">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="a271e-385">Testez la configuration de votre fédération et les notifications Push.</span><span class="sxs-lookup"><span data-stu-id="a271e-385">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="a271e-386">Configurer votre serveur Edge Skype Entreprise pour les notifications Push</span><span class="sxs-lookup"><span data-stu-id="a271e-386">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="a271e-387">Log on, with an account that’s a member of the **CsAdministrator** role, to a computer **where Skype for Business Server Management Shell** and **Ocscore** are installed.</span><span class="sxs-lookup"><span data-stu-id="a271e-387">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a271e-388">Démarrez **Skype Entreprise Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="a271e-388">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a271e-389">Ajoutez un fournisseur d’hébergement en ligne Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a271e-389">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="a271e-390">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a271e-390">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="a271e-391">Vous ne pouvez pas avoir plusieurs relations de fédération avec un seul fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="a271e-391">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="a271e-392">Par exemple, si vous avez déjà mis en place un fournisseur d’hébergement qui a une relation de fédération avec sipfed.online.lync.com, n’ajoutez pas d’autre fournisseur d’hébergement pour celui-ci, même si l’identité du fournisseur d’hébergement est autre que SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="a271e-392">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="a271e-393">Configurer la fédération du fournisseur d’hébergement entre votre organisation et le service de notifications Push sur Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="a271e-393">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="a271e-394">Sur la ligne de commande, vous devez taper :</span><span class="sxs-lookup"><span data-stu-id="a271e-394">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="a271e-395">Activer les notifications Push</span><span class="sxs-lookup"><span data-stu-id="a271e-395">Enable push notifications</span></span>

1. <span data-ttu-id="a271e-396">Log on, with an account that’s a member of the **CsAdministrator** role, to a computer **where Skype for Business Server Management Shell** and **Ocscore** are installed.</span><span class="sxs-lookup"><span data-stu-id="a271e-396">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a271e-397">Démarrez **Skype Entreprise Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="a271e-397">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a271e-398">Activez les notifications Push :</span><span class="sxs-lookup"><span data-stu-id="a271e-398">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="a271e-399">Activer la fédération :</span><span class="sxs-lookup"><span data-stu-id="a271e-399">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="a271e-400">Tester la fédération et les notifications Push</span><span class="sxs-lookup"><span data-stu-id="a271e-400">Test federation and push notifications</span></span>

1. <span data-ttu-id="a271e-401">Log on, with an account that’s a member of the **CsAdministrator** role, to a computer **where Skype for Business Server Management Shell** and **Ocscore** are installed.</span><span class="sxs-lookup"><span data-stu-id="a271e-401">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a271e-402">Démarrez **Skype Entreprise Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="a271e-402">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a271e-403">Testez la configuration de la fédération :</span><span class="sxs-lookup"><span data-stu-id="a271e-403">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="a271e-404">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a271e-404">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="a271e-405">Testez vos notifications Push :</span><span class="sxs-lookup"><span data-stu-id="a271e-405">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="a271e-406">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a271e-406">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="a271e-407">Configurer la stratégie de mobilité</span><span class="sxs-lookup"><span data-stu-id="a271e-407">Configure Mobility policy</span></span>
<span data-ttu-id="a271e-408"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="a271e-408"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="a271e-409">Vous avez la possibilité avec Skype Entreprise Server de déterminer qui peut utiliser votre service de mobilité, appel via le travail, voIP ou vidéo, ainsi que si le WiFi sera requis pour voIP ou vidéo.</span><span class="sxs-lookup"><span data-stu-id="a271e-409">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="a271e-410">L’appel via le lieu de travail permet à un utilisateur mobile d’utiliser son numéro de téléphone de travail, au lieu de son numéro de téléphone mobile, pour passer et recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="a271e-410">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="a271e-411">La personne à l’autre extrémité de la ligne ne verra pas le numéro de téléphone portable de cet utilisateur mobile et elle lui permet d’éviter les frais d’appels sortants.</span><span class="sxs-lookup"><span data-stu-id="a271e-411">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="a271e-412">Lorsque voIP et vidéo sont mis en place, les utilisateurs peuvent prendre et effectuer des appels VoIP et de la vidéo.</span><span class="sxs-lookup"><span data-stu-id="a271e-412">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="a271e-413">Les paramètres d’utilisation du WiFi déterminent si l’appareil mobile d’un utilisateur doit utiliser un réseau WiFi sur un réseau de données cellulaires.</span><span class="sxs-lookup"><span data-stu-id="a271e-413">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="a271e-414">La mobilité, l’appel via le travail et les fonctionnalités VoIP et vidéo sont toutes activées par défaut.</span><span class="sxs-lookup"><span data-stu-id="a271e-414">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="a271e-415">Le paramètre pour exiger le WiFi pour VoIP et la vidéo est désactivé.</span><span class="sxs-lookup"><span data-stu-id="a271e-415">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="a271e-416">Un administrateur a la possibilité de modifier cela, globalement, par site ou par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a271e-416">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="a271e-417">Pour pouvoir utiliser les fonctionnalités de mobilité et appel via le travail, les utilisateurs doivent :</span><span class="sxs-lookup"><span data-stu-id="a271e-417">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="a271e-418">Activé pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a271e-418">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="a271e-419">Activé pour les Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="a271e-419">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="a271e-420">Affecté à une stratégie de mobilité dont l’option **EnableMobility** est définie sur **True**.</span><span class="sxs-lookup"><span data-stu-id="a271e-420">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="a271e-421">Pour que les utilisateurs puissent utiliser l’appel via le travail, ils doivent également :</span><span class="sxs-lookup"><span data-stu-id="a271e-421">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="a271e-422">Une stratégie de voix dont l’option Activer **la sonnerie** simultanée des téléphones est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a271e-422">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="a271e-423">Affecté à une stratégie de mobilité dont la valeur **EnableOutsideVoice** est définie sur **True**.</span><span class="sxs-lookup"><span data-stu-id="a271e-423">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a271e-424">Les utilisateurs qui ne sont pas activés pour Voix Entreprise peuvent utiliser leur appareil mobile pour effectuer des appels VoIP Skype vers Skype ou participer à des conférences à l’aide du lien Cliquer pour rejoindre sur leur appareil mobile, si les options appropriées sont définies pour la stratégie de voix à qui ils sont associés.</span><span class="sxs-lookup"><span data-stu-id="a271e-424">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="a271e-425">Vous y avez plus de détails dans la rubrique PLANIFICATION.</span><span class="sxs-lookup"><span data-stu-id="a271e-425">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="a271e-426">Modifier la stratégie de mobilité globale</span><span class="sxs-lookup"><span data-stu-id="a271e-426">Modify global Mobility policy</span></span>

1. <span data-ttu-id="a271e-427">Log on, with an account that’s a member of the **CsAdministrator** role, to a computer **where Skype for Business Server Management Shell** and **Ocscore** are installed.</span><span class="sxs-lookup"><span data-stu-id="a271e-427">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a271e-428">Démarrez **Skype Entreprise Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="a271e-428">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a271e-429">Désactiver globalement l’accès à la mobilité et à l’appel via le travail en tapant :</span><span class="sxs-lookup"><span data-stu-id="a271e-429">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="a271e-430">Vous pouvez désactiver l’appel via le travail sans désactiver l’accès à la mobilité.</span><span class="sxs-lookup"><span data-stu-id="a271e-430">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="a271e-431">Toutefois, vous ne pouvez pas désactiver la mobilité sans également désactiver l’appel via le travail.</span><span class="sxs-lookup"><span data-stu-id="a271e-431">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="a271e-432">Pour plus d’informations, [consultez Set-CsMobilityPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a271e-432">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="a271e-433">Modifier la stratégie de mobilité par site</span><span class="sxs-lookup"><span data-stu-id="a271e-433">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="a271e-434">Log on, with an account that’s a member of the **CsAdministrator** role, to a computer **where Skype for Business Server Management Shell** and **Ocscore** are installed.</span><span class="sxs-lookup"><span data-stu-id="a271e-434">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a271e-435">Démarrez **Skype Entreprise Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="a271e-435">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a271e-436">Vous pouvez créer une stratégie au niveau du site, désactiver voIP et vidéo, activer Le WiFi nécessaire pour l’audio IP et Exiger le WiFi pour la vidéo IP par site.</span><span class="sxs-lookup"><span data-stu-id="a271e-436">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="a271e-437">Type :</span><span class="sxs-lookup"><span data-stu-id="a271e-437">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="a271e-438">Pour plus [d’informations, ez-vous sur New-CsMobilityPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a271e-438">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="a271e-439">Modifier la stratégie de mobilité par utilisateur</span><span class="sxs-lookup"><span data-stu-id="a271e-439">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="a271e-440">Log on, with an account that’s a member of the **CsAdministrator** role, to a computer **where Skype for Business Server Management Shell** and **Ocscore** are installed.</span><span class="sxs-lookup"><span data-stu-id="a271e-440">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a271e-441">Démarrez **Skype Entreprise Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="a271e-441">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a271e-442">Créer des stratégies de mobilité au niveau de l’utilisateur et désactiver la mobilité et l’appel via le travail par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a271e-442">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="a271e-443">Type :</span><span class="sxs-lookup"><span data-stu-id="a271e-443">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="a271e-444">Un autre exemple avec des exemples de données :</span><span class="sxs-lookup"><span data-stu-id="a271e-444">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="a271e-445">Vous pouvez désactiver l’appel via le travail sans désactiver l’accès à la mobilité.</span><span class="sxs-lookup"><span data-stu-id="a271e-445">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="a271e-446">Toutefois, vous ne pouvez pas désactiver la mobilité sans également désactiver l’appel via le travail.</span><span class="sxs-lookup"><span data-stu-id="a271e-446">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

