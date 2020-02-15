---
title: Désactivation de TLS 1.0/1.1 dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Résumé : Préparez et implémentez la désactivation de TLS 1,0 et 1,1 dans vos environnements.'
ms.openlocfilehash: 0a25060463ed3b67db8ca523171c2bc48660293d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42012747"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="39359-103">Désactivation de TLS 1.0/1.1 dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="39359-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="39359-104">L’objectif de cet article est de fournir les instructions nécessaires pour vous préparer à la désactivation de la désactivation de TLS 1,0 et 1,1 dans vos environnements.</span><span class="sxs-lookup"><span data-stu-id="39359-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="39359-105">Ce processus nécessite une planification et une préparation étendues.</span><span class="sxs-lookup"><span data-stu-id="39359-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="39359-106">Consultez attentivement toutes les informations contenues dans cet article lorsque vous prévoyez de désactiver TLS 1,0 et 1,1 pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="39359-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="39359-107">Notez qu’il existe de nombreuses dépendances externes et conditions de connectivité pouvant être affectées par la désactivation de TLS 1.0/1.1, de sorte que la planification et les tests détaillés sont justifiés.</span><span class="sxs-lookup"><span data-stu-id="39359-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="39359-108">Contenu de cet article</span><span class="sxs-lookup"><span data-stu-id="39359-108">In this article</span></span>

