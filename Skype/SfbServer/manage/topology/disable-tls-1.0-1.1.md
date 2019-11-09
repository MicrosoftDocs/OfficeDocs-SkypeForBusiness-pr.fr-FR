---
title: Désactiver TLS 1.0/1.1 dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Résumé : Préparez-vous à la désactivation de TLS 1,0 et 1,1 dans vos environnements.'
ms.openlocfilehash: ce158aeaa84e00367b265404fe3d3407606f4759
ms.sourcegitcommit: f3b698379eb663202ce127eeaf6c07328c166556
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2019
ms.locfileid: "38077437"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="b808c-103">Désactiver TLS 1.0/1.1 dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b808c-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="b808c-104">Dans le cadre de cet article, vous devez fournir les recommandations nécessaires pour vous préparer à la désactivation de TLS 1,0 et 1,1 dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="b808c-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="b808c-105">Ce processus nécessite une planification et une préparation complètes.</span><span class="sxs-lookup"><span data-stu-id="b808c-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="b808c-106">Veuillez lire attentivement toutes les informations contenues dans cet article lorsque vous planifiez la désactivation de TLS 1,0 et 1,1 pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b808c-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="b808c-107">Notez qu’il existe de nombreuses dépendances externes et conditions de connectivité qui peuvent être affectées en désactivant TLS 1.0/1.1, de telle sorte que la planification et le test de grande envergure se garantissent.</span><span class="sxs-lookup"><span data-stu-id="b808c-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="b808c-108">Dans cet article</span><span class="sxs-lookup"><span data-stu-id="b808c-108">In this article</span></span>

