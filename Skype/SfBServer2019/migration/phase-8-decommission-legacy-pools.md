---
title: Réserves léguées en phase 8
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: httpsfix
description: La rubrique suivante fournit des recommandations pour la mise à jour des entrées DNS, le déplacement de pools, la désaffectation de pools, la désactivation et la suppression de serveurs et de pools à partir d’un déploiement hérité. Toutes les procédures indiquées dans cette section ne sont pas obligatoires. Lisez la documentation et déterminez la procédure de désactivation à utiliser.
ms.openlocfilehash: 5edad470bcd7bcf0340a311a890f73ef01645138
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236995"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="d1448-105">Étape 8 : Mettre des pools hérités hors service</span><span class="sxs-lookup"><span data-stu-id="d1448-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="d1448-106">La rubrique suivante fournit des recommandations pour la mise à jour des entrées DNS, le déplacement de pools, la désaffectation de pools, la désactivation et la suppression de serveurs et de pools à partir d’un déploiement hérité.</span><span class="sxs-lookup"><span data-stu-id="d1448-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="d1448-107">Toutes les procédures indiquées dans cette section ne sont pas obligatoires.</span><span class="sxs-lookup"><span data-stu-id="d1448-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="d1448-108">Lisez la documentation et déterminez la procédure de désactivation à utiliser.</span><span class="sxs-lookup"><span data-stu-id="d1448-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="d1448-109">Pour obtenir un article daté d’une présentation détaillée lors de la suppression de serveurs et de rôles de serveur, et d’un guide pas à pas permettant de désaffecter un déploiement, téléchargez la désinstallation de [Microsoft Lync Server et la suppression des rôles de serveur](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="d1448-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d1448-110">Pour plus d’informations sur la migration et la mise à niveau des applications d’API managées Microsoft Unified Communications (UCMA), voir [applications UCMA: scénarios de coexistence, de migration et de mise à niveau](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span><span class="sxs-lookup"><span data-stu-id="d1448-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="d1448-111">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="d1448-111">In this section</span></span>

> [<span data-ttu-id="d1448-112">Mettre à jour les enregistrements SRV DNS</span><span class="sxs-lookup"><span data-stu-id="d1448-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="d1448-113">Déplacer le serveur de gestion centralisé d’installation hérité vers Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="d1448-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="d1448-114">Déplacement des annuaires de conférences</span><span class="sxs-lookup"><span data-stu-id="d1448-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="d1448-115">Supprimer l’association au serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="d1448-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="d1448-116">Supprimer l’association au serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="d1448-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="d1448-117">Suppression du serveur frontal Enterprise Edition ou du serveur frontal Standard Edition</span><span class="sxs-lookup"><span data-stu-id="d1448-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="d1448-118">Suppression des instances et des bases de données SQL Server sur le serveur principal</span><span class="sxs-lookup"><span data-stu-id="d1448-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