- [<span data-ttu-id="39359-109">Arrière-plan et étendue</span><span class="sxs-lookup"><span data-stu-id="39359-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="39359-110">Conditions préalables et processus</span><span class="sxs-lookup"><span data-stu-id="39359-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="39359-111">Scénarios de déploiement avancés</span><span class="sxs-lookup"><span data-stu-id="39359-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="39359-112">Arrière-plan</span><span class="sxs-lookup"><span data-stu-id="39359-112">Background</span></span>

<span data-ttu-id="39359-113">Les principaux pilotes permettant de fournir TLS 1,0 et 1,1 désactivent la prise en charge de Skype entreprise Server en local sont les exigences en matière de normes de sécurité PCI (Security Card Industry) et de normes de traitement des informations fédérales.</span><span class="sxs-lookup"><span data-stu-id="39359-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="39359-114">Vous trouverez plus d’informations sur les exigences PCI [ici](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span><span class="sxs-lookup"><span data-stu-id="39359-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="39359-115">Microsoft ne peut pas indiquer si votre organisation doit respecter ces exigences ou d’autres.</span><span class="sxs-lookup"><span data-stu-id="39359-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="39359-116">Vous devez déterminer s’il est nécessaire de désactiver TLS 1,0 et/ou 1,1 dans vos environnements.</span><span class="sxs-lookup"><span data-stu-id="39359-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="39359-117">Microsoft a publié un livre blanc sur le protocole TLS disponible [ici](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), et nous vous recommandons également la lecture d’arrière-plan disponible dans ce [blog Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span><span class="sxs-lookup"><span data-stu-id="39359-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="39359-118">Étendue de prise en charge</span><span class="sxs-lookup"><span data-stu-id="39359-118">Supportability Scope</span></span>

<span data-ttu-id="39359-119">L' *étendue* fait référence aux limites de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="39359-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="39359-120">*Entièrement testé et pris en charge* , nous mettons entièrement en service et nous avons testé la désactivation des protocoles TLS 1,0 et 1,1 pour les versions de produit indiquées.</span><span class="sxs-lookup"><span data-stu-id="39359-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="39359-121">*En cours d’examen* , c’est juste cela : Nous étudions activement l’intégration de ces produits à la prise en charge de la désactivation TLS.</span><span class="sxs-lookup"><span data-stu-id="39359-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="39359-122">« *Hors de portée* » signifie que ces versions de produit ne prennent pas en charge la désactivation de TLS 1,0 ou 1,1 et ne fonctionneront pas, avec les exceptions indiquées.</span><span class="sxs-lookup"><span data-stu-id="39359-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="39359-123">Serveurs entièrement testés et pris en charge</span><span class="sxs-lookup"><span data-stu-id="39359-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="39359-124">Skype entreprise Server 2019 CU1 17.0.2046.123 (juin 2019) ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="39359-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="39359-125">Skype entreprise Server 2015 CU9 6.0.9319.548 (2019) ou version ultérieure sur Windows Server 2012 (avec KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou remplacement de mise à jour), 2012 R2 ou 2016.</span><span class="sxs-lookup"><span data-stu-id="39359-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="39359-126">Mise à niveau sur place de Skype entreprise Server 2015 avec CU9 6.0.9319.548 (2019) ou version ultérieure sur Windows Server 2008 R2, 2012 (avec KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou remplacement de mise à jour) ou 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="39359-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="39359-127">Exchange Connectivity and Outlook Web App avec Exchange Server 2010 SP3 RU19 ou supérieur, conseils [ici](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="39359-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="39359-128">Survivable Branch Appliance (SBA) avec Skype entreprise Server 2015 CU6 HF2 ou version ultérieure (vérifiez auprès de votre fournisseur qu’il a empaqueté les mises à jour appropriée et qu’il a été mis à disposition pour votre appliance)</span><span class="sxs-lookup"><span data-stu-id="39359-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="39359-129">Survivable Branch Server (SBS) avec Skype entreprise Server 2015 CU6 HF2 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="39359-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="39359-130">**Rôle Edge**Lync Server 2013 uniquement, cela est dû au fait que le rôle Edge n’a pas de dépendance sur Windows Fabric 1,0.</span><span class="sxs-lookup"><span data-stu-id="39359-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="39359-131">Clients entièrement testés et pris en charge</span><span class="sxs-lookup"><span data-stu-id="39359-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="39359-132">Client de bureau Lync 2013 (Skype entreprise), MSI et C2R, y compris Basic [15.0.5023.1000 ou version ultérieure](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="39359-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="39359-133">Client de bureau Skype entreprise 2016, MSI [16.0.4678.1000 ou version ultérieure](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), y compris Basic</span><span class="sxs-lookup"><span data-stu-id="39359-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="39359-134">Skype entreprise 2016 cliquez pour exécuter les mises à jour d' [avril 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) :</span><span class="sxs-lookup"><span data-stu-id="39359-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="39359-135">Mensuel et semi-annuel ciblé, 16\.0\.9126\.2152 ou supérieur</span><span class="sxs-lookup"><span data-stu-id="39359-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="39359-136">Canal semi-annuel et différé, 16\.0\.8431\.2242 ou supérieur</span><span class="sxs-lookup"><span data-stu-id="39359-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="39359-137">Skype entreprise sur Mac 16,15 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="39359-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="39359-138">Skype entreprise pour iOS et Android 6,19 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="39359-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="39359-139">Microsoft teams rooms (précédemment appelé Skype Room System v2 SRS v2) 4.0.64.0 (2018 décembre) ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="39359-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="39359-140">Mise à jour de surface Hub pour Team Edition basée sur KB4499162 (mai 2019, version 15063,1835 de se) ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="39359-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="39359-141">Skype Web App 2015 CU6 HF2 ou version ultérieure (fourni avec le serveur)</span><span class="sxs-lookup"><span data-stu-id="39359-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="39359-142">En cours d’examen</span><span class="sxs-lookup"><span data-stu-id="39359-142">Currently being investigated</span></span>

- <span data-ttu-id="39359-143">Tableau de bord de qualité des appels (nouvelle installation après TLS 1,0, 1,1 ont été désactivés, voir ci-dessous) \*</span><span class="sxs-lookup"><span data-stu-id="39359-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="39359-144">Non compris</span><span class="sxs-lookup"><span data-stu-id="39359-144">Out of scope</span></span>

<span data-ttu-id="39359-145">Sauf indication contraire, les produits suivants ne sont pas dans le champ d’application de TLS 1.0/1.1 désactiver la prise en charge et ne fonctionneront pas dans un environnement où TLS 1,0 et 1,1 ont été désactivés.</span><span class="sxs-lookup"><span data-stu-id="39359-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="39359-146">Cela signifie que si vous utilisez toujours des serveurs ou des clients hors plage, vous devez les mettre à jour ou les supprimer si vous devez désactiver TLS 1.0/1.1 n’importe où dans votre déploiement sur site de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="39359-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="39359-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39359-147">Lync Server 2013</span></span>
- <span data-ttu-id="39359-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="39359-148">Lync Server 2010</span></span>
- <span data-ttu-id="39359-149">Windows Server 2008 ou inférieur</span><span class="sxs-lookup"><span data-stu-id="39359-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="39359-150">Lync pour Mac 2011</span><span class="sxs-lookup"><span data-stu-id="39359-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="39359-151">Lync 2013 pour mobile-iOS, iPad, Android ou Windows Phone</span><span class="sxs-lookup"><span data-stu-id="39359-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="39359-152">Client Windows Store « MX » Lync</span><span class="sxs-lookup"><span data-stu-id="39359-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="39359-153">Lync Room System (alias</span><span class="sxs-lookup"><span data-stu-id="39359-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="39359-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="39359-154">SRSv1).</span></span> <span data-ttu-id="39359-155">LRS a atteint la fin du support le 9 octobre à 2018 et ne sera pas mis à jour pour prendre en charge TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="39359-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="39359-156">Tous les clients Lync 2010</span><span class="sxs-lookup"><span data-stu-id="39359-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="39359-157">Aide de Lync Phone Edition-mise à jour [ici](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span><span class="sxs-lookup"><span data-stu-id="39359-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="39359-158">Serveur Survivable Branch Appliance 2013 (SBA) ou serveur Survivable Branch Server (SBS) basé sur</span><span class="sxs-lookup"><span data-stu-id="39359-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="39359-159">Version Cloud Connector (CCE)</span><span class="sxs-lookup"><span data-stu-id="39359-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="39359-160">Skype entreprise pour Windows Phone</span><span class="sxs-lookup"><span data-stu-id="39359-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="39359-161">Exceptions</span><span class="sxs-lookup"><span data-stu-id="39359-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="39359-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39359-162">Lync Server 2013</span></span>

<span data-ttu-id="39359-163">Lync Server 2013 prend une dépendance vis-à-vis de la version 1,0 de Windows fabric.</span><span class="sxs-lookup"><span data-stu-id="39359-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="39359-164">Dans la phase de conception de Lync Server 2013, Windows Fabric 1,0 a été choisi pour sa nouvelle architecture distribuée et sa nouvelle architecture distribuée pour fournir la réplication, la haute disponibilité et la tolérance de panne.</span><span class="sxs-lookup"><span data-stu-id="39359-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="39359-165">Au fil du temps, Skype entreprise Server et Windows Fabric ont grandement amélioré cette architecture conjointe avec une nouvelle conception importante dans les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="39359-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="39359-166">Le serveur Skype entreprise 2015 actuel utilise Windows Fabric 3,0, par exemple.</span><span class="sxs-lookup"><span data-stu-id="39359-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="39359-167">Malheureusement, Windows Fabric 1,0 **ne prend pas en charge TLS 1,2.  Toutefois, nous allons mettre à jour Lync Server 2013 pour qu’il fonctionne avec TLS 1,2**.</span><span class="sxs-lookup"><span data-stu-id="39359-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="39359-168">La prochaine mise à jour cumulative de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39359-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="39359-169">Nous fournissons la prise en charge du protocole TLS 1,2 pour permettre la coexistence, la migration, la Fédération et les scénarios hybrides.</span><span class="sxs-lookup"><span data-stu-id="39359-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="39359-170">Si votre organisation est requise pour désactiver TLS 1,0 et 1,1, et que vous utilisez actuellement Lync Server 2013, nous vous recommandons de commencer votre processus de planification, avec la possibilité d’effectuer une mise à niveau sur place ou une migration côte à côte (nouveaux pools, déplacer des utilisateurs) vers Skype Business Server 2015 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="39359-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="39359-171">Vous pouvez également accélérer la migration vers Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="39359-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="39359-172">Tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="39359-172">Call Quality Dashboard</span></span>

<span data-ttu-id="39359-173">Le tableau de bord de qualité des appels sur site a une dépendance vis-à-vis du TLS 1,0 lors de la nouvelle installation (première exécution de l’installation dans vos environnements locaux).</span><span class="sxs-lookup"><span data-stu-id="39359-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="39359-174">Nous étudions actuellement ce problème et nous prévoyons de publier un correctif dans un futur proche.</span><span class="sxs-lookup"><span data-stu-id="39359-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="39359-175">Si vous envisagez d’installer CQD et que vous désactivez également TLS 1,0, nous vous recommandons d’effectuer d’abord l’installation de CQD, puis de procéder à la désactivation de TLS 1,0.</span><span class="sxs-lookup"><span data-stu-id="39359-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="39359-176">Appareils tiers</span><span class="sxs-lookup"><span data-stu-id="39359-176">Third-party devices</span></span>

<span data-ttu-id="39359-177">Sur les appareils tiers comme les téléphones 3PIP, la vidéoconférence, les proxys inverses et les programmes d’équilibrage de la charge, veillez à valider la prise en charge du protocole TLS 1,2, tester soigneusement et contacter le fournisseur si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="39359-177">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="39359-178">Considérations relatives à la Fédération lors de la désactivation de TLS 1.0/1.1 sur les serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="39359-178">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="39359-179">Vous devez soigneusement planifier et prendre en compte l’impact de la désactivation de TLS 1.0/1.1 sur vos serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="39359-179">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="39359-180">Une fois les protocoles TLS 1,0 et 1,1 désactivés, vous pouvez constater que d’autres organisations ne sont plus en mesure de fédérer avec votre organisation.</span><span class="sxs-lookup"><span data-stu-id="39359-180">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="39359-181">Vous pouvez choisir de conserver TLS 1.0/1.1 activé sur vos serveurs Edge afin de maintenir la compatibilité descendante avec les systèmes externes sans correctif (SfB 2015, Lync 2013) ou plus (2010).</span><span class="sxs-lookup"><span data-stu-id="39359-181">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="39359-182">Microsoft ne peut pas fournir de conseils ou de recommandations sur le fait que votre réseau Edge (ou un réseau) tombe sous la norme PCI. Cela doit être déterminé par la société individuelle.</span><span class="sxs-lookup"><span data-stu-id="39359-182">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="39359-183">Skype entreprise Online prend en charge TLS 1,2 aujourd’hui, donc aucun impact sur la Fédération hybride/Fédération avec Online n’est attendu.</span><span class="sxs-lookup"><span data-stu-id="39359-183">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="39359-184">PIC (Public IM Connectivity) vers le service de grand public Skype : nous ne prévoyons pas la désactivation de TLS 1.0/1.1 pour influer sur la [connectivité Skype](../../deploy/deploy-skype-connectivity.md); Les passerelles Microsoft PIC sont déjà compatibles avec TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="39359-184">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="39359-185">Conditions préalables et processus</span><span class="sxs-lookup"><span data-stu-id="39359-185">Prerequisites and process</span></span>

<span data-ttu-id="39359-186">Sauf mention contraire ci-dessus, une fois que TLS 1,0 et 1,1 sont désactivés, les clients et les appareils ne fonctionnent plus correctement, ou du tout.</span><span class="sxs-lookup"><span data-stu-id="39359-186">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="39359-187">Cela peut signifier que vous devez suspendre et attendre des conseils mis à jour de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="39359-187">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="39359-188">Une fois que vous êtes satisfait du respect de toutes les exigences et que vous avez l’intention de traiter les lacunes, continuez.</span><span class="sxs-lookup"><span data-stu-id="39359-188">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="39359-189">À un niveau élevé, tandis que Skype entreprise Server 2019 est prêt pour la procédure d’installation, Skype entreprise Server 2015 nécessite l’installation de CU9, l’application de mises à jour préalables à .NET et SQL, le déploiement de clés de Registre prérequises, et enfin d’une autre les mises à jour de la configuration du système d’exploitation (par exemple, la désactivation de TLS 1,0 et 1,1 via importation de fichier de registre).</span><span class="sxs-lookup"><span data-stu-id="39359-189">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="39359-190">Il est très important que vous terminiez l’installation de tous les éléments prérequis, notamment Skype entreprise Server 2015 CU6 HF2, avant de désactiver TLS 1,0 et 1,1 sur n’importe quel serveur de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="39359-190">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="39359-191">Chaque serveur Skype entreprise Server, y compris le rôle Edge et les serveurs SQL-ends, nécessite les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="39359-191">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="39359-192">Assurez-vous également que tous les clients pris en charge (dans l’étendue) ont été mis à jour avec les versions minimales requises.</span><span class="sxs-lookup"><span data-stu-id="39359-192">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="39359-193">N’oubliez pas de mettre à jour les stations de travail de gestion.</span><span class="sxs-lookup"><span data-stu-id="39359-193">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="39359-194">Nous souhaitons suivre l’ordre habituel des opérations « Inside Out » pour la mise à niveau des serveurs Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="39359-194">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="39359-195">Traitez les pools de directeurs, la conversation permanente et les pools couplés comme vous le feriez normalement.</span><span class="sxs-lookup"><span data-stu-id="39359-195">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="39359-196">L’ordre et les méthodes de mise à niveau sont présentés [ici](topology.md) et [ici](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="39359-196">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="39359-197">Processus de haut niveau</span><span class="sxs-lookup"><span data-stu-id="39359-197">High-level process</span></span>

1. <span data-ttu-id="39359-198">Testez toutes les étapes de votre atelier avant de configurer des serveurs de production.</span><span class="sxs-lookup"><span data-stu-id="39359-198">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="39359-199">Sauvegardez et conservez une copie du Registre exporté sur chaque serveur individuel à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="39359-199">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="39359-200">Vous ne pouvez pas partager des registres entre les serveurs ; elles contiennent des clés basées sur un ordinateur unique.</span><span class="sxs-lookup"><span data-stu-id="39359-200">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="39359-201">Mettez à niveau tous les serveurs Skype entreprise 2015 vers CU9 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="39359-201">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="39359-202">Pour Skype entreprise Server 2019, effectuez une mise à niveau vers CU1 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="39359-202">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="39359-203">Installez tous les éléments prérequis sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="39359-203">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="39359-204">Déployer des clés de Registre prérequises.</span><span class="sxs-lookup"><span data-stu-id="39359-204">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="39359-205">Assurez-vous que tous les clients de portée sont mis à jour.</span><span class="sxs-lookup"><span data-stu-id="39359-205">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="39359-206">Désactivez les protocoles TLS 1,0 et 1,1 via l’importation du Registre.</span><span class="sxs-lookup"><span data-stu-id="39359-206">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="39359-207">Vérifier que les charges de travail fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="39359-207">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="39359-208">Si des problèmes sont rencontrés, dépanner et résoudre, ou</span><span class="sxs-lookup"><span data-stu-id="39359-208">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="39359-209">Restaurez le registre à partir de l’étape 2 pour réactiver TLS 1,0 et 1,1</span><span class="sxs-lookup"><span data-stu-id="39359-209">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="39359-210">Vérifiez que seul le protocole TLS 1,2 est utilisé.</span><span class="sxs-lookup"><span data-stu-id="39359-210">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="39359-211">Installer les composants requis sur tous les serveurs</span><span class="sxs-lookup"><span data-stu-id="39359-211">Install prerequisites to all servers</span></span>

<span data-ttu-id="39359-212">Une mise à jour étendue de la dépendance est requise avant de commencer à désactiver les protocoles TLS 1,0 et 1,1 au niveau du système d’exploitation dans vos déploiements Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="39359-212">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="39359-213">Les versions minimales suivantes peuvent prendre en charge TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="39359-213">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="39359-214">Déployez toutes les mises à jour prérequises sur chaque serveur Skype entreprise dans votre environnement avant de commencer à désactiver les protocoles TLS 1,0 et 1,1.</span><span class="sxs-lookup"><span data-stu-id="39359-214">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="39359-215">Skype entreprise Server 2015 CU9 6.0.9319.548 (2019) ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="39359-215">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="39359-216">[.NET Framework 4,7](https://www.microsoft.com/download/details.aspx?id=55167) ou version ultérieure avec SchUseStrongCrypto activé dans le registre (fourni ci-dessous)</span><span class="sxs-lookup"><span data-stu-id="39359-216">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="39359-217">SQL doit être mis à jour sur tous les serveurs Skype entreprise 2015 et les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="39359-217">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="39359-218">Mettre à jour le pool SQL Enterprise Edition en premier, puis leur FEs respectif.</span><span class="sxs-lookup"><span data-stu-id="39359-218">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="39359-219">[SQL server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)ou version ultérieure/sql Server 2012 SP2 + CU16 ou supérieur/ [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), ou version ultérieure/SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="39359-219">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="39359-220">SQL Server Native Client pour SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="39359-220">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="39359-221">[Pilote ODBC Microsoft 11 pour SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="39359-221">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="39359-222">Objets de gestion partagés pour SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="39359-222">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="39359-223">SQLSysClrTypes pour SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="39359-223">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="39359-224">Étapes de base pour l’installation des conditions préalables, dans l’ordre des opérations recommandées</span><span class="sxs-lookup"><span data-stu-id="39359-224">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="39359-225">Installez la mise à jour de Skype entreprise Server CU9 sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="39359-225">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="39359-226">Installez la mise à jour des composants à l’aide de l’utilitaire de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="39359-226">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="39359-227">Mettez à jour les bases de données conformément aux procédures documentées.</span><span class="sxs-lookup"><span data-stu-id="39359-227">Update databases according to documented procedures.</span></span> <span data-ttu-id="39359-228">Pour Skype entreprise Server 2015, voir KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="39359-228">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="39359-229">Validez les fonctionnalités du produit dans le déploiement avant de passer à d’autres modifications.</span><span class="sxs-lookup"><span data-stu-id="39359-229">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="39359-230">Téléchargez .NET 4,7 Offline Installer.</span><span class="sxs-lookup"><span data-stu-id="39359-230">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="39359-231">Aide[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="39359-231">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="39359-232">Assurez-vous que les services Skype entreprise Server 2015 sont arrêtés sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="39359-232">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="39359-233">Aide[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="39359-233">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="39359-234">Ex (Standard Edition) :```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="39359-234">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="39359-235">Ex (Enterprise Edition) :```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="39359-235">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="39359-236">Exécutez le package d’installation.</span><span class="sxs-lookup"><span data-stu-id="39359-236">Run the installer package.</span></span>
    7. <span data-ttu-id="39359-237">Redémarrez le serveur.</span><span class="sxs-lookup"><span data-stu-id="39359-237">Reboot the server.</span></span>
3. <span data-ttu-id="39359-238">Mettez à jour SQL Express 2014 sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="39359-238">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="39359-239">Aide[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="39359-239">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="39359-240">Télécharger SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="39359-240">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="39359-241">Aide[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="39359-241">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="39359-242">Copiez le support d’installation dans un dossier sur le serveur (par exemple : C:\ 01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="39359-242">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="39359-243">Vérifier que les services Skype entreprise Server 2015 sont arrêtés sur le serveur frontal</span><span class="sxs-lookup"><span data-stu-id="39359-243">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="39359-244">Ex (Standard Edition) :```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="39359-244">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="39359-245">Ex (Enterprise Edition) :```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="39359-245">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="39359-246">Ouvrir une invite de commandes d’administration et mettre à niveau tous les composants et les instances installés</span><span class="sxs-lookup"><span data-stu-id="39359-246">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="39359-247">Exemple : C:\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/QS/IAcceptSQLServerLicenseTerms/action = patch/AllInstances</span><span class="sxs-lookup"><span data-stu-id="39359-247">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="39359-248">Mettre à jour SQL Native Client.</span><span class="sxs-lookup"><span data-stu-id="39359-248">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="39359-249">Référence : [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="39359-249">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="39359-250">Télécharger à partir de[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="39359-250">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="39359-251">Vérifiez que les services Skype entreprise Server 2015 sont arrêtés sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="39359-251">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="39359-252">Ex (Standard Edition) :```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="39359-252">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="39359-253">Ex (Enterprise Edition) :```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="39359-253">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="39359-254">Arrêter l’exécution des instances SQL installées</span><span class="sxs-lookup"><span data-stu-id="39359-254">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="39359-255">Ex```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="39359-255">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="39359-256">Ex```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="39359-256">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="39359-257">Ex (Standard Edition uniquement) :```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="39359-257">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="39359-258">Installez la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="39359-258">Install the update.</span></span>
5. <span data-ttu-id="39359-259">Mettez à jour le pilote ODBC 11 pour SQL Server afin d’inclure la prise en charge de TLS 1,2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span><span class="sxs-lookup"><span data-stu-id="39359-259">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="39359-260">Téléchargez [le pilote ODBC 11 pour SQL Server-Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span><span class="sxs-lookup"><span data-stu-id="39359-260">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="39359-261">Assurez-vous que les services Skype entreprise Server 2015 sont arrêtés sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="39359-261">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="39359-262">Exemple (Standard Edition) :```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="39359-262">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="39359-263">Exemple (Enterprise Edition) :```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="39359-263">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="39359-264">Installez la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="39359-264">Install the update.</span></span>
6. <span data-ttu-id="39359-265">Déployer des clés de Registre prérequises.</span><span class="sxs-lookup"><span data-stu-id="39359-265">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="39359-266">Clés de Registre requises</span><span class="sxs-lookup"><span data-stu-id="39359-266">Pre-requisite registry keys</span></span>

<span data-ttu-id="39359-267">Copiez/collez le test suivant dans le bloc-notes et renommez TLSPreReq. reg ou un nom de votre choix, puis importez :</span><span class="sxs-lookup"><span data-stu-id="39359-267">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="39359-268">Pour les serveurs SQL back-end des pools Enterprise Edition, les conditions préalables et la désactivation TLS doivent être traitées comme les mises à jour SQL ou OS ; reportez-vous à :[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="39359-268">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="39359-269">Bien que l’application prérequise et la procédure de désactivation TLS puissent être combinées, nous vous recommandons vivement d’appliquer toutes les conditions préalables avant de désactiver TLS 1,0 et 1,1 au niveau du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="39359-269">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="39359-270">L’approche recommandée consiste à préparer l’environnement en déployant tous les éléments prérequis, en validant que toutes les charges de travail fonctionnent correctement et comme prévu, puis en poursuivant la désactivation de TLS 1.0/1.1 ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="39359-270">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="39359-271">Désactiver TLS 1,0 et 1,1 via l’importation du Registre</span><span class="sxs-lookup"><span data-stu-id="39359-271">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="39359-272">Avant de passer aux étapes suivantes, *Vérifiez que vous avez terminé toutes les conditions préalables et mis à jour les serveurs Skype entreprise*.</span><span class="sxs-lookup"><span data-stu-id="39359-272">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="39359-273">Copiez le texte suivant dans un fichier bloc-notes et renommez-le **TLSDisable. reg**:</span><span class="sxs-lookup"><span data-stu-id="39359-273">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="39359-274">Importez le fichier. reg sur chaque serveur pour lequel vous souhaitez désactiver TLS 1,0 et 1,1.</span><span class="sxs-lookup"><span data-stu-id="39359-274">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="39359-275">Redémarrez le serveur.</span><span class="sxs-lookup"><span data-stu-id="39359-275">Reboot the server.</span></span> <span data-ttu-id="39359-276">Une fois les services reconnectés, accédez au serveur suivant.</span><span class="sxs-lookup"><span data-stu-id="39359-276">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="39359-277">L’approche pour les pools Enterprise Edition est identique pour toutes les mises à jour du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="39359-277">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="39359-278">Vous avez peut-être remarqué que nous ne faisons pas seulement désactiver les protocoles TLS 1,0 et 1,1 ici.</span><span class="sxs-lookup"><span data-stu-id="39359-278">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="39359-279">Nous prenons en charge la réorganisation de la suite de chiffrement (comme indiqué ci-dessus) et la désactivation de certains chiffrements faibles plus anciens.</span><span class="sxs-lookup"><span data-stu-id="39359-279">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="39359-280">Il s’agit de la première fois que nous avons officiellement pris en charge ces modifications apportées aux API SCHANNEL et crypto sur Skype entreprise Server, et il est important de noter que ces modifications sont les seules à prendre en charge et qu’elles ont été testées pour le moment.</span><span class="sxs-lookup"><span data-stu-id="39359-280">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="39359-281">Nous pouvons envisager des configurations supplémentaires à l’avenir, mais pour l’instant, ne modifiez pas le fichier d’importation de Registre dans votre implémentation.</span><span class="sxs-lookup"><span data-stu-id="39359-281">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="39359-282">Vérifier que les charges de travail fonctionnent comme prévu</span><span class="sxs-lookup"><span data-stu-id="39359-282">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="39359-283">Une fois que TLS 1,0 et 1,1 ont été désactivés dans votre environnement, assurez-vous que toutes vos charges de travail principales fonctionnent comme prévu, comme la messagerie instantanée & la présence, les appels P2P, la voix entreprise, etc.</span><span class="sxs-lookup"><span data-stu-id="39359-283">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="39359-284">**Validation uniquement TLS 1,2 est utilisé**</span><span class="sxs-lookup"><span data-stu-id="39359-284">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="39359-285">Demandez à votre équipe de sécurité d’effectuer un nouvel audit du trafic Skype entreprise afin de vous assurer que les anciens protocoles TLS 1,0 et 1,1 ne sont plus utilisés.</span><span class="sxs-lookup"><span data-stu-id="39359-285">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="39359-286">Vous pouvez également utiliser Internet Explorer pour tester les connexions TLS aux services Web à partir de Skype entreprise Server 2015 après que TLS 1,0 et TLS 1,1 ont été désactivés.</span><span class="sxs-lookup"><span data-stu-id="39359-286">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="39359-287">Lancez Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="39359-287">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="39359-288">Sélectionnez **Outils** > **Internet options**.</span><span class="sxs-lookup"><span data-stu-id="39359-288">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="39359-289">Sélectionnez l’onglet **avancé** .</span><span class="sxs-lookup"><span data-stu-id="39359-289">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="39359-290">Sous **paramètres**, faites défiler vers le bas.</span><span class="sxs-lookup"><span data-stu-id="39359-290">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="39359-291">Vérifiez que TLS 1,0, TLS 1,1 et TLS 1,2 sont activés.</span><span class="sxs-lookup"><span data-stu-id="39359-291">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="39359-292">Parcourez l’URL du service Web interne de votre pool SfB 2015 (doit se connecter correctement).</span><span class="sxs-lookup"><span data-stu-id="39359-292">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="39359-293">Revenez dans Internet Explorer et désactivez l’option d' **utilisation de TLS 1,2** uniquement.</span><span class="sxs-lookup"><span data-stu-id="39359-293">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="39359-294">Parcourez l’URL du service Web interne de votre pool SfB 2015 (elle ne doit pas se connecter).</span><span class="sxs-lookup"><span data-stu-id="39359-294">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Options Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="39359-296">Scénarios de déploiement avancés</span><span class="sxs-lookup"><span data-stu-id="39359-296">Advanced deployment scenarios</span></span>

<span data-ttu-id="39359-297">Étant donné que certaines conditions préalables de dépendance sont requises pour prendre en charge TLS 1,2 dans Skype entreprise ser 2015, l’installation à partir de médias RTM échouera sur tous les systèmes où TLS 1,0 et 1,1 ont été désactivés.</span><span class="sxs-lookup"><span data-stu-id="39359-297">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="39359-298">**Le déploiement de nouveaux serveurs Standard Edition ou pools Enterprise Edition une fois les protocoles TLS 1,0 et 1,1 ont été désactivés dans votre environnement.**</span><span class="sxs-lookup"><span data-stu-id="39359-298">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="39359-299">**Option 1 :** Utilisez [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="39359-299">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="39359-300">Notez que nous mettons à jour SmartSetup pour prendre en charge les fichiers binaires SQL mis à jour dans une mise à jour cumulative future, et mettra à jour cet article à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="39359-300">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="39359-301">**Option 2 :** Pré-installer des instances SQL locales (RTCLOCAL et LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="39359-301">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="39359-302">Téléchargez et copiez SQL Express 2014 SP2 (SQLEXPR_x64. exe) dans le dossier local sur FE.</span><span class="sxs-lookup"><span data-stu-id="39359-302">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="39359-303">Supposons que le chemin d’accès au dossier <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="39359-303">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="39359-304">Lancez PowerShell ou l’invite de commandes et accédez à <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="39359-304">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="39359-305">Créez l’instance SQL RTCLOCAL en exécutant la commande ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="39359-305">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="39359-306">Patientez jusqu’à ce que SQLEXPR_x64. exe se termine avant de procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="39359-306">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="39359-307">SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = install/FEATURES = SQLEngine, Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = AUTOi</span><span class="sxs-lookup"><span data-stu-id="39359-307">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="39359-308">Créez l’instance SQL LYNCLOCAL en exécutant la commande ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="39359-308">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="39359-309">Patientez jusqu’à ce que SQLEXPR_x64. exe se termine avant de passer à l’étape suivante :</span><span class="sxs-lookup"><span data-stu-id="39359-309">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="39359-310">SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = install/FEATURES = SQLEngine, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automatic</span><span class="sxs-lookup"><span data-stu-id="39359-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="39359-311">Exécutez le programme d’installation de Skype entreprise Server 2015 RTM.</span><span class="sxs-lookup"><span data-stu-id="39359-311">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="39359-312">Suivez les étapes restantes de la section conditions préalables ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="39359-312">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="39359-313">**Option 3 :** Vous pouvez également remplacer manuellement les fichiers binaires dans un répertoire multimédia de l’installation locale comme suit :</span><span class="sxs-lookup"><span data-stu-id="39359-313">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="39359-314">Installer les composants requis pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="39359-314">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="39359-315">Installez .NET 4,7 :</span><span class="sxs-lookup"><span data-stu-id="39359-315">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="39359-316">**Remarque :** Nous avons introduit pour la première fois la prise en charge de .NET 4,7 dans Skype entreprise Server 2015 CU5 (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="39359-316">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="39359-317">Par conséquent, dans les étapes suivantes, nous allons mettre à jour les composants principaux avant l’installation principale.</span><span class="sxs-lookup"><span data-stu-id="39359-317">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="39359-318">Téléchargement : https://www.microsoft.com/download/details.aspx?id=55167.</span><span class="sxs-lookup"><span data-stu-id="39359-318">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="39359-319">Référence : [logiciels devant être installés avant un déploiement de Skype entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="39359-319">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="39359-320">Copier les fichiers/dossiers ISO :</span><span class="sxs-lookup"><span data-stu-id="39359-320">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="39359-321">Une fois Skype entreprise Server 2015 ISO attaché, ouvrez le répertoire racine du lecteur auquel il est attaché en tant que (par exemple :\) D : dans l’Explorateur de fichiers.</span><span class="sxs-lookup"><span data-stu-id="39359-321">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="39359-322">Copiez tous les dossiers et les fichiers dans un dossier sur un disque local (par exemple : C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="39359-322">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="39359-323">**Remarque :** Avant d’installer les composants, certains fichiers devront être mis à jour pour prendre en charge TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="39359-323">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="39359-324">Remplacez les packages MSI/EXE :</span><span class="sxs-lookup"><span data-stu-id="39359-324">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="39359-325">Remplacez les packages MSI et EXE existants dans le dossier/Setup/amd64/du support d’installation sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="39359-325">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="39359-326">SQL 2014 SP2 Express :https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="39359-326">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="39359-327">Renommez-le en SQLEXPR_x64 sur l’ordinateur local et remplacez le fichier existant dans le dossier Setup/amd64/du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="39359-327">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="39359-328">SQL Native Client :https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="39359-328">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="39359-329">**Remarque :** Renommez-le, si nécessaire, sqlncli. msi, puis remplacez le fichier existant qui existe dans le dossier Setup/amd64/du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="39359-329">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="39359-330">Objets de gestion SQL :https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="39359-330">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="39359-331">**Remarque :** Le Feature Pack aura un grand nombre d’éléments qui peuvent être téléchargés.</span><span class="sxs-lookup"><span data-stu-id="39359-331">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="39359-332">Sélectionnez cette option pour télécharger SharedManagementObjects. msi uniquement.</span><span class="sxs-lookup"><span data-stu-id="39359-332">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="39359-333">**Remarque :** Remplacez le fichier existant qui existe dans le dossier Setup/amd64/du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="39359-333">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="39359-334">Types CLR SQL :https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="39359-334">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="39359-335">**Remarque :** Le Feature Pack aura un grand nombre d’éléments qui peuvent être téléchargés.</span><span class="sxs-lookup"><span data-stu-id="39359-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="39359-336">Sélectionnez pour télécharger CQLSysClrTypes. msi uniquement</span><span class="sxs-lookup"><span data-stu-id="39359-336">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="39359-337">**Remarque**: remplacez le fichier existant qui existe dans le dossier Setup/amd64/du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="39359-337">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="39359-338">Installer les composants principaux :</span><span class="sxs-lookup"><span data-stu-id="39359-338">Install Core Components:</span></span> 
    - <span data-ttu-id="39359-339">Exécutez setup. exe à partir du dossier Setup/amd64/du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="39359-339">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="39359-340">Suivez les instructions pour installer les composants principaux</span><span class="sxs-lookup"><span data-stu-id="39359-340">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="39359-341">Fermez les composants principaux.</span><span class="sxs-lookup"><span data-stu-id="39359-341">Close Core Components.</span></span>
6. <span data-ttu-id="39359-342">Mettre à jour les composants principaux :</span><span class="sxs-lookup"><span data-stu-id="39359-342">Update Core Components:</span></span> 
    - <span data-ttu-id="39359-343">Téléchargez le programme d’installation de la mise à jour de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="39359-343">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="39359-344">Exécutez le programme d’installation pour mettre à jour les composants principaux et installer les compteurs de performance.</span><span class="sxs-lookup"><span data-stu-id="39359-344">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="39359-345">**Remarque :** À partir de la version d’CU6HF2, la fonctionnalité de mise à jour automatique est actuellement uniquement installée sur CU6.</span><span class="sxs-lookup"><span data-stu-id="39359-345">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="39359-346">Par conséquent, l’utilitaire de mise à jour doit être exécuté séparément pour mettre à jour les composants principaux vers 6.0.9319.516.</span><span class="sxs-lookup"><span data-stu-id="39359-346">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="39359-347">Aidehttps://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="39359-347">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="39359-348">Installer les outils d’administration (facultatif) :</span><span class="sxs-lookup"><span data-stu-id="39359-348">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="39359-349">Cette opération installe le client natif Microsoft SQL Server 2012, les objets de gestion SQL Server 2014 (x64) et les types CLR du système Microsoft pour SQL Server 2014 (x64) à l’aide des fichiers mis à jour.</span><span class="sxs-lookup"><span data-stu-id="39359-349">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="39359-350">De plus, le générateur de topologies Skype entreprise Server 2015 et le panneau de configuration sont disponibles sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="39359-350">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="39359-351">Installer le magasin de configurations local (étape 1) :</span><span class="sxs-lookup"><span data-stu-id="39359-351">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="39359-352">Ouvrez l’Assistant Déploiement, cliquez sur installer ou mettre à jour le système Skype entreprise Server, puis cliquez sur **exécuter** à l’étape 1 : installer le magasin de configurations local.</span><span class="sxs-lookup"><span data-stu-id="39359-352">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="39359-353">Cliquez sur **suivant** dans la boîte de dialogue **installer le magasin de configurations local** .</span><span class="sxs-lookup"><span data-stu-id="39359-353">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="39359-354">![Boîte de dialogue installer le magasin de configurations local](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="39359-354">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="39359-355">Examinez les résultats et assurez-vous que l’état de la tâche est terminé.</span><span class="sxs-lookup"><span data-stu-id="39359-355">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="39359-356">Consultez le fichier journal résultant en cliquant sur **afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="39359-356">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="39359-357">![L’état de la tâche indique terminé](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="39359-357">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="39359-358">Cliquez sur**Terminer**.</span><span class="sxs-lookup"><span data-stu-id="39359-358">Click **Finish**.</span></span>
9. <span data-ttu-id="39359-359">Configurez ou supprimez les composants Skype entreprise Server (étape 2) :</span><span class="sxs-lookup"><span data-stu-id="39359-359">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="39359-360">Ouvrez l’Assistant Déploiement, cliquez sur **installer ou mettre à jour le système Skype entreprise Server**, puis cliquez sur **exécuter** à l’étape 2 : configurer ou supprimer des composants Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="39359-360">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="39359-361">Cliquez sur **suivant** dans la boîte de dialogue Configurer les composants de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="39359-361">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="39359-362">![fenêtre Configurer les composants de Skype entreprise Server](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="39359-362">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="39359-363">Examinez le journal à l’aide du journal d’affichage et vérifiez que l’installation s’est effectuée sans problèmes.</span><span class="sxs-lookup"><span data-stu-id="39359-363">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="39359-364">Cliquez sur**Terminer**.</span><span class="sxs-lookup"><span data-stu-id="39359-364">Click **Finish**.</span></span>
10. <span data-ttu-id="39359-365">Poursuivez l’installation et la configuration supplémentaires, si nécessaire (vous pouvez reprendre les procédures d’installation normales à ce stade).</span><span class="sxs-lookup"><span data-stu-id="39359-365">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
