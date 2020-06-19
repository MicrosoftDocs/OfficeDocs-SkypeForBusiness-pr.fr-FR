---
title: Étude de cas de voix contoso teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Étude de cas de voix dans teams pour les entreprises à plusieurs nationaux
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786026"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="c3b32-103">Étude de cas contoso : système téléphonique</span><span class="sxs-lookup"><span data-stu-id="c3b32-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="c3b32-104">En fonction de l’emplacement géographique et d’autres facteurs, contoso avait des bureaux utilisant les solutions de téléphonie suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3b32-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="c3b32-105">Type de site A : voix Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="c3b32-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="c3b32-106">Type de site B : systèmes de téléphonie traditionnels traditionnels</span><span class="sxs-lookup"><span data-stu-id="c3b32-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="c3b32-107">Type de site C : combinaison de Skype entreprise voix et de systèmes de téléphonie traditionnels.</span><span class="sxs-lookup"><span data-stu-id="c3b32-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="c3b32-108">Pour implémenter une solution du système Microsoft Phone pour l’ensemble de votre organisation, contoso devait déterminer &mdash; pour chaque type &mdash; de site les options suivantes qui seraient utilisées avec le système téléphonique pour se connecter au réseau téléphonique public commuté (RTC) :</span><span class="sxs-lookup"><span data-stu-id="c3b32-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="c3b32-109">Système téléphonique avec un plan d’appels</span><span class="sxs-lookup"><span data-stu-id="c3b32-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="c3b32-110">Système téléphonique avec son propre opérateur PSTN via le routage direct</span><span class="sxs-lookup"><span data-stu-id="c3b32-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="c3b32-111">Système téléphonique avec un plan d’appels et un système téléphonique avec son propre opérateur PSTN via le routage direct</span><span class="sxs-lookup"><span data-stu-id="c3b32-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="c3b32-112">Pour déterminer la solution adaptée à son organisation, Contoso a utilisé les [solutions de téléphonie de Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) et les appels de session 2019 [dans Microsoft teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="c3b32-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="c3b32-113">Type de site A : voix Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="c3b32-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="c3b32-114">Contoso Skype entreprise voix entreprise a été configuré comme Hub et spoke.</span><span class="sxs-lookup"><span data-stu-id="c3b32-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="c3b32-115">Il s’agissait d’un emplacement central qui gérait la passerelle RTC dans la région qui avait fourni la connexion au RTC pour les utilisateurs de voix Skype entreprise dans le pays.</span><span class="sxs-lookup"><span data-stu-id="c3b32-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="c3b32-116">Souvent, ces bureaux ne disposant pas d’une sortie Internet.</span><span class="sxs-lookup"><span data-stu-id="c3b32-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="c3b32-117">Les numéros de ces utilisateurs qui se trouvent sur le Trunk SIP connecté à un SBC existant.</span><span class="sxs-lookup"><span data-stu-id="c3b32-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="c3b32-118">Pour déterminer si le SBC déjà déployé est certifié pour le routage direct et le contournement du média, Contoso a vérifié la [liste des contrôleurs de bordure de session certifiés pour le routage direct](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="c3b32-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="c3b32-119">Les habitudes de numérotation de l’utilisateur ont été de composer un utilisateur sur le système de téléphonie hérité en utilisant une extension, même si un client Skype entreprise est disponible pour le son d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="c3b32-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="c3b32-120">Contoso a émis ses décisions sur les questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3b32-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="c3b32-121">F.</span><span class="sxs-lookup"><span data-stu-id="c3b32-121">Q.</span></span> <span data-ttu-id="c3b32-122">Avons-nous besoin de conserver les fonctionnalités fournies par notre déploiement local ?</span><span class="sxs-lookup"><span data-stu-id="c3b32-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="c3b32-123">Un.</span><span class="sxs-lookup"><span data-stu-id="c3b32-123">A.</span></span> <span data-ttu-id="c3b32-124">Non</span><span class="sxs-lookup"><span data-stu-id="c3b32-124">No</span></span> 

