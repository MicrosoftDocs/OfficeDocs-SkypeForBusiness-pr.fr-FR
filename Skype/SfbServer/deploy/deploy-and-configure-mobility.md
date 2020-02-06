---
title: Déploiement et configuration de la mobilité pour Skype entreprise Server
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
description: Cet article vous guide dans la procédure de configuration d’une installation de Skype entreprise Server existante pour utiliser le service de mobilité et permettre à vos appareils mobiles de profiter des fonctionnalités de mobilité de Skype entreprise Server.
ms.openlocfilehash: 7b619da5b0567aff73b3d8d48eda96efdc098611
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796083"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="53372-103">Déploiement et configuration de la mobilité pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="53372-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="53372-104">Cet article vous guide dans la procédure de configuration d’une installation de Skype entreprise Server existante pour utiliser le service de mobilité et permettre à vos appareils mobiles de profiter des fonctionnalités de mobilité de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="53372-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="53372-105">Après avoir consulté le [plan de mobilité pour l’article Skype entreprise Server](../plan-your-deployment/mobility.md) , vous devez être prêt à suivre les étapes ci-dessous pour déployer la mobilité dans votre environnement Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="53372-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="53372-106">Voici les étapes à suivre (avec une liste des autorisations incluse dans le tableau) :</span><span class="sxs-lookup"><span data-stu-id="53372-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="53372-107">**Phase**</span><span class="sxs-lookup"><span data-stu-id="53372-107">**Phase**</span></span>|<span data-ttu-id="53372-108">**Autorisations**</span><span class="sxs-lookup"><span data-stu-id="53372-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="53372-109">Créer des enregistrements DNS</span><span class="sxs-lookup"><span data-stu-id="53372-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="53372-110">DomainAdmins</span><span class="sxs-lookup"><span data-stu-id="53372-110">Domain Admins</span></span>  <br/> <span data-ttu-id="53372-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="53372-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="53372-112">Modifier les certificats</span><span class="sxs-lookup"><span data-stu-id="53372-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="53372-113">Administrateur local</span><span class="sxs-lookup"><span data-stu-id="53372-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="53372-114">Configurer le proxy inverse</span><span class="sxs-lookup"><span data-stu-id="53372-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="53372-115">Administrateur local</span><span class="sxs-lookup"><span data-stu-id="53372-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="53372-116">Configurer la découverte automatique pour la mobilité avec les déploiements hybrides</span><span class="sxs-lookup"><span data-stu-id="53372-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="53372-117">DomainAdmins</span><span class="sxs-lookup"><span data-stu-id="53372-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="53372-118">Tester votre déploiement de mobilité</span><span class="sxs-lookup"><span data-stu-id="53372-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="53372-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="53372-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="53372-120">Configurer les notifications push</span><span class="sxs-lookup"><span data-stu-id="53372-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="53372-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="53372-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="53372-122">Configurer la stratégie de mobilité</span><span class="sxs-lookup"><span data-stu-id="53372-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="53372-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="53372-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="53372-p102">Toutes les sections suivantes comprennent des étapes qui impliquent que vous ayez parcouru la rubrique concernant la planification. En cas de doute, n'hésitez pas à consulter les informations fournies ici.</span><span class="sxs-lookup"><span data-stu-id="53372-p102">All the following sections contain steps that assume you've read the Planning topic. If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="53372-126">La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="53372-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="53372-127">Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts.</span><span class="sxs-lookup"><span data-stu-id="53372-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="53372-128">Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="53372-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="53372-129">Créer des enregistrements DNS</span><span class="sxs-lookup"><span data-stu-id="53372-129">Create DNS records</span></span>
<span data-ttu-id="53372-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="53372-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="53372-131">Vous pouvez déjà disposer de ces éléments dans le cadre de votre environnement Skype entreprise Server, mais vous devez créer les enregistrements suivants pour que la découverte automatique fonctionne :</span><span class="sxs-lookup"><span data-stu-id="53372-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="53372-132">un enregistrement DNS interne afin de prendre en charge les utilisateurs mobiles qui se connectent depuis le réseau de votre organisation ;</span><span class="sxs-lookup"><span data-stu-id="53372-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="53372-133">un enregistrement DNS externe (ou public) afin de prendre en charge les utilisateurs mobiles qui se connectent depuis le réseau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="53372-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="53372-134">Ces enregistrements sont soit des enregistrements de noms (d'hôte) A, soit des enregistrements CNAME (vous n'avez pas à créer ces deux enregistrements, mais nous décrivons ici toutes les étapes pour les deux types d'enregistrement).</span><span class="sxs-lookup"><span data-stu-id="53372-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="53372-135">Créer un enregistrement CNAME DNS interne</span><span class="sxs-lookup"><span data-stu-id="53372-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="53372-136">Ouvrez une session sur un serveur DNS de votre réseau qui est membre du groupe **Administrateurs du domaine** ou du groupe **DnsAdmins**.</span><span class="sxs-lookup"><span data-stu-id="53372-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="53372-137">Cliquez sur **Démarrer**, Sélectionnez \*\*Outils d’administration \*\* (vous devrez peut-être \*\*Rechercher \*\* l'option si elle n'existe pas dans le menu Démarrer), puis cliquez sur **DNS** pour ouvrir le composant logiciel enfichable d'administration DNS.</span><span class="sxs-lookup"><span data-stu-id="53372-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="53372-138">Dans le volet gauche de la fenêtre de la console, vous devez vous rendre sur le domaine qui est destiné aux serveurs frontaux de Skype entreprise Server et étendre les **zones de recherche directe** .</span><span class="sxs-lookup"><span data-stu-id="53372-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="53372-139">Prenez un moment pour vérifiez lequel des enregistrements suivants vous avez :</span><span class="sxs-lookup"><span data-stu-id="53372-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="53372-140">Un ou plusieurs enregistrements d’hôte A ou AAAA pour votre serveur frontal (standard ou entreprise) ou le ou les pools front-end.</span><span class="sxs-lookup"><span data-stu-id="53372-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="53372-141">Tout enregistrement d’hôte A ou AAAA d’un directeur ou d’un pool de réalisateur (Configuration facultative éventuellement disponible dans votre déploiement).</span><span class="sxs-lookup"><span data-stu-id="53372-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="53372-142">Une fois l'information vérifiée, cliquez avec le bouton droit de la souris sur votre nom de domaine SIP, puis sélectionnez **Nouvel alias (CNAME)** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="53372-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="53372-143">Dans la zone **Nom de l’alias**, saisissez le nom d’hôte correspondant à l’URL de service interne de découverte automatique : lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="53372-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="53372-144">Dans le **nom de domaine complet (FQDN pour l’hôte cible**), vous devez taper ou parcourir le nom de domaine complet (FQDN) des services Web interne pour votre liste frontale (ou un serveur frontal ou un réalisateur), comme indiqué à l’étape 4 ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="53372-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="53372-145">Cliquez sur Entrée une fois le nom saisi.</span><span class="sxs-lookup"><span data-stu-id="53372-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="53372-146">Vous devez créer un enregistrement CNAMe de découverte automatique dans la zone de recherche directe pour chaque domaine SIP pris en charge dans votre environnement Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="53372-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="53372-147">Créer un enregistrement CNAME DNS externe</span><span class="sxs-lookup"><span data-stu-id="53372-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="53372-148">Ces étapes sont génériques, car nous ne pouvons pas déterminer quel fournisseur DNS public vous utilisez, mais elles pourront toujours vous être utiles. Connectez-vous à votre fournisseur DNS public avec un compte qui vous permettra de créer ici de nouveaux enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="53372-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="53372-149">À ce moment-là, un domaine SIP doit déjà exister pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="53372-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="53372-150">Développez la **zone de recherche directe** pour ce domaine SIP, ou procédez à son ouverture.</span><span class="sxs-lookup"><span data-stu-id="53372-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="53372-151">Prenez un moment pour vérifiez lequel des enregistrements suivants vous avez :</span><span class="sxs-lookup"><span data-stu-id="53372-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="53372-152">Un ou plusieurs enregistrements d’hôte A ou AAAA pour votre serveur frontal (standard ou entreprise) ou le ou les pools front-end.</span><span class="sxs-lookup"><span data-stu-id="53372-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="53372-153">Tout enregistrement d’hôte A ou AAAA d’un directeur ou d’un pool de réalisateur (Configuration facultative éventuellement disponible dans votre déploiement).</span><span class="sxs-lookup"><span data-stu-id="53372-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="53372-154">Une fois que vous avez vérifié l'information, vous devriez pouvoir sélectionner une option pour créer un **Nouvel alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="53372-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="53372-155">Vous devriez maintenant pouvoir saisir un **Nom d'alias**. Saisissez ensuite lyncdiscover en tant qu'URL de service interne de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="53372-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="53372-156">À présent, il devrait y avoir une zone à entrer dans un nom de domaine complet (FQDN) **pour l’hôte cible**, il doit s’agir du nom de domaine complet (FQDN) du pool frontal (ou d’un serveur frontal ou réalisateur), identifié à l’étape 3 ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="53372-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="53372-157">Vous devrez peut-être enregistrer cet emplacement ou, si vous avez besoin de créer des enregistrements CNAMe supplémentaires dans la zone de recherche directe de chaque domaine SIP de votre environnement Skype entreprise Server, procédez ainsi, mais lorsque vous serez prêt, enregistrez votre travail.</span><span class="sxs-lookup"><span data-stu-id="53372-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="53372-158">Créer un enregistrement A DNS interne</span><span class="sxs-lookup"><span data-stu-id="53372-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="53372-159">Ouvrez une session sur un serveur DNS de votre réseau qui est membre du groupe **Administrateurs du domaine** ou du groupe **DnsAdmins**.</span><span class="sxs-lookup"><span data-stu-id="53372-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="53372-160">Cliquez sur **Démarrer**, Sélectionnez \*\*Outils d’administration \*\* (vous devrez peut-être \*\*Rechercher \*\* l'option si elle n'existe pas dans le menu Démarrer), puis cliquez sur **DNS** pour ouvrir le composant logiciel enfichable d'administration DNS.</span><span class="sxs-lookup"><span data-stu-id="53372-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="53372-161">Dans le volet gauche de la fenêtre de la console, vous devez vous rendre sur le domaine qui est destiné aux serveurs frontaux de Skype entreprise Server et étendre les **zones de recherche directe** .</span><span class="sxs-lookup"><span data-stu-id="53372-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="53372-162">Prenez un moment pour vérifiez lequel des enregistrements suivants vous avez :</span><span class="sxs-lookup"><span data-stu-id="53372-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="53372-163">Un ou plusieurs enregistrements d’hôte A ou AAAA pour votre serveur frontal (standard ou entreprise) ou le ou les pools front-end.</span><span class="sxs-lookup"><span data-stu-id="53372-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="53372-164">Tout enregistrement d’hôte A ou AAAA d’un directeur ou d’un pool de réalisateur (Configuration facultative éventuellement disponible dans votre déploiement).</span><span class="sxs-lookup"><span data-stu-id="53372-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="53372-165">Une fois l'information vérifiée, cliquez avec le bouton droit de la souris sur votre nom de domaine SIP, puis sélectionnez **Nouvel hôte (A ou AAAA)** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="53372-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="53372-166">Dans la zone **Nom**, saisissez le nom d’hôte correspondant à l’URL de service interne de découverte automatique : lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="53372-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="53372-167">Dans la zone de saisie de l' **adresse IP** , tapez l’adresse IP des services Web internes de votre pool frontal (ou un serveur frontal ou un réalisateur), identifié à l’étape 4 ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="53372-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="53372-168">Une fois terminé, cliquez sur **Ajouter un hôte**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="53372-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="53372-169">Vous devez créer un nouvel enregistrement de découverte automatique A ou AAAA dans la zone de recherche directe pour chaque domaine SIP pris en charge dans votre environnement Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="53372-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="53372-170">Pour ce faire, répétez les étapes 6 à 8 autant de fois que nécessaire.</span><span class="sxs-lookup"><span data-stu-id="53372-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="53372-171">Une fois l'opération terminée, cliquez sur **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="53372-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="53372-172">Créer un enregistrement A DNS externe</span><span class="sxs-lookup"><span data-stu-id="53372-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="53372-173">Ces étapes sont génériques, car nous ne pouvons pas déterminer quel fournisseur DNS public vous utilisez, mais elles pourront toujours vous être utiles. Connectez-vous à votre fournisseur DNS public avec un compte qui vous permettra de créer ici de nouveaux enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="53372-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="53372-174">À ce moment-là, un domaine SIP doit déjà exister pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="53372-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="53372-175">Développez la **zone de recherche directe** pour ce domaine SIP, ou procédez à son ouverture.</span><span class="sxs-lookup"><span data-stu-id="53372-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="53372-176">Prenez un moment pour vérifiez lequel des enregistrements suivants vous avez :</span><span class="sxs-lookup"><span data-stu-id="53372-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="53372-177">Un ou plusieurs enregistrements d’hôte A ou AAAA pour votre serveur frontal (standard ou entreprise) ou le ou les pools front-end.</span><span class="sxs-lookup"><span data-stu-id="53372-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="53372-178">Tout enregistrement d’hôte A ou AAAA d’un directeur ou d’un pool de réalisateur (Configuration facultative éventuellement disponible dans votre déploiement).</span><span class="sxs-lookup"><span data-stu-id="53372-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="53372-179">Une fois que vous avez vérifié l'information, vous devriez être capable de sélectionner une option pour créer un **Nouvel hôte A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="53372-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="53372-180">Vous devriez maintenant pouvoir saisir un **Nom**. Saisissez ensuite lyncdiscover en tant qu'URL de service interne de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="53372-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="53372-181">Ensuite, il devrait y avoir une zone à entrer dans une **adresse IP**, il doit s’agir de l’adresse IP de votre pool frontal (ou d’un serveur frontal unique ou du réalisateur), identifié à l’étape 3 ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="53372-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="53372-182">Vous devrez peut-être enregistrer cet emplacement ou, si vous avez besoin de créer des enregistrements A ou AAAA supplémentaires dans la zone de recherche directe de chaque domaine SIP pour votre environnement Skype entreprise Server, vous devez le faire, mais une fois que vous êtes prêt, enregistrez votre travail.</span><span class="sxs-lookup"><span data-stu-id="53372-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="53372-183">Modifier les certificats</span><span class="sxs-lookup"><span data-stu-id="53372-183">Modify certificates</span></span>
<span data-ttu-id="53372-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="53372-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="53372-185">Si vous avez des questions sur la planification des certificats, nous avons documenté le [projet dans notre plan de mobilité pour Skype entreprise Server](../plan-your-deployment/mobility.md) .</span><span class="sxs-lookup"><span data-stu-id="53372-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="53372-186">Une fois que vous avez examiné ce qui suit, nous vous guidons à travers les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="53372-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="53372-187">Dois-je obtenir de nouveaux certificats ?</span><span class="sxs-lookup"><span data-stu-id="53372-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="53372-188">Demande de nouveaux certificats auprès de votre autorité de certification (CA).</span><span class="sxs-lookup"><span data-stu-id="53372-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="53372-189">Mise à jour sur site de certificats avec les remplacements à l'aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53372-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="53372-190">Vérification des certificats à l’aide du composant logiciel enfichable Certificats dans Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="53372-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="53372-191">Dois-je obtenir de nouveaux certificats ?</span><span class="sxs-lookup"><span data-stu-id="53372-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="53372-192">Vous devez d'abord vérifier quels certificats sont en place et s'ils disposent ou non des entrées dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="53372-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="53372-193">Pour ce faire, vous devez vous connecter à Skype entreprise Server à l’aide d’un compte d’administrateur local.</span><span class="sxs-lookup"><span data-stu-id="53372-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="53372-194">Ce compte doit également disposer des autorisations d'accès à l'autorité de certification (CA) émettrice pour effectuer certaines de ces étapes.</span><span class="sxs-lookup"><span data-stu-id="53372-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="53372-195">Ouvrez Skype entreprise Server Management Shell (vous pouvez utiliser la recherche pour le rechercher si vous n’avez pas épinglé le menu Démarrer ou la barre des tâches).</span><span class="sxs-lookup"><span data-stu-id="53372-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="53372-p110">Vous devrez absolument savoir quels certificats ont été affectés avant de pouvoir ajouter un certificat mis à jour. À partir de la ligne de commande, saisissez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="53372-p110">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate. So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="53372-p111">Les informations fournies à partir de l'étape 3 vous seront spécifiques. Vous devez les vérifier afin de déterminer si vous disposez d'un certificat unique ayant été affecté à plusieurs éléments, ou si vous disposez d'un autre certificat affecté pour les différents composants qui en ont besoin. Le paramètre **Utiliser** vous permettra de savoir de quelle manière un certificat est utilisé et le paramètre **Thumbprint** vous permettra de savoir s'il s'agit du même certificat ou de plusieurs certificats.</span><span class="sxs-lookup"><span data-stu-id="53372-p111">The information from Step 3 will be unique to you. You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them. The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="53372-p112">Si vous disposez des entrées SAN recommandées dans votre section Planification, vous n'avez rien à faire. Sinon, vous devrez demander un nouveau certificat ou plusieurs certificats (en fonction de votre configuration) auprès de votre autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="53372-p112">If you have the SAN entries recommended in our Planning section, you're good. If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="53372-203">Demander un nouveau certificat ou de nouveaux certificats auprès de votre autorité de certification (CA)</span><span class="sxs-lookup"><span data-stu-id="53372-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="53372-204">Après avoir vérifié les entrées SAN dont vous disposez, vous savez que vous avez un **certificat unique** (la vérification ayant été effectuée en suivant la procédure décrite précédemment) et vous savez que vous ne disposez pas de toutes les entrées dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="53372-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="53372-205">Une nouvelle demande de certificat doit être effectuée auprès de votre autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="53372-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="53372-206">Ouvrez votre PowerShell Skype entreprise Server :</span><span class="sxs-lookup"><span data-stu-id="53372-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="53372-207">Pour un SAN de service de découverte automatique (en remplaçant le paramètre -Ca par votre propre chemin d'accès à l'autorité de certification) :</span><span class="sxs-lookup"><span data-stu-id="53372-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="53372-208">À présent, si vous avez plusieurs domaines SIP, vous ne pouvez pas utiliser le paramètre AllSipDomain comme dans l’exemple ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="53372-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="53372-209">Vous devrez plutôt utiliser le paramètre DomainName.</span><span class="sxs-lookup"><span data-stu-id="53372-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="53372-210">De plus, lorsque vous utilisez le paramètre DomainName, vous devez définir le nom de domaine complet pour les enregistrements lyncdiscoverinternal et lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="53372-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="53372-211">En voici un exemple (en remplaçant le paramètre -Ca par votre propre chemin d'accès à l'autorité de certification) :</span><span class="sxs-lookup"><span data-stu-id="53372-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="53372-212">Ou, après avoir vérifié les entrées SAN dont vous disposez, vous savez que vous avez **plusieurs certificats** qui ne disposent pas de toutes les entrées dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="53372-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="53372-213">Une nouvelle demande de certificat doit être effectuée auprès de votre autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="53372-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="53372-214">Ouvrez votre PowerShell Skype entreprise Server :</span><span class="sxs-lookup"><span data-stu-id="53372-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="53372-215">Pour un SAN de service de découverte automatique (en remplaçant le paramètre -Ca par votre propre chemin d'accès à l'autorité de certification) :</span><span class="sxs-lookup"><span data-stu-id="53372-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="53372-216">À présent, si vous avez plusieurs domaines SIP, vous ne pouvez pas utiliser le paramètre AllSipDomain comme dans l’exemple ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="53372-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="53372-217">Vous devrez plutôt utiliser le paramètre DomainName.</span><span class="sxs-lookup"><span data-stu-id="53372-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="53372-218">De plus, lorsque vous utilisez le paramètre DomainName, vous devez définir le nom de domaine complet pour les enregistrements lyncdiscoverinternal et lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="53372-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="53372-219">En voici des exemples (en remplaçant le paramètre -Ca par votre propre chemin d'accès à l'autorité de certification) :</span><span class="sxs-lookup"><span data-stu-id="53372-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="53372-220">Une fois que les nouveaux certificats ont été générés par votre autorité de certification, vous devrez les affecter.</span><span class="sxs-lookup"><span data-stu-id="53372-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="53372-221">Affecter des certificats à l'aide de Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="53372-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="53372-222">En fonction de ce que vous avez trouvé dans la section Dois-je obtenir de nouveaux certificats ci-dessus, vous devrez effectuer l'\*\*une \*\* des mesures suivantes.</span><span class="sxs-lookup"><span data-stu-id="53372-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="53372-223">Si vous disposez d'un certificat unique pour tout (les thumbprints sont identiques), vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="53372-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="53372-224">Si vous disposez de plusieurs certificats (les thumbprints sont tous différents), procédez plutôt comme suit :</span><span class="sxs-lookup"><span data-stu-id="53372-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="53372-225">Affichage des certificats dans la console MMC (Microsoft Management Console)</span><span class="sxs-lookup"><span data-stu-id="53372-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="53372-p117">Vous avez la possibilité de consulter vos certificats à l'aide du composant logiciel enfichable Certificats pour la console MMC. Saisissez simplement MMC dans la zone de recherche pour les faire apparaître en tant qu'option d'application</span><span class="sxs-lookup"><span data-stu-id="53372-p117">You have an option to look at your certificates using the Certificates snap-in for the MMC. Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="53372-p118">Pour ajouter le composant logiciel enfichable Certificats, cliquez sur **Fichier**, puis sur **Ajouter/Supprimer un composant logiciel enfichable...** (ou utilisez le raccourci clavier **Ctrl+M**). **Certificats** apparaîtra comme option dans le volet de gauche ; sélectionnez-la, puis choisissez **Compte d'ordinateur** dans la fenêtre contextuelle et cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="53372-p118">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work). **Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="53372-230">Vous effectuez probablement cette opération sur l'ordinateur qui héberge les certificats que vous souhaitez consulter, vous pouvez donc laisser la sélection, toujours dans la fenêtre contextuelle, sur **Ordinateur local**.</span><span class="sxs-lookup"><span data-stu-id="53372-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="53372-231">Si vous utilisez une machine distante, changez le bouton radio sur **Autre ordinateur**, puis entrez le nom de domaine complet de cet ordinateur ou utilisez le bouton **Naviguer** pour rechercher cet ordinateur via Active Directory.</span><span class="sxs-lookup"><span data-stu-id="53372-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="53372-232">Après avoir sélectionné l’ordinateur, vous devez cliquer sur **Terminer** lorsque vous êtes prêt, puis sur **OK** pour ajouter le composant logiciel enfichable à la console MMC.</span><span class="sxs-lookup"><span data-stu-id="53372-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="53372-233">Développez la section **certificats** dans le volet gauche de la console MMC.</span><span class="sxs-lookup"><span data-stu-id="53372-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="53372-234">Développez également le dossier **Personnel**, puis sélectionnez **Certificats**.</span><span class="sxs-lookup"><span data-stu-id="53372-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="53372-235">Ceci vous permet de visualiser les certificats dans ce magasin.</span><span class="sxs-lookup"><span data-stu-id="53372-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="53372-236">Localisez le certificat que vous souhaitez visualiser, cliquez dessus avec le bouton de la souris et sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="53372-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="53372-237">Comment savez-vous de quel certificat il s'agit ?</span><span class="sxs-lookup"><span data-stu-id="53372-237">How do you know what certificate this is?</span></span> <span data-ttu-id="53372-238">Il doit s’agir du certificat unique affecté à tout le contenu de votre batterie de serveurs, ou vous pouvez avoir plusieurs certificats pour différentes choses (par exemple, des services Web internes par défaut, etc.).</span><span class="sxs-lookup"><span data-stu-id="53372-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="53372-239">Plusieurs certificats auront le même thumbprint.</span><span class="sxs-lookup"><span data-stu-id="53372-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="53372-p122">Une fois l'affichage **Certificat** défini, sélectionnez **Détails**. Ceci vous permettra de visualiser le nom de l'objet du certificat lorsque vous sélectionnerez **Objet** et le nom de l'objet affecté ainsi que les propriétés associées s'afficheront.</span><span class="sxs-lookup"><span data-stu-id="53372-p122">Once you've gotten to the **Certificate** view, choose **Details**. This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="53372-p123">Vous devrez également vérifier les entrées \*\*Autres noms du sujet \*\*. Les éléments suivants peuvent apparaître :</span><span class="sxs-lookup"><span data-stu-id="53372-p123">You'll also need to check the **Subject Alternate Name** entries. You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="53372-244">Nom du pool pour ce pool ou nom de serveur unique s’il ne s’agit pas d’un pool.</span><span class="sxs-lookup"><span data-stu-id="53372-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="53372-245">Nom du serveur auquel le certificat est affecté.</span><span class="sxs-lookup"><span data-stu-id="53372-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="53372-246">Enregistrements d’URL simples, généralement meet et dialin.</span><span class="sxs-lookup"><span data-stu-id="53372-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="53372-247">Services Web internes et services Web (par exemple, webpool01.contoso.net, webpool01.contoso.com), en fonction des choix effectués dans le générateur de topologie et des sélections de services Web.</span><span class="sxs-lookup"><span data-stu-id="53372-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="53372-248">S’il est déjà attribué, le lyncdiscover. \<sipdomain\> et lyncdiscoverinternal. \<enregistrements\> sipdomain.</span><span class="sxs-lookup"><span data-stu-id="53372-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="53372-249">Vous devrez vérifier les différents certificats dans le cas où plusieurs certificats ont été affectés (consultez la remarque ci-dessus).</span><span class="sxs-lookup"><span data-stu-id="53372-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="53372-250">Par conséquent, si vous trouvez lyncdiscover. \<sipdomain\> et lyncdiscoverinternal. \<sipdomain\> les enregistrements que vous avez déjà configurés.</span><span class="sxs-lookup"><span data-stu-id="53372-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="53372-251">Vous pouvez fermer la console MMC.</span><span class="sxs-lookup"><span data-stu-id="53372-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="53372-252">S'ils ne sont pas affectés, vous devrez effectuer une nouvelle demande de certificat (telle que décrite ci-dessus) ou les installer une fois la demande effectuée (nous recommandons d'utiliser PowerShell à cet effet).</span><span class="sxs-lookup"><span data-stu-id="53372-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="53372-253">Configurer le proxy inverse</span><span class="sxs-lookup"><span data-stu-id="53372-253">Configure the reverse proxy</span></span>
<span data-ttu-id="53372-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="53372-254"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="53372-p125">Les étapes ci-dessous ne doivent pas nécessairement être suivies pas à pas. Dans les versions précédentes de ce produit, nous vous avons par exemple guidé tout au long de la procédure de configuration de Threat Management Gateway (TMG) et si vous ne l'utilisez pas, vous devrez élaborer votre propre procédure selon la version que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="53372-p125">The steps below are not meant to be followed exactly. That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="53372-257">TMG n’est plus offert par Microsoft en tant que produit et, si vous le souhaitez, vous pouvez examiner les étapes de la [2013 serveur Lync](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="53372-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="53372-258">Toutefois, les informations suivantes sont destinées à être plus utiles, même si vous n’êtes pas en mesure de fournir des étapes de procédures spécifiques pour chaque proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="53372-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="53372-259">Deux points essentiels doivent être pris en compte :</span><span class="sxs-lookup"><span data-stu-id="53372-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="53372-260">Allez-vous effectuer votre demande de découverte automatique initiale sur HTTPS (ce que nous recommandons) ?</span><span class="sxs-lookup"><span data-stu-id="53372-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="53372-261">Si vous avez une règle de publication web, vous devez la modifier.</span><span class="sxs-lookup"><span data-stu-id="53372-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="53372-262">Si vous n'avez pas de règle de publication web, vous devez la créer.</span><span class="sxs-lookup"><span data-stu-id="53372-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="53372-263">Si vous effectuez votre demande de découverte automatique initiale sur HTTPS, vous devrez également créer ou modifier cette règle.</span><span class="sxs-lookup"><span data-stu-id="53372-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="53372-264">**Important** La valeur du délai d’expiration du proxy est un nombre qui peut varier d’un déploiement au déploiement.</span><span class="sxs-lookup"><span data-stu-id="53372-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="53372-265">Nous vous conseillons de surveiller votre déploiement et de modifier la valeur de la meilleure utilisation pour les clients.</span><span class="sxs-lookup"><span data-stu-id="53372-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="53372-266">Il est possible que vous puissiez définir la valeur sur une valeur inférieure ou égale à 200.</span><span class="sxs-lookup"><span data-stu-id="53372-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="53372-267">Si vous prenez en charge des clients mobiles Lync dans votre environnement, définissez la valeur sur 960 pour autoriser les délais d’expiration de la notification de transmission d’Office 365, qui ont une valeur de délai d’expiration de 900.</span><span class="sxs-lookup"><span data-stu-id="53372-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="53372-268">Il est très probable que vous deviez augmenter la valeur du délai d’expiration pour éviter que le client se déconnecte lorsque la valeur est trop faible, ou si les connexions par le biais du proxy ne se déconnectent pas une fois qu’il a été déconnecté.</span><span class="sxs-lookup"><span data-stu-id="53372-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="53372-269">Le fait de surveiller et de définir ce qui est habituel pour votre environnement est le seul moyen de déterminer le paramètre approprié pour cette valeur.</span><span class="sxs-lookup"><span data-stu-id="53372-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="53372-270">Modifiez la règle de publication web existante pour votre SAN et URL de découverte automatique externes.</span><span class="sxs-lookup"><span data-stu-id="53372-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="53372-271">Ouvrez votre interface de proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="53372-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="53372-272">Vous devez localiser votre règle de publication Web, puis sélectionner l’option modifier (il peut s’agir d’un menu ou d’un onglet, en fonction de votre configuration de proxy inverse).</span><span class="sxs-lookup"><span data-stu-id="53372-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="53372-273">Un emplacement doit être utilisé pour indiquer le type de cette règle de publication Web.</span><span class="sxs-lookup"><span data-stu-id="53372-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="53372-274">Vous devez modifier cette règle pour les sites entrants ou les demandes pour les sites.</span><span class="sxs-lookup"><span data-stu-id="53372-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="53372-275">Vous allez **ajouter** une nouvelle entrée.</span><span class="sxs-lookup"><span data-stu-id="53372-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="53372-276">Tapez le nom de votre site de découverte automatique (l’exemple utilisé est lyncdiscover.contoso.com), puis cliquez sur **OK** ou sur **Enregistrer**en fonction du format de votre proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="53372-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="53372-277">Vous devez avoir un nouveau certificat contenant l'entrée SAN de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="53372-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="53372-278">Il doit être installé en même temps et configuré pour une utilisation en fonction des paramètres de votre proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="53372-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="53372-279">Assurez-vous de tout sauvegarder une fois la configuration terminée.</span><span class="sxs-lookup"><span data-stu-id="53372-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="53372-280">Si votre proxy inverse dispose d’une fonctionnalité de **test** , utilisez-le pour vous assurer que tout fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="53372-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="53372-281">À présent, il est possible que vous deviez répéter ces étapes si vous disposez d’un directeur ou d’un pool de réalisateur dans votre environnement (cela signifie que vous disposez d’une deuxième règle).</span><span class="sxs-lookup"><span data-stu-id="53372-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="53372-282">Créer une règle de publication Web pour l’URL de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="53372-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="53372-283">Ouvrez votre interface de proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="53372-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="53372-284">Vous devez localiser l’emplacement dans l’interface dans laquelle vous créez les règles de publication Web, puis sélectionner l’option **nouveau** ou **créer** (il peut s’agir d’un menu ou d’un onglet, en fonction de votre configuration de proxy inverse).</span><span class="sxs-lookup"><span data-stu-id="53372-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="53372-285">Vous recherchez l'option permettant de créer une nouvelle règle de publication web.</span><span class="sxs-lookup"><span data-stu-id="53372-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="53372-286">Vous devrez généralement saisir les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="53372-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="53372-287">**Nom** : le nom de votre règle.</span><span class="sxs-lookup"><span data-stu-id="53372-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="53372-288">**Action**de la règle : dans ce cas, il s’agit d’une règle d' **autorisation** , que vous laissez un autre proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="53372-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="53372-289">La règle ou l'option de **Publication** que vous choisissez doit être **un seul site web ou équilibrage de charge**.</span><span class="sxs-lookup"><span data-stu-id="53372-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="53372-290">Choisissez l'option **SSL** pour l'accès externe.</span><span class="sxs-lookup"><span data-stu-id="53372-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="53372-291">Vous aurez besoin de publier un chemin pour la **publication interne**, puis entrez le nom de domaine complet (FQDN) pour les services Web externes sur le solde de charge de votre pool frontal (ou le nom de domaine complet du solde de charge du pool de réalisateur si vous en avez un); par exemple, sfb_pool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="53372-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="53372-292">Vous devez taper \*\* / \*\*\* pour le chemin d’accès à publier, mais vous devez également **transférer l’en-tête d’hôte d’origine**.</span><span class="sxs-lookup"><span data-stu-id="53372-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="53372-p131">Une option vous permettra de sélectionner les informations du **nom public ou externe**. À cet endroit, vous pourrez saisir les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="53372-p131">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="53372-295">**Accepter les demandes**, mais pour le nom de domaine.</span><span class="sxs-lookup"><span data-stu-id="53372-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="53372-296">Pour le **Nom**, vous devez saisir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="53372-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="53372-297"><sipdomain>(il s’agit de l’URL du service de découverte automatique externe).</span><span class="sxs-lookup"><span data-stu-id="53372-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="53372-298">À présent, si vous créez une règle pour l’URL des services Web externes sur le pool frontal, vous devez taper le nom de domaine complet (FQDN) pour les services Web externes dans votre liste frontale (par exemple, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="53372-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="53372-299">Une option **path** sera disponible et vous devrez entrer \*\* / \*\*\* ici.</span><span class="sxs-lookup"><span data-stu-id="53372-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="53372-300">Vous devrez sélectionner un **Écouteur SSL** avec votre certificat public à jour.</span><span class="sxs-lookup"><span data-stu-id="53372-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="53372-301">**Délégation de l’authentification** doit être définie sur **Aucune délégation**, mais une authentification client directe **doit** être autorisée.</span><span class="sxs-lookup"><span data-stu-id="53372-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="53372-302">La règle doit être définie sur **Tous les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="53372-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="53372-303">Il s'agit de toutes les informations dont vous avez besoin pour créer cette règle et vous permettre de suivre la procédure.</span><span class="sxs-lookup"><span data-stu-id="53372-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="53372-304">Vous devez vous assurer que l'**en-tête de l’hôte d’origine** est transmis.</span><span class="sxs-lookup"><span data-stu-id="53372-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="53372-305">Les ports du **serveur web** devront également être définis ; procédez de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="53372-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="53372-306">**Rediriger les demandes au port HTTP**, avec le numéro de port **8080**.</span><span class="sxs-lookup"><span data-stu-id="53372-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="53372-307">**Rediriger les demandes au port SSL**, avec le numéro de port **4443**.</span><span class="sxs-lookup"><span data-stu-id="53372-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="53372-308">Une fois tous les éléments configurés, vous devrez enregistrer et appliquer les paramètres, puis tester la règle.</span><span class="sxs-lookup"><span data-stu-id="53372-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="53372-309">Créer une règle de publication web pour le port 80 (facultatif)</span><span class="sxs-lookup"><span data-stu-id="53372-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="53372-310">Ouvrez votre interface de proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="53372-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="53372-311">Vous devez localiser l’emplacement dans l’interface dans laquelle vous créez les règles de publication Web, puis sélectionner l’option **nouveau** ou **créer** (il peut s’agir d’un menu ou d’un onglet, en fonction de votre configuration de proxy inverse).</span><span class="sxs-lookup"><span data-stu-id="53372-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="53372-312">Vous recherchez l'option permettant de créer une nouvelle règle de publication web.</span><span class="sxs-lookup"><span data-stu-id="53372-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="53372-313">Vous devrez généralement saisir les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="53372-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="53372-314">**Nom** : le nom de votre règle.</span><span class="sxs-lookup"><span data-stu-id="53372-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="53372-315">**Action**de la règle : dans ce cas, il s’agit d’une règle d' **autorisation** , que vous laissez un autre proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="53372-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="53372-316">La règle ou l'option de **Publication** que vous choisissez doit être **un seul site web ou équilibrage de charge**.</span><span class="sxs-lookup"><span data-stu-id="53372-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="53372-317">Une **connexion non sécurisée est nécessaire pour se connecter au serveur web publié ou à la batterie de serveurs**.</span><span class="sxs-lookup"><span data-stu-id="53372-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="53372-318">Vous devez publier un chemin pour la **publication interne**et entrer le nom de domaine complet (FQDN) de l' **adresse VIP** de l’équilibrage de charge de votre pool frontal, par exemple sfb_pool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="53372-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="53372-319">Vous devez taper \*\* / \*\*\* pour le chemin d’accès à publier, mais vous devez également **transférer l’en-tête d’hôte d’origine**.</span><span class="sxs-lookup"><span data-stu-id="53372-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="53372-p134">Une option vous permettra de sélectionner les informations du **nom public ou externe**. À cet endroit, vous pourrez saisir les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="53372-p134">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="53372-322">**Accepter les demandes**, mais pour le nom de domaine.</span><span class="sxs-lookup"><span data-stu-id="53372-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="53372-323">Pour le **Nom**, vous devez saisir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="53372-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="53372-324"><sipdomain>(il s’agit de l’URL du service de découverte automatique externe).</span><span class="sxs-lookup"><span data-stu-id="53372-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="53372-325">Une option **path** sera disponible et vous devrez entrer \*\* / \*\*\* ici.</span><span class="sxs-lookup"><span data-stu-id="53372-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="53372-326">Vous devez sélectionner un écouteur Web ou autoriser votre proxy inverse à en créer un pour vous.</span><span class="sxs-lookup"><span data-stu-id="53372-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="53372-327">**Délégation de l’authentification** doit être définie sur **Aucune délégation**, mais une authentification client directe **ne doit pas** être autorisée.</span><span class="sxs-lookup"><span data-stu-id="53372-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="53372-328">La règle doit être définie sur **Tous les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="53372-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="53372-329">Il s'agit de toutes les informations dont vous avez besoin pour créer cette règle et vous permettre de suivre la procédure.</span><span class="sxs-lookup"><span data-stu-id="53372-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="53372-330">Les ports du **serveur web** devront être définis ; procédez de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="53372-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="53372-331">**Rediriger les demandes au port HTTP**, avec le numéro de port **8080**.</span><span class="sxs-lookup"><span data-stu-id="53372-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="53372-332">**Rediriger les demandes au port SSL**, avec le numéro de port **4443**.</span><span class="sxs-lookup"><span data-stu-id="53372-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="53372-333">Une fois tous les éléments configurés, vous devrez enregistrer et appliquer les paramètres, puis tester la règle.</span><span class="sxs-lookup"><span data-stu-id="53372-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="53372-334">Configurer la découverte automatique pour la mobilité avec les déploiements hybrides</span><span class="sxs-lookup"><span data-stu-id="53372-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="53372-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="53372-335"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="53372-336">Les environnements hybrides dans Skype entreprise Server sont des environnements qui combinent un environnement local et Office 365.</span><span class="sxs-lookup"><span data-stu-id="53372-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="53372-337">Lorsque Skype entreprise Server fonctionne dans un environnement hybride, le service de découverte automatique doit être en mesure de rechercher un utilisateur à partir de l’un de ces environnements.</span><span class="sxs-lookup"><span data-stu-id="53372-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="53372-p137">Pour permettre aux clients mobiles de découvrir où est localisé un utilisateur, le service de découverte automatique doit être configuré avec une nouvelle URL (uniform resource locator). Les étapes à suivre sont :</span><span class="sxs-lookup"><span data-stu-id="53372-p137">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL). The steps are:</span></span>
  
