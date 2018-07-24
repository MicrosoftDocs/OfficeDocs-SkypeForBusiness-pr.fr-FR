---
title: Déployer et configurer la mobilité pour Skype pour Business Server
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Cet article vous guidera dans les étapes pour configurer un Skype existant pour l’installation de Business Server afin d’utiliser le service de mobilité, qui permet à vos appareils mobiles et être en mesure de tirer parti de Skype pour les fonctionnalités de mobilité Server.
ms.openlocfilehash: c8d30f11fed3b6c45f06b7e21f0038bee0274df4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003137"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="6e174-103">Déployer et configurer la mobilité pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="6e174-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="6e174-104">Cet article vous guidera dans les étapes pour configurer un Skype existant pour l’installation de Business Server afin d’utiliser le service de mobilité, qui permet à vos appareils mobiles et être en mesure de tirer parti de Skype pour les fonctionnalités de mobilité Server.</span><span class="sxs-lookup"><span data-stu-id="6e174-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="6e174-105">Avoir examiné l’article [Plan pour la mobilité pour Skype pour Business Server](../plan-your-deployment/mobility.md) , vous devez être prêt à effectuer les étapes ci-dessous pour déployer la mobilité dans votre Skype pour un environnement de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="6e174-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="6e174-106">Voici les étapes à suivre (avec une liste des autorisations incluse dans le tableau) :</span><span class="sxs-lookup"><span data-stu-id="6e174-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="6e174-107">**Phase**</span><span class="sxs-lookup"><span data-stu-id="6e174-107">**Phase**</span></span>|<span data-ttu-id="6e174-108">**Autorisations**</span><span class="sxs-lookup"><span data-stu-id="6e174-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="6e174-109">Créer des enregistrements DNS</span><span class="sxs-lookup"><span data-stu-id="6e174-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="6e174-110">DomainAdmins</span><span class="sxs-lookup"><span data-stu-id="6e174-110">Domain Admins</span></span>  <br/> <span data-ttu-id="6e174-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="6e174-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="6e174-112">Modifier les certificats</span><span class="sxs-lookup"><span data-stu-id="6e174-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="6e174-113">Administrateur local</span><span class="sxs-lookup"><span data-stu-id="6e174-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="6e174-114">Configurer le proxy inverse</span><span class="sxs-lookup"><span data-stu-id="6e174-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="6e174-115">Administrateur local</span><span class="sxs-lookup"><span data-stu-id="6e174-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="6e174-116">Configurer la découverte automatique pour la mobilité avec les déploiements hybrides</span><span class="sxs-lookup"><span data-stu-id="6e174-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="6e174-117">DomainAdmins</span><span class="sxs-lookup"><span data-stu-id="6e174-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="6e174-118">Tester votre déploiement de mobilité</span><span class="sxs-lookup"><span data-stu-id="6e174-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="6e174-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6e174-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="6e174-120">Configurer les notifications push</span><span class="sxs-lookup"><span data-stu-id="6e174-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="6e174-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6e174-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="6e174-122">Configurer la stratégie de mobilité</span><span class="sxs-lookup"><span data-stu-id="6e174-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="6e174-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6e174-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="6e174-p102">Toutes les sections suivantes comprennent des étapes qui impliquent que vous ayez parcouru la rubrique concernant la planification. En cas de doute, n'hésitez pas à consulter les informations fournies ici.</span><span class="sxs-lookup"><span data-stu-id="6e174-p102">All the following sections contain steps that assume you've read the Planning topic. If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="6e174-126">Prise en charge MCX pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6e174-126">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="6e174-127">Vos utilisateurs devez mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="6e174-127">Your users will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="6e174-128">Créer des enregistrements DNS</span><span class="sxs-lookup"><span data-stu-id="6e174-128">Create DNS records</span></span>
<span data-ttu-id="6e174-129"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="6e174-129"></span></span>

<span data-ttu-id="6e174-130">Vous disposez peut-être déjà dans le cadre de votre Skype pour un environnement Business Server, mais vous n’avez pas besoin de créer les enregistrements suivants pour la découverte automatique fonctionner :</span><span class="sxs-lookup"><span data-stu-id="6e174-130">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="6e174-131">un enregistrement DNS interne afin de prendre en charge les utilisateurs mobiles qui se connectent depuis le réseau de votre organisation ;</span><span class="sxs-lookup"><span data-stu-id="6e174-131">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="6e174-132">un enregistrement DNS externe (ou public) afin de prendre en charge les utilisateurs mobiles qui se connectent depuis le réseau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6e174-132">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="6e174-133">Ces enregistrements sont soit des enregistrements de noms (d'hôte) A, soit des enregistrements CNAME (vous n'avez pas à créer ces deux enregistrements, mais nous décrivons ici toutes les étapes pour les deux types d'enregistrement).</span><span class="sxs-lookup"><span data-stu-id="6e174-133">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="6e174-134">Créer un enregistrement CNAME DNS interne</span><span class="sxs-lookup"><span data-stu-id="6e174-134">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="6e174-135">Ouvrez une session sur un serveur DNS de votre réseau qui est membre du groupe **Administrateurs du domaine** ou du groupe **DnsAdmins**.</span><span class="sxs-lookup"><span data-stu-id="6e174-135">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="6e174-136">Cliquez sur **Démarrer**, Sélectionnez **Outils d’administration ** (vous devrez peut-être **Rechercher ** l'option si elle n'existe pas dans le menu Démarrer), puis cliquez sur **DNS** pour ouvrir le composant logiciel enfichable d'administration DNS.</span><span class="sxs-lookup"><span data-stu-id="6e174-136">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="6e174-137">Dans le volet gauche de la fenêtre de console, vous devez accéder au domaine d’accueil à votre Skype pour les serveurs frontaux Business Server et développez **Zones de recherche directes** il.</span><span class="sxs-lookup"><span data-stu-id="6e174-137">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="6e174-138">Prenez un moment pour vérifiez lequel des enregistrements suivants vous avez :</span><span class="sxs-lookup"><span data-stu-id="6e174-138">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="6e174-139">N’importe quel A ou AAAA enregistrements d’hôte pour votre serveur frontal (Standard ou Enterprise) ou les pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="6e174-139">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="6e174-140">N’importe quel hôte (A) ou les enregistrements AAAA pour un directeur ou un directeur (configuration facultative qu'avoir dans votre déploiement) du pool.</span><span class="sxs-lookup"><span data-stu-id="6e174-140">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="6e174-141">Une fois l'information vérifiée, cliquez avec le bouton droit de la souris sur votre nom de domaine SIP, puis sélectionnez **Nouvel alias (CNAME)** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="6e174-141">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="6e174-142">Dans la zone **Nom de l’alias**, saisissez le nom d’hôte correspondant à l’URL de service interne de découverte automatique : lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="6e174-142">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="6e174-143">Dans la **nom de domaine complet (nom de domaine complet pour l’hôte cible**, vous devez entrez ou recherchez le nom complet interne des Services Web pour votre Front End pool (ou serveur frontal unique, ou pool directeur ou directeur), identifié à l’étape 4 ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="6e174-143">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="6e174-144">Cliquez sur Entrée une fois le nom saisi.</span><span class="sxs-lookup"><span data-stu-id="6e174-144">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="6e174-145">Vous devez créer un nouvel enregistrement CNAME Autodiscover dans la zone de recherche directe pour chaque domaine SIP pris en charge dans votre Skype pour un environnement de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="6e174-145">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="6e174-146">Créer un enregistrement CNAME DNS externe</span><span class="sxs-lookup"><span data-stu-id="6e174-146">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="6e174-147">Ces étapes sont génériques, car nous ne pouvons pas déterminer quel fournisseur DNS public vous utilisez, mais elles pourront toujours vous être utiles. Connectez-vous à votre fournisseur DNS public avec un compte qui vous permettra de créer ici de nouveaux enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="6e174-147">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="6e174-148">À ce stade, un domaine SIP doit déjà exister il pour Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="6e174-148">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="6e174-149">Développez la **zone de recherche directe** pour ce domaine SIP, ou procédez à son ouverture.</span><span class="sxs-lookup"><span data-stu-id="6e174-149">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="6e174-150">Prenez un moment pour vérifiez lequel des enregistrements suivants vous avez :</span><span class="sxs-lookup"><span data-stu-id="6e174-150">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="6e174-151">N’importe quel A ou AAAA enregistrements d’hôte pour votre serveur frontal (Standard ou Enterprise) ou les pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="6e174-151">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="6e174-152">N’importe quel hôte (A) ou les enregistrements AAAA pour un directeur ou un directeur (configuration facultative qu'avoir dans votre déploiement) du pool.</span><span class="sxs-lookup"><span data-stu-id="6e174-152">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="6e174-153">Une fois que vous avez vérifié l'information, vous devriez pouvoir sélectionner une option pour créer un **Nouvel alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="6e174-153">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="6e174-154">Vous devriez maintenant pouvoir saisir un **Nom d'alias**. Saisissez ensuite lyncdiscover en tant qu'URL de service interne de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="6e174-154">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="6e174-155">Suivant doit être une zone d’entrer dans un **nom de domaine complet pour l’hôte de destination**, il doit être le nom de domaine complet pour votre Front End pool (ou serveur frontal unique, ou pool directeur ou directeur), identifié à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="6e174-155">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="6e174-156">Vous devrez peut-être enregistrer ici, ou si vous avez besoin créer des enregistrements CNAME supplémentaires dans la zone de recherche directe de chaque domaine SIP dans votre Skype pour un environnement Business Server, vous le faire, mais une fois que vous êtes prêt, enregistrez votre travail.</span><span class="sxs-lookup"><span data-stu-id="6e174-156">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="6e174-157">Créer un enregistrement A DNS interne</span><span class="sxs-lookup"><span data-stu-id="6e174-157">Create an internal DNS A record</span></span>

