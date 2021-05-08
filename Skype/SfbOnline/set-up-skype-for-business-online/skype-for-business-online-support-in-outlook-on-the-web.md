---
title: Prise en charge de Skype Entreprise Online avec Outlook sur le Web
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Outlook web (Outlook Web App) dans Microsoft 365 ou Office 365 propose un client web de base Skype Entreprise à partir de la barre de navigation. Ce client de base est disponible pour les utilisateurs en ligne dont l’administrateur n’a pas configuré d’URL de vanity pour leurs Microsoft 365 et Office 365. Tant que le compte de l’utilisateur est en ligne et qu’il n’a pas d’URL de vanity, il pourra toujours voir l’expérience, même si son organisation possède des comptes d’utilisateurs sur site. Les utilisateurs qui ont des comptes d’utilisateurs sur site (qu’ils soient ou non des URL de personnel) ou qui sont gérés par Microsoft pourront voir l’expérience Lync dans l’Outlook Web App.
ms.openlocfilehash: aa6f82f6647db1816c630486bee0d415d05b3b77
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239569"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="7c40c-106">Prise en charge de Skype Entreprise Online avec Outlook sur le Web</span><span class="sxs-lookup"><span data-stu-id="7c40c-106">Skype for Business Online support in Outlook on the web</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="7c40c-107">Outlook web (Outlook Web App) dans Microsoft 365 ou Office 365 propose un client web de base Skype Entreprise à partir de la barre de navigation.</span><span class="sxs-lookup"><span data-stu-id="7c40c-107">Outlook on the web (Outlook Web App) in Microsoft 365 or Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="7c40c-108">Ce client de base est disponible pour les utilisateurs en ligne dont l’administrateur n’a pas configuré d’URL de vanity pour leurs Microsoft 365 et Office 365.</span><span class="sxs-lookup"><span data-stu-id="7c40c-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Microsoft 365 and Office 365.</span></span> <span data-ttu-id="7c40c-109">Tant que le compte de l’utilisateur est en ligne et qu’il n’a pas d’URL de vanity, il pourra toujours voir l’expérience, même si son organisation possède des comptes d’utilisateurs sur site.</span><span class="sxs-lookup"><span data-stu-id="7c40c-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="7c40c-110">Les utilisateurs qui ont des comptes d’utilisateurs sur site (qu’ils soient ou non des URL de personnel) ou qui sont gérés par Microsoft pourront voir l’expérience Lync dans l’Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="7c40c-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="7c40c-111">Le tableau suivant récapitule les différentes configurations que vous pouvez utiliser et le client web utilisé.</span><span class="sxs-lookup"><span data-stu-id="7c40c-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="7c40c-112">**Le compte utilisateur est**</span><span class="sxs-lookup"><span data-stu-id="7c40c-112">**User account is located**</span></span> <br/> |<span data-ttu-id="7c40c-113">**Une URL de redirection vers un microsite est configurée ou il existe une configuration dédiée**</span><span class="sxs-lookup"><span data-stu-id="7c40c-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="7c40c-114">**Expérience Skype Entreprise ou Lync ?**</span><span class="sxs-lookup"><span data-stu-id="7c40c-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="7c40c-115">Online</span><span class="sxs-lookup"><span data-stu-id="7c40c-115">Online</span></span>  <br/> |<span data-ttu-id="7c40c-116">Non</span><span class="sxs-lookup"><span data-stu-id="7c40c-116">No</span></span>  <br/> |<span data-ttu-id="7c40c-117">Expérience Web Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="7c40c-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="7c40c-118">Online</span><span class="sxs-lookup"><span data-stu-id="7c40c-118">Online</span></span>  <br/> |<span data-ttu-id="7c40c-119">Oui</span><span class="sxs-lookup"><span data-stu-id="7c40c-119">Yes</span></span>  <br/> |<span data-ttu-id="7c40c-120">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="7c40c-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="7c40c-121">Hybride mais domicilié en ligne</span><span class="sxs-lookup"><span data-stu-id="7c40c-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="7c40c-122">Non</span><span class="sxs-lookup"><span data-stu-id="7c40c-122">No</span></span>  <br/> |<span data-ttu-id="7c40c-123">Expérience Web Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="7c40c-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="7c40c-124">Hybride mais domicilié en ligne</span><span class="sxs-lookup"><span data-stu-id="7c40c-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="7c40c-125">Oui</span><span class="sxs-lookup"><span data-stu-id="7c40c-125">Yes</span></span>  <br/> |<span data-ttu-id="7c40c-126">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="7c40c-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="7c40c-127">Hybride mais domicilié sur site</span><span class="sxs-lookup"><span data-stu-id="7c40c-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="7c40c-128">Non</span><span class="sxs-lookup"><span data-stu-id="7c40c-128">No</span></span>  <br/> |<span data-ttu-id="7c40c-129">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="7c40c-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="7c40c-130">Hybride mais domicilié sur site</span><span class="sxs-lookup"><span data-stu-id="7c40c-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="7c40c-131">Oui</span><span class="sxs-lookup"><span data-stu-id="7c40c-131">Yes</span></span>  <br/> |<span data-ttu-id="7c40c-132">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="7c40c-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="7c40c-133">Pure sur prém</span><span class="sxs-lookup"><span data-stu-id="7c40c-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="7c40c-134">Non</span><span class="sxs-lookup"><span data-stu-id="7c40c-134">No</span></span>  <br/> |<span data-ttu-id="7c40c-135">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="7c40c-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="7c40c-136">Pure sur prém</span><span class="sxs-lookup"><span data-stu-id="7c40c-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="7c40c-137">Oui</span><span class="sxs-lookup"><span data-stu-id="7c40c-137">Yes</span></span>  <br/> |<span data-ttu-id="7c40c-138">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="7c40c-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="7c40c-139">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="7c40c-139">Related topics</span></span>
[<span data-ttu-id="7c40c-140">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="7c40c-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="7c40c-141">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="7c40c-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
