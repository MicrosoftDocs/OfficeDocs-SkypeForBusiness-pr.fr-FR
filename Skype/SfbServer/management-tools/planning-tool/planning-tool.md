---
title: Outil de planification de Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: Conseils relatifs à l’utilisation de l’outil de planification de Skype entreprise Server 2015.
ms.openlocfilehash: b130ca05200ea30bed8008399050affa96438644
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288949"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="92ad4-103">Outil de planification de Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="92ad4-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="92ad4-104">Conseils relatifs à l’utilisation de l’outil de planification de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="92ad4-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="92ad4-105">L’outil de planification de Skype entreprise Server 2015 est un outil piloté par un Assistant, qui pose des questions sur la topologie 2015 de Skype entreprise Server que vous concevez.</span><span class="sxs-lookup"><span data-stu-id="92ad4-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="92ad4-106">L’outil de planification utilise les informations fournies, associées à des pratiques recommandées en matière de conception et de capacité topologique, pour présenter une topologie recommandée selon les réponses fournies.</span><span class="sxs-lookup"><span data-stu-id="92ad4-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="92ad4-107">Vous pouvez télécharger l’outil de planification à partir de l' [outil de planification de Skype entreprise Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span><span class="sxs-lookup"><span data-stu-id="92ad4-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="92ad4-108">En fin de compte, l’objectif de l’outil de planification consiste à faciliter la complexité de la conception d’une topologie complète de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="92ad4-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="92ad4-109">L’outil fournit également des références contextuelles sur la planification et la documentation de déploiement à l’intérieur de l’outil, à condition qu’une connexion Internet soit disponible pour la connexion au site Web Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92ad4-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="92ad4-110">Après avoir personnalisé la topologie avec les adresses TCP/IP de l’infrastructure et les noms de domaine complets (FQDN), l’outil de planification met à votre disposition une série de rapports qui couvrent l’attribution de noms DNS (Domain Name System), les règles de pare-feu, les certificats, etc.</span><span class="sxs-lookup"><span data-stu-id="92ad4-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="92ad4-111">Utiliser cet outil est la première étape pour la planification de votre implémentation.</span><span class="sxs-lookup"><span data-stu-id="92ad4-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="92ad4-112">L’étape suivante consiste à entrer les informations de votre site dans le [calculateur de capacités de Skype entreprise server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=51196), à ajuster selon les besoins, puis à utiliser l' [outil de stress et de performance de skype entreprise Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50367) . vous aurez besoin de votre implémentation.</span><span class="sxs-lookup"><span data-stu-id="92ad4-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="92ad4-113">L’outil de planification offre également la possibilité d’exporter des informations dans deux formats:</span><span class="sxs-lookup"><span data-stu-id="92ad4-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="92ad4-114">Microsoft Excel (feuille de calcul .xml)</span><span class="sxs-lookup"><span data-stu-id="92ad4-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="92ad4-115">Microsoft Visio (.vdx)</span><span class="sxs-lookup"><span data-stu-id="92ad4-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="92ad4-116">Les rubriques suivantes présentent et décrivent en détail l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="92ad4-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="92ad4-117">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="92ad4-117">In this section</span></span>

- [<span data-ttu-id="92ad4-118">Install the Planning Tool in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="92ad4-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="92ad4-119">Optional Software</span><span class="sxs-lookup"><span data-stu-id="92ad4-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="92ad4-120">Navigate the Planning Tool in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="92ad4-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="92ad4-121">Create the initial topology design for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="92ad4-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="92ad4-122">Edit the topology in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="92ad4-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="92ad4-123">Edit the network configuration diagram</span><span class="sxs-lookup"><span data-stu-id="92ad4-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="92ad4-124">Review the Administrator Reports in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="92ad4-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="92ad4-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="92ad4-125">See also</span></span>

[<span data-ttu-id="92ad4-126">Installer Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="92ad4-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="92ad4-127">Plan for instant messaging and presence in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="92ad4-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
