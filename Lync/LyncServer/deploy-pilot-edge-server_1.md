---
title: Déploiement d’un serveur Edge pilote
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
ms.openlocfilehash: 686973f9334b9bf376a2e56c52f3306cf243c0eb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="3ef59-102">Déploiement d’un serveur Edge pilote</span><span class="sxs-lookup"><span data-stu-id="3ef59-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ef59-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3ef59-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3ef59-104">Cette rubrique présente les paramètres de configuration que vous devez prendre en compte avant de déployer votre serveur Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ef59-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="3ef59-105">Cette section présente uniquement les points clés à prendre en compte dans le cadre de votre déploiement de pool de périphériques pilote.</span><span class="sxs-lookup"><span data-stu-id="3ef59-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="3ef59-106">Pour obtenir la procédure détaillée, consultez la rubrique déploiement d’un [accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement, qui décrit le processus de déploiement et fournit également des informations de configuration pour l’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="3ef59-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="3ef59-107">À mesure que vous parcourez l’Assistant **définir un nouveau pool de bords** , passez en revue les paramètres de configuration clés indiqués dans les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="3ef59-107">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="3ef59-108">Notez que seules quelques pages de l’Assistant **définir un nouveau pool de bords** sont affichées.</span><span class="sxs-lookup"><span data-stu-id="3ef59-108">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="3ef59-109">**Définir un pool de bords**</span><span class="sxs-lookup"><span data-stu-id="3ef59-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="3ef59-110">Ouvrez la topologie de pool pilote à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="3ef59-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="3ef59-111">Accédez au nœud Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ef59-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="3ef59-112">Cliquez avec le bouton droit sur **pools de bords**, puis cliquez sur **nouvelle liste de bord**.</span><span class="sxs-lookup"><span data-stu-id="3ef59-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="3ef59-113">![Boîte de dialogue définir la nouvelle réserve de bords](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Boîte de dialogue définir la nouvelle réserve de bords")</span><span class="sxs-lookup"><span data-stu-id="3ef59-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="3ef59-114">Un pool Edge peut être un pool d' **ordinateurs** ou un **pool d’ordinateurs unique**.</span><span class="sxs-lookup"><span data-stu-id="3ef59-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="3ef59-115">![Définir la boîte de dialogue nom de domaine complet du pool de bords](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Définir la boîte de dialogue nom de domaine complet du pool de bords")</span><span class="sxs-lookup"><span data-stu-id="3ef59-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="3ef59-116">Dans la page **Sélectionner des fonctionnalités** , n’activez pas la Fédération de Fédération ou XMPP.</span><span class="sxs-lookup"><span data-stu-id="3ef59-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="3ef59-117">La Fédération des fédérations et XMPP est actuellement routée via le serveur Edge Office Communications Server 2007 R2 hérité.</span><span class="sxs-lookup"><span data-stu-id="3ef59-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="3ef59-118">Ces fonctionnalités seront configurées lors de la phase de migration ultérieure.</span><span class="sxs-lookup"><span data-stu-id="3ef59-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="3ef59-119">![Boîte de dialogue Sélectionner les fonctionnalités](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Boîte de dialogue Sélectionner les fonctionnalités")</span><span class="sxs-lookup"><span data-stu-id="3ef59-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="3ef59-120">Continuez à compléter les pages suivantes de l’Assistant : **sélectionnez Options IP**, noms de **domaine complets externes**, **définir l’adresse IP interne**et **définir l’adresse IP externe**.</span><span class="sxs-lookup"><span data-stu-id="3ef59-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="3ef59-121">Sur la page **définir le tronçon suivant** , sélectionnez le directeur pour le tronçon suivant du pool de périphériques Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ef59-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="3ef59-122">![Boîte de dialogue définir un nouveau pool de bords, liste de pools de tronçons suivants](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Boîte de dialogue définir un nouveau pool de bords, liste de pools de tronçons suivants")</span><span class="sxs-lookup"><span data-stu-id="3ef59-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="3ef59-123">Dans la page **Associate front end pools** , n’associez pas un pool à ce pool d’arêtes pour le moment.</span><span class="sxs-lookup"><span data-stu-id="3ef59-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="3ef59-124">Le trafic de médias externes est actuellement acheminé via le serveur Edge Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3ef59-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="3ef59-125">Ce paramètre sera configuré lors de la phase de migration ultérieure.</span><span class="sxs-lookup"><span data-stu-id="3ef59-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="3ef59-126">![Boîte de dialogue définir un nouveau pool de bords](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Boîte de dialogue définir un nouveau pool de bords")</span><span class="sxs-lookup"><span data-stu-id="3ef59-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="3ef59-127">Cliquez sur **Terminer** , puis **publiez** la topologie.</span><span class="sxs-lookup"><span data-stu-id="3ef59-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="3ef59-128">Suivez les étapes décrites dans l' [article installer des serveurs Edge pour Lync Server 2013](lync-server-2013-install-edge-servers.md) dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur Edge, configurer des certificats et démarrer les services.</span><span class="sxs-lookup"><span data-stu-id="3ef59-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="3ef59-129">Il est très important de suivre les recommandations contenues dans les rubriques déploiement d’un [accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="3ef59-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="3ef59-130">Cette section fournit uniquement des recommandations en matière de paramètres de configuration lors de l’installation de ces rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="3ef59-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="3ef59-131">Pour le moment, vous devez disposer d’un déploiement d’Office Communications Server 2007 R2 d’ancienne génération, indiqué par la présence de BackCompatSite, parallèlement à un déploiement Lync Server 2013 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="3ef59-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="3ef59-132">La Fédération est configurée pour utiliser le directeur Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3ef59-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="3ef59-133">Vérifiez que les deux déploiements s’exécutent correctement, que les services sont démarrés et que vous pouvez gérer chaque déploiement avant de passer à la phase suivante.</span><span class="sxs-lookup"><span data-stu-id="3ef59-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="3ef59-134">![Générateur de topologie montrant un serveur Edge OCS](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Générateur de topologie montrant un serveur Edge OCS")</span><span class="sxs-lookup"><span data-stu-id="3ef59-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

