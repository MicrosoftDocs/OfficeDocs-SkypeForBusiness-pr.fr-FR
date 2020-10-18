---
title: 'Lync Server 2013 : configuration de serveurs frontaux et de pools frontaux'
description: 'Lync Server 2013 : configuration de serveurs frontaux et de pools frontaux.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Front End Servers and Front End pools
ms:assetid: c88526f9-69e2-47dd-b3d7-056139d74fb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398827(v=OCS.15)
ms:contentKeyID: 48185381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d746bf342f6937c068e32caddd484b708a123910
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577240"
---
# <a name="setting-up-front-end-servers-and-front-end-pools-for-lync-server-2013"></a><span data-ttu-id="7e40a-103">Configuration de serveurs frontaux et de pools frontaux pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e40a-103">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e40a-104">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7e40a-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7e40a-105">Cette section vous guide tout au long de l’installation de Lync Server 2013 et de la configuration des rôles de serveur pour le serveur Standard Edition et le pool frontal, y compris les serveurs frontaux et les rôles de serveur qui sont colocalisés avec les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="7e40a-105">This section guides you through installing Lync Server 2013 and setting up the server roles for the Standard Edition server and the Front End pool, including the Front End Servers and any server roles that are collocated with the Front End Servers.</span></span> <span data-ttu-id="7e40a-106">Pour installer et configurer les rôles serveur, exécutez l’Assistant Déploiement de Lync Server sur chaque ordinateur sur lequel vous installez un rôle serveur.</span><span class="sxs-lookup"><span data-stu-id="7e40a-106">To install and set up server roles, you run the Lync Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="7e40a-107">L’Assistant déploiement vous permet d’effectuer les quatre étapes de déploiement, notamment l’installation du magasin de configurations local, l’installation des serveurs frontaux, la configuration des certificats et le démarrage des services.</span><span class="sxs-lookup"><span data-stu-id="7e40a-107">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7e40a-108">Avant de pouvoir configurer les rôles serveur, vous devez avoir réussi la publication d’une topologie.</span><span class="sxs-lookup"><span data-stu-id="7e40a-108">Before you can set up server roles, you must have successfully published a topology.</span></span> <span data-ttu-id="7e40a-109">Pour plus d’informations sur la publication d’une topologie, reportez-vous à <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">la section finalisation et implémentation de la conception de la topologie dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7e40a-109">For details about publishing a topology, see <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing and implementing the topology design in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7e40a-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="7e40a-110">In This Section</span></span>

  - [<span data-ttu-id="7e40a-111">Installer le magasin de configurations local dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e40a-111">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="7e40a-112">Installer les composants serveur pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e40a-112">Install server components for Lync Server 2013</span></span>](lync-server-2013-install-lync-server-server-components.md)

  - [<span data-ttu-id="7e40a-113">Configurer des certificats pour les serveurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e40a-113">Configure certificates for servers in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-servers.md)

  - [<span data-ttu-id="7e40a-114">Démarrer des services sur des serveurs pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e40a-114">Start services on servers for Lync Server 2013</span></span>](lync-server-2013-start-services-on-servers.md)

  - [<span data-ttu-id="7e40a-115">Test du déploiement du pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e40a-115">Test the pool deployment in Lync Server 2013</span></span>](lync-server-2013-test-the-pool-deployment.md)

  - [<span data-ttu-id="7e40a-116">Test du serveur Standard Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e40a-116">Test the Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-test-the-standard-edition-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

