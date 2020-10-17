---
title: 'Lync Server 2013 : déploiement de l’archivage'
description: 'Lync Server 2013 : déploiement de l’archivage.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Archiving
ms:assetid: a89edd16-12d5-4602-ad2f-194b47d1188e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205147(v=OCS.15)
ms:contentKeyID: 48185031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4ba38b7dcde0c72469e361f59ade7cb7f6ebb53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558500"
---
# <a name="deploying-archiving-in-lync-server-2013"></a><span data-ttu-id="301fe-103">Déploiement de l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="301fe-103">Deploying Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="301fe-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="301fe-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="301fe-105">Lync Server 2013 fournit une solution pour l’archivage du contenu de messagerie instantanée et des communications de conférence dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="301fe-105">Lync Server 2013 provides a solution for archiving instant messaging (IM) content and conferencing communications in Lync Server.</span></span> <span data-ttu-id="301fe-106">Vous pouvez implémenter la prise en charge de l’archivage en intégrant le stockage d’archivage avec le stockage Exchange 2013, en utilisant les bases de données SQL Server pour le stockage des données d’archivage Lync Server 2013 ou en utilisant Lync Server 2013 et Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="301fe-106">You can implement archiving support by integrating archiving storage with Exchange 2013 storage, by using SQL Server databases for storage of Lync Server 2013 archiving data, or by using both Lync Server 2013 and Exchange 2013 storage.</span></span> <span data-ttu-id="301fe-107">Le contrôle de l’archivage des données s’effectue à l’aide de stratégies et de configurations d’archivage.</span><span class="sxs-lookup"><span data-stu-id="301fe-107">You control how data is archived using policies and archiving configurations.</span></span> <span data-ttu-id="301fe-108">Pour plus d’informations, reportez-vous à la rubrique [planification de l’archivage dans Lync server 2013](lync-server-2013-planning-for-archiving.md) dans la documentation de planification et fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="301fe-108">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation and [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<span data-ttu-id="301fe-109">Vous pouvez utiliser les informations de cette section pour procéder à la configuration initiale de l’archivage.</span><span class="sxs-lookup"><span data-stu-id="301fe-109">You can use the information in this section to set up and configure Archiving initially.</span></span> <span data-ttu-id="301fe-110">Après le déploiement, vous pouvez modifier les paramètres d’archivage.</span><span class="sxs-lookup"><span data-stu-id="301fe-110">After deployment, you can change Archiving settings.</span></span> <span data-ttu-id="301fe-111">Pour plus d’informations sur la façon dont vous implémentez la prise en charge de l’archivage pour la gestion quotidienne ou pour répondre à de nouvelles exigences au sein de votre organisation, voir [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="301fe-111">For details about how you implement archiving support for day-to-day management or to meet new requirements in your organization, see [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="301fe-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="301fe-112">In This Section</span></span>

  - [<span data-ttu-id="301fe-113">Fonctionnement de l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="301fe-113">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="301fe-114">Liste de vérification du déploiement pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="301fe-114">Deployment checklist for Archiving in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-archiving.md)

  - [<span data-ttu-id="301fe-115">Configuration des systèmes et de l’infrastructure pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="301fe-115">Setting up systems and infrastructure for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md)

  - [<span data-ttu-id="301fe-116">Ajout de bases de données d’archivage à un déploiement Lync Server 2013 existant</span><span class="sxs-lookup"><span data-stu-id="301fe-116">Adding Archiving databases to an existing Lync Server 2013 Deployment</span></span>](lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md)

  - [<span data-ttu-id="301fe-117">Configuration de la prise en charge de l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="301fe-117">Configuring support for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-archiving.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