1. <span data-ttu-id="6e174-158">Ouvrez une session sur un serveur DNS de votre réseau qui est membre du groupe **Administrateurs du domaine** ou du groupe **DnsAdmins**.</span><span class="sxs-lookup"><span data-stu-id="6e174-158">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="6e174-159">Cliquez sur **Démarrer**, Sélectionnez **Outils d’administration ** (vous devrez peut-être **Rechercher ** l'option si elle n'existe pas dans le menu Démarrer), puis cliquez sur **DNS** pour ouvrir le composant logiciel enfichable d'administration DNS.</span><span class="sxs-lookup"><span data-stu-id="6e174-159">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="6e174-160">Dans le volet gauche de la fenêtre de console, vous devez accéder au domaine d’accueil à votre Skype pour les serveurs frontaux Business Server et développez **Zones de recherche directes** il.</span><span class="sxs-lookup"><span data-stu-id="6e174-160">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="6e174-161">Prenez un moment pour vérifiez lequel des enregistrements suivants vous avez :</span><span class="sxs-lookup"><span data-stu-id="6e174-161">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="6e174-162">N’importe quel A ou AAAA enregistrements d’hôte pour votre serveur frontal (Standard ou Enterprise) ou les pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="6e174-162">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="6e174-163">N’importe quel hôte (A) ou les enregistrements AAAA pour un directeur ou un directeur (configuration facultative qu'avoir dans votre déploiement) du pool.</span><span class="sxs-lookup"><span data-stu-id="6e174-163">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="6e174-164">Une fois l'information vérifiée, cliquez avec le bouton droit de la souris sur votre nom de domaine SIP, puis sélectionnez **Nouvel hôte (A ou AAAA)** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="6e174-164">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="6e174-165">Dans la zone **Nom**, saisissez le nom d’hôte correspondant à l’URL de service interne de découverte automatique : lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="6e174-165">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="6e174-166">Dans la zone de texte **Adresse IP** , tapez l’adresse IP des Services Web interne pour votre Front End pool (ou serveur frontal unique, ou pool directeur ou directeur), identifié à l’étape 4 ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="6e174-166">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="6e174-167">Une fois terminé, cliquez sur **Ajouter un hôte**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e174-167">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="6e174-168">Vous devez créer des enregistrements Autodiscover A ou AAAA de la zone de recherche directe pour chaque domaine SIP pris en charge dans votre Skype pour un environnement Business Server.</span><span class="sxs-lookup"><span data-stu-id="6e174-168">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="6e174-169">Pour ce faire, répétez les étapes 6 à 8 autant de fois que nécessaire.</span><span class="sxs-lookup"><span data-stu-id="6e174-169">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="6e174-170">Une fois l'opération terminée, cliquez sur **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="6e174-170">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="6e174-171">Créer un enregistrement A DNS externe</span><span class="sxs-lookup"><span data-stu-id="6e174-171">Create an external DNS A record</span></span>