- <span data-ttu-id="c3b32-125">F.</span><span class="sxs-lookup"><span data-stu-id="c3b32-125">Q.</span></span> <span data-ttu-id="c3b32-126">Avons-nous besoin d’interopérer avec des systèmes PBX tiers et d’autres équipements de téléphonie ?</span><span class="sxs-lookup"><span data-stu-id="c3b32-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="c3b32-127">Un.</span><span class="sxs-lookup"><span data-stu-id="c3b32-127">A.</span></span> <span data-ttu-id="c3b32-128">Non</span><span class="sxs-lookup"><span data-stu-id="c3b32-128">No</span></span> 

- <span data-ttu-id="c3b32-129">F.</span><span class="sxs-lookup"><span data-stu-id="c3b32-129">Q.</span></span> <span data-ttu-id="c3b32-130">Ai-je besoin de conserver notre opérateur tiers actuel ?</span><span class="sxs-lookup"><span data-stu-id="c3b32-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="c3b32-131">A. Oui (pays réglementés) et non</span><span class="sxs-lookup"><span data-stu-id="c3b32-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="c3b32-132">F.</span><span class="sxs-lookup"><span data-stu-id="c3b32-132">Q.</span></span> <span data-ttu-id="c3b32-133">Avons-nous besoin d’obtenir le ROI d’un déploiement SBCs ?</span><span class="sxs-lookup"><span data-stu-id="c3b32-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="c3b32-134">A. Oui et non</span><span class="sxs-lookup"><span data-stu-id="c3b32-134">A. Yes and No</span></span>  

- <span data-ttu-id="c3b32-135">F.</span><span class="sxs-lookup"><span data-stu-id="c3b32-135">Q.</span></span> <span data-ttu-id="c3b32-136">Est-ce que les forfaits d’appels RTC Microsoft sont disponibles dans cette région ?</span><span class="sxs-lookup"><span data-stu-id="c3b32-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="c3b32-137">A. Oui et non</span><span class="sxs-lookup"><span data-stu-id="c3b32-137">A. Yes and No</span></span> 

<span data-ttu-id="c3b32-138">En fonction des réponses à leurs questions, Contoso a décidé d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3b32-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="c3b32-139">Déplacer les utilisateurs qui se trouvent dans une région où les plans d’appel RTC sont disponibles pour le système téléphonique avec des plans d’appels.</span><span class="sxs-lookup"><span data-stu-id="c3b32-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="c3b32-140">Déplacez les utilisateurs qui ne sont pas situés dans une région où les plans d’appel RTC sont disponibles, et les utilisateurs qui se trouvent sur un site pour lesquels le ROI sur l’SBCs doivent avoir été satisfaits, et les utilisateurs résidant dans un pays disposant de réglementations de téléphonie pour le système téléphonique avec le routage direct.</span><span class="sxs-lookup"><span data-stu-id="c3b32-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="c3b32-141">Le diagramme suivant montre le déploiement initial de Skype entreprise et la façon dont ce déploiement a été migré vers les plans d’appel Microsoft et le routage directe :</span><span class="sxs-lookup"><span data-stu-id="c3b32-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![Diagramme affichant les États avant et après](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="c3b32-143">Type de site B : systèmes de téléphonie traditionnels traditionnels</span><span class="sxs-lookup"><span data-stu-id="c3b32-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="c3b32-144">Contoso possédait de nombreux bureaux ayant recours à des systèmes de téléphonie hérités.</span><span class="sxs-lookup"><span data-stu-id="c3b32-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="c3b32-145">Il existait un sous-ensemble d’utilisateurs qui disposaient d’un numéro de téléphone 1.64, tandis que les autres n’avaient qu’une extension.</span><span class="sxs-lookup"><span data-stu-id="c3b32-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="c3b32-146">Ces numéros sont stockés sur le Trunk TDM de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="c3b32-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="c3b32-147">La numérotation intra-site a été configurée en tirant parti d’un code de site devant l’extension afin de déterminer l’emplacement de routage de l’appel.</span><span class="sxs-lookup"><span data-stu-id="c3b32-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="c3b32-148">Les habitudes de numérotation des utilisateurs pouvaient composer le numéro par poste.</span><span class="sxs-lookup"><span data-stu-id="c3b32-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="c3b32-149">Contoso a émis ses décisions sur les questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3b32-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="c3b32-150">F.</span><span class="sxs-lookup"><span data-stu-id="c3b32-150">Q.</span></span> <span data-ttu-id="c3b32-151">Avons-nous besoin de conserver les fonctionnalités fournies par notre déploiement local ?</span><span class="sxs-lookup"><span data-stu-id="c3b32-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="c3b32-152">Un.</span><span class="sxs-lookup"><span data-stu-id="c3b32-152">A.</span></span> <span data-ttu-id="c3b32-153">Non</span><span class="sxs-lookup"><span data-stu-id="c3b32-153">No</span></span> 

