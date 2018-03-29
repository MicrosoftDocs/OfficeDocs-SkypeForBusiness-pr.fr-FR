---
title: Planification du contrôle d’appel distant dans Skype Entreprise 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Contrôle d’appel distant est une fonctionnalité dans les versions précédentes de Lync Server, qui a permis aux utilisateurs de contrôler leur téléphone PBX avec Lync Server. Dans Skype pour le serveur de l’entreprise, cette fonctionnalité a été remplacée à appeler Via le travail. Dans les versions de client pour Skype Business Server 2015 et allant vers l’avant, à distance le contrôle n’est plus disponible pour configurer le client et a été supprimée pour une utilisation.
ms.openlocfilehash: 2db859ad33a697d5bca632ca9b6677a3a67bd103
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-remote-call-control-in-skype-for-business-2015"></a><span data-ttu-id="813fc-105">Planification du contrôle d’appel distant dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="813fc-105">Plan for remote call control in Skype for Business 2015</span></span>
 
<span data-ttu-id="813fc-106">Contrôle d’appel distant est une fonctionnalité dans les versions précédentes de Lync Server, qui a permis aux utilisateurs de contrôler leur téléphone PBX avec Lync Server.</span><span class="sxs-lookup"><span data-stu-id="813fc-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="813fc-107">Dans Skype pour le serveur de l’entreprise, cette fonctionnalité a été remplacée à appeler Via le travail.</span><span class="sxs-lookup"><span data-stu-id="813fc-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="813fc-108">*Dans les versions de client pour Skype Business Server 2015 et allant vers l’avant, à distance le contrôle n’est plus disponible pour configurer le client et a été supprimée pour une utilisation.*</span><span class="sxs-lookup"><span data-stu-id="813fc-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="813fc-109">Appel distant contrôle les utilisateurs de votre organisation qui sont hébergées sur les serveurs frontaux exécutant Lync Server peuvent continuer à utiliser le contrôle d’appel distant, même s’ils utilisent un Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="813fc-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="813fc-110">Toutefois, pour tous les utilisateurs hébergement sur Skype pour le serveur de l’entreprise, contrôle d’appel distant n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="813fc-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="813fc-111">Consultez le tableau suivant pour les combinaisons serveur/client et pour savoir si elles peuvent prendre en charge le contrôle d’appel distant ou un appel via le bureau.</span><span class="sxs-lookup"><span data-stu-id="813fc-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="813fc-112">**Skype pour entreprise 2015 With Skype interface utilisateur du Client activé**</span><span class="sxs-lookup"><span data-stu-id="813fc-112">**Skype for Business 2015 Client With Skype UI enabled**</span></span>|<span data-ttu-id="813fc-113">**Skype pour entreprise 2015 avec Lync interface utilisateur du Client activé**</span><span class="sxs-lookup"><span data-stu-id="813fc-113">**Skype for Business 2015 Client With Lync UI enabled**</span></span>|<span data-ttu-id="813fc-114">**Skype pour entreprise 2016 Client**</span><span class="sxs-lookup"><span data-stu-id="813fc-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="813fc-115">**Client de Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="813fc-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="813fc-116">**Client de Lync 2010**</span><span class="sxs-lookup"><span data-stu-id="813fc-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="813fc-117">Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="813fc-117">Skype for Business Server 2015</span></span> <br/> |<span data-ttu-id="813fc-118">Appel via le bureau</span><span class="sxs-lookup"><span data-stu-id="813fc-118">Call via Work</span></span>  <br/> |<span data-ttu-id="813fc-119">1</span><span class="sxs-lookup"><span data-stu-id="813fc-119">1</span></span> <br/> |<span data-ttu-id="813fc-120">Appel via le bureau</span><span class="sxs-lookup"><span data-stu-id="813fc-120">Call via Work</span></span>  <br/> |<span data-ttu-id="813fc-121">1</span><span class="sxs-lookup"><span data-stu-id="813fc-121">1</span></span> <br/> |<span data-ttu-id="813fc-122">1</span><span class="sxs-lookup"><span data-stu-id="813fc-122">1</span></span> <br/> |
| <span data-ttu-id="813fc-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="813fc-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="813fc-124">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="813fc-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="813fc-125">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="813fc-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="813fc-126">1</span><span class="sxs-lookup"><span data-stu-id="813fc-126">1</span></span> <br/> |<span data-ttu-id="813fc-127">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="813fc-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="813fc-128">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="813fc-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="813fc-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="813fc-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="813fc-130">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="813fc-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="813fc-131">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="813fc-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="813fc-132">1</span><span class="sxs-lookup"><span data-stu-id="813fc-132">1</span></span> <br/> |<span data-ttu-id="813fc-133">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="813fc-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="813fc-134">Contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="813fc-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="813fc-135">Aucune fonctionnalité n’est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="813fc-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="813fc-136">Pour plus d’informations, consultez [Contrôle d’appel distant](https://go.microsoft.com/fwlink/p/?LinkId=530208) dans la documentation de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="813fc-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="813fc-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="813fc-137">See also</span></span>

#### 

[<span data-ttu-id="813fc-138">Plan pour un appel Via le travail dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="813fc-138">Plan for Call Via Work in Skype for Business Server 2015</span></span>](call-via-work.md)
  
[<span data-ttu-id="813fc-139">Comparaison des fonctionnalités client de bureau pour Skype pour entreprise</span><span class="sxs-lookup"><span data-stu-id="813fc-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)
#### 

[<span data-ttu-id="813fc-140">Rendre un Skype pour l’appel de l’entreprise, mais utiliser votre téléphone de bureau PBX pour l’audio</span><span class="sxs-lookup"><span data-stu-id="813fc-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

