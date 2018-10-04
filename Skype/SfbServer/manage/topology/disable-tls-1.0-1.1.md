---
title: Désactiver TLS 1.0/1.1 dans Skype pour Business Server 2015
ms.author: heidip
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Résumé : Préparer et implémenter la désactivation TLS 1.0 et 1.1 dans votre environnement.'
ms.openlocfilehash: e220a6615ef259e5ccba5b47a9e0f992289e6af4
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373070"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="d6d19-103">Désactiver TLS 1.0/1.1 dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d6d19-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="d6d19-104">L’objectif de cet article est de fournir les instructions nécessaires pour préparer et implémenter la désactivation TLS 1.0 et 1.1 dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="d6d19-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="d6d19-105">Ce processus nécessite une planification étendue et préparation.</span><span class="sxs-lookup"><span data-stu-id="d6d19-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="d6d19-106">Veuillez lire attentivement toutes les informations contenues dans cet article lorsque vous effectuez votre plan pour désactiver TLS 1.0 et 1.1 pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d6d19-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="d6d19-107">Notez que plusieurs dépendances externes et les conditions de connectivité qui peuvent être affectées en désactivant TLS 1.0/1.1, importantes, planification et test se justifie.</span><span class="sxs-lookup"><span data-stu-id="d6d19-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="d6d19-108">Dans cet article</span><span class="sxs-lookup"><span data-stu-id="d6d19-108">In this article</span></span>