1. <span data-ttu-id="6e174-172">Ces étapes sont génériques, car nous ne pouvons pas déterminer quel fournisseur DNS public vous utilisez, mais elles pourront toujours vous être utiles. Connectez-vous à votre fournisseur DNS public avec un compte qui vous permettra de créer ici de nouveaux enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="6e174-172">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="6e174-173">À ce stade, un domaine SIP doit déjà exister il pour Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="6e174-173">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="6e174-174">Développez la **zone de recherche directe** pour ce domaine SIP, ou procédez à son ouverture.</span><span class="sxs-lookup"><span data-stu-id="6e174-174">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="6e174-175">Prenez un moment pour vérifiez lequel des enregistrements suivants vous avez :</span><span class="sxs-lookup"><span data-stu-id="6e174-175">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="6e174-176">N’importe quel A ou AAAA enregistrements d’hôte pour votre serveur frontal (Standard ou Enterprise) ou les pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="6e174-176">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="6e174-177">N’importe quel hôte (A) ou les enregistrements AAAA pour un directeur ou un directeur (configuration facultative qu'avoir dans votre déploiement) du pool.</span><span class="sxs-lookup"><span data-stu-id="6e174-177">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="6e174-178">Une fois que vous avez vérifié l'information, vous devriez être capable de sélectionner une option pour créer un **Nouvel hôte A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="6e174-178">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="6e174-179">Vous devriez maintenant pouvoir saisir un **Nom**. Saisissez ensuite lyncdiscover en tant qu'URL de service interne de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="6e174-179">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="6e174-180">Ensuite, il doit y avoir une zone d’entrer dans une **Adresse IP**, cela doit être l’adresse IP de votre Front End pool (ou serveur frontal unique, ou pool directeur ou directeur), identifié à l’étape 3 ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="6e174-180">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="6e174-181">Vous devrez peut-être enregistrer ici, ou si vous devez créer d’autres A ou AAAA des enregistrements dans la zone de recherche directe de chaque domaine SIP pour votre Skype pour un environnement Business Server, vous devez le faire, mais lorsque vous êtes prêt, enregistrez votre travail.</span><span class="sxs-lookup"><span data-stu-id="6e174-181">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="6e174-182">Modifier les certificats</span><span class="sxs-lookup"><span data-stu-id="6e174-182">Modify certificates</span></span>
<span data-ttu-id="6e174-183"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="6e174-183"></span></span>

<span data-ttu-id="6e174-184">Si vous avez des questions sur la planification autour de certificats, nous avons qui documentée dans notre article de [planification pour la mobilité pour Skype pour Business Server](../plan-your-deployment/mobility.md) .</span><span class="sxs-lookup"><span data-stu-id="6e174-184">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="6e174-185">Une fois que vous avez vérifié que, nous allons vous aider aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6e174-185">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="6e174-186">Dois-je obtenir de nouveaux certificats ?</span><span class="sxs-lookup"><span data-stu-id="6e174-186">Do I need new certificates?</span></span>
    
- <span data-ttu-id="6e174-187">Demande de nouveaux certificats auprès de votre autorité de certification (CA).</span><span class="sxs-lookup"><span data-stu-id="6e174-187">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="6e174-188">Mise à jour sur site de certificats avec les remplacements à l'aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e174-188">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="6e174-189">Vérification des certificats à l’aide du composant logiciel enfichable Certificats dans Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="6e174-189">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="6e174-190">Dois-je obtenir de nouveaux certificats ?</span><span class="sxs-lookup"><span data-stu-id="6e174-190">Do I need new certificates?</span></span>

1. <span data-ttu-id="6e174-191">Vous devez d'abord vérifier quels certificats sont en place et s'ils disposent ou non des entrées dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="6e174-191">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="6e174-192">Pour cela, vous devez connecter votre Skype pour Business Server avec un compte qui est un administrateur local.</span><span class="sxs-lookup"><span data-stu-id="6e174-192">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="6e174-193">Ce compte doit également disposer des autorisations d'accès à l'autorité de certification (CA) émettrice pour effectuer certaines de ces étapes.</span><span class="sxs-lookup"><span data-stu-id="6e174-193">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="6e174-194">Ouvrez le Skype pour Business Server Management Shell (vous pouvez utiliser recherche trouver si vous ne l’avez pas épinglés à la barre de menu ou de la tâche Démarrer).</span><span class="sxs-lookup"><span data-stu-id="6e174-194">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="6e174-p110">Vous devrez absolument savoir quels certificats ont été affectés avant de pouvoir ajouter un certificat mis à jour. À partir de la ligne de commande, saisissez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="6e174-p110">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate. So at the command, type:</span></span>
    
   ```
   Get-CsCertificate
   ```

4. <span data-ttu-id="6e174-p111">Les informations fournies à partir de l'étape 3 vous seront spécifiques. Vous devez les vérifier afin de déterminer si vous disposez d'un certificat unique ayant été affecté à plusieurs éléments, ou si vous disposez d'un autre certificat affecté pour les différents composants qui en ont besoin. Le paramètre **Utiliser** vous permettra de savoir de quelle manière un certificat est utilisé et le paramètre **Thumbprint** vous permettra de savoir s'il s'agit du même certificat ou de plusieurs certificats.</span><span class="sxs-lookup"><span data-stu-id="6e174-p111">The information from Step 3 will be unique to you. You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them. The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="6e174-p112">Si vous disposez des entrées SAN recommandées dans votre section Planification, vous n'avez rien à faire. Sinon, vous devrez demander un nouveau certificat ou plusieurs certificats (en fonction de votre configuration) auprès de votre autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="6e174-p112">If you have the SAN entries recommended in our Planning section, you're good. If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="6e174-202">Demander un nouveau certificat ou de nouveaux certificats auprès de votre autorité de certification (CA)</span><span class="sxs-lookup"><span data-stu-id="6e174-202">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="6e174-203">Après avoir vérifié les entrées SAN dont vous disposez, vous savez que vous avez un **certificat unique** (la vérification ayant été effectuée en suivant la procédure décrite précédemment) et vous savez que vous ne disposez pas de toutes les entrées dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="6e174-203">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="6e174-204">Une nouvelle demande de certificat doit être effectuée auprès de votre autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="6e174-204">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="6e174-205">Ouvrez votre Skype pour Business Server PowerShell :</span><span class="sxs-lookup"><span data-stu-id="6e174-205">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="6e174-206">Pour un SAN de service de découverte automatique (en remplaçant le paramètre -Ca par votre propre chemin d'accès à l'autorité de certification) :</span><span class="sxs-lookup"><span data-stu-id="6e174-206">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="6e174-p114">Si vous avez plusieurs domaines SIP, vous ne pouvez pas utiliser le paramètre AllSipDomain comme dans l'exemple ci-dessus. Vous devrez plutôt utiliser le paramètre DomainName. De plus, lorsque vous utilisez le paramètre DomainName, vous devez définir le nom de domaine complet pour les enregistrements lyncdiscoverinternal et lyncdiscover. En voici un exemple (en remplaçant le paramètre -Ca par votre propre chemin d'accès à l'autorité de certification) :</span><span class="sxs-lookup"><span data-stu-id="6e174-p114">Now, if you have multiple SIP domains, you can't use the AllSipDomain paramater as in the example above. You'll need to use the DomainName parameter instead. And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records. An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="6e174-211">Ou, après avoir vérifié les entrées SAN dont vous disposez, vous savez que vous avez **plusieurs certificats** qui ne disposent pas de toutes les entrées dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="6e174-211">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="6e174-212">Une nouvelle demande de certificat doit être effectuée auprès de votre autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="6e174-212">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="6e174-213">Ouvrez votre Skype pour Business Server PowerShell :</span><span class="sxs-lookup"><span data-stu-id="6e174-213">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="6e174-214">Pour un SAN de service de découverte automatique (en remplaçant le paramètre -Ca par votre propre chemin d'accès à l'autorité de certification) :</span><span class="sxs-lookup"><span data-stu-id="6e174-214">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="6e174-p116">Si vous avez plusieurs domaines SIP, vous ne pouvez pas utiliser le paramètre AllSipDomain comme dans l'exemple ci-dessus. Vous devrez plutôt utiliser le paramètre DomainName. De plus, lorsque vous utilisez le paramètre DomainName, vous devez définir le nom de domaine complet pour les enregistrements lyncdiscoverinternal et lyncdiscover. En voici des exemples (en remplaçant le paramètre -Ca par votre propre chemin d'accès à l'autorité de certification) :</span><span class="sxs-lookup"><span data-stu-id="6e174-p116">Now, if you have multiple SIP domains, you can't use the AllSipDomain paramater as in the example above. You'll need to use the DomainName parameter instead. And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records. Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="6e174-219">Une fois que les nouveaux certificats ont été générés par votre autorité de certification, vous devrez les affecter.</span><span class="sxs-lookup"><span data-stu-id="6e174-219">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6e174-220">Affecter des certificats à l'aide de Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="6e174-220">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="6e174-221">En fonction de ce que vous avez trouvé dans la section Dois-je obtenir de nouveaux certificats ci-dessus, vous devrez effectuer l'**une ** des mesures suivantes.</span><span class="sxs-lookup"><span data-stu-id="6e174-221">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="6e174-222">Si vous disposez d'un certificat unique pour tout (les thumbprints sont identiques), vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="6e174-222">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="6e174-223">Si vous disposez de plusieurs certificats (les thumbprints sont tous différents), procédez plutôt comme suit :</span><span class="sxs-lookup"><span data-stu-id="6e174-223">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="6e174-224">Affichage des certificats dans la console MMC (Microsoft Management Console)</span><span class="sxs-lookup"><span data-stu-id="6e174-224">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="6e174-p117">Vous avez la possibilité de consulter vos certificats à l'aide du composant logiciel enfichable Certificats pour la console MMC. Saisissez simplement MMC dans la zone de recherche pour les faire apparaître en tant qu'option d'application</span><span class="sxs-lookup"><span data-stu-id="6e174-p117">You have an option to look at your certificates using the Certificates snap-in for the MMC. Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="6e174-p118">Pour ajouter le composant logiciel enfichable Certificats, cliquez sur **Fichier**, puis sur **Ajouter/Supprimer un composant logiciel enfichable...** (ou utilisez le raccourci clavier **Ctrl+M**). **Certificats** apparaîtra comme option dans le volet de gauche ; sélectionnez-la, puis choisissez **Compte d'ordinateur** dans la fenêtre contextuelle et cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="6e174-p118">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work). **Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="6e174-229">Vous effectuez probablement cette opération sur l'ordinateur qui héberge les certificats que vous souhaitez consulter, vous pouvez donc laisser la sélection, toujours dans la fenêtre contextuelle, sur **Ordinateur local**.</span><span class="sxs-lookup"><span data-stu-id="6e174-229">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="6e174-230">Si vous utilisez une machine distante, changez le bouton radio sur **Autre ordinateur**, puis entrez le nom de domaine complet de cet ordinateur ou utilisez le bouton **Naviguer** pour rechercher cet ordinateur via Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6e174-230">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="6e174-231">Après avoir sélectionné l’ordinateur, vous devez cliquez sur **Terminer** lorsque vous êtes prêt, puis sur **OK** pour ajouter le composant logiciel enfichable à la console MMC.</span><span class="sxs-lookup"><span data-stu-id="6e174-231">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="6e174-232">Développez la section **certificats** dans le volet gauche de la console MMC.</span><span class="sxs-lookup"><span data-stu-id="6e174-232">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="6e174-233">Développez également le dossier **Personnel**, puis sélectionnez **Certificats**.</span><span class="sxs-lookup"><span data-stu-id="6e174-233">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="6e174-234">Ceci vous permet de visualiser les certificats dans ce magasin.</span><span class="sxs-lookup"><span data-stu-id="6e174-234">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="6e174-235">Localisez le certificat que vous souhaitez visualiser, cliquez dessus avec le bouton de la souris et sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="6e174-235">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6e174-236">Comment savez-vous de quel certificat il s'agit ?</span><span class="sxs-lookup"><span data-stu-id="6e174-236">How do you know what certificate this is?</span></span> <span data-ttu-id="6e174-237">Il doit être soit le certificat unique assigné à tous les éléments de votre batterie de serveurs, ou avoir plusieurs certificats différents éléments, tels que la valeur par défaut, les Services Web internes, etc., auquel cas vous devrez peut-être consulter plusieurs certificats.</span><span class="sxs-lookup"><span data-stu-id="6e174-237">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="6e174-238">Plusieurs certificats auront le même thumbprint.</span><span class="sxs-lookup"><span data-stu-id="6e174-238">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="6e174-p122">Une fois l'affichage **Certificat** défini, sélectionnez **Détails**. Ceci vous permettra de visualiser le nom de l'objet du certificat lorsque vous sélectionnerez **Objet** et le nom de l'objet affecté ainsi que les propriétés associées s'afficheront.</span><span class="sxs-lookup"><span data-stu-id="6e174-p122">Once you've gotten to the **Certificate** view, choose **Details**. This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="6e174-p123">Vous devrez également vérifier les entrées **Autres noms du sujet **. Les éléments suivants peuvent apparaître :</span><span class="sxs-lookup"><span data-stu-id="6e174-p123">You'll also need to check the **Subject Alternate Name** entries. You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="6e174-243">Le nom du pool pour ce pool ou le nom de serveur unique, si ce n’est pas un pool.</span><span class="sxs-lookup"><span data-stu-id="6e174-243">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="6e174-244">Nom du serveur auquel le certificat est affecté.</span><span class="sxs-lookup"><span data-stu-id="6e174-244">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="6e174-245">Enregistrements d’URL simples, généralement meet et dialin.</span><span class="sxs-lookup"><span data-stu-id="6e174-245">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="6e174-246">Services Web internes et Services Web externes noms (par exemple, webpool01.contoso.net, webpool01.contoso.com), en fonction des choix effectués dans le Générateur de topologie et substituées sélections de Services Web.</span><span class="sxs-lookup"><span data-stu-id="6e174-246">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="6e174-247">Si déjà affecté, le lyncdiscover. \<sipdomain\> et lyncdiscoverinternal. \<sipdomain\> enregistrements.</span><span class="sxs-lookup"><span data-stu-id="6e174-247">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="6e174-248">Vous devrez vérifier les différents certificats dans le cas où plusieurs certificats ont été affectés (consultez la remarque ci-dessus).</span><span class="sxs-lookup"><span data-stu-id="6e174-248">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="6e174-249">Par conséquent, si vous recherchez lyncdiscover. \<sipdomain\> et lyncdiscoverinternal. \<sipdomain\> enregistrements, vous obtenez ce configuré déjà.</span><span class="sxs-lookup"><span data-stu-id="6e174-249">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="6e174-250">Vous pouvez fermer la console MMC.</span><span class="sxs-lookup"><span data-stu-id="6e174-250">You can close the MMC.</span></span>
    
