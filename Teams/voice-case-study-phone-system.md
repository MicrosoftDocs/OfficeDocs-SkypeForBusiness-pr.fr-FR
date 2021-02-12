---
title: Étude de cas Teams voix Contoso
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
description: Étude de cas Voix Teams pour une entreprise multinationale
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786026"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="59d69-103">Étude de cas Contoso : Phone System</span><span class="sxs-lookup"><span data-stu-id="59d69-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="59d69-104">En fonction de l’emplacement géographique et d’autres facteurs, les bureaux de Contoso ont été bureaux à l’aide des solutions téléphoniques suivantes :</span><span class="sxs-lookup"><span data-stu-id="59d69-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="59d69-105">Type de site A : skype entreprise Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="59d69-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="59d69-106">Type de site B : systèmes de téléphonie hérités traditionnels</span><span class="sxs-lookup"><span data-stu-id="59d69-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="59d69-107">Type de site C : combinaison de systèmes téléphoniques Skype Voix Entreprise et des systèmes de téléphonie hérités traditionnels</span><span class="sxs-lookup"><span data-stu-id="59d69-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="59d69-108">Pour implémenter une solution Microsoft Phone System pour l’ensemble de l’organisation, Contoso devait déterminer pour chaque type de site les options suivantes qui seraient utilisées avec le système téléphonique public commuté pour se connecter au réseau téléphonique commuté &mdash; &mdash; (PSTN) :</span><span class="sxs-lookup"><span data-stu-id="59d69-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="59d69-109">Système téléphonique avec forfait d’appels</span><span class="sxs-lookup"><span data-stu-id="59d69-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="59d69-110">Système téléphonique avec son propre opérateur PSTN via un routage direct</span><span class="sxs-lookup"><span data-stu-id="59d69-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="59d69-111">Combinaison du système téléphonique avec le plan d’appels et le système téléphonique avec un opérateur PSTN qui lui est propre via un routage direct</span><span class="sxs-lookup"><span data-stu-id="59d69-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="59d69-112">Pour déterminer la solution appropriée pour leur organisation, Contoso a utilisé les solutions téléphoniques Microsoft et les [appels](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) de session Ignite 2019 dans [Microsoft Teams.](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="59d69-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="59d69-113">Type de site A : skype entreprise Voix Entreprise</span><span class="sxs-lookup"><span data-stu-id="59d69-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="59d69-114">La Voix Entreprise Skype Entreprise contoso a été définie comme hub et s’est exprimé.</span><span class="sxs-lookup"><span data-stu-id="59d69-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="59d69-115">Il y avait un emplacement central qui maincait la passerelle PSTN dans la région qui fournissait la connexion au réseau PSTN pour les utilisateurs de Skype Entreprise Voix Entreprise dans le pays.</span><span class="sxs-lookup"><span data-stu-id="59d69-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="59d69-116">Bien souvent, ces sites satellitaires ne possèdent pas leur propre sortie Internet.</span><span class="sxs-lookup"><span data-stu-id="59d69-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="59d69-117">Les numéros pour ces utilisateurs résident sur la ligne SIP qui se connecte à un SBC existant.</span><span class="sxs-lookup"><span data-stu-id="59d69-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="59d69-118">Pour déterminer si le SBC déjà déployé est certifié pour le routage direct et la dérivation média, Contoso a coché la liste des contrôleurs de session certifiés pour le [routage direct.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="59d69-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="59d69-119">Les habitudes de numérotation de l’utilisateur étaient de composer un utilisateur sur l’ancien système téléphonique à l’aide d’une extension, même si l’utilisateur dispose d’un client Skype Entreprise disponible pour l’audio P2T.</span><span class="sxs-lookup"><span data-stu-id="59d69-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="59d69-120">Contoso a basé sa décision sur les questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="59d69-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="59d69-121">Q.</span><span class="sxs-lookup"><span data-stu-id="59d69-121">Q.</span></span> <span data-ttu-id="59d69-122">Devons-nous conserver les fonctionnalités fournies par notre déploiement local ?</span><span class="sxs-lookup"><span data-stu-id="59d69-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="59d69-123">A.</span><span class="sxs-lookup"><span data-stu-id="59d69-123">A.</span></span> <span data-ttu-id="59d69-124">Non</span><span class="sxs-lookup"><span data-stu-id="59d69-124">No</span></span> 

- <span data-ttu-id="59d69-125">Q.</span><span class="sxs-lookup"><span data-stu-id="59d69-125">Q.</span></span> <span data-ttu-id="59d69-126">Devons-nous interopérables avec des systèmes PBX tiers et d’autres équipements téléphoniques ?</span><span class="sxs-lookup"><span data-stu-id="59d69-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="59d69-127">A.</span><span class="sxs-lookup"><span data-stu-id="59d69-127">A.</span></span> <span data-ttu-id="59d69-128">Non</span><span class="sxs-lookup"><span data-stu-id="59d69-128">No</span></span> 

- <span data-ttu-id="59d69-129">Q.</span><span class="sxs-lookup"><span data-stu-id="59d69-129">Q.</span></span> <span data-ttu-id="59d69-130">Devons-nous conserver notre opérateur tiers actuel ?</span><span class="sxs-lookup"><span data-stu-id="59d69-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="59d69-131">A. Oui (pays régulés) et Non</span><span class="sxs-lookup"><span data-stu-id="59d69-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="59d69-132">Q.</span><span class="sxs-lookup"><span data-stu-id="59d69-132">Q.</span></span> <span data-ttu-id="59d69-133">Devons-nous obtenir le retour sur investissement sur des SBCs déployés ?</span><span class="sxs-lookup"><span data-stu-id="59d69-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="59d69-134">A. Oui et Non</span><span class="sxs-lookup"><span data-stu-id="59d69-134">A. Yes and No</span></span>  

- <span data-ttu-id="59d69-135">Q.</span><span class="sxs-lookup"><span data-stu-id="59d69-135">Q.</span></span> <span data-ttu-id="59d69-136">Les plans d’appel PSTN Microsoft sont-ils disponibles dans cette région ?</span><span class="sxs-lookup"><span data-stu-id="59d69-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="59d69-137">A. Oui et Non</span><span class="sxs-lookup"><span data-stu-id="59d69-137">A. Yes and No</span></span> 

<span data-ttu-id="59d69-138">En se basant sur les réponses à leurs questions, Contoso a décidé de :</span><span class="sxs-lookup"><span data-stu-id="59d69-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="59d69-139">Déplacez les utilisateurs situés dans une région dans laquelle des plans d’appel PSTN sont disponibles vers Phone System avec des forfaits d’appels.</span><span class="sxs-lookup"><span data-stu-id="59d69-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="59d69-140">Déplacer les utilisateurs situés dans une région où des plans d’appel RTC sont disponibles, les utilisateurs situés sur un site où le retour sur investissement sur les SBCs n’ont pas encore été satisfaits et les utilisateurs résidant dans un pays qui dispose d’une réglementation téléphonique vers un système téléphonique avec un routage direct.</span><span class="sxs-lookup"><span data-stu-id="59d69-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="59d69-141">Le diagramme suivant illustre le déploiement initial de Skype Voix Entreprise entreprise et la façon dont ce déploiement a été migré vers les plans d’appels Microsoft et le routage direct :</span><span class="sxs-lookup"><span data-stu-id="59d69-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![Diagramme montrant des états avant et après](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="59d69-143">Type de site B : systèmes de téléphonie hérités traditionnels</span><span class="sxs-lookup"><span data-stu-id="59d69-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="59d69-144">Contoso avait de nombreux bureaux qui tirent parti de systèmes de téléphonie hérités.</span><span class="sxs-lookup"><span data-stu-id="59d69-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="59d69-145">Un sous-ensemble d’utilisateurs avait un numéro de téléphone E1.64, tandis que d’autres n’avaient qu’une extension.</span><span class="sxs-lookup"><span data-stu-id="59d69-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="59d69-146">Ces numéros résident sur la ligne TDM de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="59d69-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="59d69-147">La numérotation intras site a été configurée en tirant parti d’un code de site devant l’extension pour déterminer l’emplacement d’itinéraire de l’appel.</span><span class="sxs-lookup"><span data-stu-id="59d69-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="59d69-148">Les habitudes de numérotation des utilisateurs deaient composer le numéro par poste.</span><span class="sxs-lookup"><span data-stu-id="59d69-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="59d69-149">Contoso a basé sa décision sur les questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="59d69-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="59d69-150">Q.</span><span class="sxs-lookup"><span data-stu-id="59d69-150">Q.</span></span> <span data-ttu-id="59d69-151">Devons-nous conserver les fonctionnalités fournies par notre déploiement local ?</span><span class="sxs-lookup"><span data-stu-id="59d69-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="59d69-152">A.</span><span class="sxs-lookup"><span data-stu-id="59d69-152">A.</span></span> <span data-ttu-id="59d69-153">Non</span><span class="sxs-lookup"><span data-stu-id="59d69-153">No</span></span> 

- <span data-ttu-id="59d69-154">Q.</span><span class="sxs-lookup"><span data-stu-id="59d69-154">Q.</span></span> <span data-ttu-id="59d69-155">Devons-nous interopérables avec des systèmes PBX tiers et d’autres équipements téléphoniques ?</span><span class="sxs-lookup"><span data-stu-id="59d69-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="59d69-156">A. Oui</span><span class="sxs-lookup"><span data-stu-id="59d69-156">A. Yes</span></span>

- <span data-ttu-id="59d69-157">Q.</span><span class="sxs-lookup"><span data-stu-id="59d69-157">Q.</span></span> <span data-ttu-id="59d69-158">Devons-nous conserver notre opérateur tiers actuel ?</span><span class="sxs-lookup"><span data-stu-id="59d69-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="59d69-159">A. Non</span><span class="sxs-lookup"><span data-stu-id="59d69-159">A. No</span></span> 

- <span data-ttu-id="59d69-160">Q.</span><span class="sxs-lookup"><span data-stu-id="59d69-160">Q.</span></span> <span data-ttu-id="59d69-161">L’offre d’appels PSTN de Microsoft est-elle disponible dans notre région ?</span><span class="sxs-lookup"><span data-stu-id="59d69-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="59d69-162">A. Oui et Non</span><span class="sxs-lookup"><span data-stu-id="59d69-162">A. Yes and No</span></span> 

<span data-ttu-id="59d69-163">En se basant sur les réponses à leurs questions, Contoso a décidé de :</span><span class="sxs-lookup"><span data-stu-id="59d69-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="59d69-164">Déplacez les utilisateurs situés dans une région dans laquelle des plans d’appel PSTN sont disponibles vers Phone System avec des forfaits d’appels.</span><span class="sxs-lookup"><span data-stu-id="59d69-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="59d69-165">Déplacer les utilisateurs qui ne sont pas situés dans une région dans laquelle des plans d’appel PSTN sont disponibles vers Phone System avec un routage direct.</span><span class="sxs-lookup"><span data-stu-id="59d69-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="59d69-166">Tenez à jour une connexion RSTN aux appareils analogiques critiques d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="59d69-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="59d69-167">Les diagrammes suivants montrent le déploiement d’origine du système hérité avec des sites distants et la migration vers un déploiement de routage direct avec l’optimisation des médias locaux :</span><span class="sxs-lookup"><span data-stu-id="59d69-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="59d69-168">**Déploiement hérité d’origine**  
 ![ Diagramme montrant des états avant et après](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="59d69-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="59d69-169">**Déploiement avec routage direct**</span><span class="sxs-lookup"><span data-stu-id="59d69-169">**Deployment with Direct Routing**</span></span>

![Diagramme montrant des états avant et après](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="59d69-171">Type de site C : combinaison de systèmes téléphoniques Skype Voix Entreprise et de systèmes de téléphonie hérités traditionnels</span><span class="sxs-lookup"><span data-stu-id="59d69-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="59d69-172">Contoso Skype Entreprise Voix Entreprise les numéros des utilisateurs résident sur la ligne SIP de la ligne SBC de l’opérateur.</span><span class="sxs-lookup"><span data-stu-id="59d69-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="59d69-173">Les numéros des systèmes téléphoniques traditionnels résidant sur la ligne TDM de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="59d69-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="59d69-174">Contoso a basé sa décision sur les questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="59d69-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="59d69-175">Q.</span><span class="sxs-lookup"><span data-stu-id="59d69-175">Q.</span></span> <span data-ttu-id="59d69-176">Devons-nous conserver les fonctionnalités fournies par notre déploiement local ?</span><span class="sxs-lookup"><span data-stu-id="59d69-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="59d69-177">A.</span><span class="sxs-lookup"><span data-stu-id="59d69-177">A.</span></span> <span data-ttu-id="59d69-178">Non</span><span class="sxs-lookup"><span data-stu-id="59d69-178">No</span></span> 

- <span data-ttu-id="59d69-179">Q.</span><span class="sxs-lookup"><span data-stu-id="59d69-179">Q.</span></span> <span data-ttu-id="59d69-180">Devons-nous interopérables avec des systèmes PBX tiers et d’autres équipements téléphoniques ?</span><span class="sxs-lookup"><span data-stu-id="59d69-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="59d69-181">A. Non</span><span class="sxs-lookup"><span data-stu-id="59d69-181">A. No</span></span> 

- <span data-ttu-id="59d69-182">Q.</span><span class="sxs-lookup"><span data-stu-id="59d69-182">Q.</span></span> <span data-ttu-id="59d69-183">Devons-nous conserver notre opérateur tiers actuel ?</span><span class="sxs-lookup"><span data-stu-id="59d69-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="59d69-184">A. Non</span><span class="sxs-lookup"><span data-stu-id="59d69-184">A. No</span></span> 

- <span data-ttu-id="59d69-185">Q.</span><span class="sxs-lookup"><span data-stu-id="59d69-185">Q.</span></span> <span data-ttu-id="59d69-186">Devons-nous obtenir le retour sur investissement sur des SBCs déployés ?</span><span class="sxs-lookup"><span data-stu-id="59d69-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="59d69-187">A. Oui et Non</span><span class="sxs-lookup"><span data-stu-id="59d69-187">A. Yes and No</span></span>  

- <span data-ttu-id="59d69-188">Q.</span><span class="sxs-lookup"><span data-stu-id="59d69-188">Q.</span></span> <span data-ttu-id="59d69-189">Le plan d’appel PSTN de Microsoft est-il disponible dans cette région ?</span><span class="sxs-lookup"><span data-stu-id="59d69-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="59d69-190">A. Non</span><span class="sxs-lookup"><span data-stu-id="59d69-190">A. No</span></span> 

<span data-ttu-id="59d69-191">En se basant sur les réponses à leurs questions, Contoso a décidé des solutions suivantes :</span><span class="sxs-lookup"><span data-stu-id="59d69-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="59d69-192">Pour les utilisateurs téléphoniques hérités qui seront activés pour le routage direct, Contoso a porté les numéros de la ligne TDM vers la ligne SIP pour le SBC, étant donné que le SBC est certifié pour le routage direct.</span><span class="sxs-lookup"><span data-stu-id="59d69-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="59d69-193">Pour prendre en charge un sous-ensemble d’utilisateurs qui passe au système téléphonique et pour permettre un routage continu via le système hérité, le système de téléphonie hérité a été créé comme le prochain saut vers le SBC.</span><span class="sxs-lookup"><span data-stu-id="59d69-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="59d69-194">En outre, pour encourager le changement de comportement des utilisateurs et supprimer la dépendance vis-à-vis des numéros d’extension inter et intra-sites, Contoso a fourni des conseils pour utiliser Teams pour tous les appels internes.</span><span class="sxs-lookup"><span data-stu-id="59d69-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="59d69-195">Les diagrammes suivants montrent le déploiement d’origine de la version Voix Entreprise et de l’ancien système téléphonique Skype Entreprise, et la migration vers un déploiement mixte à l’aide du routage direct :</span><span class="sxs-lookup"><span data-stu-id="59d69-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="59d69-196">**Déploiement mixte d’origine** 
 ![ Diagramme montrant avant l’état](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="59d69-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="59d69-197">**Déploiement mixte avec routage direct** 
 ![ Diagramme montrant avant l’état](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="59d69-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="59d69-198">Forfaits d’appel</span><span class="sxs-lookup"><span data-stu-id="59d69-198">Calling Plans</span></span>

<span data-ttu-id="59d69-199">Pour déterminer les configurations requises pour les plans d’appels, Contoso a examiné les principales décisions de [déploiement du plan d’appels.](calling-plan-landing-page.md#core-deployment-decisions)</span><span class="sxs-lookup"><span data-stu-id="59d69-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="59d69-200">Les décisions qui s’en découlent ont été prises :</span><span class="sxs-lookup"><span data-stu-id="59d69-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="59d69-201">Q.</span><span class="sxs-lookup"><span data-stu-id="59d69-201">Q.</span></span> <span data-ttu-id="59d69-202">Mes utilisateurs ont-ils besoin d’appels internationaux ?</span><span class="sxs-lookup"><span data-stu-id="59d69-202">Do my users need international calling?</span></span><br> <span data-ttu-id="59d69-203">A. Oui</span><span class="sxs-lookup"><span data-stu-id="59d69-203">A. Yes</span></span> 

- <span data-ttu-id="59d69-204">Q.</span><span class="sxs-lookup"><span data-stu-id="59d69-204">Q.</span></span> <span data-ttu-id="59d69-205">Mes utilisateurs ont-ils chacun un numéro de téléphone directement vers l’intérieur ?</span><span class="sxs-lookup"><span data-stu-id="59d69-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="59d69-206">R. Pas aujourd’hui.</span><span class="sxs-lookup"><span data-stu-id="59d69-206">A. Not today.</span></span> <span data-ttu-id="59d69-207">Tous les utilisateurs activés recevront un DID.</span><span class="sxs-lookup"><span data-stu-id="59d69-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="59d69-208">Q.</span><span class="sxs-lookup"><span data-stu-id="59d69-208">Q.</span></span> <span data-ttu-id="59d69-209">Dois-je masquer ou désactiver l’ID de l’appelant ?</span><span class="sxs-lookup"><span data-stu-id="59d69-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="59d69-210">A. L’ID d’appelant d’un utilisateur est masquée sur le numéro local de Contoso.</span><span class="sxs-lookup"><span data-stu-id="59d69-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="59d69-211">Routage direct</span><span class="sxs-lookup"><span data-stu-id="59d69-211">Direct Routing</span></span>

<span data-ttu-id="59d69-212">Contoso a participé à Ignite pour rester à jour sur les fonctionnalités d’Office 365, y compris celles disponibles avec le système téléphonique et le routage direct.</span><span class="sxs-lookup"><span data-stu-id="59d69-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="59d69-213">Les dirigeants techniques et les architectes se sont servis des conseils fournis lors de l’édition d’Ignite 2019 pour déterminer leur direction.</span><span class="sxs-lookup"><span data-stu-id="59d69-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="59d69-214">Sessions clés utilisées :</span><span class="sxs-lookup"><span data-stu-id="59d69-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="59d69-215">Planifier le succès avec le routage direct de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="59d69-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="59d69-216">Mises à jour pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="59d69-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="59d69-217">Configuration</span><span class="sxs-lookup"><span data-stu-id="59d69-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="59d69-218">Sites Forfaits d’appels</span><span class="sxs-lookup"><span data-stu-id="59d69-218">Calling Plans sites</span></span>

<span data-ttu-id="59d69-219">Pour obtenir des licences et attribuer des numéros de téléphone aux utilisateurs, Contoso a suivi les étapes de la procédure [Configurer les forfaits d’appels.](set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="59d69-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="59d69-220">En raison du nombre d’utilisateurs devant se voir attribuer des numéros de téléphone, Contoso a décidé d’utiliser PowerShell pour affecter les numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="59d69-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="59d69-221">Pour découvrir comment attribuer des numéros à l’aide de PowerShell en plus d’autres paramètres, Contoso a utilisé la vue d’ensemble &mdash; &mdash; de Teams [PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="59d69-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="59d69-222">Sites de routage direct</span><span class="sxs-lookup"><span data-stu-id="59d69-222">Direct Routing sites</span></span>

<span data-ttu-id="59d69-223">Pour connecter l’infrastructure téléphonique locale de Contoso à Microsoft Teams, l’administrateur de Contoso a suivi les étapes de la procédure Configurer le [routage](direct-routing-configure.md) direct et examiné la vidéo [Routage](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) direct dans Microsoft Teams pour obtenir des instructions.</span><span class="sxs-lookup"><span data-stu-id="59d69-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="59d69-224">Contoso fait également référence à la documentation relative au déploiement du routage direct par le fournisseur SBC certifié.</span><span class="sxs-lookup"><span data-stu-id="59d69-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="59d69-225">Une fois le routage direct configuré entre le système SBC et Microsoft Phone System, Contoso devait tester la configuration.</span><span class="sxs-lookup"><span data-stu-id="59d69-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="59d69-226">Pour ce faire, les administrateurs Contoso ont utilisé le client de test SIP évoqué lors de la session Mises à jour pour le routage direct sur [Ignite 2019.](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="59d69-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="59d69-227">Le script et la documentation du client test SIP ont été téléchargés à partir du script PowerShell pour tester les connexions du contrôleur de bordure de session de routage direct.</span><span class="sxs-lookup"><span data-stu-id="59d69-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="59d69-228">Optimisation des médias locaux</span><span class="sxs-lookup"><span data-stu-id="59d69-228">Local Media Optimization</span></span>

<span data-ttu-id="59d69-229">Contoso a vu l’opportunité de tirer parti de l’optimisation des médias locaux dans les différentes régions du monde entier.</span><span class="sxs-lookup"><span data-stu-id="59d69-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="59d69-230">Les scénarios pris en charge pour Contoso sont décrits dans l’optimisation des médias [locaux pour le routage direct.](direct-routing-media-optimization.md)</span><span class="sxs-lookup"><span data-stu-id="59d69-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="59d69-231">La configuration de l’optimisation des médias locaux a été effectuée en suivant les conseils du fournisseur SBC et de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="59d69-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="59d69-232">Les étapes de configuration de l’optimisation des médias locaux sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="59d69-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="59d69-233">Configurer l’utilisateur et les sites SBC</span><span class="sxs-lookup"><span data-stu-id="59d69-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="59d69-234">Configurez le SBC en fonction de la spécification du fournisseur SBC,</span><span class="sxs-lookup"><span data-stu-id="59d69-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="59d69-235">Ajouter des adresses IP fiables externes à chaque site utilisé pour l’optimisation des médias locaux</span><span class="sxs-lookup"><span data-stu-id="59d69-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="59d69-236">Définir la topologie de réseau</span><span class="sxs-lookup"><span data-stu-id="59d69-236">Define the network topology</span></span> 

- <span data-ttu-id="59d69-237">Définir la topologie de réseau virtuel</span><span class="sxs-lookup"><span data-stu-id="59d69-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="59d69-238">Déterminer le mode : Toujours contourner ou uniquement pour les utilisateurs locaux</span><span class="sxs-lookup"><span data-stu-id="59d69-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="59d69-239">Considérations en relation avec la mise en réseau</span><span class="sxs-lookup"><span data-stu-id="59d69-239">Networking considerations</span></span>

<span data-ttu-id="59d69-240">Contoso avait un nombre d’utilisateurs qui devaient travailler à distance pendant une période prolongée après avoir été activés pour Phone System.</span><span class="sxs-lookup"><span data-stu-id="59d69-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="59d69-241">Les utilisateurs utilisaient le vpn pour accéder à certaines applications Métier.</span><span class="sxs-lookup"><span data-stu-id="59d69-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="59d69-242">Sur un réseau VPN, les utilisateurs du système téléphonique ont connu une dégradation de la qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="59d69-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="59d69-243">Pour résoudre le problème de qualité, Contoso a implémenté la tunnelliser fractionnée VPN, qui permettait à son trafic Office 365 de traverser Internet alors que la connexion aux applications internes restait sur le VPN.</span><span class="sxs-lookup"><span data-stu-id="59d69-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="59d69-244">Pour implémenter la tunnelliser fractionnement VPN, Contoso a suivi les recommandations de la tunnelliser fractionnement [VPN pour Office 365.](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel)</span><span class="sxs-lookup"><span data-stu-id="59d69-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

 





