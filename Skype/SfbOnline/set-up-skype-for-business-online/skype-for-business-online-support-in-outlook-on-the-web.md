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
description: Outlook sur le Web (Outlook Web App) dans Office 365 propose un client Web Skype entreprise de base à partir de la barre de navigation. Ce client de base est disponible pour les utilisateurs en ligne dont l’administrateur n’a pas configuré d’URL entraînant pour leur organisation Office 365. Tant que le compte de l’utilisateur est en ligne et qu’il n’a pas d’URL entraînant, il verra toujours l’environnement, même si son organisation dispose de comptes d’utilisateurs hébergés sur site. Les utilisateurs disposant de comptes d’utilisateurs locaux (qu’ils possèdent ou non une URL entraînant) ou gérés par Microsoft pourront voir l’environnement Lync dans Outlook Web App.
ms.openlocfilehash: 7eab3ce7c8d6ea8c1f004559ea92f64f554fb010
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692849"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="27176-106">Prise en charge de Skype Entreprise Online avec Outlook sur le Web</span><span class="sxs-lookup"><span data-stu-id="27176-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="27176-p102">Outlook sur le Web (Outlook Web App) dans Office 365 propose un client Web Skype entreprise de base à partir de la barre de navigation. Ce client de base est disponible pour les utilisateurs en ligne dont l’administrateur n’a pas configuré d’URL entraînant pour leur organisation Office 365. Tant que le compte de l’utilisateur est en ligne et qu’il n’a pas d’URL entraînant, il verra toujours l’environnement, même si son organisation dispose de comptes d’utilisateurs hébergés sur site. Les utilisateurs disposant de comptes d’utilisateurs locaux (qu’ils possèdent ou non une URL entraînant) ou gérés par Microsoft pourront voir l’environnement Lync dans Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="27176-p102">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar. This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization. As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises. Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="27176-111">Le tableau suivant résume les différentes opérations d’installation que vous pouvez avoir et le client Web utilisé.</span><span class="sxs-lookup"><span data-stu-id="27176-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="27176-112">**Le compte utilisateur est**</span><span class="sxs-lookup"><span data-stu-id="27176-112">**User account is located**</span></span> <br/> |<span data-ttu-id="27176-113">**Une URL de redirection vers un microsite est configurée ou il existe une configuration dédiée**</span><span class="sxs-lookup"><span data-stu-id="27176-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="27176-114">**Expérience Skype Entreprise ou Lync ?**</span><span class="sxs-lookup"><span data-stu-id="27176-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="27176-115">Online</span><span class="sxs-lookup"><span data-stu-id="27176-115">Online</span></span>  <br/> |<span data-ttu-id="27176-116">Non</span><span class="sxs-lookup"><span data-stu-id="27176-116">No</span></span>  <br/> |<span data-ttu-id="27176-117">Expérience Web Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="27176-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="27176-118">Online</span><span class="sxs-lookup"><span data-stu-id="27176-118">Online</span></span>  <br/> |<span data-ttu-id="27176-119">Oui</span><span class="sxs-lookup"><span data-stu-id="27176-119">Yes</span></span>  <br/> |<span data-ttu-id="27176-120">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="27176-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="27176-121">Hybride mais domicilié en ligne</span><span class="sxs-lookup"><span data-stu-id="27176-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="27176-122">Non</span><span class="sxs-lookup"><span data-stu-id="27176-122">No</span></span>  <br/> |<span data-ttu-id="27176-123">Expérience Web Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="27176-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="27176-124">Hybride mais domicilié en ligne</span><span class="sxs-lookup"><span data-stu-id="27176-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="27176-125">Oui</span><span class="sxs-lookup"><span data-stu-id="27176-125">Yes</span></span>  <br/> |<span data-ttu-id="27176-126">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="27176-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="27176-127">Hybride mais domicilié sur site</span><span class="sxs-lookup"><span data-stu-id="27176-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="27176-128">Non</span><span class="sxs-lookup"><span data-stu-id="27176-128">No</span></span>  <br/> |<span data-ttu-id="27176-129">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="27176-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="27176-130">Hybride mais domicilié sur site</span><span class="sxs-lookup"><span data-stu-id="27176-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="27176-131">Oui</span><span class="sxs-lookup"><span data-stu-id="27176-131">Yes</span></span>  <br/> |<span data-ttu-id="27176-132">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="27176-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="27176-133">Pure sur locaux</span><span class="sxs-lookup"><span data-stu-id="27176-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="27176-134">Non</span><span class="sxs-lookup"><span data-stu-id="27176-134">No</span></span>  <br/> |<span data-ttu-id="27176-135">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="27176-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="27176-136">Pure sur locaux</span><span class="sxs-lookup"><span data-stu-id="27176-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="27176-137">Oui</span><span class="sxs-lookup"><span data-stu-id="27176-137">Yes</span></span>  <br/> |<span data-ttu-id="27176-138">Expérience Web Lync</span><span class="sxs-lookup"><span data-stu-id="27176-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="27176-139">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="27176-139">Related topics</span></span>
[<span data-ttu-id="27176-140">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="27176-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="27176-141">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="27176-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
