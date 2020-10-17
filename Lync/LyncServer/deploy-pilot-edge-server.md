---
title: Déploiement d’un serveur Edge pilote
description: Déployez le serveur Edge pilote.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d63e9255ad448995fcafa05fed12e97ea151736b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550730"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="eec5e-103">Déploiement d’un serveur Edge pilote</span><span class="sxs-lookup"><span data-stu-id="eec5e-103">Deploy pilot Edge Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eec5e-104">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="eec5e-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="eec5e-105">Cette rubrique présente les paramètres de configuration que vous devez connaître avant de déployer votre serveur Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eec5e-105">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="eec5e-106">Les processus de déploiement et de configuration de Lync Server 2013 sont très similaires à Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="eec5e-106">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="eec5e-107">Cette section présente uniquement les points clés dont vous devez tenir compte dans le cadre du déploiement de votre pool pilote.</span><span class="sxs-lookup"><span data-stu-id="eec5e-107">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="eec5e-108">Pour obtenir la procédure détaillée, voir [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement, qui décrit le processus de déploiement et fournit également des informations de configuration pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="eec5e-108">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="eec5e-p102">À mesure que vous parcourez l’Assistant **Définir un nouveau pool Edge**, examinez les principaux paramètres de configuration mentionnés aux étapes suivantes. Notez que seules quelques pages de l’Assistant **Définir un nouveau pool Edge** sont illustrées.</span><span class="sxs-lookup"><span data-stu-id="eec5e-p102">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="eec5e-111">**Pour définir un pool Edge**</span><span class="sxs-lookup"><span data-stu-id="eec5e-111">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="eec5e-112">Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="eec5e-112">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="eec5e-113">Accédez au nœud Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eec5e-113">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="eec5e-114">Cliquez avec le bouton droit sur **Pools Edge**, puis cliquez sur **Nouveau pool de serveurs Edge**.</span><span class="sxs-lookup"><span data-stu-id="eec5e-114">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="eec5e-115">![Boîte de dialogue définir le nouveau pool Edge](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Boîte de dialogue définir le nouveau pool Edge")</span><span class="sxs-lookup"><span data-stu-id="eec5e-115">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="eec5e-116">Un pool Edge peut être un **pool de plusieurs ordinateurs** ou un **pool d’un seul ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="eec5e-116">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="eec5e-117">![Boîte de dialogue définir le nom de domaine complet du pool Edge](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Boîte de dialogue définir le nom de domaine complet du pool Edge")</span><span class="sxs-lookup"><span data-stu-id="eec5e-117">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="eec5e-118">Dans la page **Sélectionner les fonctionnalités**, n’activez pas la fédération ni la fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="eec5e-118">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="eec5e-119">Fédération et la Fédération XMPP sont actuellement routées via le serveur Edge Lync Server 2010 hérité.</span><span class="sxs-lookup"><span data-stu-id="eec5e-119">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="eec5e-120">Ces fonctionnalités seront configurées lors d’une phase ultérieure de la migration.</span><span class="sxs-lookup"><span data-stu-id="eec5e-120">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="eec5e-121">![Boîte de dialogue Sélectionner les fonctionnalités](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Boîte de dialogue Sélectionner les fonctionnalités")</span><span class="sxs-lookup"><span data-stu-id="eec5e-121">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="eec5e-122">Ensuite, continuez à remplir les pages suivantes de l’Assistant : **Noms de domaine complets externes**, **Définir l’adresse IP interne** et **Définir l’adresse IP externe**.</span><span class="sxs-lookup"><span data-stu-id="eec5e-122">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="eec5e-123">Sur la page **définir le tronçon suivant** , sélectionnez le directeur pour le tronçon suivant du pool de serveurs Edge Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="eec5e-123">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="eec5e-124">![Boîte de dialogue définir le tronçon suivant](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Boîte de dialogue définir le tronçon suivant")</span><span class="sxs-lookup"><span data-stu-id="eec5e-124">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="eec5e-125">Dans la page **associer des pools frontaux ou des pools de médiation** , n’associez pas un pool à ce pool Edge pour le moment.</span><span class="sxs-lookup"><span data-stu-id="eec5e-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="eec5e-126">Le trafic multimédia externe est actuellement routé via le serveur Edge Lync Server 2010 hérité.</span><span class="sxs-lookup"><span data-stu-id="eec5e-126">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="eec5e-127">Ce paramètre sera configuré lors d’une phase ultérieure de la migration.</span><span class="sxs-lookup"><span data-stu-id="eec5e-127">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="eec5e-128">![Boîte de dialogue pools frontaux associés](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Boîte de dialogue pools frontaux associés")</span><span class="sxs-lookup"><span data-stu-id="eec5e-128">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="eec5e-129">Cliquez sur **Terminer**, puis sur **Publier** pour publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="eec5e-129">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="eec5e-130">Suivez les étapes décrites dans [install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur Edge, configurer les certificats et démarrer les services.</span><span class="sxs-lookup"><span data-stu-id="eec5e-130">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="eec5e-131">Il est très important de suivre les instructions des rubriques déploiement de l' [accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="eec5e-131">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="eec5e-132">Cette section ne fait que fournir des recommandations concernant les paramètres de configuration lors de l’installation de ces rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="eec5e-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="eec5e-133">Vous devez maintenant disposer d’un serveur Edge Lync Server 2010 hérité déployé en parallèle avec un déploiement de serveur Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eec5e-133">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="eec5e-134">Vérifiez que les deux déploiements fonctionnent correctement, que les services ont démarré et que vous pouvez administrer chaque déploiement avant de passer à la phase suivante.</span><span class="sxs-lookup"><span data-stu-id="eec5e-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

