---
title: Configurer les itinéraires de fédération et le trafic multimédia
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La fédération est une relation d’approbation entre deux ou plusieurs domaines SIP qui permet aux utilisateurs d’organisations distinctes de communiquer au-delà des limites des réseaux. Une fois que vous avez effectué la migration vers votre pool pilote, vous devez effectuer une transition de l’itinéraire de Fédération de vos serveurs Edge de versions précédentes vers l’itinéraire de Fédération de vos serveurs Edge Skype entreprise Server 2019.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754034"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="69b5b-104">Configurer les itinéraires de fédération et le trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="69b5b-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="69b5b-105">La fédération est une relation d’approbation entre deux ou plusieurs domaines SIP qui permet aux utilisateurs d’organisations distinctes de communiquer au-delà des limites des réseaux.</span><span class="sxs-lookup"><span data-stu-id="69b5b-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="69b5b-106">Une fois que vous avez effectué la migration vers votre pool pilote, vous devez passer de l’itinéraire de Fédération de vos serveurs Edge de la version précédente à l’itinéraire de Fédération de vos serveurs Edge Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="69b5b-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="69b5b-107">Utilisez les procédures suivantes pour effectuer la transition de l’itinéraire de Fédération et de l’itinéraire de trafic multimédia depuis le serveur Edge et le directeur de votre version précédente vers votre serveur Edge Skype entreprise Server 2019, pour un déploiement sur un seul site.</span><span class="sxs-lookup"><span data-stu-id="69b5b-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="69b5b-108">Le changement de l’itinéraire de Fédération et de l’itinéraire de trafic multimédia nécessite de planifier le temps d’arrêt de la maintenance pour les serveurs Edge Skype entreprise Server 2019 et version précédente.</span><span class="sxs-lookup"><span data-stu-id="69b5b-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="69b5b-109">Ce processus de transition signifie également que l’accès fédéré sera indisponible pendant la durée de l’interruption.</span><span class="sxs-lookup"><span data-stu-id="69b5b-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="69b5b-110">Vous devez donc planifier cette interruption à un moment où l’activité des utilisateurs sera minimale.</span><span class="sxs-lookup"><span data-stu-id="69b5b-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="69b5b-111">Prévoyez aussi d’en informer les utilisateurs finaux suffisamment à l’avance.</span><span class="sxs-lookup"><span data-stu-id="69b5b-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="69b5b-112">Anticipez cette interruption à tous les niveaux et informez-en votre organisation afin qu’elle s’y prépare en conséquence.</span><span class="sxs-lookup"><span data-stu-id="69b5b-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="69b5b-113">Si votre serveur Edge hérité est configuré pour utiliser le même nom de domaine complet pour le service Edge d’accès, le service Edge de conférence Web et le service Edge A/V, les procédures décrites dans cette section ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="69b5b-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="69b5b-114">Si les services Edge hérités sont configurés pour utiliser le même nom de domaine complet, vous devez d’abord migrer tous vos utilisateurs, puis désactivez le serveur Edge des versions précédentes avant d’activer la Fédération sur le serveur Edge de Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="69b5b-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="69b5b-115">Si votre Fédération XMPP est acheminée via un serveur Edge Skype entreprise Server 2019, les utilisateurs de la version précédente ne seront pas en mesure de communiquer avec le partenaire fédéré XMPP tant que tous les utilisateurs n’ont pas été déplacés vers Skype entreprise Server 2019, que les stratégies XMPP et les certificats ont été configurés, le partenaire fédéré XMPP a été configuré sur Skype entreprise Server 2019 et, enfin, les entrées DNS ont été mises à jour.</span><span class="sxs-lookup"><span data-stu-id="69b5b-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="69b5b-116">Pour supprimer l’Association de Fédération héritée des sites Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="69b5b-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="69b5b-117">Sur le serveur frontal Skype entreprise Server 2019, ouvrez la topologie existante dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="69b5b-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="69b5b-118">Dans le volet de gauche, accédez au nœud de site, qui se trouve directement sous **Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="69b5b-119">Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="69b5b-120">Dans le volet gauche, sélectionnez **Itinéraire de fédération**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="69b5b-121">Sous **attribution**de l’itinéraire de Fédération du site, désactivez la case à cocher **activer la Fédération SIP** pour désactiver l’itinéraire de Fédération dans l’environnement hérité.</span><span class="sxs-lookup"><span data-stu-id="69b5b-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="69b5b-122">Cliquez sur **OK** pour fermer la page Modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="69b5b-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="69b5b-123">Dans le **Générateur de topologies**, sélectionnez le nœud supérieur **Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="69b5b-124">Dans le menu **Action**, cliquez sur **Publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="69b5b-125">Cliquez sur **suivant** pour terminer le processus de publication, puis cliquez sur **Terminer** lorsque le processus de publication est terminé.</span><span class="sxs-lookup"><span data-stu-id="69b5b-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="69b5b-126">Pour configurer le serveur Edge hérité en tant que serveur Edge non-fédérant</span><span class="sxs-lookup"><span data-stu-id="69b5b-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="69b5b-127">Dans le volet gauche, accédez au nœud installation héritée, puis au nœud **pool** de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="69b5b-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="69b5b-128">Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="69b5b-129">Sélectionnez **Général** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="69b5b-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="69b5b-130">Désactivez la case à cocher **activer la Fédération pour ce pool Edge (port 5061)** et sélectionnez **OK** pour fermer la page.</span><span class="sxs-lookup"><span data-stu-id="69b5b-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="69b5b-131">Dans le menu **Action**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="69b5b-132">Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.</span><span class="sxs-lookup"><span data-stu-id="69b5b-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="69b5b-133">Vérifiez que la Fédération pour le serveur Edge hérité est désactivée dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="69b5b-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="69b5b-134">Pour configurer des certificats sur le serveur Edge hérité</span><span class="sxs-lookup"><span data-stu-id="69b5b-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="69b5b-135">Exportez le certificat de proxy d’accès externe, avec la clé privée, à partir du serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="69b5b-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="69b5b-136">Sur le serveur Edge de Skype entreprise Server 2019, puis importez le certificat externe de proxy d’accès à partir de l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="69b5b-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="69b5b-137">Affectez le certificat externe de proxy d’accès à l’interface externe Skype entreprise Server 2019 du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="69b5b-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="69b5b-138">Le certificat d’interface interne du serveur Edge de Skype entreprise Server 2019 doit être demandé auprès d’une autorité de certification approuvée et affecté.</span><span class="sxs-lookup"><span data-stu-id="69b5b-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="69b5b-139">Pour modifier l’itinéraire de Fédération de la version précédente afin d’utiliser le serveur Edge de Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="69b5b-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="69b5b-140">À partir du générateur de topologie, dans le volet gauche, accédez au nœud **Skype entreprise Server 2019** , puis au nœud **pool** de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="69b5b-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="69b5b-141">Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="69b5b-142">Sélectionnez **Général** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="69b5b-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="69b5b-143">Activez la case à cocher **activer la Fédération pour ce pool Edge (port 5061)**, puis cliquez sur **OK** pour fermer la page.</span><span class="sxs-lookup"><span data-stu-id="69b5b-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="69b5b-144">Dans le menu **Action**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="69b5b-145">Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.</span><span class="sxs-lookup"><span data-stu-id="69b5b-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="69b5b-146">Vérifiez que la **Fédération (port 5061)** est définie sur **activé** dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="69b5b-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="69b5b-147">Pour mettre à jour le tronçon suivant de la Fédération du serveur Edge de Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="69b5b-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="69b5b-148">À partir du générateur de topologie, dans le volet gauche, accédez au nœud **Skype entreprise Server 2019** , puis au nœud **pool** de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="69b5b-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="69b5b-149">Développez le nœud, cliquez avec le bouton droit sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="69b5b-150">Dans la page **général** , sous **sélection du tronçon suivant**, sélectionnez dans la liste déroulante le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="69b5b-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="69b5b-151">Cliquez sur **OK** pour fermer la page Modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="69b5b-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="69b5b-152">Dans le **Générateur de topologies**, sélectionnez le nœud supérieur **Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="69b5b-153">Dans le menu **Actions**, cliquez sur **Publier la topologie** et terminez l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="69b5b-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="69b5b-154">Pour configurer le chemin d’accès sortant du serveur Edge de Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="69b5b-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="69b5b-155">Dans le volet gauche du générateur de topologie, accédez au nœud **Skype entreprise Server 2019** , puis au pool sous **serveurs frontaux Standard Edition** ou **Pools frontaux Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="69b5b-156">Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="69b5b-157">Dans la section **Associations**, activez la case à cocher **Associer un pool Edge (pour les composants multimédias)**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="69b5b-158">Dans la zone de liste déroulante, sélectionnez le serveur Edge de Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="69b5b-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="69b5b-159">Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="69b5b-160">Pour activer la Fédération de serveur Edge de Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="69b5b-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="69b5b-161">À partir du générateur de topologie, dans le volet gauche, accédez au nœud **Skype entreprise Server 2019** , puis au nœud **pool** de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="69b5b-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="69b5b-162">Développez le nœud, cliquez avec le bouton droit sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="69b5b-163">La Fédération ne peut être activée que pour un seul pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="69b5b-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="69b5b-164">Si vous avez plusieurs pools de serveurs Edge, sélectionnez-en un à utiliser comme pool Edge fédérateur.</span><span class="sxs-lookup"><span data-stu-id="69b5b-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="69b5b-165">Sur la page **général** , vérifiez que la case à cocher **activer la Fédération pour ce pool Edge (port 5061)** est activée.</span><span class="sxs-lookup"><span data-stu-id="69b5b-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="69b5b-166">Cliquez sur **OK** pour fermer la page Modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="69b5b-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="69b5b-167">Naviguez jusqu’au nœud de site.</span><span class="sxs-lookup"><span data-stu-id="69b5b-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="69b5b-168">Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="69b5b-169">Dans le volet gauche, cliquez sur **Itinéraire de fédération**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="69b5b-170">Sous **attribution**de l’itinéraire de Fédération du site, sélectionnez **activer la Fédération SIP**, puis dans la liste, sélectionnez le serveur Edge de Skype entreprise Server 2019 répertorié.</span><span class="sxs-lookup"><span data-stu-id="69b5b-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="69b5b-171">Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="69b5b-172">Pour les déploiements sur plusieurs sites, effectuez cette procédure sur chaque site.</span><span class="sxs-lookup"><span data-stu-id="69b5b-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="69b5b-173">Pour publier les modifications de configuration du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="69b5b-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="69b5b-174">Dans le **Générateur de topologies**, sélectionnez le nœud supérieur **Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="69b5b-175">Dans le menu **Actions**, sélectionnez **Publier la topologie** et terminez l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="69b5b-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="69b5b-176">Attendez que la réplication Active Directory se produise sur tous les pools de serveurs impliqués dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="69b5b-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="69b5b-177">Le message suivant peut s’afficher : **Avertissement : la topologie contient plus d’un serveur Edge fédéré. Cela peut se produire lors de la migration vers une version plus récente du produit. Dans ce cas, un seul serveur Edge est activement utilisé pour la Fédération. Vérifiez que l’enregistrement SRV DNS externe pointe vers le serveur Edge approprié. Si vous souhaitez déployer plusieurs serveurs Edge de Fédération comme étant actifs simultanément (autrement dit, pas un scénario de migration), vérifiez que tous les partenaires fédérés utilisent Skype entreprise Server. Vérifiez que l’enregistrement DNS SRV externe répertorie tous les serveurs Edge de Fédération activés.**</span><span class="sxs-lookup"><span data-stu-id="69b5b-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="69b5b-178">Cet avertissement est attendu et peut être ignoré en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="69b5b-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="69b5b-179">Pour configurer le serveur Edge de Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="69b5b-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="69b5b-180">Mettez tous les serveurs Edge Skype entreprise Server 2019 en ligne.</span><span class="sxs-lookup"><span data-stu-id="69b5b-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="69b5b-181">Mettez à jour les règles de routage du pare-feu externe ou les paramètres du programme d’équilibrage de la charge matérielle pour envoyer le trafic SIP pour l’accès externe (généralement le port 443) et la Fédération (généralement le port 5061) vers le serveur Edge de Skype entreprise Server 2019, au lieu du serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="69b5b-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="69b5b-182">Si vous ne disposez pas d’un programme d’équilibrage de la charge matérielle, vous devez mettre à jour l’enregistrement DNS A de la Fédération pour qu’il soit résolu en nouveau serveur Edge d’accès Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="69b5b-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="69b5b-183">Pour effectuer cette opération avec une interruption minimale, réduisez la valeur TLL pour le nom de domaine complet du serveur Edge d’accès externe Skype entreprise Server de sorte que lorsque DNS est mis à jour pour pointer vers le nouveau serveur Edge d’accès Skype entreprise, la Fédération et l’accès à distance seront mis à jour rapidement.</span><span class="sxs-lookup"><span data-stu-id="69b5b-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="69b5b-184">Arrêtez le serveur **Edge d’accès Skype entreprise Server** à partir de chaque ordinateur serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="69b5b-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="69b5b-185">À partir de chaque ordinateur serveur Edge hérité, ouvrez l’applet **services** à partir des **Outils d’administration**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="69b5b-186">Dans la liste des services, recherchez **serveur Edge d’accès Skype entreprise**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="69b5b-187">Cliquez avec le bouton droit sur le nom du service, puis sélectionnez **Arrêter** pour arrêter le service.</span><span class="sxs-lookup"><span data-stu-id="69b5b-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="69b5b-188">Définissez le type de démarrage sur **Désactivé**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="69b5b-189">Cliquez sur **OK** pour fermer la fenêtre **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="69b5b-189">Click **OK** to close the **Properties** window.</span></span> 
    