9. <span data-ttu-id="6e174-251">S'ils ne sont pas affectés, vous devrez effectuer une nouvelle demande de certificat (telle que décrite ci-dessus) ou les installer une fois la demande effectuée (nous recommandons d'utiliser PowerShell à cet effet).</span><span class="sxs-lookup"><span data-stu-id="6e174-251">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="6e174-252">Configurer le proxy inverse</span><span class="sxs-lookup"><span data-stu-id="6e174-252">Configure the reverse proxy</span></span>
<span data-ttu-id="6e174-253"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="6e174-253"></span></span>

<span data-ttu-id="6e174-p125">Les étapes ci-dessous ne doivent pas nécessairement être suivies pas à pas. Dans les versions précédentes de ce produit, nous vous avons par exemple guidé tout au long de la procédure de configuration de Threat Management Gateway (TMG) et si vous ne l'utilisez pas, vous devrez élaborer votre propre procédure selon la version que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="6e174-p125">The steps below are not meant to be followed exactly. That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="6e174-256">TMG n’est plus offert par Microsoft en tant que produit, et si vous avez besoin de configurer, vous pouvez consulter les [étapes de Lync Server 2013](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="6e174-256">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="6e174-257">Mais les informations suivantes de destiné à être plus utile, même s’il n’existe aucun moyen que nous pouvons fournir une procédure spécifique pour chaque proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="6e174-257">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="6e174-258">Deux points essentiels doivent être pris en compte :</span><span class="sxs-lookup"><span data-stu-id="6e174-258">We have two main things to consider:</span></span>
  
