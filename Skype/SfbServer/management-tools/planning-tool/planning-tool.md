---
title: Outil de planification Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: Recommandations sur l’utilisation de l’outil de planification de Skype Entreprise Server 2015.
ms.openlocfilehash: aef46fac65ba1d5651cada81bc79cfc21021bf54
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832384"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="5ae4f-103">Outil de planification Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5ae4f-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="5ae4f-104">Recommandations sur l’utilisation de l’outil de planification de Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5ae4f-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="5ae4f-105">L’outil de planification de Skype Entreprise Server 2015 est un outil piloté par un Assistant qui vous pose des questions sur la topologie Skype Entreprise Server 2015 que vous concevez.</span><span class="sxs-lookup"><span data-stu-id="5ae4f-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="5ae4f-106">L’outil de planification utilise les informations fournies, associées aux pratiques recommandées pour la conception et la capacité de la topologie, pour présenter une topologie recommandée en fonction des réponses fournies.</span><span class="sxs-lookup"><span data-stu-id="5ae4f-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="5ae4f-107">Vous pouvez télécharger l’outil de planification à partir de l’outil de planification [de Skype Entreprise Server 2015.](https://go.microsoft.com/fwlink/p/?LinkID=282725)</span><span class="sxs-lookup"><span data-stu-id="5ae4f-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="5ae4f-108">En fin de compte, l’objectif de l’outil de planification est de réduire la complexité potentielle de la conception d’une topologie Skype Entreprise Server 2015 complète.</span><span class="sxs-lookup"><span data-stu-id="5ae4f-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="5ae4f-109">L’outil fournit également des références contextuelles à la documentation de planification et de déploiement à l’intérieur de l’outil, à condition qu’une connexion Internet soit disponible pour se connecter au site web microsoft.</span><span class="sxs-lookup"><span data-stu-id="5ae4f-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="5ae4f-110">Après avoir personnalisé la topologie avec les adresses TCP/IP et les noms de domaine complets de l’infrastructure, l’outil de planification met à disposition une série de rapports qui couvrent l’appellation DNS (Domain Name System), les règles de pare-feu, les certificats, etc.</span><span class="sxs-lookup"><span data-stu-id="5ae4f-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="5ae4f-111">L’utilisation de cet outil est la première étape de la planification de votre implémentation.</span><span class="sxs-lookup"><span data-stu-id="5ae4f-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="5ae4f-112">L’étape suivante consiste à entrer les informations spécifiques de votre site dans la calculatrice de capacité de Skype Entreprise [Server 2015,](https://www.microsoft.com/download/details.aspx?id=51196)à ajuster selon vos besoins, puis à utiliser l’outil Stress and Performance de Skype Entreprise [Server 2015](https://www.microsoft.com/download/details.aspx?id=50367) pour simuler et vérifier que l’implémentation sera en mesure de répondre à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="5ae4f-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="5ae4f-113">L’outil de planification permet également d’exporter des informations dans deux formats :</span><span class="sxs-lookup"><span data-stu-id="5ae4f-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="5ae4f-114">Microsoft Excel (feuille de calcul .xml)</span><span class="sxs-lookup"><span data-stu-id="5ae4f-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="5ae4f-115">Microsoft Visio (.vdx)</span><span class="sxs-lookup"><span data-stu-id="5ae4f-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="5ae4f-116">Les rubriques suivantes présentent et détaillent l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="5ae4f-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="5ae4f-117">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="5ae4f-117">In this section</span></span>

- [<span data-ttu-id="5ae4f-118">Installer l’outil de planification dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5ae4f-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="5ae4f-119">Logiciels facultatifs</span><span class="sxs-lookup"><span data-stu-id="5ae4f-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="5ae4f-120">Naviguer dans l’outil de planification dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5ae4f-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="5ae4f-121">Création de la conception de topologie initiale pour Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5ae4f-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="5ae4f-122">Modifier la topologie dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5ae4f-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="5ae4f-123">Modifier le diagramme de configuration réseau</span><span class="sxs-lookup"><span data-stu-id="5ae4f-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="5ae4f-124">Examiner les rapports de l’administrateur dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5ae4f-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="5ae4f-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5ae4f-125">See also</span></span>

[<span data-ttu-id="5ae4f-126">Installer Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5ae4f-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="5ae4f-127">Planifier la messagerie instantanée et la présence dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5ae4f-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