- <span data-ttu-id="c3b32-154">F.</span><span class="sxs-lookup"><span data-stu-id="c3b32-154">Q.</span></span> <span data-ttu-id="c3b32-155">Avons-nous besoin d’interopérer avec des systèmes PBX tiers et d’autres équipements de téléphonie ?</span><span class="sxs-lookup"><span data-stu-id="c3b32-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="c3b32-156">A. Oui</span><span class="sxs-lookup"><span data-stu-id="c3b32-156">A. Yes</span></span>

- <span data-ttu-id="c3b32-157">F.</span><span class="sxs-lookup"><span data-stu-id="c3b32-157">Q.</span></span> <span data-ttu-id="c3b32-158">Ai-je besoin de conserver notre opérateur tiers actuel ?</span><span class="sxs-lookup"><span data-stu-id="c3b32-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="c3b32-159">A. non</span><span class="sxs-lookup"><span data-stu-id="c3b32-159">A. No</span></span> 

- <span data-ttu-id="c3b32-160">F.</span><span class="sxs-lookup"><span data-stu-id="c3b32-160">Q.</span></span> <span data-ttu-id="c3b32-161">Est-ce que le plan d’appels de Microsoft RTC est disponible dans notre région ?</span><span class="sxs-lookup"><span data-stu-id="c3b32-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="c3b32-162">A. Oui et non</span><span class="sxs-lookup"><span data-stu-id="c3b32-162">A. Yes and No</span></span> 

