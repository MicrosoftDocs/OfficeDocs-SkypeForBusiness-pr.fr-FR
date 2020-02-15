---
title: Planifier le contrôle d’appel distant dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Le contrôle d’appel distant était une fonctionnalité dans les versions précédentes de Lync Server, qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server. Dans Skype entreprise Server, cette fonctionnalité a été remplacée par l’appel via le bureau. Dans les versions client pour Skype entreprise Server 2015 et en aval, le contrôle d’appel distant n’est plus disponible à configurer dans le client et a été supprimé pour être utilisé.
ms.openlocfilehash: 788939c392b1d86d14590232c19979e664fa0c09
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982799"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="0f6f5-105">Planifier le contrôle d’appel distant dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="0f6f5-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="0f6f5-106">Le contrôle d’appel distant était une fonctionnalité dans les versions précédentes de Lync Server, qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0f6f5-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="0f6f5-107">Dans Skype entreprise Server, cette fonctionnalité a été remplacée par l’appel via le bureau.</span><span class="sxs-lookup"><span data-stu-id="0f6f5-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="0f6f5-108">*Dans les versions client pour Skype entreprise Server 2015 et en aval, le contrôle d’appel distant n’est plus disponible à configurer dans le client et a été supprimé pour être utilisé.*</span><span class="sxs-lookup"><span data-stu-id="0f6f5-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="0f6f5-109">Contrôle d’appel distant les utilisateurs de votre organisation qui sont hébergés sur des serveurs frontaux exécutant Lync Server peuvent continuer à utiliser le contrôle d’appel distant, même s’ils utilisent un client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="0f6f5-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="0f6f5-110">Toutefois, pour tous les utilisateurs hébergés sur Skype entreprise Server, le contrôle d’appel distant n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="0f6f5-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="0f6f5-111">Consultez le tableau suivant pour les combinaisons serveur/client et s’ils peuvent prendre en charge le contrôle d’appel distant ou l’appel via le bureau.</span><span class="sxs-lookup"><span data-stu-id="0f6f5-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="0f6f5-112">**Client Skype entreprise avec interface utilisateur Skype activée**</span><span class="sxs-lookup"><span data-stu-id="0f6f5-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="0f6f5-113">**Client Skype entreprise avec interface utilisateur Lync activée**</span><span class="sxs-lookup"><span data-stu-id="0f6f5-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="0f6f5-114">**Client Skype entreprise 2016**</span><span class="sxs-lookup"><span data-stu-id="0f6f5-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="0f6f5-115">**Client Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="0f6f5-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="0f6f5-116">**Client Lync 2010**</span><span class="sxs-lookup"><span data-stu-id="0f6f5-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0f6f5-117">Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0f6f5-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="0f6f5-118">Appel via le Bureau</span><span class="sxs-lookup"><span data-stu-id="0f6f5-118">Call via Work</span></span>  <br/> |<span data-ttu-id="0f6f5-119">1 </span><span class="sxs-lookup"><span data-stu-id="0f6f5-119">1</span></span> <br/> |<span data-ttu-id="0f6f5-120">Appel via le Bureau</span><span class="sxs-lookup"><span data-stu-id="0f6f5-120">Call via Work</span></span>  <br/> |<span data-ttu-id="0f6f5-121">1 </span><span class="sxs-lookup"><span data-stu-id="0f6f5-121">1</span></span> <br/> |<span data-ttu-id="0f6f5-122">1 </span><span class="sxs-lookup"><span data-stu-id="0f6f5-122">1</span></span> <br/> |
| <span data-ttu-id="0f6f5-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f6f5-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="0f6f5-124">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="0f6f5-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="0f6f5-125">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="0f6f5-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="0f6f5-126">1 </span><span class="sxs-lookup"><span data-stu-id="0f6f5-126">1</span></span> <br/> |<span data-ttu-id="0f6f5-127">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="0f6f5-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="0f6f5-128">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="0f6f5-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="0f6f5-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="0f6f5-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="0f6f5-130">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="0f6f5-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="0f6f5-131">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="0f6f5-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="0f6f5-132">1 </span><span class="sxs-lookup"><span data-stu-id="0f6f5-132">1</span></span> <br/> |<span data-ttu-id="0f6f5-133">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="0f6f5-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="0f6f5-134">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="0f6f5-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="0f6f5-135">Aucune des fonctionnalités n’est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="0f6f5-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="0f6f5-136">Pour plus d’informations, reportez-vous à [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) dans la documentation Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0f6f5-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0f6f5-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0f6f5-137">See also</span></span>

[<span data-ttu-id="0f6f5-138">Planifier l’appel via le bureau dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0f6f5-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="0f6f5-139">Comparaison des fonctionnalités des clients de bureau pour Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="0f6f5-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="0f6f5-140">Passer un appel Skype entreprise mais utiliser votre téléphone de bureau PBX pour l’audio</span><span class="sxs-lookup"><span data-stu-id="0f6f5-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