- [<span data-ttu-id="d6d19-109">Arrière-plan et étendue</span><span class="sxs-lookup"><span data-stu-id="d6d19-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="d6d19-110">Conditions préalables et les processus</span><span class="sxs-lookup"><span data-stu-id="d6d19-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="d6d19-111">Scénarios de déploiement avancé</span><span class="sxs-lookup"><span data-stu-id="d6d19-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="d6d19-112">Arrière-plan</span><span class="sxs-lookup"><span data-stu-id="d6d19-112">Background</span></span>

<span data-ttu-id="d6d19-113">Les pilotes principales permettant de TLS 1.0 et 1.1 disable prise en charge de Skype pour Business Server localement sont Conseil de sécurité des normes du secteur PCI (Payment Card) et Federal Information Processing Standards requise.</span><span class="sxs-lookup"><span data-stu-id="d6d19-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="d6d19-114">Vous pouvez trouver plus d’informations pour les exigences PCI [ici](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span><span class="sxs-lookup"><span data-stu-id="d6d19-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="d6d19-115">Microsoft ne peut pas fournissent des recommandations ou non votre organisation est obligée de respecter ces ou d’autres composants requis.</span><span class="sxs-lookup"><span data-stu-id="d6d19-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="d6d19-116">Vous devez déterminer si elle est nécessaire pour désactiver TLS 1.0 ou 1.1 dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="d6d19-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="d6d19-117">Microsoft a produit un livre blanc sur TLS disponible [ici](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), et il est également recommandé de l’arrière-plan de la lecture disponibles dans ce [blog Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span><span class="sxs-lookup"><span data-stu-id="d6d19-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="d6d19-118">Prise en charge étendue</span><span class="sxs-lookup"><span data-stu-id="d6d19-118">Supportability Scope</span></span>

<span data-ttu-id="d6d19-119">*La portée* fait référence aux limites de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="d6d19-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="d6d19-120">Pour Skype pour Business Server localement, *dans la portée* signifie nous entièrement à prendre en charge et testés désactivation de TLS 1.0 et 1.1 pour les versions de produits répertoriées.</span><span class="sxs-lookup"><span data-stu-id="d6d19-120">For Skype for Business Server On-Premises, *in scope* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="d6d19-121">*En cours d’étude* signifie simplement que ; Nous étudions activement transfert de ces produits dans la portée pour désactiver la prise en charge TLS.</span><span class="sxs-lookup"><span data-stu-id="d6d19-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="d6d19-122">*Hors de portée* signifie que ces versions de produit ne prennent pas en charge la désactivation TLS 1.0 ou 1.1 et ne fonctionnent pas, avec les exceptions indiquées.</span><span class="sxs-lookup"><span data-stu-id="d6d19-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="d6d19-123">Serveurs entièrement testées et pris en charge</span><span class="sxs-lookup"><span data-stu-id="d6d19-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="d6d19-124">Skype pour Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="d6d19-124">Skype for Business Server 2019</span></span>
- <span data-ttu-id="d6d19-125">Skype pour Business Server 2015 CU6 HF2 6.0.9319.516 ([mise à jour de mars 2018](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) ou ultérieure sur :</span><span class="sxs-lookup"><span data-stu-id="d6d19-125">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([March 2018 update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) and higher on:</span></span> 
    - <span data-ttu-id="d6d19-126">Windows Server 2012 (avec 3140245 Ko ou mise à jour de remplacement), 2012 R2 ou 2016</span><span class="sxs-lookup"><span data-stu-id="d6d19-126">Windows Server 2012 (with KB 3140245 or superseding update), 2012 R2 or 2016</span></span>
- <span data-ttu-id="d6d19-127">Skype de mise à niveau sur place pour Business Server 2015, avec CU6 HF2 et versions ultérieures sur</span><span class="sxs-lookup"><span data-stu-id="d6d19-127">In-place Upgraded Skype for Business Server 2015, with CU6 HF2 and higher on</span></span> 
    - <span data-ttu-id="d6d19-128">Windows Server 2008 R2, 2012 (avec KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou mise à jour de remplacement) ou 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d6d19-128">Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2</span></span>
- <span data-ttu-id="d6d19-129">Connectivité de Microsoft Exchange et Outlook Web App avec Exchange Server 2010 SP3 RU19 ou ultérieur, instructions [ici](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="d6d19-129">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
 
### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="d6d19-130">Entièrement testées et prises en charge des clients</span><span class="sxs-lookup"><span data-stu-id="d6d19-130">Fully tested and supported clients</span></span>

- <span data-ttu-id="d6d19-131">Client de bureau Lync 2013 (Skype pour les entreprises), MSI et C2R, y compris Basic [15.0.5023.1000 et plus](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="d6d19-131">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 and higher](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="d6d19-132">Skype pour le Client de bureau Business 2016, MSI [16.0.4678.1000 et versions ultérieures](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), y compris Basic</span><span class="sxs-lookup"><span data-stu-id="d6d19-132">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 and higher](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="d6d19-133">Skype pour Business 2016, cliquez sur Exécuter nécessitent les mises à jour [d’avril 2018](https://docs.microsoft.com/en-us/officeupdates/release-notes-office365-proplus) :</span><span class="sxs-lookup"><span data-stu-id="d6d19-133">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/en-us/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="d6d19-134">Tous les mois et annuel séparées ciblé, 16\.0\.9126\.2152 et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="d6d19-134">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 and higher</span></span>
    - <span data-ttu-id="d6d19-135">Annuel séparées et canal différé, 16\.0\.8431\.2242 et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="d6d19-135">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 and higher</span></span>
- <span data-ttu-id="d6d19-136">Skype pour les entreprises des 16.15 Mac</span><span class="sxs-lookup"><span data-stu-id="d6d19-136">Skype for Business on Mac 16.15 and higher</span></span>
- <span data-ttu-id="d6d19-137">Skype pour l’entreprise pour iOS et Android 6.19 et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="d6d19-137">Skype for Business for iOS and Android 6.19 and higher</span></span>
- <span data-ttu-id="d6d19-138">Skype Web application 2015 CU6 HF2 et supérieur (fourni avec serveur)</span><span class="sxs-lookup"><span data-stu-id="d6d19-138">Skype Web App 2015 CU6 HF2 and higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="d6d19-139">En cours d’étude</span><span class="sxs-lookup"><span data-stu-id="d6d19-139">Currently being investigated</span></span>

#### <a name="devices"></a><span data-ttu-id="d6d19-140">Périphériques</span><span class="sxs-lookup"><span data-stu-id="d6d19-140">Devices</span></span>

- <span data-ttu-id="d6d19-141">Le système Lync salle (également appelé</span><span class="sxs-lookup"><span data-stu-id="d6d19-141">Lync Room System (a.k.a.</span></span> <span data-ttu-id="d6d19-142">SRSv1)</span><span class="sxs-lookup"><span data-stu-id="d6d19-142">SRSv1)</span></span>
- <span data-ttu-id="d6d19-143">Systèmes de salle Skype v2 (également appelé</span><span class="sxs-lookup"><span data-stu-id="d6d19-143">Skype Room Systems v2 (a.k.a.</span></span> <span data-ttu-id="d6d19-144">SRSv2)</span><span class="sxs-lookup"><span data-stu-id="d6d19-144">SRSv2)</span></span>
- <span data-ttu-id="d6d19-145">Surface Hub</span><span class="sxs-lookup"><span data-stu-id="d6d19-145">Surface Hub</span></span>
- <span data-ttu-id="d6d19-146">en fonction de 2015 Survivable Branch Appliance (SBA) ou serveur Survivable Branch Server (SBS)</span><span class="sxs-lookup"><span data-stu-id="d6d19-146">2015 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>

#### <a name="other"></a><span data-ttu-id="d6d19-147">Autre</span><span class="sxs-lookup"><span data-stu-id="d6d19-147">Other</span></span>

- <span data-ttu-id="d6d19-148">Tableau de bord qualité des appels (nouvelle installation après TLS 1.0, 1.1 ont été désactivées, voir ci-dessous) \*</span><span class="sxs-lookup"><span data-stu-id="d6d19-148">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="d6d19-149">Hors de portée</span><span class="sxs-lookup"><span data-stu-id="d6d19-149">Out of scope</span></span>

<span data-ttu-id="d6d19-150">Sauf mention contraire, les produits suivants ne sont pas dans la portée de prise en charge de la désactiver TLS 1.0/1.1 et ne fonctionnent pas dans un environnement où TLS 1.0 et 1.1 ont été désactivés.</span><span class="sxs-lookup"><span data-stu-id="d6d19-150">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span>  <span data-ttu-id="d6d19-151">Cela signifie que : Si vous utilisez toujours des clients ou serveurs hors de portée, vous devez mettre à jour ou supprimer ces si vous devez désactiver TLS 1.0/1.1 n’importe où dans votre Skype pour Business Server déploiement local.</span><span class="sxs-lookup"><span data-stu-id="d6d19-151">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="d6d19-152">Lync Server 2013 \*</span><span class="sxs-lookup"><span data-stu-id="d6d19-152">Lync Server 2013\*</span></span>
- <span data-ttu-id="d6d19-153">Windows Server 2008 et inférieur</span><span class="sxs-lookup"><span data-stu-id="d6d19-153">Windows Server 2008 and lower</span></span>
- <span data-ttu-id="d6d19-154">Lync pour Mac 2011</span><span class="sxs-lookup"><span data-stu-id="d6d19-154">Lync for Mac 2011</span></span>
- <span data-ttu-id="d6d19-155">Lync 2013 pour Mobile - iOS, iPad, Android ou Windows Phone</span><span class="sxs-lookup"><span data-stu-id="d6d19-155">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="d6d19-156">Client Lync « MX » Windows Store</span><span class="sxs-lookup"><span data-stu-id="d6d19-156">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="d6d19-157">Tous les clients Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d6d19-157">All Lync 2010 clients</span></span>
- <span data-ttu-id="d6d19-158">Lync Phone Edition - conseils mis à jour [ici](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span><span class="sxs-lookup"><span data-stu-id="d6d19-158">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="d6d19-159">en fonction de 2013 Survivable Branch Appliance (SBA) ou serveur Survivable Branch Server (SBS)</span><span class="sxs-lookup"><span data-stu-id="d6d19-159">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>

### <a name="exceptions"></a><span data-ttu-id="d6d19-160">Exceptions</span><span class="sxs-lookup"><span data-stu-id="d6d19-160">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="d6d19-161">\* Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6d19-161">\*Lync Server 2013</span></span>

<span data-ttu-id="d6d19-162">Lync Server 2013 prend en charge une dépendance Windows Fabric version 1.0.</span><span class="sxs-lookup"><span data-stu-id="d6d19-162">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="d6d19-163">Dans la phase de conception pour Lync Server 2013 Windows Fabric 1.0 a été sélectionné pour son architecture distribuée attrayants et nouveau pour une réplication, haute disponibilité et tolérance de pannes.</span><span class="sxs-lookup"><span data-stu-id="d6d19-163">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="d6d19-164">Au fil du temps, les deux Skype pour Business Server et Windows Fabric ont considérablement amélioré cette architecture commune avec redéfinissez significatif dans les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="d6d19-164">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="d6d19-165">Cours Skype pour Business 2015 Server utilise Windows Fabric 3.0, par exemple.</span><span class="sxs-lookup"><span data-stu-id="d6d19-165">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="d6d19-166">Malheureusement, Windows Fabric 1.0 **ne prend pas en charge TLS 1.2.  Toutefois, nous mettrons à jour Lync Server 2013 pour fonctionner avec TLS 1.2**.</span><span class="sxs-lookup"><span data-stu-id="d6d19-166">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="d6d19-167">Il sera bientôt dans la prochaine mise à jour Cumulative pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d6d19-167">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="d6d19-168">Nous vous fournissons prise en charge TLS 1.2 pour activer les scénarios de coexistence, la migration, la fédération et hybrides.</span><span class="sxs-lookup"><span data-stu-id="d6d19-168">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="d6d19-169">Si votre organisation est obligée de désactiver TLS 1.0 et 1.1 et que vous utilisez actuellement Lync Server 2013, nous vous recommandons de commencer votre processus de planification, la possibilité vous devrez peut-être mise à niveau sur place ou côte à côte vers Skype pour (de nouveaux pools, déplacer les utilisateurs) Business Server 2015 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="d6d19-169">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="d6d19-170">Ou vous souhaiterez peut-être accélérer la migration vers Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="d6d19-170">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="d6d19-171">\* Tableau de bord qualité des appels</span><span class="sxs-lookup"><span data-stu-id="d6d19-171">\*Call Quality Dashboard</span></span>

<span data-ttu-id="d6d19-172">Tableau de bord qualité d’appel local a actuellement une dépendance sur TLS 1.0 pendant l’installation du nouveau (première installation dans vos environnements sur site).</span><span class="sxs-lookup"><span data-stu-id="d6d19-172">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="d6d19-173">Nous étudions ce problème et planifier la publication d’un correctif dans un avenir proche.</span><span class="sxs-lookup"><span data-stu-id="d6d19-173">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="d6d19-174">Si vous prévoyez d’installer CQD et également désactiver TLS 1.0, nous vous recommandons que vous effectuez installation CQD tout d’abord, puis poursuivez la désactivation de TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="d6d19-174">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="d6d19-175">Périphériques tiers</span><span class="sxs-lookup"><span data-stu-id="d6d19-175">Third-party devices</span></span>

<span data-ttu-id="d6d19-176">Sur des appareils tiers tels que des téléphones 3PIP, vidéoconférence, proxys inverses et les équilibreurs de charge, veillez à valider la prise en charge TLS 1.2, tester avec soin et contactez le fournisseur, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="d6d19-176">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="d6d19-177">Considérations relatives à la fédération lors de la désactivation TLS 1.0/1.1 sur les serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="d6d19-177">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="d6d19-178">Vous devez soigneusement planifier et prendre en compte l’impact de la désactivation TLS 1.0/1.1 sur vos serveurs de périphérie.</span><span class="sxs-lookup"><span data-stu-id="d6d19-178">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="d6d19-179">Une fois que TLS 1.0 et 1.1 sont désactivés, vous pouvez trouver d’autres organisations sont ne plus être en mesure de se fédérer avec votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d6d19-179">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="d6d19-180">Vous pouvez choisir pour conserver TLS 1.0/1.1 activé sur vos serveurs de périphérie pour maintenir la compatibilité descendante avec non corrigées (SfB 2015, Lync 2013) ou plus anciens systèmes externes (2010).</span><span class="sxs-lookup"><span data-stu-id="d6d19-180">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="d6d19-181">Microsoft ne peuvent pas fournir des conseils ou des recommandations sur ou non votre réseau de périmètre (ou n’importe quel réseau) relève PCI standard ; qui doit être déterminée par la société.</span><span class="sxs-lookup"><span data-stu-id="d6d19-181">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="d6d19-182">Skype pour Business Online est capable de TLS 1.2 aujourd'hui, donc aucun impact sur hybride/fédération avec Online n’est prévu.</span><span class="sxs-lookup"><span data-stu-id="d6d19-182">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="d6d19-183">PIC (Public IM Connectivity) au service des utilisateurs de Skype : nous ne prévoyez pas de désactivation TLS 1.0/1.1 pour avoir un impact sur la [Connectivité Skype](../../deploy/deploy-skype-connectivity.md); Microsoft PIC passerelles sont déjà capables de TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="d6d19-183">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="d6d19-184">Conditions préalables et les processus</span><span class="sxs-lookup"><span data-stu-id="d6d19-184">Prerequisites and process</span></span>

<span data-ttu-id="d6d19-185">Sauf mention contraire ci-dessus, une fois TLS 1.0 et 1.1 sont désactivés serveurs hors de portée, clients et périphériques fonctionnent plus correctement, ou tout.</span><span class="sxs-lookup"><span data-stu-id="d6d19-185">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="d6d19-186">Cela signifie que vous deviez suspendre et attendre pour obtenir des conseils mis à jour de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6d19-186">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="d6d19-187">Une fois que vous êtes satisfait de tous les éléments requis et un plan à combler des lacunes, passez.</span><span class="sxs-lookup"><span data-stu-id="d6d19-187">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="d6d19-188">À un niveau élevé, tandis que Skype pour Business Server 2019 est prêt pour la procédure à l’installation, Skype pour Business Server 2015 nécessite que vous installez HF2 CU6, mise à jour prérequis .NET et SQL, les clés de Registre requis déploiement et enfin distincte Round de configuration du système d’exploitation met à jour (c'est-à-dire désactivation TLS 1.0 et 1.1 via l’importation des fichiers de Registre).</span><span class="sxs-lookup"><span data-stu-id="d6d19-188">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU6 HF2, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="d6d19-189">Il est essentiel de procéder à l’installation de tous les éléments prérequis, notamment Skype pour Business Server 2015 CU6 HF2, avant la désactivation TLS 1.0 et 1.1 sur n’importe quel serveur dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="d6d19-189">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="d6d19-190">Chaque Skype pour Business server, y compris le rôle de serveur Edge et les serveurs principaux SQL, nécessite les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="d6d19-190">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="d6d19-191">Vérifiez également que tous les clients (dans la portée) pris en charge ont été mis à jour pour les versions minimales requises.</span><span class="sxs-lookup"><span data-stu-id="d6d19-191">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="d6d19-192">N’oubliez pas de mettre à jour ainsi que les stations de gestion.</span><span class="sxs-lookup"><span data-stu-id="d6d19-192">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="d6d19-193">Nous voulons à suivre l’ordre des opérations de « connaître » normal de mise à niveau Skype des serveurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="d6d19-193">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="d6d19-194">Traite les pools directeurs, Pchat et Pools associés de la même manière que vous le feriez normalement.</span><span class="sxs-lookup"><span data-stu-id="d6d19-194">Treat Director pools, Pchat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="d6d19-195">Ordre et les méthodes de mise à niveau sont abordées [ici](topology.md) et [ici](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="d6d19-195">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="d6d19-196">Processus de haut niveau</span><span class="sxs-lookup"><span data-stu-id="d6d19-196">High-level process</span></span>

1. <span data-ttu-id="d6d19-197">Testez toutes les étapes dans votre laboratoire avant la configuration des serveurs de production.</span><span class="sxs-lookup"><span data-stu-id="d6d19-197">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="d6d19-198">Sauvegarder et de conserver une copie du Registre exporté sur chaque serveur individuel à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="d6d19-198">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="d6d19-199">Vous ne pouvez pas partager registres entre serveurs ; elles contiennent des touches uniques sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="d6d19-199">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="d6d19-200">Mettre à niveau tous les Skype pour les serveurs d’entreprise 2015 CU6 HF2 ou supérieur.</span><span class="sxs-lookup"><span data-stu-id="d6d19-200">Upgrade all Skype for Business 2015 servers to CU6 HF2 or higher.</span></span> <span data-ttu-id="d6d19-201">(Pour Skype pour Business Server 2019, aucune mise à jour Cumulative n’est nécessaire)</span><span class="sxs-lookup"><span data-stu-id="d6d19-201">(For Skype for Business Server 2019, no CU is needed)</span></span>
4. <span data-ttu-id="d6d19-202">Installer tous les composants requis sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="d6d19-202">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="d6d19-203">Déployer des clés de Registre requis.</span><span class="sxs-lookup"><span data-stu-id="d6d19-203">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="d6d19-204">Assurez-vous que tous les clients dans la portée sont mis à jour.</span><span class="sxs-lookup"><span data-stu-id="d6d19-204">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="d6d19-205">Désactiver TLS 1.0 et 1.1 par le biais d’importation dans le Registre.</span><span class="sxs-lookup"><span data-stu-id="d6d19-205">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="d6d19-206">Valider les charges de travail fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="d6d19-206">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="d6d19-207">Si vous rencontrez des problèmes, dépannage et la résolution, ou</span><span class="sxs-lookup"><span data-stu-id="d6d19-207">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="d6d19-208">Restaurer à partir de l’étape 2 pour réactiver TLS 1.0 et 1.1</span><span class="sxs-lookup"><span data-stu-id="d6d19-208">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="d6d19-209">Valider qu’uniquement TLS 1.2 est utilisé.</span><span class="sxs-lookup"><span data-stu-id="d6d19-209">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="d6d19-210">Installer les composants requis sur tous les serveurs</span><span class="sxs-lookup"><span data-stu-id="d6d19-210">Install prerequisites to all servers</span></span>

<span data-ttu-id="d6d19-211">Dépendance importante mise à jour est requise avant de commencer à désactiver TLS 1.0 et 1.1 niveau le système d’exploitation dans votre Skype pour les déploiements Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d6d19-211">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="d6d19-212">Voici les versions minimales pouvant prendre en charge TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="d6d19-212">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="d6d19-213">Déployer toutes les mises à jour requis sur chaque Skype pour Business server dans votre environnement avant de commencer la désactivation TLS 1.0 et 1.1.</span><span class="sxs-lookup"><span data-stu-id="d6d19-213">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="d6d19-214">Skype pour Business Server 2015 CU6 HF2 6.0.9319.516 ([mise à jour de mars 2018](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) ou supérieur</span><span class="sxs-lookup"><span data-stu-id="d6d19-214">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([March 2018 update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) or higher</span></span>
- <span data-ttu-id="d6d19-215">[.NET framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) ou supérieure avec SchUseStrongCrypto activé dans le Registre (fourni ci-dessous)</span><span class="sxs-lookup"><span data-stu-id="d6d19-215">[.NET Framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="d6d19-216">SQL doit être mis à jour sur tous les Skype pour Business 2015 serveurs et les serveurs principaux.</span><span class="sxs-lookup"><span data-stu-id="d6d19-216">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="d6d19-217">Mettre à jour les serveurs principaux du SQL Enterprise Edition Pool tout d’abord, puis leur ces respectifs.</span><span class="sxs-lookup"><span data-stu-id="d6d19-217">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="d6d19-218">SQL Server 2014 SP1 + CU5 ([lien](https://support.microsoft.com/help/3130926)) ou supérieur / SQL Server 2012 SP2 + CU16 ou supérieur / SQL Server 2014 RTM + CU12 ([lien](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) ou supérieur / SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="d6d19-218">SQL Server 2014 SP1 + CU5 ([link](https://support.microsoft.com/help/3130926)), or higher / SQL Server 2012 SP2 + CU16 or higher/ SQL Server 2014 RTM + CU12 ([link](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) or higher / SQL Server 2014 SP2</span></span>
    - <span data-ttu-id="d6d19-219">SQL Server Native Client pour SQL Server 2012 ([lien](https://www.microsoft.com/en-us/download/details.aspx?id=50402))</span><span class="sxs-lookup"><span data-stu-id="d6d19-219">SQL Server Native Client for SQL Server 2012 ([link](https://www.microsoft.com/en-us/download/details.aspx?id=50402))</span></span>
    - <span data-ttu-id="d6d19-220">11 de pilote ODBC Microsoft SQL Server ([lien](https://www.microsoft.com/en-us/download/details.aspx?id=36434)) ou supérieur</span><span class="sxs-lookup"><span data-stu-id="d6d19-220">Microsoft ODBC Driver 11 for SQL Server ([link](https://www.microsoft.com/en-us/download/details.aspx?id=36434)), or higher</span></span>
    - <span data-ttu-id="d6d19-221">Partagé des objets de gestion pour SQL Server 2014 SP2 ([lien](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span><span class="sxs-lookup"><span data-stu-id="d6d19-221">Shared Management Objects for SQL Server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span></span>
    - <span data-ttu-id="d6d19-222">SQLSysClrTypes pour SQL server 2014 SP2 ([lien](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span><span class="sxs-lookup"><span data-stu-id="d6d19-222">SQLSysClrTypes for SQL server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span></span>
 
### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="d6d19-223">Étapes de base pour installer les composants requis, dans l’ordre recommandé des opérations</span><span class="sxs-lookup"><span data-stu-id="d6d19-223">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="d6d19-224">Installer le Skype pour Business Server CU6HF2 (6.0.9319.516) mise à jour à tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="d6d19-224">Install the Skype for Business Server CU6HF2 (6.0.9319.516) update to all servers.</span></span> 
    1. <span data-ttu-id="d6d19-225">Installez la mise à jour à l’aide de la mise à jour des composants.</span><span class="sxs-lookup"><span data-stu-id="d6d19-225">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="d6d19-226">Mettre à jour les bases de données en fonction des procédures documentées.</span><span class="sxs-lookup"><span data-stu-id="d6d19-226">Update databases according to documented procedures.</span></span> <span data-ttu-id="d6d19-227">Instructions sont documentées à [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="d6d19-227">Instructions are documented at [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="d6d19-228">Valider les fonctionnalités du produit dans le déploiement avant de poursuivre les modifications.</span><span class="sxs-lookup"><span data-stu-id="d6d19-228">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="d6d19-229">Téléchargez .NET 4.7 programme d’installation en mode hors connexion.</span><span class="sxs-lookup"><span data-stu-id="d6d19-229">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="d6d19-230">Référence :[https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="d6d19-230">Reference: [https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="d6d19-231">Assurez-vous que Skype pour les services Business Server 2015 sont arrêtés sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="d6d19-231">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="d6d19-232">Référence :[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="d6d19-232">Reference: [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="d6d19-233">Ex (Standard Edition) : Stop-CsWindowsServices</span><span class="sxs-lookup"><span data-stu-id="d6d19-233">Ex (Standard Edition): Stop-CsWindowsServices</span></span>
    5. <span data-ttu-id="d6d19-234">Ex (Enterprise Edition) : Invoke-CsComputerFailover</span><span class="sxs-lookup"><span data-stu-id="d6d19-234">Ex (Enterprise Edition): Invoke-CsComputerFailover</span></span>
    6. <span data-ttu-id="d6d19-235">Exécutez le package d’installation.</span><span class="sxs-lookup"><span data-stu-id="d6d19-235">Run the installer package.</span></span>
    7. <span data-ttu-id="d6d19-236">Redémarrez le serveur.</span><span class="sxs-lookup"><span data-stu-id="d6d19-236">Reboot the server.</span></span>
3. <span data-ttu-id="d6d19-237">Mettre à jour SQL Express 2014 sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="d6d19-237">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="d6d19-238">Référence :[https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="d6d19-238">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="d6d19-239">Télécharger SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="d6d19-239">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="d6d19-240">Référence :[https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="d6d19-240">Reference: [https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="d6d19-241">Copiez le support d’installation dans un dossier sur le serveur (Ex : C:\01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="d6d19-241">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="d6d19-242">Assurez-vous de Skype pour Business Server 2015 services sont arrêtés sur le serveur frontal</span><span class="sxs-lookup"><span data-stu-id="d6d19-242">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="d6d19-243">Ex (Standard Edition) : Stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="d6d19-243">Ex (Standard Edition): Stop-CsWindowsService</span></span>
        - <span data-ttu-id="d6d19-244">Ex (Enterprise Edition) : Invoke-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="d6d19-244">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    5. <span data-ttu-id="d6d19-245">Ouvrez une invite de commandes d’administration et de mettre à niveau tous les composants installés et instances</span><span class="sxs-lookup"><span data-stu-id="d6d19-245">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="d6d19-246">Exemple : C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action = Patch /AllInstances</span><span class="sxs-lookup"><span data-stu-id="d6d19-246">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="d6d19-247">Mise à jour SQL Native Client.</span><span class="sxs-lookup"><span data-stu-id="d6d19-247">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="d6d19-248">Référence : [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="d6d19-248">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="d6d19-249">Télécharger à partir de[https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="d6d19-249">Download from [https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="d6d19-250">Vérifiez que Skype pour Business Server 2015 services sont arrêtés sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="d6d19-250">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="d6d19-251">Ex (Standard Edition) : Stop-CsWindowsServices</span><span class="sxs-lookup"><span data-stu-id="d6d19-251">Ex (Standard Edition): Stop-CsWindowsServices</span></span>
        - <span data-ttu-id="d6d19-252">Ex (Enterprise Edition) : Invoke-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="d6d19-252">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    4. <span data-ttu-id="d6d19-253">Arrêter les instances SQL installés à partir de l’exécution</span><span class="sxs-lookup"><span data-stu-id="d6d19-253">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="d6d19-254">Ex : Get-Service « MSSQL$ RTCLOCAL » | STOP-service</span><span class="sxs-lookup"><span data-stu-id="d6d19-254">Ex: Get-Service 'MSSQL$RTCLOCAL' | Stop-Servic</span></span>
        - <span data-ttu-id="d6d19-255">Ex : Get-Service « MSSQL$ LYNCLOCAL » | STOP-service</span><span class="sxs-lookup"><span data-stu-id="d6d19-255">Ex: Get-Service 'MSSQL$LYNCLOCAL' | Stop-Servic</span></span>
        - <span data-ttu-id="d6d19-256">Ex (Standard Edition seulement) : Get-Service « MSSQL$ RTC » | STOP-service</span><span class="sxs-lookup"><span data-stu-id="d6d19-256">Ex (Standard Edition Only): Get-Service 'MSSQL$RTC' | Stop-Servic</span></span>
    5. <span data-ttu-id="d6d19-257">Installez la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="d6d19-257">Install the update.</span></span>
5. <span data-ttu-id="d6d19-258">Mettre à jour le pilote ODBC 11 pour SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d6d19-258">Update ODBC Driver 11 for SQL Server.</span></span> 
    1. <span data-ttu-id="d6d19-259">Référence : [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="d6d19-259">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="d6d19-260">Télécharger à partir de[https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)</span><span class="sxs-lookup"><span data-stu-id="d6d19-260">Download from [https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)</span></span>
    3. <span data-ttu-id="d6d19-261">Assurez-vous que Skype pour les services Business Server 2015 sont arrêtés sur le serveur frontal</span><span class="sxs-lookup"><span data-stu-id="d6d19-261">Ensure that Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="d6d19-262">Ex (Standard Edition) : Stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="d6d19-262">Ex (Standard Edition): Stop-CsWindowsService</span></span>
        - <span data-ttu-id="d6d19-263">Ex (Enterprise Edition) : Invoke-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="d6d19-263">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    4. <span data-ttu-id="d6d19-264">Installez la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="d6d19-264">Install the update.</span></span>
6. <span data-ttu-id="d6d19-265">Déployer des clés de Registre requis.</span><span class="sxs-lookup"><span data-stu-id="d6d19-265">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="d6d19-266">Clés de Registre requis</span><span class="sxs-lookup"><span data-stu-id="d6d19-266">Pre-requisite registry keys</span></span>

<span data-ttu-id="d6d19-267">Copier/coller le test suivant dans le bloc-notes et renommer TLSPreReq.reg ou un nom de votre choix, puis importer :</span><span class="sxs-lookup"><span data-stu-id="d6d19-267">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

```
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

<span data-ttu-id="d6d19-268">Pour SQL back désactiver extrémités pour TLS, les conditions préalables et les Pools d’entreprise Edition doit être traitée comme le feriez pour les mises à jour SQL ou du système d’exploitation ; reportez-vous à :[https://docs.microsoft.com/en-us/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/en-us/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="d6d19-268">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/en-us/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/en-us/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="d6d19-269">Alors que l’application requise et TLS désactivation des étapes peuvent être combinés, nous vous recommandons vivement d’appliquer toutes les conditions préalables avant de procéder à la désactivation de TLS 1.0 et 1.1 au niveau du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="d6d19-269">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="d6d19-270">La meilleure pratique serait pour préparer l’environnement en déployant tous les éléments prérequis, valider que toutes les charges de travail fonctionnent comme prévu et correctement, puis continuer avec TLS 1.0/1.1 désactiver à une date ultérieure.</span><span class="sxs-lookup"><span data-stu-id="d6d19-270">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="d6d19-271">Désactiver TLS 1.0 et 1.1 par le biais d’importation dans le Registre</span><span class="sxs-lookup"><span data-stu-id="d6d19-271">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="d6d19-272">Avant de poursuivre avec les étapes suivantes, *Assurez-vous que vous avez terminé toutes les conditions préalables et mis à jour Skype des serveurs d’entreprise*.</span><span class="sxs-lookup"><span data-stu-id="d6d19-272">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="d6d19-273">Copiez le texte suivant dans un fichier Bloc-notes et renommez-le **TLSDisable.reg**:</span><span class="sxs-lookup"><span data-stu-id="d6d19-273">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

```
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

<span data-ttu-id="d6d19-274">Importez le fichier .reg sur chaque serveur que vous souhaitez désactiver TLS 1.0 et 1.1.</span><span class="sxs-lookup"><span data-stu-id="d6d19-274">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="d6d19-275">Redémarrez le serveur.</span><span class="sxs-lookup"><span data-stu-id="d6d19-275">Reboot the server.</span></span> <span data-ttu-id="d6d19-276">Une fois que les services ont remis en ligne, déplacer vers le serveur suivant.</span><span class="sxs-lookup"><span data-stu-id="d6d19-276">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="d6d19-277">L’approche pour les Pools d’entreprise Edition est la même que risque de prendre pour une mise à jour du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="d6d19-277">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="d6d19-278">Vous avez remarqué que nous faisons plus de désactiver TLS 1.0 et 1.1 ici.</span><span class="sxs-lookup"><span data-stu-id="d6d19-278">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="d6d19-279">Nous effectuons prenant en charge la Suite de chiffrement réorganiser (comme indiqué ci-dessus) et la désactivation de certains anciens chiffrement faible.</span><span class="sxs-lookup"><span data-stu-id="d6d19-279">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="d6d19-280">Il s’agit de la première fois que nous avons officiellement pris en charge ces modifications à SCHANNEL et API de chiffrement sur Skype pour Business Server, et il est important de noter que ces modifications sont les seuls à nous prennent en charge et testés à ce stade.</span><span class="sxs-lookup"><span data-stu-id="d6d19-280">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="d6d19-281">Il peut prendre en compte les configurations supplémentaires à l’avenir, mais pour l’instant, ne modifiez pas le fichier d’importation dans le Registre dans votre implémentation.</span><span class="sxs-lookup"><span data-stu-id="d6d19-281">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="d6d19-282">Valider les charges de travail fonctionnent comme prévu</span><span class="sxs-lookup"><span data-stu-id="d6d19-282">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="d6d19-283">Une fois que TLS 1.0 et 1.1 ont été désactivés dans votre environnement, assurez-vous que toutes vos charges de travail principales fonctionnent comme prévu, telles que la messagerie instantanée et présence, P2P appelle, Enterprise Voice, etc..</span><span class="sxs-lookup"><span data-stu-id="d6d19-283">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="d6d19-284">**Valider uniquement TLS 1.2 est utilisé**</span><span class="sxs-lookup"><span data-stu-id="d6d19-284">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="d6d19-285">Demandez à votre équipe de sécurité de procéder à une nouvelle vérification de Skype pour le trafic d’entreprise pour s’assurer que les anciens protocoles TLS 1.0 et 1.1 ne sont plus utilisés.</span><span class="sxs-lookup"><span data-stu-id="d6d19-285">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="d6d19-286">Sinon, vous pouvez utiliser Internet Explorer pour tester les connexions TLS aux services web à partir de Skype Business Server 2015 après que TLS 1.0 et 1.1 TLS ont été désactivés.</span><span class="sxs-lookup"><span data-stu-id="d6d19-286">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="d6d19-287">Lancez Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="d6d19-287">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="d6d19-288">Sélectionnez **Outils** > **Options Internet**.</span><span class="sxs-lookup"><span data-stu-id="d6d19-288">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="d6d19-289">Sélectionnez l’onglet **Options avancées** .</span><span class="sxs-lookup"><span data-stu-id="d6d19-289">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="d6d19-290">Sous **paramètres**, faites défiler vers le bas.</span><span class="sxs-lookup"><span data-stu-id="d6d19-290">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="d6d19-291">Vérifiez que TLS 1.0, TLS 1.1 et TLS 1.2 sont activés.</span><span class="sxs-lookup"><span data-stu-id="d6d19-291">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="d6d19-292">Accédez à l’URL du Service Web interne de votre pool 2015 SfB (doivent se connecter correctement).</span><span class="sxs-lookup"><span data-stu-id="d6d19-292">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="d6d19-293">Revenez dans Internet Explorer et désactiver l’option pour **utiliser TLS 1.2** uniquement.</span><span class="sxs-lookup"><span data-stu-id="d6d19-293">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="d6d19-294">Accédez à l’URL de Service Web interne de votre pool SfB 2015 à nouveau (défaillance pour se connecter).</span><span class="sxs-lookup"><span data-stu-id="d6d19-294">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Options Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="d6d19-296">Scénarios de déploiement avancé</span><span class="sxs-lookup"><span data-stu-id="d6d19-296">Advanced deployment scenarios</span></span>

<span data-ttu-id="d6d19-297">Étant donné que certains logiciels de dépendance sont nécessaires pour prendre en charge TLS 1.2 Skype pour Business Server 2015, l’installation à partir du média RTM échoue sur n’importe quel système où TLS 1.0 et 1.1 ont été désactivés.</span><span class="sxs-lookup"><span data-stu-id="d6d19-297">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="d6d19-298">**Déploiement de nouveaux serveurs Standard Edition Server ou Enterprise Edition Pools une fois que TLS 1.0 et 1.1 ont été désactivés dans votre environnement.**</span><span class="sxs-lookup"><span data-stu-id="d6d19-298">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="d6d19-299">**Option 1 :** Utilisez [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="d6d19-299">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="d6d19-300">Notez que nous SmartSetup pour prendre en charge les mises à jour binaires SQL dans une mise à jour Cumulative future mise à jour et met à jour cet article à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="d6d19-300">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="d6d19-301">**Option 2 :** Installation locales instances SQL (RTCLOCAL et LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="d6d19-301">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="d6d19-302">Télécharger et copier SQL Express 2014 SP2 (SQLEXPR_x64.exe) dans un dossier local sur FE.</span><span class="sxs-lookup"><span data-stu-id="d6d19-302">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="d6d19-303">Supposons que le chemin d’accès du dossier < SQL_FOLDER_PATH >.</span><span class="sxs-lookup"><span data-stu-id="d6d19-303">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="d6d19-304">Lancer PowerShell ou invite de commandes et accédez au < SQL_FOLDER_PATH >.</span><span class="sxs-lookup"><span data-stu-id="d6d19-304">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="d6d19-305">Créer l’instance SQL RTCLOCAL en exécutant la commande ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="d6d19-305">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="d6d19-306">Attendez que SQLEXPR_x64.exe se termine avant de continuer :</span><span class="sxs-lookup"><span data-stu-id="d6d19-306">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="d6d19-307">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED = 0 /HIDECONSOLE /ACTION = installer/fonctionnalités = SQLEngine, outils/InstanceName = RTCLOCAL /TCPENABLED = 1 /SQLSVCACCOUNT = « NT\SERVICE » /SQLSYSADMINACCOUNTS = Builtin\ » Les administrateurs » /BROWSERSVCSTARTUPTYPE = /AGTSVCACCOUNT « Automatique » = « NTAUTHORITY\NetworkService » /SQLSVCSTARTUPTYPE = Automati</span><span class="sxs-lookup"><span data-stu-id="d6d19-307">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="d6d19-308">Créer l’instance SQL LYNCLOCAL en exécutant la commande ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="d6d19-308">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="d6d19-309">Attendez que SQLEXPR_x64.exe se termine avant de passer à l’étape suivante :</span><span class="sxs-lookup"><span data-stu-id="d6d19-309">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="d6d19-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED = 0 /HIDECONSOLE /ACTION = installer/fonctionnalités = SQLEngine, outils/InstanceName = LYNCLOCAL /TCPENABLED = 1 /SQLSVCACCOUNT = « NT\SERVICE » /SQLSYSADMINACCOUNTS = Builtin\ » Les administrateurs » /BROWSERSVCSTARTUPTYPE = /AGTSVCACCOUNT « Automatique » = « NTAUTHORITY\NetworkService » /SQLSVCSTARTUPTYPE = automatique</span><span class="sxs-lookup"><span data-stu-id="d6d19-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="d6d19-311">Exécutez Skype pour le programme d’installation Business Server 2015 RTM.</span><span class="sxs-lookup"><span data-stu-id="d6d19-311">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="d6d19-312">Suivez les étapes restantes dans la section conditions préalables ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="d6d19-312">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="d6d19-313">**Option 3 :** Vous pouvez remplacer manuellement les fichiers binaires dans un répertoire de support d’installation locale comme suit :</span><span class="sxs-lookup"><span data-stu-id="d6d19-313">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="d6d19-314">Installer les éléments prérequis pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="d6d19-314">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. 2. <span data-ttu-id="d6d19-315">Installer .NET 4.7 :</span><span class="sxs-lookup"><span data-stu-id="d6d19-315">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="d6d19-316">**Remarque :** Tout d’abord, nous avons introduit la prise en charge de .NET 4.7 dans Skype pour Business Server 2015 CU5 + (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="d6d19-316">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5+ (6.0.9319.281).</span></span> <span data-ttu-id="d6d19-317">Par conséquent, dans les étapes ultérieures ci-dessous nous mettrons à jour des composants principaux avant l’installation principale.</span><span class="sxs-lookup"><span data-stu-id="d6d19-317">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="d6d19-318">Téléchargement : https://www.microsoft.com/en-us/download/details.aspx?id=55167.</span><span class="sxs-lookup"><span data-stu-id="d6d19-318">Download: https://www.microsoft.com/en-us/download/details.aspx?id=55167.</span></span>
      - <span data-ttu-id="d6d19-319">Référence : [logiciel qui doit être installé avant un Skype pour le déploiement de Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="d6d19-319">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="d6d19-320">Copiez les fichiers/dossiers ISO :</span><span class="sxs-lookup"><span data-stu-id="d6d19-320">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="d6d19-321">Skype pour Business Server 2015 ISO attaché, ouvrez le répertoire racine du lecteur, il est joint sous (Ex : d :\) dans l’Explorateur de fichiers.</span><span class="sxs-lookup"><span data-stu-id="d6d19-321">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="d6d19-322">Copiez tous les fichiers et dossiers dans un dossier sur un disque local (Ex : C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="d6d19-322">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="d6d19-323">**Remarque :** Avant d’installer les composants, certains fichiers devront être mis à jour pour la prise en charge de TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="d6d19-323">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="d6d19-324">Remplacez les Packages MSI/EXE :</span><span class="sxs-lookup"><span data-stu-id="d6d19-324">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="d6d19-325">Remplacez les packages MSI et EXE existants dans le dossier/amd64//Setup du support d’installation sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="d6d19-325">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="d6d19-326">SQL 2014 SP2 Express :https://www.microsoft.com/en-us/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="d6d19-326">SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="d6d19-327">Renommez SQLEXPR_x64 sur l’ordinateur local et remplacez le fichier existant dans l’installation/amd64/dossier du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="d6d19-327">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="d6d19-328">SQL Native Client :https://www.microsoft.com/en-us/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="d6d19-328">SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="d6d19-329">**Remarque :** Renommez ce si nécessaire pour sqlncli.msi et remplacez le fichier existant qui existe dans l’installation/amd64/dossier du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="d6d19-329">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="d6d19-330">Objets de gestion SQL :https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="d6d19-330">SQL Management Objects: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="d6d19-331">**Remarque :** Le pack de fonctionnalités aura un grand nombre d’éléments qui peuvent être téléchargés.</span><span class="sxs-lookup"><span data-stu-id="d6d19-331">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="d6d19-332">Sélectionnez cette option pour télécharger SharedManagementObjects.msi uniquement.</span><span class="sxs-lookup"><span data-stu-id="d6d19-332">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="d6d19-333">**Remarque :** Remplacer le fichier existant qui existe dans l’installation/amd64/dossier du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="d6d19-333">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="d6d19-334">Types CLR SQL :https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="d6d19-334">SQL CLR Types: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="d6d19-335">**Remarque :** Le pack de fonctionnalités aura un grand nombre d’éléments qui peuvent être téléchargés.</span><span class="sxs-lookup"><span data-stu-id="d6d19-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="d6d19-336">Sélectionnez cette option pour télécharger CQLSysClrTypes.msi uniquement</span><span class="sxs-lookup"><span data-stu-id="d6d19-336">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="d6d19-337">**Remarque**: remplacer le fichier existant qui existe dans l’installation/amd64/dossier du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="d6d19-337">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="d6d19-338">Installez les composants principaux :</span><span class="sxs-lookup"><span data-stu-id="d6d19-338">Install Core Components:</span></span> 
    - <span data-ttu-id="d6d19-339">Exécutez Setup.exe à partir de l’installation/amd64/dossier du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="d6d19-339">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="d6d19-340">Suivez les instructions pour installer les composants principaux</span><span class="sxs-lookup"><span data-stu-id="d6d19-340">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="d6d19-341">Fermez les composants principaux.</span><span class="sxs-lookup"><span data-stu-id="d6d19-341">Close Core Components.</span></span>
6. <span data-ttu-id="d6d19-342">Mettre à jour des composants principaux :</span><span class="sxs-lookup"><span data-stu-id="d6d19-342">Update Core Components:</span></span> 
    - <span data-ttu-id="d6d19-343">Téléchargez le Skype pour le programme d’installation de Business mise à jour.</span><span class="sxs-lookup"><span data-stu-id="d6d19-343">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="d6d19-344">Exécutez le programme d’installation pour mettre à jour les composants principaux et installer les compteurs de performance.</span><span class="sxs-lookup"><span data-stu-id="d6d19-344">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="d6d19-345">**Remarque :** La version de CU6HF2, la fonctionnalité de mise à jour automatique actuellement uniquement installera jusqu'à CU6.</span><span class="sxs-lookup"><span data-stu-id="d6d19-345">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="d6d19-346">Par conséquent, la mise à jour doit être exécuté séparément pour mettre à jour des composants principaux pour 6.0.9319.516.</span><span class="sxs-lookup"><span data-stu-id="d6d19-346">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="d6d19-347">Référence :https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="d6d19-347">Reference: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="d6d19-348">Installer les outils d’administration (facultatifs) :</span><span class="sxs-lookup"><span data-stu-id="d6d19-348">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="d6d19-349">Vous allez installer le Client natif Microsoft SQL Server 2012, SQL Server 2014 Management Objects (x64) et Types CLR du système Microsoft pour SQL Server 2014 (x64) en utilisant les fichiers de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="d6d19-349">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="d6d19-350">En outre, le Skype pour le Générateur de topologie Business Server 2015 et le panneau de configuration sera disponible sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="d6d19-350">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="d6d19-351">Magasin de configurations Local Installation (étape 1) :</span><span class="sxs-lookup"><span data-stu-id="d6d19-351">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="d6d19-352">Ouvrir l’Assistant déploiement, cliquez sur Installer ou mettre à jour Skype pour le système de serveur d’entreprise, puis cliquez sur **exécuter** à l’étape 1 : installer le magasin de Configuration Local.</span><span class="sxs-lookup"><span data-stu-id="d6d19-352">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="d6d19-353">Cliquez sur **suivant** dans la boîte de dialogue **Installer le magasin de Configuration Local** .</span><span class="sxs-lookup"><span data-stu-id="d6d19-353">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="d6d19-354">![Boîte de dialogue installer le magasin de configurations Local](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="d6d19-354">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="d6d19-355">Passez en revue les résultats et assurez-vous que l’état de la tâche est terminée.</span><span class="sxs-lookup"><span data-stu-id="d6d19-355">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="d6d19-356">Passez en revue le fichier journal en cliquant sur **Afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="d6d19-356">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="d6d19-357">![État de la tâche apparaisse comme terminé](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="d6d19-357">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="d6d19-358">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="d6d19-358">Click **Finish**.</span></span>
9. <span data-ttu-id="d6d19-359">Définir ou supprimer Skype pour les composants de serveur d’entreprise (étape 2) :</span><span class="sxs-lookup"><span data-stu-id="d6d19-359">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="d6d19-360">Ouvrir l’Assistant déploiement, cliquez sur **installer ou mise à jour Skype pour le système de serveur d’entreprise**, cliquez sur **exécuter** à l’étape 2 : configurer ou supprimer Skype pour les composants de serveur d’entreprise</span><span class="sxs-lookup"><span data-stu-id="d6d19-360">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="d6d19-361">Cliquez sur **suivant** dans Définissez les Skype pour la boîte de dialogue composants Business Server.</span><span class="sxs-lookup"><span data-stu-id="d6d19-361">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="d6d19-362">![Définir des Skype pour fenêtre composants Business Server](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="d6d19-362">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="d6d19-363">Passez en revue le journal à l’aide d’afficher le journal et valider que le programme d’installation terminé sans problème.</span><span class="sxs-lookup"><span data-stu-id="d6d19-363">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="d6d19-364">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="d6d19-364">Click **Finish**.</span></span>
10. <span data-ttu-id="d6d19-365">Poursuivre l’installation supplémentaire et la configuration selon les besoins (vous pouvez reprendre des procédures d’installation normal à ce stade).</span><span class="sxs-lookup"><span data-stu-id="d6d19-365">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