- <span data-ttu-id="6e174-259">Allez-vous effectuer votre demande de découverte automatique initiale sur HTTPS (ce que nous recommandons) ?</span><span class="sxs-lookup"><span data-stu-id="6e174-259">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="6e174-260">Si vous avez une règle de publication web, vous devez la modifier.</span><span class="sxs-lookup"><span data-stu-id="6e174-260">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="6e174-261">Si vous n'avez pas de règle de publication web, vous devez la créer.</span><span class="sxs-lookup"><span data-stu-id="6e174-261">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="6e174-262">Si vous effectuez votre demande de découverte automatique initiale sur HTTPS, vous devrez également créer ou modifier cette règle.</span><span class="sxs-lookup"><span data-stu-id="6e174-262">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6e174-263">**Important** Une valeur de délai d’expiration du Proxy est un nombre qui varie d’un déploiement à.</span><span class="sxs-lookup"><span data-stu-id="6e174-263">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="6e174-264">Vous devez analyser votre déploiement et modifiez la valeur pour optimiser les performances pour les clients.</span><span class="sxs-lookup"><span data-stu-id="6e174-264">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="6e174-265">Vous ne pourrez pas définir la valeur aussi faible que 200.</span><span class="sxs-lookup"><span data-stu-id="6e174-265">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="6e174-266">Si vous prenez en charge les clients mobiles Lync dans votre environnement, vous devez définir la valeur à 960 permettant de délais d’attente de notification push d’Office 365, qui ont une valeur de délai d’expiration de 900.</span><span class="sxs-lookup"><span data-stu-id="6e174-266">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="6e174-267">Il est très probable que vous devrez augmenter la valeur de délai d’expiration pour éviter le client se déconnecte lors de la valeur est trop faible ou diminuer le nombre si les connexions via le proxy ne vous déconnectez pas, mais désactivez long une fois que le client est déconnecté.</span><span class="sxs-lookup"><span data-stu-id="6e174-267">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="6e174-268">Analyse et comparaison habituel pour votre environnement est la seule façon de déterminer le paramètre approprié pour cette valeur.</span><span class="sxs-lookup"><span data-stu-id="6e174-268">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="6e174-269">Modifiez la règle de publication web existante pour votre SAN et URL de découverte automatique externes.</span><span class="sxs-lookup"><span data-stu-id="6e174-269">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="6e174-270">Ouvrez votre interface de proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="6e174-270">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="6e174-271">Vous devez localiser votre règle de publication web, puis choisissez l’option Modifier (il peut se trouver sur un menu ou un onglet, selon votre configuration de proxy inverse).</span><span class="sxs-lookup"><span data-stu-id="6e174-271">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="6e174-272">Il doit être indiquant que cette règle de publication web qui est appliquée à une zone.</span><span class="sxs-lookup"><span data-stu-id="6e174-272">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="6e174-273">Vous devez modifier cette règle pour les sites entrants ou les demandes pour les sites.</span><span class="sxs-lookup"><span data-stu-id="6e174-273">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="6e174-274">Vous allez **ajouter** une nouvelle entrée.</span><span class="sxs-lookup"><span data-stu-id="6e174-274">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="6e174-275">Tapez le nom de votre site de découverte automatique (l’exemple, nous allons utiliser est lyncdiscover.contoso.com), puis cliquez sur **OK** ou sur **Enregistrer**, selon le format de votre serveur proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="6e174-275">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="6e174-276">Vous devez avoir un nouveau certificat contenant l'entrée SAN de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="6e174-276">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="6e174-277">Qui doit être installé et configurés pour être utilisés en fonction des paramètres de votre serveur proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="6e174-277">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="6e174-278">Assurez-vous de tout sauvegarder une fois la configuration terminée.</span><span class="sxs-lookup"><span data-stu-id="6e174-278">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="6e174-279">Si votre serveur proxy inverse a une fonctionnalité de **Test** , puis vérifiez utilisation, afin de tout fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="6e174-279">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="6e174-280">Maintenant, vous devrez peut-être Répétez ces étapes si vous disposez d’un directeur ou un directeur pool dans votre environnement (cela signifie que vous avez une deuxième règle).</span><span class="sxs-lookup"><span data-stu-id="6e174-280">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="6e174-281">Créer une règle de publication web pour l’URL de découverte automatique externe</span><span class="sxs-lookup"><span data-stu-id="6e174-281">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="6e174-282">Ouvrez votre interface de proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="6e174-282">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="6e174-283">Vous devez localiser où dans l’interface que vous créez vos règles de publication web, choisissez l’option **Nouveau** ou **créer** (il peut se trouver sur un menu ou un onglet, selon votre configuration de proxy inverse).</span><span class="sxs-lookup"><span data-stu-id="6e174-283">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="6e174-284">Vous recherchez l'option permettant de créer une nouvelle règle de publication web.</span><span class="sxs-lookup"><span data-stu-id="6e174-284">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="6e174-285">Vous devrez généralement saisir les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6e174-285">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="6e174-286">**Nom** : le nom de votre règle.</span><span class="sxs-lookup"><span data-stu-id="6e174-286">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="6e174-287">**Action de la règle**: dans ce cas, il est une règle **d’autorisation** , vous désinscrire quelque chose transitant par votre serveur proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="6e174-287">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="6e174-288">La règle ou l'option de **Publication** que vous choisissez doit être **un seul site web ou équilibrage de charge**.</span><span class="sxs-lookup"><span data-stu-id="6e174-288">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="6e174-289">Choisissez l'option **SSL** pour l'accès externe.</span><span class="sxs-lookup"><span data-stu-id="6e174-289">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="6e174-290">Vous aurez besoin publier un chemin d’accès pour la **Publication interne**, puis entrez le nom de domaine complet pour les Services Web externes d’équilibrage de charge de votre pool frontal (ou nom de domaine complet de l’équilibrage de charge du pool directeur si vous en avez un), un exemple serait sfb_ pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="6e174-290">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="6e174-291">Vous devez taper ** / ** comme le chemin d’accès à publier, mais vous devez également **transmettre l’en-tête d’hôte d’origine**.</span><span class="sxs-lookup"><span data-stu-id="6e174-291">You should type **/\*** as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="6e174-p131">Une option vous permettra de sélectionner les informations du **nom public ou externe**. À cet endroit, vous pourrez saisir les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6e174-p131">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="6e174-294">**Accepter les demandes**, mais pour le nom de domaine.</span><span class="sxs-lookup"><span data-stu-id="6e174-294">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="6e174-295">Pour le **Nom**, vous devez saisir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="6e174-295">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="6e174-296"><sipdomain>(c’est l’URL externe du Service de découverte automatique).</span><span class="sxs-lookup"><span data-stu-id="6e174-296"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="6e174-297">Maintenant, si vous créez une règle pour l’URL des Services Web externes sur le pool frontal, vous devez taper le nom de domaine complet pour les Services Web externes sur votre pool frontal (par exemple, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="6e174-297">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="6e174-298">Il y aura une option de **chemin d’accès** , et vous devrez saisir ** / ** ici.</span><span class="sxs-lookup"><span data-stu-id="6e174-298">There will be a **Path** option, and you'll need to enter **/\*** here.</span></span>
    
   - <span data-ttu-id="6e174-299">Vous devrez sélectionner un **Écouteur SSL** avec votre certificat public à jour.</span><span class="sxs-lookup"><span data-stu-id="6e174-299">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="6e174-300">**Délégation de l’authentification** doit être définie sur **Aucune délégation**, mais une authentification client directe **doit** être autorisée.</span><span class="sxs-lookup"><span data-stu-id="6e174-300">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="6e174-301">La règle doit être définie sur **Tous les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="6e174-301">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="6e174-302">Il s'agit de toutes les informations dont vous avez besoin pour créer cette règle et vous permettre de suivre la procédure.</span><span class="sxs-lookup"><span data-stu-id="6e174-302">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="6e174-303">Vous devez vous assurer que l'**en-tête de l’hôte d’origine** est transmis.</span><span class="sxs-lookup"><span data-stu-id="6e174-303">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="6e174-304">Les ports du **serveur web** devront également être définis ; procédez de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="6e174-304">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="6e174-305">**Rediriger les demandes au port HTTP**, avec le numéro de port **8080**.</span><span class="sxs-lookup"><span data-stu-id="6e174-305">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="6e174-306">**Rediriger les demandes au port SSL**, avec le numéro de port **4443**.</span><span class="sxs-lookup"><span data-stu-id="6e174-306">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="6e174-307">Une fois tous les éléments configurés, vous devrez enregistrer et appliquer les paramètres, puis tester la règle.</span><span class="sxs-lookup"><span data-stu-id="6e174-307">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="6e174-308">Créer une règle de publication web pour le port 80 (facultatif)</span><span class="sxs-lookup"><span data-stu-id="6e174-308">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="6e174-309">Ouvrez votre interface de proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="6e174-309">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="6e174-310">Vous devez localiser où dans l’interface que vous créez vos règles de publication web, choisissez l’option **Nouveau** ou **créer** (il peut se trouver sur un menu ou un onglet, selon votre configuration de proxy inverse).</span><span class="sxs-lookup"><span data-stu-id="6e174-310">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="6e174-311">Vous recherchez l'option permettant de créer une nouvelle règle de publication web.</span><span class="sxs-lookup"><span data-stu-id="6e174-311">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="6e174-312">Vous devrez généralement saisir les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6e174-312">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="6e174-313">**Nom** : le nom de votre règle.</span><span class="sxs-lookup"><span data-stu-id="6e174-313">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="6e174-314">**Action de la règle**: dans ce cas, il est une règle **d’autorisation** , vous désinscrire quelque chose transitant par votre serveur proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="6e174-314">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="6e174-315">La règle ou l'option de **Publication** que vous choisissez doit être **un seul site web ou équilibrage de charge**.</span><span class="sxs-lookup"><span data-stu-id="6e174-315">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="6e174-316">Une **connexion non sécurisée est nécessaire pour se connecter au serveur web publié ou à la batterie de serveurs**.</span><span class="sxs-lookup"><span data-stu-id="6e174-316">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="6e174-317">Vous aurez besoin publier un chemin d’accès pour la **Publication interne**, puis entrez le nom de domaine complet de l' **adresse IP virtuelle** du programme d’équilibrage de charge de votre pool frontal, un exemple serait sfb_pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="6e174-317">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="6e174-318">Vous devez taper ** / ** comme le chemin d’accès à publier, mais vous devez également **transmettre l’en-tête d’hôte d’origine**.</span><span class="sxs-lookup"><span data-stu-id="6e174-318">You should type **/\*** as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="6e174-p134">Une option vous permettra de sélectionner les informations du **nom public ou externe**. À cet endroit, vous pourrez saisir les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6e174-p134">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="6e174-321">**Accepter les demandes**, mais pour le nom de domaine.</span><span class="sxs-lookup"><span data-stu-id="6e174-321">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="6e174-322">Pour le **Nom**, vous devez saisir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="6e174-322">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="6e174-323"><sipdomain>(c’est l’URL externe du Service de découverte automatique).</span><span class="sxs-lookup"><span data-stu-id="6e174-323"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="6e174-324">Il y aura une option de **chemin d’accès** , et vous devrez saisir ** / ** ici.</span><span class="sxs-lookup"><span data-stu-id="6e174-324">There will be a **Path** option, and you'll need to enter **/\*** here.</span></span>
    
   - <span data-ttu-id="6e174-325">Vous devez sélectionner un port d’écoute web, ou autoriser votre proxy inverse créer une pour vous.</span><span class="sxs-lookup"><span data-stu-id="6e174-325">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="6e174-326">**Délégation de l’authentification** doit être définie sur **Aucune délégation**, mais une authentification client directe **ne doit pas** être autorisée.</span><span class="sxs-lookup"><span data-stu-id="6e174-326">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="6e174-327">La règle doit être définie sur **Tous les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="6e174-327">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="6e174-328">Il s'agit de toutes les informations dont vous avez besoin pour créer cette règle et vous permettre de suivre la procédure.</span><span class="sxs-lookup"><span data-stu-id="6e174-328">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="6e174-329">Les ports du **serveur web** devront être définis ; procédez de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="6e174-329">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="6e174-330">**Rediriger les demandes au port HTTP**, avec le numéro de port **8080**.</span><span class="sxs-lookup"><span data-stu-id="6e174-330">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="6e174-331">**Rediriger les demandes au port SSL**, avec le numéro de port **4443**.</span><span class="sxs-lookup"><span data-stu-id="6e174-331">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="6e174-332">Une fois tous les éléments configurés, vous devrez enregistrer et appliquer les paramètres, puis tester la règle.</span><span class="sxs-lookup"><span data-stu-id="6e174-332">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="6e174-333">Configurer la découverte automatique pour la mobilité avec les déploiements hybrides</span><span class="sxs-lookup"><span data-stu-id="6e174-333">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="6e174-334"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="6e174-334"></span></span>

