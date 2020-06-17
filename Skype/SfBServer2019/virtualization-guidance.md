---
title: 'Prise en charge de la virtualisation pour Skype entreprise Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/20
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé : Découvrez la prise en charge de la virtualisation pour Skype entreprise Server 2019.'
ms.openlocfilehash: b4524b1284a85e7ab372b415d45c2005f8212887
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755808"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="07cbb-103">Prise en charge de la virtualisation pour Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="07cbb-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="07cbb-104">Skype entreprise Server 2019 est pris en charge sur la virtualisation.</span><span class="sxs-lookup"><span data-stu-id="07cbb-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="07cbb-105">Bien que la virtualisation soit prise en charge, il existe certains points clés à garder à l’esprit :</span><span class="sxs-lookup"><span data-stu-id="07cbb-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="07cbb-106">Conservez un ratio de 1:1 d’UC virtuelle/unité centrale physique.</span><span class="sxs-lookup"><span data-stu-id="07cbb-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="07cbb-107">Ne pas déplacer un serveur invité pendant qu’il fonctionne.</span><span class="sxs-lookup"><span data-stu-id="07cbb-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="07cbb-108">La migration d’un système actif et la portabilité d’une machine virtuelle ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="07cbb-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="07cbb-109">Désactivez la technologie Hyper-Threading sur tous les hôtes.</span><span class="sxs-lookup"><span data-stu-id="07cbb-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="07cbb-110">Ne configurez pas de mémoire dynamique sur les serveurs hôtes.</span><span class="sxs-lookup"><span data-stu-id="07cbb-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="07cbb-111">Utilisez des disques fixes ou passés plutôt que des disques dynamiques.</span><span class="sxs-lookup"><span data-stu-id="07cbb-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="07cbb-112">Autoriser une charge de travail de 6-10 pour cent pour les hyperviseurs au-delà de ce que requiert l’invité virtuel.</span><span class="sxs-lookup"><span data-stu-id="07cbb-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="07cbb-113">Hyperviseurs pris en charge</span><span class="sxs-lookup"><span data-stu-id="07cbb-113">Supported hypervisors</span></span>

<span data-ttu-id="07cbb-114">SfB Server 2019 est pris en charge sur Windows Server 2016 et Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="07cbb-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="07cbb-115">Pour les hyperviseurs tiers, vous avez besoin d’un hyperviseur qui a réussi le test du programme de validation de la virtualisation de serveur (SVVP) pour le système d’exploitation concerné.</span><span class="sxs-lookup"><span data-stu-id="07cbb-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="07cbb-116">Voir les [versions de Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) dans la liste SVVP.</span><span class="sxs-lookup"><span data-stu-id="07cbb-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="07cbb-117">Voir les [versions de Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) dans la liste SVVP.</span><span class="sxs-lookup"><span data-stu-id="07cbb-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>

## <a name="stress-and-performance-tool"></a><span data-ttu-id="07cbb-118">Outil stress and performance</span><span class="sxs-lookup"><span data-stu-id="07cbb-118">Stress and performance tool</span></span>

<span data-ttu-id="07cbb-119">L’outil stress and performance de Skype entreprise Server 2019 inclut des outils qui simplifient la planification de la capacité pour Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="07cbb-119">The Skype for Business Server 2019 Stress and Performance Tool includes tools that simplify capacity planning for Skype for Business Server 2019.</span></span> <span data-ttu-id="07cbb-120">L’outil stress and performance de Skype entreprise Server 2019 vous permet d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="07cbb-120">The Skype for Business Server 2019 Stress and Performance Tool will help you to:</span></span>

- <span data-ttu-id="07cbb-121">Simplifier la planification de votre matériel pour Skype entreprise Server 2019</span><span class="sxs-lookup"><span data-stu-id="07cbb-121">Simplify your hardware planning for Skype for Business Server 2019</span></span>
- <span data-ttu-id="07cbb-122">Vous fournir des connaissances et meilleures pratiques accrues pour le réglage des performances</span><span class="sxs-lookup"><span data-stu-id="07cbb-122">Provide you with increased knowledge and best practices for performance tuning</span></span>
- <span data-ttu-id="07cbb-123">Mesurer les performances de vos déploiements Skype entreprise Server 2019 envisagés</span><span class="sxs-lookup"><span data-stu-id="07cbb-123">Measure the performance of your intended Skype for Business Server 2019 deployments</span></span>
 
<span data-ttu-id="07cbb-124">Vous pouvez télécharger l’outil à partir de [cet emplacement](https://www.microsoft.com/download/details.aspx?id=101447).</span><span class="sxs-lookup"><span data-stu-id="07cbb-124">You can download the tool from [here](https://www.microsoft.com/download/details.aspx?id=101447).</span></span>
