---
title: 'Lync Server 2013 : gestion de l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server 2013 Archiving
ms:assetid: 48c6cc8c-c2c1-4534-9a8a-fd5eb738076a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520990(v=OCS.15)
ms:contentKeyID: 48184003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16c9b901575e844954b9dd3454c4ecc7c86e7c3b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-archiving"></a><span data-ttu-id="9722b-102">Gestion de l’archivage Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9722b-102">Managing Lync Server 2013 Archiving</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9722b-103">_**Dernière modification de la rubrique :** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="9722b-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="9722b-104">Lorsque vous déployez l’archivage pour votre organisation, vous spécifiez la configuration initiale lors du déploiement.</span><span class="sxs-lookup"><span data-stu-id="9722b-104">When you deploy Archiving for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="9722b-105">Toutefois, il peut arriver que vous souhaitiez modifier la façon dont vous implémentez la prise en charge de l’archivage pour la gestion quotidienne ou pour répondre aux nouvelles exigences de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="9722b-105">However, there may be times when you want to change how you implement archiving support for day-to-day management or to meet new requirements in your organization.</span></span> <span data-ttu-id="9722b-106">Par exemple, il se peut que vous deviez configurer la prise en charge de l’archivage différemment pour un site, un pool ou des utilisateurs spécifiques au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="9722b-106">For example, you may need to set up archiving support differently for a specific site, pool, or users within your organization.</span></span> <span data-ttu-id="9722b-107">Pour les utilisateurs hébergés sur Lync Server 2013, vous créez et personnalisez des stratégies et des configurations d’archivage.</span><span class="sxs-lookup"><span data-stu-id="9722b-107">For users homed on Lync Server 2013, you do this be creating and customizing archiving policies and configurations.</span></span> <span data-ttu-id="9722b-108">Si vous utilisez l’intégration de Microsoft Exchange, vous devez également configurer les paramètres Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="9722b-108">If you use Microsoft Exchange integration, you must also configure Exchange 2013 settings.</span></span> <span data-ttu-id="9722b-109">Cette section fournit des informations et des procédures pour vous permettre d’effectuer des modifications dans votre déploiement de l’archivage.</span><span class="sxs-lookup"><span data-stu-id="9722b-109">This section provides information and procedures to enable you to make changes to your Archiving deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9722b-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="9722b-110">In This Section</span></span>

  - [<span data-ttu-id="9722b-111">Fonctionnement de l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9722b-111">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="9722b-112">Gestion de l’archivage des communications internes et externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9722b-112">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

  - [<span data-ttu-id="9722b-113">Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools</span><span class="sxs-lookup"><span data-stu-id="9722b-113">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

  - [<span data-ttu-id="9722b-114">Modification des options de base de données d’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9722b-114">Changing Archiving database options in Lync Server 2013</span></span>](lync-server-2013-changing-archiving-database-options.md)

  - [<span data-ttu-id="9722b-115">Exportation de données archivées à partir de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9722b-115">Exporting archived data from Lync Server 2013</span></span>](lync-server-2013-exporting-archived-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