<span data-ttu-id="6e174-335">Environnements hybrides dans Skype pour Business Server sont des environnements qui associent un locaux et environnement O365.</span><span class="sxs-lookup"><span data-stu-id="6e174-335">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="6e174-336">Lorsque vous avez Skype pour fonctionner dans un environnement hybride de Business Server, le service de découverte automatique doit être en mesure de localiser un utilisateur d’une de ces environnements.</span><span class="sxs-lookup"><span data-stu-id="6e174-336">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="6e174-p137">Pour permettre aux clients mobiles de découvrir où est localisé un utilisateur, le service de découverte automatique doit être configuré avec une nouvelle URL (uniform resource locator). Les étapes à suivre sont :</span><span class="sxs-lookup"><span data-stu-id="6e174-p137">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL). The steps are:</span></span>
  
1. <span data-ttu-id="6e174-339">Ouvrez Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6e174-339">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="6e174-340">Exécutez la procédure suivante pour obtenir la valeur de l’attribut **ProxyFQDN** pour votre Skype pour un environnement Business Server :</span><span class="sxs-lookup"><span data-stu-id="6e174-340">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
  ```
  Get-CsHostingProvider
  ```

3. <span data-ttu-id="6e174-341">Puis, toujours dans la fenêtre de shell, exécutez :</span><span class="sxs-lookup"><span data-stu-id="6e174-341">Then, still in the shell window, run:</span></span>
    
  ```
  Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
  ```

    <span data-ttu-id="6e174-342">Où [identity] est remplacé par le nom de domaine de l’espace d’adresses SIP partagé.</span><span class="sxs-lookup"><span data-stu-id="6e174-342">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="6e174-343">Tester votre déploiement de mobilité</span><span class="sxs-lookup"><span data-stu-id="6e174-343">Test your Mobility deployment</span></span>
<span data-ttu-id="6e174-344"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="6e174-344"></span></span>

