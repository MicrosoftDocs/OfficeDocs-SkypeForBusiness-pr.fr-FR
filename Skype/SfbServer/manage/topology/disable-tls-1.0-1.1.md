---
title: Désactiver TLS 1.0/1.1 dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Résumé : Préparez et implémentez la désactivation de TLS 1.0 et 1.1 dans vos environnements.'
ms.openlocfilehash: da76280540f9d18435ed929aace6cf6fc439a4cf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826394"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="e30e0-103">Désactiver TLS 1.0/1.1 dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="e30e0-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="e30e0-104">L’objectif de cet article est de fournir les instructions nécessaires pour préparer et implémenter la désactivation de TLS 1.0 et 1.1 dans vos environnements.</span><span class="sxs-lookup"><span data-stu-id="e30e0-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="e30e0-105">Ce processus nécessite une planification et une préparation complètes.</span><span class="sxs-lookup"><span data-stu-id="e30e0-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="e30e0-106">Veuillez consulter attentivement toutes les informations de cet article lorsque vous planifiez la désactivation de TLS 1.0 et 1.1 pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e30e0-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="e30e0-107">Notez que de nombreuses dépendances externes et conditions de connectivité peuvent être touchées par la désactivation de TLS 1.0/1.1, ce qui justifie une planification et des tests approfondis.</span><span class="sxs-lookup"><span data-stu-id="e30e0-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="e30e0-108">Contenu de cet article</span><span class="sxs-lookup"><span data-stu-id="e30e0-108">In this article</span></span>

