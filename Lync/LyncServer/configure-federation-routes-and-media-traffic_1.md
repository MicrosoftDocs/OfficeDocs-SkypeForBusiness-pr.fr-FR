---
title: Configuration des itinéraires de fédération et du trafic multimédia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4542ae02cc72dfbac05dfa982e2fbda7f2924919
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838784"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="81dbe-102">Configuration des itinéraires de fédération et du trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="81dbe-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="81dbe-103">La Fédération est une relation d’approbation entre au moins deux domaines SIP, qui permet aux utilisateurs d’organisations distinctes de communiquer au sein des frontières du réseau.</span><span class="sxs-lookup"><span data-stu-id="81dbe-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="81dbe-104">Après avoir effectué une migration vers votre pool de pilotes de Lync Server 2013, vous devez effectuer une transition de l’itinéraire de Fédération de vos serveurs Microsoft Office Communications Server 2007 R2 vers l’itinéraire de Fédération de vos serveurs Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81dbe-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="81dbe-105">Utilisez les procédures qui suivent pour basculer l’itinéraire de la Fédération et l’itinéraire de trafic multimédia de votre serveur et directeur Office Communications Server 2007 R2 vers votre serveur Edge Lync Server 2013 pour un déploiement sur site.</span><span class="sxs-lookup"><span data-stu-id="81dbe-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="81dbe-106">La modification de l’itinéraire et de l’itinéraire de trafic multimédia requis pour la planification de la maintenance des serveurs Lync Server 2013 et Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="81dbe-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="81dbe-107">Ce processus de transition complet signifie également que l’accès fédéré ne sera pas disponible pendant la durée de la période d’interruption.</span><span class="sxs-lookup"><span data-stu-id="81dbe-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="81dbe-108">Nous vous conseillons de planifier le temps d’arrêt à un moment où vous vous attendez à un minimum d’activités utilisateur.</span><span class="sxs-lookup"><span data-stu-id="81dbe-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="81dbe-109">Vous devez également fournir une notification suffisante à vos utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="81dbe-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="81dbe-110">Planifiez en conséquence pour cette interruption et définissez les attentes appropriées au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="81dbe-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="81dbe-111">Si votre serveur Edge Office Communications Server 2007 R2 hérité est configuré de manière à utiliser le même nom de domaine complet pour le service Edge d’accès, le service Edge de conférence Web et le service Edge A/V, les procédures de cette section pour faire basculer le paramètre de Fédération vers un serveur Lync 2013 Edge Server n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="81dbe-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="81dbe-112">Si les services d’arête hérités sont configurés pour utiliser le même nom de domaine complet (FQDN), vous devez tout d’abord migrer tous vos utilisateurs d’Office Communications Server 2007 R2 vers Lync Server 2013, puis désaffecter le serveur Edge Office Communications Server 2007 R2 avant d’activer la Fédération. Serveur Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81dbe-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="81dbe-113">Pour obtenir des détails, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="81dbe-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="81dbe-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Déplacement des autres utilisateurs vers Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="81dbe-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="81dbe-115">"Supprimer les serveurs et les rôles serveur" sur<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="81dbe-115">"Remove Servers and Server Roles" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="81dbe-116">Si votre Fédération XMPP est routée via un serveur Edge Lync Server 2013, les utilisateurs d’Office Communications Server 2007 R2 hérités ne seront pas en mesure de communiquer avec le partenaire fédéré de XMPP tant que tous les utilisateurs n’ont pas été déplacés vers Lync Server 2013, les stratégies XMPP et des certificats ont été configurés, le partenaire fédéré de XMPP a été configuré sur Lync Server 2013, et la mise à jour des entrées DNS.</span><span class="sxs-lookup"><span data-stu-id="81dbe-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="81dbe-117">Pour publier, activer ou désactiver une topologie lors de l’ajout ou de la suppression d’un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Admins du domaine.</span><span class="sxs-lookup"><span data-stu-id="81dbe-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="81dbe-118">Il est également possible de déléguer les droits d’utilisateur et les autorisations nécessaires pour ajouter des rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="81dbe-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="81dbe-119">Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync server 2013](lync-server-2013-delegate-setup-permissions.md) dans la documentation de déploiement Standard Edition Server ou Enterprise Edition Server.</span><span class="sxs-lookup"><span data-stu-id="81dbe-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="81dbe-120">Pour les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est requise.</span><span class="sxs-lookup"><span data-stu-id="81dbe-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="81dbe-121">Pour supprimer l’Association de Fédération héritée des sites Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81dbe-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="81dbe-122">Ouvrez la topologie de pool pilote à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="81dbe-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="81dbe-123">Dans le volet gauche, accédez au nœud site.</span><span class="sxs-lookup"><span data-stu-id="81dbe-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="81dbe-124">Cliquez avec le bouton droit sur le site, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="81dbe-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="81dbe-125">Dans le volet gauche, sélectionnez **routage de Fédération** .</span><span class="sxs-lookup"><span data-stu-id="81dbe-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="81dbe-126">Sous affectation de l’itinéraire de Fédération de site, désactivez la case à cocher en regard de **activer la Fédération SIP** pour désactiver le routage de Fédération via le **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="81dbe-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="81dbe-127">![Boîte de dialogue Modifier les propriétés, itinéraire de Fédération] (images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, itinéraire de Fédération")</span><span class="sxs-lookup"><span data-stu-id="81dbe-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="81dbe-128">Cliquez sur **OK** pour fermer la page modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="81dbe-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="81dbe-129">Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **serveur Lync**.</span><span class="sxs-lookup"><span data-stu-id="81dbe-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="81dbe-130">Dans le menu **action** , cliquez sur **publier la topologie** et terminer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="81dbe-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="81dbe-131">Pour configurer le serveur de périphérie traditionnel en tant que serveur Edge non fédéré</span><span class="sxs-lookup"><span data-stu-id="81dbe-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="81dbe-132">Dans le **Générateur de topologie**, à partir du menu d' **action** , cliquez sur **fusionner Office Communications Server 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="81dbe-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="81dbe-133">Cliquez sur **Suivant** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="81dbe-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="81dbe-134">Dans la **configuration spécifier le bord**, sélectionnez le **FQDN interne du serveur Edge** actuellement configuré pour la Fédération, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="81dbe-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="81dbe-135">![Fusionner la topologie OCS 2007 R2, spécifier l’installation de Microsoft Edge] (images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Fusionner la topologie OCS 2007 R2, spécifier l’installation de Microsoft Edge")</span><span class="sxs-lookup"><span data-stu-id="81dbe-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="81dbe-136">Cliquez sur **suivant** et acceptez les paramètres par défaut jusqu’à ce que vous atteigniez la page **spécifier le bord externe** :</span><span class="sxs-lookup"><span data-stu-id="81dbe-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="81dbe-137">Le ![Générateur de topologie spécifie une page de bord externe] Le (images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Générateur de topologie spécifie une page de bord externe")</span><span class="sxs-lookup"><span data-stu-id="81dbe-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="81dbe-138">Dans **spécifier le bord externe**, décochez la case **ce pool de bords est utilisé pour la connectivité de Fédération et de messagerie instantanée publique** .</span><span class="sxs-lookup"><span data-stu-id="81dbe-138">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box.</span></span> <span data-ttu-id="81dbe-139">Cette opération a pour supprimer l’Association de Fédération avec le BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="81dbe-139">This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="81dbe-140">Cette étape est importante.</span><span class="sxs-lookup"><span data-stu-id="81dbe-140">This step is important.</span></span> <span data-ttu-id="81dbe-141">Vous devez désactiver cette option pour supprimer l’Association de Fédération héritée.</span><span class="sxs-lookup"><span data-stu-id="81dbe-141">You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="81dbe-142">Cliquez sur **suivant** et acceptez les paramètres par défaut des pages restantes de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="81dbe-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="81dbe-143">En **Résumé**, cliquez sur **suivant** pour commencer à fusionner les topologies.</span><span class="sxs-lookup"><span data-stu-id="81dbe-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="81dbe-144">Dans la colonne **État** , assurez-vous que la valeur est **succès**, puis cliquez sur **Terminer** pour fermer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="81dbe-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="81dbe-145">Dans le menu **action** , cliquez sur **publier la topologie**, puis sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="81dbe-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="81dbe-146">Lorsque l' **Assistant Publication** est terminé, cliquez sur **Terminer** pour fermer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="81dbe-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="81dbe-147">![Générateur de topologie avec site affiché après la fusion] (images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Générateur de topologie avec site affiché après la fusion")</span><span class="sxs-lookup"><span data-stu-id="81dbe-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="81dbe-148">Comme indiqué dans l’illustration précédente, la **Fédération SIP** située sous **affectation** de l’itinéraire de Fédération de site est définie sur **désactivé**.</span><span class="sxs-lookup"><span data-stu-id="81dbe-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="81dbe-149">Pour configurer des certificats sur le serveur Edge Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81dbe-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="81dbe-150">Exportez le certificat de proxy d’accès externe, avec la clé privée, à partir du serveur Edge Office Communications Server 2007 R2 hérité.</span><span class="sxs-lookup"><span data-stu-id="81dbe-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="81dbe-151">Sur le serveur Edge Lync Server 2013, importez le certificat externe de proxy d’accès à partir de l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="81dbe-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="81dbe-152">Attribuez le certificat externe du proxy d’accès à l’interface externe de Lync Server 2013 du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="81dbe-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="81dbe-153">Le certificat d’interface interne du serveur Edge Lync Server 2013 ne doit pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="81dbe-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="81dbe-154">Pour modifier l’itinéraire de Fédération d’Office Communications Server 2007 R2 pour utiliser Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="81dbe-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="81dbe-155">Sur le serveur Office Communications Server 2007 R2 Standard Edition Server ou front end Server, ouvrez l’outil d’administration Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="81dbe-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="81dbe-156">Dans le volet gauche, développez le nœud supérieur, puis cliquez avec le bouton droit sur le nœud de la **forêt** .</span><span class="sxs-lookup"><span data-stu-id="81dbe-156">In the left pane, expand the top node, and then right-click the **Forest** node.</span></span> <span data-ttu-id="81dbe-157">Sélectionnez **Propriétés**, puis cliquez sur **propriétés globales**.</span><span class="sxs-lookup"><span data-stu-id="81dbe-157">Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="81dbe-158">Cliquez sur l’onglet **Fédération** .</span><span class="sxs-lookup"><span data-stu-id="81dbe-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="81dbe-159">Activez la case à cocher pour activer la connectivité de Fédération et de messagerie instantanée publique.</span><span class="sxs-lookup"><span data-stu-id="81dbe-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="81dbe-160">Entrez le nom de domaine complet (FQDN) du serveur Edge Lync Server 2013, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81dbe-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="81dbe-161">![Propriétés internationales d’OCS, onglet Fédération] (images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Propriétés internationales d’OCS, onglet Fédération")</span><span class="sxs-lookup"><span data-stu-id="81dbe-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="81dbe-162">Pour activer la Fédération de serveur Edge Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81dbe-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="81dbe-163">Dans le générateur de topologie, dans le volet gauche, accédez au nœud de pools de **périphériques** Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81dbe-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="81dbe-164">Développez le nœud, cliquez avec le bouton droit sur le serveur Edge indiqué, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="81dbe-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="81dbe-165">La Fédération ne peut être activée que pour un seul pool de bords.</span><span class="sxs-lookup"><span data-stu-id="81dbe-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="81dbe-166">Si vous avez plusieurs pools de bords, sélectionnez-en un pour les utiliser comme pools de frontière de Fédération.</span><span class="sxs-lookup"><span data-stu-id="81dbe-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="81dbe-167">Dans la page **général** , activez la case à cocher **activer la Fédération pour ce pool Edge (port 5061)** .</span><span class="sxs-lookup"><span data-stu-id="81dbe-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="81dbe-168">![Modification des propriétés, générale, activer la Fédération Edge] (images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Modification des propriétés, générale, activer la Fédération Edge")</span><span class="sxs-lookup"><span data-stu-id="81dbe-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="81dbe-169">Cliquez sur **OK** pour fermer la page modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="81dbe-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="81dbe-170">Ensuite, accédez au nœud site.</span><span class="sxs-lookup"><span data-stu-id="81dbe-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="81dbe-171">Cliquez avec le bouton droit sur le site, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="81dbe-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="81dbe-172">Dans le volet de gauche, cliquez sur **route de Fédération**.</span><span class="sxs-lookup"><span data-stu-id="81dbe-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="81dbe-173">Sous **affectation**de l’itinéraire de la Fédération de sites, sélectionnez **activer la Fédération SIP**, puis dans la liste, sélectionnez le serveur Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81dbe-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="81dbe-174">Cliquez sur **OK** pour fermer la page **modifier les propriétés** .</span><span class="sxs-lookup"><span data-stu-id="81dbe-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="81dbe-175">![Modification des propriétés, général et pool de périphérie] (images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Modification des propriétés, général et pool de périphérie")</span><span class="sxs-lookup"><span data-stu-id="81dbe-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="81dbe-176">Pour les déploiements multisites, procédez comme suit sur chaque site.</span><span class="sxs-lookup"><span data-stu-id="81dbe-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="81dbe-177">Pour configurer le chemin multimédia sortant du serveur Lync Server 2013 Edge</span><span class="sxs-lookup"><span data-stu-id="81dbe-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="81dbe-178">Dans le **Générateur de topologie**, accédez au pool Lync Server 2013 inférieur aux **serveurs front end standard** ou aux pools front-end **Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="81dbe-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="81dbe-179">Cliquez avec le bouton droit sur la liste, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="81dbe-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="81dbe-180">Dans la section **associations** , activez la case à cocher **associer le pool Edge (pour les composants multimédias)** .</span><span class="sxs-lookup"><span data-stu-id="81dbe-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="81dbe-181">Dans la zone de liste déroulante, sélectionnez le serveur Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81dbe-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="81dbe-182">![Boîte de dialogue Modifier les propriétés, groupe de bords] (images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, groupe de bords")</span><span class="sxs-lookup"><span data-stu-id="81dbe-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="81dbe-183">Cliquez sur **OK** pour fermer la page **modifier les propriétés** .</span><span class="sxs-lookup"><span data-stu-id="81dbe-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="81dbe-184">Pour publier les modifications de configuration de serveur Edge</span><span class="sxs-lookup"><span data-stu-id="81dbe-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="81dbe-185">Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **serveur Lync**.</span><span class="sxs-lookup"><span data-stu-id="81dbe-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="81dbe-186">Dans le menu **action** , sélectionnez **publier la topologie** et terminer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="81dbe-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="81dbe-187">Attendez la fin de la réplication Active Directory pour tous les pools du déploiement.</span><span class="sxs-lookup"><span data-stu-id="81dbe-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="81dbe-188">Le message suivant risque de s’afficher:</span><span class="sxs-lookup"><span data-stu-id="81dbe-188">You may see the following message:</span></span><BR><span data-ttu-id="81dbe-189"><STRONG>AVERTISSEMENT: la topologie comporte plus d’un serveur Edge fédéré. Cela peut se produire lors de la migration vers une version plus récente du produit. Dans ce cas, un seul serveur Edge serait utilisé activement pour la Fédération. Vérifiez que l’enregistrement SRV DNS externe pointe vers le serveur Edge approprié. Si vous voulez déployer plusieurs serveurs de frontière de Fédération de manière à être actifs en même temps (c’est-à-dire, pas dans un scénario de migration), vérifiez que tous les partenaires fédérés utilisent Office Communications Server 2007 R2 ou Lync Server. Vérifiez que l’enregistrement SRV DNS externe recense tous les serveurs Edge compatibles avec la Fédération.</STRONG></span><span class="sxs-lookup"><span data-stu-id="81dbe-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="81dbe-190">Cet avertissement est attendu et peut être ignoré en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="81dbe-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="81dbe-191">Pour vérifier la Fédération et l’accès à distance pour les utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="81dbe-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="81dbe-192">À partir du serveur frontal Lync Server 2013, ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="81dbe-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="81dbe-193">Pour vérifier l’état de la Fédération et de l’accès à distance, à partir de la ligne de commande, tapez ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="81dbe-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="81dbe-194">Pour activer la Fédération et l’accès à distance, à partir de la ligne de commande, tapez ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="81dbe-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="81dbe-195">Pour plus d’informations sur ces applets de commande, reportez-vous aux rubriques suivantes: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) et [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="81dbe-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="81dbe-196">Attendez la fin de la réplication avant de mettre en ligne les serveurs Edge Lync Server 2013 et de tester la Fédération et l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="81dbe-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="81dbe-197">Pour configurer Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="81dbe-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="81dbe-198">Accédez à tous les serveurs Edge Lync Server 2013 en ligne.</span><span class="sxs-lookup"><span data-stu-id="81dbe-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="81dbe-199">Mettez à jour les règles de routage de pare-feu externe ou les paramètres de l’équilibrage de charge matérielle pour envoyer le trafic SIP pour l’accès externe (en général, le port 443) et la Fédération (en général, le port 5061) vers le serveur Edge Lync Server 2013, au lieu du serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="81dbe-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="81dbe-200">Si vous n’avez pas d’équilibrage de charge matérielle, vous devez mettre à jour l’enregistrement DNS A pour la Fédération pour résoudre le nouveau serveur Lync Server Access Edge.</span><span class="sxs-lookup"><span data-stu-id="81dbe-200">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server.</span></span> <span data-ttu-id="81dbe-201">Pour effectuer cette opération avec un minimum de perturbation, réduisez la valeur de durée de vie du nom de domaine complet (FQDN) du périmètre du serveur Lync Server de façon à ce qu’elle pointe vers le nouveau serveur Lync Server Access Edge.</span><span class="sxs-lookup"><span data-stu-id="81dbe-201">To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="81dbe-202">Ensuite, arrêtez le **Edge d’accès de Lync Server** depuis chaque ordinateur du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="81dbe-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="81dbe-203">À partir de chaque ordinateur serveur Edge hérité, ouvrez l’application **services** à partir des **Outils d’administration**.</span><span class="sxs-lookup"><span data-stu-id="81dbe-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="81dbe-204">Dans la liste des services, recherchez **Edge Access pour Office Communications Server**.</span><span class="sxs-lookup"><span data-stu-id="81dbe-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="81dbe-205">Cliquez avec le bouton droit sur le nom des services, puis sélectionnez **arrêter** pour arrêter le service.</span><span class="sxs-lookup"><span data-stu-id="81dbe-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="81dbe-206">Définissez le type de démarrage sur **désactivé**.</span><span class="sxs-lookup"><span data-stu-id="81dbe-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="81dbe-207">Cliquez sur **OK** pour fermer la fenêtre **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="81dbe-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="81dbe-208">Pour tester la connectivité des utilisateurs externes et l’accès externe</span><span class="sxs-lookup"><span data-stu-id="81dbe-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="81dbe-209">Utilisateurs d’au moins un domaine fédéré, utilisateur interne sur Lync Server 2013 et un utilisateur sur Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="81dbe-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="81dbe-210">Testez la messagerie instantanée, la présence, les appels audio/vidéo (A/V) et le partage de bureau.</span><span class="sxs-lookup"><span data-stu-id="81dbe-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="81dbe-211">Utilisateurs de chaque fournisseur de services de messagerie instantanée publique pris en charge par votre organisation (et pour lequel la mise en service a été effectuée) communique avec un utilisateur sur Lync Server 2013 et un utilisateur sur Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="81dbe-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="81dbe-212">Vérifiez que les utilisateurs anonymes peuvent participer à des conférences.</span><span class="sxs-lookup"><span data-stu-id="81dbe-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="81dbe-213">Un utilisateur hébergé sur Office Communications Server 2007 R2 à l’aide de l’accès des utilisateurs distants (connexion à Office Communications Server 2007 R2 hors de l’intranet, mais sans VPN) avec un utilisateur sur Lync Server 2013, et un utilisateur sur Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="81dbe-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="81dbe-214">Testez la messagerie instantanée, la présence, A/V et le partage du bureau.</span><span class="sxs-lookup"><span data-stu-id="81dbe-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="81dbe-215">Un utilisateur hébergé sur Lync Server 2013 à l’aide de l’accès des utilisateurs distants (connexion à Lync Server 2013 hors de l’intranet, mais sans VPN) avec un utilisateur sur Lync Server 2013 et un utilisateur sur Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="81dbe-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="81dbe-216">Testez la messagerie instantanée, la présence, A/V et le partage du bureau.</span><span class="sxs-lookup"><span data-stu-id="81dbe-216">Test IM, presence, A/V, and desktop sharing.</span></span>