<span data-ttu-id="6e174-345">Une fois que vous avez déployé Skype pour Service de mobilité Business Server et Skype pour le Service de découverte automatique Business Server, vous souhaiterez exécuter une transaction de test, vérifiez que travail de votre déploiement droite.</span><span class="sxs-lookup"><span data-stu-id="6e174-345">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="6e174-346">Vous pouvez exécuter **Test-CsUcwaConference** afin de tester la capacité de deux utilisateurs à créer et à rejoindre une conférence, ainsi qu'à y communiquer.</span><span class="sxs-lookup"><span data-stu-id="6e174-346">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="6e174-347">Il vous faudra deux utilisateurs (réels ou tests) et leurs informations d'identification complètes pour effectuer ce test.</span><span class="sxs-lookup"><span data-stu-id="6e174-347">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="6e174-348">Cette commande fonctionne pour les deux Skype pour les clients d’entreprise, ainsi que les clients Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6e174-348">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="6e174-349">Pour les clients Lync Server 2010 sur Skype pour Business Server 2015, vous devrez exécuter **Test-CsMcxP2PIM** pour tester.</span><span class="sxs-lookup"><span data-stu-id="6e174-349">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="6e174-350">Vos utilisateurs de Lync Server 2010 devra toujours être réels utilisateurs ou aux utilisateurs de test prédéfinies, et vous aurez besoin de leurs informations d’identification de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="6e174-350">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="6e174-351">Prise en charge MCX pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6e174-351">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="6e174-352">Vos utilisateurs devez mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="6e174-352">Your users will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="6e174-353">Conférence test pour clients mobiles Skype Entreprise et Lync 2013</span><span class="sxs-lookup"><span data-stu-id="6e174-353">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="6e174-354">Ouvrez une session en tant que membre du rôle **CsAdministrator** sur n’importe quel ordinateur où **Skype pour Business Server Management Shell** et **Ocscore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="6e174-354">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="6e174-355">Démarrez **Skype pour Business Server Management Shell** (vous pourrez taper le nom de la recherche ou accédez à **Tous les programmes** et choisissez).</span><span class="sxs-lookup"><span data-stu-id="6e174-355">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="6e174-356">Dans la ligne de commande, saisissez :</span><span class="sxs-lookup"><span data-stu-id="6e174-356">At the command line, enter:</span></span>
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="6e174-p141">Il est également possible de définir des informations d’identification dans un script et de les transmettre à l'applet de commande de test. Un exemple est fourni ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6e174-p141">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="6e174-359">Conférence test pour clients mobiles Lync 2010</span><span class="sxs-lookup"><span data-stu-id="6e174-359">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="6e174-360">Prise en charge MCX pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6e174-360">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="6e174-361">Vos utilisateurs devez mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="6e174-361">Your users will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="6e174-362">Ouvrez une session en tant que membre du rôle **CsAdministrator** sur n’importe quel ordinateur où **Skype pour Business Server Management Shell** et **Ocscore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="6e174-362">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="6e174-363">Démarrez **Skype pour Business Server Management Shell** (vous pourrez taper le nom de la recherche ou accédez à **Tous les programmes** et choisissez).</span><span class="sxs-lookup"><span data-stu-id="6e174-363">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="6e174-364">Dans la ligne de commande, saisissez :</span><span class="sxs-lookup"><span data-stu-id="6e174-364">At the command line, enter:</span></span>
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="6e174-p143">Il est également possible de définir des informations d’identification dans un script et de les transmettre à l'applet de commande de test. Un exemple est fourni ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6e174-p143">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
  ```
  $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
  $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
  $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
  $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
  Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
  ```