1. <span data-ttu-id="53372-340">Ouvrez Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="53372-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="53372-341">Pour obtenir la valeur de l’attribut **ProxyFQDN** pour votre environnement Skype entreprise Server, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="53372-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="53372-342">Puis, toujours dans la fenêtre de shell, exécutez :</span><span class="sxs-lookup"><span data-stu-id="53372-342">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="53372-343">Où [identity] est remplacé par le nom de domaine de l’espace d’adresses SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="53372-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="53372-344">Tester votre déploiement de mobilité</span><span class="sxs-lookup"><span data-stu-id="53372-344">Test your Mobility deployment</span></span>
<span data-ttu-id="53372-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="53372-345"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="53372-346">Une fois que vous avez déployé le service de mobilité Skype entreprise Server et le service de découverte automatique Skype entreprise Server, vous pouvez exécuter une transaction de test pour vous assurer que votre déploiement fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="53372-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="53372-347">Vous pouvez exécuter **Test-CsUcwaConference** afin de tester la capacité de deux utilisateurs à créer et à rejoindre une conférence, ainsi qu'à y communiquer.</span><span class="sxs-lookup"><span data-stu-id="53372-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="53372-348">Il vous faudra deux utilisateurs (réels ou tests) et leurs informations d'identification complètes pour effectuer ce test.</span><span class="sxs-lookup"><span data-stu-id="53372-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="53372-349">Cette commande fonctionne pour les clients Skype entreprise et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53372-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="53372-350">Pour les clients Lync Server 2010 sur Skype entreprise Server 2015, vous devez exécuter **le test-CsMcxP2PIM** .</span><span class="sxs-lookup"><span data-stu-id="53372-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="53372-351">Vos utilisateurs de Lync Server 2010 doivent toujours être des utilisateurs réels ou des utilisateurs de test prédéfinis et vous aurez besoin de leurs informations d’identification de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="53372-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="53372-352">La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="53372-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="53372-353">Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts.</span><span class="sxs-lookup"><span data-stu-id="53372-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="53372-354">Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="53372-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="53372-355">Conférence test pour clients mobiles Skype Entreprise et Lync 2013</span><span class="sxs-lookup"><span data-stu-id="53372-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="53372-356">Ouvrez une session en tant que membre du rôle **CsAdministrator** sur n’importe quel ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="53372-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="53372-357">Démarrez **Skype entreprise Server Management Shell** (vous pouvez taper le nom dans la zone de recherche ou accédez à **tous les programmes** , puis sélectionnez-le).</span><span class="sxs-lookup"><span data-stu-id="53372-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="53372-358">Dans la ligne de commande, saisissez :</span><span class="sxs-lookup"><span data-stu-id="53372-358">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="53372-p141">Il est également possible de définir des informations d’identification dans un script et de les transmettre à l'applet de commande de test. Un exemple est fourni ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="53372-p141">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="53372-361">Conférence test pour clients mobiles Lync 2010</span><span class="sxs-lookup"><span data-stu-id="53372-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="53372-362">La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="53372-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="53372-363">Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts.</span><span class="sxs-lookup"><span data-stu-id="53372-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="53372-364">Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="53372-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="53372-365">Ouvrez une session en tant que membre du rôle **CsAdministrator** sur n’importe quel ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="53372-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="53372-366">Démarrez **Skype entreprise Server Management Shell** (vous pouvez taper le nom dans la zone de recherche ou accédez à **tous les programmes** , puis sélectionnez-le).</span><span class="sxs-lookup"><span data-stu-id="53372-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="53372-367">Dans la ligne de commande, saisissez :</span><span class="sxs-lookup"><span data-stu-id="53372-367">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="53372-p143">Il est également possible de définir des informations d’identification dans un script et de les transmettre à l'applet de commande de test. Un exemple est fourni ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="53372-p143">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="53372-370">Pour examiner en détail les procédures de commande, vous pouvez consulter [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) et [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="53372-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="53372-371">Configurer les notifications push</span><span class="sxs-lookup"><span data-stu-id="53372-371">Configure for push notifications</span></span>
<span data-ttu-id="53372-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="53372-372"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="53372-373">Les notifications push, sous forme de badges, d’icônes ou d’alertes, peuvent être envoyées à un appareil mobile même lorsque l'application Skype ou Lync est inactive.</span><span class="sxs-lookup"><span data-stu-id="53372-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="53372-374">Que sont les notifications de transmission ?</span><span class="sxs-lookup"><span data-stu-id="53372-374">But what are push notifications?</span></span> <span data-ttu-id="53372-375">Ce sont des alertes pour des événements, comme des invitations de messagerie instantanée nouvelles ou manquées, ou un message vocal reçu.</span><span class="sxs-lookup"><span data-stu-id="53372-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="53372-376">Le service de mobilité Skype entreprise Server envoie ces notifications au service de notification Poussée dans le Cloud de Skype entreprise Server, qui envoie les notifications au service de notifications de transmission de Microsoft (MSNS) pour les utilisateurs de Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="53372-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="53372-377">Cette fonctionnalité n’est pas modifiée à partir de Lync Server 2013, mais si vous disposez d’un serveur Skype entreprise, vous devez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="53372-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="53372-378">Pour un serveur Edge Skype entreprise Server, ajoutez un nouveau fournisseur d’hébergement, Microsoft Skype entreprise Online, puis configurez la Fédération des fournisseurs d’hébergement entre votre organisation et Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="53372-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="53372-p145">Activez les notifications push en exécutant l’applet de commande **Set-CsPushNotificationConfiguration**. Par défaut, les notifications push sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="53372-p145">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet. By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="53372-381">Testez votre configuration de fédération et les notifications push.</span><span class="sxs-lookup"><span data-stu-id="53372-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="53372-382">Configurer Skype Entreprise Edge Server pour les notifications push</span><span class="sxs-lookup"><span data-stu-id="53372-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="53372-383">Ouvrez une session avec un compte membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="53372-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="53372-384">Démarrez **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="53372-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="53372-385">Ajoutez un fournisseur d’hébergement en ligne Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="53372-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="53372-386">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="53372-386">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="53372-p146">Vous ne pouvez pas avoir plus d’une relation de fédération avec un même fournisseur d’hébergement. Par conséquent, si vous avez déjà configuré un fournisseur d’hébergement ayant une relation de fédération avec sipfed.online.lync.com, vous ne devez pas ajouter d’autre fournisseur d’hébergement, même si l’identité du fournisseur d’hébergement est différente de SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="53372-p146">You can't have more than one federation relationship with a single hosting provider. So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="53372-389">Configurez la Fédération des fournisseurs d’hébergement entre votre organisation et le service de notifications de transmission de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="53372-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="53372-390">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="53372-390">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="53372-391">Activer les notifications push</span><span class="sxs-lookup"><span data-stu-id="53372-391">Enable push notifications</span></span>