- [<span data-ttu-id="e30e0-109">Arrière-plan et étendue</span><span class="sxs-lookup"><span data-stu-id="e30e0-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="e30e0-110">Conditions préalables et processus</span><span class="sxs-lookup"><span data-stu-id="e30e0-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="e30e0-111">Scénarios de déploiement avancés</span><span class="sxs-lookup"><span data-stu-id="e30e0-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="e30e0-112">Contexte</span><span class="sxs-lookup"><span data-stu-id="e30e0-112">Background</span></span>

<span data-ttu-id="e30e0-113">Les principaux facteurs de désactivation de TLS 1.0 et 1.1 pour Skype Entreprise Server local sont les normes PCI (Payment Card Industry) Security Standards Et Federal Information Processing Standards.</span><span class="sxs-lookup"><span data-stu-id="e30e0-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="e30e0-114">Pour plus d’informations sur les exigences PCI, voir [ici.](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)</span><span class="sxs-lookup"><span data-stu-id="e30e0-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="e30e0-115">Microsoft ne peut pas fournir de conseils sur la nécessité ou non pour votre organisation de respecter ces exigences ou d’autres.</span><span class="sxs-lookup"><span data-stu-id="e30e0-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="e30e0-116">Vous devez déterminer s’il est nécessaire de désactiver TLS 1.0 et/ou 1.1 dans vos environnements.</span><span class="sxs-lookup"><span data-stu-id="e30e0-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="e30e0-117">Microsoft a produit un livre blanc sur TLS disponible ici [et](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)nous vous recommandons également la lecture en arrière-plan disponible dans ce [blog Exchange.](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="e30e0-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="e30e0-118">Étendue de prise en charge</span><span class="sxs-lookup"><span data-stu-id="e30e0-118">Supportability Scope</span></span>

<span data-ttu-id="e30e0-119">*L’étendue* fait référence aux limites de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="e30e0-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="e30e0-120">*Les tests* complets et pris en charge signifient que nous activons entièrement et avons testé la désactivation de TLS 1.0 et 1.1 pour les versions de produits répertoriées.</span><span class="sxs-lookup"><span data-stu-id="e30e0-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="e30e0-121">*L’examen en cours* signifie simplement cela ; Nous sommes activement en train d’examiner l’application de ces produits à l’étendue de la désactivation de la prise en charge de TLS.</span><span class="sxs-lookup"><span data-stu-id="e30e0-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="e30e0-122">*Hors de portée signifie* que ces versions de produit ne peuvent pas désactiver TLS 1.0 ou 1.1 et ne fonctionneront pas, avec des exceptions notées.</span><span class="sxs-lookup"><span data-stu-id="e30e0-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="e30e0-123">Serveurs entièrement testés et pris en charge</span><span class="sxs-lookup"><span data-stu-id="e30e0-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="e30e0-124">Skype Entreprise Server 2019 CU1 17.0.2046.123 (juin 2019) ou supérieur</span><span class="sxs-lookup"><span data-stu-id="e30e0-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="e30e0-125">Skype Entreprise Server 2015 CU9 6.0.9319.548 (mai 2019) ou version supérieure sur Windows Server 2012 (avec la mise à jour KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou en cours de mise à jour), 2012 R2 ou 2016.</span><span class="sxs-lookup"><span data-stu-id="e30e0-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="e30e0-126">Skype Entreprise Server 2015 mis à niveau sur place, avec CU9 6.0.9319.548 (mai 2019) ou version supérieure sur Windows Server 2008 R2, 2012 (avec la mise à jour KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou de la mise à jour de super) ou 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="e30e0-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="e30e0-127">Recommandations pour Exchange Connectivity et Outlook Web App Exchange Server 2010 SP3 RU19 ou une édition [supérieure](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="e30e0-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="e30e0-128">Survivable Branch Appliance (SBA) avec Skype Entreprise Server 2015 CU6 HF2 ou version supérieure (confirmez auprès de votre fournisseur qu’il a empaqueté les mises à jour appropriées et qu’il a été mis à disposition pour votre appliance)</span><span class="sxs-lookup"><span data-stu-id="e30e0-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropriate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="e30e0-129">Serveur Survivable Branch Server (SBS) avec Skype Entreprise Server 2015 CU6 HF2 ou supérieur</span><span class="sxs-lookup"><span data-stu-id="e30e0-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="e30e0-130">Rôle **Edge** Lync Server 2013 uniquement, car le rôle Edge ne dépend pas de Windows Fabric 1.0.</span><span class="sxs-lookup"><span data-stu-id="e30e0-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="e30e0-131">Clients entièrement testés et pris en charge</span><span class="sxs-lookup"><span data-stu-id="e30e0-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="e30e0-132">Client de bureau Lync 2013 (Skype Entreprise), MSI et C2R, y compris Basic [15.0.5023.1000 ou](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334) version supérieure</span><span class="sxs-lookup"><span data-stu-id="e30e0-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="e30e0-133">Client de bureau Skype Entreprise 2016, MSI [16.0.4678.1000](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)ou version supérieure, y compris De base</span><span class="sxs-lookup"><span data-stu-id="e30e0-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="e30e0-134">Skype Entreprise 2016 Click to Run Nécessite les mises à jour [d’avril 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) :</span><span class="sxs-lookup"><span data-stu-id="e30e0-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="e30e0-135">Mensuelle et Semi-Annual ciblée, 16 \. 0 \. 9126 \. 2152 ou supérieure</span><span class="sxs-lookup"><span data-stu-id="e30e0-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="e30e0-136">Semi-Annual canal différé, 16 \. 0 \. 8431 \. 2242 ou supérieur</span><span class="sxs-lookup"><span data-stu-id="e30e0-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="e30e0-137">Skype Entreprise sur Mac 16.15 ou supérieur</span><span class="sxs-lookup"><span data-stu-id="e30e0-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="e30e0-138">Skype Entreprise pour iOS et Android 6.19 ou version supérieure</span><span class="sxs-lookup"><span data-stu-id="e30e0-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="e30e0-139">Salles Microsoft Teams (précédemment appelées Skype Room System V2 SRS v2) 4.0.64.0 (décembre 2018) ou une édition supérieure</span><span class="sxs-lookup"><span data-stu-id="e30e0-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="e30e0-140">Mise à jour du Surface Hub pour l’édition Team basée sur KB4499162 (mai 2019, version du système d’exploitation 15063.1835) ou version supérieure</span><span class="sxs-lookup"><span data-stu-id="e30e0-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="e30e0-141">Skype Web App 2015 CU6 HF2 ou une valeur supérieure (est intégré au serveur)</span><span class="sxs-lookup"><span data-stu-id="e30e0-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="e30e0-142">Actuellement en cours d’examen</span><span class="sxs-lookup"><span data-stu-id="e30e0-142">Currently being investigated</span></span>

- <span data-ttu-id="e30e0-143">Tableau de bord de qualité des appels (nouvelle installation après la désactivation de TLS 1.0, 1.1, voir ci-dessous)\*</span><span class="sxs-lookup"><span data-stu-id="e30e0-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="e30e0-144">Non compris</span><span class="sxs-lookup"><span data-stu-id="e30e0-144">Out of scope</span></span>

<span data-ttu-id="e30e0-145">Sauf remarque, les produits suivants ne sont pas dans l’étendue de TLS 1.0/1.1 désactiver la prise en charge et ne fonctionneront pas dans un environnement où TLS 1.0 et 1.1 ont été désactivés.</span><span class="sxs-lookup"><span data-stu-id="e30e0-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="e30e0-146">Cela signifie que si vous utilisez toujours des serveurs ou des clients hors étendue, vous devez les mettre à jour ou les supprimer si vous devez désactiver TLS 1.0/1.1 n’importe où dans votre déploiement local de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e30e0-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="e30e0-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e30e0-147">Lync Server 2013</span></span>
- <span data-ttu-id="e30e0-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e30e0-148">Lync Server 2010</span></span>
- <span data-ttu-id="e30e0-149">Windows Server 2008 ou une édition inférieure</span><span class="sxs-lookup"><span data-stu-id="e30e0-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="e30e0-150">Lync pour Mac 2011</span><span class="sxs-lookup"><span data-stu-id="e30e0-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="e30e0-151">Lync 2013 pour mobile - iOS, iPad, Android ou Windows Phone</span><span class="sxs-lookup"><span data-stu-id="e30e0-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="e30e0-152">Client Windows Store « MX » Lync</span><span class="sxs-lookup"><span data-stu-id="e30e0-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="e30e0-153">Lync Room System (alias</span><span class="sxs-lookup"><span data-stu-id="e30e0-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="e30e0-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="e30e0-154">SRSv1).</span></span> <span data-ttu-id="e30e0-155">LRS a atteint la fin de la prise en charge le 9 octobre 2018 et ne sera pas mis à jour pour prendre en charge TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="e30e0-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="e30e0-156">Tous les clients Lync 2010</span><span class="sxs-lookup"><span data-stu-id="e30e0-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="e30e0-157">Lync Phone Edition - Conseils mis à [jour ici.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)</span><span class="sxs-lookup"><span data-stu-id="e30e0-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="e30e0-158">Survivable Branch Appliance (SBA) ou Survivable Branch Server (SBS) 2013</span><span class="sxs-lookup"><span data-stu-id="e30e0-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="e30e0-159">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="e30e0-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="e30e0-160">Skype Entreprise pour Windows Phone</span><span class="sxs-lookup"><span data-stu-id="e30e0-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="e30e0-161">Exceptions</span><span class="sxs-lookup"><span data-stu-id="e30e0-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="e30e0-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e30e0-162">Lync Server 2013</span></span>

<span data-ttu-id="e30e0-163">Lync Server 2013 prend une dépendance sur Windows Fabric version 1.0.</span><span class="sxs-lookup"><span data-stu-id="e30e0-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="e30e0-164">Lors de la phase de conception de Lync Server 2013, Windows Fabric 1.0 a été choisi pour son architecture distribuée attrayante et nouvelle pour fournir la réplication, la haute disponibilité et la tolérance de panne.</span><span class="sxs-lookup"><span data-stu-id="e30e0-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="e30e0-165">Au fil du temps, Skype Entreprise Server et Windows Fabric ont considérablement amélioré cette architecture commune avec une nouvelle conception importante dans les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="e30e0-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="e30e0-166">Skype Entreprise Server 2015 actuel utilise Windows Fabric 3.0, par exemple.</span><span class="sxs-lookup"><span data-stu-id="e30e0-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="e30e0-167">Malheureusement, Windows Fabric 1.0 ne prend pas en **charge TLS 1.2.  Toutefois, nous mettons à jour Lync Server 2013 pour fonctionner avec TLS 1.2**.</span><span class="sxs-lookup"><span data-stu-id="e30e0-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="e30e0-168">Cette mise à jour sera prochainement mise à jour cumulative pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e30e0-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="e30e0-169">Nous fournissons la prise en charge de TLS 1.2 pour permettre la coexistence, la migration, la fédération et les scénarios hybrides.</span><span class="sxs-lookup"><span data-stu-id="e30e0-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="e30e0-170">Si votre organisation est tenue de désactiver TLS 1.0 et 1.1 et que vous utilisez actuellement Lync Server 2013, nous vous recommandons de commencer le processus de planification, avec la possibilité de devoir mettre à niveau sur place ou migrer côte à côte (nouveaux pools, déplacer des utilisateurs) vers Skype Entreprise Server 2015 ou version supérieure.</span><span class="sxs-lookup"><span data-stu-id="e30e0-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="e30e0-171">Vous pouvez également accélérer la migration vers Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="e30e0-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="e30e0-172">Tableau de bord de la qualité des appels</span><span class="sxs-lookup"><span data-stu-id="e30e0-172">Call Quality Dashboard</span></span>

<span data-ttu-id="e30e0-173">Le tableau de bord de qualité des appels local dépend actuellement de TLS 1.0 lors de la nouvelle installation (première installation dans vos environnements locaux).</span><span class="sxs-lookup"><span data-stu-id="e30e0-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="e30e0-174">Nous enquêtons actuellement sur ce problème et prévoyons de publier un correctif dans un futur proche.</span><span class="sxs-lookup"><span data-stu-id="e30e0-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="e30e0-175">Si vous envisagez d’installer le CQD et de désactiver TLS 1.0, nous vous recommandons d’effectuer d’abord l’installation du CQD, puis de procéder à la désactivation de TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="e30e0-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="skype-for-business-sdn-manager"></a><span data-ttu-id="e30e0-176">Gestionnaire de SDN Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="e30e0-176">Skype for Business SDN Manager</span></span>

<span data-ttu-id="e30e0-177">Skype For Business SDN Manager using SQL a database has a dependency on TLS 1.0 during new install.</span><span class="sxs-lookup"><span data-stu-id="e30e0-177">Skype for Business SDN Manager using SQL a database has a dependency on TLS 1.0 during new install.</span></span> <span data-ttu-id="e30e0-178">Si vous envisagez d’installer le Gestionnaire de SDN Skype Entreprise à l’aide de SQL une base de données et de désactiver TLS 1.0, nous vous recommandons d’effectuer d’abord le Gestionnaire de SDN Skype Entreprise, puis de procéder à la désactivation de TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="e30e0-178">If you are planning to install Skype for Business SDN Manager using SQL a database and also disable TLS 1.0, we recommend that you complete Skype for Business SDN Manager first, and then proceed with TLS 1.0 disabling.</span></span> <span data-ttu-id="e30e0-179">Si TLS 1.0 est désactivé avant l’installation, vous devez activer temporairement TLS 1.0 sur le serveur principal SQL Server qui sera utilisé pour héberger la base de données SQL du Gestionnaire de SDN Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="e30e0-179">In case TLS 1.0 was disabled prior to installation, you should temporarily enabled TLS 1.0 back in SQL Server backend server that will be used to host Skype for Business SDN Manager SQL database.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="e30e0-180">Appareils tiers</span><span class="sxs-lookup"><span data-stu-id="e30e0-180">Third-party devices</span></span>

<span data-ttu-id="e30e0-181">Sur les appareils tiers tels que les téléphones 3PIP, la vidéoconférence, les proxies inverses et les équilibreurs de charge, assurez-vous de valider la prise en charge de TLS 1.2, de tester attentivement et de contacter le fournisseur si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e30e0-181">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="e30e0-182">Considérations sur la fédération lors de la désactivation de TLS 1.0/1.1 sur les serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="e30e0-182">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="e30e0-183">Vous devez soigneusement planifier et prendre en compte l’impact de la désactivation de TLS 1.0/1.1 sur vos serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="e30e0-183">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="e30e0-184">Une fois que TLS 1.0 et 1.1 sont désactivés, il se peut que vous trouviez que les autres organisations ne peuvent plus se fédérer avec votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e30e0-184">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="e30e0-185">Vous pouvez choisir de conserver TLS 1.0/1.1 activé sur vos serveurs Edge pour maintenir la compatibilité ascendante avec les systèmes externes non corrigés (SfB 2015, Lync 2013) ou plus anciens (2010).</span><span class="sxs-lookup"><span data-stu-id="e30e0-185">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="e30e0-186">Microsoft ne peut pas fournir de conseils ou de recommandations sur le fait que votre réseau Edge (ou tout autre réseau) tombe ou non sous la norme PCI ; qui doit être déterminé par la société individuelle.</span><span class="sxs-lookup"><span data-stu-id="e30e0-186">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="e30e0-187">Skype Entreprise Online est capable de TLS 1.2 aujourd’hui, donc aucun impact sur l’environnement hybride/la fédération avec Online n’est attendu.</span><span class="sxs-lookup"><span data-stu-id="e30e0-187">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="e30e0-188">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Les passerelles Microsoft PIC sont déjà capables de TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="e30e0-188">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="e30e0-189">Conditions préalables et processus</span><span class="sxs-lookup"><span data-stu-id="e30e0-189">Prerequisites and process</span></span>

<span data-ttu-id="e30e0-190">Sauf cas mentionné ci-dessus, une fois que les serveurs hors étendue TLS 1.0 et 1.1 sont désactivés, les clients et les appareils fonctionneront plus correctement ou du tout.</span><span class="sxs-lookup"><span data-stu-id="e30e0-190">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="e30e0-191">Cela peut signifier que vous devez suspendre et attendre les conseils mis à jour de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e30e0-191">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="e30e0-192">Une fois que vous êtes satisfait de répondre à toutes les exigences et que vous avez un plan pour corriger les lacunes, continuez.</span><span class="sxs-lookup"><span data-stu-id="e30e0-192">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="e30e0-193">À un niveau élevé, alors que Skype Entreprise Server 2019 est prêt pour la procédure d’installation, Skype Entreprise Server 2015 nécessite l’installation de cu9, l’application des mises à jour prérequises à .NET et SQL, le déploiement des clés de Registre prérequises et enfin une série distincte de mises à jour de configuration du système d’exploitation (c’est-à-dire la désactivation de TLS 1.0 et 1.1 via l’importation de fichiers de Registre).</span><span class="sxs-lookup"><span data-stu-id="e30e0-193">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="e30e0-194">Il est essentiel de terminer l’installation de toutes les conditions préalables, y compris Skype Entreprise Server 2015 CU6 HF2, avant de désactiver TLS 1.0 et 1.1 sur n’importe quel serveur de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="e30e0-194">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="e30e0-195">Chaque serveur Skype Entreprise, y compris le rôle Edge et les serveurs SQL principal, nécessite les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="e30e0-195">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="e30e0-196">Assurez-vous également que tous les clients pris en charge (dans l’étendue) ont été mis à jour vers les versions minimales requises.</span><span class="sxs-lookup"><span data-stu-id="e30e0-196">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="e30e0-197">N’oubliez pas également de mettre à jour les stations de travail de gestion.</span><span class="sxs-lookup"><span data-stu-id="e30e0-197">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="e30e0-198">Nous voulons suivre l’ordre habituel des opérations « à l’intérieur » pour la mise à niveau des serveurs Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="e30e0-198">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="e30e0-199">Traitez les pools directeurs, la conversation permanente et les pools associés de la même manière que normalement.</span><span class="sxs-lookup"><span data-stu-id="e30e0-199">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="e30e0-200">L’ordre et les méthodes de mise à niveau sont [traités ici](topology.md) et [ici.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="e30e0-200">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="e30e0-201">Processus de haut niveau</span><span class="sxs-lookup"><span data-stu-id="e30e0-201">High-level process</span></span>

1. <span data-ttu-id="e30e0-202">Testez toutes les étapes de votre atelier avant de configurer les serveurs de production.</span><span class="sxs-lookup"><span data-stu-id="e30e0-202">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="e30e0-203">Sauvegarder et conserver une copie du Registre exporté sur chaque serveur à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="e30e0-203">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="e30e0-204">Vous ne pouvez pas partager des Registres entre des serveurs ; Elles contiennent des clés uniques basées sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e30e0-204">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="e30e0-205">Mettre à niveau tous les serveurs Skype Entreprise 2015 vers cu9 ou version supérieure.</span><span class="sxs-lookup"><span data-stu-id="e30e0-205">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="e30e0-206">Pour Skype Entreprise Server 2019, mise à niveau vers CU1 ou version supérieure.</span><span class="sxs-lookup"><span data-stu-id="e30e0-206">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="e30e0-207">Installez tous les prérequis sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="e30e0-207">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="e30e0-208">Déployez les clés de Registre prérequises.</span><span class="sxs-lookup"><span data-stu-id="e30e0-208">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="e30e0-209">Assurez-vous que tous les clients dans l’étendue sont mis à jour.</span><span class="sxs-lookup"><span data-stu-id="e30e0-209">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="e30e0-210">Désactivez TLS 1.0 et 1.1 via l’importation du Registre.</span><span class="sxs-lookup"><span data-stu-id="e30e0-210">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="e30e0-211">Vérifier que les charges de travail fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="e30e0-211">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="e30e0-212">Si des problèmes sont rencontrés, résolvez et résolvez les problèmes, ou</span><span class="sxs-lookup"><span data-stu-id="e30e0-212">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="e30e0-213">Restaurer le Registre à l’étape 2 pour ré-activer TLS 1.0 et 1.1</span><span class="sxs-lookup"><span data-stu-id="e30e0-213">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="e30e0-214">Validez que seul TLS 1.2 est utilisé.</span><span class="sxs-lookup"><span data-stu-id="e30e0-214">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="e30e0-215">Installer les conditions préalables sur tous les serveurs</span><span class="sxs-lookup"><span data-stu-id="e30e0-215">Install prerequisites to all servers</span></span>

<span data-ttu-id="e30e0-216">Une mise à jour complète des dépendances est nécessaire avant de commencer à désactiver TLS 1.0 et 1.1 au niveau du système d’exploitation dans vos déploiements Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e30e0-216">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="e30e0-217">Voici les versions minimales qui peuvent prendre en charge TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="e30e0-217">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="e30e0-218">Déployez toutes les mises à jour préalables sur chaque serveur Skype Entreprise de votre environnement avant de commencer à désactiver TLS 1.0 et 1.1.</span><span class="sxs-lookup"><span data-stu-id="e30e0-218">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="e30e0-219">Skype Entreprise Server 2015 CU9 6.0.9319.548 (mai 2019) ou une édition supérieure</span><span class="sxs-lookup"><span data-stu-id="e30e0-219">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="e30e0-220">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) ou supérieur avec SchUseStrongCrypto activé dans le Registre (fourni ci-dessous)</span><span class="sxs-lookup"><span data-stu-id="e30e0-220">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="e30e0-221">SQL doivent être mis à jour sur tous les serveurs et serveurs de skype entreprise 2015.</span><span class="sxs-lookup"><span data-stu-id="e30e0-221">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="e30e0-222">Mettez d’abord à jour SQL pool Enterprise Edition, puis leurs FES respectives.</span><span class="sxs-lookup"><span data-stu-id="e30e0-222">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="e30e0-223">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), ou supérieur / SQL Server 2012 SP2 + CU16 ou supérieur / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), ou supérieur / SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="e30e0-223">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="e30e0-224">SQL Server Native Client pour SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="e30e0-224">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="e30e0-225">[Pilote ODBC Microsoft 11 pour SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)ou supérieur</span><span class="sxs-lookup"><span data-stu-id="e30e0-225">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="e30e0-226">Objets de gestion partagés pour SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="e30e0-226">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="e30e0-227">SQLSysClrTypes pour SQL server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="e30e0-227">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="e30e0-228">Étapes de base pour installer les conditions préalables, dans l’ordre d’opérations recommandé</span><span class="sxs-lookup"><span data-stu-id="e30e0-228">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="e30e0-229">Installez la mise à jour cu9 de Skype Entreprise Server sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="e30e0-229">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="e30e0-230">Installez la mise à jour sur les composants à l’aide du programme de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="e30e0-230">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="e30e0-231">Mettre à jour les bases de données en fonction des procédures documentées.</span><span class="sxs-lookup"><span data-stu-id="e30e0-231">Update databases according to documented procedures.</span></span> <span data-ttu-id="e30e0-232">Pour Skype Entreprise Server 2015, voir la KB [3061064.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="e30e0-232">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="e30e0-233">Valider les fonctionnalités du produit dans le déploiement avant d’apporter d’autres modifications.</span><span class="sxs-lookup"><span data-stu-id="e30e0-233">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="e30e0-234">Téléchargez le programme d’installation hors connexion .NET 4.7.</span><span class="sxs-lookup"><span data-stu-id="e30e0-234">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="e30e0-235">Référence : [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="e30e0-235">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="e30e0-236">Assurez-vous que les services Skype Entreprise Server 2015 sont arrêtés sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="e30e0-236">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="e30e0-237">Référence : [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="e30e0-237">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="e30e0-238">Ex (Standard Edition) : ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="e30e0-238">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="e30e0-239">Ex (Enterprise Edition) : ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="e30e0-239">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="e30e0-240">Exécutez le package d’installation.</span><span class="sxs-lookup"><span data-stu-id="e30e0-240">Run the installer package.</span></span>
    7. <span data-ttu-id="e30e0-241">Redémarrez le serveur.</span><span class="sxs-lookup"><span data-stu-id="e30e0-241">Reboot the server.</span></span>
3. <span data-ttu-id="e30e0-242">Mettez SQL Express 2014 sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="e30e0-242">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="e30e0-243">Référence : [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="e30e0-243">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="e30e0-244">Télécharger SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="e30e0-244">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="e30e0-245">Référence : [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="e30e0-245">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="e30e0-246">Copiez le support d’installation dans un dossier sur le serveur (Ex : C:\01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="e30e0-246">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="e30e0-247">S’assurer que les services Skype Entreprise Server 2015 sont arrêtés sur le serveur frontal</span><span class="sxs-lookup"><span data-stu-id="e30e0-247">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="e30e0-248">Ex (Standard Edition) : ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="e30e0-248">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="e30e0-249">Ex (Enterprise Edition) : ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="e30e0-249">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="e30e0-250">Ouvrez une invite de commandes d’administration et mettre à niveau tous les composants et instances installés</span><span class="sxs-lookup"><span data-stu-id="e30e0-250">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="e30e0-251">Exemple : C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span><span class="sxs-lookup"><span data-stu-id="e30e0-251">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="e30e0-252">Mettez à SQL client natif.</span><span class="sxs-lookup"><span data-stu-id="e30e0-252">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="e30e0-253">Référence : [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .</span><span class="sxs-lookup"><span data-stu-id="e30e0-253">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="e30e0-254">Téléchargement à partir de [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="e30e0-254">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="e30e0-255">Assurez-vous que les services Skype Entreprise Server 2015 sont arrêtés sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="e30e0-255">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="e30e0-256">Ex (Standard Edition) : ```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="e30e0-256">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="e30e0-257">Ex (Enterprise Edition) : ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="e30e0-257">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="e30e0-258">Arrêter l’exécution SQL instances installées</span><span class="sxs-lookup"><span data-stu-id="e30e0-258">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="e30e0-259">Par exemple : ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="e30e0-259">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="e30e0-260">Par exemple : ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="e30e0-260">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="e30e0-261">Ex (Standard Edition Uniquement) : ```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="e30e0-261">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="e30e0-262">Installez la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="e30e0-262">Install the update.</span></span>
5. <span data-ttu-id="e30e0-263">Mettez à jour le pilote ODBC 11 SQL Server pour inclure la prise en charge de TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span><span class="sxs-lookup"><span data-stu-id="e30e0-263">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="e30e0-264">Téléchargez [le pilote ODBC 11 pour SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span><span class="sxs-lookup"><span data-stu-id="e30e0-264">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="e30e0-265">Assurez-vous que les services Skype Entreprise Server 2015 sont arrêtés sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="e30e0-265">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="e30e0-266">Exemple (Standard Edition) : ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="e30e0-266">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="e30e0-267">Exemple (Enterprise Edition) : ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="e30e0-267">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="e30e0-268">Installez la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="e30e0-268">Install the update.</span></span>
6. <span data-ttu-id="e30e0-269">Déployez les clés de Registre prérequises.</span><span class="sxs-lookup"><span data-stu-id="e30e0-269">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="e30e0-270">Clés de Registre pré-requises</span><span class="sxs-lookup"><span data-stu-id="e30e0-270">Pre-requisite registry keys</span></span>

<span data-ttu-id="e30e0-271">Copiez/collez le test suivant dans le Bloc-notes et renommez TLSPreReq.reg ou un nom de votre choix, puis importez :</span><span class="sxs-lookup"><span data-stu-id="e30e0-271">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

<span data-ttu-id="e30e0-272">Pour SQL des pools Enterprise Edition, les conditions préalables et la désactivation de TLS doivent être traitées comme n’importe quelle SQL ou les mises à jour du système d’exploitation . reportez-vous à : [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="e30e0-272">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="e30e0-273">Bien que les étapes de désactivation de l’application prérequise et de TLS soient combinées, nous vous recommandons vivement d’appliquer toutes les conditions préalables avant de poursuivre la désactivation de TLS 1.0 et 1.1 au niveau du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="e30e0-273">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="e30e0-274">La meilleure approche consiste à préparer l’environnement en déployant tous les prérequis, en validant que toutes les charges de travail fonctionnent correctement et comme prévu, puis en désactivant TLS 1.0/1.1 ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="e30e0-274">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="e30e0-275">Désactiver TLS 1.0 et 1.1 via l’importation du Registre</span><span class="sxs-lookup"><span data-stu-id="e30e0-275">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="e30e0-276">Avant de passer aux étapes suivantes, assurez-vous que vous avez rempli toutes les conditions préalables et mis à jour les serveurs *Skype Entreprise.*</span><span class="sxs-lookup"><span data-stu-id="e30e0-276">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="e30e0-277">Copiez le texte suivant dans un fichier Bloc-notes et renommez-le **TLSDisable.reg**:</span><span class="sxs-lookup"><span data-stu-id="e30e0-277">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

<span data-ttu-id="e30e0-278">Importez le fichier .reg sur chaque serveur pour désactiver TLS 1.0 et 1.1.</span><span class="sxs-lookup"><span data-stu-id="e30e0-278">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="e30e0-279">Redémarrez le serveur.</span><span class="sxs-lookup"><span data-stu-id="e30e0-279">Reboot the server.</span></span> <span data-ttu-id="e30e0-280">Une fois les services de retour en ligne, déplacez-vous vers le serveur suivant.</span><span class="sxs-lookup"><span data-stu-id="e30e0-280">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="e30e0-281">L’approche des pools Enterprise Edition Est la même que pour toute mise à jour du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="e30e0-281">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="e30e0-282">Vous avez peut-être remarqué que nous n’avons pas simplement désactivé TLS 1.0 et 1.1 ici.</span><span class="sxs-lookup"><span data-stu-id="e30e0-282">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="e30e0-283">Nous activons l’ordre de resserrage de la suite de chiffrement (comme illustré ci-dessus) et la désactivation de certains chiffrements faibles plus anciens.</span><span class="sxs-lookup"><span data-stu-id="e30e0-283">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="e30e0-284">C’est la première fois que nous supported officiellement ces modifications apportées à SCHANNEL et Crypto API sur Skype Entreprise Server, et il est important de noter que ces modifications sont les seules que nous supportons et que nous avons testées pour le moment.</span><span class="sxs-lookup"><span data-stu-id="e30e0-284">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="e30e0-285">Nous envisagerons peut-être des configurations supplémentaires à l’avenir, mais pour l’instant, ne modifiez pas le fichier d’importation du Registre dans votre implémentation.</span><span class="sxs-lookup"><span data-stu-id="e30e0-285">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="e30e0-286">Vérifier que les charges de travail fonctionnent comme prévu</span><span class="sxs-lookup"><span data-stu-id="e30e0-286">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="e30e0-287">Une fois que TLS 1.0 et 1.1 ont été désactivés dans votre environnement, assurez-vous que toutes vos charges de travail principales fonctionnent comme prévu, telles que la messagerie instantanée & présence, les appels P2P, les Voix Entreprise, etc.</span><span class="sxs-lookup"><span data-stu-id="e30e0-287">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="e30e0-288">**Validation de l’utilisation de TLS 1.2 uniquement**</span><span class="sxs-lookup"><span data-stu-id="e30e0-288">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="e30e0-289">Votre équipe de sécurité effectue un nouvel audit du trafic Skype Entreprise pour vous assurer que les anciens protocoles TLS 1.0 et 1.1 ne sont plus utilisés.</span><span class="sxs-lookup"><span data-stu-id="e30e0-289">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="e30e0-290">Vous pouvez également utiliser Internet Explorer pour tester les connexions TLS aux services web à partir de Skype Entreprise Server 2015 après la désactivation de TLS 1.0 et TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="e30e0-290">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="e30e0-291">Lancez Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="e30e0-291">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="e30e0-292">Sélectionnez **Outils**  >  **Options Internet.**</span><span class="sxs-lookup"><span data-stu-id="e30e0-292">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="e30e0-293">Sélectionnez **l’onglet** Avancé.</span><span class="sxs-lookup"><span data-stu-id="e30e0-293">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="e30e0-294">Sous **Paramètres,** faites défiler vers le bas.</span><span class="sxs-lookup"><span data-stu-id="e30e0-294">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="e30e0-295">Vérifiez que TLS 1.0, TLS 1.1 et TLS 1.2 sont activés.</span><span class="sxs-lookup"><span data-stu-id="e30e0-295">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="e30e0-296">Parcourez l’URL du service Web interne de votre pool SfB 2015 (doit se connecter correctement).</span><span class="sxs-lookup"><span data-stu-id="e30e0-296">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="e30e0-297">Revenir dans Internet Explorer et désactiver l’option d’utilisation de **TLS 1.2** uniquement.</span><span class="sxs-lookup"><span data-stu-id="e30e0-297">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="e30e0-298">Parcourez à nouveau l’URL du service Web interne de votre pool SfB 2015 (si la connexion échoue).</span><span class="sxs-lookup"><span data-stu-id="e30e0-298">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Internet Options](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="e30e0-300">Scénarios de déploiement avancés</span><span class="sxs-lookup"><span data-stu-id="e30e0-300">Advanced deployment scenarios</span></span>

<span data-ttu-id="e30e0-301">Étant donné que certaines conditions préalables de dépendance sont requises pour prendre en charge TLS 1.2 dans Skype Entreprise Server 2015, l’installation à partir d’un support RTM échouera sur n’importe quel système où TLS 1.0 et 1.1 ont été désactivés.</span><span class="sxs-lookup"><span data-stu-id="e30e0-301">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Server 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="e30e0-302">**Déploiement de nouveaux serveurs Standard Edition Servers ou pools Enterprise Edition Une fois que TLS 1.0 et 1.1 ont été désactivés dans votre environnement.**</span><span class="sxs-lookup"><span data-stu-id="e30e0-302">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="e30e0-303">**Option 1 :** Utilisez [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="e30e0-303">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="e30e0-304">Notez que nous mettons à jour SmartSetup pour prendre en charge les SQL binaires mis à jour dans une prochaine mise à jour de mise à jour, et que nous mettons à jour cet article à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="e30e0-304">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="e30e0-305">**Option 2 :** Préinstaller les instances SQL locales (RTCLOCAL et LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="e30e0-305">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="e30e0-306">Téléchargez et copiez SQL Express 2014 SP2 (SQLEXPR_x64.exe) dans le dossier local sur FE.</span><span class="sxs-lookup"><span data-stu-id="e30e0-306">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="e30e0-307">Supposons que le chemin d’accès <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="e30e0-307">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="e30e0-308">Lancez PowerShell ou invite de commandes et accédez à <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="e30e0-308">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="e30e0-309">Créez l’instance SQL RTCLOCAL en exécutant la commande ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e30e0-309">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="e30e0-310">Attendez que SQLEXPR_x64.exe se termine avant de poursuivre :</span><span class="sxs-lookup"><span data-stu-id="e30e0-310">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="e30e0-311">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT=" AUTORITÉNT\NetworkService » /SQLSYSADMINACCOUNTS="Builtin\Administrators » /BROWSERSVCSTARTUPTYPE="Automatic » /AGTSVCACCOUNT="NTAUTHORITY\NetworkService » /SQLSVCSTARTUPTYPE=Automati</span><span class="sxs-lookup"><span data-stu-id="e30e0-311">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="e30e0-312">Créez l’instance SQL LYNCLOCAL en exécutant la commande ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e30e0-312">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="e30e0-313">Attendez que SQLEXPR_x64.exe se termine avant de procéder à l’étape suivante :</span><span class="sxs-lookup"><span data-stu-id="e30e0-313">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="e30e0-314">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService » /SQLSYSADMINACCOUNTS="Builtin\Administrators » /BROWSERSVCSTARTUPTYPE="Automatic » /AGTSVCACCOUNT="NTAUTHORITY\NetworkService » /SQLSVCSTARTUPTYPE=Automatic</span><span class="sxs-lookup"><span data-stu-id="e30e0-314">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="e30e0-315">Exécutez le programme d’installation de Skype Entreprise Server 2015 RTM.</span><span class="sxs-lookup"><span data-stu-id="e30e0-315">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="e30e0-316">Suivez les étapes restantes de la section prérequise ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="e30e0-316">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="e30e0-317">**Option 3 :** Vous pouvez également remplacer manuellement les binaires dans un répertoire multimédia d’installation local comme suit :</span><span class="sxs-lookup"><span data-stu-id="e30e0-317">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="e30e0-318">Installation des conditions préalables pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e30e0-318">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="e30e0-319">Installez .NET 4.7 :</span><span class="sxs-lookup"><span data-stu-id="e30e0-319">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="e30e0-320">**Remarque :** Nous avons d’abord introduit la prise en charge de .NET 4.7 dans Skype Entreprise Server 2015 CU5 (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="e30e0-320">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="e30e0-321">Par conséquent, dans les étapes ultérieures ci-dessous, nous mettons à jour les composants principaux avant l’installation principale.</span><span class="sxs-lookup"><span data-stu-id="e30e0-321">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="e30e0-322">Téléchargement : https://www.microsoft.com/download/details.aspx?id=55167 .</span><span class="sxs-lookup"><span data-stu-id="e30e0-322">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="e30e0-323">Référence : logiciel à installer avant un déploiement [de Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="e30e0-323">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="e30e0-324">Copiez les fichiers/dossiers ISO :</span><span class="sxs-lookup"><span data-stu-id="e30e0-324">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="e30e0-325">Avec la norme ISO de Skype Entreprise Server 2015 attachée, ouvrez le répertoire racine du lecteur sous le nom (Ex : D: \) dans l’Explorateur de fichiers.</span><span class="sxs-lookup"><span data-stu-id="e30e0-325">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="e30e0-326">Copiez tous les dossiers et fichiers dans un dossier sur un disque local (ex : C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="e30e0-326">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="e30e0-327">**Remarque :** Avant d’installer des composants, certains fichiers devront être mis à jour pour prendre en charge TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="e30e0-327">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="e30e0-328">Remplacez les packages MSI/EXE :</span><span class="sxs-lookup"><span data-stu-id="e30e0-328">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="e30e0-329">Remplacez les packages MSI et EXE existants dans le dossier /Setup/amd64/ du support d’installation sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="e30e0-329">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="e30e0-330">SQL 2014 SP2 Express : https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="e30e0-330">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="e30e0-331">Renommez-SQLEXPR_x64 sur l’ordinateur local et remplacez le fichier existant dans le dossier Setup/amd64/ du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="e30e0-331">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="e30e0-332">SQL client natif : https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="e30e0-332">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="e30e0-333">**Remarque :** Renommez-le si nécessaire sqlncli.msi, puis remplacez le fichier existant dans le dossier Setup/amd64/ du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="e30e0-333">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="e30e0-334">SQL Management Objects : https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="e30e0-334">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="e30e0-335">**Remarque :** Le Feature Pack aura un grand nombre d’éléments qui peuvent être téléchargés.</span><span class="sxs-lookup"><span data-stu-id="e30e0-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="e30e0-336">Sélectionnez pour télécharger SharedManagementObjects.msi uniquement.</span><span class="sxs-lookup"><span data-stu-id="e30e0-336">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="e30e0-337">**Remarque :** Remplacez le fichier existant qui existe dans le dossier Setup/amd64/ du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="e30e0-337">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="e30e0-338">SQL types CLR : https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="e30e0-338">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="e30e0-339">**Remarque :** Le Feature Pack aura un grand nombre d’éléments qui peuvent être téléchargés.</span><span class="sxs-lookup"><span data-stu-id="e30e0-339">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="e30e0-340">Sélectionnez pour télécharger CQLSysClrTypes.msi uniquement</span><span class="sxs-lookup"><span data-stu-id="e30e0-340">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="e30e0-341">**Remarque**: remplacez le fichier existant qui existe dans le dossier Setup/amd64/ du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="e30e0-341">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="e30e0-342">Installez les composants principaux :</span><span class="sxs-lookup"><span data-stu-id="e30e0-342">Install Core Components:</span></span> 
    - <span data-ttu-id="e30e0-343">Exécutez Setup.exe à partir du dossier Setup/amd64/ du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="e30e0-343">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="e30e0-344">Suivez les instructions pour installer les composants principaux</span><span class="sxs-lookup"><span data-stu-id="e30e0-344">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="e30e0-345">Fermez les composants principaux.</span><span class="sxs-lookup"><span data-stu-id="e30e0-345">Close Core Components.</span></span>
6. <span data-ttu-id="e30e0-346">Mettre à jour les composants principaux :</span><span class="sxs-lookup"><span data-stu-id="e30e0-346">Update Core Components:</span></span> 
    - <span data-ttu-id="e30e0-347">Téléchargez le programme d’installation de mise à jour Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="e30e0-347">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="e30e0-348">Exécutez le programme d’installation pour mettre à jour les composants principaux et installer les compteurs de performance.</span><span class="sxs-lookup"><span data-stu-id="e30e0-348">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="e30e0-349">**Remarque :** À la publication de CU6HF2, la fonctionnalité de mise à jour automatique ne sera installée que jusqu’à CU6.</span><span class="sxs-lookup"><span data-stu-id="e30e0-349">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="e30e0-350">Par conséquent, le programme de mise à jour doit être exécuté séparément pour mettre à jour les composants principaux vers 6.0.9319.516.</span><span class="sxs-lookup"><span data-stu-id="e30e0-350">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="e30e0-351">Référence : https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="e30e0-351">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="e30e0-352">Installer les outils d’administration (facultatif) :</span><span class="sxs-lookup"><span data-stu-id="e30e0-352">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="e30e0-353">Cela installera les types Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64) et Microsoft System CLR Types pour SQL Server 2014 (x64) à l’aide des fichiers mis à jour.</span><span class="sxs-lookup"><span data-stu-id="e30e0-353">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="e30e0-354">En outre, le Générateur de topologie et le Panneau de contrôle de Skype Entreprise Server 2015 seront disponibles sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="e30e0-354">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="e30e0-355">Installer le magasin de configurations local (étape 1) :</span><span class="sxs-lookup"><span data-stu-id="e30e0-355">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="e30e0-356">Ouvrez l’Assistant Déploiement, cliquez sur Installer ou  mettre à jour le système Skype Entreprise Server, puis cliquez sur Exécuter à l’étape 1 : Installer le magasin de configurations local.</span><span class="sxs-lookup"><span data-stu-id="e30e0-356">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="e30e0-357">Cliquez **sur Suivant** dans la boîte de dialogue Installer le magasin de **configurations** local.</span><span class="sxs-lookup"><span data-stu-id="e30e0-357">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="e30e0-358">![Boîte de dialogue Installer le magasin de configurations local](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="e30e0-358">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="e30e0-359">Examinez les résultats et assurez-vous que l’état de la tâche est terminé.</span><span class="sxs-lookup"><span data-stu-id="e30e0-359">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="e30e0-360">Examinez le fichier journal résultant en cliquant sur **Afficher le journal.**</span><span class="sxs-lookup"><span data-stu-id="e30e0-360">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="e30e0-361">![L’état de la tâche s’affiche comme terminé](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="e30e0-361">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="e30e0-362">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="e30e0-362">Click **Finish**.</span></span>
9. <span data-ttu-id="e30e0-363">Configurer ou supprimer des composants Skype Entreprise Server (étape 2) :</span><span class="sxs-lookup"><span data-stu-id="e30e0-363">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="e30e0-364">Ouvrez l’Assistant Déploiement, cliquez sur Installer ou  mettre à jour le système Skype Entreprise **Server,** puis cliquez sur Exécuter à l’étape 2 : Installer ou supprimer des composants Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e30e0-364">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="e30e0-365">Cliquez **sur Suivant** dans la boîte de dialogue Configurer les composants Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e30e0-365">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="e30e0-366">![Fenêtre Configurer les composants Skype Entreprise Server](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="e30e0-366">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="e30e0-367">Consultez le journal à l’aide du journal d’affichage et validez que l’installation s’est terminée sans problème.</span><span class="sxs-lookup"><span data-stu-id="e30e0-367">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="e30e0-368">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="e30e0-368">Click **Finish**.</span></span>
10. <span data-ttu-id="e30e0-369">Procédez à l’installation et à la configuration supplémentaires si nécessaire (vous pouvez reprendre les procédures d’installation normales à ce stade).</span><span class="sxs-lookup"><span data-stu-id="e30e0-369">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