<span data-ttu-id="6e174-367">Pour passer en revue les procédures de commande, vous pouvez extraire [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) et [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6e174-367">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="6e174-368">Configurer les notifications push</span><span class="sxs-lookup"><span data-stu-id="6e174-368">Configure for push notifications</span></span>
<span data-ttu-id="6e174-369"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="6e174-369"></span></span>

<span data-ttu-id="6e174-370">Les notifications push, sous forme de badges, d’icônes ou d’alertes, peuvent être envoyées à un appareil mobile même lorsque l'application Skype ou Lync est inactive.</span><span class="sxs-lookup"><span data-stu-id="6e174-370">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="6e174-371">Mais, qu'est-ce que les notifications push ?</span><span class="sxs-lookup"><span data-stu-id="6e174-371">But what are pusn notifications?</span></span> <span data-ttu-id="6e174-372">Ce sont des alertes pour des événements, comme des invitations de messagerie instantanée nouvelles ou manquées, ou un message vocal reçu.</span><span class="sxs-lookup"><span data-stu-id="6e174-372">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="6e174-373">Le Skype pour le service de mobilité Server envoie ces notifications vers le nuage Skype pour Business Server Service de notifications Push, qui envoie ensuite les notifications à Microsoft Push Notification Service (MSNS) pour les utilisateurs de Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="6e174-373">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="6e174-374">Cette fonctionnalité est inchangée de Lync Server 2013, mais si vous avez un Skype pour Business Server, vous souhaiterez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6e174-374">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="6e174-375">Pour un Skype pour Business Server Edge Server, ajoutez un nouveau fournisseur d’hébergement, Microsoft Skype pour Business Online et puis configurer la fédération d’hébergement fournisseur entre votre organisation et de Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="6e174-375">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="6e174-p145">Activez les notifications push en exécutant l’applet de commande **Set-CsPushNotificationConfiguration**. Par défaut, les notifications push sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="6e174-p145">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet. By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="6e174-378">Testez votre configuration de fédération et les notifications push.</span><span class="sxs-lookup"><span data-stu-id="6e174-378">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="6e174-379">Configurer Skype Entreprise Edge Server pour les notifications push</span><span class="sxs-lookup"><span data-stu-id="6e174-379">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="6e174-380">Ouvrez une session, avec un compte qui est membre du rôle **CsAdministrator** , sur un ordinateur où **Skype pour Business Server Management Shell** et **Ocscore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="6e174-380">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="6e174-381">Démarrez le **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6e174-381">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6e174-382">Ajoutez un Skype pour le fournisseur d’hébergement en ligne Business Server.</span><span class="sxs-lookup"><span data-stu-id="6e174-382">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="6e174-383">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6e174-383">As an example:</span></span>
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="6e174-p146">Vous ne pouvez pas avoir plus d’une relation de fédération avec un même fournisseur d’hébergement. Par conséquent, si vous avez déjà configuré un fournisseur d’hébergement ayant une relation de fédération avec sipfed.online.lync.com, vous ne devez pas ajouter d’autre fournisseur d’hébergement, même si l’identité du fournisseur d’hébergement est différente de SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="6e174-p146">You can't have more than one federation relationship with a single hosting provider. So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="6e174-386">Configurer la fédération de fournisseur d’hébergement entre votre organisation et le Service de Notification Push à Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="6e174-386">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="6e174-387">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="6e174-387">At the command line, you'll need to type:</span></span>
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="6e174-388">Activer les notifications push</span><span class="sxs-lookup"><span data-stu-id="6e174-388">Enable push notifications</span></span>

1. <span data-ttu-id="6e174-389">Ouvrez une session, avec un compte qui est membre du rôle **CsAdministrator** , sur un ordinateur où **Skype pour Business Server Management Shell** et **Ocscore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="6e174-389">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="6e174-390">Démarrez le **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6e174-390">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6e174-391">Activer les notifications push :</span><span class="sxs-lookup"><span data-stu-id="6e174-391">Enable push notifications:</span></span>
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="6e174-392">Activer la fédération :</span><span class="sxs-lookup"><span data-stu-id="6e174-392">Enable Federation:</span></span>
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="6e174-393">Tester la fédération et les notifications push</span><span class="sxs-lookup"><span data-stu-id="6e174-393">Test federation and push notifications</span></span>

1. <span data-ttu-id="6e174-394">Ouvrez une session, avec un compte qui est membre du rôle **CsAdministrator** , sur un ordinateur où **Skype pour Business Server Management Shell** et **Ocscore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="6e174-394">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="6e174-395">Démarrez le **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6e174-395">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6e174-396">Testez la configuration de la fédération :</span><span class="sxs-lookup"><span data-stu-id="6e174-396">Test the federation configuration:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="6e174-397">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6e174-397">As an example:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="6e174-398">Testez vos notifications push</span><span class="sxs-lookup"><span data-stu-id="6e174-398">Test your push notifications:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="6e174-399">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6e174-399">As an example:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="6e174-400">Configurer la stratégie de mobilité</span><span class="sxs-lookup"><span data-stu-id="6e174-400">Configure Mobility policy</span></span>
<span data-ttu-id="6e174-401"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="6e174-401"></span></span>

<span data-ttu-id="6e174-402">Vous avez la possibilité avec Skype pour Business Server afin de déterminer qui peut utiliser votre service de mobilité, appel via le bureau, voix sur IP (VoIP), ou la vidéo, ainsi que si Wi-Fi sera nécessaire pour VoIP ou vidéo.</span><span class="sxs-lookup"><span data-stu-id="6e174-402">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="6e174-403">La fonctionnalité d'Appel via le Bureau permet à un utilisateur mobile d'utiliser son numéro de téléphone professionnel, plutôt que son numéro de téléphone mobile, pour passer et recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="6e174-403">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="6e174-404">La personne à l'autre bout de la ligne ne verra pas le numéro de téléphone mobile de cet utilisateur, et cet utilisateur mobile n'aura pas à payer de frais d'appels sortants.</span><span class="sxs-lookup"><span data-stu-id="6e174-404">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="6e174-405">Lorsque VoIP et la vidéo sont configurés, les utilisateurs peuvent prendre et effectuer des appels VoIP et vidéo.</span><span class="sxs-lookup"><span data-stu-id="6e174-405">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="6e174-406">Les paramètres d'utilisation de la fonctionnalité WiFi permettent de déterminer si l'appareil mobile d'un utilisateur sera requis pour utiliser un réseau WiFi sur un réseau de données cellulaires.</span><span class="sxs-lookup"><span data-stu-id="6e174-406">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="6e174-407">Mobilité, appel via le bureau et la VoIP et les fonctionnalités vidéo sont toutes activées par défaut.</span><span class="sxs-lookup"><span data-stu-id="6e174-407">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="6e174-408">Les paramètres pour exiger WiFi pour VoIP et pour la vidéo sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="6e174-408">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="6e174-409">Un administrateur a la capacité de modifier ces paramètres, soit de manière globale, soit par site ou par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6e174-409">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="6e174-410">Pour être en mesure d’utiliser les fonctionnalités de mobilité et d’appel via le bureau, les utilisateurs doivent être :</span><span class="sxs-lookup"><span data-stu-id="6e174-410">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="6e174-411">Activé pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="6e174-411">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="6e174-412">Activés pour Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="6e174-412">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="6e174-413">Attribué une stratégie de mobilité dont l’option **EnableMobility** a la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="6e174-413">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="6e174-414">Pour pouvoir utiliser la fonctionnalité d'Appel via le Bureau, les utilisateurs doivent également être :</span><span class="sxs-lookup"><span data-stu-id="6e174-414">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="6e174-415">Affectés à une stratégie de voix dont l’option **Activer la sonnerie simultanée de téléphones ** est activée.</span><span class="sxs-lookup"><span data-stu-id="6e174-415">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="6e174-416">Attribué une stratégie de mobilité dont l' **EnableOutsideVoice** a la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="6e174-416">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6e174-p150">Les utilisateurs non activés pour Voix Entreprise peuvent utiliser leur appareil mobile pour effectuer des appels de Skype à Skype VoIP ou peuvent participer à des conférences via le lien Clic pour participer sur leur appareil mobile, si les options adéquates sont configurées pour la stratégie de voix à laquelle ils sont associés. Vous trouverez plus de détails dans la rubrique Planification.</span><span class="sxs-lookup"><span data-stu-id="6e174-p150">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with. There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="6e174-419">Modifier la stratégie de mobilité globale</span><span class="sxs-lookup"><span data-stu-id="6e174-419">Modify global Mobility policy</span></span>

1. <span data-ttu-id="6e174-420">Ouvrez une session, avec un compte qui est membre du rôle **CsAdministrator** , sur un ordinateur où **Skype pour Business Server Management Shell** et **Ocscore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="6e174-420">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="6e174-421">Démarrez le **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6e174-421">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6e174-422">Désactiver l’accès à la mobilité et l’appel via le bureau global en tapant :</span><span class="sxs-lookup"><span data-stu-id="6e174-422">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="6e174-423">Vous pouvez désactiver l’appel via le bureau sans désactiver l’accès à la mobilité.</span><span class="sxs-lookup"><span data-stu-id="6e174-423">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="6e174-424">Mais vous ne pouvez pas désactiver la mobilité sans également désactiver appel via le bureau.</span><span class="sxs-lookup"><span data-stu-id="6e174-424">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="6e174-425">Pour plus d’informations, consultez la rubrique [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6e174-425">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="6e174-426">Modifier la stratégie de mobilité par site</span><span class="sxs-lookup"><span data-stu-id="6e174-426">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="6e174-427">Ouvrez une session, avec un compte qui est membre du rôle **CsAdministrator** , sur un ordinateur où **Skype pour Business Server Management Shell** et **Ocscore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="6e174-427">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="6e174-428">Démarrez le **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6e174-428">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6e174-p152">Vous pouvez créer une stratégie au niveau du site, désactiver les fonctionnalités VoIP et vidéo et activer l'option Exiger WiFi pour l'audio IP et Exiger WiFi pour la vidéo IP par site.</span><span class="sxs-lookup"><span data-stu-id="6e174-p152">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site. Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="6e174-431">En savoir plus sur [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6e174-431">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="6e174-432">Modifier la stratégie de mobilité par utilisateur</span><span class="sxs-lookup"><span data-stu-id="6e174-432">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="6e174-433">Ouvrez une session, avec un compte qui est membre du rôle **CsAdministrator** , sur un ordinateur où **Skype pour Business Server Management Shell** et **Ocscore** sont installés.</span><span class="sxs-lookup"><span data-stu-id="6e174-433">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="6e174-434">Démarrez le **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6e174-434">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6e174-435">Créer des stratégies de mobilité au niveau utilisateur et de désactiver la mobilité et l’appel via le bureau par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6e174-435">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="6e174-436">Tapez :</span><span class="sxs-lookup"><span data-stu-id="6e174-436">Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="6e174-437">Autre exemple avec échantillons de données :</span><span class="sxs-lookup"><span data-stu-id="6e174-437">A further example with sample data:</span></span>
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="6e174-438">Vous pouvez désactiver l’appel via le bureau sans désactiver l’accès à la mobilité.</span><span class="sxs-lookup"><span data-stu-id="6e174-438">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="6e174-439">Mais vous ne pouvez pas désactiver la mobilité sans également désactiver appel via le bureau.</span><span class="sxs-lookup"><span data-stu-id="6e174-439">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