1. <span data-ttu-id="53372-392">Ouvrez une session avec un compte membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="53372-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="53372-393">Démarrez **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="53372-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="53372-394">Activer les notifications push :</span><span class="sxs-lookup"><span data-stu-id="53372-394">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="53372-395">Activer la fédération :</span><span class="sxs-lookup"><span data-stu-id="53372-395">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="53372-396">Tester la fédération et les notifications push</span><span class="sxs-lookup"><span data-stu-id="53372-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="53372-397">Ouvrez une session avec un compte membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="53372-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="53372-398">Démarrez **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="53372-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="53372-399">Testez la configuration de la fédération :</span><span class="sxs-lookup"><span data-stu-id="53372-399">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="53372-400">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="53372-400">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="53372-401">Testez vos notifications push</span><span class="sxs-lookup"><span data-stu-id="53372-401">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="53372-402">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="53372-402">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="53372-403">Configurer la stratégie de mobilité</span><span class="sxs-lookup"><span data-stu-id="53372-403">Configure Mobility policy</span></span>
<span data-ttu-id="53372-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="53372-404"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="53372-405">Skype entreprise Server vous permet de déterminer qui peut utiliser votre service de mobilité, de passer des appels par le biais de votre travail, de la voix sur IP (VoIP) ou de la vidéo, et si vous avez besoin d’un réseau Wi-Fi ou d’une vidéo.</span><span class="sxs-lookup"><span data-stu-id="53372-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="53372-406">La fonctionnalité d'Appel via le Bureau permet à un utilisateur mobile d'utiliser son numéro de téléphone professionnel, plutôt que son numéro de téléphone mobile, pour passer et recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="53372-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="53372-407">La personne à l'autre bout de la ligne ne verra pas le numéro de téléphone mobile de cet utilisateur, et cet utilisateur mobile n'aura pas à payer de frais d'appels sortants.</span><span class="sxs-lookup"><span data-stu-id="53372-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="53372-408">Lorsque VoIP et la vidéo sont configurés, les utilisateurs peuvent prendre et effectuer des appels VoIP et vidéo.</span><span class="sxs-lookup"><span data-stu-id="53372-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="53372-409">Les paramètres d'utilisation de la fonctionnalité WiFi permettent de déterminer si l'appareil mobile d'un utilisateur sera requis pour utiliser un réseau WiFi sur un réseau de données cellulaires.</span><span class="sxs-lookup"><span data-stu-id="53372-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="53372-410">Les fonctionnalités de mobilité, d’appel via le bureau et les fonctions VoIP et vidéo sont toutes activées par défaut.</span><span class="sxs-lookup"><span data-stu-id="53372-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="53372-411">Les paramètres pour exiger WiFi pour VoIP et pour la vidéo sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="53372-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="53372-412">Un administrateur a la capacité de modifier ces paramètres, soit de manière globale, soit par site ou par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="53372-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="53372-413">Pour pouvoir utiliser les fonctionnalités de mobilité et l’appel via le bureau, les utilisateurs doivent être :</span><span class="sxs-lookup"><span data-stu-id="53372-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="53372-414">Activé pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="53372-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="53372-415">Activés pour Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="53372-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="53372-416">Attribution d’une stratégie de mobilité dont l’option **EnableMobility** est définie sur **true**.</span><span class="sxs-lookup"><span data-stu-id="53372-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="53372-417">Pour pouvoir utiliser la fonctionnalité d'Appel via le Bureau, les utilisateurs doivent également être :</span><span class="sxs-lookup"><span data-stu-id="53372-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="53372-418">Affectés à une stratégie de voix dont l’option \*\*Activer la sonnerie simultanée de téléphones \*\* est activée.</span><span class="sxs-lookup"><span data-stu-id="53372-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="53372-419">Attribution d’une stratégie de mobilité qui utilise la propriété **EnableOutsideVoice** définie sur **true**.</span><span class="sxs-lookup"><span data-stu-id="53372-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="53372-p150">Les utilisateurs non activés pour Voix Entreprise peuvent utiliser leur appareil mobile pour effectuer des appels de Skype à Skype VoIP ou peuvent participer à des conférences via le lien Clic pour participer sur leur appareil mobile, si les options adéquates sont configurées pour la stratégie de voix à laquelle ils sont associés. Vous trouverez plus de détails dans la rubrique Planification.</span><span class="sxs-lookup"><span data-stu-id="53372-p150">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with. There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="53372-422">Modifier la stratégie de mobilité globale</span><span class="sxs-lookup"><span data-stu-id="53372-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="53372-423">Ouvrez une session avec un compte membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="53372-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="53372-424">Démarrez **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="53372-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="53372-425">Désactivez l’accès à la mobilité et aux appels via le mode de fonctionnement global en entrant :</span><span class="sxs-lookup"><span data-stu-id="53372-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="53372-426">Vous pouvez désactiver les appels via le mode de fonctionnement sans désactiver l’accès à la mobilité.</span><span class="sxs-lookup"><span data-stu-id="53372-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="53372-427">En revanche, vous ne pouvez pas désactiver la mobilité sans désactiver la fonction d’appel via le mode de fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="53372-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="53372-428">Pour plus d’informations, consultez la rubrique [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="53372-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="53372-429">Modifier la stratégie de mobilité par site</span><span class="sxs-lookup"><span data-stu-id="53372-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="53372-430">Ouvrez une session avec un compte membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="53372-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="53372-431">Démarrez **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="53372-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="53372-p152">Vous pouvez créer une stratégie au niveau du site, désactiver les fonctionnalités VoIP et vidéo et activer l'option Exiger WiFi pour l'audio IP et Exiger WiFi pour la vidéo IP par site.</span><span class="sxs-lookup"><span data-stu-id="53372-p152">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site. Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="53372-434">Pour en savoir plus, reportez-vous à [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="53372-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="53372-435">Modifier la stratégie de mobilité par utilisateur</span><span class="sxs-lookup"><span data-stu-id="53372-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="53372-436">Ouvrez une session avec un compte membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="53372-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="53372-437">Démarrez **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="53372-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="53372-438">Créez des stratégies de mobilité au niveau utilisateur, puis désactivez la mobilité et les appels via votre bureau.</span><span class="sxs-lookup"><span data-stu-id="53372-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="53372-439">Tapez :</span><span class="sxs-lookup"><span data-stu-id="53372-439">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="53372-440">Autre exemple avec échantillons de données :</span><span class="sxs-lookup"><span data-stu-id="53372-440">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="53372-441">Vous pouvez désactiver les appels via le mode de fonctionnement sans désactiver l’accès à la mobilité.</span><span class="sxs-lookup"><span data-stu-id="53372-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="53372-442">En revanche, vous ne pouvez pas désactiver la mobilité sans désactiver la fonction d’appel via le mode de fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="53372-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

