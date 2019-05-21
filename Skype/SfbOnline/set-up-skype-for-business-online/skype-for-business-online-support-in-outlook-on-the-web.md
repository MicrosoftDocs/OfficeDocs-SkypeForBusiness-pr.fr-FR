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
f1keywords: None
ms.custom:
- Setup
description: Outlook sur le Web (Outlook Web App) dans Office 365 offre un client Web Skype Entreprise standard depuis la barre de navigation. Ce client de base est disponible pour les utilisateurs en ligne dont l’administrateur n’a pas configuré d’URL entraînant pour leur organisation Office 365. Tant que le compte de l’utilisateur est en ligne et qu’il n’a pas d’URL entraînant, il verra toujours l’environnement, même si son organisation dispose de comptes d’utilisateurs hébergés sur site. Les utilisateurs disposant de comptes d’utilisateurs locaux (qu’ils possèdent ou non une URL entraînant) ou gérés par Microsoft pourront voir l’environnement Lync dans Outlook Web App.
ms.openlocfilehash: 3a985bd8ad0a04198501ca8d1ec780496c59f561
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285083"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="eba9a-106">Prise en charge de Skype Entreprise Online avec Outlook sur le Web</span><span class="sxs-lookup"><span data-stu-id="eba9a-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="eba9a-107">Outlook sur le Web (Outlook Web App) dans Office 365 offre un client Web Skype Entreprise standard depuis la barre de navigation.</span><span class="sxs-lookup"><span data-stu-id="eba9a-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="eba9a-108">Ce client de base est disponible pour les utilisateurs en ligne dont l’administrateur n’a pas configuré d’URL entraînant pour leur organisation Office 365.</span><span class="sxs-lookup"><span data-stu-id="eba9a-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="eba9a-109">Tant que le compte de l’utilisateur est en ligne et qu’il n’a pas d’URL entraînant, il verra toujours l’environnement, même si son organisation dispose de comptes d’utilisateurs hébergés sur site.</span><span class="sxs-lookup"><span data-stu-id="eba9a-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="eba9a-110">Les utilisateurs disposant de comptes d’utilisateurs locaux (qu’ils possèdent ou non une URL entraînant) ou gérés par Microsoft pourront voir l’environnement Lync dans Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="eba9a-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="eba9a-111">Le tableau suivant résume les différentes opérations d’installation que vous pouvez avoir et le client Web utilisé.</span><span class="sxs-lookup"><span data-stu-id="eba9a-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="eba9a-112">**Le compte utilisateur est**</span><span class="sxs-lookup"><span data-stu-id="eba9a-112">**User account is located**</span></span> <br/> |<span data-ttu-id="eba9a-113">**Une URL de redirection vers un microsite est configurée ou il existe une configuration dédiée**</span><span class="sxs-lookup"><span data-stu-id="eba9a-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="eba9a-114">**Expérience Skype Entreprise ou Lync ?**</span><span class="sxs-lookup"><span data-stu-id="eba9a-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="eba9a-115">Online</span><span class="sxs-lookup"><span data-stu-id="eba9a-115">Online</span></span>  <br/> |<span data-ttu-id="eba9a-116">Non</span><span class="sxs-lookup"><span data-stu-id="eba9a-116">No</span></span>  <br/> |<span data-ttu-id="eba9a-117">Expérience Web Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="eba9a-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="eba9a-118">Online</span><span class="sxs-lookup"><span data-stu-id="eba9a-118">Online</span></span>  <br/> |<span data-ttu-id="eba9a-119">Oui</span><span class="sxs-lookup"><span data-stu-id="eba9a-119">Yes</span></span>  <br/> |<span data-ttu-id="eba9a-120">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="eba9a-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="eba9a-121">Hybride mais domicilié en ligne</span><span class="sxs-lookup"><span data-stu-id="eba9a-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="eba9a-122">Non</span><span class="sxs-lookup"><span data-stu-id="eba9a-122">No</span></span>  <br/> |<span data-ttu-id="eba9a-123">Expérience Web Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="eba9a-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="eba9a-124">Hybride mais domicilié en ligne</span><span class="sxs-lookup"><span data-stu-id="eba9a-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="eba9a-125">Oui</span><span class="sxs-lookup"><span data-stu-id="eba9a-125">Yes</span></span>  <br/> |<span data-ttu-id="eba9a-126">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="eba9a-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="eba9a-127">Hybride mais domicilié sur site</span><span class="sxs-lookup"><span data-stu-id="eba9a-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="eba9a-128">Non</span><span class="sxs-lookup"><span data-stu-id="eba9a-128">No</span></span>  <br/> |<span data-ttu-id="eba9a-129">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="eba9a-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="eba9a-130">Hybride mais domicilié sur site</span><span class="sxs-lookup"><span data-stu-id="eba9a-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="eba9a-131">Oui</span><span class="sxs-lookup"><span data-stu-id="eba9a-131">Yes</span></span>  <br/> |<span data-ttu-id="eba9a-132">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="eba9a-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="eba9a-133">Pure sur locaux</span><span class="sxs-lookup"><span data-stu-id="eba9a-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="eba9a-134">Non</span><span class="sxs-lookup"><span data-stu-id="eba9a-134">No</span></span>  <br/> |<span data-ttu-id="eba9a-135">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="eba9a-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="eba9a-136">Pure sur locaux</span><span class="sxs-lookup"><span data-stu-id="eba9a-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="eba9a-137">Oui</span><span class="sxs-lookup"><span data-stu-id="eba9a-137">Yes</span></span>  <br/> |<span data-ttu-id="eba9a-138">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="eba9a-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="eba9a-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eba9a-139">Related topics</span></span>
[<span data-ttu-id="eba9a-140">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="eba9a-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="eba9a-141">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="eba9a-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
