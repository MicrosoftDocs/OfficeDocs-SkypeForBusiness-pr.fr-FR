---
title: 'Lync Server 2013 : Déploiement de l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Archiving
ms:assetid: a89edd16-12d5-4602-ad2f-194b47d1188e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205147(v=OCS.15)
ms:contentKeyID: 48185031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2e9373cf49a84110c3a8b70f20dd31072a171b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-archiving-in-lync-server-2013"></a><span data-ttu-id="bd97c-102">Déploiement de l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd97c-102">Deploying Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd97c-103">_**Dernière modification de la rubrique:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="bd97c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="bd97c-104">Lync Server 2013 fournit une solution pour l’archivage de contenu de messagerie instantanée et de communications de conférence dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bd97c-104">Lync Server 2013 provides a solution for archiving instant messaging (IM) content and conferencing communications in Lync Server.</span></span> <span data-ttu-id="bd97c-105">Pour mettre en œuvre la prise en charge de l’archivage, il est possible d’intégrer la prise en charge de l’archivage au stockage Exchange 2013, en utilisant les bases de données SQL Server pour le stockage des données d’archivage de Lync Server 2013, ou à l’aide de Lync Server 2013 et du stockage 2013 Exchange</span><span class="sxs-lookup"><span data-stu-id="bd97c-105">You can implement archiving support by integrating archiving storage with Exchange 2013 storage, by using SQL Server databases for storage of Lync Server 2013 archiving data, or by using both Lync Server 2013 and Exchange 2013 storage.</span></span> <span data-ttu-id="bd97c-106">Vous contrôlez le mode d’archivage des données à l’aide de stratégies et de configurations d’archivage.</span><span class="sxs-lookup"><span data-stu-id="bd97c-106">You control how data is archived using policies and archiving configurations.</span></span> <span data-ttu-id="bd97c-107">Pour plus d’informations, reportez-vous à la rubrique [planification de l’archivage dans Lync server 2013](lync-server-2013-planning-for-archiving.md) dans la documentation de planification et fonctionnement de l' [archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou les opérations.</span><span class="sxs-lookup"><span data-stu-id="bd97c-107">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation and [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<span data-ttu-id="bd97c-108">Vous pouvez utiliser les informations de cette section pour configurer et configurer l’archivage au départ.</span><span class="sxs-lookup"><span data-stu-id="bd97c-108">You can use the information in this section to set up and configure Archiving initially.</span></span> <span data-ttu-id="bd97c-109">Après le déploiement, vous pouvez modifier les paramètres d’archivage.</span><span class="sxs-lookup"><span data-stu-id="bd97c-109">After deployment, you can change Archiving settings.</span></span> <span data-ttu-id="bd97c-110">Pour plus d’informations sur l’implémentation de la prise en charge de l’archivage pour la gestion quotidienne ou pour répondre à de nouvelles exigences au sein de votre organisation, reportez-vous à la rubrique gestion de l' [archivage Lync Server 2013](lync-server-2013-managing-archiving.md) dans la documentation sur les opérations.</span><span class="sxs-lookup"><span data-stu-id="bd97c-110">For details about how you implement archiving support for day-to-day management or to meet new requirements in your organization, see [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bd97c-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="bd97c-111">In This Section</span></span>

  - [<span data-ttu-id="bd97c-112">Fonctionnement de l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd97c-112">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="bd97c-113">Liste de vérification du déploiement pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd97c-113">Deployment checklist for Archiving in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-archiving.md)

  - [<span data-ttu-id="bd97c-114">Configuration de systèmes et d’infrastructure pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd97c-114">Setting up systems and infrastructure for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md)

  - [<span data-ttu-id="bd97c-115">Ajouter des bases de données d’archivage à un déploiement de Lync Server 2013 existant</span><span class="sxs-lookup"><span data-stu-id="bd97c-115">Adding Archiving databases to an existing Lync Server 2013 Deployment</span></span>](lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md)

  - [<span data-ttu-id="bd97c-116">Configuration de la prise en charge de l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd97c-116">Configuring support for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-archiving.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

