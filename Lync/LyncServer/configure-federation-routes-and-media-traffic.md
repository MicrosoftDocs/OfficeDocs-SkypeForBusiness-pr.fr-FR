---
title: Configurer les itinéraires de fédération et le trafic multimédia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f5b3e0a775af649b7210dd75dcf90d012f2e421
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="5ba78-102">Configurer les itinéraires de fédération et le trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="5ba78-102">Configure federation routes and media traffic</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ba78-103">_**Dernière modification de la rubrique :** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="5ba78-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="5ba78-104">La fédération est une relation d’approbation entre deux ou plusieurs domaines SIP qui permet aux utilisateurs d’organisations distinctes de communiquer au-delà des limites des réseaux.</span><span class="sxs-lookup"><span data-stu-id="5ba78-104">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="5ba78-105">Une fois que vous avez effectué la migration vers votre pool pilote Lync Server 2013, vous devez effectuer la transition de l’itinéraire de Fédération de vos serveurs Edge Lync Server 2010 vers l’itinéraire de Fédération de vos serveurs Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ba78-105">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Lync Server 2010 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="5ba78-106">Utilisez les procédures suivantes pour effectuer la transition de l’itinéraire de Fédération et de l’itinéraire de trafic multimédia de votre serveur Edge et directeur Lync Server 2010 vers votre serveur Edge Lync Server 2013, pour un déploiement sur un seul site.</span><span class="sxs-lookup"><span data-stu-id="5ba78-106">Use the following procedures to transition the federation route and the media traffic route from your Lync Server 2010 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5ba78-107">La modification de l’itinéraire de Fédération et de l’itinéraire de trafic multimédia nécessite de planifier le temps d’arrêt de la maintenance pour les serveurs Edge Lync Server 2013 et Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5ba78-107">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Lync Server 2010 Edge Servers.</span></span> <span data-ttu-id="5ba78-108">Ce processus de transition signifie également que l’accès fédéré sera indisponible pendant la durée de l’interruption.</span><span class="sxs-lookup"><span data-stu-id="5ba78-108">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="5ba78-109">Vous devez donc planifier cette interruption à un moment où l’activité des utilisateurs sera minimale.</span><span class="sxs-lookup"><span data-stu-id="5ba78-109">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="5ba78-110">Prévoyez aussi d’en informer les utilisateurs finaux suffisamment à l’avance.</span><span class="sxs-lookup"><span data-stu-id="5ba78-110">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="5ba78-111">Anticipez cette interruption à tous les niveaux et informez-en votre organisation afin qu’elle s’y prépare en conséquence.</span><span class="sxs-lookup"><span data-stu-id="5ba78-111">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5ba78-112">Si votre serveur Edge Lync Server 2010 hérité est configuré pour utiliser le même nom de domaine complet pour le service Edge d’accès, le service Edge de conférence Web et le service Edge A/V, les procédures décrites dans cette section ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="5ba78-112">If your legacy Lync Server 2010 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="5ba78-113">Si les services Edge hérités sont configurés pour utiliser le même nom de domaine complet, vous devez d’abord migrer tous vos utilisateurs de Lync Server 2010 vers Lync Server 2013, puis mettre hors service le serveur Edge Lync Server 2010 avant d’activer la Fédération sur le serveur Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ba78-113">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Lync Server 2010 to Lync Server 2013, then decommission the Lync Server 2010 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5ba78-114">Si votre Fédération XMPP est routée via un serveur Edge Lync Server 2013, les utilisateurs hérités de Lync Server 2010 ne seront pas en mesure de communiquer avec le partenaire fédéré XMPP tant que tous les utilisateurs n’ont pas été déplacés vers Lync Server 2013, les stratégies XMPP et les certificats ont été configuré, le partenaire fédéré XMPP a été configuré sur Lync Server 2013 et les entrées DNS ont été mises à jour.</span><span class="sxs-lookup"><span data-stu-id="5ba78-114">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Lync Server 2010 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="5ba78-115">Pour supprimer l’Association de Fédération héritée des sites Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ba78-115">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="5ba78-116">Sur le serveur frontal Lync Server 2013, ouvrez la topologie existante dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="5ba78-116">On the Lync Server 2013 Front End server, open the existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="5ba78-117">Dans le volet gauche, accédez au nœud du site, situé directement sous **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-117">In the left pane, navigate to the site node, which is located directly below **Lync Server**.</span></span>

