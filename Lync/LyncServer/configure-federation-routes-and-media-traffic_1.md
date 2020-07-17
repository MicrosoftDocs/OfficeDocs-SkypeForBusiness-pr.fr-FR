---
title: Configurer les itinéraires de fédération et le trafic multimédia
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d6af77188809b092050629c1b74cdab8b20a2cc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754960"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="4b65c-102">Configurer les itinéraires de fédération et le trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="4b65c-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="4b65c-103">La fédération est une relation d’approbation entre deux ou plusieurs domaines SIP qui permet aux utilisateurs d’organisations distinctes de communiquer au-delà des limites des réseaux.</span><span class="sxs-lookup"><span data-stu-id="4b65c-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="4b65c-104">Une fois que vous avez effectué la migration vers votre pool pilote Lync Server 2013, vous devez passer de l’itinéraire de Fédération de vos serveurs Edge Microsoft Office Communications Server 2007 R2 à l’itinéraire de Fédération de vos serveurs Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4b65c-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="4b65c-105">Utilisez les procédures suivantes pour effectuer la transition de l’itinéraire de Fédération et de l’itinéraire de trafic multimédia de votre serveur Edge et directeur Office Communications Server 2007 R2 vers votre serveur Edge Lync Server 2013, pour un déploiement sur un seul site.</span><span class="sxs-lookup"><span data-stu-id="4b65c-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="4b65c-106">La modification de l’itinéraire de Fédération et de l’itinéraire de trafic multimédia nécessite de planifier le temps d’arrêt de la maintenance pour les serveurs Edge Lync Server 2013 et Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="4b65c-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="4b65c-107">Ce processus de transition signifie également que l’accès fédéré sera indisponible pendant la durée de l’interruption.</span><span class="sxs-lookup"><span data-stu-id="4b65c-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="4b65c-108">Vous devez donc planifier cette interruption à un moment où l’activité des utilisateurs sera minimale.</span><span class="sxs-lookup"><span data-stu-id="4b65c-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="4b65c-109">Prévoyez aussi d’en informer les utilisateurs finaux suffisamment à l’avance.</span><span class="sxs-lookup"><span data-stu-id="4b65c-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="4b65c-110">Anticipez cette interruption à tous les niveaux et informez-en votre organisation afin qu’elle s’y prépare en conséquence.</span><span class="sxs-lookup"><span data-stu-id="4b65c-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="4b65c-111">Si votre serveur Edge Office Communications Server 2007 R2 hérité est configuré pour utiliser le même nom de domaine complet pour le service Edge d’accès, le service Edge de conférence Web et le service Edge A/V, les procédures de cette section pour faire passer le paramètre de Fédération à un serveur Edge Lync Server 2013 ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="4b65c-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="4b65c-112">Si les services Edge hérités sont configurés pour utiliser le même nom de domaine complet, vous devez d’abord migrer tous vos utilisateurs d’Office Communications Server 2007 R2 vers Lync Server 2013, puis désactivez le serveur Edge Office Communications Server 2007 R2 avant d’activer la Fédération sur le serveur Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4b65c-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="4b65c-113">Pour plus de détails, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4b65c-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="4b65c-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Déplacer les utilisateurs restants vers Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="4b65c-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="4b65c-115">« Supprimer les serveurs et les rôles serveur » à l’adresse<A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="4b65c-115">"Remove Servers and Server Roles" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="4b65c-116">Si votre Fédération XMPP est acheminée via un serveur Edge Lync Server 2013, les utilisateurs hérités d’Office Communications Server 2007 R2 ne seront pas en mesure de communiquer avec le partenaire fédéré XMPP tant que tous les utilisateurs n’ont pas été déplacés vers Lync Server 2013, les stratégies XMPP et les certificats ont été configurés, le partenaire fédéré XMPP a été configuré sur Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b65c-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="4b65c-117">Pour publier, activer ou désactiver une topologie lors de l’ajout ou de la suppression d’un rôle de serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="4b65c-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="4b65c-118">Il est également possible de déléguer les autorisations et les droits d’utilisateur voulus pour ajouter des rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="4b65c-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="4b65c-119">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) dans la documentation de déploiement du serveur Standard Edition Server ou Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="4b65c-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="4b65c-120">Pour les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est requise.</span><span class="sxs-lookup"><span data-stu-id="4b65c-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="4b65c-121">Pour supprimer l’Association de Fédération héritée des sites Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b65c-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="4b65c-122">Ouvrez la topologie du pool pilote à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="4b65c-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="4b65c-123">Dans le volet gauche, naviguez jusqu’au nœud du site.</span><span class="sxs-lookup"><span data-stu-id="4b65c-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="4b65c-124">Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="4b65c-125">Sélectionnez **Itinéraire de fédération** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="4b65c-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="4b65c-126">Sous attribution de l’itinéraire de Fédération du site, désactivez la case à cocher en regard de **activer la Fédération SIP** pour désactiver l’itinéraire de Fédération via le **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="4b65c-127">![Boîte de dialogue Modifier les propriétés, itinéraire de Fédération](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, itinéraire de Fédération")</span><span class="sxs-lookup"><span data-stu-id="4b65c-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="4b65c-128">Cliquez sur **OK** pour fermer la page Modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="4b65c-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="4b65c-129">Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="4b65c-130">Dans le menu **Actions**, cliquez sur **Publier la topologie** et terminez l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="4b65c-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="4b65c-131">Pour configurer le serveur Edge hérité en tant que serveur Edge non-fédérant</span><span class="sxs-lookup"><span data-stu-id="4b65c-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="4b65c-132">Dans le **Générateur de topologie**, dans le menu **action** , cliquez sur **fusionner la topologie Office Communications Server 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="4b65c-133">Cliquez sur \*\*Suivant \*\*pour continuer.</span><span class="sxs-lookup"><span data-stu-id="4b65c-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="4b65c-134">Dans **Spécifier la configuration Edge**, sélectionnez le **Nom de domaine complet interne du serveur Edge** qui est actuellement configuré pour la fédération, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="4b65c-135">![Fusionner la topologie OCS 2007 R2, spécifier la configuration Edge](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Fusionner la topologie OCS 2007 R2, spécifier la configuration Edge")</span><span class="sxs-lookup"><span data-stu-id="4b65c-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="4b65c-136">Cliquez sur **Suivant** et acceptez les paramètres par défaut jusqu’à ce que vous accédiez à la page **Spécifier la configuration Edge externe** :</span><span class="sxs-lookup"><span data-stu-id="4b65c-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="4b65c-137">![Page spécifier le générateur de topologies](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Page spécifier le générateur de topologies")</span><span class="sxs-lookup"><span data-stu-id="4b65c-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="4b65c-p105">Dans **Spécifier la configuration Edge externe**, désactivez la case à cocher **Ce pool de serveurs Edge est utilisé pour la fédération et la solution PIC (Public IM Connectivity)**. Cela supprimera l’association de fédération avec le BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="4b65c-p105">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box. This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4b65c-p106">Cette étape est importante. Vous devez désactiver cette option pour supprimer l’association de fédération héritée.</span><span class="sxs-lookup"><span data-stu-id="4b65c-p106">This step is important. You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="4b65c-142">Cliquez sur **Suivant** et acceptez les paramètres par défaut des pages restantes de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="4b65c-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="4b65c-143">Dans **Sommaire**, cliquez sur **Suivant** pour commencer à fusionner les topologies.</span><span class="sxs-lookup"><span data-stu-id="4b65c-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="4b65c-144">Dans la colonne **État** , vérifiez que la valeur est **opération réussie**, puis cliquez sur **Terminer** pour fermer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="4b65c-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="4b65c-145">Dans le menu **Action**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="4b65c-146">Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.</span><span class="sxs-lookup"><span data-stu-id="4b65c-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="4b65c-147">![Générateur de topologies avec site affiché après la fusion](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Générateur de topologies avec site affiché après la fusion")</span><span class="sxs-lookup"><span data-stu-id="4b65c-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="4b65c-148">Comme indiqué dans la figure précédente, la **Fédération SIP** située sous **attribution** de l’itinéraire de Fédération du site est définie sur **désactivé**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="4b65c-149">Pour configurer des certificats sur le serveur Edge Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b65c-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="4b65c-150">Exportez le certificat de proxy d’accès externe, avec la clé privée, à partir du serveur Edge Office Communications Server 2007 R2 hérité.</span><span class="sxs-lookup"><span data-stu-id="4b65c-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="4b65c-151">Sur le serveur Edge Lync Server 2013, importez le certificat externe de proxy d’accès à partir de l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="4b65c-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="4b65c-152">Affectez le certificat externe de proxy d’accès à l’interface externe Lync Server 2013 du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="4b65c-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="4b65c-153">Le certificat d’interface interne du serveur Edge Lync Server 2013 ne doit pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="4b65c-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="4b65c-154">Pour modifier l’itinéraire de Fédération Office Communications Server 2007 R2 afin d’utiliser le serveur Edge Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b65c-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="4b65c-155">Sur le serveur Office Communications Server 2007 R2 Standard Edition ou le serveur frontal, ouvrez l’outil d’administration Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="4b65c-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="4b65c-p107">Dans le volet gauche, développez le nœud supérieur, puis cliquez avec le bouton droit sur le nœud **Forêt**. Sélectionnez **Propriétés**, puis cliquez sur **Propriétés globales**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-p107">In the left pane, expand the top node, and then right-click the **Forest** node. Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="4b65c-158">Cliquez sur l’onglet **Fédération**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="4b65c-159">Activez la case à cocher pour activer la fédération et la solution PIC (Public IM Connectivity).</span><span class="sxs-lookup"><span data-stu-id="4b65c-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="4b65c-160">Entrez le nom de domaine complet (FQDN) du serveur Edge Lync Server 2013, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="4b65c-161">![Propriétés globales OCS, onglet Fédération](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Propriétés globales OCS, onglet Fédération")</span><span class="sxs-lookup"><span data-stu-id="4b65c-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="4b65c-162">Pour activer la fédération du serveur Edge Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b65c-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="4b65c-163">Dans le volet de gauche du générateur de topologie, accédez au nœud des **Pools** de serveurs Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4b65c-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="4b65c-164">Développez le nœud, cliquez avec le bouton droit sur le serveur Edge listé, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="4b65c-165">La Fédération ne peut être activée que pour un seul pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="4b65c-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="4b65c-166">Si vous avez plusieurs pools de serveurs Edge, sélectionnez-en un à utiliser comme pool Edge fédérateur.</span><span class="sxs-lookup"><span data-stu-id="4b65c-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="4b65c-167">Dans la page **Général**, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="4b65c-168">![Modifier les propriétés, général, activer la Fédération Edge](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Modifier les propriétés, général, activer la Fédération Edge")</span><span class="sxs-lookup"><span data-stu-id="4b65c-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="4b65c-169">Cliquez sur **OK** pour fermer la page Modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="4b65c-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="4b65c-170">Naviguez ensuite vers le nœud du site.</span><span class="sxs-lookup"><span data-stu-id="4b65c-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="4b65c-171">Cliquez avec le bouton droit sur le site, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="4b65c-172">Dans le volet gauche, cliquez sur **Itinéraire de fédération**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="4b65c-173">Sous **attribution**de l’itinéraire de Fédération du site, sélectionnez **activer la Fédération SIP**, puis dans la liste, sélectionnez le serveur Edge Lync Server 2013 répertorié.</span><span class="sxs-lookup"><span data-stu-id="4b65c-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="4b65c-174">Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="4b65c-175">![Modifier les propriétés, général, associer un pool de serveurs Edge](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Modifier les propriétés, général, associer un pool de serveurs Edge")</span><span class="sxs-lookup"><span data-stu-id="4b65c-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="4b65c-176">Pour les déploiements sur plusieurs sites, effectuez cette procédure sur chaque site.</span><span class="sxs-lookup"><span data-stu-id="4b65c-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="4b65c-177">Pour configurer le chemin d’accès des médias sortants du serveur Edge Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b65c-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="4b65c-178">Dans le **Générateur de topologies**, accédez au pool Lync Server 2013 sous **serveurs frontaux Standard Edition** ou **Pools frontaux Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="4b65c-179">Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="4b65c-180">Dans la section **Associations**, activez la case à cocher **Associer un pool Edge (pour les composants multimédias)**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="4b65c-181">Dans la zone de liste déroulante, sélectionnez le serveur Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4b65c-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="4b65c-182">![Boîte de dialogue Modifier les propriétés, associer un pool de serveurs Edge](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Boîte de dialogue Modifier les propriétés, associer un pool de serveurs Edge")</span><span class="sxs-lookup"><span data-stu-id="4b65c-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="4b65c-183">Cliquez sur **OK** pour fermer la page **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="4b65c-184">Pour publier les modifications de configuration du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="4b65c-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="4b65c-185">Dans le **Générateur de topologie**, sélectionnez le nœud supérieur **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="4b65c-186">Dans le menu **Actions**, sélectionnez **Publier la topologie** et terminez l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="4b65c-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="4b65c-187">Attendez que la réplication Active Directory se produise sur tous les pools de serveurs impliqués dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="4b65c-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="4b65c-188">Vous pouvez voir le message suivant :</span><span class="sxs-lookup"><span data-stu-id="4b65c-188">You may see the following message:</span></span><BR><span data-ttu-id="4b65c-189"><STRONG>Attention : La topologie contient plusieurs serveurs Edge fédérés. Cela peut se produire au cours d’une migration vers une version plus récente du produit. Dans ce cas, un seul serveur Edge serait utilisé activement pour la fédération. Vérifiez que l’enregistrement SRV DNS externe pointe vers le serveur Edge voulu. Si vous voulez déployer plusieurs serveurs Edge de fédération de sorte qu’ils soient actifs simultanément (pas un scénario de migration, donc), vérifiez que tous les partenaires fédérés utilisent Office Communications Server 2007 R2 ou Lync Server. Vérifiez que l’enregistrement SRV DNS externe liste tous les serveurs Edge activés pour la fédération.</STRONG></span><span class="sxs-lookup"><span data-stu-id="4b65c-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="4b65c-190">Cet avertissement est attendu et peut être ignoré en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="4b65c-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="4b65c-191">Pour vérifier la Fédération et l’accès à distance pour les utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="4b65c-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="4b65c-192">À partir du serveur frontal Lync Server 2013, ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4b65c-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="4b65c-193">Pour vérifier l’état de la Fédération et de l’accès à distance, à partir de la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="4b65c-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="4b65c-194">Pour activer la Fédération et l’accès à distance, à partir de la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="4b65c-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="4b65c-195">Pour plus d’informations sur ces cmdlets, consultez les rubriques suivantes : [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) et [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="4b65c-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="4b65c-196">Attendez la fin de la réplication avant de mettre en ligne les serveurs Edge Lync Server 2013, et de tester la Fédération et l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="4b65c-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="4b65c-197">Pour configurer le serveur Edge Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b65c-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="4b65c-198">Mettez tous les serveurs Edge Lync Server 2013 en ligne.</span><span class="sxs-lookup"><span data-stu-id="4b65c-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="4b65c-199">Mettez à jour les règles de routage du pare-feu externe ou les paramètres du programme d’équilibrage de la charge matérielle pour envoyer le trafic SIP pour l’accès externe (généralement le port 443) et la Fédération (généralement le port 5061) vers le serveur Edge Lync Server 2013, au lieu du serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="4b65c-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="4b65c-200">Si vous ne disposez pas d’un programme d’équilibrage de la charge matérielle, vous devez mettre à jour l’enregistrement DNS A pour la Fédération afin de résoudre le nouveau serveur Edge Lync Server Access.</span><span class="sxs-lookup"><span data-stu-id="4b65c-200">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server.</span></span> <span data-ttu-id="4b65c-201">Pour effectuer cette opération en cas de perturbation minimale, réduisez la valeur de durée de vie pour le nom de domaine complet du serveur Edge d’accès externe Lync Server de sorte que lorsque DNS est mis à jour pour pointer vers le nouveau serveur Edge Lync Server Access, la Fédération et l’accès à distance seront mis à jour rapidement.</span><span class="sxs-lookup"><span data-stu-id="4b65c-201">To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="4b65c-202">Ensuite, arrêtez le serveur **Edge d’accès Lync Server** à partir de chaque ordinateur serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="4b65c-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="4b65c-203">À partir de chaque ordinateur serveur Edge hérité, ouvrez l’applet **services** à partir des **Outils d’administration**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="4b65c-204">Dans la liste des services, recherchez **Serveur Edge d’accès Office Communications Server**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="4b65c-205">Cliquez avec le bouton droit sur le nom du service, puis sélectionnez **Arrêter** pour arrêter le service.</span><span class="sxs-lookup"><span data-stu-id="4b65c-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="4b65c-206">Définissez le type de démarrage sur **Désactivé**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="4b65c-207">Cliquez sur **OK** pour fermer la fenêtre **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4b65c-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="4b65c-208">Pour tester la connectivité des utilisateurs externes et de l’accès externe</span><span class="sxs-lookup"><span data-stu-id="4b65c-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="4b65c-209">Utilisateurs d’au moins un domaine fédéré, un utilisateur interne sur Lync Server 2013 et un utilisateur sur Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="4b65c-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="4b65c-210">Testez la messagerie instantanée, la présence, l’audio/vidéo (A/V) et le partage de Bureau.</span><span class="sxs-lookup"><span data-stu-id="4b65c-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="4b65c-211">Les utilisateurs de chaque fournisseur de services de messagerie instantanée public pris en charge par votre organisation (et pour lequel le provisionnement a été effectué) communiquant avec un utilisateur sur Lync Server 2013 et un utilisateur sur Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="4b65c-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="4b65c-212">Vérifiez que les utilisateurs anonymes peuvent participer à des conférences.</span><span class="sxs-lookup"><span data-stu-id="4b65c-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="4b65c-213">Un utilisateur hébergé sur Office Communications Server 2007 R2 à l’aide de l’accès des utilisateurs distants (connexion à Office Communications Server 2007 R2 depuis l’extérieur de l’intranet mais sans VPN) avec un utilisateur sur Lync Server 2013, et un utilisateur sur Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="4b65c-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="4b65c-214">Testez la messagerie instantanée, la présence, l’audio/vidéo et le partage de Bureau.</span><span class="sxs-lookup"><span data-stu-id="4b65c-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="4b65c-215">Un utilisateur hébergé sur Lync Server 2013 à l’aide de l’accès des utilisateurs distants (connexion à Lync Server 2013 depuis l’extérieur de l’intranet mais sans VPN) avec un utilisateur sur Lync Server 2013, et un utilisateur sur Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="4b65c-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="4b65c-216">Testez la messagerie instantanée, la présence, l’audio/vidéo et le partage de Bureau.</span><span class="sxs-lookup"><span data-stu-id="4b65c-216">Test IM, presence, A/V, and desktop sharing.</span></span>

