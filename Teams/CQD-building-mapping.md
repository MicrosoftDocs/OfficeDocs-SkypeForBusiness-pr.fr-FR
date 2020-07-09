---
title: Créer une carte de bâtiment pour le tableau de bord de qualité des appels (bord)
ms.author: lolaj
author: LolaJacobsen
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
description: Découvrez comment créer une carte de bâtiment que vous pouvez utiliser pour charger un client et générer des données dans le tableau de bord de qualité des appels (bord).
ms.openlocfilehash: 18e88c2de64d2d63589a3cd2ebddbc9643fe4522
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086044"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a><span data-ttu-id="edd1e-103">Créer une carte de bâtiment pour le tableau de bord de qualité des appels (bord)</span><span class="sxs-lookup"><span data-stu-id="edd1e-103">Create a building map for Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="edd1e-104">Dans le cas d’un déploiement de Microsoft teams ou de Skype entreprise Online, tous les clients sont externes.</span><span class="sxs-lookup"><span data-stu-id="edd1e-104">In a Microsoft Teams or Skype for Business Online deployment, all clients are external.</span></span> <span data-ttu-id="edd1e-105">Par défaut, tous les clients sont signalés comme extérieurs dans le tableau de bord de qualité des appels (bord), que le client soit connecté ou non au réseau d’entreprise interne.</span><span class="sxs-lookup"><span data-stu-id="edd1e-105">As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.</span></span>

<span data-ttu-id="edd1e-106">Lorsque vous utilisez bord, vous devez connaître l’emplacement d’un point de terminaison et savoir s’il est connecté à un réseau que vous pouvez gérer ou un réseau que vous ne pouvez pas gérer, en partant du principe que vous pouvez uniquement améliorer les réseaux que vous pouvez gérer.</span><span class="sxs-lookup"><span data-stu-id="edd1e-106">When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, the assumption being that you can only improve networks you can manage.</span></span> <span data-ttu-id="edd1e-107">En chargeant les informations de sous-réseau et en bâtiment des informations dans bord, vous activez bord pour déterminer si le point de terminaison a été connecté à un réseau interne (géré) ou à un réseau externe (non géré).</span><span class="sxs-lookup"><span data-stu-id="edd1e-107">By uploading subnet and building information to CQD, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network.</span></span> <span data-ttu-id="edd1e-108">C’est pourquoi il est important de créer une carte de bâtiment pour votre organisation et de la [Télécharger sur bord](CQD-upload-tenant-building-data.md).</span><span class="sxs-lookup"><span data-stu-id="edd1e-108">That's why it's important to create a building map for your organization and [upload it to CQD](CQD-upload-tenant-building-data.md).</span></span>

## <a name="building-mapping-tools"></a><span data-ttu-id="edd1e-109">Outils de mappage de construction</span><span class="sxs-lookup"><span data-stu-id="edd1e-109">Building mapping tools</span></span>

<span data-ttu-id="edd1e-110">Il existe de nombreuses façons de mapper les sous-réseaux de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="edd1e-110">There are many ways to map your organization's subnets.</span></span> <span data-ttu-id="edd1e-111">Si vous avez besoin d’aide, vous pouvez utiliser le module PowerShell d’CQDTools décrit dans ce [billet de blog](https://aka.ms/cqdtools).</span><span class="sxs-lookup"><span data-stu-id="edd1e-111">If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools).</span></span> <span data-ttu-id="edd1e-112">Ces outils sont basés sur PowerShell et utilisent des sites et services Active Directory (AD) et des services Microsoft DHCP pour vous aider à préremplir votre fichier de construction.</span><span class="sxs-lookup"><span data-stu-id="edd1e-112">These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file.</span></span> <span data-ttu-id="edd1e-113">Ces outils peuvent vous aider à effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="edd1e-113">These tools will help with the following tasks:</span></span>

1. <span data-ttu-id="edd1e-114">Interrogez les sites et services d’annonces et créez un fichier d’immeuble en fonction des informations contenues dans.</span><span class="sxs-lookup"><span data-stu-id="edd1e-114">Query AD Sites and Services, and create a building file based on the information contained within.</span></span>
1. <span data-ttu-id="edd1e-115">Interrogez un serveur ou un serveur DHCP Microsoft pour extraire des informations de sous-réseau et créer automatiquement un fichier de bâtiment.</span><span class="sxs-lookup"><span data-stu-id="edd1e-115">Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.</span></span>
1. <span data-ttu-id="edd1e-116">Validez un fichier de construction existant, en recherchant les doublons et les chevauchements.</span><span class="sxs-lookup"><span data-stu-id="edd1e-116">Validate an existing building file, checking for duplicates and overlaps.</span></span>
1. <span data-ttu-id="edd1e-117">Recherchez les sous-réseaux non mappés dans bord.</span><span class="sxs-lookup"><span data-stu-id="edd1e-117">Find unmapped subnets in CQD.</span></span>

## <a name="related-topics"></a><span data-ttu-id="edd1e-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="edd1e-118">Related topics</span></span>

[<span data-ttu-id="edd1e-119">Télécharger le client et générer des données dans bord</span><span class="sxs-lookup"><span data-stu-id="edd1e-119">Upload tenant and building data in CQD</span></span>](CQD-upload-tenant-building-data.md)