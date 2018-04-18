---
title: Prise en charge de Skype Entreprise Online avec Outlook sur le Web
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Outlook sur le Web (Outlook Web App) dans Office 365 offre un client Web Skype Entreprise standard depuis la barre de navigation. Ce client de base est disponible pour les utilisateurs en ligne dont admin n’a pas configuré une URL vanity pour leur organisation d’Office 365. Tant que le compte d’utilisateur est en ligne et n’a pas une URL de courtoisie, ils pourront toujours voir l’expérience même si leur organisation a certains comptes d’utilisateurs qui sont hébergées sur site. Les utilisateurs qui ont des utilisateurs comptes locaux (qu’ils aient une URL vanity ou non) ou sont gérés par Microsoft verront l’expérience Lync dans Outlook web app.
ms.openlocfilehash: 03491bb0cb200cac8eecb0ae2282a7003a85f8dc
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="32f0f-106">Prise en charge de Skype Entreprise Online avec Outlook sur le Web</span><span class="sxs-lookup"><span data-stu-id="32f0f-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="32f0f-107">Outlook sur le Web (Outlook Web App) dans Office 365 offre un client Web Skype Entreprise standard depuis la barre de navigation.</span><span class="sxs-lookup"><span data-stu-id="32f0f-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="32f0f-108">Ce client de base est disponible pour les utilisateurs en ligne dont admin n’a pas configuré une URL vanity pour leur organisation d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="32f0f-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="32f0f-109">Tant que le compte d’utilisateur est en ligne et n’a pas une URL de courtoisie, ils pourront toujours voir l’expérience même si leur organisation a certains comptes d’utilisateurs qui sont hébergées sur site.</span><span class="sxs-lookup"><span data-stu-id="32f0f-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="32f0f-110">Les utilisateurs qui ont des utilisateurs comptes locaux (qu’ils aient une URL vanity ou non) ou sont gérés par Microsoft verront l’expérience Lync dans Outlook web app.</span><span class="sxs-lookup"><span data-stu-id="32f0f-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="32f0f-111">Le tableau suivant récapitule les différentes configurations dont vous disposez et le client web qui est utilisé.</span><span class="sxs-lookup"><span data-stu-id="32f0f-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="32f0f-112">**Le compte utilisateur est**</span><span class="sxs-lookup"><span data-stu-id="32f0f-112">**User account is located**</span></span> <br/> |<span data-ttu-id="32f0f-113">**Une URL de redirection vers un microsite est configurée ou il existe une configuration dédiée**</span><span class="sxs-lookup"><span data-stu-id="32f0f-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="32f0f-114">**Expérience Skype Entreprise ou Lync ?**</span><span class="sxs-lookup"><span data-stu-id="32f0f-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="32f0f-115">Online</span><span class="sxs-lookup"><span data-stu-id="32f0f-115">Online</span></span>  <br/> |<span data-ttu-id="32f0f-116">Non</span><span class="sxs-lookup"><span data-stu-id="32f0f-116">No</span></span>  <br/> |<span data-ttu-id="32f0f-117">Expérience Web Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="32f0f-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="32f0f-118">Online</span><span class="sxs-lookup"><span data-stu-id="32f0f-118">Online</span></span>  <br/> |<span data-ttu-id="32f0f-119">Oui</span><span class="sxs-lookup"><span data-stu-id="32f0f-119">Yes</span></span>  <br/> |<span data-ttu-id="32f0f-120">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="32f0f-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="32f0f-121">Hybride mais domicilié en ligne</span><span class="sxs-lookup"><span data-stu-id="32f0f-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="32f0f-122">Non</span><span class="sxs-lookup"><span data-stu-id="32f0f-122">No</span></span>  <br/> |<span data-ttu-id="32f0f-123">Expérience Web Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="32f0f-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="32f0f-124">Hybride mais domicilié en ligne</span><span class="sxs-lookup"><span data-stu-id="32f0f-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="32f0f-125">Oui</span><span class="sxs-lookup"><span data-stu-id="32f0f-125">Yes</span></span>  <br/> |<span data-ttu-id="32f0f-126">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="32f0f-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="32f0f-127">Hybride mais domicilié sur site</span><span class="sxs-lookup"><span data-stu-id="32f0f-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="32f0f-128">Non</span><span class="sxs-lookup"><span data-stu-id="32f0f-128">No</span></span>  <br/> |<span data-ttu-id="32f0f-129">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="32f0f-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="32f0f-130">Hybride mais domicilié sur site</span><span class="sxs-lookup"><span data-stu-id="32f0f-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="32f0f-131">Oui</span><span class="sxs-lookup"><span data-stu-id="32f0f-131">Yes</span></span>  <br/> |<span data-ttu-id="32f0f-132">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="32f0f-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="32f0f-133">Pur sur prem</span><span class="sxs-lookup"><span data-stu-id="32f0f-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="32f0f-134">Non</span><span class="sxs-lookup"><span data-stu-id="32f0f-134">No</span></span>  <br/> |<span data-ttu-id="32f0f-135">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="32f0f-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="32f0f-136">Pur sur prem</span><span class="sxs-lookup"><span data-stu-id="32f0f-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="32f0f-137">Oui</span><span class="sxs-lookup"><span data-stu-id="32f0f-137">Yes</span></span>  <br/> |<span data-ttu-id="32f0f-138">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="32f0f-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="32f0f-139">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="32f0f-139">Related topics</span></span>
[<span data-ttu-id="32f0f-140">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="32f0f-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="32f0f-141">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="32f0f-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 