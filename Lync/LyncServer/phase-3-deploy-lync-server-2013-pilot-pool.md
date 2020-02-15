---
title: 'Phase 3 : déployer le pool pilote Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Phase 3: Deploy Lync Server 2013 pilot pool'
ms:assetid: f12b1517-fb56-4ded-8323-57aa9fc9ea48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205367(v=OCS.15)
ms:contentKeyID: 48185778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c87be6f690c5c31822dd59bea52c9140e43a4926
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-3-deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="a2c78-102">Phase 3 : déployer le pool pilote Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2c78-102">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2c78-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a2c78-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a2c78-104">Cette section décrit les étapes nécessaires au déploiement d’un pool pilote de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a2c78-104">This section covers the steps required to deploy a pilot pool of Lync Server 2013.</span></span> <span data-ttu-id="a2c78-105">Le déploiement de Lync Server 2013 nécessite l’utilisation du générateur de topologie pour définir votre topologie et les composants que vous souhaitez déployer, la préparation de votre environnement au déploiement des composants Lync Server 2013, la publication de votre conception de topologie sur le premier serveur frontal Serveur, puis installation et configuration du logiciel Lync Server 2013 pour les composants de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="a2c78-105">The deployment of Lync Server 2013 requires using Topology Builder to define your topology and the components you want to deploy, preparing your environment for deployment of the Lync Server 2013 components, publishing your topology design on the first Front End Server, and then installing and configuring Lync Server 2013 software for the components for your deployment.</span></span> <span data-ttu-id="a2c78-106">Lorsque vous avez terminé, votre déploiement de pool pilote Lync Server 2013 coexiste avec un pool Lync Server 2010 existant.</span><span class="sxs-lookup"><span data-stu-id="a2c78-106">When completed, your Lync Server 2013 pilot pool deployment will coexist with an existing Lync Server 2010 pool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a2c78-107">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="a2c78-107">In This Section</span></span>

  - [<span data-ttu-id="a2c78-108">Préparation d’Active Directory pour Lync Server</span><span class="sxs-lookup"><span data-stu-id="a2c78-108">Prepare Active Directory for Lync Server</span></span>](prepare-active-directory-for-lync-server.md)

  - [<span data-ttu-id="a2c78-109">Télécharger la topologie à partir d’un déploiement existant</span><span class="sxs-lookup"><span data-stu-id="a2c78-109">Download topology from existing deployment</span></span>](download-topology-from-existing-deployment.md)

  - [<span data-ttu-id="a2c78-110">Déployer le pool pilote Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2c78-110">Deploy Lync Server 2013 pilot pool</span></span>](deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="a2c78-111">Vérifier la coexistence du pool pilote avec le pool hérité</span><span class="sxs-lookup"><span data-stu-id="a2c78-111">Verify pilot pool coexistence with legacy pool</span></span>](verify-pilot-pool-coexistence-with-legacy-pool.md)

  - [<span data-ttu-id="a2c78-112">Connecter le pool pilote aux serveurs Edge hérités</span><span class="sxs-lookup"><span data-stu-id="a2c78-112">Connect pilot pool to legacy Edge Servers</span></span>](connect-pilot-pool-to-legacy-edge-servers.md)

  - [<span data-ttu-id="a2c78-113">Configuration des certificats et des stratégies d’accès à la passerelle XMPP</span><span class="sxs-lookup"><span data-stu-id="a2c78-113">Configure XMPP gateway access policies and certificates</span></span>](configure-xmpp-gateway-access-policies-and-certificates.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

