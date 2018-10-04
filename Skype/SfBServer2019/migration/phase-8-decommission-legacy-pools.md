---
title: Phase 8 pools hérités mise hors service
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: httpsfix
description: La rubrique suivante fournit des instructions pour la mise à jour des entrées DNS, déplacement du serveur de gestion de contenu, mise hors service des pools, désactivation et suppression de serveurs et les pools d’un déploiement hérité. Toutes les procédures répertoriées dans cette section sont requis. Lisez la documentation et déterminer quelle procédure mise hors service à utiliser.
ms.openlocfilehash: 0e5c7bebeb0449f8fa71942f2ac68ff9d7eb017a
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370759"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="b001e-105">Phase 8 : Mettre hors service les pools hérités</span><span class="sxs-lookup"><span data-stu-id="b001e-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="b001e-106">La rubrique suivante fournit des instructions pour la mise à jour des entrées DNS, déplacement du serveur de gestion de contenu, mise hors service des pools, désactivation et suppression de serveurs et les pools d’un déploiement hérité.</span><span class="sxs-lookup"><span data-stu-id="b001e-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="b001e-107">Toutes les procédures répertoriées dans cette section sont requis.</span><span class="sxs-lookup"><span data-stu-id="b001e-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="b001e-108">Lisez la documentation et déterminer quelle procédure mise hors service à utiliser.</span><span class="sxs-lookup"><span data-stu-id="b001e-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="b001e-109">Pour un article daté mais exhaustif sur la suppression de serveurs et rôles de serveur et un guide pas à pas pour la mise hors service un déploiement, téléchargez [la désinstallation de Microsoft Lync Server et suppression de rôles de serveur](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="b001e-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b001e-110">Pour plus d’informations sur la migration et mise à niveau des applications Microsoft Unified Communications Managed API (UCMA), avant de désaffecter votre environnement hérité, voir [applications UCMA : scénarios de mise à niveau, migration et Coexistence](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span><span class="sxs-lookup"><span data-stu-id="b001e-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b001e-111">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="b001e-111">In this section</span></span>

> [<span data-ttu-id="b001e-112">Mettre à jour les enregistrements DNS SRV</span><span class="sxs-lookup"><span data-stu-id="b001e-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="b001e-113">Atteindre la serveur de gestion centralisée d’installation héritée Skype pour Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="b001e-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="b001e-114">Déplacement des annuaires de conférences</span><span class="sxs-lookup"><span data-stu-id="b001e-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="b001e-115">Supprimer l’association du serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="b001e-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="b001e-116">Supprimer l’association du serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="b001e-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="b001e-117">Supprimer le serveur Enterprise Edition frontaux ou le serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="b001e-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="b001e-118">Supprimer des instances de SQL Server et les bases de données sur le serveur principal</span><span class="sxs-lookup"><span data-stu-id="b001e-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

