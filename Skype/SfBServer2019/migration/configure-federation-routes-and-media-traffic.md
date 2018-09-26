---
title: Configurer la fédération itinéraires et le trafic multimédia
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: La fédération est une relation d’approbation entre deux ou plusieurs domaines SIP qui permet aux utilisateurs d’entreprises distinctes de communiquer au-delà des frontières du réseau. Après avoir migré vers votre pool pilote, vous devez transition à partir de l’itinéraire de fédération de vos serveurs Edge de versions antérieures à l’itinéraire de fédération de votre Skype pour les serveurs de périphérie 2019 Business Server.
ms.openlocfilehash: 3d6fb6455221b85c4cdbfc63a5a868cdf6444341
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027332"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="290bd-104">Configurer la fédération itinéraires et le trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="290bd-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="290bd-105">La fédération est une relation d’approbation entre deux ou plusieurs domaines SIP qui permet aux utilisateurs d’entreprises distinctes de communiquer au-delà des frontières du réseau.</span><span class="sxs-lookup"><span data-stu-id="290bd-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="290bd-106">Après avoir migré vers votre pool pilote, vous devez transition à partir de l’itinéraire de fédération de la version précédente serveurs de périphérie pour l’itinéraire de fédération de votre Skype pour les serveurs de périphérie 2019 Business Server.</span><span class="sxs-lookup"><span data-stu-id="290bd-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="290bd-107">Utilisez les procédures suivantes pour passer l’itinéraire de fédération et l’itinéraire de trafic multimédia de votre version précédente du serveur de transport Edge et directeur à votre Skype pour Business 2019 Edge Server, pour un déploiement de site unique.</span><span class="sxs-lookup"><span data-stu-id="290bd-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="290bd-108">Modification de l’itinéraire de fédération et l’itinéraire de trafic multimédia nécessite que vous planifiez temps mort de maintenance pour le Skype pour Business Server 2019 et la version précédente de serveurs de périphérie.</span><span class="sxs-lookup"><span data-stu-id="290bd-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="290bd-109">Ce processus toute transition signifie également que les accès fédéré n’est pas disponible pour la durée de la panne.</span><span class="sxs-lookup"><span data-stu-id="290bd-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="290bd-110">Vous devez planifier le temps d’arrêt pendant une période donnée lorsque vous prévoyez une activité utilisateur minimale.</span><span class="sxs-lookup"><span data-stu-id="290bd-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="290bd-111">Vous devez également fournir une notification suffisante à vos utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="290bd-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="290bd-112">Planifier en conséquence, ce jeu de dépannage appropriées attentes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="290bd-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="290bd-113">Si votre serveur Edge hérité est configuré pour utiliser le même nom de domaine complet pour le service Edge d’accès, service Edge de conférence Web et A / V Edge service, les procédures décrites dans cette section ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="290bd-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="290bd-114">Si les services Edge hérités sont configurés pour utiliser le même nom de domaine complet, vous devez d’abord migrer tous vos utilisateurs, puis mettre hors service les serveur Edge de versions précédentes avant d’activer la fédération sur le Skype pour Business Server 2019 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="290bd-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="290bd-115">Si la fédération XMPP est routée via un Skype pour le serveur de périphérie 2019 Business Server, les utilisateurs de la version précédente ne sera pas en mesure de communiquer avec les partenaires fédérés XMPP jusqu'à ce que tous les utilisateurs ont été déplacés vers Skype pour Business Server 2019, stratégies XMPP et les certificats qui ont été configurés, le partenaire fédéré XMPP a été configuré sur Skype pour Business Server 2019 et, enfin, les entrées DNS ont été mis à jour.</span><span class="sxs-lookup"><span data-stu-id="290bd-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="290bd-116">Pour supprimer l’association de fédération hérité de Skype pour les sites Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="290bd-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="290bd-117">Sur Skype pour le serveur frontal Business Server 2019, ouvrez la topologie existante dans le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="290bd-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="290bd-118">Dans le volet gauche, accédez au nœud du site, qui se trouve juste au-dessous **Skype pour Business Server**.</span><span class="sxs-lookup"><span data-stu-id="290bd-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="290bd-119">Cliquez sur le site, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="290bd-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="290bd-120">Dans le volet gauche, sélectionnez **itinéraire de fédération**.</span><span class="sxs-lookup"><span data-stu-id="290bd-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="290bd-121">Sous **attribution itinéraire de fédération du Site**, désactivez la case à cocher **Activer la fédération SIP** pour désactiver l’itinéraire de fédération par le biais de l’ancien environnement.</span><span class="sxs-lookup"><span data-stu-id="290bd-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="290bd-122">Cliquez sur **OK** pour fermer la page Modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="290bd-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="290bd-123">Dans **Le Générateur de topologie**, sélectionnez le nœud supérieur **Skype pour Business Server**.</span><span class="sxs-lookup"><span data-stu-id="290bd-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="290bd-124">Dans le menu **Action** , cliquez sur **Publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="290bd-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="290bd-125">Cliquez sur **suivant** pour terminer le processus de publication, puis cliquez sur **Terminer** lorsque le processus de publication est terminée.</span><span class="sxs-lookup"><span data-stu-id="290bd-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="290bd-126">Pour configurer le serveur Edge hérité comme un serveur Edge non fédéré</span><span class="sxs-lookup"><span data-stu-id="290bd-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="290bd-127">Dans le volet gauche, accédez au nœud installer hérité, puis au nœud **Edge pools** .</span><span class="sxs-lookup"><span data-stu-id="290bd-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="290bd-128">Cliquez sur le serveur de périphérie, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="290bd-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="290bd-129">Sélectionnez **Général** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="290bd-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="290bd-130">Désactivez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)** et cliquez sur **OK** pour fermer la page.</span><span class="sxs-lookup"><span data-stu-id="290bd-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="290bd-131">Dans le menu **Action** , sélectionnez **Publier la topologie**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="290bd-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="290bd-132">Lorsque l' **Assistant Publication** a terminé, cliquez sur **Terminer** pour fermer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="290bd-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="290bd-133">Vérifiez que la fédération pour le serveur Edge hérité est désactivée dans le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="290bd-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="290bd-134">Pour configurer des certificats sur le serveur Edge hérité</span><span class="sxs-lookup"><span data-stu-id="290bd-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="290bd-135">Exportez le certificat de Proxy d’accès externe, avec la clé privée, depuis le serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="290bd-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="290bd-136">Sur le Skype pour Business Server 2019 Edge Server et l’importation du certificat externe du Proxy d’accès de l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="290bd-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="290bd-137">Affecter le certificat externe de Proxy d’accès à la Skype pour Business Server 2019, interface externe du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="290bd-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="290bd-138">Le certificat de l’interface interne de le Skype pour le serveur de périphérie 2019 Business Server doit être demandé à partir d’une autorité de certification approuvée et assigné.</span><span class="sxs-lookup"><span data-stu-id="290bd-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="290bd-139">Pour changer l’itinéraire de fédération de la version précédente pour utiliser Skype pour Business Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="290bd-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="290bd-140">À partir du Générateur de topologie dans le volet gauche, accédez au nœud **Skype pour Business Server 2019** , puis le nœud **pools de serveurs Edge** .</span><span class="sxs-lookup"><span data-stu-id="290bd-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="290bd-141">Cliquez sur le serveur de périphérie, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="290bd-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="290bd-142">Sélectionnez **Général** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="290bd-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="290bd-143">Activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**, puis cliquez sur **OK** pour fermer la page.</span><span class="sxs-lookup"><span data-stu-id="290bd-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="290bd-144">Dans le menu **Action** , sélectionnez **Publier la topologie**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="290bd-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="290bd-145">Lorsque l' **Assistant Publication** a terminé, cliquez sur **Terminer** pour fermer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="290bd-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="290bd-146">Vérifiez que **fédération (port 5061)** est **activé** dans le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="290bd-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="290bd-147">Pour mettre à jour Skype pour le tronçon suivant de fédération Business Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="290bd-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="290bd-148">À partir du Générateur de topologie dans le volet gauche, accédez au nœud **Skype pour Business Server 2019** , puis le nœud **pools de serveurs Edge** .</span><span class="sxs-lookup"><span data-stu-id="290bd-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="290bd-149">Développez le nœud, cliquez sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="290bd-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="290bd-150">Dans la page **Général** , sous **sélection du tronçon suivant**, sélectionnez le Skype pour Business Server 2019 pool dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="290bd-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="290bd-151">Cliquez sur **OK** pour fermer la page Modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="290bd-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="290bd-152">Dans **Le Générateur de topologie**, sélectionnez le nœud supérieur **Skype pour Business Server**.</span><span class="sxs-lookup"><span data-stu-id="290bd-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="290bd-153">Dans le menu **Action** , cliquez sur **Publier la topologie** et terminez l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="290bd-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="290bd-154">Pour configurer Skype pour le chemin d’accès de serveur de périphérie Business Server 2019 sortant des médias</span><span class="sxs-lookup"><span data-stu-id="290bd-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="290bd-155">À partir du Générateur de topologie dans le volet gauche, naviguez jusqu’au nœud **Skype pour Business Server 2019** puis jusqu’au pool sous **Serveurs frontaux frontaux Standard Edition** ou **pools frontaux Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="290bd-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="290bd-156">Avec le bouton droit de la liste, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="290bd-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="290bd-157">Dans la section **Associations** , activez la case à cocher **pool Edge associé (pour les composants multimédias)** .</span><span class="sxs-lookup"><span data-stu-id="290bd-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="290bd-158">Dans la zone de liste déroulante, sélectionnez le Skype pour Business Server 2019 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="290bd-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="290bd-159">Cliquez sur **OK** pour fermer la page **Modifier les propriétés** .</span><span class="sxs-lookup"><span data-stu-id="290bd-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="290bd-160">Pour activer la fédération Business Server 2019 Edge Server Skype</span><span class="sxs-lookup"><span data-stu-id="290bd-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="290bd-161">À partir du Générateur de topologie dans le volet gauche, accédez au nœud **Skype pour Business Server 2019** , puis le nœud **pools de serveurs Edge** .</span><span class="sxs-lookup"><span data-stu-id="290bd-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="290bd-162">Développez le nœud, cliquez sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="290bd-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="290bd-163">Fédération ne peut pas être activée pour un seul pool Edge.</span><span class="sxs-lookup"><span data-stu-id="290bd-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="290bd-164">Si vous avez plusieurs pools Edge, sélectionnez celle à utiliser en tant que le pool Edge fédéré.</span><span class="sxs-lookup"><span data-stu-id="290bd-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="290bd-165">Dans la page **Général** , vérifiez que la case à cocher **Activer la fédération pour ce pool Edge (Port 5061)** est activée.</span><span class="sxs-lookup"><span data-stu-id="290bd-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="290bd-166">Cliquez sur **OK** pour fermer la page Modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="290bd-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="290bd-167">Accédez au nœud du site.</span><span class="sxs-lookup"><span data-stu-id="290bd-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="290bd-168">Cliquez sur le site, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="290bd-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="290bd-169">Dans le volet gauche, cliquez sur **itinéraire de fédération**.</span><span class="sxs-lookup"><span data-stu-id="290bd-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="290bd-170">Sous **attribution itinéraire de fédération du Site**, sélectionnez **Activer la fédération SIP**, puis, dans la liste Sélectionnez le Skype pour Business Server 2019 Edge Server répertoriés.</span><span class="sxs-lookup"><span data-stu-id="290bd-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="290bd-171">Cliquez sur **OK** pour fermer la page **Modifier les propriétés** .</span><span class="sxs-lookup"><span data-stu-id="290bd-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="290bd-172">Pour les déploiements sur plusieurs sites, effectuez cette procédure sur chaque site.</span><span class="sxs-lookup"><span data-stu-id="290bd-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="290bd-173">Pour publier les modifications de configuration de serveur de transport Edge</span><span class="sxs-lookup"><span data-stu-id="290bd-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="290bd-174">Dans **Le Générateur de topologie**, sélectionnez le nœud supérieur **Skype pour Business Server**.</span><span class="sxs-lookup"><span data-stu-id="290bd-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="290bd-175">Dans le menu **Action** , sélectionnez **Publier la topologie** et terminez l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="290bd-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="290bd-176">Attendez que la réplication Active Directory se produise sur tous les pools dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="290bd-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="290bd-177">Vous pouvez voir le message suivant : **Avertissement : la topologie contient plusieurs serveurs de périphérie fédérés. Cela peut se produire durant la migration vers une version plus récente du produit. Dans ce cas, un seul serveur Edge serait activement utilisé pour la fédération. Vérifiez que l’enregistrement SRV DNS externe pointe vers le serveur de périphérie approprié. Si vous souhaitez déployer plusieurs fédération serveur Edge à active simultanément (c'est-à-dire, pas un scénario de migration), vérifiez que tous les partenaires fédérés utilisent Skype pour Business Server. Vérifiez que l’enregistrement DNS SRV externe répertorie tous les serveurs de périphérie de fédération activée.**</span><span class="sxs-lookup"><span data-stu-id="290bd-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="290bd-178">Cet avertissement est attendu et peut être ignoré en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="290bd-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="290bd-179">Pour configurer Skype pour Business Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="290bd-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="290bd-180">Mettez tous le Skype pour les serveurs de périphérie 2019 Business Server en ligne.</span><span class="sxs-lookup"><span data-stu-id="290bd-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="290bd-181">Mettre à jour les règles de routage pare-feu externe ou les paramètres d’équilibrage de charge matériel pour envoyer le trafic SIP pour l’accès externe (généralement le port 443) et la fédération (généralement le port 5061) à la Skype pour le serveur Edge 2019 Business Server, au lieu du serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="290bd-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="290bd-182">Si vous ne disposez pas d’un mécanisme d’équilibrage de charge, vous devez mettre à jour l’enregistrement DNS A pour la fédération résoudre le nouveau Skype pour le serveur Edge d’accès serveur Business.</span><span class="sxs-lookup"><span data-stu-id="290bd-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="290bd-183">Pour ce faire, avec une interruption minimale, diminuer la valeur TLL pour la Skype externe pour le nom de domaine complet Business serveur Access Edge afin que la mise à jour du DNS pour pointer vers le nouveau Skype pour Business serveur Edge d’accès, la fédération et accès à distance à jour rapidement.</span><span class="sxs-lookup"><span data-stu-id="290bd-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="290bd-184">Arrêtez le **Skype pour le serveur Edge d’accès entreprise** à partir de chaque ordinateur serveur de périphérie.</span><span class="sxs-lookup"><span data-stu-id="290bd-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="290bd-185">À partir de chaque ordinateur serveur de transport Edge hérité, ouvrez l’applet **Services** dans les **Outils d’administration**.</span><span class="sxs-lookup"><span data-stu-id="290bd-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="290bd-186">Dans la liste des services, recherchez **Skype pour Business serveur Edge d’accès**.</span><span class="sxs-lookup"><span data-stu-id="290bd-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="290bd-187">Le bouton droit sur les services, puis sélectionnez **Arrêter** pour arrêter le service.</span><span class="sxs-lookup"><span data-stu-id="290bd-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="290bd-188">Définir le type de démarrage sur **désactivé**.</span><span class="sxs-lookup"><span data-stu-id="290bd-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="290bd-189">Cliquez sur **OK** pour fermer la fenêtre **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="290bd-189">Click **OK** to close the **Properties** window.</span></span> 
    

