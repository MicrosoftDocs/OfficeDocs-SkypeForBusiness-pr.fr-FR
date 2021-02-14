---
title: 'Prise en charge de la virtualisation pour Skype Entreprise Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé : Découvrez la prise en charge de la virtualisation pour Skype Entreprise Server 2019.'
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509031"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="900e9-103">Prise en charge de la virtualisation pour Skype Entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="900e9-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="900e9-104">Skype Entreprise Server 2019 est pris en charge sur la virtualisation.</span><span class="sxs-lookup"><span data-stu-id="900e9-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="900e9-105">Bien que la virtualisation soit prise en charge, il existe quelques points clés à retenir :</span><span class="sxs-lookup"><span data-stu-id="900e9-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="900e9-106">Maintenez un rapport 1:1 entre l’UC virtuelle et l’UC physique.</span><span class="sxs-lookup"><span data-stu-id="900e9-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="900e9-107">Ne déplacez pas un serveur invité pendant son fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="900e9-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="900e9-108">La migration d’un système en direct et la portabilité d’une machine virtuelle ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="900e9-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="900e9-109">Désactivez l’hyper-threading sur tous les hôtes.</span><span class="sxs-lookup"><span data-stu-id="900e9-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="900e9-110">Ne configurez pas la mémoire dynamique sur les serveurs hôtes.</span><span class="sxs-lookup"><span data-stu-id="900e9-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="900e9-111">Utilisez des disques fixes ou pass-through plutôt que des disques dynamiques.</span><span class="sxs-lookup"><span data-stu-id="900e9-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="900e9-112">Autorisez une surcharge de 6 à 10 % pour les hyperviseurs au-delà de ce dont l’invité virtuel a besoin.</span><span class="sxs-lookup"><span data-stu-id="900e9-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="900e9-113">Hyperviseurs pris en charge</span><span class="sxs-lookup"><span data-stu-id="900e9-113">Supported hypervisors</span></span>

<span data-ttu-id="900e9-114">SfB Server 2019 est pris en charge sur Windows Server 2016 et Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="900e9-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="900e9-115">Pour les hyperviseurs tiers, vous avez besoin d’un hyperviseur qui a réussi le test SVVP (Server Virtualization Validation Program) pour le système d’exploitation approprié.</span><span class="sxs-lookup"><span data-stu-id="900e9-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="900e9-116">Consultez [les versions de Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) dans la liste SVVP.</span><span class="sxs-lookup"><span data-stu-id="900e9-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="900e9-117">Consultez [les versions de Windows Server 2019 dans](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) la liste SVVP.</span><span class="sxs-lookup"><span data-stu-id="900e9-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>

## <a name="stress-and-performance-tool"></a><span data-ttu-id="900e9-118">Outil Stress and performance</span><span class="sxs-lookup"><span data-stu-id="900e9-118">Stress and performance tool</span></span>

<span data-ttu-id="900e9-119">L’outil Stress and Performance de Skype Entreprise Server 2019 inclut des outils qui simplifient la planification de la capacité pour Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="900e9-119">The Skype for Business Server 2019 Stress and Performance Tool includes tools that simplify capacity planning for Skype for Business Server 2019.</span></span> <span data-ttu-id="900e9-120">L’outil Stress and Performance de Skype Entreprise Server 2019 vous aidera à :</span><span class="sxs-lookup"><span data-stu-id="900e9-120">The Skype for Business Server 2019 Stress and Performance Tool will help you to:</span></span>

- <span data-ttu-id="900e9-121">Simplifier la planification de votre matériel pour Skype Entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="900e9-121">Simplify your hardware planning for Skype for Business Server 2019</span></span>
- <span data-ttu-id="900e9-122">Vous fournir des connaissances accrues et des meilleures pratiques pour l’optimisation des performances</span><span class="sxs-lookup"><span data-stu-id="900e9-122">Provide you with increased knowledge and best practices for performance tuning</span></span>
- <span data-ttu-id="900e9-123">Mesurer les performances de vos déploiements Skype Entreprise Server 2019 prévus</span><span class="sxs-lookup"><span data-stu-id="900e9-123">Measure the performance of your intended Skype for Business Server 2019 deployments</span></span>
 
<span data-ttu-id="900e9-124">Vous pouvez télécharger l’outil à partir [d’ici.](https://www.microsoft.com/download/details.aspx?id=101447)</span><span class="sxs-lookup"><span data-stu-id="900e9-124">You can download the tool from [here](https://www.microsoft.com/download/details.aspx?id=101447).</span></span>
