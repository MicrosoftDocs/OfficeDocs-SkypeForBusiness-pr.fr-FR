---
title: Déploiement d’un serveur Edge pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd8fddd611422562c9384a52748623623d4e6f68
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="b940f-102">Déploiement d’un serveur Edge pilote</span><span class="sxs-lookup"><span data-stu-id="b940f-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b940f-103">_**Dernière modification de la rubrique:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b940f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b940f-104">Cette rubrique présente les paramètres de configuration que vous devez prendre en compte avant de déployer votre serveur Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b940f-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="b940f-105">Les processus de déploiement et de configuration de Lync Server 2013 sont similaires à Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b940f-105">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="b940f-106">Cette section présente uniquement les points clés à prendre en compte dans le cadre de votre déploiement de pool pilote.</span><span class="sxs-lookup"><span data-stu-id="b940f-106">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="b940f-107">Pour obtenir la procédure détaillée, consultez la rubrique déploiement d’un [accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement, qui décrit le processus de déploiement et fournit également des informations de configuration pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="b940f-107">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="b940f-108">À mesure que vous parcourez l’Assistant **définir un nouveau pool de bords** , passez en revue les paramètres de configuration clés indiqués dans les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="b940f-108">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="b940f-109">Notez que seules quelques pages de l’Assistant **définir un nouveau pool de bords** sont affichées.</span><span class="sxs-lookup"><span data-stu-id="b940f-109">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="b940f-110">**Définir un pool de bords**</span><span class="sxs-lookup"><span data-stu-id="b940f-110">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="b940f-111">Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b940f-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="b940f-112">Accédez au nœud Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b940f-112">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="b940f-113">Cliquez avec le bouton droit sur pools de **bords**, puis cliquez sur **nouvelle liste de bord**.</span><span class="sxs-lookup"><span data-stu-id="b940f-113">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="b940f-114">![Boîte de dialogue définir la nouvelle réserve de bords] (images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Boîte de dialogue définir la nouvelle réserve de bords")</span><span class="sxs-lookup"><span data-stu-id="b940f-114">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="b940f-115">Un pool Edge peut être un pool d' **ordinateurs** ou un **pool d’ordinateurs unique**.</span><span class="sxs-lookup"><span data-stu-id="b940f-115">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="b940f-116">![Définir la boîte de dialogue nom de domaine complet du pool de bords] (images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Définir la boîte de dialogue nom de domaine complet du pool de bords")</span><span class="sxs-lookup"><span data-stu-id="b940f-116">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="b940f-117">Dans la page **Sélectionner des fonctionnalités** , n’activez pas la Fédération de Fédération ou XMPP.</span><span class="sxs-lookup"><span data-stu-id="b940f-117">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="b940f-118">Les fédérations de Fédération et XMPP sont actuellement routées via le serveur Edge Lync Server 2010 hérité.</span><span class="sxs-lookup"><span data-stu-id="b940f-118">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="b940f-119">Ces fonctionnalités seront configurées lors de la phase de migration ultérieure.</span><span class="sxs-lookup"><span data-stu-id="b940f-119">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="b940f-120">![Boîte de dialogue Sélectionner les fonctionnalités] (images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Boîte de dialogue Sélectionner les fonctionnalités")</span><span class="sxs-lookup"><span data-stu-id="b940f-120">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="b940f-121">Continuez à remplir les pages suivantes de l’Assistant: noms de **domaine complets externes**, **définir l’adresse IP interne**et **définir l’adresse IP externe**.</span><span class="sxs-lookup"><span data-stu-id="b940f-121">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="b940f-122">Sur la page **définir le tronçon suivant** , sélectionnez le directeur pour le tronçon suivant du pool de périphériques Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b940f-122">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="b940f-123">![Boîte de dialogue définir le saut suivant] (images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Boîte de dialogue définir le saut suivant")</span><span class="sxs-lookup"><span data-stu-id="b940f-123">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="b940f-124">Dans la page **Associate front end ou pools de médiation** , n’associez pas un pool à ce pool d’arêtes pour le moment.</span><span class="sxs-lookup"><span data-stu-id="b940f-124">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="b940f-125">Le trafic de médias externes est actuellement acheminé via le serveur Edge Lync Server 2010 hérité.</span><span class="sxs-lookup"><span data-stu-id="b940f-125">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="b940f-126">Ce paramètre sera configuré lors de la phase de migration ultérieure.</span><span class="sxs-lookup"><span data-stu-id="b940f-126">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="b940f-127">![Boîte de dialogue Associate] (images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Boîte de dialogue Associate")</span><span class="sxs-lookup"><span data-stu-id="b940f-127">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="b940f-128">Cliquez sur **Terminer** , puis **publiez** la topologie.</span><span class="sxs-lookup"><span data-stu-id="b940f-128">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="b940f-129">Suivez les étapes décrites dans l' [article installer des serveurs Edge pour Lync Server 2013](lync-server-2013-install-edge-servers.md) dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur Edge, configurer des certificats et démarrer les services.</span><span class="sxs-lookup"><span data-stu-id="b940f-129">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="b940f-130">Il est très important de suivre les recommandations contenues dans les rubriques déploiement d’un [accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b940f-130">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="b940f-131">Cette section fournit uniquement des recommandations en matière de paramètres de configuration lors de l’installation de ces rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="b940f-131">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="b940f-132">Vous devez maintenant disposer d’un serveur Edge Lync Server 2010 hérité déployé en parallèle avec un déploiement de serveur Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b940f-132">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="b940f-133">Vérifiez que les deux déploiements s’exécutent correctement, que les services sont démarrés et que vous pouvez gérer chaque déploiement avant de passer à la phase suivante.</span><span class="sxs-lookup"><span data-stu-id="b940f-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

