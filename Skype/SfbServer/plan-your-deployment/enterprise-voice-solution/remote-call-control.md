---
title: Planification du contrôle d’appel distant dans Skype Entreprise 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Contrôle d’appel distant est une fonctionnalité dans les versions précédentes de Lync Server qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server. Dans Skype pour Business Server, cette fonctionnalité a été remplacée par un appel via le bureau. Dans les versions du client pour Skype pour Business Server 2015 et passer des appels à distance avant le contrôle n’est plus disponible pour configurer dans le client et a été supprimé à utiliser.
ms.openlocfilehash: dc71f8307fe17b9a4654bc931a621f934fd3eb02
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-remote-call-control-in-skype-for-business-2015"></a><span data-ttu-id="76859-105">Planification du contrôle d’appel distant dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="76859-105">Plan for remote call control in Skype for Business 2015</span></span>
 
<span data-ttu-id="76859-106">Contrôle d’appel distant est une fonctionnalité dans les versions précédentes de Lync Server qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server.</span><span class="sxs-lookup"><span data-stu-id="76859-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="76859-107">Dans Skype pour Business Server, cette fonctionnalité a été remplacée par un appel via le bureau.</span><span class="sxs-lookup"><span data-stu-id="76859-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="76859-108">*Dans les versions du client pour Skype pour Business Server 2015 et passer des appels à distance avant le contrôle n’est plus disponible pour configurer dans le client et a été supprimé à utiliser.*</span><span class="sxs-lookup"><span data-stu-id="76859-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="76859-109">Appel distant contrôle les utilisateurs dans votre organisation qui sont hébergés sur les serveurs frontaux exécutant Lync Server peuvent continuer à utiliser le contrôle d’appel distant, même s’ils utilisent un Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="76859-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="76859-110">Toutefois, pour tous les utilisateurs hébergement sur Skype pour Business Server, le contrôle d’appel distant n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="76859-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="76859-111">Consultez le tableau suivant pour les combinaisons serveur/client et pour savoir si elles peuvent prendre en charge le contrôle d’appel distant ou un appel via le bureau.</span><span class="sxs-lookup"><span data-stu-id="76859-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="76859-112">**Skype pour Business 2015 With Skype interface utilisateur du Client activé**</span><span class="sxs-lookup"><span data-stu-id="76859-112">**Skype for Business 2015 Client With Skype UI enabled**</span></span>|<span data-ttu-id="76859-113">**Skype pour Business 2015 With Lync interface utilisateur du Client activé**</span><span class="sxs-lookup"><span data-stu-id="76859-113">**Skype for Business 2015 Client With Lync UI enabled**</span></span>|<span data-ttu-id="76859-114">**Skype pour Business 2016 Client**</span><span class="sxs-lookup"><span data-stu-id="76859-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="76859-115">**Client de Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="76859-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="76859-116">**Client Lync 2010**</span><span class="sxs-lookup"><span data-stu-id="76859-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="76859-117">Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="76859-117">Skype for Business Server 2015</span></span> <br/> |<span data-ttu-id="76859-118">Appel via le bureau</span><span class="sxs-lookup"><span data-stu-id="76859-118">Call via Work</span></span>  <br/> |<span data-ttu-id="76859-119">1</span><span class="sxs-lookup"><span data-stu-id="76859-119">1</span></span> <br/> |<span data-ttu-id="76859-120">Appel via le bureau</span><span class="sxs-lookup"><span data-stu-id="76859-120">Call via Work</span></span>  <br/> |<span data-ttu-id="76859-121">1</span><span class="sxs-lookup"><span data-stu-id="76859-121">1</span></span> <br/> |<span data-ttu-id="76859-122">1</span><span class="sxs-lookup"><span data-stu-id="76859-122">1</span></span> <br/> |
| <span data-ttu-id="76859-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76859-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="76859-124">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="76859-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="76859-125">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="76859-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="76859-126">1</span><span class="sxs-lookup"><span data-stu-id="76859-126">1</span></span> <br/> |<span data-ttu-id="76859-127">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="76859-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="76859-128">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="76859-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="76859-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="76859-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="76859-130">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="76859-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="76859-131">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="76859-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="76859-132">1</span><span class="sxs-lookup"><span data-stu-id="76859-132">1</span></span> <br/> |<span data-ttu-id="76859-133">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="76859-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="76859-134">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="76859-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="76859-135">Aucune fonctionnalité n’est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="76859-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="76859-136">Pour plus d’informations, voir [Contrôle d’appel distant](https://go.microsoft.com/fwlink/p/?LinkId=530208) dans la documentation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="76859-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="76859-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="76859-137">See also</span></span>

#### 

[<span data-ttu-id="76859-138">Plan pour un appel via le bureau dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="76859-138">Plan for Call Via Work in Skype for Business Server 2015</span></span>](call-via-work.md)
  
[<span data-ttu-id="76859-139">Comparaison des fonctionnalités client de bureau pour Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="76859-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)
#### 

[<span data-ttu-id="76859-140">Rendre un Skype pour l’appel de l’entreprise, mais utilisez votre téléphone de bureau PBX pour l’audio</span><span class="sxs-lookup"><span data-stu-id="76859-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

