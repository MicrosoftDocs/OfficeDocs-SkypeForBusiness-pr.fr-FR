---
title: Phase 8 Désaffecter les pools hérités
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: httpsfix
description: La rubrique suivante fournit des conseils pour la mise à jour des entrées DNS, le déplacement du serveur de gestion de contenu, la désaffectation des pools et la désactivation et la suppression de serveurs et de pools d’un déploiement hérité. Certaines des procédures répertoriées dans cette section ne sont pas requises. Lisez la documentation pour déterminer la procédure de mise hors service à utiliser.
ms.openlocfilehash: b1080c68e3b4075ce92aaef497854855135dc47d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113240"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="dcb8f-105">Étape 8 : Mettre des pools hérités hors service</span><span class="sxs-lookup"><span data-stu-id="dcb8f-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="dcb8f-106">La rubrique suivante fournit des conseils pour la mise à jour des entrées DNS, le déplacement du serveur de gestion de contenu, la mise hors service des pools et la désactivation et la suppression de serveurs et de pools d’un déploiement hérité.</span><span class="sxs-lookup"><span data-stu-id="dcb8f-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="dcb8f-107">Certaines des procédures répertoriées dans cette section ne sont pas requises.</span><span class="sxs-lookup"><span data-stu-id="dcb8f-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="dcb8f-108">Lisez la documentation pour déterminer la procédure de mise hors service à utiliser.</span><span class="sxs-lookup"><span data-stu-id="dcb8f-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="dcb8f-109">Pour obtenir un article obsolète mais exhaustif sur la suppression des serveurs et des rôles serveur, et un guide pas à pas pour la désaffectation d’un déploiement, téléchargez [Désinstallation de Microsoft Lync Server](https://go.microsoft.com/fwlink/p/?linkId=246227)et suppression des rôles serveur.</span><span class="sxs-lookup"><span data-stu-id="dcb8f-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="dcb8f-110">Pour plus d’informations sur la migration et la mise à niveau des applications UCMA (Unified Communications Managed API), avant de désaffecter votre environnement hérité, voir applications UCMA : scénarios de [coexistence, de migration](/previous-versions/office/jj728782(v=office.15))et de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="dcb8f-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](/previous-versions/office/jj728782(v=office.15)).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="dcb8f-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="dcb8f-111">In this section</span></span>

> [<span data-ttu-id="dcb8f-112">Mettre à jour les enregistrements SRV DNS</span><span class="sxs-lookup"><span data-stu-id="dcb8f-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="dcb8f-113">Déplacer l’installation héritée de Central Management Server vers Skype Entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="dcb8f-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="dcb8f-114">Déplacement des annuaires de conférences</span><span class="sxs-lookup"><span data-stu-id="dcb8f-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="dcb8f-115">Supprimer l’association au serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="dcb8f-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="dcb8f-116">Supprimer l’association au serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="dcb8f-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="dcb8f-117">Supprimer le serveur frontal Enterprise Edition ou le serveur frontal Standard Edition</span><span class="sxs-lookup"><span data-stu-id="dcb8f-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="dcb8f-118">Suppression des instances et des bases de données SQL Server sur le serveur principal</span><span class="sxs-lookup"><span data-stu-id="dcb8f-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