- [<span data-ttu-id="b808c-109">Arrière-plan et étendue</span><span class="sxs-lookup"><span data-stu-id="b808c-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="b808c-110">Conditions préalables et processus</span><span class="sxs-lookup"><span data-stu-id="b808c-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="b808c-111">Scénarios de déploiement avancés</span><span class="sxs-lookup"><span data-stu-id="b808c-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="b808c-112">Arrière-plan</span><span class="sxs-lookup"><span data-stu-id="b808c-112">Background</span></span>

<span data-ttu-id="b808c-113">Les principaux pilotes pour la mise à niveau de TLS 1,0 et 1,1 la prise en charge de Skype entreprise Server sur site sont les exigences en matière de cartes de paiement (PCI) et de Processing information standards.</span><span class="sxs-lookup"><span data-stu-id="b808c-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="b808c-114">Pour plus d’informations sur la configuration requise pour PCI, consultez la [page suivante](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span><span class="sxs-lookup"><span data-stu-id="b808c-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="b808c-115">Microsoft ne peut pas vous fournir des conseils quant à la nécessité ou non que votre organisation respecte ces conditions.</span><span class="sxs-lookup"><span data-stu-id="b808c-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="b808c-116">Vous devez déterminer s’il est nécessaire de désactiver TLS 1,0 et/ou 1,1 dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="b808c-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="b808c-117">Microsoft a créé un livre blanc sur TLS disponible [ici](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)et nous recommandons également la lecture en arrière-plan disponible sur ce [blog Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span><span class="sxs-lookup"><span data-stu-id="b808c-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="b808c-118">Étendue de la prise en charge</span><span class="sxs-lookup"><span data-stu-id="b808c-118">Supportability Scope</span></span>

<span data-ttu-id="b808c-119">*Scope* fait référence aux limites de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="b808c-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="b808c-120">*Entièrement testés et pris en charge* , nous nous chargeons de la totalité et nous avons testé la désactivation de TLS 1,0 et 1,1 pour les versions de produit indiquées.</span><span class="sxs-lookup"><span data-stu-id="b808c-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="b808c-121">Pour le moment, il n’y a *pas d’étude* ; Nous étudions activement la mise en oeuvre de ces produits pour la prise en charge de la mise à niveau de TLS.</span><span class="sxs-lookup"><span data-stu-id="b808c-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="b808c-122">*Hors de l’objectif* signifie que ces versions de produit ne prennent pas en charge la désactivation de TLS 1,0 ou 1,1 et ne fonctionne pas, avec les exceptions indiquées.</span><span class="sxs-lookup"><span data-stu-id="b808c-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="b808c-123">Serveurs entièrement testés et pris en charge</span><span class="sxs-lookup"><span data-stu-id="b808c-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="b808c-124">Skype entreprise Server 2019 CU1 17.0.2046.123 (juin 2019) ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="b808c-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="b808c-125">Skype entreprise Server 2015 CU9 6.0.9319.548 (2019) ou une version ultérieure sur Windows Server 2012 (avec KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou remplacement de mise à jour), 2012 R2 ou 2016.</span><span class="sxs-lookup"><span data-stu-id="b808c-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="b808c-126">Mise à niveau sur place du serveur Skype entreprise Server 2015 avec CU9 6.0.9319.548 (2019) ou une version ultérieure sur Windows Server 2008 R2, 2012 (avec KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou version de remplacement) ou 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="b808c-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="b808c-127">Connectivité Exchange et Outlook Web App avec Exchange Server 2010 SP3 RU19 ou une version ultérieure, aide [ici](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="b808c-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="b808c-128">Appareil de branchement survivant (SBA) avec Skype entreprise Server 2015 CU6 HF2 ou une version ultérieure (vérifiez auprès de votre fournisseur qu’il a mis à jour les mises à jour de votre application.)</span><span class="sxs-lookup"><span data-stu-id="b808c-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="b808c-129">Serveur de succursales survivables (SBS) avec Skype entreprise Server 2015 CU6 HF2 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="b808c-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="b808c-130">Le **rôle Edge**de Lync Server 2013 uniquement, car le rôle Edge n’a pas de dépendance sur Windows Fabric 1,0.</span><span class="sxs-lookup"><span data-stu-id="b808c-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="b808c-131">Clients entièrement testés et pris en charge</span><span class="sxs-lookup"><span data-stu-id="b808c-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="b808c-132">Client de bureau Lync 2013 (Skype entreprise), MSI et C2R, notamment les [numéro 15.0.5023.1000 de base ou version ultérieure](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="b808c-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="b808c-133">Le client de bureau 2016 de Skype entreprise, [16.0.4678.1000 MSI ou version ultérieure](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), y compris de base</span><span class="sxs-lookup"><span data-stu-id="b808c-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="b808c-134">Skype entreprise 2016 Cliquer pour exécuter nécessite les mises à jour d' [avril 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) :</span><span class="sxs-lookup"><span data-stu-id="b808c-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="b808c-135">Cibles mensuelles et semestrielles, 16\.0\.9126\.2152 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="b808c-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="b808c-136">Un canal semi-annuel et un canal différé\.,\.16\.0 8431 2242 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="b808c-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="b808c-137">Skype entreprise sur Mac 16,15 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="b808c-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="b808c-138">Skype entreprise pour iOS et Android 6,19 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="b808c-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="b808c-139">Microsoft teams sur les salles (auparavant appelées Skype Room System v2 SRS v2) 4.0.64.0 (2018 décembre) ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="b808c-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="b808c-140">Mise à jour de surface Hub pour Team Edition basée sur KB4499162 (2019, version 15063,1835) ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="b808c-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="b808c-141">Skype Web App 2015 CU6 HF2 ou une version ultérieure (fournie avec le serveur)</span><span class="sxs-lookup"><span data-stu-id="b808c-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="b808c-142">Examen en cours</span><span class="sxs-lookup"><span data-stu-id="b808c-142">Currently being investigated</span></span>

- <span data-ttu-id="b808c-143">Tableau de bord de qualité des appels (nouvelle installation après le 1,0 de TLS, 1,1 a été désactivé, voir ci-dessous) \*</span><span class="sxs-lookup"><span data-stu-id="b808c-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="b808c-144">Hors de l’objectif</span><span class="sxs-lookup"><span data-stu-id="b808c-144">Out of scope</span></span>

<span data-ttu-id="b808c-145">Sauf indication contraire, les produits suivants ne peuvent pas être utilisés pour la prise en charge de TLS 1.0/1.1 et ne fonctionnent pas dans un environnement où les protocoles TLS 1,0 et 1,1 ont été désactivés.</span><span class="sxs-lookup"><span data-stu-id="b808c-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="b808c-146">Ce qui signifie que : Si vous utilisez toujours des serveurs ou des clients hors plage, vous devez les mettre à jour ou supprimer si vous devez désactiver TLS 1.0/1.1 n’importe où dans votre déploiement Skype entreprise Server local.</span><span class="sxs-lookup"><span data-stu-id="b808c-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="b808c-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b808c-147">Lync Server 2013</span></span>
- <span data-ttu-id="b808c-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b808c-148">Lync Server 2010</span></span>
- <span data-ttu-id="b808c-149">Windows Server 2008 ou version antérieure</span><span class="sxs-lookup"><span data-stu-id="b808c-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="b808c-150">Lync pour Mac 2011</span><span class="sxs-lookup"><span data-stu-id="b808c-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="b808c-151">Lync 2013 pour mobile-iOS, iPad, Android ou Windows Phone</span><span class="sxs-lookup"><span data-stu-id="b808c-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="b808c-152">Client Windows Store MX Lync</span><span class="sxs-lookup"><span data-stu-id="b808c-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="b808c-153">Système de salle Lync (alias</span><span class="sxs-lookup"><span data-stu-id="b808c-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="b808c-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="b808c-154">SRSv1).</span></span> <span data-ttu-id="b808c-155">LRS atteint la fin de la prise en charge le 9 octobre 2018 et ne sera pas mis à jour pour prendre en charge TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="b808c-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="b808c-156">Tous les clients Lync 2010</span><span class="sxs-lookup"><span data-stu-id="b808c-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="b808c-157">Lync Phone Edition : conseils mis à jour [ici](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span><span class="sxs-lookup"><span data-stu-id="b808c-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="b808c-158">Application de succursales Survivables 2013 (SBA) ou serveur de succursales Survivables (SBS)</span><span class="sxs-lookup"><span data-stu-id="b808c-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="b808c-159">Édition Cloud Connector (CCE)</span><span class="sxs-lookup"><span data-stu-id="b808c-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="b808c-160">Skype entreprise pour Windows Phone</span><span class="sxs-lookup"><span data-stu-id="b808c-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="b808c-161">Exceptions</span><span class="sxs-lookup"><span data-stu-id="b808c-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="b808c-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b808c-162">Lync Server 2013</span></span>

<span data-ttu-id="b808c-163">Lync Server 2013 est dépendant du Windows Fabric version 1,0.</span><span class="sxs-lookup"><span data-stu-id="b808c-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="b808c-164">Dans la phase de conception de Lync Server 2013, Windows Fabric 1,0 a été choisi pour sa nouvelle architecture distribuée et attrayante pour fournir une réplication, une disponibilité élevée et une tolérance de panne.</span><span class="sxs-lookup"><span data-stu-id="b808c-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="b808c-165">Au fil du temps, Skype entreprise Server et Windows Fabric ont considérablement amélioré cette architecture commune grâce à une nouvelle conception importante dans les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="b808c-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="b808c-166">Le serveur Skype entreprise 2015 actuel utilise le Windows Fabric 3,0, par exemple.</span><span class="sxs-lookup"><span data-stu-id="b808c-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="b808c-167">Malheureusement, Windows Fabric 1,0 **ne prend pas en charge TLS 1,2.  Toutefois, nous allons mettre à jour Lync Server 2013 pour fonctionner avec TLS 1,2**.</span><span class="sxs-lookup"><span data-stu-id="b808c-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="b808c-168">Cette opération sera disponible dans la prochaine mise à jour cumulative pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b808c-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="b808c-169">Nous proposons une prise en charge de la prise en charge des 1,2 TLS pour les scénarios de coexistence, de migration, de Fédération et hybride.</span><span class="sxs-lookup"><span data-stu-id="b808c-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="b808c-170">Si votre organisation est tenue de désactiver TLS 1,0 et 1,1, et que vous utilisez actuellement Lync Server 2013, nous vous conseillons de commencer le processus de planification, il est possible que vous deviez effectuer une mise à niveau sur place ou une migration côte à côte (nouveaux utilisateurs, déplacer des utilisateurs) vers Skype Business Server 2015 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="b808c-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="b808c-171">Vous pouvez également accélérer la migration vers Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="b808c-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="b808c-172">Tableau de bord de la qualité des appels</span><span class="sxs-lookup"><span data-stu-id="b808c-172">Call Quality Dashboard</span></span>

<span data-ttu-id="b808c-173">Le tableau de bord de qualité des appels sur site comporte actuellement une dépendance sur TLS 1,0 lors de l’installation (première utilisation dans votre environnement local).</span><span class="sxs-lookup"><span data-stu-id="b808c-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="b808c-174">Nous étudions actuellement ce problème et vous envisagez de publier un correctif à un avenir proche.</span><span class="sxs-lookup"><span data-stu-id="b808c-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="b808c-175">Si vous envisagez d’installer bord et que vous avez également désactivé TLS 1,0, nous vous recommandons de terminer d’abord l’installation d’bord, puis de procéder à la désactivation de TLS 1,0.</span><span class="sxs-lookup"><span data-stu-id="b808c-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="b808c-176">Appareils tiers</span><span class="sxs-lookup"><span data-stu-id="b808c-176">Third-party devices</span></span>

<span data-ttu-id="b808c-177">Sur les appareils tiers tels que les téléphones 3PIP, les conférences vidéo, les proxys inversés et les équilibreurs de charge, assurez-vous de valider la prise en charge de TLS 1,2, de tester soigneusement et de contacter le fabricant si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="b808c-177">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="b808c-178">Considérations relatives à la Fédération lors de la désactivation de TLS 1.0/1.1 sur les serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="b808c-178">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="b808c-179">Vous devez soigneusement planifier et réfléchir à l’impact de la désactivation de TLS 1.0/1.1 sur votre serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="b808c-179">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="b808c-180">Après la désactivation de TLS 1,0 et 1,1, il est possible que d’autres organisations ne soient plus en mesure de fédérer avec votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b808c-180">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="b808c-181">Vous pouvez opter pour la conservation de TLS 1.0/1.1 sur votre serveur Edge pour assurer la compatibilité descendante avec les systèmes externes non corrigés (marketing 2015, Lync 2013) ou les systèmes externes plus anciens (2010).</span><span class="sxs-lookup"><span data-stu-id="b808c-181">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="b808c-182">Microsoft ne peut pas vous fournir des conseils ou des recommandations concernant l’utilisation de votre réseau Edge (ou de tout autre réseau) en standard PCI ; Ce doit être déterminé par la société en particulier.</span><span class="sxs-lookup"><span data-stu-id="b808c-182">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="b808c-183">Skype entreprise Online est désormais compatible avec le protocole TLS 1,2, donc aucun impact sur l’hybride/la Fédération avec en ligne n’est attendu.</span><span class="sxs-lookup"><span data-stu-id="b808c-183">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="b808c-184">La connectivité PIC (Public IM Connectivity) au service grand public Skype : nous ne attendons pas la désactivation de TLS 1.0/1.1 pour influer sur la [connectivité Skype](../../deploy/deploy-skype-connectivity.md). Les passerelles Microsoft PIC sont déjà compatibles avec TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="b808c-184">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="b808c-185">Conditions préalables et processus</span><span class="sxs-lookup"><span data-stu-id="b808c-185">Prerequisites and process</span></span>

<span data-ttu-id="b808c-186">À l’exception des cas indiqués ci-dessus, une fois que TLS 1,0 et 1,1 ont été désactivés, les clients et les appareils fonctionneront plus correctement ou du tout.</span><span class="sxs-lookup"><span data-stu-id="b808c-186">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="b808c-187">Cela signifie que vous devez patienter avant de mettre à jour les instructions de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b808c-187">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="b808c-188">Lorsque vous avez terminé de répondre à toutes les exigences et que vous avez un plan de résolution des problèmes, continuez.</span><span class="sxs-lookup"><span data-stu-id="b808c-188">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="b808c-189">À un niveau élevé, alors que Skype entreprise Server 2019 est prêt pour la procédure d’installation, Skype entreprise Server 2015 nécessite l’installation d’CU9, l’application des mises à jour requises pour .NET et SQL, le déploiement de clés de Registre prérequises et enfin d’un autre arrondi des mises à jour de configuration du système d’exploitation (par exemple, la désactivation de TLS 1,0 et 1,1 par importation de fichier de registre).</span><span class="sxs-lookup"><span data-stu-id="b808c-189">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="b808c-190">Il est essentiel de procéder à l’installation de tous les éléments requis, y compris Skype entreprise Server 2015 CU6 HF2, avant de désactiver TLS 1,0 et 1,1 sur n’importe quel serveur de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="b808c-190">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="b808c-191">Tout Skype entreprise Server, y compris les rôles Edge et SQL end, nécessite les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="b808c-191">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="b808c-192">Assurez-vous également que tous les clients pris en charge (dans l’étendue) ont été mis à jour avec les versions minimales requises.</span><span class="sxs-lookup"><span data-stu-id="b808c-192">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="b808c-193">N’oubliez pas non plus de mettre à jour les stations de travail de gestion.</span><span class="sxs-lookup"><span data-stu-id="b808c-193">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="b808c-194">Nous voulons suivre l’ordre habituel des opérations « à l’intérieur » pour la mise à niveau de vos serveurs Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="b808c-194">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="b808c-195">Traitez les pools de réalisateurs, les discussions permanentes et les pools couplés de la même manière que dans le sens normal.</span><span class="sxs-lookup"><span data-stu-id="b808c-195">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="b808c-196">L’ordre et les méthodes de mise à niveau sont abordés [ici](topology.md) et [ici](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="b808c-196">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="b808c-197">Processus de haut niveau</span><span class="sxs-lookup"><span data-stu-id="b808c-197">High-level process</span></span>

1. <span data-ttu-id="b808c-198">Testez toutes les étapes de votre laboratoire avant de configurer des serveurs de production.</span><span class="sxs-lookup"><span data-stu-id="b808c-198">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="b808c-199">Sauvegardez et conservez une copie du Registre exporté sur chaque serveur individuel à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="b808c-199">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="b808c-200">Vous ne pouvez pas partager des registres entre serveurs ; ils contiennent des clés basées sur un ordinateur uniques.</span><span class="sxs-lookup"><span data-stu-id="b808c-200">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="b808c-201">Effectuez la mise à niveau de vos serveurs Skype entreprise 2015 vers CU9 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="b808c-201">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="b808c-202">Pour Skype entreprise Server 2019, effectuez la mise à niveau vers CU1 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="b808c-202">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="b808c-203">Installez toutes les conditions préalables pour tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="b808c-203">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="b808c-204">Déployez les clés de Registre prérequises.</span><span class="sxs-lookup"><span data-stu-id="b808c-204">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="b808c-205">Assurez-vous que tous les clients dans l’étendue sont mis à jour.</span><span class="sxs-lookup"><span data-stu-id="b808c-205">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="b808c-206">Désactivez TLS 1,0 et 1,1 par le biais de l’importation du Registre.</span><span class="sxs-lookup"><span data-stu-id="b808c-206">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="b808c-207">Vérifiez que les charges de travail fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="b808c-207">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="b808c-208">Si des problèmes sont détectés, résoudre des problèmes et résoudre ou</span><span class="sxs-lookup"><span data-stu-id="b808c-208">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="b808c-209">Restaurez le registre à partir de l’étape 2 pour réactiver TLS 1,0 et 1,1</span><span class="sxs-lookup"><span data-stu-id="b808c-209">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="b808c-210">Vérifiez que seule la 1,2 TLS est utilisée.</span><span class="sxs-lookup"><span data-stu-id="b808c-210">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="b808c-211">Installer les éléments requis sur tous les serveurs</span><span class="sxs-lookup"><span data-stu-id="b808c-211">Install prerequisites to all servers</span></span>

<span data-ttu-id="b808c-212">Il est nécessaire de mettre à jour les dépendances complètes avant de désactiver TLS 1,0 et 1,1 au niveau du système d’exploitation dans vos déploiements Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b808c-212">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="b808c-213">Voici les versions minimales qui peuvent prendre en charge TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="b808c-213">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="b808c-214">Déployez toutes les mises à jour prérequises pour chaque serveur Skype entreprise dans votre environnement avant de commencer à désactiver TLS 1,0 et 1,1.</span><span class="sxs-lookup"><span data-stu-id="b808c-214">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="b808c-215">Skype entreprise Server 2015 CU9 6.0.9319.548 (2019) ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="b808c-215">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="b808c-216">[.NET Framework 4,7](https://www.microsoft.com/download/details.aspx?id=55167) ou version ultérieure avec SchUseStrongCrypto activé dans le registre (fourni ci-dessous)</span><span class="sxs-lookup"><span data-stu-id="b808c-216">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="b808c-217">SQL doit être mis à jour sur tous les serveurs et les serveurs Skype entreprise 2015.</span><span class="sxs-lookup"><span data-stu-id="b808c-217">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="b808c-218">Mettez à jour les mises à jour du pool Enterprise Edition en premier, puis leurs FEs respectives.</span><span class="sxs-lookup"><span data-stu-id="b808c-218">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="b808c-219">SQL Server 2014 SP1 + CU5 ([lien](https://support.microsoft.com/help/3130926)) ou version ultérieure/sql Server 2012 SP2 + CU16 ou version ultérieure/sql Server 2014 RTM + CU12 ([lien](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)) ou version ultérieure/SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="b808c-219">SQL Server 2014 SP1 + CU5 ([link](https://support.microsoft.com/help/3130926)), or higher / SQL Server 2012 SP2 + CU16 or higher/ SQL Server 2014 RTM + CU12 ([link](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)) or higher / SQL Server 2014 SP2</span></span>
     - <span data-ttu-id="b808c-220">Client natif SQL Server pour SQL Server 2012 ([lien](https://www.microsoft.com/download/details.aspx?id=50402))</span><span class="sxs-lookup"><span data-stu-id="b808c-220">SQL Server Native Client for SQL Server 2012 ([link](https://www.microsoft.com/download/details.aspx?id=50402))</span></span>
     - <span data-ttu-id="b808c-221">Pilote ODBC Microsoft 11 pour SQL Server ([lien](https://www.microsoft.com/download/details.aspx?id=36434)) ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="b808c-221">Microsoft ODBC Driver 11 for SQL Server ([link](https://www.microsoft.com/download/details.aspx?id=36434)), or higher</span></span>
     - <span data-ttu-id="b808c-222">Objets de gestion partagés pour SQL Server 2014 SP2 ([lien](https://www.microsoft.com/download/details.aspx?id=42295))</span><span class="sxs-lookup"><span data-stu-id="b808c-222">Shared Management Objects for SQL Server 2014 SP2 ([link](https://www.microsoft.com/download/details.aspx?id=42295))</span></span>
     - <span data-ttu-id="b808c-223">SQLSysClrTypes pour SQL Server 2014 SP2 ([lien](https://www.microsoft.com/download/details.aspx?id=42295))</span><span class="sxs-lookup"><span data-stu-id="b808c-223">SQLSysClrTypes for SQL server 2014 SP2 ([link](https://www.microsoft.com/download/details.aspx?id=42295))</span></span>

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="b808c-224">Étapes de base pour l’installation des conditions préalables, dans l’ordre des opérations recommandées</span><span class="sxs-lookup"><span data-stu-id="b808c-224">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="b808c-225">Installez la mise à jour de Skype entreprise Server CU9 sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="b808c-225">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="b808c-226">Installez la mise à jour des composants à l’aide du programme de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="b808c-226">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="b808c-227">Mettez à jour les bases de données en fonction de procédures détaillées.</span><span class="sxs-lookup"><span data-stu-id="b808c-227">Update databases according to documented procedures.</span></span> <span data-ttu-id="b808c-228">Pour Skype entreprise Server 2015, voir KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="b808c-228">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="b808c-229">Validez les fonctionnalités de produit du déploiement avant de continuer avec d’autres modifications.</span><span class="sxs-lookup"><span data-stu-id="b808c-229">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="b808c-230">Télécharger le programme d’installation hors connexion de .NET 4,7.</span><span class="sxs-lookup"><span data-stu-id="b808c-230">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="b808c-231">Référence[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="b808c-231">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="b808c-232">Vérifiez que les services 2015 de Skype entreprise Server sont arrêtés sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="b808c-232">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="b808c-233">Référence[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="b808c-233">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="b808c-234">Ex (édition standard) :```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="b808c-234">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="b808c-235">Ex (édition entreprise) :```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="b808c-235">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="b808c-236">Exécutez le package d’installation.</span><span class="sxs-lookup"><span data-stu-id="b808c-236">Run the installer package.</span></span>
    7. <span data-ttu-id="b808c-237">Redémarrez le serveur.</span><span class="sxs-lookup"><span data-stu-id="b808c-237">Reboot the server.</span></span>
3. <span data-ttu-id="b808c-238">Mettez à jour SQL Express 2014 sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="b808c-238">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="b808c-239">Référence[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="b808c-239">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="b808c-240">Télécharger SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="b808c-240">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="b808c-241">Référence[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="b808c-241">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="b808c-242">Copiez le contenu multimédia d’installation dans un dossier sur le serveur (par exemple : C:\ 01_2014SqlSp2).</span><span class="sxs-lookup"><span data-stu-id="b808c-242">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="b808c-243">Vérifiez que les services 2015 de Skype entreprise Server sont arrêtés sur le serveur frontal</span><span class="sxs-lookup"><span data-stu-id="b808c-243">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="b808c-244">Ex (édition standard) :```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="b808c-244">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="b808c-245">Ex (édition entreprise) :```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="b808c-245">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="b808c-246">Ouvrez une invite de commandes d’administration et mettez à niveau tous les composants et instances installés</span><span class="sxs-lookup"><span data-stu-id="b808c-246">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="b808c-247">Exemple : C:\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/QS/IAcceptSQLServerLicenseTerms/action = patch/AllInstances</span><span class="sxs-lookup"><span data-stu-id="b808c-247">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="b808c-248">Mettez à jour le client natif SQL.</span><span class="sxs-lookup"><span data-stu-id="b808c-248">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="b808c-249">Référence : [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="b808c-249">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="b808c-250">Télécharger à partir de[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="b808c-250">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="b808c-251">Vérifiez que les services 2015 de Skype entreprise Server sont arrêtés sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="b808c-251">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="b808c-252">Ex (édition standard) :```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="b808c-252">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="b808c-253">Ex (édition entreprise) :```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="b808c-253">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="b808c-254">Empêcher l’exécution des instances SQL installées</span><span class="sxs-lookup"><span data-stu-id="b808c-254">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="b808c-255">Par exemple```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="b808c-255">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="b808c-256">Par exemple```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="b808c-256">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="b808c-257">Par exemple (édition standard uniquement) :```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="b808c-257">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="b808c-258">Installez la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="b808c-258">Install the update.</span></span>
5. <span data-ttu-id="b808c-259">Mettez à jour le pilote ODBC 11 pour SQL Server pour inclure la prise en charge de TLS 1,2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span><span class="sxs-lookup"><span data-stu-id="b808c-259">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="b808c-260">Télécharger [le pilote ODBC 11 pour SQL Server-Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span><span class="sxs-lookup"><span data-stu-id="b808c-260">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="b808c-261">Vérifiez que les services 2015 de Skype entreprise Server sont arrêtés sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="b808c-261">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="b808c-262">Exemple (édition standard) :```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="b808c-262">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="b808c-263">Exemple (édition entreprise) :```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="b808c-263">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="b808c-264">Installez la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="b808c-264">Install the update.</span></span>
6. <span data-ttu-id="b808c-265">Déployez les clés de Registre prérequises.</span><span class="sxs-lookup"><span data-stu-id="b808c-265">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="b808c-266">Clés de Registre préalables</span><span class="sxs-lookup"><span data-stu-id="b808c-266">Pre-requisite registry keys</span></span>

<span data-ttu-id="b808c-267">Copiez/collez le test suivant dans le bloc-notes, puis renommez TLSPreReq. reg ou un nom de votre choix, puis importez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="b808c-267">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="b808c-268">Pour les terminaisons SQL pour les pools d’éditions Enterprise Edition, les prérequis et la désactivation de la TLS doivent être considérés comme des mises à jour de SQL ou du système d’exploitation. reportez-vous à :[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="b808c-268">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="b808c-269">Tant que l’application requise et les étapes de désactivation de la fonction de mise en réseau TLS peuvent être combinées, nous vous recommandons vivement d’appliquer tous les éléments requis avant de procéder à la désactivation de TLS 1,0 et 1,1 au niveau du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="b808c-269">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="b808c-270">La meilleure pratique consiste à préparer l’environnement en déployant toutes les conditions préalables, en validant celle-ci de façon correcte et comme prévu, puis en poursuivant la désactivation de TLS 1.0/1.1 ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="b808c-270">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="b808c-271">Désactiver TLS 1,0 et 1,1 par le biais de l’importation du Registre</span><span class="sxs-lookup"><span data-stu-id="b808c-271">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="b808c-272">Avant de passer aux étapes suivantes, assurez- *vous d’avoir rempli toutes les conditions préalables et mis à jour les serveurs Skype entreprise*.</span><span class="sxs-lookup"><span data-stu-id="b808c-272">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="b808c-273">Copiez le texte suivant dans un fichier bloc-notes, puis renommez-le **TLSDisable. reg**:</span><span class="sxs-lookup"><span data-stu-id="b808c-273">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="b808c-274">Importez le fichier. reg sur chaque serveur pour lequel vous souhaitez désactiver TLS 1,0 et 1,1.</span><span class="sxs-lookup"><span data-stu-id="b808c-274">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="b808c-275">Redémarrez le serveur.</span><span class="sxs-lookup"><span data-stu-id="b808c-275">Reboot the server.</span></span> <span data-ttu-id="b808c-276">Une fois les services reconnectés, accédez au serveur suivant.</span><span class="sxs-lookup"><span data-stu-id="b808c-276">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="b808c-277">Dans le cas d’une mise à jour du système d’exploitation, l’approche pour les pools Enterprise Edition est identique.</span><span class="sxs-lookup"><span data-stu-id="b808c-277">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="b808c-278">Il est possible que vous ayez remarqué que nous ne puissions pas simplement désactiver TLS 1,0 et 1,1.</span><span class="sxs-lookup"><span data-stu-id="b808c-278">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="b808c-279">Nous prenons en charge la réorganisation de la suite de chiffrement (comme illustré ci-dessus) et la désactivation de certains chiffrements faibles plus anciens.</span><span class="sxs-lookup"><span data-stu-id="b808c-279">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="b808c-280">C’est la première fois que nous avons officiellement pris en charge ces modifications apportées à l’API SCHANNEL et crypto sur Skype entreprise Server, et il est important de noter que ces modifications sont les seules prises en charge et testées pour le moment.</span><span class="sxs-lookup"><span data-stu-id="b808c-280">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="b808c-281">Il est possible que nous puissions envisager des configurations supplémentaires à l’avenir, mais pour l’instant, ne modifiez pas le fichier d’importation du Registre dans votre implémentation.</span><span class="sxs-lookup"><span data-stu-id="b808c-281">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="b808c-282">Valider le fonctionnement normal des charges de travail</span><span class="sxs-lookup"><span data-stu-id="b808c-282">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="b808c-283">Une fois que les protocoles TLS 1,0 et 1,1 ont été désactivés dans votre environnement, assurez-vous que toutes les charges de travail principales fonctionnent comme prévu, comme la messagerie instantanée & la présence, les appels P2P, l’entreprise voix, etc.</span><span class="sxs-lookup"><span data-stu-id="b808c-283">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="b808c-284">**Valider uniquement le 1,2 TLS est utilisé**</span><span class="sxs-lookup"><span data-stu-id="b808c-284">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="b808c-285">Faire en sorte que votre équipe de sécurité effectue un nouvel audit du trafic Skype entreprise pour s’assurer que les anciens protocoles TLS 1,0 et 1,1 ne sont plus utilisés.</span><span class="sxs-lookup"><span data-stu-id="b808c-285">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="b808c-286">Par ailleurs, vous pouvez utiliser Internet Explorer pour tester les connexions TLS aux services Web à partir de Skype entreprise Server 2015 après la désactivation de TLS 1,0 et de TLS 1,1.</span><span class="sxs-lookup"><span data-stu-id="b808c-286">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="b808c-287">Lancez Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b808c-287">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="b808c-288">Sélectionnez **Outils** > **Options Internet**.</span><span class="sxs-lookup"><span data-stu-id="b808c-288">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="b808c-289">Sélectionnez l’onglet **avancé** .</span><span class="sxs-lookup"><span data-stu-id="b808c-289">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="b808c-290">Sous **paramètres**, faites défiler vers le bas.</span><span class="sxs-lookup"><span data-stu-id="b808c-290">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="b808c-291">Vérifiez que les protocoles TLS 1,0, TLS 1,1 et TLS 1,2 sont activés.</span><span class="sxs-lookup"><span data-stu-id="b808c-291">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="b808c-292">Parcourez l’URL du service Web interne de votre marketing 2015 (connexion réussie).</span><span class="sxs-lookup"><span data-stu-id="b808c-292">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="b808c-293">Revenez dans Internet Explorer et désactivez l’option d' **utilisation de TLS 1,2** uniquement.</span><span class="sxs-lookup"><span data-stu-id="b808c-293">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="b808c-294">Parcourez de nouveau l’URL du service Web interne de votre marketing 2015 (il est impossible de se connecter).</span><span class="sxs-lookup"><span data-stu-id="b808c-294">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Options Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="b808c-296">Scénarios de déploiement avancés</span><span class="sxs-lookup"><span data-stu-id="b808c-296">Advanced deployment scenarios</span></span>

<span data-ttu-id="b808c-297">Dans la mesure où certains éléments requis de dépendance sont requis pour la prise en charge de TLS 1,2 dans Skype entreprise ser 2015, l’installation à partir du support RTM peut échouer sur tout système sur lequel TLS 1,0 et 1,1 a été désactivé.</span><span class="sxs-lookup"><span data-stu-id="b808c-297">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="b808c-298">**Le déploiement de nouveaux serveurs Standard Edition Server ou de pools Enterprise Edition après la désactivation de TLS 1,0 et 1,1 dans votre environnement.**</span><span class="sxs-lookup"><span data-stu-id="b808c-298">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="b808c-299">**Option 1 :** Utilisez [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="b808c-299">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="b808c-300">Notez que nous mettons à jour SmartSetup pour prendre en charge les fichiers binaires SQL mis à jour dans une mise en cuivre future, et vous mettrez à jour cet article ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="b808c-300">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="b808c-301">**Option 2 :** Pré-installation des instances SQL locales (RTCLOCAL et LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="b808c-301">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="b808c-302">Téléchargez et copiez SQL Express 2014 SP2 (SQLEXPR_x64. exe) dans le dossier local sur FE.</span><span class="sxs-lookup"><span data-stu-id="b808c-302">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="b808c-303">Par exemple, le chemin d’accès du dossier <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="b808c-303">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="b808c-304">Lancer PowerShell ou invite de commandes et accéder à <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="b808c-304">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="b808c-305">Créez l’instance SQL RTCLOCAL en exécutant la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="b808c-305">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="b808c-306">Attendez la fin de SQLEXPR_x64. exe avant de procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="b808c-306">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="b808c-307">SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = installation/FEATURES = SQLEngine, Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "AUTORITE AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "automatique"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = automati</span><span class="sxs-lookup"><span data-stu-id="b808c-307">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="b808c-308">Créez l’instance SQL LYNCLOCAL en exécutant la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="b808c-308">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="b808c-309">Attendez la fin de SQLEXPR_x64. exe avant de passer à l’étape suivante :</span><span class="sxs-lookup"><span data-stu-id="b808c-309">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="b808c-310">SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = installer/FEATURES = SQLEngine, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "AUTORITE AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "automatique"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = automatique</span><span class="sxs-lookup"><span data-stu-id="b808c-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="b808c-311">Exécutez le programme d’installation de Skype entreprise Server 2015 RTM.</span><span class="sxs-lookup"><span data-stu-id="b808c-311">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="b808c-312">Suivez les étapes restantes décrites ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="b808c-312">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="b808c-313">**Option 3 :** Vous pouvez également remplacer manuellement des fichiers binaires dans un répertoire d’installation local en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="b808c-313">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="b808c-314">Installer la configuration requise pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b808c-314">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="b808c-315">Installez .NET 4,7 :</span><span class="sxs-lookup"><span data-stu-id="b808c-315">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="b808c-316">**Remarque :** Nous venons d’abord prendre en charge .NET 4,7 dans Skype entreprise Server 2015 CU5 (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="b808c-316">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="b808c-317">Par conséquent, dans les étapes suivantes, nous allons mettre à jour les principaux composants avant l’installation principale.</span><span class="sxs-lookup"><span data-stu-id="b808c-317">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="b808c-318">Télécharger : https://www.microsoft.com/download/details.aspx?id=55167.</span><span class="sxs-lookup"><span data-stu-id="b808c-318">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="b808c-319">Référence : [logiciels qui doivent être installés avant le déploiement de Skype entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="b808c-319">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="b808c-320">Copiez les fichiers ISO/dossiers :</span><span class="sxs-lookup"><span data-stu-id="b808c-320">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="b808c-321">Lorsque le fichier ISO 2015 de Skype entreprise Server est connecté, ouvrez le répertoire racine du lecteur qui lui est associé (par exemple :\) D : dans l’Explorateur de fichiers.</span><span class="sxs-lookup"><span data-stu-id="b808c-321">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="b808c-322">Copiez tous les dossiers et fichiers dans un dossier sur un disque local (par exemple : C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="b808c-322">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="b808c-323">**Remarque :** Avant l’installation des composants, certains fichiers devront être mis à jour pour prendre en charge le protocole TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="b808c-323">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="b808c-324">Remplacez les packages MSI/EXE :</span><span class="sxs-lookup"><span data-stu-id="b808c-324">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="b808c-325">Remplacez les packages MSI et EXE existants dans le dossier/Setup/amd64/du support d’installation sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="b808c-325">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="b808c-326">SQL 2014 SP2 Express :https://www.microsoft.com/en-us/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="b808c-326">SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="b808c-327">Renommez le fichier SQLEXPR_x64 sur l’ordinateur local, puis remplacez le fichier existant dans le dossier Setup/amd64/du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="b808c-327">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="b808c-328">Client natif SQL :https://www.microsoft.com/en-us/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="b808c-328">SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="b808c-329">**Remarque :** Renommez-le si nécessaire pour sqlncli. msi, puis remplacez le fichier existant qui existe dans le dossier Setup/amd64/du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="b808c-329">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="b808c-330">Objets de gestion SQL :https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="b808c-330">SQL Management Objects: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="b808c-331">**Remarque :** Le Feature Pack dispose de nombreux éléments qui peuvent être téléchargés.</span><span class="sxs-lookup"><span data-stu-id="b808c-331">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="b808c-332">Sélectionnez pour télécharger SharedManagementObjects. msi uniquement.</span><span class="sxs-lookup"><span data-stu-id="b808c-332">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="b808c-333">**Remarque :** Remplacez le fichier existant qui existe dans le dossier Setup/amd64/du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="b808c-333">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="b808c-334">Types CLR SQL :https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="b808c-334">SQL CLR Types: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="b808c-335">**Remarque :** Le Feature Pack dispose de nombreux éléments qui peuvent être téléchargés.</span><span class="sxs-lookup"><span data-stu-id="b808c-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="b808c-336">Sélectionnez pour télécharger CQLSysClrTypes. msi uniquement</span><span class="sxs-lookup"><span data-stu-id="b808c-336">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="b808c-337">**Remarque**: remplacez le fichier existant qui existe dans le dossier Setup/amd64/du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="b808c-337">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="b808c-338">Installer les composants principaux :</span><span class="sxs-lookup"><span data-stu-id="b808c-338">Install Core Components:</span></span> 
    - <span data-ttu-id="b808c-339">Exécutez setup. exe à partir du dossier Setup/amd64/du support d’installation.</span><span class="sxs-lookup"><span data-stu-id="b808c-339">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="b808c-340">Suivez les instructions pour installer les composants principaux</span><span class="sxs-lookup"><span data-stu-id="b808c-340">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="b808c-341">Fermez les composants principaux.</span><span class="sxs-lookup"><span data-stu-id="b808c-341">Close Core Components.</span></span>
6. <span data-ttu-id="b808c-342">Mettre à jour les composants principaux :</span><span class="sxs-lookup"><span data-stu-id="b808c-342">Update Core Components:</span></span> 
    - <span data-ttu-id="b808c-343">Téléchargez le programme d’installation de la mise à jour de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="b808c-343">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="b808c-344">Exécutez le programme d’installation pour mettre à jour les composants principaux et installer les compteurs de performance.</span><span class="sxs-lookup"><span data-stu-id="b808c-344">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="b808c-345">**Remarque :** Depuis la publication de CU6HF2, la fonctionnalité de mise à jour automatique ne peut être installée que sur CU6.</span><span class="sxs-lookup"><span data-stu-id="b808c-345">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="b808c-346">Par conséquent, l’outil de mise à jour doit être exécuté séparément pour mettre à jour les composants principaux sur 6.0.9319.516.</span><span class="sxs-lookup"><span data-stu-id="b808c-346">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="b808c-347">Référencehttps://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="b808c-347">Reference: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="b808c-348">Installer les outils d’administration (facultatif) :</span><span class="sxs-lookup"><span data-stu-id="b808c-348">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="b808c-349">Cette opération permet d’installer le client natif Microsoft SQL Server 2012, les objets de gestion SQL Server 2014 (x64) et les types CLR du système Microsoft pour SQL Server 2014 (x64) à l’aide des fichiers mis à jour.</span><span class="sxs-lookup"><span data-stu-id="b808c-349">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="b808c-350">Par ailleurs, le générateur de topologie 2015 de Skype entreprise Server et le panneau de configuration seront disponibles sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="b808c-350">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="b808c-351">Installez le magasin de configurations local (étape 1) :</span><span class="sxs-lookup"><span data-stu-id="b808c-351">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="b808c-352">Ouvrez l’Assistant Déploiement, cliquez sur installer ou mettre à jour le système Skype entreprise Server, puis cliquez sur **exécuter** à l’étape 1 : installer le magasin de configuration local.</span><span class="sxs-lookup"><span data-stu-id="b808c-352">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="b808c-353">Cliquez sur **suivant** dans la boîte de dialogue **installer le magasin de configuration local** .</span><span class="sxs-lookup"><span data-stu-id="b808c-353">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="b808c-354">![Boîte de dialogue installer le magasin de configuration local](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="b808c-354">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="b808c-355">Passez en revue les résultats et assurez-vous que l’état de la tâche est terminé.</span><span class="sxs-lookup"><span data-stu-id="b808c-355">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="b808c-356">Examinez le fichier journal obtenu en cliquant sur **afficher le journal**.</span><span class="sxs-lookup"><span data-stu-id="b808c-356">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="b808c-357">![L’état de la tâche est terminé](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="b808c-357">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="b808c-358">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="b808c-358">Click **Finish**.</span></span>
9. <span data-ttu-id="b808c-359">Configurer ou supprimer des composants de Skype entreprise Server (étape 2) :</span><span class="sxs-lookup"><span data-stu-id="b808c-359">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="b808c-360">Ouvrez l’Assistant Déploiement, cliquez sur **installer ou mettre à jour le système Skype entreprise Server**, puis cliquez sur **exécuter** à l’étape 2 : configurer ou supprimer des composants Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b808c-360">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="b808c-361">Cliquez sur **suivant** dans la boîte de dialogue Configurer les composants serveur Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="b808c-361">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="b808c-362">![fenêtre Configurer les composants de Skype entreprise Server](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="b808c-362">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="b808c-363">Examinez le journal à l’aide de l’affichage du journal et confirmez que le programme d’installation s’est terminé sans problème.</span><span class="sxs-lookup"><span data-stu-id="b808c-363">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="b808c-364">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="b808c-364">Click **Finish**.</span></span>
10. <span data-ttu-id="b808c-365">Poursuivez l’installation et la configuration supplémentaires requises (vous pouvez reprendre les procédures d’installation normales à ce stade).</span><span class="sxs-lookup"><span data-stu-id="b808c-365">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
