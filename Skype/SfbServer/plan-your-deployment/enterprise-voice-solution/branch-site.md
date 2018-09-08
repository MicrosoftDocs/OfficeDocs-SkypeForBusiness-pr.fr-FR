---
title: Acheminement SIP dans Skype pour Business Server Branch site
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Découvrez l’acheminement SIP sur les sites de succursale dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 17b387a0aec3498aa6ff15890ef39c94f1d68f60
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883857"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="10fe2-103">Acheminement SIP dans Skype pour Business Server Branch site</span><span class="sxs-lookup"><span data-stu-id="10fe2-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="10fe2-104">Découvrez l’acheminement SIP sur les sites de succursale dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="10fe2-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="10fe2-105">Dans certains cas, vous devrez implémenter la jonction SIP distribuée au niveau des sites de succursale sélectionné.</span><span class="sxs-lookup"><span data-stu-id="10fe2-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="10fe2-106">Pour déterminer si un SIP trunk est nécessaire pour un site de succursale et pour plus d’informations sur les options de topologie prise en charge pour le déploiement de jonctions SIP dans les sites de succursale, voir la [jonction SIP dans Skype pour Business Server](sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="10fe2-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="10fe2-107">Conditions requises pour le déploiement d’une jonction SIP sur un site de succursale : exemple d’analyse</span><span class="sxs-lookup"><span data-stu-id="10fe2-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="10fe2-108">Lorsque vous décidez de déployer une jonction SIP du site succursale, vous devez effectuer une analyse des coûts spécifiques au site.</span><span class="sxs-lookup"><span data-stu-id="10fe2-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="10fe2-109">Par exemple, une entreprise qui dispose d’un site central à Redmond, Washington et un site de succursale de New York, doit effectuer une analyse pour déterminer s’il convient d’implémenter une jonction SIP à partir du site de New York à un fournisseur de service local.</span><span class="sxs-lookup"><span data-stu-id="10fe2-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="10fe2-110">Pour savoir si une jonction SIP distribuée à New York est rentable, identifiez les numéros SDA (Sélection Directe à l’Arrivée) qui doivent utiliser la jonction SIP, puis analysez le nombre d’appels à destination de zones en dehors de Redmond (425) que le site de New York passe.</span><span class="sxs-lookup"><span data-stu-id="10fe2-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="10fe2-111">Vous pouvez avoir une terminaison d’arrivée pour le site de succursale sur le site central.</span><span class="sxs-lookup"><span data-stu-id="10fe2-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="10fe2-112">Par exemple, le site central Redmond peut héberger les numéros DID pour le site de succursale de New York.</span><span class="sxs-lookup"><span data-stu-id="10fe2-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="10fe2-113">Si le coût d’implémentation d’une jonction SIP distribuée est inférieure au coût de ces appels, envisagez d’implémenter une jonction SIP sur le site de succursale de New York.</span><span class="sxs-lookup"><span data-stu-id="10fe2-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="10fe2-114">Autres conditions requises pour le déploiement d’une jonction SIP sur un site de succursale</span><span class="sxs-lookup"><span data-stu-id="10fe2-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="10fe2-115">Pour déterminer si vous devez déployer une jonction SIP ou une passerelle, comparez le coût des appels PSTN (Public Switched Telephone Network, réseau téléphonique commuté) longue distance de ces deux options.</span><span class="sxs-lookup"><span data-stu-id="10fe2-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="10fe2-116">Si vous déployez une jonction SIP du site succursale, vous devez également déterminer vos besoins en bande passante et de résistance.</span><span class="sxs-lookup"><span data-stu-id="10fe2-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="10fe2-117">Si le lien entre votre site de succursale et le site central est robuste et a suffisamment de bande passante, vous pouvez déployer une jonction SIP ou une passerelle.</span><span class="sxs-lookup"><span data-stu-id="10fe2-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="10fe2-118">Il est inutile de déployer un serveur Survivable Branch Appliance sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="10fe2-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="10fe2-119">Si le lien entre votre site de succursale et le site central n’est pas robuste, déployer un serveur Survivable Branch Appliance ou déployer un serveur Survivable Branch Server avec une passerelle ou une jonction SIP sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="10fe2-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

