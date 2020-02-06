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
description: Le contrôle d’appel distant était une fonctionnalité des versions précédentes de Lync Server, qui permettaient aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server. Dans Skype entreprise Server, cette fonction a été remplacée par un appel via le travail. Dans les versions de client de Skype entreprise Server 2015 et en passant à la reprise, le contrôle d’appel distant n’est plus disponible dans le client et a été supprimé pour une utilisation.
ms.openlocfilehash: 67010a0bc74ef46dcf204e3b2a905be87c182daf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802504"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="51fe2-105">Planifier le contrôle d’appel distant dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="51fe2-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="51fe2-106">Le contrôle d’appel distant était une fonctionnalité des versions précédentes de Lync Server, qui permettaient aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server.</span><span class="sxs-lookup"><span data-stu-id="51fe2-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="51fe2-107">Dans Skype entreprise Server, cette fonction a été remplacée par un appel via le travail.</span><span class="sxs-lookup"><span data-stu-id="51fe2-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="51fe2-108">*Dans les versions de client de Skype entreprise Server 2015 et en passant à la reprise, le contrôle d’appel distant n’est plus disponible dans le client et a été supprimé pour une utilisation.*</span><span class="sxs-lookup"><span data-stu-id="51fe2-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="51fe2-109">Contrôle d’appel distant les utilisateurs de votre organisation qui résident sur des serveurs frontaux exécutant Lync Server peuvent continuer à utiliser le contrôle d’appel distant, même s’ils utilisent un client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="51fe2-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="51fe2-110">Toutefois, pour les utilisateurs hébergés sur Skype entreprise Server, le contrôle d’appel distant n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="51fe2-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="51fe2-111">Consultez le tableau suivant pour les combinaisons serveur/client et pour savoir si elles peuvent prendre en charge le contrôle d’appel distant ou un appel via le bureau.</span><span class="sxs-lookup"><span data-stu-id="51fe2-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="51fe2-112">**Client Skype entreprise avec interface utilisateur Skype activée**</span><span class="sxs-lookup"><span data-stu-id="51fe2-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="51fe2-113">**Client Skype entreprise avec interface utilisateur Lync activée**</span><span class="sxs-lookup"><span data-stu-id="51fe2-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="51fe2-114">**Client 2016 Skype entreprise**</span><span class="sxs-lookup"><span data-stu-id="51fe2-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="51fe2-115">**Client 2013 Lync**</span><span class="sxs-lookup"><span data-stu-id="51fe2-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="51fe2-116">**Client Lync 2010**</span><span class="sxs-lookup"><span data-stu-id="51fe2-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="51fe2-117">Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="51fe2-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="51fe2-118">Appel via le bureau</span><span class="sxs-lookup"><span data-stu-id="51fe2-118">Call via Work</span></span>  <br/> |<span data-ttu-id="51fe2-119">1</span><span class="sxs-lookup"><span data-stu-id="51fe2-119">1</span></span> <br/> |<span data-ttu-id="51fe2-120">Appel via le bureau</span><span class="sxs-lookup"><span data-stu-id="51fe2-120">Call via Work</span></span>  <br/> |<span data-ttu-id="51fe2-121">1</span><span class="sxs-lookup"><span data-stu-id="51fe2-121">1</span></span> <br/> |<span data-ttu-id="51fe2-122">1</span><span class="sxs-lookup"><span data-stu-id="51fe2-122">1</span></span> <br/> |
| <span data-ttu-id="51fe2-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51fe2-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="51fe2-124">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="51fe2-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="51fe2-125">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="51fe2-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="51fe2-126">1</span><span class="sxs-lookup"><span data-stu-id="51fe2-126">1</span></span> <br/> |<span data-ttu-id="51fe2-127">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="51fe2-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="51fe2-128">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="51fe2-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="51fe2-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="51fe2-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="51fe2-130">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="51fe2-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="51fe2-131">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="51fe2-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="51fe2-132">1</span><span class="sxs-lookup"><span data-stu-id="51fe2-132">1</span></span> <br/> |<span data-ttu-id="51fe2-133">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="51fe2-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="51fe2-134">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="51fe2-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="51fe2-135">Aucune de ces fonctionnalités n’est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="51fe2-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="51fe2-136">Pour plus d’informations, reportez-vous à [contrôle d’appel distant](https://go.microsoft.com/fwlink/p/?LinkId=530208) dans la documentation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="51fe2-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="51fe2-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="51fe2-137">See also</span></span>

[<span data-ttu-id="51fe2-138">Planifier un appel via le travail dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="51fe2-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="51fe2-139">Comparaison des fonctionnalités des clients de bureau pour Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="51fe2-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="51fe2-140">Passer un appel Skype entreprise en utilisant votre téléphone de bureau PBX pour le son</span><span class="sxs-lookup"><span data-stu-id="51fe2-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

