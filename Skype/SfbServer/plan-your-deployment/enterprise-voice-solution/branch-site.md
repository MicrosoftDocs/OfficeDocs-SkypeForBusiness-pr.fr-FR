---
title: Branch site SIP trunking in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: En savoir plus sur la trunking SIP sur les sites de succursale dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: f8b875fca8adc1ac78c0b24cf3e53fab2ec2cd89
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813714"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="40e61-103">Branch site SIP trunking in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40e61-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="40e61-104">En savoir plus sur la trunking SIP sur les sites de succursale dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="40e61-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="40e61-105">Dans certains cas, vous devrez peut-être implémenter une trunking SIP distribuée sur des sites de succursale sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="40e61-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="40e61-106">Pour déterminer si une trunk SIP est nécessaire pour un site de succursale et pour plus d’informations sur les options de topologie prise en charge pour le déploiement de trunks SIP dans des sites de succursale, voir [siP trunking in Skype for Business Server](sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="40e61-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="40e61-107">Conditions requises pour le déploiement d’une jonction SIP sur un site de succursale : exemple d’analyse</span><span class="sxs-lookup"><span data-stu-id="40e61-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="40e61-108">Lorsque vous décidez de déployer une trunk SIP de site de succursale, vous devez effectuer une analyse des coûts spécifique au site.</span><span class="sxs-lookup"><span data-stu-id="40e61-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="40e61-109">Par exemple, une entreprise qui possède un site central à Redmond,Washington et un site de succursale à New York, doit réaliser une analyse pour déterminer s’il faut implémenter une trunk SIP du site New York vers un fournisseur de services local.</span><span class="sxs-lookup"><span data-stu-id="40e61-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="40e61-110">Pour savoir si une jonction SIP distribuée à New York est rentable, identifiez les numéros SDA (Sélection Directe à l’Arrivée) qui doivent utiliser la jonction SIP, puis analysez le nombre d’appels à destination de zones en dehors de Redmond (425) que le site de New York passe.</span><span class="sxs-lookup"><span data-stu-id="40e61-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="40e61-111">Vous pouvez avoir un arrêt DID pour le site de succursale sur le site central.</span><span class="sxs-lookup"><span data-stu-id="40e61-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="40e61-112">Par exemple, le site central de Redmond peut héberger des numéros DID pour le site de succursale de New York.</span><span class="sxs-lookup"><span data-stu-id="40e61-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="40e61-113">Si le coût de l’implémentation d’une trunk SIP distribuée est inférieur au coût de ces appels, envisagez d’implémenter une trunk SIP sur le site de succursale de New York.</span><span class="sxs-lookup"><span data-stu-id="40e61-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="40e61-114">Autres conditions requises pour le déploiement d’une jonction SIP sur un site de succursale</span><span class="sxs-lookup"><span data-stu-id="40e61-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="40e61-115">Pour déterminer si vous devez déployer une jonction SIP ou une passerelle, comparez le coût des appels PSTN (Public Switched Telephone Network, réseau téléphonique commuté) longue distance de ces deux options.</span><span class="sxs-lookup"><span data-stu-id="40e61-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="40e61-116">Si vous déployez une connexion SIP de site de succursale, vous devez également déterminer vos besoins en résilience et en bande passante.</span><span class="sxs-lookup"><span data-stu-id="40e61-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="40e61-117">Si la liaison entre votre site de succursale et votre site central est résiliente et dispose d’une bande passante suffisante, vous pouvez déployer une passerelle ou une connexion SIP.</span><span class="sxs-lookup"><span data-stu-id="40e61-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="40e61-118">Vous n’avez pas besoin de déployer un Survivable Branch Appliance sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="40e61-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="40e61-119">Si la liaison entre votre site de succursale et votre site central n’est pas résiliente, déployez un Survivable Branch Appliance ou déployez un serveur Survivable Branch Server avec une passerelle ou une connexion SIP sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="40e61-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

