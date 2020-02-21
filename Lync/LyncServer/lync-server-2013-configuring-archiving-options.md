---
title: 'Lync Server 2013 : configuration des options d’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd70d2742e54da801f80b07f1a00b97e0d91a990
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a><span data-ttu-id="4e4f6-102">Configuration des options d’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e4f6-102">Configuring Archiving options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e4f6-103">_**Dernière modification de la rubrique :** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="4e4f6-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="4e4f6-104">Dans le panneau de configuration Lync Server 2013, vous utilisez des configurations d’archivage pour spécifier le mode d’implémentation de l’archivage.</span><span class="sxs-lookup"><span data-stu-id="4e4f6-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="4e4f6-105">Les configurations d’archivage sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="4e4f6-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="4e4f6-106">Une configuration globale qui est créée par défaut lorsque vous déployez Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e4f6-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="4e4f6-107">Configurations facultatives au niveau du site et au niveau du pool que vous pouvez créer et utiliser pour spécifier la manière d’implémenter l’archivage de sites ou de pools spécifiques.</span><span class="sxs-lookup"><span data-stu-id="4e4f6-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="4e4f6-108">Vous commencez par définir des configurations d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations à l’issue du déploiement.</span><span class="sxs-lookup"><span data-stu-id="4e4f6-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="4e4f6-109">Dans le panneau de configuration Lync Server 2013, vous pouvez utiliser la page Configuration de l' **archivage** du groupe **archivage et surveillance** pour gérer les configurations au niveau global, au niveau du site et au niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="4e4f6-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="4e4f6-110">Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="4e4f6-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="4e4f6-111">Pour plus d’informations sur la gestion des configurations après le déploiement, voir [Managing Archiving configuration options in Lync Server 2013 for Your Organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="4e4f6-111">For details about how to manage configurations after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e4f6-112">Pour utiliser l’archivage, vous devez configurer des stratégies d’archivage pour spécifier s’il faut activer l’archivage pour les communications internes, pour les communications externes ou pour les deux pour les utilisateurs hébergés sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e4f6-112">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="4e4f6-113">Par défaut, l’archivage n’est pas activé pour les communications internes ou externes.</span><span class="sxs-lookup"><span data-stu-id="4e4f6-113">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="4e4f6-114">Avant d’activer l’archivage dans des stratégies, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, éventuellement, pour des sites et pools spécifiques, comme décrit dans cette section.</span><span class="sxs-lookup"><span data-stu-id="4e4f6-114">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="4e4f6-115">Pour plus d’informations sur l’activation de l’archivage, voir <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving Policies in Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="4e4f6-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="4e4f6-116">Si vous n’utilisez pas l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous devez configurer des stratégies d’archivage pour spécifier s’il faut activer l’archivage pour les communications internes, pour les communications externes ou pour les deux.</span><span class="sxs-lookup"><span data-stu-id="4e4f6-116">If you do not use Microsoft Exchange integration for all users in your deployment, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="4e4f6-117">Par défaut, l’archivage n’est pas activé pour les communications internes ou externes pour l’archivage des données lors de l’utilisation des bases de données d’archivage Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e4f6-117">By default, archiving is not enabled for either internal or external communications for archiving of data when using Lync Server 2013 Archiving databases.</span></span> <span data-ttu-id="4e4f6-118">Avant d’activer l’archivage dans des stratégies, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, éventuellement, pour des sites et pools spécifiques, comme décrit dans la section.</span><span class="sxs-lookup"><span data-stu-id="4e4f6-118">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="4e4f6-119">Pour plus d’informations sur l’activation de l’archivage pour une utilisation avec les bases de données d’archivage de Lync Server 2013, reportez-vous à la rubrique <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configuration et affectation de stratégies d’archivage dans Lync server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="4e4f6-119">For details about enabling Archiving for use with Lync Server 2013 Archiving databases, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4e4f6-120">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="4e4f6-120">In This Section</span></span>

  - [<span data-ttu-id="4e4f6-121">Configuration des options d’archivage au niveau global dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e4f6-121">Configuring Archiving options at the global level in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [<span data-ttu-id="4e4f6-122">Configuration des options d’archivage pour un site dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e4f6-122">Configuring Archiving options for a site in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [<span data-ttu-id="4e4f6-123">Configuration des options d’archivage pour un pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e4f6-123">Configuring Archiving options for a pool in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

