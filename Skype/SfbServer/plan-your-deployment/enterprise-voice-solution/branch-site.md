---
title: Trunking SIP site dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: En savoir plus sur le trunking SIP sur les sites de succursales dans Skype entreprise Server Voice.
ms.openlocfilehash: 14af9a096b368f310b0d4fbce425bf6d1c08696a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277110"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="08498-103">Trunking SIP site dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="08498-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="08498-104">En savoir plus sur le trunking SIP sur les sites de succursales dans Skype entreprise Server Voice.</span><span class="sxs-lookup"><span data-stu-id="08498-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="08498-105">Dans certains cas, il est possible que vous deviez implémenter une agrégation SIP distribuée sur des sites de succursales sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="08498-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="08498-106">Pour déterminer si un Trunk SIP est requis pour un site de succursale et pour plus d’informations sur les options de topologie prises en charge pour le déploiement de Trunks SIP dans les sites de succursales, voir l’interconnexion [SIP dans Skype entreprise Server](sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="08498-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="08498-107">Conditions requises pour le déploiement d’une jonction SIP sur un site de succursale : exemple d’analyse</span><span class="sxs-lookup"><span data-stu-id="08498-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="08498-108">Lorsque vous décidez de déployer un Trunk SIP de site de succursale, vous devez effectuer une analyse de coûts spécifique au site.</span><span class="sxs-lookup"><span data-stu-id="08498-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="08498-109">Par exemple, une entreprise disposant d’un site central dans Redmond, Washington et sur une succursale à New York doit effectuer une analyse pour déterminer s’il est nécessaire de mettre en œuvre un Trunk SIP à partir du site de New York vers un fournisseur de services local.</span><span class="sxs-lookup"><span data-stu-id="08498-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="08498-110">Pour savoir si une jonction SIP distribuée à New York est rentable, identifiez les numéros SDA (Sélection Directe à l’Arrivée) qui doivent utiliser la jonction SIP, puis analysez le nombre d’appels à destination de zones en dehors de Redmond (425) que le site de New York passe.</span><span class="sxs-lookup"><span data-stu-id="08498-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="08498-111">Vous pouvez avoir terminé le site de succursale sur le site central.</span><span class="sxs-lookup"><span data-stu-id="08498-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="08498-112">Par exemple, le site central de Redmond peut héberger des numéros ayant été importés pour le site de succursale de New York.</span><span class="sxs-lookup"><span data-stu-id="08498-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="08498-113">Si le coût de l’implémentation d’un Trunk SIP distribué est inférieur au coût de ces appels, envisagez d’implémenter une ligne SIP sur le site de la succursale de New York.</span><span class="sxs-lookup"><span data-stu-id="08498-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="08498-114">Autres conditions requises pour le déploiement d’une jonction SIP sur un site de succursale</span><span class="sxs-lookup"><span data-stu-id="08498-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="08498-115">Pour déterminer si vous devez déployer une jonction SIP ou une passerelle, comparez le coût des appels PSTN (Public Switched Telephone Network, réseau téléphonique commuté) longue distance de ces deux options.</span><span class="sxs-lookup"><span data-stu-id="08498-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="08498-116">Si vous déployez une ligne SIP site de succursale, vous devez également déterminer votre tolérance de panne et vos besoins en bande passante.</span><span class="sxs-lookup"><span data-stu-id="08498-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="08498-117">Si le lien entre votre site de succursale et votre site central est résilient et dispose d’une bande passante suffisante, vous pouvez déployer une passerelle SIP.</span><span class="sxs-lookup"><span data-stu-id="08498-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="08498-118">Vous n’avez pas besoin de déployer une unité de branchement survivant sur le site de la succursale.</span><span class="sxs-lookup"><span data-stu-id="08498-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="08498-119">Si le lien entre votre site de succursale et votre site central n’est pas résilient, déployez une application de succursale survivant ou déployez un serveur de succursales survivant avec une passerelle ou une ligne SIP sur le site de la succursale.</span><span class="sxs-lookup"><span data-stu-id="08498-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

