---
title: Créer une carte de bâtiments pour le tableau de bord de qualité des appels
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Découvrez comment créer une carte de bâtiment que vous pouvez utiliser pour charger des données client et bâtiment dans le tableau de bord de qualité des appels.
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584033"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a><span data-ttu-id="51ddc-103">Créer une carte de bâtiments pour le tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="51ddc-103">Create a building map for Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="51ddc-104">Dans un déploiement Microsoft Teams ou Skype Entreprise Online, tous les clients sont externes.</span><span class="sxs-lookup"><span data-stu-id="51ddc-104">In a Microsoft Teams or Skype for Business Online deployment, all clients are external.</span></span> <span data-ttu-id="51ddc-105">Par conséquent, par défaut, tous les clients sont signalés comme externes dans le tableau de bord de qualité des appels, que le client soit connecté ou non sur un réseau d’entreprise interne.</span><span class="sxs-lookup"><span data-stu-id="51ddc-105">As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.</span></span>

<span data-ttu-id="51ddc-106">Lorsque vous travaillez avec le DQD, vous devez connaître l’emplacement d’un point de terminaison et savoir s’il était connecté à un réseau que vous pouvez gérer ou qu’il ne peut pas gérer, l’hypothèse étant que vous pouvez seulement améliorer les réseaux que vous pouvez gérer.</span><span class="sxs-lookup"><span data-stu-id="51ddc-106">When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, the assumption being that you can only improve networks you can manage.</span></span> <span data-ttu-id="51ddc-107">En chargeant le sous-réseau et en insérant les informations sur le CQD, vous activez le point de terminaison pour déterminer si le point de terminaison était connecté à un réseau interne (géré) ou à un réseau externe (non géré).</span><span class="sxs-lookup"><span data-stu-id="51ddc-107">By uploading subnet and building information to CQD, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network.</span></span> <span data-ttu-id="51ddc-108">C’est pourquoi il est important de créer une carte de bâtiments pour votre organisation et [de la télécharger sur le CQD.](CQD-upload-tenant-building-data.md)</span><span class="sxs-lookup"><span data-stu-id="51ddc-108">That's why it's important to create a building map for your organization and [upload it to CQD](CQD-upload-tenant-building-data.md).</span></span>

## <a name="building-mapping-tools"></a><span data-ttu-id="51ddc-109">Outils de mappage des bâtiments</span><span class="sxs-lookup"><span data-stu-id="51ddc-109">Building mapping tools</span></span>

<span data-ttu-id="51ddc-110">Il existe plusieurs façons de ma carte des sous-réseaux de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="51ddc-110">There are many ways to map your organization's subnets.</span></span> <span data-ttu-id="51ddc-111">Si vous avez besoin d’aide, vous pouvez utiliser le module PowerShell CQDTools décrit dans ce [billet de blog.](https://aka.ms/cqdtools)</span><span class="sxs-lookup"><span data-stu-id="51ddc-111">If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools).</span></span> <span data-ttu-id="51ddc-112">Ces outils sont basés sur PowerShell et utilisent les sites et services Active Directory (AD) et les services DHCP Microsoft pour pré-remplir votre fichier de construction.</span><span class="sxs-lookup"><span data-stu-id="51ddc-112">These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file.</span></span> <span data-ttu-id="51ddc-113">Les outils suivants vous aideront dans les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="51ddc-113">These tools will help with the following tasks:</span></span>

1. <span data-ttu-id="51ddc-114">recherchez des sites et services AD, puis créez un fichier de construction basé sur les informations contenues dans celui-ci.</span><span class="sxs-lookup"><span data-stu-id="51ddc-114">Query AD Sites and Services, and create a building file based on the information contained within.</span></span>
1. <span data-ttu-id="51ddc-115">Interrogez un ou plusieurs serveurs DHCP Microsoft pour obtenir des informations de sous-réseau et créer automatiquement un fichier de bâtiment.</span><span class="sxs-lookup"><span data-stu-id="51ddc-115">Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.</span></span>
1. <span data-ttu-id="51ddc-116">Validez un fichier de construction existant, en vérifiant la recherche de doublons et de chevauchements.</span><span class="sxs-lookup"><span data-stu-id="51ddc-116">Validate an existing building file, checking for duplicates and overlaps.</span></span>
1. <span data-ttu-id="51ddc-117">Recherchez des sous-réseaux non mis en réseau dans le DQD.</span><span class="sxs-lookup"><span data-stu-id="51ddc-117">Find unmapped subnets in CQD.</span></span>

## <a name="related-topics"></a><span data-ttu-id="51ddc-118">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="51ddc-118">Related topics</span></span>

[<span data-ttu-id="51ddc-119">Charger des données client et de bâtiment dans le DQD</span><span class="sxs-lookup"><span data-stu-id="51ddc-119">Upload tenant and building data in CQD</span></span>](CQD-upload-tenant-building-data.md)