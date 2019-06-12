---
title: 'Lync Server 2013 : Configuration des serveurs et des pools frontaux'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Front End Servers and Front End pools
ms:assetid: c88526f9-69e2-47dd-b3d7-056139d74fb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398827(v=OCS.15)
ms:contentKeyID: 48185381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab21e5933623af58834d3b9effa5ba1e2beecc43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-front-end-servers-and-front-end-pools-for-lync-server-2013"></a><span data-ttu-id="5b7f5-102">Configuration des serveurs et des pools frontaux pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b7f5-102">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b7f5-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5b7f5-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5b7f5-104">Cette section vous guide tout au long de l’installation de Lync Server 2013 et de la configuration des rôles de serveur du serveur Standard Edition et du pool frontal, y compris des serveurs frontaux et des rôles serveur colocalisés avec les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="5b7f5-104">This section guides you through installing Lync Server 2013 and setting up the server roles for the Standard Edition server and the Front End pool, including the Front End Servers and any server roles that are collocated with the Front End Servers.</span></span> <span data-ttu-id="5b7f5-105">Pour installer et configurer les rôles de serveur, vous devez exécuter l’Assistant Déploiement de Lync Server sur chaque ordinateur sur lequel vous installez un rôle de serveur.</span><span class="sxs-lookup"><span data-stu-id="5b7f5-105">To install and set up server roles, you run the Lync Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="5b7f5-106">Faites appel à l’Assistant Déploiement pour exécuter les quatre étapes du déploiement que sont l’installation du magasin de configurations local, l’installation des serveurs frontaux, la configuration des certificats et le démarrage des services.</span><span class="sxs-lookup"><span data-stu-id="5b7f5-106">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5b7f5-107">Pour pouvoir configurer les rôles de serveurs, vous devez avoir correctement publié une topologie.</span><span class="sxs-lookup"><span data-stu-id="5b7f5-107">Before you can set up server roles, you must have successfully published a topology.</span></span> <span data-ttu-id="5b7f5-108">Pour plus d’informations sur la publication d’une topologie, voir <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalisation et implémentation de la conception topologique dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5b7f5-108">For details about publishing a topology, see <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing and implementing the topology design in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5b7f5-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="5b7f5-109">In This Section</span></span>

  - [<span data-ttu-id="5b7f5-110">Installation du magasin de configurations local dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b7f5-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="5b7f5-111">Installation des composants serveur pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b7f5-111">Install server components for Lync Server 2013</span></span>](lync-server-2013-install-lync-server-server-components.md)

  - [<span data-ttu-id="5b7f5-112">Configuration des certificats pour les serveurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b7f5-112">Configure certificates for servers in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-servers.md)

  - [<span data-ttu-id="5b7f5-113">Démarrer des services sur les serveurs pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b7f5-113">Start services on servers for Lync Server 2013</span></span>](lync-server-2013-start-services-on-servers.md)

  - [<span data-ttu-id="5b7f5-114">Test du déploiement du pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b7f5-114">Test the pool deployment in Lync Server 2013</span></span>](lync-server-2013-test-the-pool-deployment.md)

  - [<span data-ttu-id="5b7f5-115">Test du serveur Standard Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b7f5-115">Test the Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-test-the-standard-edition-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

