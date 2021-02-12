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
description: La fédération est une relation d’approbation entre deux ou plusieurs domaines SIP qui permet aux utilisateurs d’organisations distinctes de communiquer au-delà des limites des réseaux. Après avoir migré vers votre pool pilote, vous devez passer de l’itinéraire de fédération de vos serveurs Edge de versions précédentes à l’itinéraire de fédération de vos serveurs Edge Skype Entreprise Server 2019.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754034"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="a5b19-104">Configurer les itinéraires de fédération et le trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="a5b19-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="a5b19-105">La fédération est une relation d’approbation entre deux ou plusieurs domaines SIP qui permet aux utilisateurs d’organisations distinctes de communiquer au-delà des limites des réseaux.</span><span class="sxs-lookup"><span data-stu-id="a5b19-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="a5b19-106">Après avoir migré vers votre pool pilote, vous devez passer de l’itinéraire de fédération des serveurs Edge de votre version précédente à l’itinéraire de fédération de vos serveurs Edge Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a5b19-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="a5b19-107">Utilisez les procédures suivantes pour faire passer l’itinéraire de fédération et l’itinéraire de trafic multimédia du serveur Edge et du directeur de votre version précédente vers votre serveur Edge Skype Entreprise Server 2019, pour un déploiement sur un seul site.</span><span class="sxs-lookup"><span data-stu-id="a5b19-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a5b19-108">Pour modifier l’itinéraire de fédération et l’itinéraire de trafic multimédia, vous devez planifier un temps d’arrêt de maintenance pour les serveurs Edge Skype Entreprise Server 2019 et version précédente.</span><span class="sxs-lookup"><span data-stu-id="a5b19-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="a5b19-109">Ce processus de transition signifie également que l’accès fédéré sera indisponible pendant la durée de l’interruption.</span><span class="sxs-lookup"><span data-stu-id="a5b19-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="a5b19-110">Vous devez donc planifier cette interruption à un moment où l’activité des utilisateurs sera minimale.</span><span class="sxs-lookup"><span data-stu-id="a5b19-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="a5b19-111">Prévoyez aussi d’en informer les utilisateurs finaux suffisamment à l’avance.</span><span class="sxs-lookup"><span data-stu-id="a5b19-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="a5b19-112">Anticipez cette interruption à tous les niveaux et informez-en votre organisation afin qu’elle s’y prépare en conséquence.</span><span class="sxs-lookup"><span data-stu-id="a5b19-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a5b19-113">Si votre serveur Edge hérité est configuré pour utiliser le même nom de groupe pour le service Edge d’accès, le service Edge de conférence Web et le service Edge A/V, les procédures de cette section ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="a5b19-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="a5b19-114">Si les services Edge hérités sont configurés pour utiliser le même nom de domaine complète, vous devez d’abord migrer tous vos utilisateurs, puis désaffecter les versions précédentes du serveur Edge avant d’activer la fédération sur le serveur Edge Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a5b19-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a5b19-115">Si votre fédération XMPP est acheminée via un serveur Edge Skype Entreprise Server 2019, les utilisateurs de la version précédente ne pourront pas communiquer avec le partenaire fédéré XMPP tant que tous les utilisateurs n’auront pas été déplacés vers Skype Entreprise Server 2019, que des stratégies et des certificats XMPP ont été configurés, le partenaire fédéré XMPP a été configuré sur Skype Entreprise Server 2019 enfin, les entrées DNS ont été mises à jour.</span><span class="sxs-lookup"><span data-stu-id="a5b19-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="a5b19-116">Pour supprimer l’association de fédération héritée des sites Skype Entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="a5b19-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="a5b19-117">Sur le serveur frontal Skype Entreprise Server 2019, ouvrez la topologie existante dans le Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="a5b19-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="a5b19-118">Dans le volet gauche, accédez au nœud de site, qui se trouve juste en dessous de **Skype Entreprise Server.**</span><span class="sxs-lookup"><span data-stu-id="a5b19-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="a5b19-119">Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="a5b19-120">Dans le volet gauche, sélectionnez **Itinéraire de fédération**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="a5b19-121">Sous **Affectation de l’itinéraire de** fédération du site, **désactivez** la case à cocher Activer la fédération SIP pour désactiver l’itinéraire de fédération via l’environnement hérité.</span><span class="sxs-lookup"><span data-stu-id="a5b19-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="a5b19-122">Cliquez sur **OK** pour fermer la page Modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="a5b19-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="a5b19-123">Dans **le Générateur de topologie,** sélectionnez le nœud supérieur Skype Entreprise **Server.**</span><span class="sxs-lookup"><span data-stu-id="a5b19-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="a5b19-124">Dans le menu **Action**, cliquez sur **Publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="a5b19-125">Cliquez **sur Suivant** pour terminer le processus de publication, puis cliquez sur **Terminer** une fois le processus de publication terminé.</span><span class="sxs-lookup"><span data-stu-id="a5b19-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="a5b19-126">Pour configurer le serveur Edge hérité en tant que serveur Edge non-fédérant</span><span class="sxs-lookup"><span data-stu-id="a5b19-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="a5b19-127">Dans le volet gauche, accédez au nœud d’installation hérité, puis au nœud **pools edge.**</span><span class="sxs-lookup"><span data-stu-id="a5b19-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="a5b19-128">Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="a5b19-129">Sélectionnez **Général** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="a5b19-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="a5b19-130">Activez la case à cocher Activer la fédération pour ce **pool Edge (port 5061)** et sélectionnez **OK** pour fermer la page.</span><span class="sxs-lookup"><span data-stu-id="a5b19-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="a5b19-131">Dans le menu **Action**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="a5b19-132">Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.</span><span class="sxs-lookup"><span data-stu-id="a5b19-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="a5b19-133">Vérifiez que la fédération pour le serveur Edge hérité est désactivée dans le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="a5b19-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="a5b19-134">Pour configurer des certificats sur le serveur Edge hérité</span><span class="sxs-lookup"><span data-stu-id="a5b19-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="a5b19-135">Exportez le certificat de proxy d’accès externe, avec la clé privée, à partir du serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="a5b19-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="a5b19-136">Sur le serveur Edge Skype Entreprise Server 2019 et importez le certificat externe du proxy d’accès de l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="a5b19-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="a5b19-137">Affectez le certificat externe de proxy d’accès à l’interface externe Skype Entreprise Server 2019 du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="a5b19-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="a5b19-138">Le certificat d’interface interne du serveur Edge Skype Entreprise Server 2019 doit être demandé à une ca de confiance et affecté.</span><span class="sxs-lookup"><span data-stu-id="a5b19-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="a5b19-139">Pour modifier l’itinéraire de fédération de la version précédente afin d’utiliser le serveur Edge Skype Entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="a5b19-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="a5b19-140">À partir du Générateur de topologie, dans le volet gauche, accédez au nœud Skype Entreprise **Server 2019,** puis au nœud **pools Edge.**</span><span class="sxs-lookup"><span data-stu-id="a5b19-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="a5b19-141">Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="a5b19-142">Sélectionnez **Général** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="a5b19-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="a5b19-143">Activez la case à cocher Activer la fédération pour ce **pool Edge (port 5061),** puis cliquez sur **OK** pour fermer la page.</span><span class="sxs-lookup"><span data-stu-id="a5b19-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="a5b19-144">Dans le menu **Action**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="a5b19-145">Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.</span><span class="sxs-lookup"><span data-stu-id="a5b19-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="a5b19-146">Vérifiez que **la fédération (port 5061)** est définie sur **Activé dans** le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="a5b19-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="a5b19-147">Pour mettre à jour le saut suivant de fédération du serveur Edge Skype Entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="a5b19-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="a5b19-148">À partir du Générateur de topologie, dans le volet gauche, accédez au nœud Skype Entreprise **Server 2019,** puis au nœud **pools Edge.**</span><span class="sxs-lookup"><span data-stu-id="a5b19-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="a5b19-149">Développez le nœud, cliquez avec le bouton droit sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="a5b19-150">Dans la page **Général,** sous Sélection du **saut** suivant, sélectionnez le pool Skype Entreprise Server 2019 dans la liste de listes listes.</span><span class="sxs-lookup"><span data-stu-id="a5b19-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="a5b19-151">Cliquez sur **OK** pour fermer la page Modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="a5b19-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="a5b19-152">Dans **le Générateur de topologie,** sélectionnez le nœud supérieur Skype Entreprise **Server.**</span><span class="sxs-lookup"><span data-stu-id="a5b19-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="a5b19-153">Dans le menu **Actions**, cliquez sur **Publier la topologie** et terminez l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="a5b19-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="a5b19-154">Pour configurer le chemin d’accès multimédia sortant du serveur Edge Skype Entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="a5b19-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="a5b19-155">À partir du Générateur de topologie, dans le volet gauche, accédez au nœud Skype Entreprise **Server 2019,** puis au pool sous les serveurs frontux **Standard Edition** ou **Enterprise Edition.**</span><span class="sxs-lookup"><span data-stu-id="a5b19-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="a5b19-156">Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="a5b19-157">Dans la section **Associations**, activez la case à cocher **Associer un pool Edge (pour les composants multimédias)**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="a5b19-158">Dans la zone de baisse, sélectionnez le serveur Edge Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a5b19-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="a5b19-159">Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="a5b19-160">Pour activer la fédération de serveur Edge Skype Entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="a5b19-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="a5b19-161">À partir du Générateur de topologie, dans le volet gauche, accédez au nœud Skype Entreprise **Server 2019,** puis au nœud **pools Edge.**</span><span class="sxs-lookup"><span data-stu-id="a5b19-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="a5b19-162">Développez le nœud, cliquez avec le bouton droit sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="a5b19-163">La fédération ne peut être activée que pour un seul pool edge.</span><span class="sxs-lookup"><span data-stu-id="a5b19-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="a5b19-164">Si vous avez plusieurs pools de serveurs Edge, sélectionnez-en un à utiliser comme pool Edge fédérateur.</span><span class="sxs-lookup"><span data-stu-id="a5b19-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="a5b19-165">Dans la page **Général,** vérifiez que la case à cocher Activer la fédération pour ce **pool Edge (port 5061)** est activée.</span><span class="sxs-lookup"><span data-stu-id="a5b19-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="a5b19-166">Cliquez sur **OK** pour fermer la page Modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="a5b19-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="a5b19-167">Accédez au nœud de site.</span><span class="sxs-lookup"><span data-stu-id="a5b19-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="a5b19-168">Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="a5b19-169">Dans le volet gauche, cliquez sur **Itinéraire de fédération**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="a5b19-170">Sous **Affectation de l’itinéraire** de fédération du site, sélectionnez Activer la fédération **SIP,** puis, dans la liste, sélectionnez le serveur Edge Skype Entreprise Server 2019 répertorié.</span><span class="sxs-lookup"><span data-stu-id="a5b19-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="a5b19-171">Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="a5b19-172">Pour les déploiements sur plusieurs sites, effectuez cette procédure sur chaque site.</span><span class="sxs-lookup"><span data-stu-id="a5b19-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="a5b19-173">Pour publier les modifications de configuration du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="a5b19-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="a5b19-174">Dans **le Générateur de topologie,** sélectionnez le nœud supérieur Skype Entreprise **Server.**</span><span class="sxs-lookup"><span data-stu-id="a5b19-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="a5b19-175">Dans le menu **Actions**, sélectionnez **Publier la topologie** et terminez l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="a5b19-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="a5b19-176">Attendez que la réplication Active Directory se produise sur tous les pools de serveurs impliqués dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="a5b19-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a5b19-177">Vous pouvez voir le message suivant : **Avertissement : la topologie contient plusieurs serveurs Edge fédérés. Cela peut se produire lors de la migration vers une version plus récente du produit. Dans ce cas, un seul serveur Edge serait activement utilisé pour la fédération. Vérifiez que l’enregistrement SRV DNS externe pointe vers le serveur Edge correct. Si vous souhaitez déployer plusieurs serveurs Edge de fédération pour qu’ils soient actifs simultanément (autrement dit, pas un scénario de migration), vérifiez que tous les partenaires fédérés utilisent Skype Entreprise Server. Vérifiez que l’enregistrement SRV DNS** externe répertorie tous les serveurs Edge activés pour la fédération.</span><span class="sxs-lookup"><span data-stu-id="a5b19-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="a5b19-178">Cet avertissement est attendu et peut être ignoré en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="a5b19-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="a5b19-179">Pour configurer le serveur Edge Skype Entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="a5b19-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="a5b19-180">Mettre tous les serveurs Edge Skype Entreprise Server 2019 en ligne.</span><span class="sxs-lookup"><span data-stu-id="a5b19-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="a5b19-181">Mettez à jour les règles de routage du pare-feu externe ou les paramètres du programme d’équilibrage de la charge matérielle pour envoyer le trafic SIP pour l’accès externe (généralement le port 443) et la fédération (généralement le port 5061) vers le serveur Edge Skype Entreprise Server 2019, au lieu du serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="a5b19-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a5b19-182">Si vous n’avez pas d’équilibrage de la charge matérielle, vous devez mettre à jour l’enregistrement DNS A pour la fédération afin de résoudre le nouveau serveur Edge d’accès Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a5b19-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="a5b19-183">Pour y parvenir avec une perturbation minimale, réduisez la valeur de la TLL pour le nom de domaine universel edge d’accès Skype Entreprise Server externe de sorte que lorsque le DNS est mis à jour pour pointer vers le nouveau serveur Edge d’accès Skype Entreprise Server, la fédération et l’accès à distance seront mis à jour rapidement.</span><span class="sxs-lookup"><span data-stu-id="a5b19-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="a5b19-184">Arrêtez le **serveur Edge d’accès Skype Entreprise Server** à partir de chaque ordinateur serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="a5b19-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="a5b19-185">À partir de chaque ordinateur serveur Edge hérité, ouvrez l’applet **services** à partir des **outils d’administration.**</span><span class="sxs-lookup"><span data-stu-id="a5b19-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="a5b19-186">Dans la liste des services, recherchez **Skype Entreprise Server Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="a5b19-187">Cliquez avec le bouton droit sur le nom du service, puis sélectionnez **Arrêter** pour arrêter le service.</span><span class="sxs-lookup"><span data-stu-id="a5b19-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="a5b19-188">Définissez le type de démarrage sur **Désactivé**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="a5b19-189">Cliquez sur **OK** pour fermer la fenêtre **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a5b19-189">Click **OK** to close the **Properties** window.</span></span> 
    

