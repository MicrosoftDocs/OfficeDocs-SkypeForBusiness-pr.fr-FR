---
title: Planifier le contrôle d’appel distant dans Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Le contrôle d’appel distant était une fonctionnalité des versions précédentes de Lync Server qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server. Dans Skype Entreprise Server, cette fonctionnalité a été remplacée par Appel via le travail. Dans les versions client de Skype Entreprise Server 2015 et à l’avenir, le contrôle d’appel distant n’est plus disponible pour la configuration dans le client et a été supprimé pour utilisation.
ms.openlocfilehash: b48eeed656f5889d08fe892da7d7a6896f8a11c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813514"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="4a142-105">Planifier le contrôle d’appel distant dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="4a142-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="4a142-106">Le contrôle d’appel distant était une fonctionnalité des versions précédentes de Lync Server qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a142-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="4a142-107">Dans Skype Entreprise Server, cette fonctionnalité a été remplacée par Appel via le travail.</span><span class="sxs-lookup"><span data-stu-id="4a142-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="4a142-108">*Dans les versions client de Skype Entreprise Server 2015 et à l’avenir, le contrôle d’appel distant n’est plus disponible pour la configuration dans le client et a été supprimé pour utilisation.*</span><span class="sxs-lookup"><span data-stu-id="4a142-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="4a142-109">Les utilisateurs du contrôle d’appel distant de votre organisation qui sont situés sur des serveurs frontaux exécutant Lync Server peuvent continuer à utiliser le contrôle d’appel distant, même s’ils utilisent un client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="4a142-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="4a142-110">Toutefois, pour les utilisateurs de Skype Entreprise Server, le contrôle d’appel distant n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="4a142-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="4a142-111">Consultez le tableau suivant pour les combinaisons serveur/client et pour savoir si elles peuvent prendre en charge le contrôle d’appel distant ou l’appel via le travail.</span><span class="sxs-lookup"><span data-stu-id="4a142-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="4a142-112">**Client Skype Entreprise avec l’interface utilisateur Skype activée**</span><span class="sxs-lookup"><span data-stu-id="4a142-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="4a142-113">**Client Skype Entreprise avec l’interface utilisateur Lync activée**</span><span class="sxs-lookup"><span data-stu-id="4a142-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="4a142-114">**Client Skype Entreprise 2016**</span><span class="sxs-lookup"><span data-stu-id="4a142-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="4a142-115">**Lync 2013 Client**</span><span class="sxs-lookup"><span data-stu-id="4a142-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="4a142-116">**Client Lync 2010**</span><span class="sxs-lookup"><span data-stu-id="4a142-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="4a142-117">Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4a142-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="4a142-118">Appel via le travail</span><span class="sxs-lookup"><span data-stu-id="4a142-118">Call via Work</span></span>  <br/> |<span data-ttu-id="4a142-119">1 </span><span class="sxs-lookup"><span data-stu-id="4a142-119">1</span></span> <br/> |<span data-ttu-id="4a142-120">Appel via le travail</span><span class="sxs-lookup"><span data-stu-id="4a142-120">Call via Work</span></span>  <br/> |<span data-ttu-id="4a142-121">1 </span><span class="sxs-lookup"><span data-stu-id="4a142-121">1</span></span> <br/> |<span data-ttu-id="4a142-122">1 </span><span class="sxs-lookup"><span data-stu-id="4a142-122">1</span></span> <br/> |
| <span data-ttu-id="4a142-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a142-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="4a142-124">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="4a142-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="4a142-125">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="4a142-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="4a142-126">1 </span><span class="sxs-lookup"><span data-stu-id="4a142-126">1</span></span> <br/> |<span data-ttu-id="4a142-127">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="4a142-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="4a142-128">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="4a142-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="4a142-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="4a142-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="4a142-130">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="4a142-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="4a142-131">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="4a142-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="4a142-132">1 </span><span class="sxs-lookup"><span data-stu-id="4a142-132">1</span></span> <br/> |<span data-ttu-id="4a142-133">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="4a142-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="4a142-134">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="4a142-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="4a142-135">Aucune des fonctionnalités n’est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="4a142-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="4a142-136">Pour plus d’informations, [voir Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) dans la documentation Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a142-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4a142-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4a142-137">See also</span></span>

[<span data-ttu-id="4a142-138">Planifier l’appel via le travail dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4a142-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="4a142-139">Comparaison des fonctionnalités du client de bureau pour Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="4a142-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="4a142-140">Effectuer un appel Skype Entreprise, mais utiliser votre téléphone de bureau PBX pour l’audio</span><span class="sxs-lookup"><span data-stu-id="4a142-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

