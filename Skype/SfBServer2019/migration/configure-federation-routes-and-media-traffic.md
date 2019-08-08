---
title: Configuration des itinéraires de fédération et du trafic multimédia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: La Fédération est une relation d’approbation entre au moins deux domaines SIP, qui permet aux utilisateurs d’organisations distinctes de communiquer au sein des frontières du réseau. Après avoir effectué une migration vers votre pool de pilotes, vous devez effectuer une transition de l’itinéraire de Fédération de vos serveurs de périphérie de version précédente vers l’itinéraire de Fédération de vos serveurs Edge 2019 Skype entreprise Server.
ms.openlocfilehash: 50c10a4dced237e59c8dad12b5bdee1ef7d970fe
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239361"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="b75c3-104">Configuration des itinéraires de fédération et du trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="b75c3-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="b75c3-105">La Fédération est une relation d’approbation entre au moins deux domaines SIP, qui permet aux utilisateurs d’organisations distinctes de communiquer au sein des frontières du réseau.</span><span class="sxs-lookup"><span data-stu-id="b75c3-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="b75c3-106">Après avoir effectué une migration vers votre pool de pilotes, vous devez passer de l’itinéraire de Fédération des serveurs Edge de votre version précédente à l’itinéraire de Fédération de vos serveurs de périmètre Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b75c3-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="b75c3-107">Pour effectuer un déploiement sur un site, procédez comme suit pour basculer entre l’itinéraire de la Fédération et l’itinéraire du trafic multimédia du serveur Edge et du 2019 directeur de votre version précédente.</span><span class="sxs-lookup"><span data-stu-id="b75c3-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b75c3-108">La modification de l’itinéraire de Fédération et du trafic multimédia nécessite que vous planifiiez des arrêts de maintenance pour le serveur Skype entreprise Server 2019 et la version latérale antérieure.</span><span class="sxs-lookup"><span data-stu-id="b75c3-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="b75c3-109">Ce processus de transition complet signifie également que l’accès fédéré ne sera pas disponible pendant la durée de la période d’interruption.</span><span class="sxs-lookup"><span data-stu-id="b75c3-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="b75c3-110">Nous vous conseillons de planifier le temps d’arrêt à un moment où vous vous attendez à un minimum d’activités utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b75c3-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="b75c3-111">Vous devez également fournir une notification suffisante à vos utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="b75c3-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="b75c3-112">Planifiez en conséquence pour cette interruption et définissez les attentes appropriées au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b75c3-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b75c3-113">Si votre serveur de bord antérieur est configuré pour utiliser le même nom de domaine complet pour le service Edge d’accès, le service Edge de conférence Web et le service Edge A/V, les procédures de cette section ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="b75c3-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="b75c3-114">Si les services Edge hérités sont configurés pour utiliser le même nom de domaine complet (FQDN), vous devez tout d’abord migrer tous vos utilisateurs, puis désactivez le serveur Edge versions antérieur avant d’activer la Fédération sur le serveur Edge 2019 Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b75c3-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b75c3-115">Si votre Fédération XMPP est routée par le biais d’un serveur Edge Skype entreprise Server 2019, les utilisateurs de la version précédente ne seront pas en mesure de communiquer avec le partenaire fédéré de XMPP tant que tous les utilisateurs n’ont pas été déplacés vers Skype entreprise Server 2019 et les stratégies XMPP et des certificats ont été configurés, le partenaire fédéré de XMPP a été configuré sur Skype entreprise Server 2019 et, enfin, les entrées DNS ont été mises à jour.</span><span class="sxs-lookup"><span data-stu-id="b75c3-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="b75c3-116">Pour supprimer l’Association de Fédération héritée des sites 2019 de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b75c3-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="b75c3-117">Sur le serveur frontal Skype entreprise Server 2019, ouvrez la topologie existante dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="b75c3-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="b75c3-118">Dans le volet gauche, accédez au nœud de site qui se trouve juste en dessous de **Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="b75c3-119">Cliquez avec le bouton droit sur le site, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="b75c3-120">Dans le volet gauche, sélectionnez **gamme de Fédération**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="b75c3-121">Sous **affectation**de l’itinéraire de Fédération de site, décochez la case **activer la Fédération SIP** pour désactiver le routage de Fédération par le biais de l’environnement hérité.</span><span class="sxs-lookup"><span data-stu-id="b75c3-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="b75c3-122">Cliquez sur **OK** pour fermer la page modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="b75c3-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="b75c3-123">Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="b75c3-124">Dans le menu **action** , cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="b75c3-125">Cliquez sur **suivant** pour finaliser le processus de publication, puis cliquez sur **Terminer** lorsque le processus de publication est terminé.</span><span class="sxs-lookup"><span data-stu-id="b75c3-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="b75c3-126">Pour configurer le serveur de périphérie traditionnel en tant que serveur Edge non fédéré</span><span class="sxs-lookup"><span data-stu-id="b75c3-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="b75c3-127">Dans le volet gauche, accédez au nœud d’installation hérité, puis au nœud de pools de **périphérie** .</span><span class="sxs-lookup"><span data-stu-id="b75c3-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="b75c3-128">Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="b75c3-129">Dans le volet gauche, sélectionnez **général** .</span><span class="sxs-lookup"><span data-stu-id="b75c3-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="b75c3-130">Décochez la case **activer la Fédération pour ce pool Edge (port 5061)** et sélectionnez **OK** pour fermer la page.</span><span class="sxs-lookup"><span data-stu-id="b75c3-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="b75c3-131">Dans le menu **action** , cliquez sur **publier la topologie**, puis sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="b75c3-132">Lorsque l' **Assistant Publication** est terminé, cliquez sur **Terminer** pour fermer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="b75c3-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="b75c3-133">Vérifiez que la Fédération du serveur Edge héritée est désactivée dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="b75c3-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="b75c3-134">Pour configurer des certificats sur le serveur Edge hérité</span><span class="sxs-lookup"><span data-stu-id="b75c3-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="b75c3-135">Exportez le certificat de proxy d’accès externe, avec la clé privée, à partir du serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="b75c3-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="b75c3-136">Sur le serveur Edge 2019 de Skype entreprise Server, puis importez le certificat externe de proxy d’accès à partir de l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="b75c3-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="b75c3-137">Affectez le certificat externe du proxy d’accès à l’interface externe de Skype entreprise Server 2019 du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b75c3-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="b75c3-138">Le certificat d’interface interne du serveur Edge 2019 de Skype entreprise Server doit être demandé auprès d’une autorité de certification approuvée et attribué.</span><span class="sxs-lookup"><span data-stu-id="b75c3-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="b75c3-139">Pour modifier l’itinéraire de Fédération de la version précédente pour utiliser Skype entreprise Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="b75c3-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="b75c3-140">Dans le générateur de topologie, dans le volet gauche, accédez au nœud **Skype entreprise Server 2019** , puis au nœud Pools de **périphérie** .</span><span class="sxs-lookup"><span data-stu-id="b75c3-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="b75c3-141">Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="b75c3-142">Dans le volet gauche, sélectionnez **général** .</span><span class="sxs-lookup"><span data-stu-id="b75c3-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="b75c3-143">Activez la case à cocher **activer la Fédération pour ce pool Edge (port 5061)**, puis cliquez sur **OK** pour fermer la page.</span><span class="sxs-lookup"><span data-stu-id="b75c3-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="b75c3-144">Dans le menu **action** , cliquez sur **publier la topologie**, puis sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="b75c3-145">Lorsque l' **Assistant Publication** est terminé, cliquez sur **Terminer** pour fermer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="b75c3-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="b75c3-146">Vérifiez que la **Fédération (port 5061)** est définie sur **activée** dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="b75c3-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="b75c3-147">Pour mettre à jour Skype entreprise Server 2019 Edge Server Federation Next tronçon</span><span class="sxs-lookup"><span data-stu-id="b75c3-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="b75c3-148">Dans le générateur de topologie, dans le volet gauche, accédez au nœud **Skype entreprise Server 2019** , puis au nœud Pools de **périphérie** .</span><span class="sxs-lookup"><span data-stu-id="b75c3-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="b75c3-149">Développez le nœud, cliquez avec le bouton droit sur le serveur Edge indiqué, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="b75c3-150">Dans la page **général** , sous **sélection du tronçon suivant**, sélectionnez dans la liste déroulante le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b75c3-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="b75c3-151">Cliquez sur **OK** pour fermer la page modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="b75c3-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="b75c3-152">Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="b75c3-153">Dans le menu **action** , cliquez sur **publier la topologie** et terminer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="b75c3-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="b75c3-154">Pour configurer le chemin multimédia sortant du serveur Microsoft Skype entreprise Server 2019 Edge</span><span class="sxs-lookup"><span data-stu-id="b75c3-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="b75c3-155">Dans le concepteur de topologies, dans le volet gauche, accédez au nœud **Skype entreprise Server 2019** , puis au pool sous **Standard Edition serveurs front end** ou **Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="b75c3-156">Cliquez avec le bouton droit sur la liste, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="b75c3-157">Dans la section **associations** , activez la case à cocher **associer le pool Edge (pour les composants multimédias)** .</span><span class="sxs-lookup"><span data-stu-id="b75c3-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="b75c3-158">Dans la liste déroulante, sélectionnez le serveur Edge 2019 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b75c3-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="b75c3-159">Cliquez sur **OK** pour fermer la page **modifier les propriétés** .</span><span class="sxs-lookup"><span data-stu-id="b75c3-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="b75c3-160">Pour activer Skype entreprise Server 2019 Edge Server Federation</span><span class="sxs-lookup"><span data-stu-id="b75c3-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="b75c3-161">Dans le générateur de topologie, dans le volet gauche, accédez au nœud **Skype entreprise Server 2019** , puis au nœud Pools de **périphérie** .</span><span class="sxs-lookup"><span data-stu-id="b75c3-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="b75c3-162">Développez le nœud, cliquez avec le bouton droit sur le serveur Edge indiqué, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b75c3-163">La Fédération ne peut être activée que pour un seul pool de bords.</span><span class="sxs-lookup"><span data-stu-id="b75c3-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="b75c3-164">Si vous avez plusieurs pools de bords, sélectionnez-en un pour les utiliser comme pools de frontière de Fédération.</span><span class="sxs-lookup"><span data-stu-id="b75c3-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="b75c3-165">Dans la page **général** , vérifiez que la case à cocher **activer la Fédération pour ce pool Edge (port 5061)** est activée.</span><span class="sxs-lookup"><span data-stu-id="b75c3-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="b75c3-166">Cliquez sur **OK** pour fermer la page modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="b75c3-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="b75c3-167">Accédez au nœud site.</span><span class="sxs-lookup"><span data-stu-id="b75c3-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="b75c3-168">Cliquez avec le bouton droit sur le site, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="b75c3-169">Dans le volet de gauche, cliquez sur **route de Fédération**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="b75c3-170">Sous **affectation**de l’itinéraire de la Fédération de sites, sélectionnez **activer la Fédération SIP**, puis dans la liste, sélectionnez le serveur Edge 2019 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b75c3-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="b75c3-171">Cliquez sur **OK** pour fermer la page **modifier les propriétés** .</span><span class="sxs-lookup"><span data-stu-id="b75c3-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="b75c3-172">Pour les déploiements multisites, procédez comme suit sur chaque site.</span><span class="sxs-lookup"><span data-stu-id="b75c3-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="b75c3-173">Pour publier les modifications de configuration de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b75c3-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="b75c3-174">Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="b75c3-175">Dans le menu **action** , sélectionnez **publier la topologie** et terminer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="b75c3-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="b75c3-176">Attendez la fin de la réplication Active Directory pour tous les pools du déploiement.</span><span class="sxs-lookup"><span data-stu-id="b75c3-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b75c3-177">Le message suivant risque de s’afficher: **Avertissement: la topologie comporte plusieurs serveurs Edge fédérés. Cela peut se produire lors de la migration vers une version plus récente du produit. Dans ce cas, un seul serveur Edge serait utilisé activement pour la Fédération. Vérifiez que l’enregistrement SRV DNS externe pointe vers le serveur Edge approprié. Si vous voulez déployer plusieurs serveurs de frontière de Fédération de manière à être actifs en même temps (il ne s’agit pas d’un scénario de migration), vérifiez que tous les partenaires fédérés utilisent Skype entreprise Server. Vérifiez que l’enregistrement SRV DNS externe recense tous les serveurs Edge compatibles avec la Fédération.**</span><span class="sxs-lookup"><span data-stu-id="b75c3-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="b75c3-178">Cet avertissement est attendu et peut être ignoré en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="b75c3-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="b75c3-179">Pour configurer Skype entreprise Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="b75c3-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="b75c3-180">Accédez à tous les serveurs Edge Skype entreprise Server 2019 en ligne.</span><span class="sxs-lookup"><span data-stu-id="b75c3-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="b75c3-181">Mettez à jour les règles de routage de pare-feu externe ou les paramètres de l’équilibrage de charge matérielle pour envoyer le trafic SIP pour l’accès externe (généralement le port 443) et la Fédération (généralement port 5061) vers le serveur Edge Skype entreprise Server 2019, au lieu du serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="b75c3-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b75c3-182">Si vous n’avez pas d’équilibrage de charge matérielle, vous devez mettre à jour l’enregistrement DNS A pour la Fédération pour résoudre le nouveau serveur de périphérie de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b75c3-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="b75c3-183">Pour effectuer cette opération avec un minimum de perturbation, réduisez la valeur TLL du nom de domaine complet (FQDN) du périmètre du serveur Skype entreprise externe, de sorte que lorsque DNS est mis à jour de manière à ce qu’il pointe vers le nouveau serveur Skype entreprise Server Access, la Fédération et l’accès à distance seront mis à jour rapidement.</span><span class="sxs-lookup"><span data-stu-id="b75c3-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="b75c3-184">Arrêtez l' **accès à Skype entreprise Server** depuis chaque ordinateur du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b75c3-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="b75c3-185">À partir de chaque ordinateur serveur Edge hérité, ouvrez l’application **services** à partir des **Outils d’administration**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="b75c3-186">Dans la liste services, recherchez **Edge Access pour Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="b75c3-187">Cliquez avec le bouton droit sur le nom des services, puis sélectionnez **arrêter** pour arrêter le service.</span><span class="sxs-lookup"><span data-stu-id="b75c3-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="b75c3-188">Définissez le type de démarrage sur **désactivé**.</span><span class="sxs-lookup"><span data-stu-id="b75c3-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="b75c3-189">Cliquez sur **OK** pour fermer la fenêtre **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="b75c3-189">Click **OK** to close the **Properties** window.</span></span> 
    