<span data-ttu-id="c3b32-163">En fonction des réponses à leurs questions, Contoso a décidé d’effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3b32-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="c3b32-164">Déplacer les utilisateurs qui se trouvent dans une région où les plans d’appel RTC sont disponibles pour le système téléphonique avec des plans d’appels.</span><span class="sxs-lookup"><span data-stu-id="c3b32-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="c3b32-165">Déplacer les utilisateurs qui ne se trouvent pas dans une région où les plans d’appel RTC sont accessibles au système téléphonique avec le routage direct.</span><span class="sxs-lookup"><span data-stu-id="c3b32-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="c3b32-166">Maintenir une connexion RTC aux appareils analogiques cruciaux de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="c3b32-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="c3b32-167">Les schémas suivants montrent le déploiement d’origine du système hérité avec les sites distants et la migration vers un déploiement de routage direct avec l’optimisation de média locale :</span><span class="sxs-lookup"><span data-stu-id="c3b32-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="c3b32-168">**Original legacy deployment**  
 Déploiement ![ d’origine hérité Diagramme affichant les États avant et après](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="c3b32-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="c3b32-169">**Déploiement avec le routage direct**</span><span class="sxs-lookup"><span data-stu-id="c3b32-169">**Deployment with Direct Routing**</span></span>

![Diagramme affichant les États avant et après](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="c3b32-171">Type de site C : combinaison de Skype entreprise voix et de systèmes de téléphonie traditionnels.</span><span class="sxs-lookup"><span data-stu-id="c3b32-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="c3b32-172">Les numéros d’utilisateurs vocaux de contoso entreprise pour les entreprises sont stockés sur le Trunk SIP sur l’SBC à partir du transporteur.</span><span class="sxs-lookup"><span data-stu-id="c3b32-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="c3b32-173">Les numéros des systèmes de téléphonie traditionnels résident sur le Trunk de TDM de la passerelle RTC.</span><span class="sxs-lookup"><span data-stu-id="c3b32-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="c3b32-174">Contoso a émis ses décisions sur les questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3b32-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="c3b32-175">F.</span><span class="sxs-lookup"><span data-stu-id="c3b32-175">Q.</span></span> <span data-ttu-id="c3b32-176">Avons-nous besoin de conserver les fonctionnalités fournies par notre déploiement local ?</span><span class="sxs-lookup"><span data-stu-id="c3b32-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="c3b32-177">Un.</span><span class="sxs-lookup"><span data-stu-id="c3b32-177">A.</span></span> <span data-ttu-id="c3b32-178">Non</span><span class="sxs-lookup"><span data-stu-id="c3b32-178">No</span></span> 

- <span data-ttu-id="c3b32-179">F.</span><span class="sxs-lookup"><span data-stu-id="c3b32-179">Q.</span></span> <span data-ttu-id="c3b32-180">Avons-nous besoin d’interopérer avec des systèmes PBX tiers et d’autres équipements de téléphonie ?</span><span class="sxs-lookup"><span data-stu-id="c3b32-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="c3b32-181">A. non</span><span class="sxs-lookup"><span data-stu-id="c3b32-181">A. No</span></span> 

- <span data-ttu-id="c3b32-182">F.</span><span class="sxs-lookup"><span data-stu-id="c3b32-182">Q.</span></span> <span data-ttu-id="c3b32-183">Ai-je besoin de conserver notre opérateur tiers actuel ?</span><span class="sxs-lookup"><span data-stu-id="c3b32-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="c3b32-184">A. non</span><span class="sxs-lookup"><span data-stu-id="c3b32-184">A. No</span></span> 

- <span data-ttu-id="c3b32-185">F.</span><span class="sxs-lookup"><span data-stu-id="c3b32-185">Q.</span></span> <span data-ttu-id="c3b32-186">Avons-nous besoin d’obtenir le ROI d’un déploiement SBCs ?</span><span class="sxs-lookup"><span data-stu-id="c3b32-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="c3b32-187">A. Oui et non</span><span class="sxs-lookup"><span data-stu-id="c3b32-187">A. Yes and No</span></span>  

- <span data-ttu-id="c3b32-188">F.</span><span class="sxs-lookup"><span data-stu-id="c3b32-188">Q.</span></span> <span data-ttu-id="c3b32-189">Est-ce que le plan d’appels RTC de Microsoft est disponible dans cette région ?</span><span class="sxs-lookup"><span data-stu-id="c3b32-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="c3b32-190">A. non</span><span class="sxs-lookup"><span data-stu-id="c3b32-190">A. No</span></span> 

<span data-ttu-id="c3b32-191">En fonction des réponses à leurs questions, Contoso a déterminé les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="c3b32-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="c3b32-192">Pour les utilisateurs de la téléphonie héritée qui seront activés pour le routage direct, Contoso a porté les numéros de l’Trunk de TDM sur le Trunk SIP pour l’SBC, car l’SBC est certifié pour le routage direct.</span><span class="sxs-lookup"><span data-stu-id="c3b32-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="c3b32-193">Pour permettre la prise en charge d’un sous-ensemble d’utilisateurs déplacés vers un système téléphonique et permettre le routage continu via le système hérité, le système de téléphonie hérité a été configuré comme tronçon suivant de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="c3b32-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="c3b32-194">Par ailleurs, pour encourager le changement de comportement des utilisateurs et supprimer la dépendance à la numérotation entre les extensions intra-et intra-site, Contoso a fourni des recommandations pour l’utilisation de teams pour tous les appels internes.</span><span class="sxs-lookup"><span data-stu-id="c3b32-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="c3b32-195">Les schémas suivants illustrent le déploiement d’origine du système de téléphonie et de la voix de Skype entreprise, et la migration vers un déploiement mixte utilisant le routage direct :</span><span class="sxs-lookup"><span data-stu-id="c3b32-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="c3b32-196">**Original mixed deployment** 
 Déploiement ![ mixte d’origine Diagramme dont l’État est antérieur](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="c3b32-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="c3b32-197">**Déploiement mixte avec le routage direct** 
 ![ Diagramme dont l’État est antérieur](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="c3b32-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="c3b32-198">Forfaits d’appel</span><span class="sxs-lookup"><span data-stu-id="c3b32-198">Calling Plans</span></span>

<span data-ttu-id="c3b32-199">Pour déterminer la configuration requise pour les offres d’appels, Contoso a examiné les [décisions de déploiement principales du plan d’appel](calling-plan-landing-page.md#core-deployment-decisions).</span><span class="sxs-lookup"><span data-stu-id="c3b32-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="c3b32-200">Les décisions qui en résultent ont été prises :</span><span class="sxs-lookup"><span data-stu-id="c3b32-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="c3b32-201">F.</span><span class="sxs-lookup"><span data-stu-id="c3b32-201">Q.</span></span> <span data-ttu-id="c3b32-202">Mes utilisateurs doivent-ils utiliser les appels internationaux ?</span><span class="sxs-lookup"><span data-stu-id="c3b32-202">Do my users need international calling?</span></span><br> <span data-ttu-id="c3b32-203">A. Oui</span><span class="sxs-lookup"><span data-stu-id="c3b32-203">A. Yes</span></span> 

- <span data-ttu-id="c3b32-204">F.</span><span class="sxs-lookup"><span data-stu-id="c3b32-204">Q.</span></span> <span data-ttu-id="c3b32-205">Mes utilisateurs ont-ils chacun un numéro de téléphone à l’intérieur direct ?</span><span class="sxs-lookup"><span data-stu-id="c3b32-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="c3b32-206">A. non aujourd’hui.</span><span class="sxs-lookup"><span data-stu-id="c3b32-206">A. Not today.</span></span> <span data-ttu-id="c3b32-207">Tous les utilisateurs activés reçoivent un message.</span><span class="sxs-lookup"><span data-stu-id="c3b32-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="c3b32-208">F.</span><span class="sxs-lookup"><span data-stu-id="c3b32-208">Q.</span></span> <span data-ttu-id="c3b32-209">Souhaitez-vous masquer ou désactiver l’identification de l’appelant ?</span><span class="sxs-lookup"><span data-stu-id="c3b32-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="c3b32-210">A. l’identification de l’appelant pour un utilisateur est masquée par le numéro local de contoso.</span><span class="sxs-lookup"><span data-stu-id="c3b32-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="c3b32-211">Routage direct</span><span class="sxs-lookup"><span data-stu-id="c3b32-211">Direct Routing</span></span>

<span data-ttu-id="c3b32-212">Contoso a suivi ses appels pour rester à jour sur les fonctionnalités de 365 d’Office, notamment celles disponibles avec le système téléphonique et le routage direct.</span><span class="sxs-lookup"><span data-stu-id="c3b32-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="c3b32-213">Le leadership technique et les architectes ont utilisé les recommandations fournies lors de la 2019 de l’enflamme pour en déterminer la direction.</span><span class="sxs-lookup"><span data-stu-id="c3b32-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="c3b32-214">Sessions principales utilisées :</span><span class="sxs-lookup"><span data-stu-id="c3b32-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="c3b32-215">Planifier le succès du routage direct de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="c3b32-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="c3b32-216">Mises à jour du routage direct</span><span class="sxs-lookup"><span data-stu-id="c3b32-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="c3b32-217">Configuration</span><span class="sxs-lookup"><span data-stu-id="c3b32-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="c3b32-218">Sites d’offres d’appels</span><span class="sxs-lookup"><span data-stu-id="c3b32-218">Calling Plans sites</span></span>

<span data-ttu-id="c3b32-219">Pour obtenir des licences et affecter des numéros de téléphone aux utilisateurs, Contoso a suivi les étapes décrites dans la rubrique [configurer les offres d’appels](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="c3b32-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="c3b32-220">En raison du nombre d’utilisateurs auxquels des numéros de téléphone ont besoin, Contoso a décidé d’utiliser PowerShell pour attribuer les numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="c3b32-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="c3b32-221">Pour plus d’informations sur l’attribution de nombres à l’aide &mdash; de PowerShell, en plus d’autres paramètres, &mdash; Contoso a utilisé la [vue d’ensemble de PowerShell teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c3b32-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="c3b32-222">Sites de routage direct</span><span class="sxs-lookup"><span data-stu-id="c3b32-222">Direct Routing sites</span></span>

<span data-ttu-id="c3b32-223">Pour connecter l’infrastructure téléphonique locale de contoso à Microsoft Teams, l’administrateur de Contoso a suivi les étapes décrites dans [configurer le routage direct](direct-routing-configure.md) et examiné le [routage direct de la vidéo dans Microsoft teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) pour obtenir des instructions.</span><span class="sxs-lookup"><span data-stu-id="c3b32-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="c3b32-224">Contoso a également fait référence à la documentation de déploiement de routage directe par le fournisseur de SBC certifié.</span><span class="sxs-lookup"><span data-stu-id="c3b32-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="c3b32-225">Lorsque le routage direct a été configuré entre le système SBC et le système Microsoft Phone, il était nécessaire pour Contoso de tester la configuration.</span><span class="sxs-lookup"><span data-stu-id="c3b32-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="c3b32-226">Pour ce faire, les administrateurs contoso ont utilisé le client de testeur SIP évoqué dans les [mises à jour de la session de routage direct](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)de l’appareil 2019.</span><span class="sxs-lookup"><span data-stu-id="c3b32-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="c3b32-227">Le script client du testeur SIP et la documentation ont été téléchargés à partir du script PowerShell pour tester les connexions de la manette de session de routage direct.</span><span class="sxs-lookup"><span data-stu-id="c3b32-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="c3b32-228">Optimisation des éléments multimédias locaux</span><span class="sxs-lookup"><span data-stu-id="c3b32-228">Local Media Optimization</span></span>

<span data-ttu-id="c3b32-229">Contoso a appris à tirer parti de l’optimisation des contenus multimédias locaux dans les différentes régions du monde.</span><span class="sxs-lookup"><span data-stu-id="c3b32-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="c3b32-230">Les scénarios pris en charge pour Contoso sont décrits dans [optimisation des médias locaux pour le routage direct](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="c3b32-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="c3b32-231">La configuration de l’optimisation de média locale s’est effectuée en suivant les instructions de la part du fournisseur de SBC et de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c3b32-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="c3b32-232">Les étapes de configuration de l’optimisation de média locale sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3b32-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="c3b32-233">Configurer les sites utilisateur et SBC</span><span class="sxs-lookup"><span data-stu-id="c3b32-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="c3b32-234">Configurer l’SBC conformément à la spécification du fournisseur SBC</span><span class="sxs-lookup"><span data-stu-id="c3b32-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="c3b32-235">Ajouter des adresses IP de confiance externes à chaque site utilisé pour l’optimisation de médias locaux</span><span class="sxs-lookup"><span data-stu-id="c3b32-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="c3b32-236">Définissez la topologie du réseau.</span><span class="sxs-lookup"><span data-stu-id="c3b32-236">Define the network topology</span></span> 

- <span data-ttu-id="c3b32-237">Définir la topologie du réseau virtuel</span><span class="sxs-lookup"><span data-stu-id="c3b32-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="c3b32-238">Déterminer le mode : toujours contournement ou uniquement pour les utilisateurs locaux</span><span class="sxs-lookup"><span data-stu-id="c3b32-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="c3b32-239">Considérations en matière de réseau</span><span class="sxs-lookup"><span data-stu-id="c3b32-239">Networking considerations</span></span>

<span data-ttu-id="c3b32-240">Contoso disposait de nombreux utilisateurs qui devaient travailler à distance pour une période prolongée après leur activation pour le système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="c3b32-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="c3b32-241">Les utilisateurs ont utilisé VPN pour accéder à certaines applications métier.</span><span class="sxs-lookup"><span data-stu-id="c3b32-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="c3b32-242">Sur un réseau privé virtuel (VPN), les utilisateurs du système téléphonique ont rencontré une diminution de la qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="c3b32-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="c3b32-243">Pour résoudre le problème de qualité, il est possible d’implémenter une connexion VPN fractionnée par Contoso, qui permettait au trafic d’Office 365 de traverser Internet pendant que la connexion aux applications internes restait sur le VPN.</span><span class="sxs-lookup"><span data-stu-id="c3b32-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="c3b32-244">Pour mettre en œuvre une connexion VPN fractionnée, Contoso a suivi les recommandations de mise en œuvre de l' [encapsulation par VPN Split pour Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span><span class="sxs-lookup"><span data-stu-id="c3b32-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

 