3.  <span data-ttu-id="5ba78-118">Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-118">Right-click the site and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="5ba78-119">Dans le volet gauche, sélectionnez **Itinéraire de fédération**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-119">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="5ba78-120">Sous **attribution**de l’itinéraire de Fédération du site, désactivez la case à cocher **activer la Fédération SIP** pour désactiver l’itinéraire de Fédération via l’environnement Lync Server 2010 hérité.</span><span class="sxs-lookup"><span data-stu-id="5ba78-120">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy Lync Server 2010 environment.</span></span>
    
    <span data-ttu-id="5ba78-121">![Boîte de dialogue Modifier les propriétés, page itinéraire de Fédération](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page itinéraire de Fédération")</span><span class="sxs-lookup"><span data-stu-id="5ba78-121">![Edit Properties dialog, Federation route page](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>

6.  <span data-ttu-id="5ba78-122">Cliquez sur **OK** pour fermer la page Modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="5ba78-122">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="5ba78-123">Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-123">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="5ba78-124">Dans le menu **Action**, cliquez sur **Publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-124">From the **Action** menu, click **Publish Topology**.</span></span>

9.  <span data-ttu-id="5ba78-125">Cliquez sur **Suivant** pour terminer le processus de publication, puis cliquez sur **Terminer** quand la publication est terminée.</span><span class="sxs-lookup"><span data-stu-id="5ba78-125">Click **Next** to complete the publishing process and then click **Finish** when the publishing process has completed.</span></span>

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="5ba78-126">Pour configurer le serveur Edge hérité en tant que serveur Edge non-fédérant</span><span class="sxs-lookup"><span data-stu-id="5ba78-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="5ba78-127">Dans le volet gauche, accédez au nœud **Lync Server 2010**, puis au nœud **Pool de serveurs Edge**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-127">In the left pane, navigate to the **Lync Server 2010** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="5ba78-128">Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="5ba78-129">Sélectionnez **Général** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="5ba78-129">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="5ba78-130">Décochez la case **Activer la fédération pour ce pool Edge (port 5061)** et sélectionnez **OK** pour fermer la page.</span><span class="sxs-lookup"><span data-stu-id="5ba78-130">Clear the **Enable federation for this Edge pool (port 5061)** check box entry and select **OK** to close the page.</span></span>
    
    <span data-ttu-id="5ba78-131">![Modifier les propriétés, général, effacer la Fédération d’activation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Modifier les propriétés, général, effacer la Fédération d’activation")</span><span class="sxs-lookup"><span data-stu-id="5ba78-131">![Edit Properties, General, clear Enable federation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Edit Properties, General, clear Enable federation")</span></span>

5.  <span data-ttu-id="5ba78-132">Dans le menu **Action**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-132">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="5ba78-133">Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.</span><span class="sxs-lookup"><span data-stu-id="5ba78-133">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="5ba78-134">Vérifiez que la fédération pour le serveur Edge hérité est désactivée.</span><span class="sxs-lookup"><span data-stu-id="5ba78-134">Verify federation for the legacy Edge server is disabled.</span></span>
    
    <span data-ttu-id="5ba78-135">![Générateur de topologies, pool Edge, Fédération désactivée](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Générateur de topologies, pool Edge, Fédération désactivée")</span><span class="sxs-lookup"><span data-stu-id="5ba78-135">![Topology Builder, Edge pool, federation disabled](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topology Builder, Edge pool, federation disabled")</span></span>

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a><span data-ttu-id="5ba78-136">Pour configurer des certificats sur le serveur Edge Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="5ba78-136">To configure certificates on the Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="5ba78-137">Exportez le certificat de proxy d’accès externe, avec la clé privée, à partir du serveur Edge hérité de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5ba78-137">Export the external Access Proxy certificate, with the private key, from the legacy Lync Server 2010 Edge Server.</span></span>

2.  <span data-ttu-id="5ba78-138">Sur le serveur Edge Lync Server 2013, importez le certificat externe de proxy d’accès à partir de l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="5ba78-138">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="5ba78-139">Affectez le certificat externe de proxy d’accès à l’interface externe Lync Server 2013 du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="5ba78-139">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="5ba78-140">Le certificat d’interface interne du serveur Edge Lync Server 2013 doit être demandé auprès d’une autorité de certification approuvée et affecté.</span><span class="sxs-lookup"><span data-stu-id="5ba78-140">The internal interface certificate of the Lync Server 2013 Edge Server should be requested from a trusted CA and assigned.</span></span>

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="5ba78-141">Pour changer l’itinéraire de fédération Lync Server 2010 pour utiliser un serveur Edge Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ba78-141">To change Lync Server 2010 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="5ba78-142">Dans le volet gauche du Générateur de topologie, accédez au nœud **Lync Server 2013**, puis au nœud **Pool de serveurs Edge**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-142">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="5ba78-143">Cliquez avec le bouton droit sur le serveur Edge, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-143">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="5ba78-144">Sélectionnez **Général** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="5ba78-144">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="5ba78-145">Cochez la case **Activer la fédération pour ce pool Edge (port 5061)**, puis cliquez sur **OK** pour fermer la page.</span><span class="sxs-lookup"><span data-stu-id="5ba78-145">Select the check box entry for **Enable federation for this Edge pool (port 5061)** and then click **OK** to close the page.</span></span>
    
    <span data-ttu-id="5ba78-146">![Boîte de dialogue Modifier les propriétés, page général](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page général")</span><span class="sxs-lookup"><span data-stu-id="5ba78-146">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

5.  <span data-ttu-id="5ba78-147">Dans le menu **Action**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-147">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="5ba78-148">Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.</span><span class="sxs-lookup"><span data-stu-id="5ba78-148">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="5ba78-149">Vérifiez que **Fédération (port 5061)** est **Activé**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-149">Verify **Federation (port 5061)** is set to **Enabled**.</span></span>
    
    <span data-ttu-id="5ba78-150">![Générateur de topologies, pool de serveurs Edge, Fédération activée](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Générateur de topologies, pool de serveurs Edge, Fédération activée")</span><span class="sxs-lookup"><span data-stu-id="5ba78-150">![Topology Builder, Edge pool, Federation enabled](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topology Builder, Edge pool, Federation enabled")</span></span>

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a><span data-ttu-id="5ba78-151">Pour mettre à jour le tronçon suivant de fédération du serveur Edge Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ba78-151">To update Lync Server 2013 Edge Server federation next hop</span></span>

1.  <span data-ttu-id="5ba78-152">Dans le volet gauche du Générateur de topologie, accédez au nœud **Lync Server 2013**, puis au nœud **Pool de serveurs Edge**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-152">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="5ba78-153">Développez le nœud, cliquez avec le bouton droit sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-153">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="5ba78-154">Dans la page **général** , sous **sélection du tronçon suivant**, sélectionnez dans la liste déroulante le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ba78-154">On the **General** page, under **Next hop selection**, select from the drop-down list the Lync Server 2013  pool.</span></span>
    
    <span data-ttu-id="5ba78-155">![Boîte de dialogue Modifier les propriétés, page tronçon suivant](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page tronçon suivant")</span><span class="sxs-lookup"><span data-stu-id="5ba78-155">![Edit Properties dialog, Next hop page](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Edit Properties dialog, Next hop page")</span></span>

4.  <span data-ttu-id="5ba78-156">Cliquez sur **OK** pour fermer la page Modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="5ba78-156">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="5ba78-157">Dans le **Générateur de topologies**, sélectionnez le nœud supérieur **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="5ba78-157">From **Topology Builder**, select the top node **Lync Server** .</span></span>

6.  <span data-ttu-id="5ba78-158">Dans le menu **Actions**, cliquez sur **Publier la topologie** et terminez l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="5ba78-158">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="5ba78-159">Pour configurer le chemin d’accès des médias sortants du serveur Edge Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ba78-159">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="5ba78-160">À partir du générateur de topologie, dans le volet gauche, accédez au nœud **Lync Server 2013** , puis au pool sous **serveurs frontaux Standard Edition** ou **Pools frontaux Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-160">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="5ba78-161">Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-161">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="5ba78-162">Dans la section **Associations**, activez la case à cocher **Associer un pool Edge (pour les composants multimédias)**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-162">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>
    
    <span data-ttu-id="5ba78-163">![Modifier les propriétés, général, associer un pool de serveurs Edge](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Modifier les propriétés, général, associer un pool de serveurs Edge")</span><span class="sxs-lookup"><span data-stu-id="5ba78-163">![Edit Properties, General, Associate Edge pool](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>

4.  <span data-ttu-id="5ba78-164">Dans la zone de liste déroulante, sélectionnez le serveur Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ba78-164">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>

5.  <span data-ttu-id="5ba78-165">Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-165">Click **OK** to close the **Edit Properties** page.</span></span>

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="5ba78-166">Pour activer la fédération du serveur Edge Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ba78-166">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="5ba78-167">Dans le volet gauche du Générateur de topologie, accédez au nœud **Lync Server 2013**, puis au nœud **Pool de serveurs Edge**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-167">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="5ba78-168">Développez le nœud, cliquez avec le bouton droit sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-168">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ba78-169">La Fédération ne peut être activée que pour un seul pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="5ba78-169">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="5ba78-170">Si vous avez plusieurs pools de serveurs Edge, sélectionnez-en un à utiliser comme pool Edge fédérateur.</span><span class="sxs-lookup"><span data-stu-id="5ba78-170">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>

    
    </div>

3.  <span data-ttu-id="5ba78-171">Dans la page **Général**, vérifiez que le paramètre **Activer la fédération pour ce pool Edge (port 5061)** est coché.</span><span class="sxs-lookup"><span data-stu-id="5ba78-171">On the **General** page, verify the **Enable federation for this Edge pool (Port 5061)** setting is checked.</span></span>
    
    <span data-ttu-id="5ba78-172">![Boîte de dialogue Modifier les propriétés, page général](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, page général")</span><span class="sxs-lookup"><span data-stu-id="5ba78-172">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

4.  <span data-ttu-id="5ba78-173">Cliquez sur **OK** pour fermer la page Modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="5ba78-173">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="5ba78-174">Naviguez ensuite vers le nœud du site.</span><span class="sxs-lookup"><span data-stu-id="5ba78-174">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="5ba78-175">Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-175">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="5ba78-176">Dans le volet gauche, cliquez sur **Itinéraire de fédération**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-176">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="5ba78-177">Sous **attribution**de l’itinéraire de Fédération du site, sélectionnez **activer la Fédération SIP**, puis dans la liste, sélectionnez le serveur Edge Lync Server 2013 répertorié.</span><span class="sxs-lookup"><span data-stu-id="5ba78-177">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>
    
    <span data-ttu-id="5ba78-178">![Modifier les propriétés, page itinéraire de Fédération](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Modifier les propriétés, page itinéraire de Fédération")</span><span class="sxs-lookup"><span data-stu-id="5ba78-178">![Edit Properties, Federation route page](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Edit Properties, Federation route page")</span></span>

9.  <span data-ttu-id="5ba78-179">Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-179">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="5ba78-180">Pour les déploiements sur plusieurs sites, effectuez cette procédure sur chaque site.</span><span class="sxs-lookup"><span data-stu-id="5ba78-180">For multi-site deployments, complete this procedure at each site.</span></span>

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="5ba78-181">Pour publier les modifications de configuration du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="5ba78-181">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="5ba78-182">Dans le **Générateur de topologies**, sélectionnez le nœud supérieur **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="5ba78-182">From **Topology Builder**, select the top node **Lync Server** .</span></span>

2.  <span data-ttu-id="5ba78-183">Dans le menu **Actions**, sélectionnez **Publier la topologie** et terminez l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="5ba78-183">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="5ba78-184">Attendez que la réplication Active Directory se produise sur tous les pools de serveurs impliqués dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="5ba78-184">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ba78-185">Vous pouvez voir le message suivant :</span><span class="sxs-lookup"><span data-stu-id="5ba78-185">You may see the following message:</span></span><BR><span data-ttu-id="5ba78-186"><STRONG>Attention : La topologie contient plusieurs serveurs Edge fédérés. Cela peut se produire au cours d’une migration vers une version plus récente du produit. Dans ce cas, un seul serveur Edge serait utilisé activement pour la fédération. Vérifiez que l’enregistrement SRV DNS externe pointe vers le serveur Edge voulu. Si vous voulez déployer plusieurs serveurs Edge de fédération de sorte qu’ils soient actifs simultanément (pas un scénario de migration, donc), vérifiez que tous les partenaires fédérés utilisent Lync Server. Vérifiez que l’enregistrement SRV DNS externe liste tous les serveurs Edge activés pour la fédération.</STRONG></span><span class="sxs-lookup"><span data-stu-id="5ba78-186"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="5ba78-187">Cet avertissement est attendu et peut être ignoré en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="5ba78-187">This warning is expected and can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="5ba78-188">Pour configurer le serveur Edge Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ba78-188">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="5ba78-189">Mettez tous les serveurs Edge Lync Server 2013 en ligne.</span><span class="sxs-lookup"><span data-stu-id="5ba78-189">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="5ba78-190">Mettez à jour les règles de routage du pare-feu externe ou les paramètres du programme d’équilibrage de la charge matérielle pour envoyer le trafic SIP pour l’accès externe (généralement le port 443) et la Fédération (généralement le port 5061) vers le serveur Edge Lync Server 2013, au lieu du serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="5ba78-190">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ba78-p105">Si vous n’utilisez pas un équilibreur de charge matérielle, vous devez mettre à jour l’enregistrement A DNS pour que la fédération puisse résoudre le nouveau serveur Edge d’accès Lync Server. Pour ce faire, réduisez la valeur TLL pour le FQDN du serveur Edge d’accès Lync Server externe afin que lorsque le DNS est mis à jour pour pointer vers le nouveau serveur Edge d’accès Lync Server, la fédération et l’accès à distance soient mis à jour rapidement.</span><span class="sxs-lookup"><span data-stu-id="5ba78-p105">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Lync Server Access Edge server. To accomplish this with minimum disruption, reduce the TLL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge, federation and remote access will be updated quickly.</span></span>

    
    </div>

3.  <span data-ttu-id="5ba78-193">Ensuite, arrêtez le serveur **Edge d’accès Lync Server** à partir de chaque ordinateur serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="5ba78-193">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="5ba78-194">À partir de chaque ordinateur serveur Edge hérité, ouvrez l’applet **services** à partir des **Outils d’administration**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-194">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="5ba78-195">Dans la liste des services, trouvez **Serveur Edge d’accès Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-195">In the services list, find **Lync Server Access Edge**.</span></span>

6.  <span data-ttu-id="5ba78-196">Cliquez avec le bouton droit sur le nom du service, puis sélectionnez **Arrêter** pour arrêter le service.</span><span class="sxs-lookup"><span data-stu-id="5ba78-196">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="5ba78-197">Définissez le type de démarrage sur **Désactivé**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-197">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="5ba78-198">Cliquez sur **OK** pour fermer la fenêtre **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5ba78-198">Click **OK** to close the **Properties** window.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

