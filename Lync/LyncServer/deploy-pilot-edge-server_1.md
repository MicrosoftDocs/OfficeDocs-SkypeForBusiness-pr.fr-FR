---
title: Déploiement du serveur Edge pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cbf3be6dd47f794768ba0f3c8140e7124a1cabb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="a5ff7-102">Déploiement du serveur Edge pilote</span><span class="sxs-lookup"><span data-stu-id="a5ff7-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5ff7-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a5ff7-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a5ff7-104">Cette rubrique présente les paramètres de configuration que vous devez connaître avant de déployer votre serveur Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="a5ff7-105">Cette section met en évidence les points clés que vous devez prendre en compte dans le cadre de votre déploiement pilote de pool Edge.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="a5ff7-106">Pour obtenir la procédure détaillée, voir [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement, qui décrit le processus de déploiement et fournit également des informations de configuration pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="a5ff7-p102">À mesure que vous parcourez l’Assistant **Définir un nouveau pool Edge**, examinez les principaux paramètres de configuration mentionnés aux étapes suivantes. Notez que seules quelques pages de l’Assistant **Définir un nouveau pool Edge** sont illustrées.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-p102">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="a5ff7-109">**Pour définir un pool Edge**</span><span class="sxs-lookup"><span data-stu-id="a5ff7-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="a5ff7-110">Ouvrez la topologie du pool pilote à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="a5ff7-111">Accédez au nœud Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="a5ff7-112">Cliquez avec le bouton droit sur **Pools Edge**, puis cliquez sur **Nouveau pool de serveurs Edge**.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="a5ff7-113">![Boîte de dialogue définir le nouveau pool Edge](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Boîte de dialogue définir le nouveau pool Edge")</span><span class="sxs-lookup"><span data-stu-id="a5ff7-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="a5ff7-114">Un pool Edge peut être un **pool de plusieurs ordinateurs** ou un **pool d’un seul ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="a5ff7-115">![Boîte de dialogue définir le nom de domaine complet du pool Edge](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Boîte de dialogue définir le nom de domaine complet du pool Edge")</span><span class="sxs-lookup"><span data-stu-id="a5ff7-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="a5ff7-116">Dans la page **Sélectionner les fonctionnalités**, n’activez pas la fédération ni la fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="a5ff7-117">Fédération et la Fédération XMPP sont actuellement routées via le serveur Edge Office Communications Server 2007 R2 hérité.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="a5ff7-118">Ces fonctionnalités seront configurées lors d’une phase ultérieure de la migration.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="a5ff7-119">![Boîte de dialogue Sélectionner les fonctionnalités](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Boîte de dialogue Sélectionner les fonctionnalités")</span><span class="sxs-lookup"><span data-stu-id="a5ff7-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="a5ff7-120">Ensuite, continuez à remplir les pages suivantes de l’Assistant : **Sélectionner les options IP**, noms de **domaine complets externes**, **définir l’adresse IP interne**et **définir l’adresse IP externe**.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="a5ff7-121">Sur la page **définir le tronçon suivant** , sélectionnez le directeur pour le tronçon suivant du pool de serveurs Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="a5ff7-122">![Boîte de dialogue définir un nouveau pool de serveurs Edge, liste Pool du tronçon suivant](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Boîte de dialogue définir un nouveau pool de serveurs Edge, liste Pool du tronçon suivant")</span><span class="sxs-lookup"><span data-stu-id="a5ff7-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="a5ff7-123">Dans la page **Pools frontaux associés** , n’associez pas un pool à ce pool Edge pour le moment.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="a5ff7-124">Le trafic multimédia externe est actuellement routé via le serveur Edge Office Communications Server 2007 R2 hérité.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="a5ff7-125">Ce paramètre sera configuré lors d’une phase ultérieure de la migration.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="a5ff7-126">![Boîte de dialogue définir un nouveau pool de serveurs Edge](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Boîte de dialogue définir un nouveau pool de serveurs Edge")</span><span class="sxs-lookup"><span data-stu-id="a5ff7-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="a5ff7-127">Cliquez sur **Terminer**, puis sur **Publier** pour publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="a5ff7-128">Suivez les étapes décrites dans [install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur Edge, configurer les certificats et démarrer les services.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="a5ff7-129">Il est très important de suivre les instructions des rubriques déploiement de l' [accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="a5ff7-130">Cette section ne fait que fournir des recommandations concernant les paramètres de configuration lors de l’installation de ces rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="a5ff7-131">Vous devez maintenant disposer d’un déploiement de serveur Edge Office Communications Server 2007 R2 hérité, indiqué par la présence du BackCompatSite, en parallèle à un déploiement de serveur Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="a5ff7-132">La Fédération est configurée pour utiliser le directeur Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="a5ff7-133">Vérifiez que les deux déploiements fonctionnent correctement, que les services ont démarré et que vous pouvez administrer chaque déploiement avant de passer à la phase suivante.</span><span class="sxs-lookup"><span data-stu-id="a5ff7-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="a5ff7-134">![Générateur de topologies affichant le serveur Edge OCS](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Générateur de topologies affichant le serveur Edge OCS")</span><span class="sxs-lookup"><span data-stu-id="a5ff7-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

