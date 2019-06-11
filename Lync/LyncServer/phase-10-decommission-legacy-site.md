---
title: 'Étape 10: désaffecter le site hérité'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a04054c158f1c97f5090328e1277dcdb63b1d823
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846124"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="21513-102">Étape 10: désaffecter le site hérité</span><span class="sxs-lookup"><span data-stu-id="21513-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21513-103">_**Dernière modification de la rubrique:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="21513-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="21513-104">Les rubriques suivantes fournissent des recommandations en matière de mise en service de pools, et de désactivation et de suppression de serveurs et de pools à partir d’un déploiement hérité d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="21513-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="21513-105">Toutes les procédures indiquées dans cette section ne sont pas obligatoires.</span><span class="sxs-lookup"><span data-stu-id="21513-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="21513-106">Lisez les informations contenues dans ces rubriques pour déterminer la procédure de désactivation à utiliser.</span><span class="sxs-lookup"><span data-stu-id="21513-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="21513-107">Si vous avez importé des annuaires de conférences pour les conférences rendez-vous sur Lync Server 2013, il est important de basculer la propriété de l’annuaire de conférences vers Lync Server 2013 avant de commencer à mettre vos pools en service.</span><span class="sxs-lookup"><span data-stu-id="21513-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="21513-108">Si vous désorganisez un pool sans avoir préalablement transféré la propriété de l’annuaire de conférences, la fonctionnalité de connexion à toutes les réunions migrées ne fonctionnera plus.</span><span class="sxs-lookup"><span data-stu-id="21513-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="21513-109">Vous devez effectuer cette étape pour une transition de propriété unique pour chaque annuaire de conférences de votre pool hérité.</span><span class="sxs-lookup"><span data-stu-id="21513-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="21513-110">Pour plus d’informations sur la migration et la mise à niveau des applications UCMA (Unified Communications Managed API), avant de désaffecter votre environnement hérité, voir<A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="21513-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="21513-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="21513-111">In This Section</span></span>

  - [<span data-ttu-id="21513-112">Déplacer des répertoires de conférences</span><span class="sxs-lookup"><span data-stu-id="21513-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="21513-113">Mettre à jour les enregistrements SRV DNS</span><span class="sxs-lookup"><span data-stu-id="21513-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="21513-114">Désaffectation de serveurs et de pools</span><span class="sxs-lookup"><span data-stu-id="21513-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="21513-115">Supprimer BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="21513-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

