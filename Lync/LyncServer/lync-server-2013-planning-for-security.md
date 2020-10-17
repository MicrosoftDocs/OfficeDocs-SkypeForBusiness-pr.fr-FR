---
title: 'Lync Server 2013 : planification de la sécurité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for security
ms:assetid: 17eeba87-cafa-4e9b-852d-c017a7d10d59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342827(v=OCS.15)
ms:contentKeyID: 56107267
ms.date: 06/22/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f99fbd5e511063d7687dbb9e1b9a73fa0cb6ab6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507001"
---
# <a name="planning-for-security-in-lync-server-2013"></a><span data-ttu-id="1a1be-102">Planification de la sécurité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a1be-102">Planning for security in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a1be-103">_**Dernière modification de la rubrique :** 2016-06-22_</span><span class="sxs-lookup"><span data-stu-id="1a1be-103">_**Topic Last Modified:** 2016-06-22_</span></span>

<span data-ttu-id="1a1be-104">Utilisez cette section sécurité pour évaluer et gérer les risques de sécurité pour votre déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a1be-104">Use this security section to assess and manage security risks to your deployment of Lync Server 2013.</span></span>

<span data-ttu-id="1a1be-105">Même si votre déploiement Lync Server 2013 est modeste, les composants de votre réseau disposent probablement de leur propre documentation de sécurité.</span><span class="sxs-lookup"><span data-stu-id="1a1be-105">Even if your Lync Server 2013 deployment is modest, you probably have components in your network that have their own security documentation.</span></span> <span data-ttu-id="1a1be-106">Par conséquent, il est peu probable que cette section traite de tous les aspects de la sécurité pour tous les composants et les zones pertinents pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="1a1be-106">Therefore, it is unlikely that this section covers all aspects of security for all components and areas that are pertinent to your deployment.</span></span>

<span data-ttu-id="1a1be-107">Utilisez cette section comme point de départ pour gérer la sécurité de votre déploiement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a1be-107">Use this section as a starting point to address the security of your Lync Server 2013 deployment.</span></span> <span data-ttu-id="1a1be-108">Il fournit des instructions générales et les meilleures pratiques pour évaluer et gérer les risques de sécurité les plus courants.</span><span class="sxs-lookup"><span data-stu-id="1a1be-108">It provides general guidelines and best practices for assessing and managing the most common security risks.</span></span> <span data-ttu-id="1a1be-109">Des ressources de produit et de sécurité supplémentaires sont répertoriées à la fin de chaque rubrique.</span><span class="sxs-lookup"><span data-stu-id="1a1be-109">Additional product and security resources are listed at the end of each topic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1a1be-110">La sécurité est un sujet en perpétuelle évolution.</span><span class="sxs-lookup"><span data-stu-id="1a1be-110">Security is a constantly evolving topic.</span></span> <span data-ttu-id="1a1be-111">À mesure que de nouvelles menaces et solutions se posent, des documents, des solutions, des méthodes et des procédures obsolètes doivent être remplacés par des documents à jour.</span><span class="sxs-lookup"><span data-stu-id="1a1be-111">As new threats and solutions arise, outdated documents, solutions, methods, and procedures should be replaced with up-to-date material.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1a1be-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="1a1be-112">In This Section</span></span>

  - [<span data-ttu-id="1a1be-113">Principales fonctionnalités de sécurité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a1be-113">Key security features in Lync Server 2013</span></span>](lync-server-2013-key-security-features.md)

  - [<span data-ttu-id="1a1be-114">Menaces de sécurité courantes lors de l’informatique moderne</span><span class="sxs-lookup"><span data-stu-id="1a1be-114">Common security threats in modern day computing</span></span>](lync-server-2013-common-security-threats-in-modern-day-computing.md)

  - [<span data-ttu-id="1a1be-115">Exclusions d’analyse antivirus pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a1be-115">Antivirus scanning exclusions for Lync Server 2013</span></span>](lync-server-2013-antivirus-scanning-exclusions.md)

  - [<span data-ttu-id="1a1be-116">Infrastructure de sécurité pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a1be-116">Security framework for Lync Server 2013</span></span>](lync-server-2013-security-framework-for-lync-server.md)

  - [<span data-ttu-id="1a1be-117">Résolution des menaces pesant sur votre infrastructure de base pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a1be-117">Addressing threats to your core infrastructure for Lync Server 2013</span></span>](lync-server-2013-addressing-threats-to-your-core-infrastructure.md)

  - [<span data-ttu-id="1a1be-118">Déploiement d’un port et d’un alias SQL Server non standard dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a1be-118">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>](deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

