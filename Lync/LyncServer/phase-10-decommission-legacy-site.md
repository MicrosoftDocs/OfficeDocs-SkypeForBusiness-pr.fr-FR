---
title: 'Phase 10 : mettre hors service le site hérité'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3140e3529ec9e4c48ca41c26963f833f89d9f929
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="becdd-102">Phase 10 : mettre hors service le site hérité</span><span class="sxs-lookup"><span data-stu-id="becdd-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="becdd-103">_**Dernière modification de la rubrique :** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="becdd-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="becdd-104">Les rubriques suivantes fournissent des conseils dans la mise hors service des pools et la désactivation et la suppression des serveurs et des pools d’un déploiement hérité d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="becdd-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="becdd-105">Certaines des procédures répertoriées dans cette section ne sont pas requises.</span><span class="sxs-lookup"><span data-stu-id="becdd-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="becdd-106">Lisez les informations de chacune de ces rubriques pour déterminer la procédure de mise hors service à utiliser.</span><span class="sxs-lookup"><span data-stu-id="becdd-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="becdd-107">Si vous avez importé des annuaires de conférence pour la Conférence rendez-vous vers Lync Server 2013, il est important de faire passer la propriété de l’annuaire des conférences à Lync Server 2013 avant de commencer à désaffecter vos pools.</span><span class="sxs-lookup"><span data-stu-id="becdd-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="becdd-108">Si vous mettez hors service un pool sans transmettre la propriété des annuaires des conférences au préalable, la fonctionnalité de conférence rendez-vous ne fonctionnera plus pour toutes les réunions migrées.</span><span class="sxs-lookup"><span data-stu-id="becdd-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="becdd-109">Vous devez effectuer l’étape de transmission de propriété une fois pour chaque annuaire des conférences compris dans votre pool hérité.</span><span class="sxs-lookup"><span data-stu-id="becdd-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="becdd-110">Pour plus d’informations sur la migration et la mise à niveau des applications Microsoft Unified Communications Managed API (UCMA), avant de mettre hors service votre environnement hérité, voir<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="becdd-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="becdd-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="becdd-111">In This Section</span></span>

  - [<span data-ttu-id="becdd-112">Déplacer les annuaires des conférences</span><span class="sxs-lookup"><span data-stu-id="becdd-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="becdd-113">Mettre à jour les enregistrements SRV DNS</span><span class="sxs-lookup"><span data-stu-id="becdd-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="becdd-114">Mise hors service des serveurs et des pools</span><span class="sxs-lookup"><span data-stu-id="becdd-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="becdd-115">Supprimer BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="becdd-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

